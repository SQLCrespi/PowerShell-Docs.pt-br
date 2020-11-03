---
description: Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 5b59d8fb05ee118f5b2d7b5b859efad9be75814a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195483"
---
# <a name="about-session-configurations"></a>Sobre as configurações de sessão

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve as configurações de sessão, que determinam os usuários que podem se conectar ao computador remotamente e os comandos que eles podem executar.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Uma configuração de sessão, também conhecida como "ponto de extremidade", é um grupo de configurações no computador local que define o ambiente para as sessões do PowerShell que são criadas quando os usuários remotos ou locais se conectam ao PowerShell no computador local.

Os administradores do computador podem usar configurações de sessão para proteger o computador e definir ambientes personalizados para usuários que se conectam ao computador.

Os administradores também podem usar as configurações de sessão para determinar as permissões necessárias para se conectar ao computador remotamente. Por padrão, somente os membros do grupo Administradores têm permissão para usar a configuração de sessão para se conectar remotamente, mas você pode alterar as configurações padrão para permitir que todos os usuários ou usuários selecionados se conectem remotamente ao seu computador.

A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir os elementos de uma configuração de sessão. Esse recurso facilita a personalização de sessões sem escrever código e descobrir as propriedades de uma configuração de sessão. Para criar um arquivo de configuração de sessão, use o cmdlet New-PSSessionConfiguration. Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](about_Session_Configuration_Files.md).

As configurações de sessão são um recurso da comunicação remota do PowerShell baseada em Web Services para gerenciamento (WS-Management). Eles são usados somente quando você usa os cmdlets New-PSSession, Invoke-Command ou Enter-PSSession para se conectar a um computador remoto.

Observação: para gerenciar as configurações de sessão, inicie o PowerShell com a opção "executar como administrador".

Sobre as configurações de sessão

Cada sessão do PowerShell usa uma configuração de sessão. Isso inclui sessões persistentes que você cria usando os cmdlets New-PSSession ou Enter-PSSession e as sessões temporárias que o PowerShell cria quando você usa o parâmetro ComputerName de um cmdlet que usa a tecnologia de comunicação remota baseada no WS-Management, como Invoke-Command.

Os administradores podem usar as configurações de sessão para proteger os recursos do computador e criar ambientes personalizados para os usuários que se conectam ao computador. Por exemplo, você pode usar uma configuração de sessão para limitar o tamanho dos objetos que o computador recebe na sessão, para definir o modo de linguagem da sessão e para especificar os cmdlets, provedores e funções que estão disponíveis na sessão.

Ao configurar o descritor de segurança de uma configuração de sessão, você determina quem pode usar a configuração de sessão para se conectar ao computador.
Os usuários devem ter permissão de execução para uma configuração de sessão para usá-la em uma sessão. Se um usuário não tiver as permissões necessárias para usar qualquer uma das configurações de sessão em um computador, o usuário não poderá se conectar ao computador remotamente.

Por padrão, somente os administradores do computador têm permissão para usar as configurações de sessão padrão. Porém, você pode alterar os descritores de segurança para permitir que todos, nenhum ou apenas usuários selecionados usem as configurações de sessão no seu computador.

Configurações de sessão internas

O PowerShell 3,0 inclui configurações de sessão internas chamadas Microsoft. PowerShell e Microsoft. PowerShell. Workflow. Em computadores que executam versões de 64 bits do Windows, o PowerShell também fornece o Microsoft. PowerShell32, uma configuração de sessão de 32 bits.

A configuração de sessão do Microsoft. PowerShell é usada para sessões por padrão, ou seja, quando um comando para criar uma sessão não inclui o parâmetro ConfigurationName do cmdlet New-PSSession, Enter-PSSession ou Invoke-Command.

Os descritores de segurança para as configurações de sessão padrão permitem que somente membros do grupo Administradores no computador local os usem. Assim, somente os membros do grupo Administradores podem se conectar ao computador remotamente, a menos que você altere as configurações padrão.

Você pode alterar as configurações de sessão padrão usando a variável de preferência $PSSessionConfigurationName. Para obter mais informações, consulte about_preference_variables.

Exibindo configurações de sessão no computador local

Para obter as configurações de sessão no computador local, use o cmdlet Get-PSSessionConfiguration.

Por exemplo, digite:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

O objeto de configuração de sessão é expandido no PowerShell 3,0 para exibir as propriedades da configuração de sessão que são configuradas usando um arquivo de configuração de sessão.

Por exemplo, para ver todas as propriedades de um objeto de configuração de sessão, digite:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

Você também pode usar o provedor WSMan no PowerShell para exibir as configurações de sessão. O provedor WSMan cria uma unidade WSMAN: em sua sessão.

Na unidade WSMAN:, as configurações de sessão estão no nó plugin. (Todas as configurações de sessão estão no nó plugin, mas há itens no nó plug-in que não são configurações de sessão.)

Por exemplo, para exibir as configurações de sessão no computador local, digite:

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Exibindo configurações de sessão em um computador remoto

Para exibir as configurações de sessão em um computador remoto, use o cmdlet Connect-WSMan para adicionar uma nota para o computador remoto para a unidade WSMAN: no computador local e, em seguida, use a unidade WSMAN: para exibir as configurações de sessão.

Por exemplo, o comando a seguir adiciona um nó para o computador remoto Server01 à unidade WSMAN: no computador local.

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

Quando o comando for concluído, você poderá navegar até o nó do computador Server01 para exibir as configurações de sessão.

Por exemplo:

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Alterando o descritor de segurança de uma configuração de sessão

No Windows Server 2012 e versões mais recentes do Windows Server, as configurações de sessão internas são habilitadas para usuários remotos por padrão. Em outras versões com suporte do Windows, você deve alterar os descritores de segurança das configurações de sessão para permitir o acesso remoto.

Para habilitar o acesso remoto às configurações de sessão no computador, use o cmdlet Enable-PSRemoting. Esse cmdlet cria duas configurações de sessão:

- com o nome definido como: "PowerShell". + "versão atual do PowerShell"
- com o nome "PowerShell. 6", não vinculado a nenhuma versão específica do PowerShell.

Além disso, por padrão, somente os membros do grupo Administradores no computador têm a permissão executar para as configurações de sessão padrão, mas você pode alterar os descritores de segurança nas configurações de sessão padrão e em todas as configurações de sessão que você criar.

Para conceder a outros usuários permissão para se conectar ao computador remotamente, use o cmdlet Set-PSSessionConfiguration para adicionar permissões "executar" para esses usuários aos descritores de segurança das configurações de sessão Microsoft. PowerShell e Microsoft. PowerShell32.

Por exemplo, o comando a seguir abre uma página de propriedades que permite alterar o descritor de segurança para a configuração de sessão padrão do Microsoft. PowerShell.

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Para negar a permissão Everyone para todas as configurações de sessão no computador, use o cmdlet Disable-PSSessionConfiguration. Por exemplo, o comando a seguir desabilita as configurações de sessão padrão no computador.

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

Para impedir que usuários remotos se conectem ao computador, mas permitir que os usuários locais se conectem, use o cmdlet Disable-PSRemoting. Disable-PSRemoting adiciona uma entrada "Network_Deny_All" a todas as configurações de sessão no computador.

```powershell
PS C:> Disable-PSRemoting
```

Para permitir que usuários remotos usem todas as configurações de sessão no computador, use o cmdlet Enable-PSRemoting ou Enable-PSSessionConfiguration. Por exemplo, o comando a seguir habilita o acesso remoto às configurações de sessão internas.

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

Para fazer outras alterações no descritor de segurança de uma configuração de sessão, use o cmdlet Set-PSSessionConfiguration. Use o parâmetro SecurityDescriptorSDDL para enviar um valor de cadeia de caracteres SDDL. Use o parâmetro ShowSecurityDescriptorUI dos para exibir uma folha de propriedades da interface do usuário que ajuda você a criar uma nova SDDL.

Por exemplo:

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Criando uma nova configuração de sessão

Para criar uma nova configuração de sessão no computador local, use o cmdlet Register-PSSessionConfiguration. Para definir a nova configuração de sessão, você pode usar um assembly C#, um script do PowerShell e os parâmetros do cmdlet Register-PSSessionConfiguration.

Por exemplo, o comando a seguir cria uma configuração de sessão que é idêntica à configuração de sessão do Microsoft. PowerShell, exceto pelo fato de que ela limita os dados recebidos de um comando remoto para 20 megabytes (MB). (O padrão é 50 MB).

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

Ao criar uma configuração de sessão, você pode gerenciá-la usando os outros cmdlets de configuração de sessão e ela aparece na unidade WSMAN:.

Para obter mais informações, consulte Register-PSSessionConfiguration.

Removendo uma configuração de sessão

Para remover uma configuração de sessão do computador local, use o cmdlet Unregister-PSSessionConfiguration. Por exemplo, o comando a seguir remove a configuração de sessão NewConfig do computador.

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

Para obter mais informações, consulte Unregister-PSSessionConfiguration.

Restaurando uma configuração de sessão

Para restaurar uma configuração de sessão padrão que foi excluída (não registrada) acidentalmente, use o cmdlet Enable-PSRemoting.

O cmdlet Enable-PSRemoting recria todas as configurações de sessões padrão que não existem no computador. Ele não substitui nem altera os valores de propriedade das configurações de sessão existentes.

Para restaurar os valores de propriedade originais de uma configuração de sessão padrão, use o Unregister-PSSessionConfiguration para excluir a configuração de sessão e, em seguida, use o cmdlet Enable-PSRemoting para recriá-lo.

Selecionando uma configuração de sessão

Para selecionar uma configuração de sessão específica para uma sessão, use o parâmetro ConfigurationName de New-PSSession, Enter-PSSession ou Invoke-Command.

Por exemplo, esse comando usa o cmdlet New-PSSession para iniciar uma PSSession no computador Server01. O comando usa o parâmetro ConfigurationName para selecionar a configuração WithProfile no computador Server01.

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

Esse comando só terá sucesso se o usuário atual tiver permissão para usar a configuração de sessão WithProfile ou puder fornecer as credenciais de um usuário que tem as permissões necessárias.

Você também pode usar a variável de preferência $PSSessionConfigurationName para alterar a configuração de sessão padrão no computador. Para obter mais informações sobre a variável de preferência $PSSessionConfigurationName, consulte about_Preference_Variables.

## <a name="keywords"></a>Palavras-chave

about_Endpoints about_SessionConfigurations

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Preference_Variables](about_Preference_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Session_Configuration_Files](about_Session_Configuration_Files.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
