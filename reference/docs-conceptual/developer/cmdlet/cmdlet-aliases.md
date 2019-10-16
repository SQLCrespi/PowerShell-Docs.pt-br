---
title: Aliases de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369975"
---
# <a name="cmdlet-aliases"></a>Aliases de cmdlet

Você pode usar aliases de cmdlet para melhorar a experiência do usuário do cmdlet. Você pode adicionar aliases a cmdlets usados com frequência para reduzir a digitação e facilitar a conclusão das tarefas rapidamente. Você pode incluir aliases internos em seus cmdlets ou os usuários podem definir seus próprios aliases personalizados.

Por exemplo, o cmdlet [Get-Command](/powershell/module/microsoft.powershell.core/get-command) tem um alias interno `gcm`. Você também pode usar aliases para adicionar nomes de comando de outros idiomas para que os usuários não precisem aprender novos comandos.

## <a name="alias-guidelines"></a>Diretrizes de alias

Siga estas diretrizes ao criar aliases internos para seus cmdlets:

- Antes de atribuir aliases, inicie o Windows PowerShell e execute o cmdlet [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) para ver os aliases que já foram usados.

- Inclua um prefixo de alias que referencie o verbo do nome do cmdlet e um sufixo de alias que referencie o substantivo do nome do cmdlet. Por exemplo, o alias para o cmdlet `Import-Module` é "ipmo". Para obter uma lista de todos os verbos e seus aliases, consulte [verbos de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

- Para os cmdlets que têm o mesmo verbo, inclua o mesmo prefixo de alias. Por exemplo, os aliases para todos os cmdlets do Windows PowerShell que têm o verbo "Get" em seu nome usam o prefixo "g".

- Para os cmdlets que têm o mesmo substantivo, inclua o mesmo sufixo de alias. Por exemplo, os aliases para todos os cmdlets do Windows PowerShell que têm o substantivo "Session" em seu nome usam o sufixo "SN".

- Para cmdlets equivalentes a comandos em outros idiomas, use o nome do comando.

- Em geral, torne os aliases o mais curto possível. Verifique se o alias tem pelo menos um caractere distinto para o verbo e um caractere distinto para o substantivo. Adicione mais caracteres conforme necessário para tornar o alias exclusivo.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
