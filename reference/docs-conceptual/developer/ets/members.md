---
title: Membros da classe do sistema de tipo estendido
ms.date: 07/09/2020
ms.openlocfilehash: 24a57b7fd0b3db47d0d7138859aa0502ca9016f0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786264"
---
# <a name="extended-type-system-class-members"></a>Membros da classe do sistema de tipo estendido

O ETS refere-se a vários tipos diferentes de membros cujos tipos são definidos pela enumeração **PSMemberTypes** . Esses tipos de membro incluem propriedades, métodos, membros e conjuntos de membros que são definidos por seu próprio tipo CLR. Por exemplo, uma **NoteProperty** é definida por seu próprio tipo **PSNoteProperty** . Esses tipos CLR individuais têm suas próprias propriedades exclusivas e propriedades comuns que são herdadas da [classe PSMemberInfo](/dotnet/api/system.management.automation.psmemberinfo).

## <a name="the-psmemberinfo-class"></a>A classe PSMemberInfo

A classe **PSMemberInfo** serve como uma classe base para todos os tipos de membro do ETS. Essa classe fornece as seguintes propriedades de base para todos os tipos CLR de membro.

- Propriedade **Name** : o nome do membro. Esse nome pode ser definido pelo objeto base ou definido pelo PowerShell quando Membros adaptados ou membros estendidos são expostos.
- Propriedade **Value** : o valor retornado do membro específico. Cada tipo de membro define como ele manipula seu valor de membro.
- Propriedade **TypeNameOfValue** : esse é o nome do tipo CLR do valor que é retornado pela propriedade Value.

## <a name="accessing-members"></a>Acessando membros

As coleções de membros podem ser acessadas por meio das propriedades **Members**, **Methods**e **Properties** do objeto **PSObject** .

## <a name="ets-properties"></a>Propriedades do ETS

As propriedades do ETS são membros que podem ser tratados como uma propriedade. Essencialmente, eles podem aparecer no lado esquerdo de uma expressão. Eles incluem propriedades de alias, propriedades de código, propriedades do PowerShell, propriedades de observação e propriedades de script. Para obter mais informações sobre esses tipos de propriedades, consulte [Propriedades do ETS](properties.md).

## <a name="ets-methods"></a>Métodos do ETS

Os métodos ETS são membros que podem receber argumentos, podem retornar resultados e não podem aparecer no lado esquerdo de uma expressão. Eles incluem métodos de código, métodos do PowerShell e métodos de script.
Para obter mais informações sobre esses tipos de métodos, consulte [métodos do ETS](methods.md).
