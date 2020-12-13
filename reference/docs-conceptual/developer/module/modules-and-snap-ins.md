---
ms.date: 09/13/2016
ms.topic: reference
title: Módulos e snap-ins
description: Módulos e snap-ins
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658681"
---
# <a name="modules-and-snap-ins"></a>Módulos e snap-ins

Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.

Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:

- Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido. Não há necessidade de implementar uma classe de snap-in.

- Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.

- Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.

## <a name="see-also"></a>Consulte Também

[Escrever um módulo do Windows PowerShell](writing-a-windows-powershell-module.md)

[Writing a Windows PowerShell Cmdlet](../cmdlet/cmdlet-overview.md) (Escrevendo um Cmdlet do Windows PowerShell)
