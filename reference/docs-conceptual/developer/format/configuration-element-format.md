---
title: Elemento Configuration (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783833"
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

As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Configuration` elemento. Esse elemento deve ser o elemento raiz para cada arquivo de formatação, e esse elemento deve conter pelo menos um elemento filho.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento Controls para Configuration (formato)](./controls-element-for-configuration-format.md)|Elemento opcional.<br /><br /> Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Elemento opcional.<br /><br /> Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|
|[Formato do elemento SelectionSets](./selectionsets-element-format.md)|Elemento opcional.<br /><br /> Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.|
|[Elemento ViewDefinitions (formato)](./viewdefinitions-element-format.md)|Elemento opcional.<br /><br /> Define as exibições usadas para exibir objetos.|

### <a name="parent-elements"></a>Elementos pai

Nenhum.

## <a name="remarks"></a>Comentários

Arquivos de formatação definem como os objetos são exibidos. Na maioria dos casos, esse elemento raiz contém um elemento [ViewDefinitions](./viewdefinitions-element-format.md) que define a tabela, a lista e as exibições amplas do arquivo de formatação. Além das definições de exibição, o arquivo de formatação pode definir conjuntos de seleção, configurações e controles comuns que podem ser usados por essas exibições.

## <a name="see-also"></a>Consulte Também

[Elemento Controls para Configuration (formato)](./controls-element-for-configuration-format.md)

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)

[Elemento SelectionSets (formato)](./selectionsets-element-format.md)

[Elemento ViewDefinitions (formato)](./viewdefinitions-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
