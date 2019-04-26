---
title: Como substituir os métodos de processamento de entrada | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: cfee55576518cf9ce38501192872ce94054f5213
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067936"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="8e323-102">Como substituir os métodos de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="8e323-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="8e323-103">Estes exemplos mostram como substituir os métodos dentro de um cmdlet de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="8e323-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="8e323-104">Esses métodos são usados para executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="8e323-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="8e323-105">O [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) método é usado para executar operações de inicialização única que são válidas para todos os objetos processados pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e323-105">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="8e323-106">O tempo de execução do Windows PowerShell chama esse método apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="8e323-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="8e323-107">O [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método é usado para processar os objetos passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e323-107">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="8e323-108">O tempo de execução do Windows PowerShell chama esse método para cada objeto passado para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e323-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="8e323-109">O [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) método é usado para executar operações de processamento de postagem única.</span><span class="sxs-lookup"><span data-stu-id="8e323-109">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="8e323-110">O tempo de execução do Windows PowerShell chama esse método apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="8e323-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="8e323-111">Para substituir o método BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="8e323-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="8e323-112">Declarar uma substituição protegida do [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-112">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="8e323-113">A classe a seguir imprime uma mensagem de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8e323-113">The following class prints a sample message.</span></span> <span data-ttu-id="8e323-114">Para usar essa classe, altere o verbo e substantivo no atributo de Cmdlet, altere o nome da classe para refletir o novo verbo e substantivo e, em seguida, adicionar a funcionalidade necessária para a substituição do [System.Management.Automation.Cmdlet.BeginProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="8e323-115">Substituir o método ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="8e323-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="8e323-116">Declarar uma substituição protegida do [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-116">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="8e323-117">A classe a seguir imprime uma mensagem de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8e323-117">The following class prints a sample message.</span></span> <span data-ttu-id="8e323-118">Para usar essa classe, altere o verbo e substantivo no atributo de Cmdlet, altere o nome da classe para refletir o novo verbo e substantivo e, em seguida, adicionar a funcionalidade necessária para a substituição do [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="8e323-119">Para substituir o método EndProcessing</span><span class="sxs-lookup"><span data-stu-id="8e323-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="8e323-120">Declarar uma substituição protegida do [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-120">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="8e323-121">A classe a seguir imprime uma amostra.</span><span class="sxs-lookup"><span data-stu-id="8e323-121">The following class prints a sample.</span></span> <span data-ttu-id="8e323-122">Para usar essa classe, altere o verbo e substantivo no atributo de Cmdlet, altere o nome da classe para refletir o novo verbo e substantivo e, em seguida, adicionar a funcionalidade necessária para a substituição do [System.Management.Automation.Cmdlet.EndProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) método.</span><span class="sxs-lookup"><span data-stu-id="8e323-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a><span data-ttu-id="8e323-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e323-123">See Also</span></span>

[<span data-ttu-id="8e323-124">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="8e323-124">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="8e323-125">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="8e323-125">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="8e323-126">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="8e323-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

<span data-ttu-id="8e323-127">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8e323-127">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
