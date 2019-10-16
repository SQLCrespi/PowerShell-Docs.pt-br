---
title: Exemplo de GetProcessSample04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2aa4c4-3457-4601-806a-801afe3dcc80
caps.latest.revision: 6
ms.openlocfilehash: 095bebf868efd00f8eeaec979a5606f140714cb1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365705"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="4e8a3-102">Amostra GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="4e8a3-102">GetProcessSample04 Sample</span></span>

<span data-ttu-id="4e8a3-103">Este exemplo mostra como implementar um cmdlet que recupera os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="4e8a3-104">Ele gera um erro de não encerramento se ocorrer um erro durante a recuperação de um processo.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-104">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="4e8a3-105">Este cmdlet é uma versão simplificada do cmdlet `Get-Process` fornecido pelo Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4e8a3-106">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="4e8a3-107">Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="4e8a3-108">O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="4e8a3-109">Clique duas vezes no ícone do arquivo da solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="4e8a3-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="4e8a3-110">Isso abre o projeto de exemplo no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="4e8a3-111">No menu **Compilar** , selecione **Compilar solução**.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="4e8a3-112">A biblioteca do exemplo será criada nas pastas \bin ou \bin\Debug padrão.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="4e8a3-113">Como executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="4e8a3-113">How to run the sample</span></span>

1. <span data-ttu-id="4e8a3-114">Crie a seguinte pasta de módulo:</span><span class="sxs-lookup"><span data-stu-id="4e8a3-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="4e8a3-115">Copie o assembly de exemplo para a pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="4e8a3-116">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="4e8a3-117">Execute o seguinte comando para carregar o assembly no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e8a3-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="4e8a3-118">Execute o seguinte comando para executar o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4e8a3-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="4e8a3-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e8a3-119">Requirements</span></span>

<span data-ttu-id="4e8a3-120">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4e8a3-121">Demonstrar</span><span class="sxs-lookup"><span data-stu-id="4e8a3-121">Demonstrates</span></span>

<span data-ttu-id="4e8a3-122">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="4e8a3-123">Declarando uma classe de cmdlet usando o atributo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="4e8a3-124">Declarando um parâmetro de cmdlet usando o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="4e8a3-125">Especificando a posição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="4e8a3-126">Especificando que o parâmetro recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="4e8a3-127">A entrada pode ser Obtida de um objeto ou de um valor de uma propriedade de um objeto cujo nome de propriedade é igual ao nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="4e8a3-128">Declarando um atributo de validação para a entrada de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-128">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="4e8a3-129">Interceptar um erro de não encerramento e gravar uma mensagem de erro no fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-129">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="4e8a3-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4e8a3-130">Example</span></span>

<span data-ttu-id="4e8a3-131">Este exemplo mostra como criar um cmdlet que trata erros de não encerramento e grava mensagens de erro no fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="4e8a3-131">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
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
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="4e8a3-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e8a3-132">See Also</span></span>

<span data-ttu-id="4e8a3-133">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4e8a3-133">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
