---
title: Módulos e snap-ins | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787301"
---
# <a name="modules-and-snap-ins"></a>Módulos e snap-ins

Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.

Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:

- Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido. Não há necessidade de implementar uma classe de snap-in.

- Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.

- Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.

## <a name="see-also"></a>Consulte Também

[Escrevendo um módulo do Windows PowerShell](writing-a-windows-powershell-module.md)

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/cmdlet-overview.md)
