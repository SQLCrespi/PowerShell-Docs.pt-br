---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: c64a59300cdaffe71de04c7843bf644df49530d5
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390109"
---
# Import-PSSession

## SINOPSE
Importa comandos de outra sessão para a sessão atual.

## SYNTAX

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## DESCRIPTION

O `Import-PSSession` cmdlet importa comandos, como cmdlets, funções e aliases, de uma PSSession em um computador local ou remoto para a sessão atual. Você pode importar qualquer comando que o `Get-Command` cmdlet possa encontrar na PSSession.

Use um `Import-PSSession` comando para importar comandos de um shell personalizado, como um shell do Microsoft Exchange Server, ou de uma sessão que inclui módulos e snap-ins do Windows PowerShell ou outros elementos que não estão na sessão atual.

Para importar comandos, primeiro use o `New-PSSession` cmdlet para criar uma PSSession. Em seguida, use o `Import-PSSession` cmdlet para importar os comandos. Por padrão, `Import-PSSession` o importa todos os comandos, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual. Para importar todos os comandos, use o parâmetro **AllowClobber**.

Você pode usar comandos importados da mesma maneira que usaria qualquer comando na sessão. Quando você usa um comando importado, a parte importada do comando é executada implicitamente na sessão da qual ele foi importado. No entanto, as operações remotas são manipuladas inteiramente pelo Windows PowerShell. Você não precisa nem estar ciente delas, exceto de que a conexão com a outra sessão (PSSession) deve ser mantida aberta. Se ela for fechada, os comandos importados não estarão mais disponíveis.

Como os comandos importados podem levar mais tempo do que comandos locais, `Import-PSSession` o adiciona um parâmetro **AsJob** a todos os comandos importados. Esse parâmetro permite que você execute o comando como um trabalho em segundo plano do Windows PowerShell. Para obter mais informações, consulte [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).

Quando você usa `Import-PSSession` o, o Windows PowerShell adiciona os comandos importados a um módulo temporário que existe somente em sua sessão e retorna um objeto que representa o módulo. Para criar um módulo persistente que você pode usar em sessões futuras, use o `Export-PSSession` cmdlet.

O `Import-PSSession` cmdlet usa o recurso de comunicação remota implícita do Windows PowerShell. Quando você importa comandos para a sessão atual, eles são executados implicitamente na sessão original ou em uma sessão semelhante no computador de origem.

A partir do Windows PowerShell 3,0, você pode usar o `Import-Module` cmdlet para importar módulos de uma sessão remota para a sessão atual. Esse recurso usa a comunicação remota implícita. É equivalente a usar `Import-PSSession` o para importar módulos selecionados de uma sessão remota para a sessão atual.

## EXEMPLOS

### Exemplo 1: importar todos os comandos de uma PSSession

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

Este comando importa todos os comandos de uma PSSession no computador Server01 para a sessão atual, com exceção de comandos que possuem os mesmos nomes de comandos na sessão atual.

Como esse comando não usa o parâmetro **CommandName** , ele também importa todos os dados de formatação necessários para os comandos importados.

### Exemplo 2: importar comandos que terminam com uma cadeia de caracteres específica

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

Esses comandos importam os comandos com nomes que terminam em "-test" de uma PSSession para a sessão local e mostram como usar um cmdlet importado.

O primeiro comando usa o `New-PSSession` cmdlet para criar uma PSSession. Ele salva a PSSession na `$S` variável.

O segundo comando usa o `Import-PSSession` cmdlet para importar comandos da PSSession para `$S` a sessão atual. Ele usa o parâmetro **CommandName** para especificar comandos com o substantivo Test (Teste) e o parâmetro **FormatTypeName** para importar os dados de formatação para os comandos Test.

Os terceiro e o quarto comandos usam os comandos importados na sessão atual. Como comandos importados, na verdade, são adicionados à sessão atual, a sintaxe local é usada para executá-los. Você não precisa usar o `Invoke-Command` cmdlet para executar um comando importado.

### Exemplo 3: importar cmdlets de uma PSSession

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

Este exemplo mostra que é possível usar cmdlets importados da mesma maneira que cmdlets locais.

Esses comandos importam os `New-Test` `Get-Test` cmdlets e de uma PSSession no computador Server01 e o `Set-Test` cmdlet de uma PSSession no computador Server02.

Embora os cmdlets sejam importados de diferentes PSSessions, é possível direcionar um objeto de um cmdlet para outro sem erro.

### Exemplo 4: executar um comando importado como um trabalho em segundo plano

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

Este exemplo mostra como executar um comando importado como um trabalho em segundo plano.

Como os comandos importados podem levar mais tempo do que comandos locais, `Import-PSSession` o adiciona um parâmetro **AsJob** a todos os comandos importados. O parâmetro **AsJob** permite que você execute o comando como um trabalho em segundo plano.

O primeiro comando cria uma PSSession no computador Server01 e salva o objeto PSSession na `$S` variável.

O segundo comando usa `Import-PSSession` para importar os cmdlets de teste da PSSession `$S` para a sessão atual.

O terceiro comando usa o parâmetro **AsJob** do cmdlet importado `New-Test` para executar um `New-Test` comando como um trabalho em segundo plano. O comando salva o objeto de trabalho que `New-Test` retorna na `$batch` variável.

O quarto comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho na `$batch` variável.

### Exemplo 5: importar cmdlets e funções de um módulo do Windows PowerShell

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

Este exemplo mostra como importar os cmdlets e funções de um módulo do Windows PowerShell em um computador remoto para a sessão atual.

O primeiro comando cria uma PSSession no computador Server01 e salva-a na `$S` variável.

O segundo comando usa o `Invoke-Command` cmdlet para executar um `Import-Module` comando na PSSession em `$S` .

Normalmente, o módulo seria adicionado a todas as sessões por um `Import-Module` comando em um perfil do Windows PowerShell, mas os perfis não são executados em PSSessions.

O terceiro comando usa o parâmetro **Module** do `Import-PSSession` para importar os cmdlets e funções no módulo para a sessão atual.

### Exemplo 6: criar um módulo em um arquivo temporário

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

Este exemplo mostra que `Import-PSSession` cria um módulo em um arquivo temporário no disco. Ele também mostra que todos os comandos são convertidos em funções antes de serem importados para a sessão atual.

O comando usa o `Import-PSSession` cmdlet para importar um `Get-Date` cmdlet e uma função SearchHelp para a sessão atual.

O `Import-PSSession` cmdlet retorna um objeto **PSModuleInfo** que representa o módulo temporário. O valor da propriedade **path** mostra que `Import-PSSession` criou um arquivo de módulo de script (. psm1) em um local temporário. A propriedade **ExportedFunctions** mostra que o `Get-Date` cmdlet e a função SearchHelp foram importados como funções.

### Exemplo 7: executar um comando que está oculto por um comando importado

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

Este exemplo mostra como executar um comando que está oculto por um comando importado.

O primeiro comando importa um `Get-Date` cmdlet da PSSession na `$S` variável. Como a sessão atual inclui um `Get-Date` cmdlet, o parâmetro **AllowClobber** é necessário no comando.

O segundo comando usa o parâmetro **All** do `Get-Command` cmdlet para obter todos os `Get-Date` comandos na sessão atual. A saída mostra que a sessão inclui o `Get-Date` cmdlet original e uma `Get-Date` função. A `Get-Date` função executa o cmdlet importado `Get-Date` na PSSession no `$S` .

O terceiro comando executa um `Get-Date` comando. Como as funções têm precedência sobre os cmdlets, o Windows PowerShell executa a função importada `Get-Date` , que retorna uma data do calendário juliano.

Os quarto e quinto comandos mostram como usar um nome qualificado para executar um comando que está oculto por um comando importado.

O quarto comando obtém o nome do snap-in do Windows PowerShell que adicionou o `Get-Date` cmdlet original à sessão atual.

O quinto comando usa o nome qualificado do snap-in do `Get-Date` cmdlet para executar um `Get-Date` comando.

Para obter mais informações sobre precedência de comandos e comandos ocultos, consulte [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).

### Exemplo 8: importar comandos que têm uma cadeia de caracteres específica em seus nomes

```
PS C:\> Import-PSSession -Session $S -CommandName **Item** -AllowClobber
```

Este comando importa os comandos cujos nomes incluem item da PSSession em `$S` . Como o comando inclui o parâmetro **CommandName** , mas não o parâmetro **FormatTypeData** , somente o comando é importado.

Use esse comando quando estiver usando `Import-PSSession` o para executar um comando em um computador remoto e você já tiver os dados de formatação para o comando na sessão atual.

### Exemplo 9: usar o parâmetro Module para descobrir quais comandos foram importados para a sessão

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

Este comando mostra como usar o parâmetro **Module** do `Get-Command` para descobrir quais comandos foram importados para a sessão por um `Import-PSSession` comando.

O primeiro comando usa o `Import-PSSession` cmdlet para importar comandos cujos nomes incluem "bits" da PSSession na `$S` variável. O `Import-PSSession` comando retorna um módulo temporário e o comando salva o módulo na `$m` variável.

O segundo comando usa o `Get-Command` cmdlet para obter os comandos que são exportados pelo módulo na `$M` variável.

O parâmetro **Module** obtém um valor de cadeia de caracteres, que é projetado para o nome do módulo. No entanto, quando você envia um objeto de módulo, o Windows PowerShell usa o método **ToString** no objeto de módulo, que retorna o nome do módulo.

O `Get-Command` comando é o equivalente a `Get-Command $M.Name` ".

## PARAMETERS

### -AllowClobber

Indica que esse cmdlet importa os comandos especificados, mesmo que eles tenham os mesmos nomes que os comandos na sessão atual.

Se você importar um comando com o mesmo nome de um comando na sessão atual, os comandos importado ocultam ou substituem os originais. Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).

Por padrão, `Import-PSSession` o não importa comandos com o mesmo nome que os comandos na sessão atual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArgumentList

Especifica uma matriz de comandos que resulta do uso dos argumentos especificados (valores de parâmetro).

Por exemplo, para importar a variante do `Get-Item` comando no certificado (CERT:) na PSSession em `$S` , digite `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificado

Especifica o certificado do cliente que é usado para assinar os arquivos de formato (* .Format.ps1XML) ou arquivos de módulo de script (. psm1) no módulo temporário que o `Import-PSSession` cria.

Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.

Para localizar um certificado, use o `Get-PfxCertificate` cmdlet ou use o `Get-ChildItem` cmdlet no certificado (CERT:) Dirigir. Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandName

Especifica os comandos com os nomes especificados ou padrões de nome. Caracteres curinga são permitidos. Use **CommandName** ou seu alias, **Name**.

Por padrão, `Import-PSSession` o importa todos os comandos da sessão, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual. Isso impede que os comandos importados ocultem ou substituam os comandos da sessão. Para importar todos os comandos, mesmo aqueles que ocultam ou substituem outros comandos, use o parâmetro **AllowClobber**.

Se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro **FormatTypeName**. Da mesma forma, se você usar o parâmetro **FormatTypeName** , nenhum comando é importado, a menos que você use o parâmetro **CommandName**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Especifica o tipo de objetos de comando. O valor padrão é Cmdlet. Use o **CommandType** ou seu alias, **Type**. Os valores aceitáveis para esse parâmetro são:

- Receber. Os aliases do Windows PowerShell na sessão remota.
- Todos. Os cmdlets e funções na sessão remota.
- Console. Todos os arquivos que não sejam Windows-PowerShell arquivos nos caminhos listados na variável de ambiente Path ( `$env:path` ) na sessão remota, incluindo arquivos. txt,. exe e. dll.
- Cmdlet. Os cmdlets na sessão remota. "Cmdlet" é o padrão.
- ExternalScript. Os arquivos. ps1 nos caminhos listados na variável de ambiente Path ( `$env:path` ) na sessão remota.
- Filtro e função. As funções do Windows PowerShell na sessão remota.
- Script. Os blocos de script na sessão remota.

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableNameChecking

Indica que esse cmdlet suprime a mensagem que avisa quando você importa um cmdlet ou função cujo nome inclui um verbo não aprovado ou um caractere proibido.

Por padrão, quando um módulo que você importa exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o Windows PowerShell exibe a seguinte mensagem de aviso:

"Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis. Use o parâmetro Verbose para obter mais detalhes ou digite `Get-Verb` para ver a lista de verbos aprovados.

A mensagem é apenas um aviso. O módulo completo ainda é importado, incluindo os comandos não autorizados. Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatTypeName

Especifica instruções de formatação para os tipos de estrutura de Microsoft .NET especificados.
Insira os nomes de tipo.
Caracteres curinga são permitidos.

O valor desse parâmetro deve ser o nome de um tipo que é retornado por um `Get-FormatData` comando na sessão da qual os comandos estão sendo importados. Para obter todos os dados de formatação na sessão remota, digite `*` .

Se o comando não incluir o parâmetro **CommandName** ou **FormatTypeName** , o `Import-PSSession` importará instruções de formatação para todos os tipos de .NET Framework retornados por um `Get-FormatData` comando na sessão remota.

Se você usar o parâmetro **FormatTypeName** , nenhum comando será importado, a menos que você use o parâmetro **CommandName**.

Da mesma forma, se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro **FormatTypeName**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule

Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** (descritos na seção comentários do [Construtor ModuleSpecification (HASHTABLE)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) no SDK do PowerShell. Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado no formato:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}` ou
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.

**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.

Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** . Os dois parâmetros são mutuamente exclusivos.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Módulo

Especifica e a matriz de comandos nos módulos e snap-ins do Windows PowerShell. Digite os nomes de módulos e snap-ins. Caracteres curinga não são permitidos.

`Import-PSSession` Não é possível importar provedores de um snap-in.

Para obter mais informações, consulte [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) e [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefixo

Especifica um prefixo para os substantivos nos nomes dos comandos importados.

Use este parâmetro para evitar conflitos de nome que podem ocorrer quando diferentes membros da sessão têm o mesmo nome.

Por exemplo, se você especificar o prefixo Remote e, em seguida, importar um `Get-Date` cmdlet, o cmdlet será conhecido na sessão como `Get-RemoteDate` , e não será confundido com o `Get-Date` cmdlet original.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica a **PSSession** da qual os cmdlets são importados. Insira uma variável que contém um objeto de sessão ou um comando que obtém um objeto de sessão, como `New-PSSession` um `Get-PSSession` comando ou. Você pode especificar somente uma sessão. Este parâmetro é necessário.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PSModuleInfo

`Import-PSSession` Retorna o mesmo objeto de módulo que os `New-Module` `Get-Module` cmdlets retornam.
No entanto, o módulo importado é temporário e existe somente na sessão atual. Para criar um módulo permanente no disco, use o `Export-PSSession` cmdlet.

## OBSERVAÇÕES

- `Import-PSSession` depende da infraestrutura de comunicação remota do PowerShell. Para usar esse cmdlet, o computador deve ser configurado para comunicação remota do WS-Management. Para obter mais informações, consulte [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) e [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).
- `Import-PSSession` Não importa variáveis ou provedores do PowerShell.
- Quando você importa comandos que têm os mesmos nomes que comandos na sessão atual, os comandos importados podem ocultar aliases, funções e cmdlets na sessão e eles podem substituir funções e variáveis na sessão. Para evitar conflitos de nome, use o parâmetro **Prefix**. Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).
- `Import-PSSession` Converte todos os comandos em funções antes de importá-los. Como resultado, comandos importados possuem um comportamento um pouco diferente de quando mantém tipo de comando original. Por exemplo, se você importar um cmdlet de uma PSSession e um cmdlet com o mesmo nome de um módulo ou snap-in, o cmdlet é importado da PSSession sempre será executado por padrão porque funções têm precedência sobre cmdlets. Por outro lado, se você importar um alias para uma sessão com um alias com o mesmo nome, o alias original sempre é usado, pois aliases têm precedência sobre funções. Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).
- `Import-PSSession` usa o `Write-Progress` cmdlet para exibir o progresso do comando. Você pode ver a barra de progresso enquanto o comando é executado.
- Para localizar os comandos a serem importados, `Import-PSSession` o usa o `Invoke-Command` cmdlet para executar um `Get-Command` comando na PSSession. Para obter dados de formatação para os comandos, ele usa o `Get-FormatData` cmdlet. Você poderá ver mensagens de erro desses cmdlets ao executar um `Import-PSSession` comando. Além disso, `Import-PSSession` o não pode importar comandos de uma PSSession que não inclua os `Get-Command` `Get-FormatData` cmdlets,, `Select-Object` e `Get-Help` .
- Comandos importados têm as mesmas limitações que outros comandos remotos, inclusive a incapacidade de iniciar um programa com uma interface de usuário, como o Bloco de notas.
- Como os perfis do Windows PowerShell não são executados em PSSessions, os comandos que um perfil adiciona a uma sessão não estão disponíveis para o `Import-PSSession` . Para importar comandos de um perfil, use um `Invoke-Command` comando para executar o perfil na PSSession manualmente antes de importar os comandos.
- O módulo temporário que o `Import-PSSession` cria pode incluir um arquivo de formatação, mesmo que o comando não importe dados de formatação. Se o comando não importar dados de formatação, quaisquer arquivos de formatação criados não conterão dados de formatação.
- Para usar `Import-PSSession` o, a política de execução na sessão atual não pode ser restrita ou AllSigned, pois o módulo temporário que o `Import-PSSession` cria contém arquivos de script não assinados que são proibidos por essas políticas. Para usar `Import-PSSession` sem alterar a política de execução para o computador local, use o parâmetro de **escopo** de `Set-ExecutionPolicy` para definir uma política de execução menos restritiva para um único processo.
- No Windows PowerShell 2.0, os tópicos de ajuda para comandos importados de outra sessão não incluem o prefixo que você atribui usando o parâmetro **Prefix**. Para obter ajuda sobre um comando importado no Windows PowerShell 2.0, use o nome original do comando (sem prefixo).

## LINKS RELACIONADOS

[Export-PSSession](Export-PSSession.md)
