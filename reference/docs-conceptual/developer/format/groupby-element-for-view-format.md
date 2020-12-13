---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento GroupBy para View (formato)
description: Elemento GroupBy para View (formato)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652095"
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

nenhuma.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento CustomControl para GroupBy (formato)](./customcontrol-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Define o controle personalizado que exibe novos grupos.|
|[Elemento CustomControlName para GroupBy (formato)](./customcontrolname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o nome de um controle usado para exibir o novo grupo.|
|[Elemento Label para GroupBy (formato)](./label-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica um rótulo que é exibido quando um novo grupo é encontrado.|
|[Elemento PropertyName para GroupBy (formato)](./propertyname-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.|
|[Elemento ScriptBlock para GroupBy (formato)](./scriptblock-element-for-groupby-format.md)|Elemento opcional.<br /><br /> Especifica o script que inicia um novo grupo sempre que seu valor é alterado.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento View (formato)](./view-element-format.md)|Define uma exibição que exibe um ou mais objetos .NET.|

## <a name="remarks"></a>Comentários

Ao definir como um novo grupo de objetos é exibido, você deve especificar a propriedade ou o script que iniciará o novo grupo; no entanto, você não pode especificar ambos.

## <a name="see-also"></a>Consulte Também

[Elemento CustomControlName para GroupBy (formato)](./customcontrolname-element-for-groupby-format.md)

[Elemento Label para GroupBy (formato)](./label-element-for-groupby-format.md)

[Elemento PropertyName para GroupBy (formato)](./propertyname-element-for-groupby-format.md)

[Elemento ScriptBlock para GroupBy (formato)](./scriptblock-element-for-groupby-format.md)

[Elemento View (formato)](./view-element-format.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
