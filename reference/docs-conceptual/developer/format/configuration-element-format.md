---
title: Elemento Configuration (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363495"
---
# <a name="configuration-element-format"></a>Elemento Configuration (formato)

Representa o elemento de nível superior de um arquivo de formatação.

Elemento de configuração

## <a name="syntax"></a>Sintaxe

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Configuration`. Esse elemento deve ser o elemento raiz para cada arquivo de formatação, e esse elemento deve conter pelo menos um elemento filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Controls para configuração (Format)](./controls-element-for-configuration-format.md)|Elemento opcional.<br /><br /> Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Elemento opcional.<br /><br /> Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|
|[Formato do elemento SelectionSets](./selectionsets-element-format.md)|Elemento opcional.<br /><br /> Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.|
|[Elemento ViewDefinitions (Format)](./viewdefinitions-element-format.md)|Elemento opcional.<br /><br /> Define as exibições usadas para exibir objetos.|

### <a name="parent-elements"></a>Elementos pais

Nenhum.

## <a name="remarks"></a>Comentários

Arquivos de formatação definem como os objetos são exibidos. Na maioria dos casos, esse elemento raiz contém um elemento [ViewDefinitions](./viewdefinitions-element-format.md) que define a tabela, a lista e as exibições amplas do arquivo de formatação. Além das definições de exibição, o arquivo de formatação pode definir conjuntos de seleção, configurações e controles comuns que podem ser usados por essas exibições.

## <a name="see-also"></a>Consulte Também

[Elemento Controls para configuração (Format)](./controls-element-for-configuration-format.md)

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)

[Elemento SelectionSets (Format)](./selectionsets-element-format.md)

[Elemento ViewDefinitions (Format)](./viewdefinitions-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
