---
title: Elemento GroupBy para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065524"
---
# <a name="groupby-element-for-view-format"></a>Elemento GroupBy para View (formato)

Define como um novo grupo de objetos é exibido. Esse elemento é usado durante a definição de uma tabela, a lista, o modo de exibição do controle ampla ou personalizado.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato)

## <a name="syntax"></a>Sintaxe

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para GroupBy (formato)](./customcontrol-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Define o controle personalizado que exibem os novos grupos.|
|[Elemento CustomControlName para GroupBy (formato)](./customcontrolname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle que é usado para exibir o novo grupo.|
|[Elemento de rótulo para GroupBy (formato)](./label-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um rótulo que é exibido quando um novo grupo é encontrado.|
|[Elemento PropertyName para GroupBy (formato)](./propertyname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET o inicia um novo grupo sempre que seu valor é alterado.|
|[Elemento ScriptBlock para GroupBy (formato)](./scriptblock-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script que inicia um novo grupo sempre que seu valor é alterado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de exibição (formato)](./view-element-format.md)|Define uma exibição que exibe um ou mais objetos do .NET.|

## <a name="remarks"></a>Comentários

Ao definir como um novo grupo de objetos é exibido, você deve especificar a propriedade ou o script que iniciará o novo grupo. No entanto, é possível especificar ambos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControlName para GroupBy (formato)](./customcontrolname-element-for-groupby-format.md)

[Elemento de rótulo para GroupBy (formato)](./label-element-for-groupby-format.md)

[Elemento PropertyName para GroupBy (formato)](./propertyname-element-for-groupby-format.md)

[Elemento ScriptBlock para GroupBy (formato)](./scriptblock-element-for-groupby-format.md)

[Elemento de exibição (formato)](./view-element-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
