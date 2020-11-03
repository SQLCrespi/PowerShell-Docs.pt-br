---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 29a39e88d6d39659df1dd9d2e05318351dc47f3a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192906"
---
# Add-Member

## SINOPSE
Adiciona propriedades e métodos personalizados a uma instância de um objeto do PowerShell.

## SYNTAX

### TypeNameset (padrão)

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### NotePropertyMultiMemberSet

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### NotePropertySingleMemberSet

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### MemberSet

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

O `Add-Member` cmdlet permite que você adicione Membros (Propriedades e métodos) a uma instância de um objeto do PowerShell. Por exemplo, você pode adicionar um membro NoteProperty que contém uma descrição do objeto ou um membro **ScriptMethod** que executa um script para alterar o objeto.

Para usar `Add-Member` , redirecione o objeto para `Add-Member` ou use o parâmetro **InputObject** para especificar o objeto.

O parâmetro **MemberType** indica o tipo de membro que você deseja adicionar. O parâmetro **Name** atribui um nome ao novo membro e o parâmetro **Value** define o valor do membro.

As propriedades e métodos que você adiciona são acrescentados apenas à instância específica do objeto especificado por você. `Add-Member` Não altera o tipo de objeto. Para criar um novo tipo de objeto, use o `Add-Type` cmdlet.

Você também pode usar o `Export-Clixml` cmdlet para salvar a instância do objeto, incluindo os membros adicionais, em um arquivo. Em seguida, você pode usar o `Import-Clixml` cmdlet para recriar a instância do objeto a partir das informações armazenadas no arquivo exportado.

A partir do Windows PowerShell 3,0, `Add-Member` há novos recursos que facilitam a adição de propriedades de anotação a objetos.
Você pode usar os parâmetros **NotePropertyName** e **NotePropertyValue** para definir uma propriedade de anotação ou usar o parâmetro **NotePropertyMembers** , que usa uma tabela de hash de valores e nomes de propriedades de anotação.

Além disso, a partir do Windows PowerShell 3.0, o parâmetro **PassThru** , que gera um objeto de saída, é necessário com menos frequência. `Add-Member` Agora adiciona os novos membros diretamente ao objeto de entrada de mais tipos. Para obter mais informações, consulte a descrição do parâmetro **PassThru** .

## EXEMPLOS

### Exemplo 1: adicionar uma propriedade de observação a um PSObject

O exemplo a seguir adiciona uma propriedade de observação de **status** com um valor de "Done" para o objeto **FileInfo** que representa o `Test.txt` arquivo.

O primeiro comando usa o `Get-ChildItem` cmdlet para obter um objeto **FileInfo** que representa o `Test.txt` arquivo. Ele o salva na `$a` variável.

O segundo comando adiciona a propriedade Note ao objeto em `$a` .

O terceiro comando usa a notação de ponto para obter o valor da propriedade **status** do objeto no `$a` . Como mostra a saída, o valor é "Done".

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### Exemplo 2: adicionar uma propriedade de alias a um PSObject

O exemplo a seguir adiciona uma propriedade de alias de **tamanho** ao objeto que representa o `Test.txt` arquivo. A nova propriedade é um alias para a propriedade **Length** .

O primeiro comando usa o `Get-ChildItem` cmdlet para obter o `Test.txt` objeto **FileInfo** .

O segundo comando adiciona a propriedade de alias de **tamanho** .
O terceiro comando usa a notação de ponto para obter o valor da nova propriedade **size** .

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### Exemplo 3: adicionar uma propriedade de observação StringUse a uma cadeia de caracteres

Este exemplo adiciona a propriedade **StringUse** note a uma cadeia de caracteres.
Como `Add-Member` o não pode adicionar tipos a objetos de entrada de **cadeia de caracteres** , você pode especificar o parâmetro **PassThru** para gerar um objeto de saída. O último comando no exemplo exibe a nova propriedade.

Este exemplo usa o parâmetro **NotePropertyMembers** . O valor do parâmetro **NotePropertyMembers** é uma tabela de hash. A chave é o nome da propriedade de observação, **StringUse** , e o valor é o valor da propriedade Note, **Display** .

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### Exemplo 4: adicionar um método de script a um objeto FileInfo

Este exemplo adiciona o método de script **SizeInMB** a um objeto **FileInfo** que calcula o tamanho do arquivo para o megabyte mais próximo. O segundo comando cria um **scriptblock** que usa o método estático **round** do `[math]` tipo para arredondar o tamanho do arquivo para a segunda casa decimal.

O parâmetro **Value** também usa a `$This` variável automática, que representa o objeto atual. A `$This` variável é válida somente em blocos de script que definem novas propriedades e métodos.

O último comando usa a notação de ponto para chamar o novo método de script **SizeInMB** no objeto na `$A` variável.

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### Exemplo 5: copiar todas as propriedades de um objeto para outro

Esta função copia todas as propriedades de um objeto em outro objeto.

O `foreach` loop usa o `Get-Member` cmdlet para obter cada uma das propriedades do objeto **from** . Os comandos dentro do `foreach` loop são executados em série em cada uma das propriedades.

O `Add-Member` comando adiciona a propriedade do objeto **de** ao objeto **to** como uma **NoteProperty** . O valor é copiado usando o parâmetro **Value** . Ele usa o parâmetro **Force** para adicionar membros com o mesmo nome de membro.

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### Exemplo 6: criar um objeto personalizado

Este exemplo cria um objeto personalizado de **ativo** .

O `New-Object` cmdlet cria um **PSObject** . O exemplo salva o **PSObject** na `$Asset` variável.

O segundo comando usa o `[ordered]` acelerador de tipo para criar um dicionário ordenado de nomes e valores. O comando salva o resultado na `$D` variável.

O terceiro comando usa o parâmetro **NotePropertyMembers** do `Add-Member` cmdlet para adicionar o dicionário na `$D` variável ao **PSObject** .
A propriedade **TypeName** atribui um novo nome, **ativo** , ao **PSObject** .

O último comando canaliza o novo objeto **Asset** para o `Get-Member` cmdlet. A saída mostra que o objeto tem um nome de tipo de **ativo** e as propriedades de observação que definimos no dicionário ordenado.

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## PARAMETERS

### -Force

Indica que esse cmdlet adiciona um novo membro até mesmo o objeto tem um membro personalizado com o mesmo nome.
Você não pode usar o parâmetro **Force** para substituir um membro padrão de um tipo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica o objeto ao qual o novo membro é adicionado.
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberType

Especifica o tipo do membro a ser adicionado.
Este parâmetro é necessário.
Os valores aceitáveis para esse parâmetro são:

- NoteProperty
- AliasProperty
- ScriptProperty
- CodeProperty
- ScriptMethod
- CodeMethod

Para obter informações sobre esses valores, consulte [Enumeração PSMemberTypes](/dotnet/api/system.management.automation.psmembertypes) na biblioteca MSDN.

Nem todos os objetos têm todos os tipos de membros.
Se você especificar um tipo de membro que o objeto não tem, o PowerShell retornará um erro.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome do membro que este cmdlet adiciona.

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotePropertyMembers

Especifica uma tabela de hash ou dicionário ordenado de valores e nomes de propriedade de observação.
Digite uma tabela de hash ou dicionário no qual as chaves são os nomes de propriedade de observação e os valores são valores de propriedade de observação.

Para obter mais informações sobre tabelas de hash e dicionários ordenados no PowerShell, consulte [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotePropertyName

Especifica o nome da propriedade de observação.

Use este parâmetro com o parâmetro **NotePropertyValue** .
Esse parâmetro é opcional.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotePropertyValue

Especifica o valor da propriedade de observação.

Use esse parâmetro com o parâmetro **NotePropertyName** .
Esse parâmetro é opcional.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

Para a maioria dos objetos, `Add-Member` o adiciona os novos membros ao objeto de entrada.
No entanto, quando o objeto de entrada é uma cadeia de caracteres, o `Add-Member` não pode adicionar o membro ao objeto de entrada.
Para estes objetos, use o parâmetro **PassThru** para criar um objeto de saída.

No Windows PowerShell 2,0, `Add-Member` adicionamos membros somente ao wrapper do **PSObject** de objetos, não ao objeto.
Use o parâmetro **PassThru** para criar um objeto de saída para qualquer objeto que tenha um wrapper de **PSObject** .

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

### -Segundovalue

Especifica informações opcionais adicionais sobre membros **AliasProperty** , **ScriptProperty** , **CodeProperty** ou **CodeMethod** .

Se usado ao adicionar um **AliasProperty** , esse parâmetro deve ser um tipo de dados.
Uma conversão para o tipo de dados especificado é adicionada ao valor de **AliasProperty** .

Por exemplo, se você adicionar um **AliasProperty** que forneça um nome alternativo para uma propriedade de cadeia de caracteres, você também poderá especificar um parâmetro de **segundovalue** de **System. Int32** para indicar que o valor dessa propriedade de cadeia de caracteres deve ser convertido em um inteiro quando acessado usando o **AliasProperty** correspondente.

Você pode usar o parâmetro **segundovalue** para especificar um **scriptblock** adicional ao adicionar um membro **ScriptProperty** . O primeiro **scriptblock** , especificado no parâmetro **Value** , é usado para obter o valor de uma variável. O segundo **scriptblock** , especificado no parâmetro **SecondValue** , é usado para definir o valor de uma variável.

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica o valor inicial do membro adicionado.
Se você adicionar um membro **AliasProperty** , **CodeProperty** , **ScriptProperty** ou **CodeMethod** , poderá fornecer informações adicionais opcionais usando o parâmetro **SecondValue** .

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Especifica um nome para o tipo.

Quando o tipo é uma classe no namespace **System** ou um tipo que tem um acelerador de tipo, você pode inserir o nome curto do tipo. Caso contrário, é necessário o nome completo do tipo.
Esse parâmetro é efetivo somente quando **InputObject** é um **PSObject** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar qualquer tipo de objeto para este cmdlet.

## SAÍDAS

### Nenhum ou System. Object

Quando você usa o parâmetro **PassThru** , esse cmdlet retorna o objeto recém estendido.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

Você pode adicionar membros somente a objetos **PSObject** . Para determinar se um objeto é um objeto **PSObject** , use o `-is` operador.

Por exemplo, para testar um objeto armazenado na `$obj` variável, digite `$obj -is [PSObject]` .

Os nomes dos parâmetros **MemberType** , **Name** , **Value** e **SecondValue** são opcionais.
Se você omitir os nomes de parâmetro, os valores de parâmetro não nomeados deverão aparecer nesta ordem: **MemberType** , **Name** , **Value** e **SecondValue** .

Se você incluir os nomes dos parâmetros, os parâmetros podem aparecer em qualquer ordem.

Você pode usar a `$this` variável automática em blocos de script que definem os valores de novas propriedades e métodos.
A `$this` variável refere-se à instância do objeto ao qual as propriedades e os métodos estão sendo adicionados. Para obter mais informações sobre a `$this` variável, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## LINKS RELACIONADOS

[Export-Clixml](Export-Clixml.md)

[Get-Member](Get-Member.md)

[Import-Clixml](Import-Clixml.md)

[New-Object](New-Object.md)

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
