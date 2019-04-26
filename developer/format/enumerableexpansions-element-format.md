---
title: Elemento EnumerableExpansions (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066083"
---
# <a name="enumerableexpansions-element-format"></a>Elemento EnumerableExpansions (formato)

Define como os objetos de coleção do .NET são expandidos quando eles são exibidos em uma exibição.

Configuração (formato) elemento DefaultSettings (formato) EnumerableExpansions elemento (formato)

## <a name="syntax"></a>Sintaxe

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansions` elemento. Não há nenhum limite para o número de elementos filho que você pode usar.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento EnumerableExpansion (formato)](./enumerableexpansion-element-format.md)|Elemento opcional.<br /><br /> Define os objetos de coleção específicos do .NET que são expandidos quando eles são exibidos em uma exibição.|

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos. Nesse caso, um objeto de coleção refere-se a qualquer objeto que dá suporte a **System.Collections.ICollection** interface.

## <a name="see-also"></a>Consulte Também

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
