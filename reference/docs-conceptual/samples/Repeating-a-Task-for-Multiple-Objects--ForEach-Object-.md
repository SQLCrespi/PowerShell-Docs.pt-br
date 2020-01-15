---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Repetir uma tarefa para vários objetos ForEach Object
ms.openlocfilehash: bf89070fd9b006fa9b0b262ab63ffadd81072ecc
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736872"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="f0056-103">Repetir uma tarefa para vários objetos (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="f0056-103">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="f0056-104">O cmdlet `ForEach-Object` usa blocos de script e o descritor `$_` do objeto de pipeline atual para permitir a execução de um comando em cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="f0056-104">The `ForEach-Object` cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="f0056-105">Isso pode ser usado para executar algumas tarefas complicadas.</span><span class="sxs-lookup"><span data-stu-id="f0056-105">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="f0056-106">Uma situação em que isso pode ser útil é manipular dados para torná-los mais úteis.</span><span class="sxs-lookup"><span data-stu-id="f0056-106">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="f0056-107">Por exemplo, a classe **Win32_LogicalDisk** do WMI pode ser usada para retornar informações de espaço livre para cada disco local.</span><span class="sxs-lookup"><span data-stu-id="f0056-107">For example, the **Win32_LogicalDisk** class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="f0056-108">Contudo, os dados são retornados em bytes, o que dificulta a leitura:</span><span class="sxs-lookup"><span data-stu-id="f0056-108">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

<span data-ttu-id="f0056-109">Podemos converter o valor **FreeSpace** para megabytes dividindo cada valor por 1 MB.</span><span class="sxs-lookup"><span data-stu-id="f0056-109">We can convert the **FreeSpace** value to megabytes by dividing each value by 1MB.</span></span> <span data-ttu-id="f0056-110">Você pode fazer isso em um bloco de script de `ForEach-Object` digitando:</span><span class="sxs-lookup"><span data-stu-id="f0056-110">You can do that in a `ForEach-Object` script block by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

<span data-ttu-id="f0056-111">Infelizmente, a saída agora é de dados sem nenhum rótulo associado.</span><span class="sxs-lookup"><span data-stu-id="f0056-111">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="f0056-112">Como propriedades WMI como essa são somente leitura, não é possível converter diretamente o **FreeSpace**.</span><span class="sxs-lookup"><span data-stu-id="f0056-112">Because WMI properties such as this are read-only, you cannot directly convert **FreeSpace**.</span></span> <span data-ttu-id="f0056-113">Se você digitar:</span><span class="sxs-lookup"><span data-stu-id="f0056-113">If you type this:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

<span data-ttu-id="f0056-114">Receberá uma mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f0056-114">You get an error message:</span></span>

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

<span data-ttu-id="f0056-115">É possível reorganizar os dados usando algumas técnicas avançadas, mas uma abordagem mais simples é criar um objeto usando `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="f0056-115">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using `Select-Object`.</span></span>
