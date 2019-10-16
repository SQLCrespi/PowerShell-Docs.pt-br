---
title: Declaração de atributo de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlet attribute, described
- attributes, Cmdlet
- Cmdlet attribute
ms.assetid: 1d323332-f773-4c0e-8a69-2aada765afb2
caps.latest.revision: 12
ms.openlocfilehash: 6887467ad5ccafe6edf8f03f531b4750133aa9e9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363535"
---
# <a name="cmdlet-attribute-declaration"></a>Declaração de atributo de cmdlet

O atributo cmdlet identifica uma classe Microsoft .NET Framework como um cmdlet e especifica o verbo e o substantivo usados para invocar o cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a>Parâmetros

`VerbName` ([System. String](/dotnet/api/System.String)) necessário. Especifica o verbo do cmdlet. Esse verbo especifica a ação realizada pelo cmdlet. Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md) e diretrizes de [desenvolvimento necessárias](./required-development-guidelines.md).

`NounName` ([System. String](/dotnet/api/System.String)) necessário. Especifica o substantivo do cmdlet. Esse substantivo especifica o recurso no qual o cmdlet atua. Para obter mais informações sobre substantivos de cmdlet, consulte [declaração de cmdlet](./cmdlet-class-declaration.md) e [diretrizes de desenvolvimento altamente incentivadas](./strongly-encouraged-development-guidelines.md).

parâmetro nomeado opcional `SupportsShouldProcess` ([System. Boolean](/dotnet/api/System.Boolean)). `True` indica que o cmdlet dá suporte a chamadas para o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , que fornece ao cmdlet uma maneira de avisar o usuário antes que uma ação que muda o sistema seja executada. `False`, o valor padrão, indica que o cmdlet não oferece suporte a chamadas para o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Para obter mais informações sobre solicitações de confirmação, consulte [solicitando confirmação](./requesting-confirmation-from-cmdlets.md).

`ConfirmImpact` ([System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) parâmetro nomeado opcional. Especifica quando a ação do cmdlet deve ser confirmada por uma chamada para o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) só será chamado quando o valor ConfirmImpact do cmdlet (por padrão, Medium) for igual ou maior que o valor da variável `$ConfirmPreference`. Esse parâmetro deve ser especificado somente quando o parâmetro `SupportsShouldProcess` for especificado.

parâmetro nomeado opcional `DefaultParameterSetName` ([System. String](/dotnet/api/System.String)). Especifica o conjunto de parâmetros padrão que o tempo de execução do Windows PowerShell tenta usar quando não pode determinar qual conjunto de parâmetros usar. Observe que essa situação pode ser eliminada, fazendo com que o parâmetro exclusivo de cada parâmetro defina um parâmetro obrigatório.

Há um caso em que o Windows PowerShell não pode usar o conjunto de parâmetros padrão, mesmo se um nome de conjunto de parâmetros padrão for especificado. O tempo de execução do Windows PowerShell não pode distinguir entre conjuntos de parâmetros com base apenas no tipo de objeto. Por exemplo, se você tiver um conjunto de parâmetros que usa uma cadeia de caracteres como o caminho do arquivo e outro conjunto que usa um objeto **FileInfo** diretamente, o Windows PowerShell não poderá determinar qual conjunto de parâmetros usar com base nos valores passados para o cmdlet, nem usará o conjunto de parâmetros padrão. Nesse caso, mesmo se você especificar um nome de conjunto de parâmetros padrão, o Windows PowerShell lançará uma mensagem de erro de definição de parâmetro ambíguo.

parâmetro nomeado opcional `SupportsTransactions` ([System. Boolean](/dotnet/api/System.Boolean)). `True` indica que o cmdlet pode ser usado em uma transação. Quando `True` é especificado, o tempo de execução do Windows PowerShell adiciona o parâmetro `UseTransaction` à lista de parâmetros do cmdlet. `False`, o valor padrão, indica que o cmdlet não pode ser usado em uma transação.

## <a name="remarks"></a>Comentários

- Juntos, o verbo e o substantivo são usados para identificar o cmdlet registrado e para invocar o cmdlet em um script.

- Quando o cmdlet é invocado no console do Windows PowerShell, o comando é semelhante ao seguinte comando:

**Verbname-Substantivoname**

- Todos os cmdlets que alteram recursos fora do Windows PowerShell devem incluir a palavra-chave `SupportsShouldProcess` quando o atributo de cmdlet é declarado, o que permite que o cmdlet chame o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) antes da executa sua ação. Se a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) retornar `false`, a ação não deverá ser executada. Para obter mais informações sobre as solicitações de confirmação geradas pela chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , consulte [solicitando confirmação](./requesting-confirmation-from-cmdlets.md).

Os parâmetros de cmdlet `Confirm` e `WhatIf` estão disponíveis somente para cmdlets que dão suporte a chamadas [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .

## <a name="example"></a>Exemplo

A definição de classe a seguir usa o atributo cmdlet para identificar a classe .NET Framework para um cmdlet **Get-proc** que recupera informações sobre os processos em execução no computador local.

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

Para obter mais informações sobre o cmdlet **Get-proc** , consulte [tutorial do getproc](./getproc-tutorial.md).

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
