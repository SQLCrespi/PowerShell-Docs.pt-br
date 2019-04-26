---
title: Métodos de processamento de entrada do cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual methods (PowerShell SDK]
ms.assetid: b0bb8172-c9fa-454b-9f1b-57c3fe60671b
caps.latest.revision: 12
ms.openlocfilehash: a28c8d3df19bc72bf338d6abc4e02768c5097209
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068480"
---
# <a name="cmdlet-input-processing-methods"></a>Métodos de processamento de entrada de cmdlet

Cmdlets deve substituir um ou mais dos métodos descritos neste tópico para realizar seu trabalho de processamento de entrada.
Esses métodos permitem que o cmdlet executar operações de pré-processamento, processamento de entrada e pós-processamento.
Esses métodos também permitem que você parar o processamento de cmdlet.
Para obter um exemplo mais detalhado de como usar esses métodos, consulte [SelectStr Tutorial](selectstr-tutorial.md).

## <a name="pre-processing-operations"></a>Pré-processando operações

Cmdlets deve substituir a [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) método para adicionar quaisquer operações de pré-processamento são válidas para todos os registros que serão processados posteriormente pelo cmdlet.
Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método uma vez para cada instância do cmdlet no pipeline.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento do Cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método BeginProcessing.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>Operações de processamento de entrada

Cmdlets pode substituir a [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método para processar a entrada que é enviada para o cmdlet.
Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método para cada registro de entrada é processado pelo cmdlet.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento do Cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método ProcessRecord.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>Operações de pós-processamento

Cmdlets deve substituir a [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) método para adicionar qualquer pós-processamento operações que são válidas para todos os registros que foram processados pelo cmdlet.
Por exemplo, o cmdlet pode ter que limpar as variáveis de objeto depois que ele é concluído de processamento.

Quando o PowerShell processa um pipeline de comando, o PowerShell chama esse método uma vez para cada instância do cmdlet no pipeline.
No entanto, é importante lembrar-se de que o tempo de execução do PowerShell não chamará o método EndProcessing se o cmdlet é cancelado no Centro por meio de seu processamento de entrada ou se ocorrer um erro de terminação em qualquer parte do cmdlet.
Por esse motivo, um cmdlet que requer a limpeza do objeto deve implementar completo [System. IDisposable](/dotnet/api/System.IDisposable) padrão, incluindo um finalizador, para que o tempo de execução pode chamar os dois o EndProcessing e [ IDisposable](/dotnet/api/System.IDisposable.Dispose) métodos no final do processamento.
Para obter mais informações sobre como o PowerShell invoca o pipeline de comando, consulte [ciclo de vida de processamento do Cmdlet](/previous-versions/ms714429(v=vs.85)).

O código a seguir mostra uma implementação do método EndProcessing.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>Consulte Também

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Tutorial de SelectStr](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Shell do Windows PowerShell do SDK](../windows-powershell-reference.md)
