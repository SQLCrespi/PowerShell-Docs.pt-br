---
ms.date: 09/13/2016
ms.topic: reference
title: Mensagens de confirmação
description: Mensagens de confirmação
ms.openlocfilehash: 76302b2f8d8ca6dcdfe1b3c36f71aad23a53f7cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355180"
---
# <a name="confirmation-messages"></a>Mensagens de confirmação

Aqui estão as diferentes mensagens de confirmação que podem ser exibidas dependendo das variantes dos métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) que são chamados.

> [!IMPORTANT]
> Para obter um exemplo de código que mostra como solicitar confirmações, consulte [como solicitar confirmações](./how-to-request-confirmations.md).

## <a name="specifying-the-resource"></a>Especificando o recurso

Você pode especificar o recurso que está prestes a ser alterado chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Nesse caso, você fornece o recurso usando o `target` parâmetro do método e a operação é adicionada pelo Windows PowerShell. Na mensagem a seguir, o texto "MyResource" é o recurso acionado e a operação é o nome do comando que faz a chamada.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Se o usuário selecionar **Sim** ou **Sim para todos** na solicitação de confirmação (como mostrado no exemplo a seguir), será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>Especificando a operação e o recurso

Você pode especificar o recurso que está prestes a ser alterado e a operação que o comando está prestes a executar chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Nesse caso, você fornece o recurso usando o `target` parâmetro e a operação usando o `target` parâmetro. Na mensagem a seguir, o texto "MyResource" é o recurso acionado e "myaction" é a operação a ser executada.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Se o usuário selecionar **Sim** ou **Sim para todos** na mensagem anterior, será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
