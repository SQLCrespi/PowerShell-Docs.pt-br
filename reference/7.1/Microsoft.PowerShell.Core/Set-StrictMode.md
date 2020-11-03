---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: c68b8a7e106b9bac56199684a926f3dabe006e7b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194568"
---
# Set-StrictMode

## SINOPSE
Estabelece e impõe regras de codificação em expressões, scripts e blocos de script.

## SYNTAX

### Versão (padrão)

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### Desativado

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## DESCRIPTION

O `Set-StrictMode` cmdlet configura o modo estrito para o escopo atual e todos os escopos filho e ativa e desativa. Quando o modo estrito está ativado, o PowerShell gera um erro de encerramento quando o conteúdo de uma expressão, script ou bloco de script viola as regras básicas de codificação de práticas recomendadas.

Use o parâmetro **version** para determinar quais regras de codificação são impostas.

`Set-PSDebug -Strict` o cmdlet ativa o modo estrito para o escopo global. `Set-StrictMode` afeta apenas o escopo atual e seus escopos filho. Portanto, você pode usá-lo em um script ou função para substituir a configuração herdada do escopo global.

Quando `Set-StrictMode` está desativado, o PowerShell tem os seguintes comportamentos:

- Presumidas variáveis não inicializadas devem ter um valor de 0 (zero) ou `$Null` , dependendo do tipo
- Referências a propriedades não existentes retornam `$Null`
- Os resultados da sintaxe de função incorreta variam de acordo com as condições de erro
- A tentativa de recuperar um valor usando um índice inválido em uma matriz retorna `$Null`

## EXEMPLOS

### Exemplo 1: ativar o modo estrito como a versão 1,0

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
The variable $a cannot be retrieved because it has not been set yet.

At line:1 char:3
+ $a <<<<  -gt 5
+ CategoryInfo          : InvalidOperation: (a:Token) [], RuntimeException
+ FullyQualifiedErrorId : VariableIsUndefined
```

Com o modo estrito definido como a versão 1,0, as tentativas de fazer referência a variáveis que não são inicializadas falham.

### Exemplo 2: ativar o modo estrito como a versão 2,0

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
The function or command was called like a method. Parameters should be separated by spaces,
as described in 'Get-Help about_Parameter.'
At line:1 char:4
+ add <<<< (3,4)
+ CategoryInfo          : InvalidOperation: (:) [], RuntimeException
+ FullyQualifiedErrorId : StrictModeFunctionCallWithParens
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$string.Month -eq $null
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$string.Month -eq $null
```

```Output
Property 'Month' cannot be found on this object; make sure it exists.
At line:1 char:9
+ $string. <<<< month
+ CategoryInfo          : InvalidOperation: (.:OperatorToken) [], RuntimeException
+ FullyQualifiedErrorId : PropertyNotFoundStrict
```

Esse comando ativa o modo estrito e o define para a versão 2,0. Como resultado, o PowerShell retornará um erro se você usar a sintaxe do método, que usa parênteses e vírgulas, para uma chamada de função ou para referenciar variáveis não inicializadas ou Propriedades inexistentes.

A saída de exemplo mostra o efeito do modo estrito da versão 2,0.

Sem o modo estrito versão 2.0, o valor "(3,4)" é interpretado como um único objeto de matriz ao qual nada é adicionado. Usando o modo estrito da versão 2,0, ele é corretamente interpretado como sintaxe com falha para enviar dois valores.

Sem a versão 2,0, a referência à propriedade **month** não existente de uma cadeia de caracteres retorna apenas `$Null` . Usando a versão 2,0, ela é interpretada corretamente como um erro de referência.

### Exemplo 3: ativar o modo estrito como a versão 3,0

Com o modo estrito definido como **desativado** , índices inválidos ou fora dos limites resultam em valores nulos de retorno de resultados.

```powershell
# Strict mode is off by default.
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
Index was outside the bounds of the array.
At line:1 char:1
+ $a[2] -eq $null
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
    + FullyQualifiedErrorId : System.IndexOutOfRangeException

Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
At line:1 char:1
+ $a['abc'] -eq $null
+ ~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvalidCastFromStringToInteger
```

Com o modo estrito definido para a versão 3 ou superior, índices inválidos ou fora dos limites resultam em erros.

## PARAMETERS

### -Desativado

Indica que esse cmdlet desativa o modo estrito para o escopo atual e todos os escopos filho.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Especifica as condições que causam um erro no modo estrito. Esse parâmetro aceita qualquer número de versão válido do PowerShell. Qualquer número maior que 3 é tratado como o **mais recente** .

Os valores efetivos para esse parâmetro são:

- 1.0
  - Proíbe referências a variáveis não inicializadas, exceto para variáveis não inicializadas em cadeias de caracteres.
- 2.0
  - Proíbe referências a variáveis não inicializadas. Isso inclui variáveis não inicializadas em cadeias de caracteres.
  - Proíbe referências a propriedades não existentes de um objeto.
  - Proíbe chamadas de função que usam a sintaxe para chamar métodos.
- 3.0
  - Proíbe referências a variáveis não inicializadas. Isso inclui variáveis não inicializadas em cadeias de caracteres.
  - Proíbe referências a propriedades não existentes de um objeto.
  - Proíbe chamadas de função que usam a sintaxe para chamar métodos.
  - Proibir fora dos limites ou índices de matriz não resolvidos.
- Última
  - Seleciona a versão mais recente disponível. A versão mais recente é a mais estrita. Use esse valor para garantir que os scripts usem a versão mais estrita disponível, mesmo quando novas versões forem adicionadas ao PowerShell.

> [!CAUTION]
> Usando uma **versão** do **mais recente** em scripts. O significado da **mais recente** pode mudar em novas versões do PowerShell. Portanto, um script escrito para uma versão mais antiga do PowerShell que o usa `Set-StrictMode -Version Latest` está sujeito a regras mais restritivas quando executado em uma versão mais recente do PowerShell.

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

`Set-StrictMode` entra em vigor somente no escopo no qual ele está definido e em seus escopos filho. Para obter mais informações sobre escopos no PowerShell, consulte [about_Scopes](about/about_Scopes.md).

## LINKS RELACIONADOS

[Set-PSDebug](Set-PSDebug.md)

