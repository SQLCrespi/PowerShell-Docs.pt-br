---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194367"
---
# Test-Json

## SINOPSE
Testa se uma cadeia de caracteres é um documento JSON válido

## SYNTAX

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## DESCRIPTION

O `Test-Json` cmdlet testa se uma cadeia de caracteres é um documento JavaScript Object Notation (JSON) válido e pode, opcionalmente, verificar esse documento JSON em relação a um esquema fornecido.

A cadeia de caracteres verificada pode ser usada com o `ConvertFrom-Json` cmdlet converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell ou enviado a outro programa ou serviço Web que acessa a entrada JSON.

Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.

Esse cmdlet foi introduzido no PowerShell 6,1

## EXEMPLOS

### Exemplo 1: testar se um objeto é um JSON válido

Este exemplo testa se a cadeia de caracteres de entrada é um documento JSON válido.

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### Exemplo 2: testar um objeto em relação a um esquema fornecido

Este exemplo usa uma cadeia de caracteres que contém um esquema JSON e o compara a uma cadeia de caracteres de entrada.

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

Neste exemplo, obtemos um erro porque o esquema espera um inteiro para a **idade** , mas a entrada JSON que testamos usa um valor de cadeia de caracteres em vez disso.

Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).

## PARAMETERS

### -JSON

Especifica a cadeia de caracteres JSON para testar a validade. Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia. Você também pode canalizar uma cadeia de caracteres para `Test-Json` .

O parâmetro **JSON** é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Esquema

Especifica um esquema para validar a entrada JSON. Se for passado, `Test-Json` validará que a entrada JSON está de acordo com a especificação especificada pelo parâmetro de **esquema** e retornará `$True` somente se a entrada estiver em conformidade com o esquema fornecido.

Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres JSON para `Test-Json` .

## SAÍDAS

### Booliano

## OBSERVAÇÕES

O `Test-Json` cmdlet é implementado usando a [classe NJsonSchema](https://github.com/RSuter/NJsonSchema).

## LINKS RELACIONADOS

[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[Detalhes adicionais do esquema JSON](https://json-schema.org/)

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
