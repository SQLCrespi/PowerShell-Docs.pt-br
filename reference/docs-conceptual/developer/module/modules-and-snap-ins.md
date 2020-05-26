---
title: Módulos e snap-ins | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: b3d8209ea7e3e8353e73ebce1531991ec9519c74
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811655"
---
# <a name="modules-and-snap-ins"></a>Módulos e snap-ins

Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.

Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:

- Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido. Não há necessidade de implementar uma classe de snap-in.

- Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.

- Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.

## <a name="see-also"></a>Consulte Também

[Escrever um módulo do Windows PowerShell](writing-a-windows-powershell-module.md)

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/cmdlet-overview.md)
