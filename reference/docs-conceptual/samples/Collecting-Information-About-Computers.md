---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Coletando informações sobre computadores
ms.openlocfilehash: 9407ff15b3c3ca6b3adab60d4d01d957c599e79e
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737229"
---
# <a name="collecting-information-about-computers"></a><span data-ttu-id="59f88-103">Coletando informações sobre computadores</span><span class="sxs-lookup"><span data-stu-id="59f88-103">Collecting Information About Computers</span></span>

<span data-ttu-id="59f88-104">Os cmdlets do módulo **CimCmdlets** são os cmdlets mais importantes para tarefas de gerenciamento geral do sistema.</span><span class="sxs-lookup"><span data-stu-id="59f88-104">Cmdlets from **CimCmdlets** module are the most important cmdlets for general system management tasks.</span></span> <span data-ttu-id="59f88-105">Todas as configurações do subsistema críticas são expostas por meio do WMI.</span><span class="sxs-lookup"><span data-stu-id="59f88-105">All critical subsystem settings are exposed through WMI.</span></span> <span data-ttu-id="59f88-106">Além disso, o WMI trata dados como objetos que são coleções de um ou mais itens.</span><span class="sxs-lookup"><span data-stu-id="59f88-106">Furthermore, WMI treats data as objects that are in collections of one or more items.</span></span> <span data-ttu-id="59f88-107">Como o Windows PowerShell também funciona com objetos e tem um pipeline que permite tratar objetos únicos ou vários objetos da mesma forma, o acesso ao WMI genérico permite executar algumas tarefas avançadas com pouquíssimo trabalho.</span><span class="sxs-lookup"><span data-stu-id="59f88-107">Because Windows PowerShell also works with objects and has a pipeline that allows you to treat single or multiple objects in the same way, generic WMI access allows you to perform some advanced tasks with very little work.</span></span>

## <a name="listing-desktop-settings"></a><span data-ttu-id="59f88-108">Listar Configurações de Área de Trabalho</span><span class="sxs-lookup"><span data-stu-id="59f88-108">Listing Desktop Settings</span></span>

<span data-ttu-id="59f88-109">Vamos começar com um comando que coleta informações sobre as áreas de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="59f88-109">We'll begin with a command that collects information about the desktops on the local computer.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop
```

<span data-ttu-id="59f88-110">Isso retorna informações para todos os desktops, independentemente de estarem em uso ou não.</span><span class="sxs-lookup"><span data-stu-id="59f88-110">This returns information for all desktops, whether they are in use or not.</span></span>

> [!NOTE]
> <span data-ttu-id="59f88-111">Informações retornadas por algumas classes WMI podem ser muito detalhadas e geralmente incluem metadados sobre a classe WMI.</span><span class="sxs-lookup"><span data-stu-id="59f88-111">Information returned by some WMI classes can be very detailed, and often include metadata about the WMI class.</span></span>

<span data-ttu-id="59f88-112">Como a maioria dessas propriedades de metadados tem nomes que começam com **Cim**, é possível filtrar as propriedades usando `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="59f88-112">Because most of these metadata properties have names that begin with **Cim**, you can filter the properties using `Select-Object`.</span></span> <span data-ttu-id="59f88-113">Especifique o parâmetro **-ExcludeProperty** com "Cim\*" como o valor.</span><span class="sxs-lookup"><span data-stu-id="59f88-113">Specify the **-ExcludeProperty** parameter with "Cim\*" as the value.</span></span> <span data-ttu-id="59f88-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59f88-114">For example:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="59f88-115">Para filtrar os metadados, use um operador de pipeline (|) para enviar os resultados do comando `Get-CimInstance` para `Select-Object -ExcludeProperty "CIM*"`.</span><span class="sxs-lookup"><span data-stu-id="59f88-115">To filter out the metadata, use a pipeline operator (|) to send the results of the `Get-CimInstance` command to `Select-Object -ExcludeProperty "CIM*"`.</span></span>

## <a name="listing-bios-information"></a><span data-ttu-id="59f88-116">Listando informações de BIOS</span><span class="sxs-lookup"><span data-stu-id="59f88-116">Listing BIOS Information</span></span>

<span data-ttu-id="59f88-117">A classe WMI **Win32_BIOS** retorna informações bastante compactas e completas sobre o BIOS do sistema no computador local:</span><span class="sxs-lookup"><span data-stu-id="59f88-117">The WMI **Win32_BIOS** class returns fairly compact and complete information about the system BIOS on the local computer:</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

## <a name="listing-processor-information"></a><span data-ttu-id="59f88-118">Listar informações do processador</span><span class="sxs-lookup"><span data-stu-id="59f88-118">Listing Processor Information</span></span>

<span data-ttu-id="59f88-119">Você pode recuperar informações gerais do processador por meio da classe **Win32_Processor** do WMI, embora provavelmente você preferirá filtrar as informações:</span><span class="sxs-lookup"><span data-stu-id="59f88-119">You can retrieve general processor information by using WMI's **Win32_Processor** class, although you will likely want to filter the information:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Processor | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="59f88-120">Para ver uma cadeia de caracteres de descrição genérica da família do processador, basta retornar a propriedade **SystemType**:</span><span class="sxs-lookup"><span data-stu-id="59f88-120">For a generic description string of the processor family, you can just return the **SystemType** property:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a><span data-ttu-id="59f88-121">Listar o modelo e o fabricante do computador</span><span class="sxs-lookup"><span data-stu-id="59f88-121">Listing Computer Manufacturer and Model</span></span>

<span data-ttu-id="59f88-122">As informações de modelo do computador também estão disponíveis no **Win32_ComputerSystem**.</span><span class="sxs-lookup"><span data-stu-id="59f88-122">Computer model information is also available from **Win32_ComputerSystem**.</span></span> <span data-ttu-id="59f88-123">A saída padrão exibida não precisará de filtragem para fornecer dados de OEM:</span><span class="sxs-lookup"><span data-stu-id="59f88-123">The standard displayed output will not need any filtering to provide OEM data:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```Output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

<span data-ttu-id="59f88-124">A saída de comandos como este, que retornam informações diretamente de alguns dispositivos de hardware, é válida na mesma medida que os dados que você tem.</span><span class="sxs-lookup"><span data-stu-id="59f88-124">Your output from commands such as this, which return information directly from some hardware, is only as good as the data you have.</span></span> <span data-ttu-id="59f88-125">Algumas informações não são configuradas corretamente pelos fabricantes de hardware e, portanto, podem estar indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="59f88-125">Some information is not correctly configured by hardware manufacturers and may therefore be unavailable.</span></span>

## <a name="listing-installed-hotfixes"></a><span data-ttu-id="59f88-126">Listar os hotfixes instalados</span><span class="sxs-lookup"><span data-stu-id="59f88-126">Listing Installed Hotfixes</span></span>

<span data-ttu-id="59f88-127">Você pode listar os hotfixes instalados usando **Win32_QuickFixEngineering**:</span><span class="sxs-lookup"><span data-stu-id="59f88-127">You can list all installed hotfixes by using **Win32_QuickFixEngineering**:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering
```

<span data-ttu-id="59f88-128">Essa classe retorna uma lista de hotfixes que tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="59f88-128">This class returns a list of hotfixes that looks like this:</span></span>

```Output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

<span data-ttu-id="59f88-129">Para uma saída mais sucinta, pode ser útil excluir algumas propriedades.</span><span class="sxs-lookup"><span data-stu-id="59f88-129">For more succinct output, you may want to exclude some properties.</span></span> <span data-ttu-id="59f88-130">Embora você possa usar o parâmetro **Property** de `Get-CimInstance` para escolher somente a **HotFixID**, fazer isso, na verdade, retornará mais informações, pois todos os metadados são exibidos por padrão:</span><span class="sxs-lookup"><span data-stu-id="59f88-130">Although you can use the `Get-CimInstance`'s **Property** parameter to choose only the **HotFixID**, doing so will actually return more information, because all the metadata is displayed by default:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixID
```

```Output
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4533002
InstalledBy           :
ServicePackInEffect   :
PSComputerName        :
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name…}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
...
```

<span data-ttu-id="59f88-131">Os dados adicionais são retornados, pois o parâmetro**Property** no `Get-CimInstance` restringe as propriedades retornadas de instâncias da classe WMI, não o objeto retornado para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59f88-131">The additional data is returned, because the **Property** parameter in `Get-CimInstance` restricts the properties returned from WMI class instances, not the object returned to PowerShell.</span></span> <span data-ttu-id="59f88-132">Para reduzir a saída, use `Select-Object`:</span><span class="sxs-lookup"><span data-stu-id="59f88-132">To reduce the output, use `Select-Object`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixId | Select-Object -Property HotFixId
```

```Output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a><span data-ttu-id="59f88-133">Listar informações de versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="59f88-133">Listing Operating System Version Information</span></span>

<span data-ttu-id="59f88-134">As propriedades da classe **Win32_OperatingSystem** incluem informações sobre versão e service pack.</span><span class="sxs-lookup"><span data-stu-id="59f88-134">The **Win32_OperatingSystem** class properties include version and service pack information.</span></span> <span data-ttu-id="59f88-135">Você pode selecionar apenas essas propriedades para obter um resumo das informações de versão de **Win32_OperatingSystem**:</span><span class="sxs-lookup"><span data-stu-id="59f88-135">You can explicitly select only these properties to get a version information summary from **Win32_OperatingSystem**:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

<span data-ttu-id="59f88-136">Você também pode usar caracteres curinga com o parâmetro **Property** de `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="59f88-136">You can also use wildcards with the `Select-Object`'s **Property** parameter.</span></span> <span data-ttu-id="59f88-137">Como todas as propriedades que começam com **Build** ou **ServicePack** são importantes para usar aqui, podemos reduzir isso para a seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="59f88-137">Because all the properties beginning with either **Build** or **ServicePack** are important to use here, we can shorten this to the following form:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property Build*,OSType,ServicePack*
```

```Output
BuildNumber             : 18362
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

## <a name="listing-local-users-and-owner"></a><span data-ttu-id="59f88-138">Listar proprietário e usuários locais</span><span class="sxs-lookup"><span data-stu-id="59f88-138">Listing Local Users and Owner</span></span>

<span data-ttu-id="59f88-139">Informações gerais de usuário local – o número de usuários licenciados, número de usuários atuais e nome do proprietário – podem ser encontradas com uma seleção das propriedades da classe **Win32_OperatingSystem**.</span><span class="sxs-lookup"><span data-stu-id="59f88-139">Local general user information — number of licensed users, current number of users, and owner name — can be found with a selection of **Win32_OperatingSystem** class properties.</span></span> <span data-ttu-id="59f88-140">Você pode selecionar as propriedades a serem exibidas desta forma:</span><span class="sxs-lookup"><span data-stu-id="59f88-140">You can explicitly select the properties to display like this:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

<span data-ttu-id="59f88-141">Uma versão mais sucinta usando caracteres curinga seria:</span><span class="sxs-lookup"><span data-stu-id="59f88-141">A more succinct version using wildcards is:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a><span data-ttu-id="59f88-142">Obter o espaço em disco disponível</span><span class="sxs-lookup"><span data-stu-id="59f88-142">Getting Available Disk Space</span></span>

<span data-ttu-id="59f88-143">Para ver o espaço em disco e o espaço livre para as unidades locais, você pode usar a classe WMI Win32_LogicalDisk.</span><span class="sxs-lookup"><span data-stu-id="59f88-143">To see the disk space and free space for local drives, you can use the Win32_LogicalDisk WMI class.</span></span>
<span data-ttu-id="59f88-144">Você precisa ver apenas as instâncias com um DriveType de 3 – o valor que o WMI usa para discos rígidos fixos.</span><span class="sxs-lookup"><span data-stu-id="59f88-144">You need to see only instances with a DriveType of 3 — the value WMI uses for fixed hard disks.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
```

```Output
DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .
```

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" |
  Measure-Object -Property FreeSpace,Size -Sum |
    Select-Object -Property Property,Sum
```

```Output
Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

## <a name="getting-logon-session-information"></a><span data-ttu-id="59f88-145">Obter informações de sessão de logon</span><span class="sxs-lookup"><span data-stu-id="59f88-145">Getting Logon Session Information</span></span>

<span data-ttu-id="59f88-146">Você pode obter informações gerais sobre as sessões de logon associadas aos usuários por meio da classe WMI **Win32_LogonSession**:</span><span class="sxs-lookup"><span data-stu-id="59f88-146">You can get general information about logon sessions associated with users through the **Win32_LogonSession** WMI class:</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogonSession
```

## <a name="getting-the-user-logged-on-to-a-computer"></a><span data-ttu-id="59f88-147">Obter o usuário conectado a um computador</span><span class="sxs-lookup"><span data-stu-id="59f88-147">Getting the User Logged on to a Computer</span></span>

<span data-ttu-id="59f88-148">Você pode exibir o usuário conectado a um sistema de computador específico usando Win32_ComputerSystem.</span><span class="sxs-lookup"><span data-stu-id="59f88-148">You can display the user logged on to a particular computer system using Win32_ComputerSystem.</span></span> <span data-ttu-id="59f88-149">Esse comando retorna somente o usuário conectado à área de trabalho do sistema:</span><span class="sxs-lookup"><span data-stu-id="59f88-149">This command returns only the user logged on to the system desktop:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName
```

## <a name="getting-local-time-from-a-computer"></a><span data-ttu-id="59f88-150">Obter a hora local de um computador</span><span class="sxs-lookup"><span data-stu-id="59f88-150">Getting Local Time from a Computer</span></span>

<span data-ttu-id="59f88-151">Você pode recuperar a hora local atual em um computador específico usando a classe WMI **Win32_LocalTime**.</span><span class="sxs-lookup"><span data-stu-id="59f88-151">You can retrieve the current local time on a specific computer by using the **Win32_LocalTime** WMI class.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LocalTime
```

```Output
Day            : 23
DayOfWeek      : 1
Hour           : 8
Milliseconds   :
Minute         : 52
Month          : 12
Quarter        : 4
Second         : 55
WeekInMonth    : 4
Year           : 2019
PSComputerName :
```

## <a name="displaying-service-status"></a><span data-ttu-id="59f88-152">Exibir o status do serviço</span><span class="sxs-lookup"><span data-stu-id="59f88-152">Displaying Service Status</span></span>

<span data-ttu-id="59f88-153">Para exibir o status de todos os serviços em um computador específico, você pode usar o cmdlet `Get-Service` localmente.</span><span class="sxs-lookup"><span data-stu-id="59f88-153">To view the status of all services on a specific computer, you can locally use the `Get-Service` cmdlet.</span></span> <span data-ttu-id="59f88-154">Para sistemas remotos, você pode usar a classe WMI **Win32_Service**.</span><span class="sxs-lookup"><span data-stu-id="59f88-154">For remote systems, you can use the **Win32_Service** WMI class.</span></span> <span data-ttu-id="59f88-155">Se você também usar `Select-Object` para filtrar os resultados para **Status**, **Nome** e **DisplayName**, o formato de saída será praticamente idêntico ao de `Get-Service`:</span><span class="sxs-lookup"><span data-stu-id="59f88-155">If you also use `Select-Object` to filter the results to **Status**, **Name**, and **DisplayName**, the output format will be almost identical to that from `Get-Service`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Select-Object -Property Status,Name,DisplayName
```

<span data-ttu-id="59f88-156">Para permitir a exibição completa de nomes para os serviços ocasionais com nomes muito longos, pode ser útil usar `Format-Table` com os parâmetros **AutoSize** e **Wrap** para otimizar a largura da coluna e permitir o encapsulamento de nomes longos em vez do truncamento:</span><span class="sxs-lookup"><span data-stu-id="59f88-156">To allow the complete display of names for the occasional services with extremely long names, you may want to use `Format-Table` with the **AutoSize** and **Wrap** parameters, to optimize column width and allow long names to wrap instead of being truncated:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
