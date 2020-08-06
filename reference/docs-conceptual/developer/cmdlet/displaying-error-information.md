---
title: Exibindo informações de erro | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774568"
---
# <a name="displaying-error-information"></a>Exibir informações de erro

Este tópico discute as maneiras pelas quais os usuários podem exibir informações de erro.

Quando o cmdlet encontrar um erro, a apresentação das informações de erro, por padrão, será semelhante à saída de erro a seguir.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

No entanto, os usuários podem exibir erros por categoria definindo a `$ErrorView` variável como `"CategoryView"` . A exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro. Esse modo de exibição pode ser útil se você tiver uma longa lista de erros a serem verificados. No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Para obter mais informações sobre categorias de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).

## <a name="see-also"></a>Consulte Também

[Registros de erros do Windows PowerShell](./windows-powershell-error-records.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
