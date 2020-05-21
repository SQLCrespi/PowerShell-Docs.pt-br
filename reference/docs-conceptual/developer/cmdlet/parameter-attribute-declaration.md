---
title: Declaração de atributo de parâmetro | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, Parameter
- Parameter attribute, described
- Parameter attribute
ms.assetid: 08433d0b-169b-42c8-9335-2881d9034698
caps.latest.revision: 13
ms.openlocfilehash: 7482690c44cdaabf23b886107ac5d112c0fa5c9d
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692395"
---
# <a name="parameter-attribute-declaration"></a>Declaração de atributo de parâmetro

O atributo Parameter identifica uma propriedade pública da classe cmdlet como um parâmetro de cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a>Parâmetros

`Mandatory`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. `True`indica que o parâmetro de cmdlet é necessário. Se um parâmetro necessário não for fornecido quando o cmdlet for invocado, o Windows PowerShell solicitará ao usuário um valor de parâmetro. O padrão é `false`.

`ParameterSetName`([System. String](/dotnet/api/System.String)) parâmetro nomeado opcional. Especifica o conjunto de parâmetros ao qual este parâmetro de cmdlet pertence. Se nenhum conjunto de parâmetros for especificado, o parâmetro pertencerá a todos os conjuntos de parâmetros.

`Position`([System. Int32](/dotnet/api/System.Int32)) parâmetro nomeado opcional. Especifica a posição do parâmetro em um comando do Windows PowerShell.

`ValueFromPipeline`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. `True`indica que o parâmetro de cmdlet obtém seu valor de um objeto de pipeline. Especifique essa palavra-chave se o cmdlet acessar o objeto completo, não apenas uma propriedade do objeto. O padrão é `false`.

`ValueFromPipelineByPropertyName`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. `True`indica que o parâmetro de cmdlet obtém seu valor de uma propriedade de um objeto de pipeline que tem o mesmo nome ou o mesmo alias que esse parâmetro. Por exemplo, se o cmdlet tiver um `Name` parâmetro e o objeto de pipeline também tiver uma `Name` propriedade, o valor da `Name` propriedade será atribuído ao `Name` parâmetro do cmdlet. O padrão é `false`.

`ValueFromRemainingArguments`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. `True`indica que o parâmetro de cmdlet aceita todos os argumentos restantes que são passados para o cmdlet. O padrão é `false`.

`HelpMessage`Parâmetro nomeado opcional. Especifica uma breve descrição do parâmetro. O Windows PowerShell exibe essa mensagem quando um cmdlet é executado e um parâmetro obrigatório não é especificado.

`HelpMessageBaseName`Parâmetro nomeado opcional. Especifica o local onde os identificadores de recursos residem. Por exemplo, esse parâmetro pode especificar um assembly de recurso que contém mensagens de ajuda que você deseja localizar.

`HelpMessageResourceId`Parâmetro nomeado opcional. Especifica o identificador de recurso para uma mensagem de ajuda.

## <a name="remarks"></a>Comentários

- Para obter mais informações sobre como declarar esse atributo, consulte [como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md).

- Um cmdlet pode ter qualquer número de parâmetros. No entanto, para uma melhor experiência do usuário, limite o número de parâmetros.

- Os parâmetros devem ser declarados em Propriedades ou campos públicos não estáticos. Os parâmetros devem ser declarados em Propriedades. A propriedade deve ter um acessador set público e, se a `ValueFromPipeline` `ValueFromPipelineByPropertyName` palavra-chave ou for especificada, a propriedade deverá ter um acessador get público.

- Quando você especifica parâmetros posicionais, limite o número de parâmetros posicionais em um parâmetro definido para menos de cinco. E os parâmetros posicionais não precisam ser contíguos. As posições 5, 100 e 250 funcionam da mesma forma que as posições 0, 1 e 2.

- Quando a `Position` palavra-chave não for especificada, o parâmetro de cmdlet deverá ser referenciado por seu nome.

- Ao usar conjuntos de parâmetros, observe o seguinte:

  - Cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo. Um bom design de cmdlet indica que esse parâmetro exclusivo também deve ser obrigatório, se possível. Se o cmdlet for projetado para ser executado sem parâmetros, o parâmetro exclusivo não poderá ser obrigatório.

  - Nenhum conjunto de parâmetros deve conter mais de um parâmetro posicional com a mesma posição.

  - Somente um parâmetro em um conjunto de parâmetros deve declarar `ValueFromPipeline = true` . Vários parâmetros podem ser definidos `ValueFromPipelineByPropertyName = true` .

  - Vários parâmetros podem ser definidos `ValueFromPipelineByPropertyName = true` .

- Para obter mais informações sobre as diretrizes para nomes de parâmetro, consulte [nomes de parâmetro de cmdlet](standard-cmdlet-parameter-names-and-types.md).

- O atributo de parâmetro é definido pela classe [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute)

[Nomes de parâmetro de cmdlet](standard-cmdlet-parameter-names-and-types.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
