---
description: Descreve como acessar variáveis de ambiente do Windows no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: 4b5894822f4436f127ed4789fd8008a0e7f2f2df
ms.sourcegitcommit: f5986121386c81acddcf324eb0526d7d092bcc8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98584654"
---
# <a name="about-environment-variables"></a>Sobre variáveis de ambiente

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como acessar variáveis de ambiente do Windows no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

As variáveis de ambiente armazenam informações sobre o ambiente do sistema operacional. Essas informações incluem detalhes como o caminho do sistema operacional, o número de processadores usados pelo sistema operacional e o local das pastas temporárias.

As variáveis de ambiente armazenam dados que são usados pelo sistema operacional e outros programas. Por exemplo, a `WINDIR` variável de ambiente contém o local do diretório de instalação do Windows. Os programas podem consultar o valor dessa variável para determinar onde os arquivos do sistema operacional Windows estão localizados.

O PowerShell pode acessar e gerenciar variáveis de ambiente em qualquer uma das plataformas de sistema operacional com suporte. O provedor de ambiente do PowerShell simplifica esse processo, facilitando a exibição e a alteração das variáveis de ambiente.

Variáveis de ambiente, ao contrário de outros tipos de variáveis no PowerShell, são herdadas por processos filho, como trabalhos em segundo plano locais e as sessões em que os membros do módulo são executados. Isso torna as variáveis de ambiente adequadas para armazenar valores que são necessários nos processos pai e filho.

## <a name="using-and-changing-environment-variables"></a>Usando e alterando variáveis de ambiente

No Windows, as variáveis de ambiente podem ser definidas em três escopos:

- Escopo da máquina (ou do sistema)
- Escopo do usuário
- Escopo do processo

O escopo do _processo_ contém as variáveis de ambiente disponíveis no processo atual ou na sessão do PowerShell. Essa lista de variáveis é herdada do processo pai e é construída a partir das variáveis nos escopos de _computador_ e de _usuário_ . As plataformas baseadas em UNIX têm apenas o escopo do _processo_ .

Você pode exibir e alterar os valores das variáveis de ambiente sem usar um cmdlet usando uma sintaxe de variável com o provedor de ambiente. Para exibir o valor de uma variável de ambiente, use a seguinte sintaxe:

```
$Env:<variable-name>
```

Por exemplo, para exibir o valor da `WINDIR` variável de ambiente, digite o seguinte comando no prompt de comando do PowerShell:

```powershell
$Env:windir
```

Nessa sintaxe, o cifrão ( `$` ) indica uma variável e o nome da unidade ( `Env:` ) indica uma variável de ambiente seguida pelo nome da variável ( `windir` ).

Quando você altera as variáveis de ambiente no PowerShell, a alteração afeta apenas a sessão atual. Esse comportamento é semelhante ao comportamento do `Set` comando no Shell de comando do Windows e no `Setenv` comando em ambientes baseados em UNIX. Para alterar valores nos escopos do computador ou do usuário, você deve usar os métodos da classe **System. Environment** .

Para fazer alterações em variáveis no escopo do computador, também deve ter permissão. Se você tentar alterar um valor sem permissão suficiente, o comando falhará e o PowerShell exibirá um erro.

Você pode alterar os valores de variáveis sem usar um cmdlet usando a seguinte sintaxe:

```powershell
$Env:<variable-name> = "<new-value>"
```

Por exemplo, para acrescentar `;c:\temp` ao valor da variável de `Path` ambiente, use a seguinte sintaxe:

```powershell
$Env:Path += ";c:\temp"
```

No Linux ou macOS, os dois-pontos ( `:` ) no comando separam o novo caminho do caminho que o precede na lista.

```powershell
$Env:PATH += ":/usr/local/temp"
```

Você também pode usar os cmdlets do item, como `Set-Item` , `Remove-Item` e `Copy-Item` para alterar os valores das variáveis de ambiente. Por exemplo, para usar o `Set-Item` cmdlet para acrescentar `;c:\temp` ao valor da variável de `Path` ambiente, use a seguinte sintaxe:

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

Nesse comando, o valor é colocado entre parênteses para que seja interpretado como uma unidade.

## <a name="environment-variables-that-store-preferences"></a>Variáveis de ambiente que armazenam preferências

Os recursos do PowerShell podem usar variáveis de ambiente para armazenar as preferências do usuário.
Essas variáveis funcionam como variáveis de preferência, mas são herdadas por sessões filho das sessões nas quais elas são criadas. Para obter mais informações sobre variáveis de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).

As variáveis de ambiente que armazenam as preferências incluem:

- PSExecutionPolicyPreference

  Armazena a política de execução definida para a sessão atual. Essa variável de ambiente existe somente quando você define uma política de execução para uma única sessão.
  Você pode fazer isso de duas maneiras diferentes.

  - Inicie uma sessão na linha de comando usando o parâmetro **ExecutionPolicy** para definir a política de execução para a sessão.

  - Use o cmdlet `Set-ExecutionPolicy`. Use o parâmetro de escopo com um valor de "processo".

    Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).

- PSModuleAnalysisCachePath

  O PowerShell fornece controle sobre o arquivo usado para armazenar em cache dados sobre módulos e seus cmdlets. O cache é lido na inicialização durante a pesquisa de um comando e é gravado em um thread em segundo plano depois que um módulo é importado.

  O local padrão do cache é:

  - Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`
  - PowerShell 6,0 e superior: `$env:LOCALAPPDATA\Microsoft\PowerShell`
  - Padrão não Windows: `~/.cache/powershell`

  O nome de arquivo padrão para o cache é `ModuleAnalysisCache` . Quando você tem várias instâncias do PowerShell instaladas, o nome de arquivo inclui um sufixo hexadecimal para que haja um nome de arquivo exclusivo por instalação.

  > [!NOTE]
  > Se a descoberta de comando não estiver funcionando corretamente, por exemplo, o IntelliSense mostrará os comandos que não existem, você poderá excluir o arquivo de cache. O cache é recriado na próxima vez que você iniciar o PowerShell.

  Para alterar o local padrão do cache, defina a variável de ambiente antes de iniciar o PowerShell. As alterações nessa variável de ambiente afetam apenas os processos filho. O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos.

  Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  Isso define o caminho para o dispositivo **nul** . O PowerShell não pode gravar no caminho, mas nenhum erro é retornado. Você pode ver os erros relatados usando um rastreador:

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- PSDisableModuleAnalysisCacheCleanup

  Ao gravar o cache de análise de módulo, o PowerShell verifica se há módulos que não existem mais para evitar um cache desnecessariamente grande. Às vezes, essas verificações não são desejáveis; nesse caso, você pode desativá-las definindo esse valor de variável de ambiente como `1` .

  Definir essa variável de ambiente entra em vigor imediatamente no processo atual.

- PSModulePath

  A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.

  Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:

  - Locais de todo o sistema: essas pastas contêm módulos que acompanham o PowerShell. Os módulos são armazenados no `$PSHOME\Modules` local. Além disso, esse é o local onde os módulos de gerenciamento do Windows estão instalados.

  - Módulos instalados pelo usuário: são módulos instalados pelo usuário.
    `Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários. Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).

    - No Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME\Documents\PowerShell\Modules` pasta. O local do escopo **AllUsers** é `$env:ProgramFiles\PowerShell\Modules` .
    - Em sistemas não Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME/.local/share/powershell/Modules` pasta. O local do escopo **AllUsers** é `/usr/local/share/powershell/Modules` .

  Além disso, os programas de instalação que instalam módulos em outros diretórios, como o diretório arquivos de programas, podem acrescentar seus locais ao valor de `$env:PSModulePath` .

  Para obter mais informações, consulte [about_PSModulePath](about_PSModulePath.md).

## <a name="managing-environment-variables"></a>Gerenciar variáveis de ambiente

O PowerShell fornece vários métodos diferentes para gerenciar variáveis de ambiente.

- A unidade do provedor de ambiente
- Os cmdlets do item
- A classe **System. Environment** do .net
- No Windows, o painel de controle do sistema

### <a name="using-the-environment-provider"></a>Usando o provedor de ambiente

Cada variável de ambiente é representada por uma instância da classe **System. Collections. DictionaryEntry** . Em cada objeto **DictionaryEntry** , o nome da variável de ambiente é a chave de dicionário. O valor da variável é o valor do dicionário.

Para exibir as propriedades e os métodos do objeto que representa uma variável de ambiente no PowerShell, use o `Get-Member` cmdlet. Por exemplo, para exibir os métodos e as propriedades de todos os objetos na `Env:` unidade, digite:

```powershell
Get-Item -Path Env:* | Get-Member
```

O provedor de ambiente do PowerShell permite que você acesse variáveis de ambiente em uma unidade do PowerShell (a `Env:` unidade). Essa unidade é muito parecida com uma unidade do sistema de arquivos. Para ir para a `Env:` unidade, digite:

```powershell
Set-Location Env:
```

Use os cmdlets de conteúdo para obter ou definir os valores de uma variável de ambiente.

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

Você pode exibir as variáveis de ambiente na `Env:` unidade de qualquer outra unidade do PowerShell e pode entrar na `Env:` unidade para exibir e alterar as variáveis de ambiente.

### <a name="using-item-cmdlets"></a>Usando cmdlets de item

Quando você se referir a uma variável de ambiente, digite o `Env:` nome da unidade seguido pelo nome da variável. Por exemplo, para exibir o valor da `COMPUTERNAME` variável de ambiente, digite:

```powershell
Get-ChildItem Env:Computername
```

Para exibir os valores de todas as variáveis de ambiente, digite:

```powershell
Get-ChildItem Env:
```

Como as variáveis de ambiente não têm itens filho, a saída de `Get-Item` e `Get-ChildItem` é a mesma.

Por padrão, o PowerShell exibe as variáveis de ambiente na ordem em que as recupera. Para classificar a lista de variáveis de ambiente por nome de variável, redirecione a saída de um `Get-ChildItem` comando para o `Sort-Object` cmdlet. Por exemplo, em qualquer unidade do PowerShell, digite:

```powershell
Get-ChildItem Env: | Sort Name
```

Você também pode entrar na `Env:` unidade usando o `Set-Location` cmdlet:

```powershell
Set-Location Env:
```

Quando estiver na `Env:` unidade, você poderá omitir o `Env:` nome da unidade do caminho. Por exemplo, para exibir todas as variáveis de ambiente, digite:

```powershell
PS Env:\> Get-ChildItem
```

Para exibir o valor da `COMPUTERNAME` variável de dentro da `Env:` unidade, digite:

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a>Salvando alterações em variáveis de ambiente

Para fazer uma alteração persistente em uma variável de ambiente no Windows, use o painel de controle do sistema. Selecione **Configurações avançadas do sistema**. Na guia **avançado** , clique em **variável de ambiente...**. Você pode adicionar ou editar variáveis de ambiente existentes nos escopos de **usuário** e **sistema** (computador). O Windows grava esses valores no registro para que eles persistam entre as sessões e reinicializações do sistema.

Como alternativa, você pode adicionar ou alterar variáveis de ambiente no seu perfil do PowerShell. Esse método funciona para qualquer versão do PowerShell em qualquer plataforma com suporte.

### <a name="using-systemenvironment-methods"></a>Usando métodos System. Environment

A classe **System. Environment** fornece os métodos **GetEnvironmentVariable** e **SetEnvironmentVariable não** que permitem especificar o escopo da variável.

O exemplo a seguir usa o método **GetEnvironmentVariable** para obter a configuração do computador `PSModulePath` e o método **SetEnvironmentVariable não** para adicionar o `C:\Program Files\Fabrikam\Modules` caminho ao valor.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

Para obter mais informações sobre os métodos da classe **System. Environment** , consulte [métodos de ambiente](/dotnet/api/system.environment).

## <a name="see-also"></a>CONSULTE TAMBÉM

- [Ambiente (provedor)](../About/about_Environment_Provider.md)
- [about_Modules](about_Modules.md)

