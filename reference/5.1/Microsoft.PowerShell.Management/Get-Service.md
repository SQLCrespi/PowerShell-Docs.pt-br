---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194167"
---
# <span data-ttu-id="f4399-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-103">Get-Service</span></span>

## <span data-ttu-id="f4399-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f4399-104">SYNOPSIS</span></span>
<span data-ttu-id="f4399-105">Obtém os serviços em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="f4399-105">Gets the services on a local or remote computer.</span></span>

## <span data-ttu-id="f4399-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4399-106">SYNTAX</span></span>

### <span data-ttu-id="f4399-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="f4399-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f4399-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4399-108">DisplayName</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f4399-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="f4399-109">InputObject</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="f4399-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4399-110">DESCRIPTION</span></span>

<span data-ttu-id="f4399-111">O cmdlet **Get-Service** obtém objetos que representam os serviços em um computador local ou em um computador remoto, incluindo serviços em execução e interrompidos.</span><span class="sxs-lookup"><span data-stu-id="f4399-111">The **Get-Service** cmdlet gets objects that represent the services on a local computer or on a remote computer, including running and stopped services.</span></span>

<span data-ttu-id="f4399-112">Você pode direcionar esse cmdlet para obter apenas serviços específicos especificando o nome do serviço ou o nome de exibição dos serviços, ou pode canalizar objetos de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4399-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="f4399-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f4399-113">EXAMPLES</span></span>

### <span data-ttu-id="f4399-114">Exemplo 1: obter todos os serviços no computador</span><span class="sxs-lookup"><span data-stu-id="f4399-114">Example 1: Get all services on the computer</span></span>

```powershell
Get-Service
```

<span data-ttu-id="f4399-115">Esse comando obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-115">This command gets all of the services on the computer.</span></span>
<span data-ttu-id="f4399-116">Ele se comporta como se você tivesse digitado `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="f4399-116">It behaves as though you typed `Get-Service *`.</span></span>
<span data-ttu-id="f4399-117">A exibição padrão mostra o status, o nome do serviço e o nome para exibição de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="f4399-117">The default display shows the status, service name, and display name of each service.</span></span>

### <span data-ttu-id="f4399-118">Exemplo 2: obter serviços que começam com uma cadeia de caracteres de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f4399-118">Example 2: Get services that begin with a search string</span></span>

```powershell
Get-Service "wmi*"
```

<span data-ttu-id="f4399-119">Esse comando recupera serviços com nomes de serviço que começam com WMI (o acrônimo para Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="f4399-119">This command retrieves services with service names that begin with WMI (the acronym for Windows Management Instrumentation).</span></span>

### <span data-ttu-id="f4399-120">Exemplo 3: Exibir serviços que incluem uma cadeia de caracteres de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f4399-120">Example 3: Display services that include a search string</span></span>

```powershell
Get-Service -Displayname "*network*"
```

<span data-ttu-id="f4399-121">Este comando exibe os serviços com um nome de exibição que inclui a palavra rede.</span><span class="sxs-lookup"><span data-stu-id="f4399-121">This command displays services with a display name that includes the word network.</span></span>
<span data-ttu-id="f4399-122">A pesquisa pelo nome de exibição localiza os serviços relacionados à rede mesmo quando o nome do serviço não inclui "Net", como xmlprov, o serviço de provisionamento de rede.</span><span class="sxs-lookup"><span data-stu-id="f4399-122">Searching the display name finds network-related services even when the service name does not include "Net", such as xmlprov, the Network Provisioning Service.</span></span>

### <span data-ttu-id="f4399-123">Exemplo 4: obter serviços que começam com uma cadeia de caracteres de pesquisa e uma exclusão</span><span class="sxs-lookup"><span data-stu-id="f4399-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

<span data-ttu-id="f4399-124">Esses comandos obtêm somente os serviços com nomes de serviço que começam com Win, exceto para o serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="f4399-124">These commands get only the services with service names that begin with win, except for the WinRM service.</span></span>

### <span data-ttu-id="f4399-125">Exemplo 5: Exibir serviços ativos no momento</span><span class="sxs-lookup"><span data-stu-id="f4399-125">Example 5: Display services that are currently active</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="f4399-126">Esse comando exibe somente os serviços que estão ativos no momento.</span><span class="sxs-lookup"><span data-stu-id="f4399-126">This command displays only the services that are currently active.</span></span>
<span data-ttu-id="f4399-127">Ele usa o cmdlet **Get-Service** para obter todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-127">It uses the **Get-Service** cmdlet to get all of the services on the computer.</span></span>
<span data-ttu-id="f4399-128">O operador de pipeline (|) passa os resultados para o cmdlet Where-Object, que seleciona apenas os serviços com uma propriedade de status igual a em execução.</span><span class="sxs-lookup"><span data-stu-id="f4399-128">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects only the services with a Status property that equals Running.</span></span>

<span data-ttu-id="f4399-129">O status é apenas uma propriedade de objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="f4399-129">Status is only one property of service objects.</span></span>
<span data-ttu-id="f4399-130">Para ver todas as propriedades, digite `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f4399-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="f4399-131">Exemplo 6: obter os serviços em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="f4399-131">Example 6: Get the services on a remote computer</span></span>

```powershell
Get-Service -ComputerName "Server02"
```

<span data-ttu-id="f4399-132">Esse comando obtém os serviços no computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="f4399-132">This command gets the services on the Server02 remote computer.</span></span>

<span data-ttu-id="f4399-133">Como o parâmetro *ComputerName* de **Get-Service** não usa a comunicação remota do Windows PowerShell, você pode usar esse parâmetro mesmo que o computador não esteja configurado para comunicação remota no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4399-133">Because the *ComputerName* parameter of **Get-Service** does not use Windows PowerShell remoting, you can use this parameter even if the computer is not configured for remoting in Windows PowerShell.</span></span>

### <span data-ttu-id="f4399-134">Exemplo 7: listar os serviços no computador local que têm serviços dependentes</span><span class="sxs-lookup"><span data-stu-id="f4399-134">Example 7: List the services on the local computer that have dependent services</span></span>

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

<span data-ttu-id="f4399-135">O primeiro comando usa o cmdlet **Get-Service** para obter os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-135">The first command uses the **Get-Service** cmdlet to get the services on the computer.</span></span>
<span data-ttu-id="f4399-136">Um operador de pipeline (|) envia os serviços para o cmdlet **Where-Object** , que seleciona os serviços cuja propriedade **dependservices** não é nula.</span><span class="sxs-lookup"><span data-stu-id="f4399-136">A pipeline operator (|) sends the services to the **Where-Object** cmdlet, which selects the services whose **DependentServices** property is not null.</span></span>

<span data-ttu-id="f4399-137">Outro operador de pipeline envia os resultados para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="f4399-137">Another pipeline operator sends the results to the Format-List cmdlet.</span></span>
<span data-ttu-id="f4399-138">O comando usa seu parâmetro *Property* para exibir o nome do serviço, o nome dos serviços dependentes e uma propriedade calculada que exibe o número de serviços dependentes que cada serviço tem.</span><span class="sxs-lookup"><span data-stu-id="f4399-138">The command uses its *Property* parameter to display the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services that each service has.</span></span>

### <span data-ttu-id="f4399-139">Exemplo 8: classificar serviços por valor de propriedade</span><span class="sxs-lookup"><span data-stu-id="f4399-139">Example 8: Sort services by property value</span></span>

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

<span data-ttu-id="f4399-140">Esse comando mostra que quando você classifica os serviços em ordem crescente pelo valor de sua propriedade **status** , os serviços interrompidos aparecem antes de executar os serviços.</span><span class="sxs-lookup"><span data-stu-id="f4399-140">This command shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span>
<span data-ttu-id="f4399-141">Isso acontece porque o valor de status é uma enumeração, na qual Stopped tem um valor de 1, e a execução tem um valor de 4.</span><span class="sxs-lookup"><span data-stu-id="f4399-141">This happens because the value of Status is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span>

<span data-ttu-id="f4399-142">Para listar os serviços em execução primeiro, use o parâmetro *decrescente* do cmdlet Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="f4399-142">To list running services first, use the *Descending* parameter of the Sort-Object cmdlet.</span></span>

### <span data-ttu-id="f4399-143">Exemplo 9: obter serviços em vários computadores</span><span class="sxs-lookup"><span data-stu-id="f4399-143">Example 9: Get services on multiple computers</span></span>

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

<span data-ttu-id="f4399-144">Esse comando usa o cmdlet **Get-Service** para executar um comando Get-Service WinRM em dois computadores remotos e no computador local ("localhost").</span><span class="sxs-lookup"><span data-stu-id="f4399-144">This command uses the **Get-Service** cmdlet to run a Get-Service Winrm command on two remote computers and the local computer ("localhost").</span></span>

<span data-ttu-id="f4399-145">O comando é executado nos computadores remotos e os resultados são retornados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="f4399-145">The command runs on the remote computers, and the results are returned to the local computer.</span></span>
<span data-ttu-id="f4399-146">Um operador de pipeline (|) envia os resultados para o cmdlet **Format-Table** , que formata os serviços como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f4399-146">A pipeline operator (|) sends the results to the **Format-Table** cmdlet, which formats the services as a table.</span></span>
<span data-ttu-id="f4399-147">O comando **Format-Table** usa o parâmetro *Property* para especificar as propriedades exibidas na tabela, incluindo a propriedade **MachineName** .</span><span class="sxs-lookup"><span data-stu-id="f4399-147">The **Format-Table** command uses the *Property* parameter to specify the properties displayed in the table, including the **MachineName** property.</span></span>

### <span data-ttu-id="f4399-148">Exemplo 10: obter os serviços dependentes de um serviço</span><span class="sxs-lookup"><span data-stu-id="f4399-148">Example 10: Get the dependent services of a service</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

<span data-ttu-id="f4399-149">Esse comando obtém os serviços que o serviço WinRM necessita.</span><span class="sxs-lookup"><span data-stu-id="f4399-149">This command gets the services that the WinRM service requires.</span></span>

<span data-ttu-id="f4399-150">O comando retorna o valor da propriedade **ServicesDependedOn** do serviço.</span><span class="sxs-lookup"><span data-stu-id="f4399-150">The command returns the value of the **ServicesDependedOn** property of the service.</span></span>

### <span data-ttu-id="f4399-151">Exemplo 11: obter um serviço por meio do operador de pipeline</span><span class="sxs-lookup"><span data-stu-id="f4399-151">Example 11: Get a service through the pipeline operator</span></span>

```powershell
"WinRM" | Get-Service
```

<span data-ttu-id="f4399-152">Esse comando inicia o serviço WinRM no computador local.</span><span class="sxs-lookup"><span data-stu-id="f4399-152">This command gets the WinRM service on the local computer.</span></span>
<span data-ttu-id="f4399-153">Este exemplo mostra que é possível canalizar uma cadeia de caracteres de nome de serviço (entre aspas) para **Get-Service** .</span><span class="sxs-lookup"><span data-stu-id="f4399-153">This example shows that you can pipe a service name string (enclosed in quotation marks) to **Get-Service** .</span></span>

## <span data-ttu-id="f4399-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4399-154">PARAMETERS</span></span>

### <span data-ttu-id="f4399-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f4399-155">-ComputerName</span></span>

<span data-ttu-id="f4399-156">Obtém os serviços em execução nos computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="f4399-156">Gets the services running on the specified computers.</span></span>
<span data-ttu-id="f4399-157">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="f4399-157">The default is the local computer.</span></span>

<span data-ttu-id="f4399-158">Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f4399-158">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="f4399-159">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="f4399-159">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="f4399-160">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4399-160">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="f4399-161">Você pode usar o parâmetro *ComputerName* de **Get-Service** mesmo se o computador não estiver configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="f4399-161">You can use the *ComputerName* parameter of **Get-Service** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4399-162">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="f4399-162">-DependentServices</span></span>

<span data-ttu-id="f4399-163">Indica que esse cmdlet obtém apenas os serviços que dependem do serviço especificado.</span><span class="sxs-lookup"><span data-stu-id="f4399-163">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

<span data-ttu-id="f4399-164">Por padrão, esse cmdlet obtém todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="f4399-164">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4399-165">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4399-165">-DisplayName</span></span>

<span data-ttu-id="f4399-166">Especifica, como uma matriz de cadeia de caracteres, os nomes de exibição dos serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="f4399-166">Specifies, as a string array, the display names of services to be retrieved.</span></span>
<span data-ttu-id="f4399-167">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f4399-167">Wildcards are permitted.</span></span>
<span data-ttu-id="f4399-168">Por padrão, esse cmdlet obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-168">By default, this cmdlet gets all services on the computer.</span></span>

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

### <span data-ttu-id="f4399-169">-Excluir</span><span class="sxs-lookup"><span data-stu-id="f4399-169">-Exclude</span></span>

<span data-ttu-id="f4399-170">Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="f4399-170">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="f4399-171">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="f4399-171">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="f4399-172">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="f4399-172">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="f4399-173">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f4399-173">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f4399-174">-Incluir</span><span class="sxs-lookup"><span data-stu-id="f4399-174">-Include</span></span>

<span data-ttu-id="f4399-175">Especifica, como uma matriz de cadeia de caracteres, um serviço ou serviços que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="f4399-175">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="f4399-176">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="f4399-176">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="f4399-177">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="f4399-177">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="f4399-178">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f4399-178">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f4399-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f4399-179">-InputObject</span></span>

<span data-ttu-id="f4399-180">Especifica objetos **ServiceController** que representam os serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="f4399-180">Specifies **ServiceController** objects representing the services to be retrieved.</span></span>
<span data-ttu-id="f4399-181">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="f4399-181">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>
<span data-ttu-id="f4399-182">Você também pode canalizar um objeto de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4399-182">You can also pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="f4399-183">-Name</span><span class="sxs-lookup"><span data-stu-id="f4399-183">-Name</span></span>

<span data-ttu-id="f4399-184">Especifica os nomes de serviço dos serviços a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="f4399-184">Specifies the service names of services to be retrieved.</span></span>
<span data-ttu-id="f4399-185">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f4399-185">Wildcards are permitted.</span></span>
<span data-ttu-id="f4399-186">Por padrão, esse cmdlet obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-186">By default, this cmdlet gets all of the services on the computer.</span></span>

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

### <span data-ttu-id="f4399-187">-Obrigatórioservices</span><span class="sxs-lookup"><span data-stu-id="f4399-187">-RequiredServices</span></span>

<span data-ttu-id="f4399-188">Indica que esse cmdlet obtém apenas os serviços que esse serviço requer.</span><span class="sxs-lookup"><span data-stu-id="f4399-188">Indicates that this cmdlet gets only the services that this service requires.</span></span>

<span data-ttu-id="f4399-189">Esse parâmetro Obtém o valor da propriedade **ServicesDependedOn** do serviço.</span><span class="sxs-lookup"><span data-stu-id="f4399-189">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>
<span data-ttu-id="f4399-190">Por padrão, esse cmdlet obtém todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="f4399-190">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f4399-191">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4399-191">CommonParameters</span></span>

<span data-ttu-id="f4399-192">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4399-192">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4399-193">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4399-193">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4399-194">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f4399-194">INPUTS</span></span>

### <span data-ttu-id="f4399-195">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="f4399-195">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="f4399-196">É possível canalizar um objeto de serviço ou um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4399-196">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="f4399-197">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f4399-197">OUTPUTS</span></span>

### <span data-ttu-id="f4399-198">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="f4399-198">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f4399-199">Esse cmdlet retorna objetos que representam os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="f4399-199">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="f4399-200">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f4399-200">NOTES</span></span>

<span data-ttu-id="f4399-201">Você também pode se referir ao **Get-Service** por seu alias interno, "GSV".</span><span class="sxs-lookup"><span data-stu-id="f4399-201">You can also refer to **Get-Service** by its built-in alias, "gsv".</span></span> <span data-ttu-id="f4399-202">Para obter mais informações, consulte about_Aliases.</span><span class="sxs-lookup"><span data-stu-id="f4399-202">For more information, see about_Aliases.</span></span>

<span data-ttu-id="f4399-203">Esse cmdlet pode exibir serviços somente quando o usuário atual tem permissão para vê-los.</span><span class="sxs-lookup"><span data-stu-id="f4399-203">This cmdlet can display services only when the current user has permission to see them.</span></span>
<span data-ttu-id="f4399-204">Se esse cmdlet não exibir serviços, talvez você não tenha permissão para vê-los.</span><span class="sxs-lookup"><span data-stu-id="f4399-204">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="f4399-205">Para localizar o nome do serviço e o nome de exibição de cada serviço em seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="f4399-205">To find the service name and display name of each service on your system, type `Get-Service`.</span></span>
<span data-ttu-id="f4399-206">Os nomes de serviço são exibidos na coluna Name, e os nomes de exibição aparecem na coluna DisplayName.</span><span class="sxs-lookup"><span data-stu-id="f4399-206">The service names appear in the Name column, and the display names appear in the DisplayName column.</span></span>

<span data-ttu-id="f4399-207">Quando você classifica em ordem crescente por valor de status, os serviços "Stopped" aparecem antes dos serviços "Running".</span><span class="sxs-lookup"><span data-stu-id="f4399-207">When you sort in ascending order by status value, "Stopped" services appear before "Running" services.</span></span>
<span data-ttu-id="f4399-208">A propriedade de Status de um serviço é um valor enumerado onde os nomes de status representam valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="f4399-208">The Status property of a service is an enumerated value in which the names of the statuses represent integer values.</span></span>
<span data-ttu-id="f4399-209">A classificação baseia-se no valor do inteiro, não no nome.</span><span class="sxs-lookup"><span data-stu-id="f4399-209">The sort is based on the integer value, not the name.</span></span>
<span data-ttu-id="f4399-210">"Running" aparece antes de "Stopped" porque "Stopped" tem o valor "1" e "Running" tem o valor "4".</span><span class="sxs-lookup"><span data-stu-id="f4399-210">"Running" appears before "Stopped" because "Stopped" has a value of "1", and "Running" has a value of "4".</span></span>

## <span data-ttu-id="f4399-211">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f4399-211">RELATED LINKS</span></span>

[<span data-ttu-id="f4399-212">New-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-212">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="f4399-213">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-213">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="f4399-214">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-214">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f4399-215">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-215">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="f4399-216">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-216">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f4399-217">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-217">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f4399-218">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f4399-218">Suspend-Service</span></span>](Suspend-Service.md)
