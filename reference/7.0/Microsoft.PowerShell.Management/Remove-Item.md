---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: ddb3f8d1889887e01db8663e21cdb0323e6d4084
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192767"
---
# Remove-Item

## SINOPSE
Exclui os itens especificados.

## SYNTAX

### Caminho (padrão)

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### LiteralPath

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Item` cmdlet exclui um ou mais itens. Como há suporte para vários provedores, ele pode excluir vários tipos diferentes de itens, incluindo arquivos, pastas, chaves do registro, variáveis, aliases e funções.

## EXEMPLOS

### Exemplo 1: excluir arquivos que têm qualquer extensão de nome de arquivo

Este exemplo exclui todos os arquivos que têm nomes que incluem um ponto ( `.` ) da `C:\Test` pasta. Como o comando especifica um ponto, o comando não exclui pastas ou arquivos que não têm nenhuma extensão de nome de arquivo.

```powershell
Remove-Item C:\Test\*.*
```

### Exemplo 2: excluir alguns dos arquivos de documento em uma pasta

Este exemplo exclui da pasta atual todos os arquivos que têm uma `.doc` extensão de nome de arquivo e um nome que não inclui `*1*` .

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

Ele usa o caractere curinga ( `*` ) para especificar o conteúdo da pasta atual. Ele usa os parâmetros **include** e **Exclude** para especificar os arquivos a serem excluídos.

### Exemplo 3: excluir arquivos ocultos e somente leitura

Esse comando exclui um arquivo que está *oculto* e *somente leitura* .

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

Ele usa o parâmetro **path** para especificar o arquivo. Ele usa o parâmetro **Force** para excluí-lo. Sem **forçar** , você não pode excluir arquivos _somente leitura_ ou _ocultos_ .

### Exemplo 4: excluir arquivos em subpastas de forma recursiva

Esse comando exclui todos os arquivos CSV na pasta atual e todas as subpastas de forma recursiva.

Como o parâmetro **recurse** no `Remove-Item` tem um problema conhecido, o comando neste exemplo usa `Get-ChildItem` para obter os arquivos desejados e, em seguida, usa o operador de pipeline para passá-los para `Remove-Item` .

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

No `Get-ChildItem` comando, **Path** tem um valor de ( `*` ), que representa o conteúdo da pasta atual. Ele usa **include** para especificar o tipo de arquivo CSV e usa **recurse** para tornar a recuperação recursiva. Se você tentar especificar o tipo de arquivo o caminho, como `-Path *.csv` , o cmdlet interpretará o assunto da pesquisa para ser um arquivo que não tem itens filhos e **recurse** falhará.

### Exemplo 5: excluir subchaves recursivamente

Esse comando exclui a chave do registro "OldApp" e todas as suas subchaves e valores. Ele usa `Remove-Item` para remover a chave. O caminho é especificado, mas o nome de parâmetro opcional ( **caminho** ) é omitido.

O parâmetro **recurse** exclui todo o conteúdo da chave "OldApp" recursivamente. Se a chave contiver subchaves e você omitir o parâmetro **recurse** , será solicitado que você confirme se deseja excluir o conteúdo da chave.

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### Exemplo 6: excluindo arquivos com caracteres especiais

O exemplo a seguir mostra como excluir arquivos que contêm caracteres especiais, como colchetes ou parênteses.

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### Exemplo 7: remover um fluxo de dados alternativo

Este exemplo mostra como usar o parâmetro **Stream** dinâmico do `Remove-Item` cmdlet para excluir um fluxo de dados alternativo. O parâmetro Stream é introduzido no Windows PowerShell 3,0.

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

O parâmetro de **fluxo** `Get-Item` Obtém o fluxo de **Zone. identificador** do `Copy-Script.ps1` arquivo. `Remove-Item` usa o parâmetro de **fluxo** para remover o fluxo de **zona. identificador** do arquivo. Por fim, o `Get-Item` cmdlet mostra que o fluxo de **Zone. identificador** foi excluído.

## PARAMETERS

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.
> Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos. O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Especifica um filtro para qualificar o parâmetro **path** . O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros. Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Força o cmdlet a remover itens que não podem ser alterados de outra forma, como arquivos ocultos ou somente leitura ou aliases ou variáveis somente leitura. O cmdlet não pode remover variáveis nem aliases constantes.
A implementação varia de provedor para provedor. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md). Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `"*.txt"` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath

Especifica um caminho para um ou mais locais. O valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica um caminho dos itens que estão sendo removidos.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Recurse

Indica que esse cmdlet exclui os itens nos locais especificados e em todos os itens filho dos locais.

Quando usado com o parâmetro **include** , o parâmetro **recurse** pode não excluir todas as subpastas ou todos os itens filho. Este é um problema conhecido. Como alternativa, tente canalizar os resultados do `Get-ChildItem -Recurse` comando para `Remove-Item` , conforme descrito no "exemplo 4" neste tópico.

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

### -Fluxo

O parâmetro de **fluxo** é um parâmetro dinâmico que o provedor FileSystem adiciona `Remove-Item` .
Esse parâmetro funciona somente em unidades de sistema de arquivos.

Você pode usar `Remove-Item` para excluir um fluxo de dados alternativo. No entanto, não é a maneira recomendada para eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet. Para obter mais informações, consulte os seguintes artigos:

- [about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

O `Remove-Item` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Quando você tenta excluir uma pasta que contém itens sem usar o parâmetro **recurse** , o cmdlet solicita confirmação. Usar não `-Confirm:$false` suprime o prompt. Isso ocorre por design.

## LINKS RELACIONADOS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
