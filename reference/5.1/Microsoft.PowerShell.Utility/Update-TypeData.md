---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: eb7bafff1af34ef34a1b67c1fbe8f9e2db0ca7ad
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193721"
---
# Update-TypeData

## Sinopse
Atualiza os dados de tipo estendido na sessão.

## Syntax

### Fileset (padrão)

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DynamicTypeSet

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TypeDataSet

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Descrição

O `Update-TypeData` cmdlet atualiza os dados de tipo estendido na sessão recarregando os `Types.ps1xml` arquivos na memória e adicionando novos dados de tipo estendido.

Por padrão, o PowerShell carrega dados de tipo estendido conforme necessário. Sem parâmetros, `Update-TypeData` o recarrega todos os `Types.ps1xml` arquivos que ele carregou na sessão, incluindo os arquivos de tipo que você adicionou. Você pode usar os parâmetros de `Update-TypeData` para adicionar novos arquivos de tipo e adicionar e substituir dados de tipo estendido.

O `Update-TypeData` cmdlet pode ser usado para pré-carregar todos os dados de tipo. Esse recurso é particularmente útil quando você estiver desenvolvendo tipos e desejar carregar esses novos tipos para fins de teste.

A partir do Windows PowerShell 3,0, você pode usar `Update-TypeData` para adicionar e substituir dados de tipo estendido na sessão sem usar um `Types.ps1xml` arquivo. Dados de tipo adicionados dinamicamente, ou seja, sem um arquivo, são adicionados somente à sessão atual. Para adicionar os dados de tipo a todas as sessões, adicione um `Update-TypeData` comando ao seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Além disso, a partir do Windows PowerShell 3,0, você pode usar o `Get-TypeData` cmdlet para obter os tipos estendidos na sessão atual e o `Remove-TypeData` cmdlet para excluir tipos estendidos da sessão atual.

As exceções que ocorrem em Propriedades ou a adição de propriedades a um `Update-TypeData` comando não relatam erros. Isso é para suprimir exceções que podem ocorrer em muitos tipos comuns durante a formatação e a saída. Se você estiver obtendo propriedades do .NET, poderá contornar a supressão de exceções usando a sintaxe do método, conforme mostrado no exemplo a seguir:

`"hello".get_Length()`

Observe que a sintaxe do método só pode ser usada com as propriedades do .NET. As propriedades que são adicionadas executando o `Update-TypeData` cmdlet não podem usar a sintaxe do método.

Para obter mais informações sobre os `Types.ps1xml` arquivos no PowerShell, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

## Exemplos

### Exemplo 1: atualizar tipos estendidos

```powershell
Update-TypeData
```

Esse comando atualiza a configuração de tipo estendido dos `Types.ps1xml` arquivos que já foram usados na sessão.

### Exemplo 2: atualizar tipos várias vezes

Este exemplo mostra como atualizar os tipos em um arquivo de tipo várias vezes na mesma sessão.

O primeiro comando atualiza a configuração de tipo estendido dos `Types.ps1xml` arquivos, processando os `TypesA.types.ps1xml` `TypesB.types.ps1xml` arquivos e primeiro.

O segundo comando mostra como atualizar `TypesA.types.ps1xml` novamente, como você pode fazer se adicionou ou alterou um tipo no arquivo. Você pode repetir o comando anterior para o `TypesA.types.ps1xml` arquivo ou executar um `Update-TypeData` comando sem parâmetros, pois `TypesA.types.ps1xml` já está na lista de arquivos de tipo da sessão atual.

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### Exemplo 3: adicionar uma propriedade de script a objetos DateTime

Este exemplo usa `Update-TypeData` para adicionar a propriedade de script **Quarter** aos objetos **System. DateTime** na sessão atual, como os retornados pelo `Get-Date` cmdlet.

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

O `Update-TypeData` comando usa o parâmetro **TypeName** para especificar **o tipo System. DateTime** , o parâmetro **MemberName** para especificar um nome para a nova propriedade, a propriedade **MemberType** para especificar o tipo **ScriptProperty** e o parâmetro **Value** para especificar o script que determina o trimestre anual.

O valor da propriedade **Value** é um script que calcula o trimestre atual. O bloco de script usa a `$this` variável automática para representar a instância atual do objeto e o operador in para determinar se o valor de mês aparece em cada matriz de inteiros. Para obter mais informações sobre o `-in` operador, consulte [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).

O segundo comando obtém a nova propriedade Quarter da data atual.

### Exemplo 4: atualizar um tipo que é exibido em listas por padrão

Este exemplo mostra como definir as propriedades de um tipo que é exibido em listas por padrão, ou seja, quando nenhuma propriedade é especificada. Como os dados de tipo não são especificados em um `Types.ps1xml` arquivo, ele só entra em vigor na sessão atual.

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

O primeiro comando usa o `Update-TypeData` cmdlet para definir as propriedades de lista padrão para o tipo **System. DateTime** . O comando usa o parâmetro **TypeName** para especificar o tipo e o parâmetro **DefaultDisplayPropertySet** para especificar as propriedades padrão para uma lista. As propriedades selecionadas incluem a nova propriedade de script de **trimestre** que foi adicionada em um exemplo anterior.

O segundo comando usa o `Get-Date` cmdlet para obter um objeto **System. DateTime** que representa a data atual. O comando usa um operador de pipeline ( `|` ) para enviar o objeto **DateTime** para o `Format-List` cmdlet. Como o `Format-List` comando não especifica as propriedades a serem exibidas na lista, o PowerShell usa os valores padrão que foram estabelecidos pelo `Update-TypeData` comando.

### Exemplo 5: atualizar dados de tipo para um objeto de pipe

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

Este exemplo demonstra que, quando você canaliza um objeto para `Update-TypeData` , `Update-TypeData` adiciona dados de tipo estendido para o tipo de objeto.

Essa técnica é mais rápida do que usar o `Get-Member` cmdlet ou o `Get-Type` método para obter o tipo de objeto. No entanto, se você canalizar uma coleção de objetos para `Update-TypeData` , ele atualizará os dados de tipo do primeiro tipo de objeto e, em seguida, retornará um erro para todos os outros objetos na coleção, pois o membro já está definido no tipo.

O primeiro comando usa o `Get-Module` cmdlet para obter o módulo PSScheduledJob. O comando canaliza o objeto de módulo para o `Update-TypeData` cmdlet, que atualiza os dados de tipo para o tipo **System. Management. Automation. PSModuleInfo** e os tipos derivados dele, como o tipo ModuleInfoGrouping que `Get-Module` retorna quando você usa o parâmetro **listAvailable** no comando.

Os `Update-TypeData` comandos adicionam a propriedade de script **SupportsUpdatableHelp** a todos os módulos importados. O valor do parâmetro **Value** é um script que retorna `$True` se a propriedade **HelpInfoUri** do módulo for populada e `$False` , de outra forma,.

O segundo comando canaliza os objetos de módulo do `Get-Module` para o `Format-Table` cmdlet, que exibe as propriedades **Name** e **SupportsUpdatableHelp** de todos os módulos em uma lista.

## Parâmetros

### -AppendPath

Especifica o caminho para arquivos opcionais `.ps1xml` . Os arquivos especificados são carregados na ordem em que estão listados depois que os arquivos internos são carregados. Também é possível canalizar um valor de **AppendPath** para `Update-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultDisplayProperty

Especifica a propriedade do tipo que é exibido pelo `Format-Wide` cmdlet quando nenhuma outra propriedade é especificada.

Digite o nome de uma propriedade estendida ou padrão do tipo. O valor desse parâmetro pode ser o nome de um tipo que é adicionado no mesmo comando.

Esse valor só é eficaz quando não há exibições amplas definidas para o tipo em um `Format.ps1xml` arquivo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultDisplayPropertySet

Especifica uma ou mais propriedades do tipo. Essas propriedades são exibidas pelo `Format-List` cmdlet quando nenhuma outra propriedade é especificada.

Digite os nomes das propriedades estendidas ou padrão do tipo. O valor desse parâmetro pode ser os nomes de tipos que são adicionados no mesmo comando.

Esse valor só é eficaz quando não há exibições de lista definidas para o tipo em um `Format.ps1xml` arquivo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultKeyPropertySet

Especifica uma ou mais propriedades do tipo. Essas propriedades são usadas pelos `Group-Object` `Sort-Object` cmdlets e quando nenhuma outra propriedade é especificada.

Digite os nomes das propriedades estendidas ou padrão do tipo. O valor desse parâmetro pode ser os nomes de tipos que são adicionados no mesmo comando.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que o cmdlet usa os dados de tipo especificados, mesmo que os dados de tipo já tenham sido especificados para esse tipo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InheritPropertySerializationSet

Indica se o conjunto de propriedades que são serializadas é herdado. O valor padrão é `$Null`. Os valores aceitáveis para esse parâmetro são:

- `$True`. O conjunto de propriedades é herdado.
- `$False`. O conjunto de propriedades não é herdado.
- `$Null`. A herança não está definida.

Esse parâmetro é válido somente quando o valor do parâmetro **o** é `SpecificProperties` . Quando o valor desse parâmetro é `$False` , o parâmetro **PropertySerializationSet** é necessário.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberName

Especifica o nome de uma propriedade ou método.

Use este parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou método de um tipo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberType

Especifica o tipo do membro para adicionar ou alterar.

Use este parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou método de um tipo. Os valores aceitáveis para esse parâmetro são:

- AliasProperty
- CodeMethod
- CodeProperty
- NoteProperty
- ScriptMethod
- ScriptProperty

Para obter informações sobre esses valores, consulte [Enumeração PSMemberTypes](/dotnet/api/system.management.automation.psmembertypes).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrependPath

Especifica o caminho para os arquivos opcionais `.ps1xml` . Os arquivos especificados são carregados na ordem em que estão listados antes que os arquivos internos são carregados.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertySerializationSet

Especifica os nomes das propriedades serializadas. Use esse parâmetro quando o valor do parâmetro **SerializationMethod** for **SpecificProperties** .

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Segundovalue

Especifica valores adicionais para os membros **AliasProperty** , **ScriptProperty** , **CodeProperty** ou **CodeMethod** .

Use esse parâmetro com os parâmetros **TypeName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.

Quando o valor do parâmetro **MemberType** é `AliasProperty` , o valor do parâmetro **segundovalue** deve ser um tipo de dados. O PowerShell converte (isto é, conversões) do valor da propriedade alias para o tipo especificado. Por exemplo, se você adicionar uma propriedade de alias que forneça um nome alternativo para uma propriedade de cadeia de caracteres, também poderá especificar um **segundovalue** de **System. Int32** para converter o valor de cadeia de caracteres com alias em um inteiro.

Quando o valor do parâmetro **MemberType** é `ScriptProperty` , você pode usar o parâmetro **segundovalue** para especificar um bloco de script adicional. O bloco de script no valor do parâmetro **Value** obtém o valor de uma variável. O bloco de script no valor do parâmetro **SecondValue** define o valor da variável.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerializationDepth

Especifica quantos níveis de objetos de tipo são serializados como cadeias de caracteres. O valor padrão `1` serializa o objeto e suas propriedades. Um valor `0` serializa o objeto, mas não suas propriedades. Um valor `2` serializa o objeto, suas propriedades e todos os objetos em valores de propriedade.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -O

Especifica um método de serialização para o tipo. Um método de serialização determina quais propriedades do tipo são serializadas e a técnica usada para serializá-las. Os valores aceitáveis para esse parâmetro são:

- `AllPublicProperties`. Serialize todas as propriedades públicas do tipo. Você pode usar o parâmetro **SerializationDepth** para determinar se as propriedades filho são serializadas.
- `String`. Serialize o tipo como uma cadeia de caracteres. Você pode usar o **StringSerializationSource** para especificar uma propriedade do tipo a ser usado como o resultado da serialização. Caso contrário, o tipo é serializado usando o método **ToString** do objeto.
- `SpecificProperties`. Serialize apenas as propriedades especificadas deste tipo. Use o parâmetro **PropertySerializationSet** para especificar as propriedades do tipo serializado.
  Você também pode usar o parâmetro **InheritPropertySerializationSet** para determinar se o conjunto de propriedades é herdado e o parâmetro **SerializationDepth** para determinar se as propriedades filho são serializadas.

No PowerShell, os métodos de serialização são armazenados em objetos internos **PSStandardMembers** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StringSerializationSource

Especifica o nome de uma propriedade do tipo. O valor da propriedade especificada é usado como o resultado da serialização. Esse parâmetro é válido somente quando o valor do parâmetro **o** é String.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetTypeForDeserialization

Especifica o tipo ao qual objeto desse tipo é convertido quando desserializado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeAdapter

Especifica o tipo de um adaptador de tipo, como **Microsoft. PowerShell. CIM. CimInstanceAdapter** . Um adaptador de tipo permite que o PowerShell obtenha os membros de um tipo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeConverter

Especifica um conversor de tipos para converter valores entre tipos diferentes. Se for definido um conversor de tipo para um tipo, uma instância do conversor de tipo é usada para a conversão.

Insira um **System.Type** valor derivado das classes **System.ComponentModel.TypeConverter** ou **System.Management.Automation.PSTypeConverter** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeData

Especifica uma matriz do tipo de dados que esse cmdlet adiciona à sessão. Insira uma variável que contém um objeto **TypeData** ou um comando que obtém um objeto **TypeData** , como um `Get-TypeData` comando. Também é possível canalizar um objeto **TypeData** para `Update-TypeData` .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TypeName

Especifica o nome do tipo a ser estendido.

Para tipos no namespace **System** , insira o nome abreviado. Caso contrário, é necessário o nome completo do tipo. Não há suporte para caracteres curinga.

Você pode canalizar nomes de tipo para `Update-TypeData` . Quando você canaliza um objeto para `Update-TypeData` , `Update-TypeData` Obtém o nome do tipo do objeto e digita os dados para o tipo de objeto.

Use esse parâmetro com os parâmetros **MemberName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Value

Especifica o valor da propriedade ou método.

Se você adicionar um `AliasProperty` membro,, `CodeProperty` `ScriptProperty` ou `CodeMethod` , você poderá usar o parâmetro **segundovalue** para adicionar informações adicionais.

Use esse parâmetro com os parâmetros **MemberName** , **MemberType** , **Value** e **SecondValue** para adicionar ou alterar uma propriedade ou um método de um tipo.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System.String

É possível canalizar uma cadeia de caracteres que contém os valores dos parâmetros **AppendPath** , **TypeName** ou **TypeData** para `Update-TypeData` .

## Saídas

### Nenhum

Este cmdlet não retorna nenhuma saída.

## Observações

## Links relacionados

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Get-TypeData](Get-TypeData.md)

[Remove-TypeData](Remove-TypeData.md)
