---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra GetProcessSample02
description: Amostra GetProcessSample02
ms.openlocfilehash: a0f43806b707359cb454817341f2c4972033c46a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660525"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="c9069-103">Amostra GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="c9069-103">GetProcessSample02 Sample</span></span>

<span data-ttu-id="c9069-104">Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="c9069-104">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="c9069-105">Ele fornece um `Name` parâmetro que pode ser usado para especificar os processos a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="c9069-105">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="c9069-106">Este cmdlet é uma versão simplificada do `Get-Process` cmdlet fornecida pelo Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9069-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="c9069-107">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9069-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="c9069-108">Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta GetProcessSample02.</span><span class="sxs-lookup"><span data-stu-id="c9069-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="c9069-109">O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span><span class="sxs-lookup"><span data-stu-id="c9069-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="c9069-110">Clique duas vezes no ícone do arquivo da solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="c9069-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="c9069-111">Isso abre o projeto de exemplo no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9069-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="c9069-112">No menu **Compilar**, selecione **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="c9069-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="c9069-113">A biblioteca do exemplo será criada nas pastas \bin ou \bin\Debug padrão.</span><span class="sxs-lookup"><span data-stu-id="c9069-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="c9069-114">Como executar a amostra</span><span class="sxs-lookup"><span data-stu-id="c9069-114">How to run the sample</span></span>

1. <span data-ttu-id="c9069-115">Crie a seguinte pasta de módulo:</span><span class="sxs-lookup"><span data-stu-id="c9069-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="c9069-116">Copie o assembly de exemplo para a pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="c9069-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="c9069-117">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9069-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="c9069-118">Execute o seguinte comando para carregar o assembly no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9069-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="c9069-119">Execute o seguinte comando para executar o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c9069-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="c9069-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9069-120">Requirements</span></span>

<span data-ttu-id="c9069-121">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9069-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c9069-122">Demonstra</span><span class="sxs-lookup"><span data-stu-id="c9069-122">Demonstrates</span></span>

<span data-ttu-id="c9069-123">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="c9069-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="c9069-124">Declarando uma classe de cmdlet usando o atributo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9069-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="c9069-125">Declarando um parâmetro de cmdlet usando o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="c9069-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="c9069-126">Especificando a posição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c9069-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="c9069-127">Declarando um atributo de validação para a entrada de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c9069-127">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="c9069-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c9069-128">Example</span></span>

<span data-ttu-id="c9069-129">Este exemplo mostra uma implementação do cmdlet Get-Proc que inclui um `Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c9069-129">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;     // Windows PowerShell namespace

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
    /// Gets or sets the list of process names on which
    /// the Get-Proc cmdlet will work.
    /// </summary>
    [Parameter(Position = 0)]
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
    /// associated process objects to the pipeline.
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
        // If process names are passed to cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames...).
    } // End ProcessRecord.
    #endregion Cmdlet Overrides
  } // End GetProcCommand class.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="c9069-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9069-130">See Also</span></span>

[<span data-ttu-id="c9069-131">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9069-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
