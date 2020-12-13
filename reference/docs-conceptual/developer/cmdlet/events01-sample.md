---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra Events01
description: Amostra Events01
ms.openlocfilehash: ed8b7903537504609602e27693351847d322f904
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390398"
---
# <a name="events01-sample"></a><span data-ttu-id="6ee3f-103">Amostra Events01</span><span class="sxs-lookup"><span data-stu-id="6ee3f-103">Events01 Sample</span></span>

<span data-ttu-id="6ee3f-104">Este exemplo mostra como criar um cmdlet que permite ao usuário se registrar para eventos que são gerados por [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span><span class="sxs-lookup"><span data-stu-id="6ee3f-104">This sample shows how to create a cmdlet that allows the user to register for events that are raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="6ee3f-105">Com esse cmdlet, os usuários podem registrar uma ação a ser executada quando um arquivo é criado em um diretório específico.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-105">With this cmdlet, users can register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="6ee3f-106">Este exemplo deriva da classe base [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) .</span><span class="sxs-lookup"><span data-stu-id="6ee3f-106">This sample derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="6ee3f-107">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-107">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="6ee3f-108">Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta Events01.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-108">With the Windows PowerShell 2.0 SDK installed, navigate to the Events01 folder.</span></span> <span data-ttu-id="6ee3f-109">O local padrão é `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-109">The default location is `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.</span></span>

2. <span data-ttu-id="6ee3f-110">Clique duas vezes no ícone do arquivo da solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="6ee3f-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="6ee3f-111">Isso abre o projeto de exemplo no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-111">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="6ee3f-112">No menu **Compilar**, selecione **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-112">In the **Build** menu, select **Build Solution**.</span></span> <span data-ttu-id="6ee3f-113">A biblioteca do exemplo será criada no padrão `\bin` ou `\bin\debug` nas pastas.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-113">The library for the sample will be built in the default `\bin` or `\bin\debug` folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="6ee3f-114">Como executar a amostra</span><span class="sxs-lookup"><span data-stu-id="6ee3f-114">How to run the sample</span></span>

1. <span data-ttu-id="6ee3f-115">Crie a seguinte pasta de módulo:</span><span class="sxs-lookup"><span data-stu-id="6ee3f-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/events01`

2. <span data-ttu-id="6ee3f-116">Copie o arquivo de biblioteca do exemplo para a pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-116">Copy the library file for the sample to the module folder.</span></span>

3. <span data-ttu-id="6ee3f-117">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="6ee3f-118">Execute o seguinte comando para carregar o cmdlet no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ee3f-118">Run the following command to load the cmdlet into Windows PowerShell:</span></span>

    ```powershell
    import-module events01
    ```

5. <span data-ttu-id="6ee3f-119">Use o cmdlet Register-FileSystemEvent para registrar uma ação que irá gravar uma mensagem quando um arquivo for criado no diretório temporário.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-119">Use the Register-FileSystemEvent cmdlet to register an action that will write a message when a file is created under the TEMP directory.</span></span>

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. <span data-ttu-id="6ee3f-120">Crie um arquivo no diretório TEMP e observe que a ação é executada (a mensagem é exibida).</span><span class="sxs-lookup"><span data-stu-id="6ee3f-120">Create a file under the TEMP directory and note that the action is executed (the message is displayed).</span></span>

<span data-ttu-id="6ee3f-121">Esta é uma saída de exemplo que resulta seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-121">This is a sample output that results by following these steps.</span></span>

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

## <a name="requirements"></a><span data-ttu-id="6ee3f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ee3f-122">Requirements</span></span>

<span data-ttu-id="6ee3f-123">Este exemplo requer o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-123">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="6ee3f-124">Demonstra</span><span class="sxs-lookup"><span data-stu-id="6ee3f-124">Demonstrates</span></span>

<span data-ttu-id="6ee3f-125">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-125">This sample demonstrates the following.</span></span>

### <a name="how-to-write-a-cmdlet-for-event-registration"></a><span data-ttu-id="6ee3f-126">Como escrever um cmdlet para o registro de eventos</span><span class="sxs-lookup"><span data-stu-id="6ee3f-126">How to write a cmdlet for event registration</span></span>

<span data-ttu-id="6ee3f-127">O cmdlet deriva da classe [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) , que fornece suporte para parâmetros comuns aos `Register-*Event` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-127">The cmdlet derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) class, which provides support for parameters common to the `Register-*Event` cmdlets.</span></span> <span data-ttu-id="6ee3f-128">Os cmdlets que são derivados de [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) precisam apenas definir seus parâmetros específicos e substituir `GetSourceObject` os `GetSourceObjectEventName` métodos e abstract.</span><span class="sxs-lookup"><span data-stu-id="6ee3f-128">Cmdlets that are derived from [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) need only to define their particular parameters and override the `GetSourceObject` and `GetSourceObjectEventName` abstract methods.</span></span>

## <a name="example"></a><span data-ttu-id="6ee3f-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6ee3f-129">Example</span></span>

<span data-ttu-id="6ee3f-130">Este exemplo mostra como registrar eventos gerados por [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span><span class="sxs-lookup"><span data-stu-id="6ee3f-130">This sample shows how to register for events raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span>

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6ee3f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ee3f-131">See Also</span></span>

[<span data-ttu-id="6ee3f-132">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ee3f-132">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
