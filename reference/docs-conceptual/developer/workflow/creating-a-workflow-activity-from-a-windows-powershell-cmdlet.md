---
title: Criando uma atividade de fluxo de trabalho a partir de um cmdlet do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4174e84f-d516-4aca-b418-273047dcfb07
caps.latest.revision: 7
ms.openlocfilehash: f45b5e985fa38ca4ff41707f1842ddb8b930e2b1
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557492"
---
# <a name="creating-a-workflow-activity-from-a-windows-powershell-cmdlet"></a><span data-ttu-id="07543-102">Criar uma atividade de fluxo de trabalho de um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07543-102">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>

<span data-ttu-id="07543-103">Qualquer módulo ou cmdlet do Windows PowerShell pode ser empacotado como uma atividade de fluxo de trabalho usando os métodos da classe [Microsoft. PowerShell. Activities. Activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) .</span><span class="sxs-lookup"><span data-stu-id="07543-103">Any Windows PowerShell module or cmdlet can be packaged as a Workflow activity by using the methods of the [Microsoft.Powershell.Activities.Activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) class.</span></span> <span data-ttu-id="07543-104">Use os métodos [Microsoft. PowerShell. Activities. Activitygenerator. Generatefrommoduleinfo \*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromModuleInfo), [Microsoft. PowerShell. Activities. Activitygenerator. Generatefromcommandinfo \*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromCommandInfo)e [Microsoft. PowerShell. Activities. Activitygenerator. Generatefromname \*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromName) da classe [Microsoft. PowerShell. Activities. Activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) para gerar código C# que representa uma atividade.</span><span class="sxs-lookup"><span data-stu-id="07543-104">Use the [Microsoft.Powershell.Activities.Activitygenerator.Generatefrommoduleinfo\*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromModuleInfo), [Microsoft.Powershell.Activities.Activitygenerator.Generatefromcommandinfo\*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromCommandInfo), and [Microsoft.Powershell.Activities.Activitygenerator.Generatefromname\*](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromName) methods of the [Microsoft.Powershell.Activities.Activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) class to generate C# code that represents an activity.</span></span> <span data-ttu-id="07543-105">Em seguida, você pode compilar o código C# resultante em um assembly que pode ser adicionado a um projeto como uma atividade.</span><span class="sxs-lookup"><span data-stu-id="07543-105">You can then compile the resulting C# code into an assembly that can be added to a project as an activity.</span></span>

<span data-ttu-id="07543-106">Em seguida, você pode compilar o código C# resultante em um assembly que pode ser adicionado a um projeto como uma atividade usando uma linha de comando com o formulário a seguir.</span><span class="sxs-lookup"><span data-stu-id="07543-106">You can then compile the resulting C# code into an assembly that can be added to a project as an activity by using a command line with the following form.</span></span>

<span data-ttu-id="07543-107">**CSC/nologo/out: AssemblyName/target: library/Reference: System. Activities. Activity/Reference: Microsoft. PowerShell. Activities codefile.cs**</span><span class="sxs-lookup"><span data-stu-id="07543-107">**csc /nologo /out:AssemblyName /target:library /reference:System.Activities.Activity /reference:Microsoft.PowerShell.Activities codefile.cs**</span></span>

## <a name="example"></a><span data-ttu-id="07543-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="07543-108">Example</span></span>

<span data-ttu-id="07543-109">O exemplo a seguir demonstra como gerar código C# para uma atividade de um módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07543-109">The following example demonstrates how to generate C# code for an activity from a Windows PowerShell module.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromModuleInfo(ModuleInfo, "MyNamespace").First<String>();

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```

## <a name="example"></a><span data-ttu-id="07543-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="07543-110">Example</span></span>

<span data-ttu-id="07543-111">O exemplo a seguir demonstra como gerar código C# para uma atividade de um cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07543-111">The following example demonstrates how to generate C# code for an activity from a Windows PowerShell cmdlet.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            Collection<CommandInfo> CommandInfos = new Collection<CommandInfo> { };
            CommandInfo MyCommand;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ps.AddCommand("Get-Command").AddArgument(ModuleInfo);
            CommandInfos = ps.Invoke<CommandInfo>();

            MyCommand = CommandInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromCommandInfo(MyCommand, "MyNamespace");

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```
