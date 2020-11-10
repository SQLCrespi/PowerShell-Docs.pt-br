---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: d3a2aae9318da7235070b68dd379081467fa611a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388698"
---
# Get-Module

## SINOPSE
Obtém os módulos que foram importados ou podem ser importados para a sessão atual.

## SYNTAX

### Carregado (padrão)

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### Disponível

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] [<CommonParameters>]
```

### PsSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### CimSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable] [-Refresh]
 -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Module` cmdlet obtém os módulos do PowerShell que foram importados ou que podem ser importados em uma sessão do PowerShell. O objeto de módulo que `Get-Module` retorna contém informações valiosas sobre o módulo. Você também pode canalizar os objetos de módulo para outros cmdlets, como `Import-Module` os `Remove-Module` cmdlets e.

Sem parâmetros, `Get-Module` Obtém os módulos que foram importados para a sessão atual. Para obter todos os módulos instalados, especifique o parâmetro **listAvailable** .

`Get-Module` Obtém os módulos, mas não os importa. A partir do Windows PowerShell 3,0, os módulos são importados automaticamente quando você usa um comando no módulo, mas um `Get-Module` comando não dispara uma importação automática. Você também pode importar os módulos para a sessão usando o `Import-Module` cmdlet.

A partir do Windows PowerShell 3,0, você pode obter e, em seguida, importar módulos de sessões remotas para a sessão local. Essa estratégia usa o recurso de comunicação remota implícita do PowerShell e é equivalente a usar o `Import-PSSession` cmdlet. Quando você usa comandos em módulos importados de outra sessão, os comandos são executados implicitamente na sessão remota. Esse recurso permite que você gerencie o computador remoto a partir da sessão local.

Além disso, a partir do Windows PowerShell 3,0, você pode usar `Get-Module` e `Import-Module` para obter e importar módulos de modelo CIM (CIM), nos quais os cmdlets são definidos em arquivos de definição de cmdlet (CDXML). Esse recurso permite que você use cmdlets que são implementados em assemblies de código não gerenciado, como os escritos em C++.

Com esses novos recursos, os `Get-Module` `Import-Module` cmdlets e se tornam ferramentas principais para gerenciar empresas heterogêneas que incluem computadores que executam o sistema operacional Windows e computadores que executam outros sistemas operacionais.

Para gerenciar computadores remotos que executam o sistema operacional Windows que tem o PowerShell e a comunicação remota do PowerShell habilitada, crie uma **PSSession** no computador remoto e, em seguida, use o parâmetro **PSSession** do `Get-Module` para obter os módulos do PowerShell na **PSSession**. Quando você importa os módulos e, em seguida, usa os comandos importados na sessão atual, os comandos são executados implicitamente na **PSSession** no computador remoto. Você pode usar essa estratégia para gerenciar o computador remoto.

Você pode usar uma estratégia semelhante para gerenciar computadores que não têm a comunicação remota do PowerShell habilitada.
Isso inclui computadores que não estão executando o sistema operacional Windows e computadores que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.

Comece criando uma sessão CIM no computador remoto. Uma sessão CIM é uma conexão com Instrumentação de Gerenciamento do Windows (WMI) no computador remoto. Em seguida, use o parâmetro **CIMSession** de `Get-Module` para obter módulos CIM da sessão CIM. Quando você importa um módulo CIM usando o `Import-Module` cmdlet e, em seguida, executa os comandos importados, os comandos são executados implicitamente no computador remoto. Você pode usar essa estratégia de WMI e CIM para gerenciar o computador remoto.

## EXEMPLOS

### Exemplo 1: obter os módulos importados para a sessão atual

```powershell
Get-Module
```

Este comando obtém módulos que foram importados para a sessão atual.

### Exemplo 2: obter módulos instalados e módulos disponíveis

```powershell
Get-Module -ListAvailable
```

Este comando obtém os módulos que estão instalados no computador e que podem ser importados para a sessão atual.

`Get-Module` procura os módulos disponíveis no caminho especificado pelo **$env:P** variável de ambiente smodulepath. Para obter mais informações sobre o **PSModulePath** , consulte [about_Modules](About/about_Modules.md) e [about_Environment_Variables](About/about_Environment_Variables.md).

### Exemplo 3: obter todos os arquivos exportados

```powershell
Get-Module -ListAvailable -All
```

Este comando obtém todos os arquivos exportados para todos os módulos disponíveis.

### Exemplo 4: obter um módulo por seu nome totalmente qualificado

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

Esse comando obtém o módulo **Microsoft. PowerShell. Management** especificando o nome totalmente qualificado do módulo usando o parâmetro **FullyQualifiedName** . Em seguida, o comando canaliza os resultados para o `Format-Table` cmdlet para formatar os resultados como uma tabela com **nome** e **versão** como títulos de coluna.

### Exemplo 5: obter propriedades de um módulo

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

Esse comando obtém as propriedades do objeto **PSModuleInfo** que `Get-Module` retorna. Há um objeto para cada arquivo de módulo.

Você pode usar as propriedades para formatar e filtrar os objetos do módulo. Para obter mais informações sobre as propriedades, consulte [Propriedades de PSModuleInfo](/dotnet/api/system.management.automation.psmoduleinfo).

A saída inclui as novas propriedades, como **Author** e **CompanyName** , que foram introduzidas no Windows PowerShell 3,0.

### Exemplo 6: agrupar todos os módulos por nome

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

Esse comando obtém todos os arquivos de módulo, importados e disponíveis e, em seguida, os agrupa por nome de módulo. Isso lhe permite visualizar os arquivos de módulo que cada script está exportando.

### Exemplo 7: exibir o conteúdo de um manifesto de módulo

Esses comandos exibem o conteúdo do manifesto do módulo para o módulo **BitsTransfer** do Windows PowerShell.

Os módulos não precisam ter arquivos de manifesto. Quando eles têm um arquivo de manifesto, o arquivo de manifesto é necessário apenas para incluir um número de versão. No entanto, os arquivos de manifesto muitas vezes fornecem informações úteis sobre um módulo, seus requisitos e seu conteúdo.

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

O primeiro comando obtém o objeto PSModuleInfo, que representa o módulo BitsTransfer. Ele salva o objeto na `$m` variável.

O segundo comando usa o `Get-Content` cmdlet para obter o conteúdo do arquivo de manifesto no caminho especificado. Ele usa a notação de ponto para obter o caminho para o arquivo de manifesto, que é armazenado na propriedade Path do objeto. A saída mostra o conteúdo do manifesto do módulo.

### Exemplo 8: listar arquivos no diretório do módulo

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

Esse comando lista os arquivos no diretório do módulo. Esta é outra maneira de determinar o que está em um módulo antes de importá-lo. Alguns módulos podem ter arquivos de ajuda ou Leia-me, que descrevem o módulo.

### Exemplo 9: obter os módulos instalados em um computador

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

Estes comandos obtêm os módulos instalados no computador Servidor01.

O primeiro comando usa o `New-PSSession` cmdlet para criar uma **PSSession** no computador Server01. O comando salva a **PSSession** na variável $s.

O segundo comando usa os parâmetros **PSSession** e **listAvailable** de `Get-Module` para obter os módulos na **PSSession** na `$s` variável.

Se você canaliza módulos de outras sessões para o `Import-Module` cmdlet, o `Import-Module` importa o módulo para a sessão atual usando o recurso de comunicação remota implícita. Isso é equivalente a usar o `Import-PSSession` cmdlet. Você pode usar os cmdlets do módulo na sessão atual, mas os comandos que usam esses cmdlets, na verdade, executam a sessão remota. Para obter mais informações, confira [`Import-Module`](Import-Module.md) e [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).

### Exemplo 10: gerenciar um computador que não executa o sistema operacional Windows

Os comandos neste exemplo permitem que você gerencie os sistemas de armazenamento de um computador remoto que não está executando o sistema operacional Windows.
Neste exemplo, como o administrador do computador instalou o provedor WMI de descoberta do módulo, os comandos CIM podem usar os valores padrão, que são projetados para o provedor.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

O primeiro comando usa o `New-CimSession` cmdlet para criar uma sessão no computador remoto RSDGF03. A sessão conecta-se ao WMI no computador remoto. O comando salva a sessão CIM na `$cs` variável.

O segundo comando usa a sessão CIM na `$cs` variável para executar um `Get-Module` comando no computador RSDGF03. O comando usa o parâmetro Name para especificar o módulo de armazenamento. O comando usa um operador de pipeline (|) para enviar o módulo de armazenamento para o `Import-Module` cmdlet, que o importa para a sessão local.

O terceiro comando executa o `Get-Command` cmdlet no `Get-Disk` comando no módulo de armazenamento.
Quando você importa um módulo CIM para a sessão local, o PowerShell converte os arquivos CDXML que representam o módulo CIM em scripts do PowerShell, que aparecem como funções na sessão local.

O quarto comando executa o `Get-Disk` comando. Embora o comando seja digitado na sessão local, ele é executado implicitamente no computador remoto do qual foi importado. O comando obtém os objetos por meio do computador remoto e os retorna para a sessão local.

## PARAMETERS

### -All

Indica que esse cmdlet obtém todos os módulos em cada pasta de módulo, incluindo módulos aninhados, arquivos de manifesto (. psd1), arquivos de módulo de script (. psm1) e arquivos de módulo binário (. dll). Sem esse parâmetro, `Get-Module` obtém apenas o módulo padrão em cada pasta de módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimNamespace

Especifica o namespace de um provedor CIM alternativo que expõe módulos CIM. O valor padrão é o namespace do provedor WMI de detecção de módulos.

Use esse parâmetro para obter módulos CIM de computadores e dispositivos que não estão executando o sistema operacional Windows.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimResourceUri

Especifica um local alternativo para módulos CIM. O valor padrão é o URI de recurso do provedor WMI de descoberta de módulo no computador remoto.

Use esse parâmetro para obter módulos CIM de computadores e dispositivos que não estão executando o sistema operacional Windows.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Especifica uma sessão CIM no computador remoto. Insira uma variável que contém a sessão CIM ou um comando que obtém a sessão CIM, como um comando [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .

`Get-Module` usa a conexão de sessão CIM para obter módulos do computador remoto. Quando você importa o módulo usando o `Import-Module` cmdlet e usa os comandos do módulo importado na sessão atual, os comandos realmente são executados no computador remoto.

Você pode usar esse parâmetro para obter módulos de computadores e dispositivos que não estão executando o sistema operacional Windows e computadores que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.

O parâmetro **CimSession** obtém todos os módulos em **CIMSession**. Porém, você pode importar somente módulos baseados em CIM e baseados em XML de definição de cmdlets (CDXML).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** . Consulte a seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um destes formatos:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional. Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** . os dois parâmetros são mutuamente exclusivos.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListAvailable

Indica que este cmdlet obtém todos os módulos instalados. `Get-Module` Obtém os módulos nos caminhos listados na variável de ambiente **PSModulePath** . Sem esse parâmetro, `Get-Module` obtém somente os módulos listados na variável de ambiente **PSModulePath** e que são carregados na sessão atual. O **ListAvailable** não retorna informações sobre os módulos que não são encontrados na variável de ambiente **PSModulePath** , mesmo que esses módulos estejam carregados na sessão atual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica nomes ou padrões de nome dos módulos que esse cmdlet obtém. Caracteres curinga são permitidos. Você também pode canalizar os nomes para `Get-Module` . Você não pode especificar o parâmetro **FullyQualifiedName** no mesmo comando que um parâmetro de **nome** .

O **nome** não pode aceitar um GUID de módulo como um valor.
Para retornar módulos especificando um GUID, use **FullyQualifiedName** em vez disso.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -PSEdition

Obtém os módulos que dão suporte à edição especificada do PowerShell.

Os valores aceitáveis para esse parâmetro são:

- Desktop
- Núcleo

O cmdlet Get-Module verifica a propriedade **CompatiblePSEditions** do objeto **PSModuleInfo** para o valor especificado e retorna somente os módulos que o têm definido.

> [!NOTE]
>
> - **Desktop Edition:** criada no .NET Framework, fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.
> - **Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSession

Obtém os módulos na sessão do PowerShell gerenciada pelo usuário especificada ( **PSSession** ). Insira uma variável que contenha a sessão, um comando que obtém a sessão, como um `Get-PSSession` comando, ou um comando que cria a sessão, como um `New-PSSession` comando.

Quando a sessão estiver conectada a um computador remoto, você deverá especificar o parâmetro **listAvailable** .

Um `Get-Module` comando que usa o parâmetro **PSSession** é equivalente a usar o `Invoke-Command` cmdlet para executar um `Get-Module -ListAvailable` comando em uma **PSSession**.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atualizar

Indica que esse cmdlet atualiza o cache de comandos instalados. O cache de comando é criado no início da sessão. Ele permite que o `Get-Command` cmdlet obtenha comandos de módulos que não são importados para a sessão.

Este parâmetro é projetado para cenários de desenvolvimento e testes, nos quais o conteúdo dos módulos foi alterado desde o início da sessão.

Ao especificar o parâmetro de **atualização** em um comando, você deve especificar **listAvailable**.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PsSession, Available, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

Você pode canalizar nomes de módulo para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSModuleInfo

Esse cmdlet retorna objetos que representam módulos.
Quando você especifica o parâmetro **listAvailable** , `Get-Module` retorna um objeto **ModuleInfoGrouping** , que é um tipo de objeto **PSModuleInfo** que tem as mesmas propriedades e métodos.

## OBSERVAÇÕES

- A partir do Windows PowerShell 3,0, os comandos principais incluídos no PowerShell são empacotados em módulos. A exceção é **Microsoft. PowerShell. Core** , que é um snap-in ( **PSSnapin** ). Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão.
Os módulos são importados automaticamente no primeiro uso e você pode usar o `Import-Module` cmdlet para importá-los.
- A partir do Windows PowerShell 3,0, os comandos principais instalados com o PowerShell são empacotados em módulos. No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do PowerShell, os comandos principais são empacotados em snap-ins ( **PSSnapins** ). A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in. Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.

  Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- `Get-Module` Obtém apenas módulos em locais que são armazenados no valor da variável de ambiente **PSModulePath** ($env:P smodulepath). Você pode usar o parâmetro **path** do `Import-Module` cmdlet para importar módulos em outros locais, mas não pode usar o `Get-Module` cmdlet para obtê-los.
- Além disso, a partir do PowerShell 3,0, novas propriedades foram adicionadas ao objeto que `Get-Module` retorna para facilitar o aprendizado sobre os módulos, mesmo antes de serem importados. Todas as propriedades são preenchidas antes da importação. Isso inclui as propriedades **ExportedCommands** , **ExportedCmdlets** e **ExportedFunctions** que listam os comandos que o módulo exporta.
- O parâmetro **listAvailable** obtém apenas módulos bem formados, ou seja, pastas que contêm pelo menos um arquivo cujo nome de base é o mesmo que o nome da pasta do módulo. O nome base é o nome sem a extensão de nome de arquivo. As pastas que contêm arquivos com nomes diferentes são consideradas contêineres, mas não módulos.

  Para obter os módulos que são implementados como arquivos. dll, mas não são colocados em uma pasta de módulo, especifique o **listAvailable** e **todos os** parâmetros.

- Para usar o recurso de sessão CIM, o computador remoto deve ter comunicação remota do WS-Management e a Instrumentação de Gerenciamento do Windows (WMI), que é a implementação da Microsoft do padrão CIM. O computador também deve ter o provedor WMI de descoberta do módulo ou um provedor WMI alternativo com os mesmos recursos básicos.

  Você pode usar o recurso de sessão CIM em computadores que não estão executando o sistema operacional Windows e em computadores com Windows que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.

  Você também pode usar os parâmetros CIM para obter módulos CIM de computadores que têm a comunicação remota do PowerShell habilitada. Isso inclui o computador local.
Quando você cria uma sessão CIM no computador local, o PowerShell usa DCOM, em vez de WMI, para criar a sessão.

## LINKS RELACIONADOS

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[about_Modules](About/about_Modules.md)

[Get-PSSession](Get-PSSession.md)

[Import-Module](Import-Module.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[New-PSSession](New-PSSession.md)

[Remove-Module](Remove-Module.md)
