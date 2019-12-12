---
title: Parâmetros de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.assetid: 3f1cca5f-5b95-4bce-94a6-a22db1aefd47
caps.latest.revision: 23
ms.openlocfilehash: 914a10907bcf980eed8d7e2f819c382fe6b341ad
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365925"
---
# <a name="cmdlet-parameters"></a>Parâmetros de cmdlets

Os parâmetros de cmdlet fornecem o mecanismo que permite que um cmdlet aceite entrada. Os parâmetros podem aceitar a entrada diretamente da linha de comando ou de objetos passados para o cmdlet por meio do pipeline, os argumentos (também conhecidos como *valores*) desses parâmetros podem especificar a entrada que o cmdlet aceita, como o cmdlet deve executar suas ações e os dados que o cmdlet retorna para o pipeline.

## <a name="in-this-section"></a>Nesta seção

[Declarando propriedades como parâmetros](./declaring-properties-as-parameters.md) Fornece informações básicas que você deve entender antes de declarar os parâmetros de um cmdlet.

[Tipos de parâmetros de cmdlet](./types-of-cmdlet-parameters.md) Descreve os diferentes tipos de parâmetros que você pode declarar em cmdlets.

[Diretrizes de funcionalidade e nome de parâmetro de cmdlet](./standard-cmdlet-parameter-names-and-types.md) Discuta os nomes, o tipo de dados recomendado e a funcionalidade dos parâmetros padrão.

[Aliases de parâmetro](./parameter-aliases.md) Discute os aliases que você pode definir para parâmetros.

[Nomes de parâmetro comuns](./common-parameter-names.md) Este tópico descreve os parâmetros que o Windows PowerShell adiciona aos cmdlets do.

[Conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md) Discute como os conjuntos de parâmetros permitem que você escreva um único cmdlet que possa executar ações diferentes para cenários diferentes.

[Parâmetros dinâmicos de cmdlet](./cmdlet-dynamic-parameters.md) Discute os parâmetros que estão disponíveis para o usuário em condições especiais.

[Suporte a caracteres curinga em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md) Descreve como fornecer suporte para caracteres curinga quando você cria um cmdlet que será executado em um grupo de recursos.

[Validando entrada de parâmetro](./validating-parameter-input.md) Descreve como o Windows PowerShell valida os argumentos passados para parâmetros de cmdlet.

[Parâmetros de filtro de entrada](./input-filter-parameters.md) Discute os parâmetros `Filter`, `Include`e `Exclude` que filtram o conjunto de objetos de entrada que o cmdlet afeta.

## <a name="related-sections"></a>Seções pertinentes

[Como validar a entrada de parâmetro](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>Consulte Também

[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md)

[Cmdlets do Windows PowerShell](./cmdlet-overview.md)
