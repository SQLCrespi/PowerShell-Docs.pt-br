---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: ff1b709b363684e27a1f4eb8fdeada2d5ae1d588
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193075"
---
# Export-PSSession

## SINOPSE

Exporta comandos de outra sessão e salva-os em um módulo do PowerShell.

## SYNTAX

### Tudo

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## DESCRIPTION

O `Export-PSSession` cmdlet obtém cmdlets, funções, aliases e outros tipos de comando de outra sessão do PowerShell (PSSession) em um computador local ou remoto e os salva em um módulo do PowerShell. Para adicionar os comandos do módulo à sessão atual, use o `Import-Module` cmdlet.

Ao contrário de `Import-PSSession` , que importa os comandos de outra PSSession para a sessão atual, `Export-PSSession` o salva os comandos em um módulo. Os comandos não são importados para a sessão atual.

Para exportar comandos, use o `New-PSSession` cmdlet para criar uma PSSession que tenha os comandos que você deseja exportar. Em seguida, use o `Export-PSSession` cmdlet para exportar os comandos.

Para evitar conflitos de nome de comando, o padrão para `Export-PSSession` é exportar todos os comandos, exceto os comandos existentes na sessão atual. Você pode usar o parâmetro **CommandName** para especificar os comandos a serem exportados.

O `Export-PSSession` cmdlet usa o recurso de comunicação remota implícita do PowerShell. Quando você importa comandos para a sessão atual, eles são executados implicitamente na sessão original ou em uma sessão semelhante no computador de origem.

## EXEMPLOS

### Exemplo 1: exportar comandos de uma PSSession

Este exemplo cria uma nova PSSession do computador local para o computador Server01. Todos os comandos, exceto aqueles que existem na sessão atual, são exportados para o módulo chamado Server01 no computador local. A exportação inclui os dados de formatação para os comandos.

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

O `New-PSSession` comando cria uma PSSession no computador Server01. A PSSession é armazenada na `$S` variável. O `Export-PSSession` comando exporta os `$S` comandos da variável e os dados de formatação para o módulo Server01.

### Exemplo 2: exportar os comandos Get e Set

Este exemplo exporta todos os `Get` comandos e `Set` de um servidor.

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

Esses comandos exportam os `Get` `Set` comandos e de um snap-in do Microsoft Exchange Server em um computador remoto para um módulo do Exchange no `$PSHOME\Modules` diretório no computador local.
Colocar o módulo no `$PSHOME\Modules` diretório o torna acessível a todos os usuários do computador.

### Exemplo 3: exportar comandos de um computador remoto

Este exemplo exporta os cmdlets de uma PSSession em um computador remoto e os salva em um módulo no computador local. Os cmdlets do módulo são adicionados à sessão atual para que possam ser usados.

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

O `New-PSSession` comando cria uma PSSession no computador Server01 e salva-a na `$S` variável. O `Export-PSSession` comando exporta os cmdlets cujos nomes começam com teste de PSSession em `$S` para o módulo TestCmdlets no computador local.

O `Remove-PSSession` cmdlet exclui a PSSession in `$S` da sessão atual. Esse comando mostra que a PSSession não precisa estar ativa para usar os comandos que foram importados da sessão. O `Import-Module` cmdlet adiciona os cmdlets no módulo TestCmdlets à sessão atual. O comando pode ser executado em qualquer sessão a qualquer momento.

O `Get-Help` cmdlet obtém ajuda para os cmdlets cujos nomes começam com Test. Depois que os comandos em um módulo são adicionados à sessão atual, você pode usar os `Get-Help` `Get-Command` cmdlets e para saber mais sobre os comandos importados. O `Test-Files` cmdlet foi exportado do computador Server01 e adicionado à sessão. O `Test-Files` cmdlet é executado em uma sessão remota no computador do qual o comando foi importado. O PowerShell cria uma sessão de informações armazenadas no módulo TestCmdlets.

### Exemplo 4: exportar e sobrescrição comandos na sessão atual

Este exemplo exporta comandos que são armazenados em uma variável na sessão atual.

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

Esse `Export-PSSession` comando exporta todos os comandos e todos os dados de formatação da PSSession na `$S` variável para a sessão atual. O parâmetro **AllowClobber** inclui comandos com os mesmos nomes dos comandos na sessão atual.

### Exemplo 5: exportar comandos de uma PSSession fechada

Este exemplo mostra como executar os comandos exportados com opções especiais quando a PSSession que criou os comandos exportados é fechada.

Se a sessão remota original for fechada quando um módulo for importado, o módulo usará qualquer sessão remota aberta que se conectar ao computador de origem. Se não houver nenhuma sessão atual para o computador de origem, o módulo restabelecerá uma sessão.

Para executar comandos exportados com opções especiais em uma sessão remota, você deve criar uma sessão remota com essas opções antes de importar o módulo. Use o `New-PSSession` cmdlet com o parâmetro **SessionOption**

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

O `New-PSSessionOption` cmdlet cria um objeto **PSSessionOption** e salva o objeto na `$Options` variável. O `New-PSSession` comando cria uma PSSession no computador Server01.
O parâmetro **SessionOption** usa o objeto armazenado em `$Options` . A sessão é armazenada na `$S` variável.

O `Export-PSSession` cmdlet exporta os comandos de PSSession `$S` para o módulo Server01.
O `Remove-PSSession` cmdlet exclui a PSSession na `$S` variável.

O `New-PSSession` cmdlet cria uma nova PSSession que se conecta ao computador Server01. O parâmetro **SessionOption** usa o objeto armazenado em `$Options` . O `Import-Module` cmdlet importa os comandos do módulo Server01. Os comandos no módulo são executados na PSSession no computador Server01.

## PARAMETERS

### -AllowClobber

Exporta os comandos especificados, mesmo se tiverem os mesmos nomes de comandos na sessão atual.

Se você exportar um comando com o mesmo nome de um comando na sessão atual, o comando exportado ocultará ou substituirá os comandos originais. Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).

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

Exporta a variante do comando resultante ao usar os argumentos especificados (valores de parâmetro).

Por exemplo, para exportar a variante do `Get-Item` comando no certificado (CERT:) na PSSession em `$S` , digite `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

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

Especifica o certificado do cliente que é usado para assinar os arquivos de formato (* .Format.ps1XML) ou arquivos de módulo de script (. psm1) no módulo que o `Export-PSSession` cria. Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.

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

Exporta somente os comandos com os nomes especificados ou padrões de nome. Caracteres curinga são permitidos. Use **CommandName** ou seu alias, **Name** .

Por padrão, `Export-PSSession` o exporta todos os comandos da PSSession, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual. Isso impede que os comandos sejam ocultados ou substituídos por comandos na sessão atual. Para exportar todos os comandos, mesmo aqueles que ocultam ou substituem outros comandos, use o parâmetro **AllowClobber** .

Se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão exportados, a menos que você use o parâmetro **FormatTypeName** . Da mesma forma, se você usar o parâmetro **FormatTypeName** , nenhum comando será exportado a menos que você use o parâmetro **CommandName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### -CommandType

Exporta somente os tipos especificados de objetos de comando. Use o **CommandType** ou seu alias, **Type** .

Os valores aceitáveis para esse parâmetro são os seguintes:

- Receber. Todos os aliases do PowerShell na sessão atual.
- Todos. Todos os tipos de comando. É o equivalente de `Get-Command -Name *` .
- Console. Todos os arquivos que não sejam arquivos do PowerShell em caminhos listados na variável de ambiente Path ( `$env:path` ), incluindo arquivos. txt,. exe e. dll.
- Cmdlet. Os cmdlets na sessão atual. É o padrão.
- Configuração. Uma configuração do PowerShell. Para obter mais informações, consulte [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).
- ExternalScript. Todos os arquivos. ps1 nos caminhos listados na variável de ambiente Path ( `$env:path` ).
- Filtro e função. Todas as funções do PowerShell.
- Script. Blocos de script na sessão atual.
- Modelo. Um fluxo de trabalho do PowerShell. Para obter mais informações, consulte [about_Workflows](/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1).

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8.
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.


A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Substitui um ou mais arquivos de saída existentes, mesmo se o arquivo tem o atributo somente leitura.

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

Exporta instruções de formatação para os tipos especificados do Microsoft .NET Framework. Insira os nomes de tipo. Por padrão, o `Export-PSSession` exporta as instruções de formatação para todos os tipos de .NET Framework que não estão no namespace **System. Management. Automation** .

O valor desse parâmetro deve ser o nome de um tipo que é retornado por um `Get-FormatData` comando na sessão da qual os comandos estão sendo importados. Para obter todos os dados de formatação na sessão remota, digite `*` .

Se você usar o parâmetro **FormatTypeName** , nenhum comando será exportado a menos que você use o parâmetro **CommandName** .

Se você usar o parâmetro **CommandName** , os arquivos de formatação para os comandos não serão exportados, a menos que você use o parâmetro **FormatTypeName** .

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

Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .
Consulte a seção comentários do [Construtor ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290).

Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um destes formatos:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional. Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** ; os dois parâmetros são mutuamente exclusivos.

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

Exporta somente os comandos nos módulos e snap-ins especificados do PowerShell. Digite os nomes de módulos e snap-ins. Caracteres curinga não são permitidos.

Para obter mais informações, consulte `Import-Module` e [about_Pssnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputModule

Especifica um caminho opcional e um nome para o módulo criado pelo `Export-PSSession` . O caminho padrão é `$home\Documents\WindowsPowerShell\Modules`. Este parâmetro é necessário.

Se o subdiretório do módulo ou qualquer um dos arquivos que o `Export-PSSession` cria já existir, o comando falhará. Para substituir os arquivos existentes, use o parâmetro **Force** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessão

Especifica a PSSession da qual os comandos são exportados. Insira uma variável que contém um objeto de sessão ou um comando que obtém um objeto de sessão, como um `Get-PSSession` comando. Este parâmetro é necessário.

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

Não é possível canalizar objetos para `Export-PSSession` .

## SAÍDAS

### System. IO. FileInfo

`Export-PSSession` Retorna uma lista de arquivos que compõem o módulo que ele criou.

## OBSERVAÇÕES

`Export-PSSession` depende da infraestrutura de comunicação remota do PowerShell. Para usar esse cmdlet, o computador deve ser configurado para comunicação remota. Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Você não pode usar `Export-PSSession` o para exportar um provedor do PowerShell.

Os comandos exportados são executados implicitamente na PSSession da qual foram exportados. Os detalhes da execução de comandos remotamente são tratados inteiramente pelo PowerShell. Você pode executar os comandos exportados exatamente como você executaria comandos locais.

`Export-ModuleMember` captura e salva informações sobre a PSSession no módulo que ela exporta. Se a PSSession da qual os comandos foram exportados for fechada quando você importar o módulo e não houver nenhuma PSSession ativa para o mesmo computador, os comandos no módulo tentarão recriar a PSSession. Se as tentativas de recriar a PSSession falharem, os comandos exportados não serão executados.

As informações de sessão que o `Export-ModuleMember` captura e salva no módulo não incluem opções de sessão, como aquelas que você especificar na variável de `$PSSessionOption` preferência ou usando o parâmetro **SessionOption** dos `New-PSSession` `Enter-PSSession` cmdlets,, ou `Invoke-Command` . Se a PSSession original for fechada quando você importar o módulo, o módulo usará outra PSSession no mesmo computador, se disponível. Para habilitar os comandos importados para serem executados em uma sessão configurada corretamente, crie uma PSSession com as opções que você deseja antes de importar o módulo.

Para localizar os comandos a serem exportados, `Export-PSSession` o usa o `Invoke-Command` cmdlet para executar um `Get-Command` comando na PSSession. Para obter e salvar dados de formatação para os comandos, ele usa `Get-FormatData` os `Export-FormatData` cmdlets e. Você pode ver mensagens de erro de `Invoke-Command` , `Get-Command` , `Get-FormatData` e `Export-FormatData` quando você executa um `Export-PSSession` comando. Além disso, `Export-PSSession` o não pode exportar comandos de uma sessão que não inclua os `Get-Command` `Get-FormatData` cmdlets,, `Select-Object` e `Get-Help` .

`Export-PSSession` usa o `Write-Progress` cmdlet para exibir o progresso do comando. Você pode ver a barra de progresso enquanto o comando é executado.

Comandos exportados têm as mesmas limitações que outros comandos remotos, inclusive a incapacidade de iniciar um programa com uma interface de usuário, como o Bloco de notas.

Como os perfis do PowerShell não são executados em PSSessions, os comandos que um perfil adiciona a uma sessão não estão disponíveis para o `Export-PSSession` . Para exportar comandos de um perfil, use um `Invoke-Command` comando para executar o perfil na PSSession manualmente antes de exportar os comandos.

O módulo que o `Export-PSSession` cria pode incluir um arquivo de formatação, mesmo que o comando não importe dados de formatação. Se o comando não importar dados de formatação, quaisquer arquivos de formatação criados não conterão dados de formatação.

## LINKS RELACIONADOS

[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Import-PSSession](Import-PSSession.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSSessionOption](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[Remove-PSSession](../Microsoft.PowerShell.Core/Remove-PSSession.md)
