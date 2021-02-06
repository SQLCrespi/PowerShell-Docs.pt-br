---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: c27dac11cdd8ebbf1705ac3bba0c0aa5147d4fa8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598622"
---
# <span data-ttu-id="45e15-102">Get-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-102">Get-Service</span></span>

## <span data-ttu-id="45e15-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="45e15-103">SYNOPSIS</span></span>
<span data-ttu-id="45e15-104">Obtém os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="45e15-104">Gets the services on the computer.</span></span>

## <span data-ttu-id="45e15-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="45e15-105">SYNTAX</span></span>

### <span data-ttu-id="45e15-106">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="45e15-106">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="45e15-107">DisplayName</span><span class="sxs-lookup"><span data-stu-id="45e15-107">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="45e15-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="45e15-108">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="45e15-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="45e15-109">DESCRIPTION</span></span>

<span data-ttu-id="45e15-110">O `Get-Service` cmdlet obtém objetos que representam os serviços em um computador, incluindo serviços em execução e interrompidos.</span><span class="sxs-lookup"><span data-stu-id="45e15-110">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="45e15-111">Por padrão, quando `Get-Service` o é executado sem parâmetros, todos os serviços do computador local são retornados.</span><span class="sxs-lookup"><span data-stu-id="45e15-111">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="45e15-112">Você pode direcionar esse cmdlet para obter apenas serviços específicos especificando o nome do serviço ou o nome de exibição dos serviços, ou pode canalizar objetos de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="45e15-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="45e15-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="45e15-113">EXAMPLES</span></span>

### <span data-ttu-id="45e15-114">Exemplo 1: obter todos os serviços no computador</span><span class="sxs-lookup"><span data-stu-id="45e15-114">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="45e15-115">Este exemplo obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="45e15-115">This example gets all of the services on the computer.</span></span> <span data-ttu-id="45e15-116">Ele se comporta como se você tivesse digitado `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="45e15-116">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="45e15-117">A exibição padrão mostra o status, o nome do serviço e o nome para exibição de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="45e15-117">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="45e15-118">Exemplo 2: obter serviços que começam com uma cadeia de caracteres de pesquisa</span><span class="sxs-lookup"><span data-stu-id="45e15-118">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="45e15-119">Este exemplo recupera serviços com nomes de serviço que começam com WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="45e15-119">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="45e15-120">Exemplo 3: Exibir serviços que incluem uma cadeia de caracteres de pesquisa</span><span class="sxs-lookup"><span data-stu-id="45e15-120">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="45e15-121">Este exemplo exibe serviços com um nome de exibição que inclui a palavra Network.</span><span class="sxs-lookup"><span data-stu-id="45e15-121">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="45e15-122">Pesquisar o nome de exibição localiza serviços relacionados à rede mesmo quando o nome do serviço não inclui net, como xmlprov, o serviço de provisionamento de rede.</span><span class="sxs-lookup"><span data-stu-id="45e15-122">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="45e15-123">Exemplo 4: obter serviços que começam com uma cadeia de caracteres de pesquisa e uma exclusão</span><span class="sxs-lookup"><span data-stu-id="45e15-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="45e15-124">Este exemplo só obtém os serviços com nomes de serviço que começam com **Win**, exceto para o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="45e15-124">This example only gets the services with service names that begin with **win**, except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="45e15-125">Exemplo 5: Exibir serviços ativos no momento</span><span class="sxs-lookup"><span data-stu-id="45e15-125">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="45e15-126">Este exemplo exibe somente os serviços com um status de em execução.</span><span class="sxs-lookup"><span data-stu-id="45e15-126">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="45e15-127">`Get-Service` Obtém todos os serviços no computador e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="45e15-127">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="45e15-128">O `Where-Object` cmdlet seleciona apenas os serviços com uma propriedade de **status** igual a em execução.</span><span class="sxs-lookup"><span data-stu-id="45e15-128">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="45e15-129">O status é apenas uma propriedade de objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="45e15-129">Status is only one property of service objects.</span></span> <span data-ttu-id="45e15-130">Para ver todas as propriedades, digite `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="45e15-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="45e15-131">Exemplo 6: listar os serviços no computador que têm serviços dependentes</span><span class="sxs-lookup"><span data-stu-id="45e15-131">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="45e15-132">Este exemplo obtém serviços que têm serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="45e15-132">This example gets services that have dependent services.</span></span>

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

<span data-ttu-id="45e15-133">O `Get-Service` cmdlet obtém todos os serviços no computador e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="45e15-133">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="45e15-134">O `Where-Object` cmdlet seleciona os serviços cuja propriedade **dependservices** não é nula.</span><span class="sxs-lookup"><span data-stu-id="45e15-134">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="45e15-135">Os resultados são enviados para o pipeline para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="45e15-135">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="45e15-136">O parâmetro **Property** exibe o nome do serviço, o nome dos serviços dependentes e uma propriedade calculada que exibe o número de serviços dependentes para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="45e15-136">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="45e15-137">Exemplo 7: classificar serviços por valor de propriedade</span><span class="sxs-lookup"><span data-stu-id="45e15-137">Example 7: Sort services by property value</span></span>

<span data-ttu-id="45e15-138">Este exemplo mostra que quando você classifica os serviços em ordem crescente pelo valor de sua propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços.</span><span class="sxs-lookup"><span data-stu-id="45e15-138">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="45e15-139">O motivo é que o valor de **status** é uma enumeração, na qual Stopped tem um valor de 1, e a execução tem um valor de 4.</span><span class="sxs-lookup"><span data-stu-id="45e15-139">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="45e15-140">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="45e15-140">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="45e15-141">Para listar os serviços em execução primeiro, use o parâmetro **decrescente** do `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="45e15-141">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

### <span data-ttu-id="45e15-142">Exemplo 8: obter os serviços dependentes de um serviço</span><span class="sxs-lookup"><span data-stu-id="45e15-142">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="45e15-143">Este exemplo obtém os serviços que o serviço WinRM requer.</span><span class="sxs-lookup"><span data-stu-id="45e15-143">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="45e15-144">O valor da propriedade **ServicesDependedOn** do serviço é retornado.</span><span class="sxs-lookup"><span data-stu-id="45e15-144">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="45e15-145">Exemplo 9: obter um serviço por meio do operador de pipeline</span><span class="sxs-lookup"><span data-stu-id="45e15-145">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="45e15-146">Este exemplo obtém o serviço WinRM no computador local.</span><span class="sxs-lookup"><span data-stu-id="45e15-146">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="45e15-147">A cadeia de caracteres do nome do serviço, entre aspas, é enviada ao pipeline para `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="45e15-147">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="45e15-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="45e15-148">PARAMETERS</span></span>

### <span data-ttu-id="45e15-149">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="45e15-149">-DependentServices</span></span>

<span data-ttu-id="45e15-150">Indica que esse cmdlet obtém apenas os serviços que dependem do serviço especificado.</span><span class="sxs-lookup"><span data-stu-id="45e15-150">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45e15-151">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="45e15-151">-DisplayName</span></span>

<span data-ttu-id="45e15-152">Especifica, como uma matriz de cadeia de caracteres, os nomes de exibição dos serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="45e15-152">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="45e15-153">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="45e15-153">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="45e15-154">-Excluir</span><span class="sxs-lookup"><span data-stu-id="45e15-154">-Exclude</span></span>

<span data-ttu-id="45e15-155">Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="45e15-155">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="45e15-156">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="45e15-156">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="45e15-157">Insira um elemento de nome ou padrão, como `s*` .</span><span class="sxs-lookup"><span data-stu-id="45e15-157">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="45e15-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="45e15-158">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="45e15-159">-Incluir</span><span class="sxs-lookup"><span data-stu-id="45e15-159">-Include</span></span>

<span data-ttu-id="45e15-160">Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="45e15-160">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="45e15-161">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="45e15-161">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="45e15-162">Insira um elemento de nome ou padrão, como `s*` .</span><span class="sxs-lookup"><span data-stu-id="45e15-162">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="45e15-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="45e15-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="45e15-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="45e15-164">-InputObject</span></span>

<span data-ttu-id="45e15-165">Especifica objetos **ServiceController** que representam os serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="45e15-165">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="45e15-166">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="45e15-166">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="45e15-167">É possível canalizar um objeto de serviço para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="45e15-167">You can pipe a service object to this cmdlet.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="45e15-168">-Name</span><span class="sxs-lookup"><span data-stu-id="45e15-168">-Name</span></span>

<span data-ttu-id="45e15-169">Especifica os nomes de serviço dos serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="45e15-169">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="45e15-170">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="45e15-170">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="45e15-171">-Obrigatórioservices</span><span class="sxs-lookup"><span data-stu-id="45e15-171">-RequiredServices</span></span>

<span data-ttu-id="45e15-172">Indica que esse cmdlet obtém apenas os serviços que esse serviço requer.</span><span class="sxs-lookup"><span data-stu-id="45e15-172">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="45e15-173">Esse parâmetro Obtém o valor da propriedade **ServicesDependedOn** do serviço.</span><span class="sxs-lookup"><span data-stu-id="45e15-173">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="45e15-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="45e15-174">CommonParameters</span></span>

<span data-ttu-id="45e15-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="45e15-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="45e15-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="45e15-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="45e15-177">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="45e15-177">INPUTS</span></span>

### <span data-ttu-id="45e15-178">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="45e15-178">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="45e15-179">É possível canalizar um objeto de serviço ou um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="45e15-179">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="45e15-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="45e15-180">OUTPUTS</span></span>

### <span data-ttu-id="45e15-181">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="45e15-181">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="45e15-182">Esse cmdlet retorna objetos que representam os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="45e15-182">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="45e15-183">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="45e15-183">NOTES</span></span>

<span data-ttu-id="45e15-184">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="45e15-184">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="45e15-185">A partir do PowerShell 6,0, as seguintes propriedades são adicionadas aos objetos **ServiceController** : **username**, **Description**, **DelayedAutoStart**, **BinaryPathName** e **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="45e15-185">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName**, **Description**, **DelayedAutoStart**, **BinaryPathName**, and **StartupType** .</span></span>

<span data-ttu-id="45e15-186">Você também pode consultar `Get-Service` por seu alias interno, `gsv` .</span><span class="sxs-lookup"><span data-stu-id="45e15-186">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="45e15-187">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="45e15-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="45e15-188">Esse cmdlet pode exibir serviços somente quando o usuário atual tem permissão para vê-los.</span><span class="sxs-lookup"><span data-stu-id="45e15-188">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="45e15-189">Se esse cmdlet não exibir serviços, talvez você não tenha permissão para vê-los.</span><span class="sxs-lookup"><span data-stu-id="45e15-189">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="45e15-190">Para localizar o nome do serviço e o nome de exibição de cada serviço em seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="45e15-190">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="45e15-191">Os nomes de serviço aparecem na coluna nome e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="45e15-191">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="45e15-192">Quando você classifica em ordem crescente pelo valor da propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços.</span><span class="sxs-lookup"><span data-stu-id="45e15-192">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="45e15-193">A propriedade **status** do serviço é um valor enumerado e os nomes de status representam valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="45e15-193">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="45e15-194">A ordem de classificação é baseada no valor inteiro, não no nome.</span><span class="sxs-lookup"><span data-stu-id="45e15-194">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="45e15-195">Parado aparece antes porque a execução foi interrompida tem um valor de 1 e a execução tem um valor de 4.</span><span class="sxs-lookup"><span data-stu-id="45e15-195">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="45e15-196">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="45e15-196">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="45e15-197">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="45e15-197">RELATED LINKS</span></span>

[<span data-ttu-id="45e15-198">New-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-198">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="45e15-199">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-199">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="45e15-200">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-200">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="45e15-201">Set-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-201">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="45e15-202">Start-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-202">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="45e15-203">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-203">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="45e15-204">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-204">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="45e15-205">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="45e15-205">Remove-Service</span></span>](Remove-Service.md)
