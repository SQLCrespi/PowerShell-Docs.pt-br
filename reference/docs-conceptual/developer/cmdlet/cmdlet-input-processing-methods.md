---
ms.date: 09/13/2016
ms.topic: reference
title: Métodos de processamento de entrada de cmdlet
description: Métodos de processamento de entrada de cmdlet
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653389"
---
# <a name="cmdlet-input-processing-methods"></a>Métodos de processamento de entrada de cmdlet

Os cmdlets devem substituir um ou mais dos métodos de processamento de entrada descritos neste tópico para executar seu trabalho.
Esses métodos permitem que o cmdlet execute operações de pré-processamento, processamento de entrada e pós-processamento.
Esses métodos também permitem que você interrompa o processamento de cmdlets.
Para obter um exemplo mais detalhado de como usar esses métodos, consulte o [tutorial do SelectStr](selectstr-tutorial.md).

## <a name="pre-processing-operations"></a>Operações de pré-processamento

Os cmdlets devem substituir o método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) para adicionar quaisquer operações de pré-processamento que sejam válidas para todos os registros que serão processados posteriormente pelo cmdlet.
Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método uma vez para cada instância do cmdlet no pipeline.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento de cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método BeginProcessing.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>Operações de processamento de entrada

Os cmdlets podem substituir o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para processar a entrada que é enviada para o cmdlet.
Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método para cada registro de entrada que é processado pelo cmdlet.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento de cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método ProcessRecord.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>Operações de pós-processamento

Os cmdlets devem substituir o método [System. Management. Automation. cmdlet. Endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) para adicionar quaisquer operações de pós-processamento que sejam válidas para todos os registros que foram processados pelo cmdlet.
Por exemplo, o cmdlet pode precisar limpar as variáveis de objeto após o processamento terminar.

Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método uma vez para cada instância do cmdlet no pipeline.
No entanto, é importante lembrar que o tempo de execução do PowerShell não chamará o método endprocessor se o cmdlet for cancelado no meio de seu processamento de entrada ou se ocorrer um erro de encerramento em qualquer parte do cmdlet.
Por esse motivo, um cmdlet que requer a limpeza de objeto deve implementar o padrão [System. IDisposable](/dotnet/api/System.IDisposable) completo, incluindo um finalizador, para que o tempo de execução possa chamar os métodos noprocessing e [System. IDisposable. Dispose](/dotnet/api/System.IDisposable.Dispose) no final do processamento.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento de cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método endprocessor.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Sistema. Management. Automation. cmdlet. endprocessation](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Tutorial de SelectStr](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[SDK do Shell do Windows PowerShell](../windows-powershell-reference.md)
