---
ms.date: 07/09/2020
ms.topic: reference
title: Conversores de tipo de sistema de tipo estendido
description: Conversores de tipo de sistema de tipo estendido
ms.openlocfilehash: 0774e9eaae1187162b3d55cc45b902f7411a1f18
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648434"
---
# <a name="ets-type-converters"></a>Conversores de tipo do ETS

O ETS usa dois tipos básicos de conversores de tipo quando uma chamada é feita ao `LanguagePrimitives.ConvertTo(System.Object, System.Type)` método. Quando esse método é chamado, o PowerShell tenta executar a conversão de tipo usando seus conversores de idioma padrão do PowerShell ou um conversor personalizado. Se o PowerShell não puder executar a conversão, ele lançará uma exceção **PSInvalidCastException** .

## <a name="standard-windows-powershell-language-converters"></a>Conversores de idioma padrão do Windows PowerShell

Essas conversões padrão são verificadas antes de qualquer conversões personalizadas e não podem ser substituídas. A tabela a seguir lista as conversões de tipo executadas pelo PowerShell quando o `ConvertTo(System.Object, System.Type)` método é chamado. Lembre-se de que as referências aos parâmetros **valueToConvert** e **ResultType** se referem aos parâmetros do `ConvertTo(System.Object,System.Type)` método.

| De (valueToConvert) |  Para (ResultType)  |                                                                               Retornos                                                                               |
| --------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nulo                  | Cadeia de caracteres            | ""                                                                                                                                                                  |
| Nulo                  | Char              | '\0'                                                                                                                                                                |
| Nulo                  | Numérico           | `0` do tipo especificado no parâmetro **ResultType** .                                                                                                          |
| Nulo                  | Booliano           | Resultados da chamada para o `IsTrue(System.Object)(Null)` método.                                                                                                        |
| Nulo                  | PSObject          | Novo objeto do tipo **PSObject**.                                                                                                                                    |
| Nulo                  | Tipo sem valor    | Nulo.                                                                                                                                                               |
| Nulo                  | &lt;T anulável&gt; | Nulo.                                                                                                                                                               |
| Classe derivada         | Classe base        | **valueToConvert**                                                                                                                                                  |
| Dado              | Void              | **AutomationNull. Value**                                                                                                                                            |
| Dado              | Cadeia de caracteres            | Chama o `ToString` mecanismo.                                                                                                                                         |
| Dado              | Booliano           | `IsTrue(System.Object) (valueToConvert)`                                                                                                                            |
| Dado              | PSObject          | Resultados da chamada para o `AsPSObject(System.Object) (valueToConvert)` método.                                                                                         |
| Dado              | Documento XML      | Converte **valueToConvert** em String e, em seguida, chama o construtor **XmlDocument** .                                                                                      |
| Array                 | Array             | Tenta converter cada elemento da matriz.                                                                                                                      |
| Singleton             | Array             | `Array[0]` é igual a **valueToConvert** que é convertido para o tipo de elemento da matriz.                                                                            |
| IDictionary           | Tabela de hash        | Resultados da chamada para Hashtable (valueToConvert).                                                                                                                       |
| String                | Char[]            | `valueToConvert.ToCharArray`                                                                                                                                        |
| Cadeia de caracteres                | RegEx             | Resultados da chamada para `Regx(valueToConvert)` .                                                                                                                          |
| Cadeia de caracteres                | Tipo              | Retorna o tipo apropriado usando o parâmetro **valueToConvert** para pesquisar **RunspaceConfiguration. assemblies**.                                                 |
| String                | Numérico           | Se **valueToConvert** for "", retornará `0` o **ResultType**. Caso contrário, a cultura "cultura invariável" é usada para produzir um valor numérico.                       |
| Integer               | System.Enum       | Converte o inteiro para a constante se o inteiro for definido pela enumeração. Se o inteiro não for definido, uma exceção **PSInvalidCastException** será lançada. |

## <a name="custom-conversions"></a>Conversões personalizadas

Se o PowerShell não puder converter o tipo usando um conversor de idioma padrão do PowerShell, ele verificará conversores personalizados. O PowerShell procura vários tipos de conversores personalizados na ordem descrita nesta seção. Lembre-se de que as referências aos parâmetros **valueToConvert** e **ResultType** se referem aos parâmetros do `ConvertTo(System.Object, System.Type)` método. Se um conversor personalizado lançar uma exceção, nenhuma tentativa adicional será feita para converter o objeto e essa exceção será encapsulada em uma exceção **PSInvalidCastException** , que é então lançada.

## <a name="powershell-type-converter"></a>Conversor de tipo do PowerShell

Os conversores de tipo do PowerShell são usados para converter um único tipo ou uma família de tipos, como todos os tipos que derivam da classe **System. Enum** . Para criar um conversor de tipo do PowerShell, você deve implementar uma classe PSTypeConverter e associar essa implementação à classe de destino. Há duas maneiras de associar o conversor de tipo do PowerShell com sua classe de destino.

- Por meio do arquivo de configuração de tipo
- Aplicando o atributo **TypeConverterAttribute** à classe de destino

Conversores de tipo do PowerShell, derivados da classe abstrata [PSTypeConverter](/dotnet/api/system.management.automation.pstypeconverter) , fornecem métodos para converter um objeto para um tipo específico ou de um tipo específico. Se o parâmetro **valueToConvert** contiver um objeto que tenha um conversor de tipo do PowerShell associado a ele, o PowerShell chamará o `PSTypeConverter.ConvertTo(System.Object, System.Type,System.IFormatProvider, System.Boolean)`
método do conversor associado para converter o objeto para o tipo especificado pelo parâmetro **ResultType** . Se o parâmetro **ResultType** fizer referência a um tipo que tenha um conversor de tipo do PowerShell associado a ele, o PowerShell chamará o `PSTypeConverter.ConvertFrom(System.Object,System.Type, System.IFormatProvider, System.Boolean)`
método do conversor associado para converter o objeto do tipo especificado pelo parâmetro **ResultType** .

## <a name="system-type-converter"></a>Conversor de tipo de sistema

Conversores de tipo de sistema são usados para converter uma classe de destino específica. Esse tipo de conversor não pode ser usado para converter uma família de classes. Para criar um conversor de tipo de sistema, você deve implementar uma classe [TypeConverter](/dotnet/api/system.management.automation.runspaces.typedata.typeconverter#System_Management_Automation_Runspaces_TypeData_TypeConverter) e associar essa implementação à classe de destino. Há duas maneiras de associar o conversor de tipo de sistema à sua classe de destino.

- Por meio do arquivo de configuração de tipo
- Aplicando o atributo TypeConverterAttribute à classe de destino

## <a name="parse-converter"></a>Conversor de análise

Se o parâmetro **valueToConvert** for uma cadeia de caracteres e o tipo de objeto do parâmetro **ResultType** tiver um `Parse` método, o `Parse` método será chamado para converter a cadeia de caracteres.

## <a name="constructor-converter"></a>Conversor de Construtor

Se o tipo de objeto do parâmetro **ResultType** tiver um construtor que tenha um único parâmetro que seja do mesmo tipo que o objeto do parâmetro **valueToConvert** , esse construtor será chamado.

## <a name="implicit-cast-operator-converter"></a>Conversor de operador de conversão implícita

Se o parâmetro **valueToConvert** tiver um operador de conversão implícita que converte em **ResultType**, seu operador cast será chamado. Se o parâmetro **ResultType** tiver um operador de conversão implícita que converta de **valueToConvert**, seu operador cast será chamado.

## <a name="explicit-cast-operator-converter"></a>Conversor de operador de conversão explícita

Se o parâmetro **valueToConvert** tiver um operador de conversão explícita que converte em **ResultType**, seu operador cast será chamado. Se o parâmetro **ResultType** tiver um operador cast explícito que converte de **valueToConvert**, seu operador cast será chamado.
