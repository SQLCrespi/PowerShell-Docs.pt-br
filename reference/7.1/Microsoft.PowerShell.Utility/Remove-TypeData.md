---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 926239c0bbdb17f53b7d869c0bb08c8ab125f1a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194000"
---
# Remove-TypeData

## Sinopse
Exclui tipos estendidos da sessão atual.

## Syntax

### RemoveTypeDataSet (padrão)

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveTypeSet

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Removeset

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-TypeData` cmdlet exclui dados de tipo estendido da sessão atual. Este cmdlet afeta somente a sessão atual e as sessões que são criadas na sessão atual.

Você pode adicionar propriedades e métodos a objetos no PowerShell definindo-os em `Update-TypeData` comandos e `Types.ps1xml` arquivos. `Remove-TypeData` exclui as propriedades estendidas e os métodos da sessão atual. `Remove-TypeData` não exclui os `Types.ps1xml` arquivos nem exclui nenhuma definição de tipo estendido dos `Types.ps1xml` arquivos. Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## Exemplos

### Exemplo 1: remover dados de tipo para um tipo especificado

Este exemplo exclui todos os dados de tipo para o tipo **System. array** da sessão, incluindo dados de tipo que foram adicionados por um `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados à sessão usando o `Update-TypeData` cmdlet.

```powershell
Remove-TypeData -TypeName System.Array
```

### Exemplo 2: remover um tipo de dados estendido de uma sessão

Este exemplo mostra o efeito de remover dados de tipo estendido de uma sessão. A primeira `Get-TypeData` obtém dados de tipo estendido para o tipo **System. DateTime** . A saída mostra que uma propriedade **DateTime** foi adicionada a todos os objetos **System. DateTime** no PowerShell. O `Get-Date` cmdlet retorna um objeto **System. DateTime** . O comando usa a notação de ponto para obter o valor da propriedade **DateTime** do objeto **System. DateTime** que `Get-Date` retorna.

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

O próximo `Get-TypeData` cmdlet para obter todos os dados de tipo estendido para o tipo **System. DateTime** e canaliza para o `Remove-TypeData` cmdlet para excluir os dados de tipo estendido. O último `Get-Date` cmdlet mostra o efeito de excluir os dados de tipo estendido para o tipo **System. DateTime** . Como a propriedade **System. DateTime** não existe mais, um comando para obter seu valor não retorna nada.

### Exemplo 3: remover tipos estendidos para módulos

Este exemplo remove todos os dados de tipo estendido para objetos de módulo. Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo de objeto e remove todos os dados de tipo de todos os objetos desse tipo.

```powershell
Get-Module | Remove-TypeData
```

### Exemplo 4: remover tipos estendidos de módulos especificados

Este exemplo usa o parâmetro **path** do `Remove-TypeData` cmdlet para remover os tipos estendidos que são definidos nos `Types.ps1xml` arquivos que são adicionados pelos módulos **PSScheduledJob** e **PSWorkflow** . Esse comando não afeta os dados de tipo dinâmico que são adicionados usando o `Update-TypeData` cmdlet. O comando terá êxito somente quando os módulos tiverem sido importados para a sessão atual.

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

### Exemplo 5: remover tipos estendidos de uma sessão remota

Este exemplo remove os tipos estendidos de uma sessão remota. O comando usa o `Invoke-Command` cmdlet para remover dados de tipo estendido para todos os tipos de CIM nas sessões na `$S` variável.

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## Parâmetros

### -Path

Especifica uma matriz de arquivos que esse cmdlet exclui dos dados de tipo estendido da sessão. Este parâmetro é necessário.

Insira os caminhos e os nomes de arquivo de um ou mais `Types.ps1xml` arquivos. Não há suporte para caracteres curinga. Se você omitir o caminho, o local padrão a considerar é o diretório atual.

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeData

Especifica os dados de tipo que esse cmdlet exclui da sessão. Este parâmetro é necessário. Insira uma variável que contém objetos **TypeData** ( **System. Management. Automation. Runspaces. TypeData** ) ou um comando que obtém objetos **TypeData** , como um `Get-TypeData` comando. Você também pode canalizar objetos **TypeData** para `Remove-TypeData` .

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TypeName

Especifica os tipos para os quais este cmdlet exclui todos os dados de tipo estendido. Para tipos no namespace System, insira o nome abreviado. Caso contrário, é necessário o nome completo do tipo. Não há suporte para caracteres curinga.

Você pode canalizar nomes de tipo para `Remove-TypeData` . Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System. Management. Automation. Runspaces. TypeData

Você pode canalizar o objeto **TypeData** , como aqueles que o `Get-TypeData` cmdlet retorna, para `Remove-TypeData` .

### System.String

Você pode canalizar os nomes de tipo para `Remove-TypeData` . Quando você canaliza um objeto para `Remove-TypeData` , `Remove-TypeData` Obtém o nome do tipo do objeto e remove todos os dados do tipo para o tipo de objeto.

## Saídas

### Nenhum

Este cmdlet não gera saída.

## Observações

`Remove-TypeData` pode remover somente os dados de tipo estendido na sessão atual. Ele não pode remover dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.

## Links relacionados

[Get-TypeData](Get-TypeData.md)

[Update-TypeData](Update-TypeData.md)

