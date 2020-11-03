---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: d58d26a93e9b785bcba425537ea570feeffa1606
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192972"
---
# <span data-ttu-id="f6d45-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-103">Set-Service</span></span>

## <span data-ttu-id="f6d45-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f6d45-104">SYNOPSIS</span></span>
<span data-ttu-id="f6d45-105">Inicia, interrompe, suspende um serviço e altera suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="f6d45-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="f6d45-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f6d45-106">SYNTAX</span></span>

### <span data-ttu-id="f6d45-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="f6d45-107">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f6d45-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="f6d45-108">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f6d45-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f6d45-109">DESCRIPTION</span></span>

<span data-ttu-id="f6d45-110">O `Set-Service` cmdlet altera as propriedades de um serviço, como **status** , **Descrição** , **DisplayName** e **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="f6d45-111">`Set-Service` pode iniciar, parar, suspender ou pausar um serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="f6d45-112">Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="f6d45-113">Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="f6d45-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f6d45-114">EXAMPLES</span></span>

### <span data-ttu-id="f6d45-115">Exemplo 1: alterar um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="f6d45-115">Example 1: Change a display name</span></span>

<span data-ttu-id="f6d45-116">Neste exemplo, o nome de exibição de um serviço é alterado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="f6d45-117">Para exibir o nome de exibição original, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="f6d45-118">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="f6d45-119">O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="f6d45-120">Exemplo 2: alterar o tipo de inicialização dos serviços</span><span class="sxs-lookup"><span data-stu-id="f6d45-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="f6d45-121">Este exemplo mostra como alterar o tipo de inicialização de um serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="f6d45-122">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="f6d45-123">O parâmetro **StartupType** define o serviço como **automático** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="f6d45-124">`Get-Service` usa o parâmetro **Name** para especificar o serviço **bits** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6d45-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="f6d45-125">`Select-Object` usa o parâmetro **Property** para exibir o status do serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="f6d45-126">Exemplo 3: alterar a descrição de um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="f6d45-127">Este exemplo altera a descrição do serviço BITS e exibe o resultado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="f6d45-128">O `Get-CimInstance` cmdlet é usado porque retorna um objeto **Win32_Service** que inclui a **Descrição** do serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

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

<span data-ttu-id="f6d45-129">`Get-CimInstance` envia o objeto para baixo do pipeline para `Format-List` e exibe o nome e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="f6d45-130">Para fins de comparação, o comando é executado antes e depois que a descrição é atualizada.</span><span class="sxs-lookup"><span data-stu-id="f6d45-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="f6d45-131">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="f6d45-132">O parâmetro **Description** especifica o texto atualizado para a descrição dos serviços.</span><span class="sxs-lookup"><span data-stu-id="f6d45-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="f6d45-133">Exemplo 4: iniciar um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-133">Example 4: Start a service</span></span>

<span data-ttu-id="f6d45-134">Neste exemplo, um serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="f6d45-135">`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="f6d45-136">O parâmetro **status** usa o valor **em execução** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="f6d45-137">O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="f6d45-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="f6d45-138">Exemplo 5: suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="f6d45-139">Este exemplo usa o pipeline para pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="f6d45-140">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6d45-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="f6d45-141">`Set-Service` usa o parâmetro **status** para definir o serviço em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="f6d45-142">Exemplo 6: parar um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-142">Example 6: Stop a service</span></span>

<span data-ttu-id="f6d45-143">Este exemplo usa uma variável para parar um serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="f6d45-144">`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="f6d45-145">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="f6d45-146">`Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="f6d45-147">O parâmetro **status** define o serviço como **parado** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-147">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="f6d45-148">Exemplo 7: parar um serviço em um sistema remoto</span><span class="sxs-lookup"><span data-stu-id="f6d45-148">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="f6d45-149">Este exemplo interrompe um serviço em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f6d45-149">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="f6d45-150">Para obter mais informações, consulte [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="f6d45-150">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="f6d45-151">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$Cred` variável.</span><span class="sxs-lookup"><span data-stu-id="f6d45-151">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="f6d45-152">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-152">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="f6d45-153">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-153">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="f6d45-154">`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f6d45-154">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="f6d45-155">O parâmetro **Credential** usa a `$Cred` variável para fazer logon no computador.</span><span class="sxs-lookup"><span data-stu-id="f6d45-155">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="f6d45-156">O **scriptblock** chama `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-156">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="f6d45-157">O parâmetro **InputObject** especifica o objeto de serviço armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-157">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="f6d45-158">O parâmetro **status** define o serviço como **parado** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-158">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="f6d45-159">Exemplo 8: alterar a credencial de um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-159">Example 8: Change credential of a service</span></span>

<span data-ttu-id="f6d45-160">Este exemplo altera as credenciais que são usadas para gerenciar um serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-160">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="f6d45-161">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$credential` variável.</span><span class="sxs-lookup"><span data-stu-id="f6d45-161">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="f6d45-162">`Set-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-162">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="f6d45-163">O parâmetro **Credential** usa a `$credential` variável e atualiza o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-163">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

### <span data-ttu-id="f6d45-164">Exemplo 9: alterar o SecurityDescriptor de um serviço</span><span class="sxs-lookup"><span data-stu-id="f6d45-164">Example 9: Change the SecurityDescriptor of a service</span></span>

<span data-ttu-id="f6d45-165">Este exemplo altera o **SecurityDescriptor** de um serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-165">This example changes a service's **SecurityDescriptor** .</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

<span data-ttu-id="f6d45-166">O **SecurityDescriptor** é armazenado na `$SDDL` variável.</span><span class="sxs-lookup"><span data-stu-id="f6d45-166">The **SecurityDescriptor** is stored in the `$SDDL` variable.</span></span> <span data-ttu-id="f6d45-167">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-167">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="f6d45-168">O parâmetro **SecurityDescriptorSddl** usa `$SDDL` para alterar o **SecurityDescriptor** para o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-168">The **SecurityDescriptorSddl** parameter uses `$SDDL` to change the **SecurityDescriptor** for the **BITS** service.</span></span>

## <span data-ttu-id="f6d45-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f6d45-169">PARAMETERS</span></span>

### <span data-ttu-id="f6d45-170">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f6d45-170">-Confirm</span></span>

<span data-ttu-id="f6d45-171">Solicita a confirmação antes de executar `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-171">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="f6d45-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="f6d45-172">-Credential</span></span>

<span data-ttu-id="f6d45-173">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="f6d45-173">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="f6d45-174">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6d45-174">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f6d45-175">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="f6d45-175">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="f6d45-176">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="f6d45-176">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f6d45-177">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="f6d45-177">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="f6d45-178">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="f6d45-178">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="f6d45-179">-Description</span><span class="sxs-lookup"><span data-stu-id="f6d45-179">-Description</span></span>

<span data-ttu-id="f6d45-180">Especifica uma nova descrição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-180">Specifies a new description for the service.</span></span>

<span data-ttu-id="f6d45-181">A descrição do serviço aparece em **Gerenciamento do computador, serviços** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-181">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="f6d45-182">A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-182">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="f6d45-183">Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-183">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="f6d45-184">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f6d45-184">-DisplayName</span></span>

<span data-ttu-id="f6d45-185">Especifica um novo nome para exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-185">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="f6d45-186">-Force</span><span class="sxs-lookup"><span data-stu-id="f6d45-186">-Force</span></span>

<span data-ttu-id="f6d45-187">Especifica o modo de interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-187">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="f6d45-188">Esse parâmetro só funciona quando `-Status Stopped` é usado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-188">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="f6d45-189">Se habilitada, `Set-Service` o interrompe os serviços dependentes antes que o serviço de destino seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="f6d45-189">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="f6d45-190">Por padrão, as exceções são geradas quando outros serviços em execução dependem do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="f6d45-190">By default, exceptions are raised when other running services depend on the target service.</span></span>

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

### <span data-ttu-id="f6d45-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f6d45-191">-InputObject</span></span>

<span data-ttu-id="f6d45-192">Especifica um objeto **ServiceController** que representa o serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-192">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="f6d45-193">Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando.</span><span class="sxs-lookup"><span data-stu-id="f6d45-193">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="f6d45-194">Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-194">You can use the pipeline to send a service object to `Set-Service`.</span></span>

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

### <span data-ttu-id="f6d45-195">-Name</span><span class="sxs-lookup"><span data-stu-id="f6d45-195">-Name</span></span>

<span data-ttu-id="f6d45-196">Especifica o nome do serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-196">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="f6d45-197">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f6d45-197">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="f6d45-198">Você pode usar o pipeline para enviar um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-198">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="f6d45-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f6d45-199">-PassThru</span></span>

<span data-ttu-id="f6d45-200">Retorna um objeto **ServiceController** que representa os serviços que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="f6d45-200">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="f6d45-201">Por padrão, o `Set-Service` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f6d45-201">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="f6d45-202">-StartupType</span><span class="sxs-lookup"><span data-stu-id="f6d45-202">-StartupType</span></span>

<span data-ttu-id="f6d45-203">Especifica o modo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-203">Specifies the start mode of the service.</span></span>

<span data-ttu-id="f6d45-204">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f6d45-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f6d45-205">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="f6d45-205">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="f6d45-206">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="f6d45-206">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="f6d45-207">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="f6d45-207">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="f6d45-208">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f6d45-208">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="f6d45-209">**Inválidos** -não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="f6d45-209">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="f6d45-210">O cmdlet não retorna um erro, mas o StartupType do serviço não é alterado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-210">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="f6d45-211">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f6d45-211">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6d45-212">-Status</span><span class="sxs-lookup"><span data-stu-id="f6d45-212">-Status</span></span>

<span data-ttu-id="f6d45-213">Especifica o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-213">Specifies the status for the service.</span></span>

<span data-ttu-id="f6d45-214">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f6d45-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f6d45-215">Em **pausa** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-215">**Paused** .</span></span> <span data-ttu-id="f6d45-216">Suspende o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-216">Suspends the service.</span></span>
- <span data-ttu-id="f6d45-217">**Em execução** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-217">**Running** .</span></span> <span data-ttu-id="f6d45-218">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-218">Starts the service.</span></span>
- <span data-ttu-id="f6d45-219">**Parado** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-219">**Stopped** .</span></span> <span data-ttu-id="f6d45-220">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="f6d45-220">Stops the service.</span></span>

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

### <span data-ttu-id="f6d45-221">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="f6d45-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="f6d45-222">Especifica o **SecurityDescriptor** para o serviço no formato **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-222">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6d45-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f6d45-223">-WhatIf</span></span>

<span data-ttu-id="f6d45-224">Mostra o que aconteceria se `Set-Service` for executado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-224">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="f6d45-225">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f6d45-225">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="f6d45-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f6d45-226">CommonParameters</span></span>

<span data-ttu-id="f6d45-227">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f6d45-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6d45-228">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f6d45-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6d45-229">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f6d45-229">INPUTS</span></span>

### <span data-ttu-id="f6d45-230">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="f6d45-230">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="f6d45-231">Você pode usar o pipeline para enviar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-231">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="f6d45-232">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f6d45-232">OUTPUTS</span></span>

### <span data-ttu-id="f6d45-233">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="f6d45-233">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f6d45-234">Por padrão, o `Set-Service` não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="f6d45-234">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="f6d45-235">Use o parâmetro **PassThru** para gerar um objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-235">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="f6d45-236">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f6d45-236">NOTES</span></span>

<span data-ttu-id="f6d45-237">`Set-Service` requer permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="f6d45-237">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="f6d45-238">Use a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-238">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="f6d45-239">`Set-Service` Só é possível controlar os serviços quando o usuário atual tem permissões para gerenciar serviços.</span><span class="sxs-lookup"><span data-stu-id="f6d45-239">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="f6d45-240">Se um comando não funcionar corretamente, talvez você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6d45-240">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="f6d45-241">Para localizar o nome do serviço ou nome de exibição do serviço, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="f6d45-241">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="f6d45-242">Os nomes de serviço estão na coluna **nome** e os nomes de exibição estão na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="f6d45-242">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="f6d45-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f6d45-243">RELATED LINKS</span></span>

[<span data-ttu-id="f6d45-244">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-244">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="f6d45-245">New-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-245">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="f6d45-246">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-246">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="f6d45-247">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-247">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f6d45-248">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-248">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f6d45-249">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-249">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f6d45-250">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-250">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="f6d45-251">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="f6d45-251">Remove-Service</span></span>](Remove-Service.md)
