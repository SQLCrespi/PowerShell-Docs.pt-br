---
description: Descreve como criar e usar um perfil do PowerShell.
keywords: powershell, cmdlet
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: 17b89df0ec0ce88127385287cee560996af7a628
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195994"
---
# <a name="about-profiles"></a>Sobre perfis

## <a name="short-description"></a>Descrição breve
Descreve como criar e usar um perfil do PowerShell.

## <a name="long-description"></a>Descrição longa

Você pode criar um perfil do PowerShell para personalizar seu ambiente e adicionar elementos específicos da sessão para cada sessão do PowerShell que você iniciar.

Um perfil do PowerShell é um script executado quando o PowerShell é iniciado. Você pode usar o perfil como um script de logon para personalizar o ambiente. Você pode adicionar comandos, aliases, funções, variáveis, snap-ins, módulos e unidades do PowerShell. Você também pode adicionar outros elementos específicos da sessão ao seu perfil para que eles estejam disponíveis em cada sessão sem a necessidade de importá-los ou recriá-los.

O PowerShell dá suporte a vários perfis para usuários e programas de host. No entanto, ele não cria os perfis para você. Este tópico descreve os perfis e descreve como criar e manter perfis no seu computador.

Ele explica como usar o parâmetro **NoProfile** do console do PowerShell (PowerShell.exe) para iniciar o PowerShell sem nenhum perfil. E explica o efeito da política de execução do PowerShell em perfis.

## <a name="the-profile-files"></a>Os arquivos de perfil

O PowerShell dá suporte a vários arquivos de perfil. Além disso, os programas de host do PowerShell podem dar suporte a seus próprios perfis específicos de host.

Por exemplo, o console do PowerShell dá suporte aos seguintes arquivos de perfil básicos. Os perfis são listados em ordem de precedência. O primeiro perfil tem a precedência mais alta.

|Descrição               | Caminho                                          |
|--------------------------|-----------------------------------------------|
|Todos os usuários, todos os hosts      |$PSHOME \\Profile.ps1                           |
|Todos os usuários, host atual   |$PSHOME \\Microsoft.PowerShell_profile.ps1      |
|Usuário atual, todos os hosts   |$Home \\ [My] Documents \\ WindowsPowerShell \\Profile.ps1 |
|Usuário atual, host atual|$Home \\ [meus] documentos \\ WindowsPowerShell\\<br>Microsoft.PowerShell_profile.ps1 |

Os caminhos de perfil incluem as seguintes variáveis:

- A `$PSHOME` variável, que armazena o diretório de instalação do PowerShell
- A `$Home` variável, que armazena o diretório base do usuário atual

Além disso, outros programas que hospedam o PowerShell podem dar suporte a seus próprios perfis. Por exemplo, o ISE (ambiente de script integrado) do PowerShell dá suporte aos seguintes perfis específicos de host.

|Descrição               | Caminho                                       |
|--------------------------|--------------------------------------------|
|Todos os usuários, host atual   |$PSHOME \\Microsoft.PowerShellISE_profile.ps1|
|Usuário atual, host atual|$Home \\ [meus] documentos \\ WindowsPowerShell\\<br>Microsoft.PowerShellISE_profile.ps1 |

Na ajuda do PowerShell, o perfil "CurrentUser, host atual" é o perfil mais conhecido como "seu perfil do PowerShell".

## <a name="the-profile-variable"></a>A variável $PROFILE

A `$PROFILE` variável automática armazena os caminhos para os perfis do PowerShell que estão disponíveis na sessão atual.

Para exibir um caminho de perfil, exiba o valor da `$PROFILE` variável. Você também pode usar a `$PROFILE` variável em um comando para representar um caminho.

A `$PROFILE` variável armazena o caminho para o perfil "usuário atual, host atual". Os outros perfis são salvos nas propriedades de observação da `$PROFILE` variável.

Por exemplo, a `$PROFILE` variável tem os seguintes valores no console do Windows PowerShell.

|Descrição                |Name                              |
|---------------------------|----------------------------------|
|Usuário atual, host atual |`$PROFILE`                        |
|Usuário atual, host atual |`$PROFILE.CurrentUserCurrentHost` |
|Usuário atual, todos os hosts    |`$PROFILE.CurrentUserAllHosts`    |
|Todos os usuários, host atual    |`$PROFILE.AllUsersCurrentHost`    |
|Todos os usuários, todos os hosts       |`$PROFILE.AllUsersAllHosts`       |

Como os valores da `$PROFILE` variável são alterados para cada usuário e em cada aplicativo host, certifique-se de exibir os valores das variáveis de perfil em cada aplicativo host do PowerShell que você usa.

Para ver os valores atuais da `$PROFILE` variável, digite:

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

Você pode usar a `$PROFILE` variável em muitos comandos. Por exemplo, o comando a seguir abre o perfil "usuário atual, host atual" no bloco de notas:

```powershell
notepad $PROFILE
```

O comando a seguir determina se um perfil "todos os usuários, todos os hosts" foi criado no computador local:

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a>Como criar um perfil

Para criar um perfil do PowerShell, use o seguinte formato de comando:

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

Por exemplo, para criar um perfil para o usuário atual no aplicativo host do PowerShell atual, use o seguinte comando:

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

Nesse comando, a `If` instrução impede que você substitua um perfil existente. Substitua o valor do \<profile-path\> espaço reservado pelo caminho para o arquivo de perfil que você deseja criar.

> [!NOTE]
> Para criar perfis de "todos os usuários" no Windows Vista e versões posteriores do Windows, inicie o PowerShell com a opção **Executar como administrador** .

## <a name="how-to-edit-a-profile"></a>Como editar um perfil

Você pode abrir qualquer perfil do PowerShell em um editor de texto, como o bloco de notas.

Para abrir o perfil do usuário atual no aplicativo host do PowerShell atual no bloco de notas, digite:

```powershell
notepad $PROFILE
```

Para abrir outros perfis, especifique o nome do perfil. Por exemplo, para abrir o perfil para todos os usuários de todos os aplicativos host, digite:

```powershell
notepad $PROFILE.AllUsersAllHosts
```

Para aplicar as alterações, salve o arquivo de perfil e reinicie o PowerShell.

## <a name="how-to-choose-a-profile"></a>Como escolher um perfil

Se você usar vários aplicativos host, coloque os itens que você usa em todos os aplicativos host em seu `$PROFILE.CurrentUserAllHosts` perfil. Coloque os itens que são específicos de um aplicativo host, como um comando que define a cor do plano de fundo de um aplicativo host, em um perfil específico para esse aplicativo host.

Se você for um administrador que está Personalizando o PowerShell para muitos usuários, siga estas diretrizes:

- Armazenar os itens comuns no `$PROFILE.AllUsersAllHosts` perfil
- Armazenar itens que são específicos a um aplicativo host em `$PROFILE.AllUsersCurrentHost` perfis que são específicos para o aplicativo host
- Armazenar itens para usuários específicos nos perfis específicos do usuário

Certifique-se de verificar a documentação do aplicativo host para qualquer implementação especial de perfis do PowerShell.

## <a name="how-to-use-a-profile"></a>Como usar um perfil

Muitos dos itens que você cria no PowerShell e a maioria dos comandos que você executa afetam apenas a sessão atual. Quando você encerra a sessão, os itens são excluídos.

Os comandos e itens específicos da sessão incluem variáveis, variáveis de preferência, aliases, funções, comandos (exceto para [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)) e módulos do PowerShell que você adiciona à sessão.

Para salvar esses itens e torná-los disponíveis em todas as sessões futuras, adicione-os a um perfil do PowerShell.

Outro uso comum para perfis é salvar funções, aliases e variáveis usadas com frequência. Ao salvar os itens em um perfil, você pode usá-los em qualquer sessão aplicável, sem recriá-los.

## <a name="how-to-start-a-profile"></a>Como iniciar um perfil

Quando você abre o arquivo de perfil, ele fica em branco. No entanto, você pode preenchê-lo com as variáveis, os aliases e os comandos que você usa com frequência.

Aqui estão algumas sugestões para você começar.

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a>Adicionar comandos que facilitam a abertura do seu perfil

Isso é especialmente útil se você usar um perfil diferente do perfil "usuário atual, host atual". Por exemplo, adicione o seguinte comando:

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a>Adicionar uma função que lista os aliases para qualquer cmdlet

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a>Personalizar o console

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a>Adicionar um prompt personalizado do PowerShell

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

Para obter mais informações sobre o prompt do PowerShell, consulte [about_Prompts](about_Prompts.md).

## <a name="the-noprofile-parameter"></a>O parâmetro NoProfile

Para iniciar o PowerShell sem perfis, use o parâmetro **NoProfile** de **PowerShell.exe** , o programa que inicia o PowerShell.

Para começar, abra um programa que possa iniciar o PowerShell, como Cmd.exe ou próprio PowerShell. Você também pode usar a caixa de diálogo Executar no Windows.

Tipo:

```
PowerShell -NoProfile
```

Para obter uma lista completa dos parâmetros de PowerShell.exe, digite:

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a>Perfis e política de execução

A política de execução do PowerShell determina, em parte, se você pode executar scripts e carregar arquivos de configuração, incluindo os perfis. A política de execução **restrita** é o padrão. Ele impede a execução de todos os scripts, incluindo os perfis. Se você usar a política "Restricted", o perfil não é executado e seu conteúdo não é aplicado.

Um `Set-ExecutionPolicy` comando define e altera sua política de execução. É um dos poucos comandos que se aplica em todas as sessões do PowerShell porque o valor é salvo no registro. Você não precisa defini-lo ao abrir o console do e não precisa armazenar um `Set-ExecutionPolicy` comando em seu perfil.

## <a name="profiles-and-remote-sessions"></a>Perfis e sessões remotas

Os perfis do PowerShell não são executados automaticamente em sessões remotas, portanto, os comandos que os perfis adicionam não estão presentes na sessão remota. Além disso, a `$PROFILE` variável automática não é populada em sessões remotas.

Para executar um perfil em uma sessão, use o cmdlet [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .

Por exemplo, o comando a seguir executa o perfil "usuário atual, host atual" do computador local na sessão em `$s` .

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

O comando a seguir executa o perfil "usuário atual, host atual" do computador remoto na sessão no `$s` . Como a `$PROFILE` variável não é populada, o comando usa o caminho explícito para o perfil. Usamos o operador de fornecimento de ponto para que o perfil seja executado no escopo atual no computador remoto e não em seu próprio escopo.

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

Depois de executar esse comando, os comandos que o perfil adiciona à sessão estão disponíveis no `$s` .

## <a name="see-also"></a>Consulte Também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Prompts](about_Prompts.md)

[about_Execution_Policies](about_Execution_Policies.md)

[about_Signing](about_Signing.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)
