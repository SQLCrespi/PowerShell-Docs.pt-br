---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193920"
---
# <span data-ttu-id="de81c-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-103">Set-Service</span></span>

## <span data-ttu-id="de81c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="de81c-104">SYNOPSIS</span></span>
<span data-ttu-id="de81c-105">Inicia, interrompe, suspende um serviço e altera suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="de81c-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="de81c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de81c-106">SYNTAX</span></span>

### <span data-ttu-id="de81c-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="de81c-107">Name (Default)</span></span>

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="de81c-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="de81c-108">InputObject</span></span>

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="de81c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de81c-109">DESCRIPTION</span></span>

<span data-ttu-id="de81c-110">O `Set-Service` cmdlet altera as propriedades de um serviço, como **status** , **Descrição** , **DisplayName** e **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="de81c-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="de81c-111">`Set-Service` pode iniciar, parar, suspender ou pausar um serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="de81c-112">Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="de81c-113">Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="de81c-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="de81c-114">EXAMPLES</span></span>

### <span data-ttu-id="de81c-115">Exemplo 1: alterar um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="de81c-115">Example 1: Change a display name</span></span>

<span data-ttu-id="de81c-116">Neste exemplo, o nome de exibição de um serviço é alterado.</span><span class="sxs-lookup"><span data-stu-id="de81c-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="de81c-117">Para exibir o nome de exibição original, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="de81c-118">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation** .</span><span class="sxs-lookup"><span data-stu-id="de81c-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="de81c-119">O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan** .</span><span class="sxs-lookup"><span data-stu-id="de81c-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="de81c-120">Exemplo 2: alterar o tipo de inicialização dos serviços</span><span class="sxs-lookup"><span data-stu-id="de81c-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="de81c-121">Este exemplo mostra como alterar o tipo de inicialização de um serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="de81c-122">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits** .</span><span class="sxs-lookup"><span data-stu-id="de81c-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="de81c-123">O parâmetro **StartupType** define o serviço como **automático** .</span><span class="sxs-lookup"><span data-stu-id="de81c-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="de81c-124">`Get-Service` usa o parâmetro **Name** para especificar o serviço **bits** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="de81c-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="de81c-125">`Select-Object` usa o parâmetro **Property** para exibir o status do serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="de81c-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="de81c-126">Exemplo 3: alterar a descrição de um serviço</span><span class="sxs-lookup"><span data-stu-id="de81c-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="de81c-127">Este exemplo altera a descrição do serviço BITS e exibe o resultado.</span><span class="sxs-lookup"><span data-stu-id="de81c-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="de81c-128">O `Get-CimInstance` cmdlet é usado porque retorna um objeto **Win32_Service** que inclui a **Descrição** do serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="de81c-129">`Get-CimInstance` envia o objeto para baixo do pipeline para `Format-List` e exibe o nome e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="de81c-130">Para fins de comparação, o comando é executado antes e depois que a descrição é atualizada.</span><span class="sxs-lookup"><span data-stu-id="de81c-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="de81c-131">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="de81c-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="de81c-132">O parâmetro **Description** especifica o texto atualizado para a descrição dos serviços.</span><span class="sxs-lookup"><span data-stu-id="de81c-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="de81c-133">Exemplo 4: iniciar um serviço</span><span class="sxs-lookup"><span data-stu-id="de81c-133">Example 4: Start a service</span></span>

<span data-ttu-id="de81c-134">Neste exemplo, um serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="de81c-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="de81c-135">`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de81c-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="de81c-136">O parâmetro **status** usa o valor **em execução** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="de81c-137">O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="de81c-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="de81c-138">Exemplo 5: suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="de81c-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="de81c-139">Este exemplo usa o pipeline para pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="de81c-140">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="de81c-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="de81c-141">`Set-Service` usa o parâmetro **status** para definir o serviço em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="de81c-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="de81c-142">Exemplo 6: parar um serviço</span><span class="sxs-lookup"><span data-stu-id="de81c-142">Example 6: Stop a service</span></span>

<span data-ttu-id="de81c-143">Este exemplo usa uma variável para parar um serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="de81c-144">`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda** .</span><span class="sxs-lookup"><span data-stu-id="de81c-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="de81c-145">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="de81c-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="de81c-146">`Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="de81c-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="de81c-147">O parâmetro **status** define o serviço como **parado** .</span><span class="sxs-lookup"><span data-stu-id="de81c-147">The **Status** parameter sets the service to **Stopped** .</span></span>

## <span data-ttu-id="de81c-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de81c-148">PARAMETERS</span></span>

### <span data-ttu-id="de81c-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="de81c-149">-ComputerName</span></span>

<span data-ttu-id="de81c-150">Especifica um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="de81c-150">Specifies one or more computers.</span></span> <span data-ttu-id="de81c-151">Para computadores remotos, digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="de81c-151">For remote computers, type the NetBIOS name, an IP address, or a fully qualified domain name.</span></span> <span data-ttu-id="de81c-152">Se o parâmetro **ComputerName** não for especificado, o comando será executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="de81c-152">If the **ComputerName** parameter isn't specified, the command runs on the local computer.</span></span>

<span data-ttu-id="de81c-153">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de81c-153">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="de81c-154">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="de81c-154">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="de81c-155">-Confirm</span></span>

<span data-ttu-id="de81c-156">Solicita a confirmação antes de executar `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-156">Prompts you for confirmation before running `Set-Service`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-157">-Description</span><span class="sxs-lookup"><span data-stu-id="de81c-157">-Description</span></span>

<span data-ttu-id="de81c-158">Especifica uma nova descrição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-158">Specifies a new description for the service.</span></span>

<span data-ttu-id="de81c-159">A descrição do serviço aparece em **Gerenciamento do computador, serviços** .</span><span class="sxs-lookup"><span data-stu-id="de81c-159">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="de81c-160">A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="de81c-160">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="de81c-161">Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-161">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-162">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="de81c-162">-DisplayName</span></span>

<span data-ttu-id="de81c-163">Especifica um novo nome para exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-163">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="de81c-164">-InputObject</span></span>

<span data-ttu-id="de81c-165">Especifica um objeto **ServiceController** que representa o serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="de81c-165">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="de81c-166">Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando.</span><span class="sxs-lookup"><span data-stu-id="de81c-166">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="de81c-167">Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-167">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-168">-Name</span><span class="sxs-lookup"><span data-stu-id="de81c-168">-Name</span></span>

<span data-ttu-id="de81c-169">Especifica o nome do serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="de81c-169">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="de81c-170">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="de81c-170">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="de81c-171">Você pode usar o pipeline para enviar um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-171">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-172">-PassThru</span><span class="sxs-lookup"><span data-stu-id="de81c-172">-PassThru</span></span>

<span data-ttu-id="de81c-173">Retorna um objeto **ServiceController** que representa os serviços que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="de81c-173">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="de81c-174">Por padrão, o `Set-Service` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="de81c-174">By default, `Set-Service` doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-175">-StartupType</span><span class="sxs-lookup"><span data-stu-id="de81c-175">-StartupType</span></span>

<span data-ttu-id="de81c-176">Define o tipo de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-176">Sets the startup type of the service.</span></span> <span data-ttu-id="de81c-177">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="de81c-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de81c-178">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="de81c-178">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="de81c-179">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="de81c-179">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="de81c-180">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="de81c-180">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="de81c-181">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="de81c-181">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="de81c-182">**Inicialização** -indica que o serviço é um driver de dispositivo iniciado pelo carregador do sistema.</span><span class="sxs-lookup"><span data-stu-id="de81c-182">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="de81c-183">Esse valor é válido somente para drivers de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de81c-183">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="de81c-184">**Sistema** -indica que o serviço é um driver de dispositivo iniciado pela função ' IOInitSystem () '.</span><span class="sxs-lookup"><span data-stu-id="de81c-184">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="de81c-185">Esse valor é válido somente para drivers de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de81c-185">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="de81c-186">O valor padrão é **automático** .</span><span class="sxs-lookup"><span data-stu-id="de81c-186">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-187">-Status</span><span class="sxs-lookup"><span data-stu-id="de81c-187">-Status</span></span>

<span data-ttu-id="de81c-188">Especifica o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-188">Specifies the status for the service.</span></span>

<span data-ttu-id="de81c-189">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="de81c-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="de81c-190">Em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="de81c-190">**Paused** .</span></span> <span data-ttu-id="de81c-191">Suspende o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-191">Suspends the service.</span></span>
- <span data-ttu-id="de81c-192">**Em execução** .</span><span class="sxs-lookup"><span data-stu-id="de81c-192">**Running** .</span></span> <span data-ttu-id="de81c-193">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-193">Starts the service.</span></span>
- <span data-ttu-id="de81c-194">**Parado** .</span><span class="sxs-lookup"><span data-stu-id="de81c-194">**Stopped** .</span></span> <span data-ttu-id="de81c-195">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="de81c-195">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="de81c-196">-WhatIf</span></span>

<span data-ttu-id="de81c-197">Mostra o que aconteceria se `Set-Service` for executado.</span><span class="sxs-lookup"><span data-stu-id="de81c-197">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="de81c-198">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="de81c-198">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de81c-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="de81c-199">CommonParameters</span></span>

<span data-ttu-id="de81c-200">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de81c-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de81c-201">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de81c-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de81c-202">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="de81c-202">INPUTS</span></span>

### <span data-ttu-id="de81c-203">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="de81c-203">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="de81c-204">Você pode usar o pipeline para enviar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-204">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="de81c-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="de81c-205">OUTPUTS</span></span>

### <span data-ttu-id="de81c-206">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="de81c-206">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="de81c-207">Por padrão, o `Set-Service` não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="de81c-207">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="de81c-208">Use o parâmetro **PassThru** para gerar um objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="de81c-208">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="de81c-209">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="de81c-209">NOTES</span></span>

<span data-ttu-id="de81c-210">`Set-Service` requer permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="de81c-210">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="de81c-211">Use a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="de81c-211">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="de81c-212">`Set-Service` Só é possível controlar os serviços quando o usuário atual tem permissões para gerenciar serviços.</span><span class="sxs-lookup"><span data-stu-id="de81c-212">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="de81c-213">Se um comando não funcionar corretamente, talvez você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="de81c-213">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="de81c-214">Para localizar o nome do serviço ou nome de exibição do serviço, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="de81c-214">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="de81c-215">Os nomes de serviço estão na coluna **nome** e os nomes de exibição estão na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="de81c-215">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="de81c-216">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="de81c-216">RELATED LINKS</span></span>

[<span data-ttu-id="de81c-217">Get-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-217">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="de81c-218">New-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-218">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="de81c-219">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-219">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="de81c-220">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-220">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="de81c-221">Start-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-221">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="de81c-222">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-222">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="de81c-223">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="de81c-223">Suspend-Service</span></span>](Suspend-Service.md)
