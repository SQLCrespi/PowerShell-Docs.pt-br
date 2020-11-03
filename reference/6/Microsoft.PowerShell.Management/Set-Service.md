---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: ad1fd47291cbe8977bd2f2ada4981589714c93a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193381"
---
# <span data-ttu-id="66d65-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-103">Set-Service</span></span>

## <span data-ttu-id="66d65-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="66d65-104">SYNOPSIS</span></span>
<span data-ttu-id="66d65-105">Inicia, interrompe, suspende um serviço e altera suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="66d65-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="66d65-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66d65-106">SYNTAX</span></span>

### <span data-ttu-id="66d65-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="66d65-107">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66d65-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="66d65-108">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66d65-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66d65-109">DESCRIPTION</span></span>

<span data-ttu-id="66d65-110">O `Set-Service` cmdlet altera as propriedades de um serviço, como **status** , **Descrição** , **DisplayName** e **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="66d65-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="66d65-111">`Set-Service` pode iniciar, parar, suspender ou pausar um serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="66d65-112">Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="66d65-113">Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="66d65-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="66d65-114">EXAMPLES</span></span>

### <span data-ttu-id="66d65-115">Exemplo 1: alterar um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="66d65-115">Example 1: Change a display name</span></span>

<span data-ttu-id="66d65-116">Neste exemplo, o nome de exibição de um serviço é alterado.</span><span class="sxs-lookup"><span data-stu-id="66d65-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="66d65-117">Para exibir o nome de exibição original, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="66d65-118">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation** .</span><span class="sxs-lookup"><span data-stu-id="66d65-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="66d65-119">O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan** .</span><span class="sxs-lookup"><span data-stu-id="66d65-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="66d65-120">Exemplo 2: alterar o tipo de inicialização dos serviços</span><span class="sxs-lookup"><span data-stu-id="66d65-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="66d65-121">Este exemplo mostra como alterar o tipo de inicialização de um serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="66d65-122">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits** .</span><span class="sxs-lookup"><span data-stu-id="66d65-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="66d65-123">O parâmetro **StartupType** define o serviço como **automático** .</span><span class="sxs-lookup"><span data-stu-id="66d65-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="66d65-124">`Get-Service` usa o parâmetro **Name** para especificar o serviço **bits** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="66d65-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="66d65-125">`Select-Object` usa o parâmetro **Property** para exibir o status do serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="66d65-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="66d65-126">Exemplo 3: alterar a descrição de um serviço</span><span class="sxs-lookup"><span data-stu-id="66d65-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="66d65-127">Este exemplo altera a descrição do serviço BITS e exibe o resultado.</span><span class="sxs-lookup"><span data-stu-id="66d65-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="66d65-128">O `Get-CimInstance` cmdlet é usado porque retorna um objeto **Win32_Service** que inclui a **Descrição** do serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

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

<span data-ttu-id="66d65-129">`Get-CimInstance` envia o objeto para baixo do pipeline para `Format-List` e exibe o nome e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="66d65-130">Para fins de comparação, o comando é executado antes e depois que a descrição é atualizada.</span><span class="sxs-lookup"><span data-stu-id="66d65-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="66d65-131">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="66d65-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="66d65-132">O parâmetro **Description** especifica o texto atualizado para a descrição dos serviços.</span><span class="sxs-lookup"><span data-stu-id="66d65-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="66d65-133">Exemplo 4: iniciar um serviço</span><span class="sxs-lookup"><span data-stu-id="66d65-133">Example 4: Start a service</span></span>

<span data-ttu-id="66d65-134">Neste exemplo, um serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="66d65-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="66d65-135">`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="66d65-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="66d65-136">O parâmetro **status** usa o valor **em execução** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="66d65-137">O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="66d65-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="66d65-138">Exemplo 5: suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="66d65-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="66d65-139">Este exemplo usa o pipeline para pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="66d65-140">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="66d65-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="66d65-141">`Set-Service` usa o parâmetro **status** para definir o serviço em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="66d65-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="66d65-142">Exemplo 6: parar um serviço</span><span class="sxs-lookup"><span data-stu-id="66d65-142">Example 6: Stop a service</span></span>

<span data-ttu-id="66d65-143">Este exemplo usa uma variável para parar um serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="66d65-144">`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda** .</span><span class="sxs-lookup"><span data-stu-id="66d65-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="66d65-145">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="66d65-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="66d65-146">`Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="66d65-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="66d65-147">O parâmetro **status** define o serviço como **parado** .</span><span class="sxs-lookup"><span data-stu-id="66d65-147">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="66d65-148">Exemplo 7: parar um serviço em um sistema remoto</span><span class="sxs-lookup"><span data-stu-id="66d65-148">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="66d65-149">Este exemplo interrompe um serviço em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d65-149">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="66d65-150">Para obter mais informações, consulte [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="66d65-150">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="66d65-151">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$Cred` variável.</span><span class="sxs-lookup"><span data-stu-id="66d65-151">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="66d65-152">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="66d65-152">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="66d65-153">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="66d65-153">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="66d65-154">`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d65-154">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="66d65-155">O parâmetro **Credential** usa a `$Cred` variável para fazer logon no computador.</span><span class="sxs-lookup"><span data-stu-id="66d65-155">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="66d65-156">O **scriptblock** chama `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-156">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="66d65-157">O parâmetro **InputObject** especifica o objeto de serviço armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="66d65-157">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="66d65-158">O parâmetro **status** define o serviço como **parado** .</span><span class="sxs-lookup"><span data-stu-id="66d65-158">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="66d65-159">Exemplo 8: alterar a credencial de um serviço</span><span class="sxs-lookup"><span data-stu-id="66d65-159">Example 8: Change credential of a service</span></span>

<span data-ttu-id="66d65-160">Este exemplo altera as credenciais que são usadas para gerenciar um serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-160">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="66d65-161">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$credential` variável.</span><span class="sxs-lookup"><span data-stu-id="66d65-161">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="66d65-162">`Set-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="66d65-162">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="66d65-163">O parâmetro **Credential** usa a `$credential` variável e atualiza o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="66d65-163">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

## <span data-ttu-id="66d65-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66d65-164">PARAMETERS</span></span>

### <span data-ttu-id="66d65-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66d65-165">-Confirm</span></span>

<span data-ttu-id="66d65-166">Solicita a confirmação antes de executar `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-166">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="66d65-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="66d65-167">-Credential</span></span>

<span data-ttu-id="66d65-168">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="66d65-168">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="66d65-169">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d65-169">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="66d65-170">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="66d65-170">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="66d65-171">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="66d65-171">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="66d65-172">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="66d65-172">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="66d65-173">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="66d65-173">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d65-174">-Description</span><span class="sxs-lookup"><span data-stu-id="66d65-174">-Description</span></span>

<span data-ttu-id="66d65-175">Especifica uma nova descrição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-175">Specifies a new description for the service.</span></span>

<span data-ttu-id="66d65-176">A descrição do serviço aparece em **Gerenciamento do computador, serviços** .</span><span class="sxs-lookup"><span data-stu-id="66d65-176">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="66d65-177">A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="66d65-177">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="66d65-178">Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-178">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="66d65-179">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="66d65-179">-DisplayName</span></span>

<span data-ttu-id="66d65-180">Especifica um novo nome para exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-180">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="66d65-181">-Force</span><span class="sxs-lookup"><span data-stu-id="66d65-181">-Force</span></span>

<span data-ttu-id="66d65-182">Especifica o modo de interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-182">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="66d65-183">Esse parâmetro só funciona quando `-Status Stopped` é usado.</span><span class="sxs-lookup"><span data-stu-id="66d65-183">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="66d65-184">Se habilitada, `Set-Service` o interrompe os serviços dependentes antes que o serviço de destino seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="66d65-184">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="66d65-185">Por padrão, as exceções são geradas quando outros serviços em execução dependem do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="66d65-185">By default, exceptions are raised when other running services depend on the target service.</span></span>

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

### <span data-ttu-id="66d65-186">-InputObject</span><span class="sxs-lookup"><span data-stu-id="66d65-186">-InputObject</span></span>

<span data-ttu-id="66d65-187">Especifica um objeto **ServiceController** que representa o serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="66d65-187">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="66d65-188">Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando.</span><span class="sxs-lookup"><span data-stu-id="66d65-188">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="66d65-189">Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-189">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66d65-190">-Name</span><span class="sxs-lookup"><span data-stu-id="66d65-190">-Name</span></span>

<span data-ttu-id="66d65-191">Especifica o nome do serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="66d65-191">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="66d65-192">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="66d65-192">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="66d65-193">Você pode usar o pipeline para enviar um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-193">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="66d65-194">-PassThru</span><span class="sxs-lookup"><span data-stu-id="66d65-194">-PassThru</span></span>

<span data-ttu-id="66d65-195">Retorna um objeto **ServiceController** que representa os serviços que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="66d65-195">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="66d65-196">Por padrão, o `Set-Service` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="66d65-196">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="66d65-197">-StartupType</span><span class="sxs-lookup"><span data-stu-id="66d65-197">-StartupType</span></span>

<span data-ttu-id="66d65-198">Especifica o modo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-198">Specifies the start mode of the service.</span></span>

<span data-ttu-id="66d65-199">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="66d65-199">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="66d65-200">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="66d65-200">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="66d65-201">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="66d65-201">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="66d65-202">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="66d65-202">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="66d65-203">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="66d65-203">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="66d65-204">**Inválidos** -não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="66d65-204">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="66d65-205">O cmdlet não retorna um erro, mas o StartupType do serviço não é alterado.</span><span class="sxs-lookup"><span data-stu-id="66d65-205">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="66d65-206">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="66d65-206">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d65-207">-Status</span><span class="sxs-lookup"><span data-stu-id="66d65-207">-Status</span></span>

<span data-ttu-id="66d65-208">Especifica o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-208">Specifies the status for the service.</span></span>

<span data-ttu-id="66d65-209">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="66d65-209">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="66d65-210">Em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="66d65-210">**Paused** .</span></span> <span data-ttu-id="66d65-211">Suspende o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-211">Suspends the service.</span></span>
- <span data-ttu-id="66d65-212">**Em execução** .</span><span class="sxs-lookup"><span data-stu-id="66d65-212">**Running** .</span></span> <span data-ttu-id="66d65-213">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-213">Starts the service.</span></span>
- <span data-ttu-id="66d65-214">**Parado** .</span><span class="sxs-lookup"><span data-stu-id="66d65-214">**Stopped** .</span></span> <span data-ttu-id="66d65-215">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="66d65-215">Stops the service.</span></span>

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

### <span data-ttu-id="66d65-216">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66d65-216">-WhatIf</span></span>

<span data-ttu-id="66d65-217">Mostra o que aconteceria se `Set-Service` for executado.</span><span class="sxs-lookup"><span data-stu-id="66d65-217">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="66d65-218">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="66d65-218">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="66d65-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66d65-219">CommonParameters</span></span>

<span data-ttu-id="66d65-220">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66d65-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66d65-221">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="66d65-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66d65-222">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="66d65-222">INPUTS</span></span>

### <span data-ttu-id="66d65-223">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="66d65-223">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="66d65-224">Você pode usar o pipeline para enviar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-224">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="66d65-225">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="66d65-225">OUTPUTS</span></span>

### <span data-ttu-id="66d65-226">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="66d65-226">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="66d65-227">Por padrão, o `Set-Service` não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="66d65-227">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="66d65-228">Use o parâmetro **PassThru** para gerar um objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="66d65-228">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="66d65-229">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="66d65-229">NOTES</span></span>

<span data-ttu-id="66d65-230">`Set-Service` requer permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="66d65-230">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="66d65-231">Use a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="66d65-231">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="66d65-232">`Set-Service` Só é possível controlar os serviços quando o usuário atual tem permissões para gerenciar serviços.</span><span class="sxs-lookup"><span data-stu-id="66d65-232">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="66d65-233">Se um comando não funcionar corretamente, talvez você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="66d65-233">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="66d65-234">Para localizar o nome do serviço ou nome de exibição do serviço, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="66d65-234">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="66d65-235">Os nomes de serviço estão na coluna **nome** e os nomes de exibição estão na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="66d65-235">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="66d65-236">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="66d65-236">RELATED LINKS</span></span>

[<span data-ttu-id="66d65-237">Get-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-237">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="66d65-238">New-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-238">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="66d65-239">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-239">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="66d65-240">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-240">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="66d65-241">Start-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-241">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="66d65-242">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-242">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="66d65-243">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-243">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="66d65-244">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="66d65-244">Remove-Service</span></span>](Remove-Service.md)
