---
description: Descreve o sistema de ajuda atualizável no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: 9f946fa1ef0f11efc3e0d964cf9ea8a55e01ff8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195604"
---
# <a name="about-updatable-help"></a>Sobre a ajuda atualizável

## <a name="short-description"></a>Descrição breve
Descreve o sistema de ajuda atualizável no PowerShell.

## <a name="long-description"></a>Descrição longa

O PowerShell fornece várias maneiras diferentes de acessar os tópicos de ajuda mais atualizados para os cmdlets e conceitos do PowerShell.

O sistema de ajuda atualizável, introduzido no PowerShell 3,0, foi projetado para garantir que você sempre tenha os tópicos mais recentes de ajuda em seu computador local para que você possa lê-los na linha de comando. Ele facilita baixar e instalar arquivos de ajuda e atualizá-los sempre que arquivos de ajuda mais recentes ficarem disponíveis.

Para fornecer ajuda atualizada para vários computadores em uma empresa e para computadores que não têm acesso à Internet, a ajuda atualizável permite que você baixe arquivos de ajuda para um diretório de sistema de arquivos ou compartilhamento de arquivos e, em seguida, instale os arquivos de ajuda do compartilhamento de arquivos.

No PowerShell 4,0, a propriedade **HelpInfoUri** é preservada pela comunicação remota do Windows PowerShell, que permite o `Save-Help` trabalho para os módulos instalados em um computador remoto, mas que não estão necessariamente instalados no computador local. Você pode salvar um objeto **PSModuleInfo** em disco ou mídia removível (como uma unidade USB) executando `Export-Clixml` em um computador que não tenha acesso à Internet, importando o objeto **PSModuleInfo** em um computador que tenha acesso à Internet e, em seguida, em execução `Save-Help` no objeto **PSModuleInfo** . A ajuda salva pode ser copiada para o computador remoto, desconectado usando mídia removível e, em seguida, instalada executando `Update-Help` . Esses aprimoramentos na `Save-Help` funcionalidade permitem que você instale a ajuda em computadores sem qualquer tipo de acesso à rede. Para obter um exemplo de como usar a nova `Save-Help` funcionalidade, consulte [como atualizar a ajuda de um compartilhamento de arquivos](#how-to-update-help-from-a-file-share) neste tópico.

A ajuda atualizável também dá suporte ao acesso online aos tópicos mais recentes de ajuda e à ajuda básica para cmdlets, mesmo quando não há arquivos de ajuda no computador.

O PowerShell 3,0 não vem com arquivos de ajuda. Você pode usar o recurso de ajuda atualizável para instalar os arquivos de ajuda para todos os comandos que estão incluídos por padrão no PowerShell e em todos os módulos do Windows.

## <a name="updatable-help-cmdlets"></a>Cmdlets de ajuda atualizáveis

- `Update-Help`: Baixa os arquivos de ajuda mais recentes da Internet ou de um compartilhamento de arquivos e os instala no computador local.

- `Save-Help`: Baixa os arquivos de ajuda mais recentes da Internet e os salva em um diretório do sistema de arquivos ou compartilhamento de arquivos. Para instalar os arquivos de ajuda nos computadores, use o `Update-Help` .

- `Get-Help`: Exibe tópicos da ajuda na linha de comando. Obtém ajuda dos arquivos de ajuda no computador. Exibe a ajuda gerada automaticamente para cmdlets e funções que não têm arquivos de ajuda. Abre tópicos de ajuda online para cmdlets, funções, scripts e fluxos de trabalho em seu navegador de Internet padrão.

## <a name="auto-generated-help-help-without-help-files"></a>Ajuda gerada automaticamente: ajuda sem arquivos de ajuda

Se você não tiver o arquivo de ajuda para um cmdlet, uma função ou um fluxo de trabalho no computador, o `Get-Help` cmdlet exibirá a ajuda gerada automaticamente e solicitará que você baixe os arquivos de ajuda ou os Leia online.

A ajuda gerada automaticamente inclui sintaxe e aliases, e comentários que explicam como usar os cmdlets de ajuda atualizáveis e para acessar os tópicos da ajuda online.

Por exemplo, o comando a seguir obtém a ajuda básica para o `Get-Culture` cmdlet. A saída mostra a `Get-Help` exibição quando não há arquivos de ajuda no computador.

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a>Arquivos de ajuda para módulos

A menor unidade de ajuda atualizável é a ajuda para um módulo. A ajuda do módulo inclui ajuda para todos os cmdlets, funções, fluxos de trabalho, provedores, scripts e conceitos em um módulo. Você pode atualizar a ajuda para todos os módulos que estão instalados no computador, mesmo que eles não sejam importados para a sessão atual.

Você pode atualizar a ajuda para o módulo inteiro, mas não pode atualizar a ajuda para cmdlets individuais.

Para localizar o módulo que contém um cmdlet específico, use o seguinte formato de comando:

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

Por exemplo, para localizar o módulo que contém o `Set-ExecutionPolicy` cmdlet, digite:

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

Para atualizar a ajuda para um módulo específico, digite:

```powershell
Update-Help -Module <ModuleName>
```

Por exemplo, para atualizar a ajuda para o módulo que contém o cmdlet Set-ExecutionPolicy, digite:

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a>Permissões para ajuda atualizável

Para atualizar a ajuda para os módulos no diretório `$pshome/Modules` , você deve ser membro do grupo Administradores no computador.

Se você não for um membro do grupo Administradores, não poderá atualizar a ajuda para esses módulos; Mas se você tiver acesso à Internet, poderá exibir a ajuda online.

A atualização da ajuda para módulos no diretório `$home/Documents/PowerShell/Modules` ou módulos em outros subdiretórios do `$home` diretório não requer permissões especiais.

Os `Update-Help` `Save-Help` cmdlets e têm um parâmetro **UseDefaultCredentials** que fornece as credenciais explícitas do usuário atual. Esse parâmetro foi projetado para acessar locais seguros da Internet.

Os `Update-Help` `Save-Help` cmdlets e também têm um parâmetro **Credential** que permite executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador. O parâmetro **Credential** é válido somente quando você usa os parâmetros SourcePath ou **LiteralPath** de `Update-Help` e os parâmetros **DestinationPath** ou **LiteralPath** de `Save-Help` .

## <a name="how-to-install-and-update-help-files"></a>Como instalar e atualizar arquivos de ajuda

Para baixar e instalar arquivos de ajuda pela primeira vez ou para atualizar os arquivos de ajuda em seu computador, use o `Update-Help` cmdlet.

O `Update-Help` cmdlet faz todo o trabalho árduo para você, incluindo as tarefas a seguir.

- Determina quais módulos dão suporte à ajuda atualizável.
- Localiza o local da Internet onde cada módulo armazena seus arquivos de ajuda atualizáveis.
- Compara os arquivos de ajuda de cada módulo em seu computador com os arquivos de ajuda mais recentes que estão disponíveis para cada módulo.
- Baixa os novos arquivos da Internet.
- Desencapsula o pacote do arquivo de ajuda.
- Verifica se os arquivos são arquivos de ajuda válidos.
- Instala os arquivos de ajuda no subdiretório específico do idioma do diretório do módulo.

Para acessar os novos tópicos da ajuda, use o `Get-Help` cmdlet. Você não precisa reiniciar o PowerShell.

Para instalar ou atualizar a ajuda para todos os módulos no computador que oferece suporte à ajuda atualizável, digite:

```powershell
Update-Help
```

Para atualizar a ajuda para determinados módulos, adicione o parâmetro **Module** de `Update-Help` . Caracteres curinga são permitidos no nome do módulo.

Por exemplo, para atualizar a ajuda para o módulo ServerManager, digite:

```powershell
Update-Help -Module ServerManager
```

Sem parâmetros, o `Update-Help` atualiza a ajuda para todos os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável. Para serem incluídos, os módulos devem ser instalados em diretórios listados no valor da variável de ambiente PSModulePath. Esses são também módulos que são retornados por um comando "Get-Help-ListAvailable".

Se o valor do parâmetro do **módulo** for `*` (All), o `Update-Help` tentará atualizar a ajuda para todos os módulos instalados, incluindo módulos que não dão suporte à ajuda atualizável. Esse comando normalmente gera muitos erros, pois o cmdlet encontra módulos que não oferecem suporte à ajuda atualizável.

## <a name="how-to-update-help-from-a-file-share"></a>Como atualizar a ajuda de um compartilhamento de arquivos

Para dar suporte a computadores que não estão conectados à Internet ou para controlar ou simplificar a atualização em uma empresa, use o `Save-Help` cmdlet. O `Save-Help` cmdlet baixa os arquivos de ajuda da Internet e os salva em um diretório FileSystem que você especificar.

`Save-Help` compara os arquivos de ajuda no diretório especificado com os arquivos de ajuda mais recentes que estão disponíveis para cada módulo. Se o diretório não tiver arquivos de ajuda ou arquivos de ajuda mais recentes estiverem disponíveis para o módulo, o `Save-Help` cmdlet baixará os novos arquivos da Internet. No entanto, ele não desencapsula ou instala os arquivos da ajuda.

Para instalar ou atualizar os arquivos de ajuda em um computador a partir de arquivos de ajuda que foram salvos em um diretório de sistema de arquivos, use o parâmetro **SourcePath** do `Update-Help` cmdlet. O `Update-Help` cmdlet identifica os arquivos de ajuda mais recentes, desencapsula e valida-os e os instala nos subdiretórios específicos do idioma dos diretórios de módulo.

Por exemplo, para salvar a ajuda para todos os módulos instalados no `\\Server\Share` diretório, digite:

```powershell
Save-Help -DestinationPath \\Server\Share
```

Em seguida, para atualizar a ajuda do `\\Server\Share` diretório, digite:

```powershell
Update-Help -SourcePath \\Server\Share
```

Os exemplos a seguir mostram o uso de `Save-Help` para salvar a ajuda para módulos que não estão instalados no computador local. Neste exemplo, o administrador é executado `Save-Help` para salvar a ajuda do módulo dhcpserver de um computador cliente conectado à Internet, sem instalar o módulo dhcpserver ou a função de servidor DHCP no computador local.

Opção 1: executar `Invoke-Command` para obter o objeto **PSModuleInfo** para o módulo remoto, salvá-lo em uma variável, `$m` e, em seguida, executar `Save-Help` no objeto **PSModuleInfo** especificando a variável `$m` como o nome do módulo.

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Opção 2: Abra uma PSSession direcionada ao computador que está executando o módulo do servidor DHCP, para obter o objeto **PSModuleInfo** para o módulo, salve-o em uma variável `$m` e, em seguida, execute `Save-Help` no objeto que é salvo na `$m` variável.

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Opção 3: Abra uma sessão CIM, direcionada ao computador que está executando o módulo do servidor DHCP, para obter o objeto **PSModuleInfo** para o módulo, salvá-lo em uma variável `$m` e, em seguida, executar `Save-Help` no objeto que é salvo na `$m` variável.

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

No exemplo a seguir, o administrador instala a ajuda para o módulo do servidor DHCP em um computador que não tem acesso à rede.

Primeiro, execute `Export-Clixml` para exportar o objeto **PSModuleInfo** para uma pasta compartilhada ou para uma mídia removível.

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

Em seguida, transporte a mídia removível para um computador que tenha acesso à Internet e, em seguida, importe o objeto **PSModuleInfo** com `Import-Clixml` . Execute `Save-Help` para salvar a ajuda para o objeto de **PSModuleInfo** do módulo do DhcpServer importado.

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

Por fim, transporte a mídia removível de volta para o computador que não tem acesso à rede e, em seguida, instale a ajuda executando `Update-Help` .

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

Sem parâmetros, o `Save-Help` baixa ajuda para todos os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável. Para serem incluídos, os módulos devem ser instalados em diretórios listados no valor da `$env:PSModulePath` variável de ambiente, no computador local ou em um computador remoto para o qual você deseja salvar a ajuda. Esses também são módulos que são retornados pela execução de um `Get-Help -ListAvailable` comando.

## <a name="how-to-update-help-files-in-different-languages"></a>Como atualizar arquivos de ajuda em diferentes idiomas

Por padrão, os `Update-Help` `Save-Help` cmdlets e baixam a ajuda na cultura da interface do usuário e no idioma definido para o Windows no computador local. Se os arquivos de ajuda para os módulos especificados não estiverem disponíveis na cultura da interface do usuário local, `Update-Help` `Save-Help` use as regras de fallback de idioma do Windows para encontrar o melhor idioma com suporte.

No entanto, você pode **UICulture** usar os parâmetros UICulture `Update-Help` dos `Save-Help` cmdlets e para baixar e instalar arquivos de ajuda em qualquer cultura de interface do usuário na qual eles estão disponíveis.

Por exemplo, para salvar os arquivos de ajuda mais recentes para todos os módulos na sessão em Japonês (ja-JP) e francês (fr-FR), digite:

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

Se os arquivos de ajuda para os módulos não estiverem disponíveis nos idiomas que você especificou, os `Update-Help` `Save-Help` cmdlets e retornarão uma mensagem de erro que lista os idiomas nos quais a ajuda para cada módulo está disponível para que você possa escolher a alternativa que melhor atenda às suas necessidades.

> [!NOTE]
> Atualmente, o conteúdo da ajuda atualizável só é publicado em inglês (en-US). Em alguns sistemas não Windows, você deve usar o parâmetro **UICulture** para solicitar explicitamente o `en-US` conteúdo.

## <a name="how-to-use-online-help"></a>Como usar a ajuda online

Se você não puder ou optar por não atualizar os arquivos de ajuda no computador local, ainda poderá obter os arquivos de ajuda mais recentes online.

Para abrir o tópico da ajuda online para qualquer cmdlet ou função, use o parâmetro **online** do `Get-Help` cmdlet.

Por exemplo, o comando a seguir abre o tópico de ajuda online para o `Get-Job` cmdlet em seu navegador de Internet padrão:

```powershell
Get-Help Get-Job -Online
```

Para obter ajuda online para um script, use o parâmetro **online** e o caminho completo para o script.

O parâmetro **online** não funciona com tópicos about. Para ver os tópicos sobre do PowerShell, incluindo tópicos de ajuda sobre a linguagem do PowerShell, confira [tópicos sobre o PowerShell](about.md).

## <a name="how-to-minimize-or-prevent-internet-downloads"></a>Como minimizar ou impedir downloads da Internet

Para minimizar os downloads da Internet e fornecer ajuda atualizável aos usuários que não estão conectados à Internet, use o `Save-Help` cmdlet. Baixe a ajuda da Internet e salve-a em um compartilhamento de rede. Em seguida, crie uma configuração de Política de Grupo ou um trabalho agendado que execute um `Update-Help` comando em todos os computadores. Defina o valor do parâmetro **SourcePath** do `Update-Help` cmdlet para o compartilhamento de rede.

Para impedir que os usuários com acesso à Internet Baixem a ajuda atualizável da Internet, use a configuração **definir o caminho de origem padrão para Update-help** política de grupo.

Essa configuração de Política de Grupo adiciona implicitamente o parâmetro **SourcePath** , com o local do sistema de arquivos que você especifica, a cada `Update-Help` comando em cada computador afetado. Os usuários podem usar o parâmetro **SourcePath** explicitamente para especificar um local de sistema de arquivos diferente, mas não podem excluir o parâmetro **SourcePath** e baixar a ajuda da Internet.

> [!NOTE]
> A configuração da política de grupo **definir o caminho de origem padrão para a atualização-ajuda** é exibida em **configuração do computador** e **configuração do usuário** . No entanto, somente a configuração de política em **configuração do computador** é eficaz. A configuração de política em **configuração do usuário** é ignorada.

Confira mais informações em [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="how-to-update-help-for-non-standard-modules"></a>Como atualizar a ajuda para módulos não padrão

Para atualizar ou salvar a ajuda para um módulo que não é retornado pelo parâmetro **listAvailable** do `Get-Module` cmdlet, importe o módulo para a sessão atual antes de executar um `Update-Help` comando ou `Save-Help` . Em um computador remoto, antes de executar o `Save-Help` comando, importe o módulo para a sessão atual ou o `Invoke-Command` bloco de script que está conectado ao computador remoto.

Quando o módulo estiver na sessão atual, execute os `Update-Help` `Save-Help` cmdlets ou sem parâmetros ou use o parâmetro **Module** para especificar o nome do módulo.

Os parâmetros de **módulo** dos `Update-Help` `Save-Help` cmdlets e aceitam apenas um nome de módulo. Eles não aceitam o caminho para um arquivo de módulo.

Use essa técnica para atualizar ou salvar a ajuda para qualquer módulo que não seja retornado pelo parâmetro **listAvailable** do `Get-Module` cmdlet, como um módulo instalado em um local que não esteja listado na variável de `$env:PSModulePath` ambiente ou um módulo que não esteja bem formado (o diretório do módulo não contém pelo menos um arquivo cujo basename seja o mesmo que o nome do diretório).

## <a name="how-to-support-updatable-help"></a>Como dar suporte à ajuda atualizável

Se você criar um módulo, poderá dar suporte à ajuda online e à ajuda atualizável para seus módulos. Para obter mais informações, consulte [dando suporte à ajuda atualizável](/powershell/scripting/developer/help/supporting-updatable-help) e [suporte à ajuda online](/powershell/scripting/developer/module/supporting-online-help) no Microsoft docs.

Ajuda atualizável não disponível para snap-ins do PowerShell ou ajuda baseada em comentários.

## <a name="remarks"></a>Comentários

`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).

## <a name="see-also"></a>Confira também

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
