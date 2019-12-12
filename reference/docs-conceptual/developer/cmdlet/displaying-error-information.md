---
title: Exibindo informações de erro | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369965"
---
# <a name="displaying-error-information"></a>Exibir informações de erro

Este tópico discute as maneiras pelas quais os usuários podem exibir informações de erro.

Quando o cmdlet encontrar um erro, a apresentação das informações de erro, por padrão, será semelhante à saída de erro a seguir.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

No entanto, os usuários podem exibir erros por categoria definindo a variável `$ErrorView` como `"CategoryView"`. A exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro. Esse modo de exibição pode ser útil se você tiver uma longa lista de erros a serem verificados. No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Para obter mais informações sobre categorias de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).

## <a name="see-also"></a>Consulte Também

[Registros de erro do Windows PowerShell](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
