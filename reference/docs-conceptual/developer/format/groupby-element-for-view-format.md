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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363625"
---
# <a name="groupby-element-for-view-format"></a>Elemento GroupBy para View (formato)

Define como um novo grupo de objetos é exibido. Esse elemento é usado ao definir uma tabela, lista, largura ou exibição de controle personalizado.

Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format)

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

## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filhos

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Define o controle personalizado que exibe novos grupos.|
|[Elemento CustomControlName para GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle usado para exibir o novo grupo.|
|[Elemento Label para GroupBy (Format)](./label-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um rótulo que é exibido quando um novo grupo é encontrado.|
|[Elemento PropertyName para GroupBy (Format)](./propertyname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.|
|[Elemento ScriptBlock para GroupBy (Format)](./scriptblock-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script que inicia um novo grupo sempre que seu valor é alterado.|

### <a name="parent-elements"></a>Elementos pais

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que exibe um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Ao definir como um novo grupo de objetos é exibido, você deve especificar a propriedade ou o script que iniciará o novo grupo; no entanto, você não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControlName para GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

[Elemento Label para GroupBy (Format)](./label-element-for-groupby-format.md)

[Elemento PropertyName para GroupBy (Format)](./propertyname-element-for-groupby-format.md)

[Elemento ScriptBlock para GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[Elemento View (formato)](./view-element-format.md)

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
