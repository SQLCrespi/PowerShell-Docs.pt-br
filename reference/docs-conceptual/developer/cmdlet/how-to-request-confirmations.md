---
ms.date: 09/13/2016
ms.topic: reference
title: Como solicitar confirmações
description: Como solicitar confirmações
ms.openlocfilehash: 3e29803407bd9fbf13e6db0d0a02239c34e9c4fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666987"
---
# <a name="how-to-request-confirmations"></a>Como solicitar confirmações

Este exemplo mostra como chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) para solicitar confirmações do usuário antes que uma ação seja executada.

> [!IMPORTANT]
> Para obter mais informações sobre como o Windows PowerShell lida com essas solicitações, consulte [solicitando confirmação](./requesting-confirmation-from-cmdlets.md).

## <a name="to-request-confirmation"></a>Para solicitar confirmação

1. Verifique se o `SupportsShouldProcess` parâmetro do atributo cmdlet está definido como `true` . (Para funções, esse é um parâmetro do atributo CmdletBinding.)

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. Adicione um `Force` parâmetro ao cmdlet para que o usuário possa substituir uma solicitação de confirmação.

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. Adicione uma `if` instrução que usa o valor de retorno do método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) para determinar se o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) é chamado.

4. Adicione uma segunda `if` instrução que usa o valor de retorno do método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) e o valor do `Force` parâmetro para determinar se a operação deve ser executada.

## <a name="example"></a>Exemplo

No exemplo de código a seguir, os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) são chamados de dentro da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . No entanto, você também pode chamar esses métodos de outros métodos de processamento de entrada.

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
