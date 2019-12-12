---
title: Exemplo de GetProcessSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b48bf80-cbf0-4cb1-8d5b-3b8d06196598
caps.latest.revision: 10
ms.openlocfilehash: 00190c7350cb0f1cfc5c389b56e48e9397480446
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369725"
---
# <a name="getprocesssample01-sample"></a><span data-ttu-id="dba6b-102">Amostra GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="dba6b-102">GetProcessSample01 Sample</span></span>

<span data-ttu-id="dba6b-103">Este exemplo mostra como implementar um cmdlet que recupera os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="dba6b-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="dba6b-104">Esse cmdlet é uma versão simplificada do cmdlet `Get-Process` fornecido pelo Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="dba6b-104">This cmdlet is a simplified version of the `Get-Process` cmdlet that is provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="dba6b-105">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dba6b-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="dba6b-106">Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta GetProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="dba6b-106">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample01 folder.</span></span> <span data-ttu-id="dba6b-107">O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="dba6b-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span></span>

2. <span data-ttu-id="dba6b-108">Clique duas vezes no ícone do arquivo da solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="dba6b-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="dba6b-109">Isso abre o projeto de exemplo no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dba6b-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="dba6b-110">No menu **Compilar**, selecione **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="dba6b-110">In the **Build** menu, select **Build Solution**.</span></span>

  <span data-ttu-id="dba6b-111">A biblioteca do exemplo será criada nas pastas \bin ou \bin\Debug padrão.</span><span class="sxs-lookup"><span data-stu-id="dba6b-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="dba6b-112">Como executar a amostra</span><span class="sxs-lookup"><span data-stu-id="dba6b-112">How to run the sample</span></span>

1. <span data-ttu-id="dba6b-113">Abra uma janela de Prompt de Comando.</span><span class="sxs-lookup"><span data-stu-id="dba6b-113">Open a Command Prompt window.</span></span>

2. <span data-ttu-id="dba6b-114">Navegue até o diretório que contém o arquivo. dll de exemplo.</span><span class="sxs-lookup"><span data-stu-id="dba6b-114">Navigate to the directory containing the sample .dll file.</span></span>

3. <span data-ttu-id="dba6b-115">Execute InstallUtil "GetProcessSample01. dll".</span><span class="sxs-lookup"><span data-stu-id="dba6b-115">Run installutil "GetProcessSample01.dll".</span></span>

4. <span data-ttu-id="dba6b-116">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dba6b-116">Start Windows PowerShell.</span></span>

5. <span data-ttu-id="dba6b-117">Execute o comando a seguir para adicionar o snap-in ao shell.</span><span class="sxs-lookup"><span data-stu-id="dba6b-117">Run the following command to add the snap-in to the shell.</span></span>

   `Add-PSSnapin GetProcPSSnapIn01`

6. <span data-ttu-id="dba6b-118">Digite o comando a seguir para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dba6b-118">Enter the following command to run the cmdlet.</span></span> `get-proc`

   `get-proc`

   <span data-ttu-id="dba6b-119">Este é um exemplo de saída resultante das seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="dba6b-119">This is a sample output that results from following these steps.</span></span>

   ```output
   Id              Name            State      HasMoreData     Location             Command
   --              ----            -----      -----------     --------             -------
   1               26932870-d3b... NotStarted False                                 Write-Host "A f...

   ```

   ```powershell
   Set-Content $env:temp\test.txt "This is a test file"
   ```

   ```output
   A file was created in the TEMP directory
   ```

## <a name="requirements"></a><span data-ttu-id="dba6b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dba6b-120">Requirements</span></span>

<span data-ttu-id="dba6b-121">Este exemplo requer o Windows PowerShell 1,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="dba6b-121">This sample requires Windows PowerShell 1.0 or later.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="dba6b-122">Demonstra</span><span class="sxs-lookup"><span data-stu-id="dba6b-122">Demonstrates</span></span>

<span data-ttu-id="dba6b-123">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="dba6b-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="dba6b-124">Criando um cmdlet de exemplo básico.</span><span class="sxs-lookup"><span data-stu-id="dba6b-124">Creating a basic sample cmdlet.</span></span>

- <span data-ttu-id="dba6b-125">Definindo uma classe de cmdlet usando o atributo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dba6b-125">Defining a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="dba6b-126">Criação de um snap-in que funciona com o Windows PowerShell 1,0 e o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="dba6b-126">Creating a snap-in that works with both Windows PowerShell 1.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="dba6b-127">Os exemplos subsequentes usam módulos em vez de snap-ins para que eles exijam o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="dba6b-127">Subsequent samples use modules instead of snap-ins so they require Windows PowerShell 2.0.</span></span>

## <a name="example"></a><span data-ttu-id="dba6b-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dba6b-128">Example</span></span>

<span data-ttu-id="dba6b-129">Este exemplo mostra como criar um cmdlet simples e seu snap-in.</span><span class="sxs-lookup"><span data-stu-id="dba6b-129">This sample shows how to create a simple cmdlet and its snap-in.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{

   #region GetProcCommand

   /// <summary>
   /// This class implements the Get-Proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes of the local computer.
      /// Then, the WriteObject method writes the associated processes
      /// to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
         // Retrieve the current processes.
         Process[] processes = Process.GetProcesses();

         // Write the processes to the pipeline to make them available
         // to the next cmdlet. The second argument (true) tells Windows
         // PowerShell to enumerate the array and to send one process
         // object at a time to the pipeline.
         WriteObject(processes, true);
      }

      #endregion Overrides

   } //GetProcCommand

   #endregion GetProcCommand

   #region PowerShell snap-in

   /// <summary>
   /// Create this sample as an PowerShell snap-in
   /// </summary>
   [RunInstaller(true)]
   public class GetProcPSSnapIn01 : PSSnapIn
   {
       /// <summary>
       /// Create an instance of the GetProcPSSnapIn01
       /// </summary>
       public GetProcPSSnapIn01()
           : base()
       {
       }

       /// <summary>
       /// Get a name for this PowerShell snap-in. This name will be used in registering
       /// this PowerShell snap-in.
       /// </summary>
       public override string Name
       {
           get
           {
               return "GetProcPSSnapIn01";
           }
       }

       /// <summary>
       /// Vendor information for this PowerShell snap-in.
       /// </summary>
       public override string Vendor
       {
           get
           {
               return "Microsoft";
           }
       }

       /// <summary>
       /// Gets resource information for vendor. This is a string of format:
       /// resourceBaseName,resourceName.
       /// </summary>
       public override string VendorResource
       {
           get
           {
               return "GetProcPSSnapIn01,Microsoft";
           }
       }

       /// <summary>
       /// Description of this PowerShell snap-in.
       /// </summary>
       public override string Description
       {
           get
           {
               return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
           }
       }
   }

   #endregion PowerShell snap-in
}
```

## <a name="see-also"></a><span data-ttu-id="dba6b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dba6b-130">See Also</span></span>

<span data-ttu-id="dba6b-131">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dba6b-131">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>