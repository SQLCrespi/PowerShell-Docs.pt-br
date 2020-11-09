---
title: Adicionar suporte a Credential às funções do PowerShell
description: Como adicionar parâmetros de credencial a seus scripts, funções e cmdlets do PowerShell.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: 3e4a3f41ccbca1cf97f2e96fd60f22d89be7bc5a
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354619"
---
# <a name="add-credential-support-to-powershell-functions"></a>Adicionar suporte a Credential às funções do PowerShell

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@joshduffney][]. Este artigo foi editado para inclusão neste site. A equipe do PowerShell agradece a Josh por compartilhar este conteúdo conosco. Confira o blog dele em [duffney.io][].

Este artigo mostra como adicionar parâmetros de credencial às funções do PowerShell e por que é conveniente fazer isso. Um parâmetro de credencial permite que você execute a função ou cmdlet como um usuário diferente. Ele é comumente usado para executar a função ou cmdlet como uma conta de usuário com privilégios elevados.

Por exemplo, o cmdlet `New-ADUser` tem um parâmetro **Credential** , para o qual você pode fornecer credenciais de administrador de domínio a fim de criar uma conta em um domínio. Supondo que sua conta normal que está executando a sessão do PowerShell ainda não tenha esse acesso.

## <a name="creating-credential-object"></a>Criar um objeto de credencial

O objeto [PSCredential][] representa um conjunto de credenciais de segurança, como nome de usuário e senha. O objeto pode ser passado como um parâmetro para uma função executada como a conta de usuário nesse objeto de credencial. Há algumas maneiras de criar um objeto de credencial. A primeira maneira é usar o cmdlet do PowerShell `Get-Credential`. Quando você faz a execução sem parâmetros, é solicitado um nome de usuário e uma senha. Ou é possível chamar o cmdlet com alguns parâmetros opcionais.

Para especificar o nome de domínio e nome de usuário com antecedência, você pode usar os parâmetros **Credential** ou **UserName**. Ao usar o parâmetro **UserName** , você também deve fornecer um valor de **Message**. O código a seguir demonstra o uso do cmdlet. Você também pode armazenar o objeto de credencial em uma variável para poder usar a credencial várias vezes. No exemplo abaixo, o objeto de credencial é armazenado na variável `$Cred`.

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

Às vezes, não será possível usar o método interativo de criação de objetos de credencial mostrado no exemplo anterior. A maioria das ferramentas de automação requer um método não interativo. Para criar uma credencial sem interação do usuário, crie uma cadeia de caracteres segura que contenha a senha. Depois, passe a cadeia de caracteres segura e o nome de usuário para o método `System.Management.Automation.PSCredential()`.

Use o seguinte comando para criar uma cadeia de caracteres segura que contém a senha:

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

Tanto o parâmetro **AsPlainText** quanto o **Force** são obrigatórios. Sem esses parâmetros, você recebe uma mensagem avisando que não deve passar texto sem formatação para uma cadeia de caracteres segura. O PowerShell retorna esse aviso porque a senha de texto sem formatação é registrada em vários logs. Depois de criar uma cadeia de caracteres segura, você precisa passá-la para o método `PSCredential()` a fim de criar o objeto de credencial. No exemplo a seguir, a variável `$password` contém a cadeia de caractere segura e `$Cred` contém o objeto de credencial.

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

Agora que você sabe como criar objetos de credencial, pode adicionar parâmetros de credencial às funções do PowerShell.

## <a name="adding-a-credential-parameter"></a>Adicionar um parâmetro de credencial

Assim como qualquer outro parâmetro, comece adicionando-o ao bloco `param` de sua função.
Recomendamos nomear o parâmetro como `$Credential` porque é isso que os cmdlets existentes do PowerShell usam. O tipo do parâmetro deve ser `[System.Management.Automation.PSCredential]`.

O exemplo a seguir mostra o bloco de parâmetro para uma função chamada `Get-Something`. Ela tem dois parâmetros: `$Name` e `$Credential`.

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

O código nesse exemplo é suficiente para ter um parâmetro de credencial funcional. no entanto, você pode adicionar alguns elementos para torná-lo mais robusto.

- Adicione o atributo de validação `[ValidateNotNull()]` para verificar se o valor está sendo passado para **Credential**. Se o valor do parâmetro for nulo, esse atributo impedirá que a função seja executada com credenciais inválidas.

- Adicione `[System.Management.Automation.Credential()]`. Isso permite que você passe um nome de usuário como uma cadeia de caracteres e tenha um prompt interativo para a senha.

- Defina um valor padrão do parâmetro `$Credential` para `[System.Management.Automation.PSCredential]::Empty`. Sua função você pode estar passando esse objeto `$Credential` para os cmdlets do PowerShell existentes. Fornecer um valor nulo ao cmdlet chamado dentro de sua função causa um erro. Para evitar isso, forneça um objeto de credencial vazio.

> [!TIP]
> Alguns cmdlets que aceitam um parâmetro de credencial não dão suporte a `[System.Management.Automation.PSCredential]::Empty` como deveriam. Confira a seção [Lidar com cmdlets herdados](#dealing-with-legacy-cmdlets) para obter uma solução alternativa.

## <a name="using-credential-parameters"></a>Usar parâmetros de credencial

O exemplo a seguir demonstra como usar parâmetros de credencial. Este exemplo mostra uma função chamada `Set-RemoteRegistryValue`, extraída do [The Pester Book][]. Essa função define o parâmetro de credencial usando as técnicas descritas na seção anterior. A função chama `Invoke-Command` usando a variável `$Credential` criada por ela. Isso permite que você altere o usuário que está executando `Invoke-Command`. Como o valor padrão de `$Credential` é uma credencial vazia, a função pode ser executada sem o fornecimento de credenciais.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

As seções a seguir mostram métodos diferentes de fornecimento de credenciais para `Set-RemoteRegistryValue`.

### <a name="prompting-for-credentials"></a>Solicitar credenciais

Usar `Get-Credential` entre parênteses `()` durante o tempo de execução faz com que `Get-credential` seja executado primeiro. Você será solicitado a informar um nome de usuário e senha. Você pode usar os parâmetros **Credential** ou **UserName** de `Get-credential` para preencher previamente o nome de usuário e o domínio. O exemplo a seguir usa uma técnica chamada nivelamento a fim de passar parâmetros para a função `Set-RemoteRegistryValue`. Para saber mais sobre o nivelamento, confira o artigo [Sobre o nivelamento][].

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Obter uma credencial em tempo de execução](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

Usar o `(Get-Credential)` parece complicado. Normalmente, quando você usa o parâmetro **Credential** com apenas um nome de usuário, o cmdlet solicita a senha automaticamente. O atributo `[System.Management.Automation.Credential()]` habilita esse comportamento.

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Solicita credenciais](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> Para definir o valor de registro mostrado, esses exemplos presumem que você possui os recursos do **Servidor da Web** do Windows instalados. Execute `Install-WindowsFeature Web-Server` e `Install-WindowsFeature web-mgmt-tools`, se necessário.

### <a name="provide-credentials-in-a-variable"></a>Fornecer credenciais em uma variável

Você também pode preencher uma variável de credencial com antecedência e passá-la para o parâmetro **Credential** da função `Set-RemoteRegistryValue`. Use esse método com ferramentas de CI/CD (integração contínua/implantação contínua), como Jenkins, TeamCity e Octopus Deploy. Para obter um exemplo de uso do Jenkins, confira a postagem no blog de Hodge [Automatizar com Jenkins e PowerShell no Windows – Parte 2][].

Este exemplo usa o método .NET para criar o objeto de credencial e uma cadeia de caracteres segura para passar a senha.

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

Nesse exemplo, a cadeia de caracteres segura é criada usando uma senha com texto não criptografado. Todas as ferramentas de CI/CD mencionadas anteriormente têm um método seguro de fornecimento de senha em tempo de execução. Ao utilizá-las, substitua a senha de texto sem formatação pela variável definida na ferramenta de CI/CD que você usa.

### <a name="run-without-credentials"></a>Executar sem credenciais

Como o `$Credential` usa como padrão um objeto de credencial vazio, você pode executar o comando sem credenciais, conforme mostrado no seguinte exemplo:

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a>Lidar com cmdlets herdados

Nem todos os cmdlets dão suporte a objetos de credencial ou permitem credenciais vazias. Em vez disso, o cmdlet prefere usar os parâmetros de nome de usuário e senha como cadeias de caracteres. Para solucionar essa limitação, há algumas alternativas.

### <a name="using-if-else-to-handle-empty-credentials"></a>Usar if-else para lidar com credenciais vazias

Neste cenário, o cmdlet que você deseja executar não aceita um objeto de credencial vazio. Este exemplo adicionará o parâmetro **Credential** a `Invoke-Command` somente se ele não estiver vazio. Caso contrário, executará o `Invoke-Command` sem o parâmetro **Credential**.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a>Usar nivelamento para lidar com credenciais vazias

Este exemplo usa o nivelamento de parâmetro para chamar o cmdlet herdado. O objeto `$Credential` é adicionado condicionalmente à tabela de hash de nivelamento e evita a necessidade de repetir o bloco de script `Invoke-Command`. Para saber mais sobre o nivelamento dentro de funções, confira a postagem no blog [Nivelar parâmetros dentro de funções avançadas][].

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a>Trabalhar com cadeias de caracteres como senha

O cmdlet `Invoke-Sqlcmd` é um dos que aceitam uma cadeia de caracteres como senha.
O `Invoke-Sqlcmd` permite executar instruções SQL simples de inserção, atualização e exclusão. O `Invoke-Sqlcmd` requer um nome de usuário e senha com texto não criptografado, em vez de um objeto de credencial mais seguro. Este exemplo mostra como extrair o nome de usuário e a senha de um objeto de credencial.

A função `Get-AllSQLDatabases` neste exemplo chama o cmdlet `Invoke-Sqlcmd` a fim de consultar um servidor SQL para todos os seus bancos de dados. A função define um parâmetro **Credential** com o mesmo atributo usado nos exemplos anteriores. Como o nome de usuário e a senha existem na variável `$Credential`, você pode extrair esses valores para usar com `Invoke-Sqlcmd`.

O nome de usuário está disponível na propriedade **UserName** da variável `$Credential`. Para obter a senha, você deve usar o método `GetNetworkCredential()` do objeto `$Credential`. Os valores são extraídos em variáveis que são adicionadas a uma tabela de hash usada para nivelamento dos parâmetros para `Invoke-Sqlcmd`.

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a>Gerenciamento de credencial de aprendizagem contínua

Criar e armazenar objetos de credenciais com segurança pode ser difícil. Os recursos a seguir podem ajudar você a manter suas credenciais do PowerShell.

- [BetterCredentials][]
- [Cofre da Chave do Azure][]
- [Projeto de Cofre][]
- [Módulo SecretManagement][]

<!-- link references -->
[versão original]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Cofre da Chave do Azure]: https://azure.microsoft.com/services/key-vault/
[Projeto de Cofre]: https://www.vaultproject.io/
[Nivelar parâmetros dentro de funções avançadas]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Automatizar com Jenkins e PowerShell no Windows – Parte 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Módulo SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
