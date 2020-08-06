---
title: Erros e exceções no sistema de tipo estendido
ms.date: 07/09/2020
ms.openlocfilehash: f60c53e33c031168eda53726e0d296bf91139fda
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786281"
---
# <a name="errors-and-exceptions-in-the-extended-type-system"></a>Erros e exceções no sistema de tipo estendido

Os erros podem ocorrer no ETS durante a inicialização do tipo dados e ao acessar um membro de um objeto **PSObject** ou usando uma das classes utilitárias, como **LanguagePrimitives**.

## <a name="runtime-errors"></a>Erros em runtime

Com uma exceção, durante a conversão, todas as exceções lançadas do ETS durante o tempo de execução são uma exceção **ExtendedTypeSystemException** ou uma exceção derivada da classe **ExtendedTypeSystemException** . Isso permite que os desenvolvedores de scripts interceptem essas exceções usando a `Trap` instrução em seu script.

## <a name="errors-getting-member-values"></a>Erros ao obter valores de membro

Todos os erros que ocorrem ao obter o valor de um membro do ETS (Propriedade, método ou propriedade parametrizada) causam a geração de uma exceção **Getvalueexception** ou **GetValueInvocationException** .
Quando o ETS reconhece que ocorreu um erro, uma exceção **Getvalorexception** é lançada. Quando o getter subjacente de um membro referenciado reconhece que ocorreu um erro, uma exceção **GetValueInvocationException** é gerada e pode não incluir a exceção interna que causou o erro de invocação Get.

## <a name="errors-setting-member-values"></a>Erros ao definir valores de membro

Todos os erros que ocorrem ao definir o valor de uma propriedade ETS provocam a geração de uma exceção **Setvalueexception** ou **SetValueInvocationException** . Quando o ETS reconhece que ocorreu um erro, uma exceção **DefinirValor** é gerada. Quando o setter subjacente de uma propriedade referenciada reconhece que ocorreu um erro, uma exceção **SetValueInvocationException** é gerada, que pode ou não incluir a exceção interna que causou o erro de invocação de conjunto.

## <a name="errors-invoking-a-method"></a>Erros ao invocar um método

Todos os erros que ocorrem ao invocar um método ETS causam a geração de uma exceção **methodexception** ou **MethodInvocationException** . Quando o ETS reconhece que ocorreu um erro, uma exceção **methodexception** é gerada. Quando o método referenciado reconhece que ocorreu um erro, uma exceção **MethodInvocationException** é gerada e pode ou não incluir a exceção interna que causou o erro de invocação.

## <a name="casting-errors"></a>Erros de conversão

Quando uma conversão inválida é tentada, um **PSInvalidCastException** é gerado. Como essa exceção deriva de **System. InvalidCastException**, não é possível interceptar diretamente do script. Lembre-se de que a entidade que tenta a conversão precisaria encapsular **PSInvalidCastException** em um **PSRuntimeException** para que isso pudesse ser interceptável pelos scripts. Se for feita uma tentativa de definir o valor de um **PSPropertySet**, **PSMemberSet**, **PSMethodInfo**ou um membro de **ReadOnlyPSMemberInfoCollection ' 1**, um **NotSupportedException** será gerado.

## <a name="common-runtime-errors"></a>Erros comuns de tempo de execução

Quaisquer outros erros comuns de tempo de execução que ocorrem são do tipo exceção **ExtendedTypeSystemException** sem tipos de exceção específicos adicionais.

## <a name="initialization-errors"></a>Erros de inicialização

Podem ocorrer erros ao inicializar `types.ps1xml` . Normalmente, esses erros são exibidos quando o tempo de execução do PowerShell é iniciado. No entanto, eles também podem ser exibidos quando um módulo é carregado.
