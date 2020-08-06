---
title: Elemento GroupBy para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781419"
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
