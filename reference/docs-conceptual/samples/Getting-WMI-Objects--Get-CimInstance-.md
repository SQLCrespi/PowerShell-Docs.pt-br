---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Obter objetos WMI (Get-CimInstance)
description: Este artigo mostra vários exemplos de como obter instâncias de objetos WMI de um sistema de computador.
ms.openlocfilehash: f7a005bbf39cf141e6474815d3e050314830453c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500446"
---
# <a name="getting-wmi-objects-get-ciminstance"></a><span data-ttu-id="14667-104">Obter objetos WMI (Get-CimInstance)</span><span class="sxs-lookup"><span data-stu-id="14667-104">Getting WMI Objects (Get-CimInstance)</span></span>

## <a name="getting-wmi-objects-get-ciminstance"></a><span data-ttu-id="14667-105">Obter objetos WMI (Get-CimInstance)</span><span class="sxs-lookup"><span data-stu-id="14667-105">Getting WMI Objects (Get-CimInstance)</span></span>

<span data-ttu-id="14667-106">O WMI (Instrumentação de Gerenciamento do Windows) é uma das principais tecnologias para a administração do sistema, pois ela expõe uma grande variedade de informações de maneira uniforme.</span><span class="sxs-lookup"><span data-stu-id="14667-106">Windows Management Instrumentation (WMI) is a core technology for Windows system administration because it exposes a wide range of information in a uniform manner.</span></span> <span data-ttu-id="14667-107">Devido às inúmeras possibilidades oferecidas pelo WMI, o cmdlet do PowerShell usado para acessar objetos WMI, `Get-CimInstance`, é um dos mais úteis para fazer o trabalho duro.</span><span class="sxs-lookup"><span data-stu-id="14667-107">Because of how much WMI makes possible, the PowerShell cmdlet for accessing WMI objects, `Get-CimInstance`, is one of the most useful for doing real work.</span></span> <span data-ttu-id="14667-108">Vamos discutir como usar CimCmdlets para acessar objetos WMI e como usar objetos WMI para fazer coisas específicas.</span><span class="sxs-lookup"><span data-stu-id="14667-108">We are going to discuss how to use the CimCmdlets to access WMI objects and then how to use WMI objects to do specific things.</span></span>

### <a name="listing-wmi-classes"></a><span data-ttu-id="14667-109">Listar classes WMI</span><span class="sxs-lookup"><span data-stu-id="14667-109">Listing WMI Classes</span></span>

<span data-ttu-id="14667-110">O primeiro problema que a maioria dos usuários do WMI encontram é tentar descobrir o que pode ser feito com o WMI.</span><span class="sxs-lookup"><span data-stu-id="14667-110">The first problem most WMI users encounter is trying to find out what can be done with WMI.</span></span> <span data-ttu-id="14667-111">As classes WMI descrevem os recursos que podem ser gerenciados.</span><span class="sxs-lookup"><span data-stu-id="14667-111">WMI classes describe the resources that can be managed.</span></span> <span data-ttu-id="14667-112">Há centenas de classes WMI, algumas das quais contêm dezenas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="14667-112">There are hundreds of WMI classes, some of which contain dozens of properties.</span></span>

<span data-ttu-id="14667-113">`Get-CimClass` cuida desse problema possibilitando que o WMI possa ser descoberto.</span><span class="sxs-lookup"><span data-stu-id="14667-113">`Get-CimClass` addresses this problem by making WMI discoverable.</span></span> <span data-ttu-id="14667-114">Você pode obter uma lista das classes WMI disponíveis no computador local digitando:</span><span class="sxs-lookup"><span data-stu-id="14667-114">You can get a list of the WMI classes available on the local computer by typing:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 |
  Where-Object CimClassName -like Win32* |
    Select-Object CimClassName
```

```Output
CimClassName
------------
Win32_DeviceChangeEvent
Win32_SystemConfigurationChangeEvent
Win32_VolumeChangeEvent
Win32_SystemTrace
Win32_ProcessTrace
Win32_ProcessStartTrace
Win32_ProcessStopTrace
Win32_ThreadTrace
Win32_ThreadStartTrace
Win32_ThreadStopTrace
...
```

<span data-ttu-id="14667-115">Você pode recuperar as mesmas informações de um computador remoto por meio do parâmetro **ComputerName** especificando um nome do computador ou endereço IP:</span><span class="sxs-lookup"><span data-stu-id="14667-115">You can retrieve the same information from a remote computer by using the **ComputerName** parameter, specifying a computer name or IP address:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

<span data-ttu-id="14667-116">A listagem de classe retornada por computadores remotos pode variar por sistema operacional específico que o computador está executando e as extensões WMI específicas adicionadas por aplicativos instalados.</span><span class="sxs-lookup"><span data-stu-id="14667-116">The class listing returned by remote computers may vary due to the specific operating system the computer is running and the particular WMI extensions added by installed applications.</span></span>

> [!NOTE]
> <span data-ttu-id="14667-117">Quando usar cmdlets do CIM para se conectar a um computador remoto, o computador remoto deverá estar executando o WMI, e a conta usada deverá estar no grupo de administradores locais no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="14667-117">When using CIM cmdlets to connect to a remote computer, the remote computer must be running WMI and the account you are using must be in the local administrators group on the remote computer.</span></span>
> <span data-ttu-id="14667-118">O sistema remoto não precisa ter o PowerShell instalado.</span><span class="sxs-lookup"><span data-stu-id="14667-118">The remote system does not need to have PowerShell installed.</span></span> <span data-ttu-id="14667-119">Isso permite administrar sistemas operacionais que não executam o PowerShell, mas que têm o WMI disponível.</span><span class="sxs-lookup"><span data-stu-id="14667-119">This allows you to administer operating systems that are not running PowerShell, but do have WMI available.</span></span>

### <a name="displaying-wmi-class-details"></a><span data-ttu-id="14667-120">Exibir detalhes da classe WMI</span><span class="sxs-lookup"><span data-stu-id="14667-120">Displaying WMI Class Details</span></span>

<span data-ttu-id="14667-121">Se você já souber o nome de uma classe WMI, poderá usá-la para obter informações imediatamente.</span><span class="sxs-lookup"><span data-stu-id="14667-121">If you already know the name of a WMI class, you can use it to get information immediately.</span></span> <span data-ttu-id="14667-122">Por exemplo, uma das classes WMI geralmente usadas para recuperar informações sobre um computador é **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="14667-122">For example, one of the WMI classes commonly used for retrieving information about a computer is **Win32_OperatingSystem** .</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

<span data-ttu-id="14667-123">Embora mostremos todos os parâmetros, o comando pode ser expresso de forma mais sucinta.</span><span class="sxs-lookup"><span data-stu-id="14667-123">Although we are showing all of the parameters, the command can be expressed in a more succinct way.</span></span>
<span data-ttu-id="14667-124">O parâmetro **ComputerName** não é necessário ao se conectar ao sistema local.</span><span class="sxs-lookup"><span data-stu-id="14667-124">The **ComputerName** parameter is not necessary when connecting to the local system.</span></span> <span data-ttu-id="14667-125">Vamos mostrá-lo para demonstrar o caso mais geral e lembrá-lo sobre o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="14667-125">We show it to demonstrate the most general case and remind you about the parameter.</span></span> <span data-ttu-id="14667-126">O **Namespace** usa `root/CIMV2` como padrão e também pode ser omitido.</span><span class="sxs-lookup"><span data-stu-id="14667-126">The **Namespace** defaults to `root/CIMV2`, and can be omitted as well.</span></span> <span data-ttu-id="14667-127">Por fim, a maioria dos cmdlets permitem omitir o nome dos parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="14667-127">Finally, most cmdlets allow you to omit the name of common parameters.</span></span> <span data-ttu-id="14667-128">Com `Get-CimInstance`, se nenhum nome for especificado para o primeiro parâmetro, o PowerShell o tratará como o parâmetro **Class** .</span><span class="sxs-lookup"><span data-stu-id="14667-128">With `Get-CimInstance`, if no name is specified for the first parameter, PowerShell treats it as the **Class** parameter.</span></span> <span data-ttu-id="14667-129">Isso significa que o último comando pode ter sido emitido digitando:</span><span class="sxs-lookup"><span data-stu-id="14667-129">This means the last command could have been issued by typing:</span></span>

```powershell
Get-CimInstance Win32_OperatingSystem
```

<span data-ttu-id="14667-130">A classe **Win32_OperatingSystem** tem muitos mais propriedades do que as exibidas aqui.</span><span class="sxs-lookup"><span data-stu-id="14667-130">The **Win32_OperatingSystem** class has many more properties than those displayed here.</span></span> <span data-ttu-id="14667-131">Você pode usar Get-Member para ver todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="14667-131">You can use Get-Member to see all the properties.</span></span> <span data-ttu-id="14667-132">As propriedades de uma classe WMI ficam automaticamente disponíveis assim como outras propriedades de objeto:</span><span class="sxs-lookup"><span data-stu-id="14667-132">The properties of a WMI class are automatically available like other object properties:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Get-Member -MemberType Property
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_OperatingSystem
Name                                      MemberType Definition
----                                      ---------- ----------
BootDevice                                Property   string BootDevice {get;}
BuildNumber                               Property   string BuildNumber {get;}
BuildType                                 Property   string BuildType {get;}
Caption                                   Property   string Caption {get;}
CodeSet                                   Property   string CodeSet {get;}
CountryCode                               Property   string CountryCode {get;}
CreationClassName                         Property   string CreationClassName {get;}
CSCreationClassName                       Property   string CSCreationClassName {get;}
CSDVersion                                Property   string CSDVersion {get;}
CSName                                    Property   string CSName {get;}
CurrentTimeZone                           Property   short CurrentTimeZone {get;}
DataExecutionPrevention_32BitApplications Property   bool DataExecutionPrevention_32BitApplications {get;}
DataExecutionPrevention_Available         Property   bool DataExecutionPrevention_Available {get;}
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a><span data-ttu-id="14667-133">Exibindo propriedades não padrão com cmdlets Format</span><span class="sxs-lookup"><span data-stu-id="14667-133">Displaying Non-Default Properties with Format Cmdlets</span></span>

<span data-ttu-id="14667-134">Se quiser ver as informações contidas na classe **Win32_OperatingSystem** que não são exibidas por padrão, você poderá exibi-las usando os cmdlets **Format** .</span><span class="sxs-lookup"><span data-stu-id="14667-134">If you want information contained in the **Win32_OperatingSystem** class that is not displayed by default, you can display it by using the **Format** cmdlets.</span></span> <span data-ttu-id="14667-135">Por exemplo, se você deseja exibir dados de memória disponível, digite:</span><span class="sxs-lookup"><span data-stu-id="14667-135">For example, if you want to display available memory data, type:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem |
  Format-Table -Property TotalVirtualMemorySize, TotalVisibleMemorySize,
    FreePhysicalMemory, FreeVirtualMemory, FreeSpaceInPagingFiles
```

```Output
TotalVirtualMemorySize TotalVisibleMemorySize FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------------- ------------------ ----------------- ----------------------
              33449088               16671872            6451868          18424496               16285032
```

> [!NOTE]
> <span data-ttu-id="14667-136">Os curingas funcionam com nomes de propriedade em `Format-Table`, portanto, o elemento final do pipeline pode ser reduzido para `Format-Table -Property Total*Memory*, Free*`</span><span class="sxs-lookup"><span data-stu-id="14667-136">Wildcards work with property names in `Format-Table`, so the final pipeline element can be reduced to `Format-Table -Property Total*Memory*, Free*`</span></span>

<span data-ttu-id="14667-137">Os dados da memória podem ficar mais legíveis se você formatá-los como uma lista digitando:</span><span class="sxs-lookup"><span data-stu-id="14667-137">The memory data might be more readable if you format it as a list by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Format-List Total*Memory*, Free*
```

```Output
TotalVirtualMemorySize : 33449088
TotalVisibleMemorySize : 16671872
FreePhysicalMemory     : 6524456
FreeSpaceInPagingFiles : 16285808
FreeVirtualMemory      : 18393668
Name                   : Microsoft Windows 10 Pro|C:\WINDOWS|\Device\Harddisk0\Partition2
```
