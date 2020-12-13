---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra GetProcessSample03
description: Amostra GetProcessSample03
ms.openlocfilehash: 7827247238f3dad2018b55e396b73d1fa434eb97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660716"
---
# <a name="getprocesssample03-sample"></a><span data-ttu-id="4fd30-103">Amostra GetProcessSample03</span><span class="sxs-lookup"><span data-stu-id="4fd30-103">GetProcessSample03 Sample</span></span>

<span data-ttu-id="4fd30-104">Este exemplo mostra como implementar um cmdlet que recupera os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="4fd30-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="4fd30-105">Ele fornece um `Name` parâmetro que pode aceitar um objeto do pipeline ou um valor de uma propriedade de um objeto cujo nome de propriedade é igual ao nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fd30-105">It provides a `Name` parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span> <span data-ttu-id="4fd30-106">Este cmdlet é uma versão simplificada do `Get-Process` cmdlet fornecida pelo Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="4fd30-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4fd30-107">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4fd30-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="4fd30-108">Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta GetProcessSample03.</span><span class="sxs-lookup"><span data-stu-id="4fd30-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample03 folder.</span></span> <span data-ttu-id="4fd30-109">O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span><span class="sxs-lookup"><span data-stu-id="4fd30-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span></span>

2. <span data-ttu-id="4fd30-110">Clique duas vezes no ícone do arquivo da solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="4fd30-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="4fd30-111">Isso abre o projeto de exemplo no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4fd30-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="4fd30-112">No menu **Compilar**, selecione **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="4fd30-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="4fd30-113">A biblioteca do exemplo será criada nas pastas \bin ou \bin\Debug padrão.</span><span class="sxs-lookup"><span data-stu-id="4fd30-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="4fd30-114">Como executar a amostra</span><span class="sxs-lookup"><span data-stu-id="4fd30-114">How to run the sample</span></span>

1. <span data-ttu-id="4fd30-115">Crie a seguinte pasta de módulo:</span><span class="sxs-lookup"><span data-stu-id="4fd30-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. <span data-ttu-id="4fd30-116">Copie o assembly de exemplo para a pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="4fd30-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="4fd30-117">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fd30-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="4fd30-118">Execute o seguinte comando para carregar o assembly no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4fd30-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample03`

5. <span data-ttu-id="4fd30-119">Execute o seguinte comando para executar o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4fd30-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="4fd30-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fd30-120">Requirements</span></span>

<span data-ttu-id="4fd30-121">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="4fd30-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4fd30-122">Demonstra</span><span class="sxs-lookup"><span data-stu-id="4fd30-122">Demonstrates</span></span>

<span data-ttu-id="4fd30-123">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="4fd30-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="4fd30-124">Declarando uma classe de cmdlet usando o atributo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fd30-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="4fd30-125">Declarando um parâmetro de cmdlet usando o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="4fd30-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="4fd30-126">Especificando a posição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fd30-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="4fd30-127">Especificando que o parâmetro recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="4fd30-127">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="4fd30-128">A entrada pode ser Obtida de um objeto ou de um valor de uma propriedade de um objeto cujo nome de propriedade é igual ao nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fd30-128">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="4fd30-129">Declarando um atributo de validação para a entrada de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fd30-129">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="4fd30-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4fd30-130">Example</span></span>

<span data-ttu-id="4fd30-131">Este exemplo mostra uma implementação do cmdlet Get-Proc que inclui um `Name` parâmetro que aceita entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="4fd30-131">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter that accepts input from the pipeline.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated processes to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="4fd30-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4fd30-132">See Also</span></span>

[<span data-ttu-id="4fd30-133">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fd30-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
