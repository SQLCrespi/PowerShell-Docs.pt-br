---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: 0c6cac03f1acbda35069780f0c53eaf6685813ff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597641"
---
# <span data-ttu-id="81721-102">Set-Service</span><span class="sxs-lookup"><span data-stu-id="81721-102">Set-Service</span></span>

## <span data-ttu-id="81721-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="81721-103">SYNOPSIS</span></span>
<span data-ttu-id="81721-104">Inicia, interrompe, suspende um serviço e altera suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="81721-104">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="81721-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="81721-105">SYNTAX</span></span>

### <span data-ttu-id="81721-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="81721-106">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="81721-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="81721-107">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="81721-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="81721-108">DESCRIPTION</span></span>

<span data-ttu-id="81721-109">O `Set-Service` cmdlet altera as propriedades de um serviço, como **status**, **Descrição**, **DisplayName** e **StartupType**.</span><span class="sxs-lookup"><span data-stu-id="81721-109">The `Set-Service` cmdlet changes the properties of a service such as the **Status**, **Description**, **DisplayName**, and **StartupType**.</span></span> <span data-ttu-id="81721-110">`Set-Service` pode iniciar, parar, suspender ou pausar um serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-110">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="81721-111">Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-111">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="81721-112">Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-112">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="81721-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="81721-113">EXAMPLES</span></span>

### <span data-ttu-id="81721-114">Exemplo 1: alterar um nome de exibição</span><span class="sxs-lookup"><span data-stu-id="81721-114">Example 1: Change a display name</span></span>

<span data-ttu-id="81721-115">Neste exemplo, o nome de exibição de um serviço é alterado.</span><span class="sxs-lookup"><span data-stu-id="81721-115">In this example, a service's display name is changed.</span></span> <span data-ttu-id="81721-116">Para exibir o nome de exibição original, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-116">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="81721-117">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation**.</span><span class="sxs-lookup"><span data-stu-id="81721-117">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation**.</span></span> <span data-ttu-id="81721-118">O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan**.</span><span class="sxs-lookup"><span data-stu-id="81721-118">The **DisplayName** parameter specifies the new display name, **LanMan Workstation**.</span></span>

### <span data-ttu-id="81721-119">Exemplo 2: alterar o tipo de inicialização dos serviços</span><span class="sxs-lookup"><span data-stu-id="81721-119">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="81721-120">Este exemplo mostra como alterar o tipo de inicialização de um serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-120">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="81721-121">`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits**.</span><span class="sxs-lookup"><span data-stu-id="81721-121">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS**.</span></span> <span data-ttu-id="81721-122">O parâmetro **StartupType** define o serviço como **automático**.</span><span class="sxs-lookup"><span data-stu-id="81721-122">The **StartupType** parameter sets the service to **Automatic**.</span></span>

<span data-ttu-id="81721-123">`Get-Service` usa o parâmetro **Name** para especificar o serviço **bits** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="81721-123">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="81721-124">`Select-Object` usa o parâmetro **Property** para exibir o status do serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="81721-124">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="81721-125">Exemplo 3: alterar a descrição de um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-125">Example 3: Change the description of a service</span></span>

<span data-ttu-id="81721-126">Este exemplo altera a descrição do serviço BITS e exibe o resultado.</span><span class="sxs-lookup"><span data-stu-id="81721-126">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="81721-127">O `Get-CimInstance` cmdlet é usado porque retorna um objeto **Win32_Service** que inclui a **Descrição** do serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-127">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description**.</span></span>

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

<span data-ttu-id="81721-128">`Get-CimInstance` envia o objeto para baixo do pipeline para `Format-List` e exibe o nome e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-128">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="81721-129">Para fins de comparação, o comando é executado antes e depois que a descrição é atualizada.</span><span class="sxs-lookup"><span data-stu-id="81721-129">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="81721-130">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="81721-130">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="81721-131">O parâmetro **Description** especifica o texto atualizado para a descrição dos serviços.</span><span class="sxs-lookup"><span data-stu-id="81721-131">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="81721-132">Exemplo 4: iniciar um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-132">Example 4: Start a service</span></span>

<span data-ttu-id="81721-133">Neste exemplo, um serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="81721-133">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="81721-134">`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="81721-134">`Set-Service` uses the **Name** parameter to specify the service, **WinRM**.</span></span> <span data-ttu-id="81721-135">O parâmetro **status** usa o valor **em execução** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-135">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="81721-136">O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="81721-136">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="81721-137">Exemplo 5: suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-137">Example 5: Suspend a service</span></span>

<span data-ttu-id="81721-138">Este exemplo usa o pipeline para pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-138">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="81721-139">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="81721-139">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="81721-140">`Set-Service` usa o parâmetro **status** para definir o serviço em **pausa**.</span><span class="sxs-lookup"><span data-stu-id="81721-140">`Set-Service` uses the **Status** parameter to set the service to **Paused**.</span></span>

### <span data-ttu-id="81721-141">Exemplo 6: parar um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-141">Example 6: Stop a service</span></span>

<span data-ttu-id="81721-142">Este exemplo usa uma variável para parar um serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-142">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="81721-143">`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda**.</span><span class="sxs-lookup"><span data-stu-id="81721-143">`Get-Service` uses the **Name** parameter to specify the service, **Schedule**.</span></span> <span data-ttu-id="81721-144">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="81721-144">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="81721-145">`Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="81721-145">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="81721-146">O parâmetro **status** define o serviço como **parado**.</span><span class="sxs-lookup"><span data-stu-id="81721-146">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="81721-147">Exemplo 7: parar um serviço em um sistema remoto</span><span class="sxs-lookup"><span data-stu-id="81721-147">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="81721-148">Este exemplo interrompe um serviço em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="81721-148">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="81721-149">Para obter mais informações, consulte [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="81721-149">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="81721-150">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$Cred` variável.</span><span class="sxs-lookup"><span data-stu-id="81721-150">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="81721-151">`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="81721-151">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="81721-152">O objeto é armazenado na variável, `$S` .</span><span class="sxs-lookup"><span data-stu-id="81721-152">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="81721-153">`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="81721-153">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="81721-154">O parâmetro **Credential** usa a `$Cred` variável para fazer logon no computador.</span><span class="sxs-lookup"><span data-stu-id="81721-154">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="81721-155">O **scriptblock** chama `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-155">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="81721-156">O parâmetro **InputObject** especifica o objeto de serviço armazenado `$S` .</span><span class="sxs-lookup"><span data-stu-id="81721-156">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="81721-157">O parâmetro **status** define o serviço como **parado**.</span><span class="sxs-lookup"><span data-stu-id="81721-157">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="81721-158">Exemplo 8: alterar a credencial de um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-158">Example 8: Change credential of a service</span></span>

<span data-ttu-id="81721-159">Este exemplo altera as credenciais que são usadas para gerenciar um serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-159">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="81721-160">`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$credential` variável.</span><span class="sxs-lookup"><span data-stu-id="81721-160">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="81721-161">`Set-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="81721-161">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="81721-162">O parâmetro **Credential** usa a `$credential` variável e atualiza o serviço de **agendamento** .</span><span class="sxs-lookup"><span data-stu-id="81721-162">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

### <span data-ttu-id="81721-163">Exemplo 9: alterar o SecurityDescriptor de um serviço</span><span class="sxs-lookup"><span data-stu-id="81721-163">Example 9: Change the SecurityDescriptor of a service</span></span>

<span data-ttu-id="81721-164">Este exemplo altera o **SecurityDescriptor** de um serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-164">This example changes a service's **SecurityDescriptor**.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

<span data-ttu-id="81721-165">O **SecurityDescriptor** é armazenado na `$SDDL` variável.</span><span class="sxs-lookup"><span data-stu-id="81721-165">The **SecurityDescriptor** is stored in the `$SDDL` variable.</span></span> <span data-ttu-id="81721-166">`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="81721-166">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="81721-167">O parâmetro **SecurityDescriptorSddl** usa `$SDDL` para alterar o **SecurityDescriptor** para o serviço **bits** .</span><span class="sxs-lookup"><span data-stu-id="81721-167">The **SecurityDescriptorSddl** parameter uses `$SDDL` to change the **SecurityDescriptor** for the **BITS** service.</span></span>

## <span data-ttu-id="81721-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="81721-168">PARAMETERS</span></span>

### <span data-ttu-id="81721-169">-Confirm</span><span class="sxs-lookup"><span data-stu-id="81721-169">-Confirm</span></span>

<span data-ttu-id="81721-170">Solicita a confirmação antes de executar `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-170">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="81721-171">-Credential</span><span class="sxs-lookup"><span data-stu-id="81721-171">-Credential</span></span>

<span data-ttu-id="81721-172">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="81721-172">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="81721-173">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="81721-173">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="81721-174">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="81721-174">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="81721-175">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="81721-175">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="81721-176">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="81721-176">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="81721-177">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="81721-177">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="81721-178">-Description</span><span class="sxs-lookup"><span data-stu-id="81721-178">-Description</span></span>

<span data-ttu-id="81721-179">Especifica uma nova descrição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-179">Specifies a new description for the service.</span></span>

<span data-ttu-id="81721-180">A descrição do serviço aparece em **Gerenciamento do computador, serviços**.</span><span class="sxs-lookup"><span data-stu-id="81721-180">The service description appears in **Computer Management, Services**.</span></span> <span data-ttu-id="81721-181">A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="81721-181">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="81721-182">Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-182">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="81721-183">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="81721-183">-DisplayName</span></span>

<span data-ttu-id="81721-184">Especifica um novo nome para exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-184">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="81721-185">-Force</span><span class="sxs-lookup"><span data-stu-id="81721-185">-Force</span></span>

<span data-ttu-id="81721-186">Especifica o modo de interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-186">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="81721-187">Esse parâmetro só funciona quando `-Status Stopped` é usado.</span><span class="sxs-lookup"><span data-stu-id="81721-187">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="81721-188">Se habilitada, `Set-Service` o interrompe os serviços dependentes antes que o serviço de destino seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="81721-188">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="81721-189">Por padrão, as exceções são geradas quando outros serviços em execução dependem do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="81721-189">By default, exceptions are raised when other running services depend on the target service.</span></span>

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

### <span data-ttu-id="81721-190">-InputObject</span><span class="sxs-lookup"><span data-stu-id="81721-190">-InputObject</span></span>

<span data-ttu-id="81721-191">Especifica um objeto **ServiceController** que representa o serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="81721-191">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="81721-192">Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando.</span><span class="sxs-lookup"><span data-stu-id="81721-192">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="81721-193">Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-193">You can use the pipeline to send a service object to `Set-Service`.</span></span>

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

### <span data-ttu-id="81721-194">-Name</span><span class="sxs-lookup"><span data-stu-id="81721-194">-Name</span></span>

<span data-ttu-id="81721-195">Especifica o nome do serviço a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="81721-195">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="81721-196">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="81721-196">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="81721-197">Você pode usar o pipeline para enviar um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-197">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="81721-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="81721-198">-PassThru</span></span>

<span data-ttu-id="81721-199">Retorna um objeto **ServiceController** que representa os serviços que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="81721-199">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="81721-200">Por padrão, o `Set-Service` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="81721-200">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="81721-201">-StartupType</span><span class="sxs-lookup"><span data-stu-id="81721-201">-StartupType</span></span>

<span data-ttu-id="81721-202">Especifica o modo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-202">Specifies the start mode of the service.</span></span>

<span data-ttu-id="81721-203">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="81721-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="81721-204">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="81721-204">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="81721-205">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="81721-205">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="81721-206">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="81721-206">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="81721-207">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81721-207">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="81721-208">**Inválidos** -não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="81721-208">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="81721-209">O cmdlet não retorna um erro, mas o StartupType do serviço não é alterado.</span><span class="sxs-lookup"><span data-stu-id="81721-209">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="81721-210">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81721-210">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

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

### <span data-ttu-id="81721-211">-Status</span><span class="sxs-lookup"><span data-stu-id="81721-211">-Status</span></span>

<span data-ttu-id="81721-212">Especifica o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-212">Specifies the status for the service.</span></span>

<span data-ttu-id="81721-213">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="81721-213">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="81721-214">Em **pausa**.</span><span class="sxs-lookup"><span data-stu-id="81721-214">**Paused**.</span></span> <span data-ttu-id="81721-215">Suspende o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-215">Suspends the service.</span></span>
- <span data-ttu-id="81721-216">**Em execução**.</span><span class="sxs-lookup"><span data-stu-id="81721-216">**Running**.</span></span> <span data-ttu-id="81721-217">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-217">Starts the service.</span></span>
- <span data-ttu-id="81721-218">**Parado**.</span><span class="sxs-lookup"><span data-stu-id="81721-218">**Stopped**.</span></span> <span data-ttu-id="81721-219">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="81721-219">Stops the service.</span></span>

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

### <span data-ttu-id="81721-220">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="81721-220">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="81721-221">Especifica o **SecurityDescriptor** para o serviço no formato **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="81721-221">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="81721-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="81721-222">-WhatIf</span></span>

<span data-ttu-id="81721-223">Mostra o que aconteceria se `Set-Service` for executado.</span><span class="sxs-lookup"><span data-stu-id="81721-223">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="81721-224">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="81721-224">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="81721-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="81721-225">CommonParameters</span></span>

<span data-ttu-id="81721-226">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="81721-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="81721-227">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="81721-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="81721-228">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="81721-228">INPUTS</span></span>

### <span data-ttu-id="81721-229">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="81721-229">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="81721-230">Você pode usar o pipeline para enviar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-230">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="81721-231">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="81721-231">OUTPUTS</span></span>

### <span data-ttu-id="81721-232">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="81721-232">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="81721-233">Por padrão, o `Set-Service` não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="81721-233">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="81721-234">Use o parâmetro **PassThru** para gerar um objeto **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="81721-234">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="81721-235">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="81721-235">NOTES</span></span>

<span data-ttu-id="81721-236">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="81721-236">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="81721-237">`Set-Service` requer permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="81721-237">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="81721-238">Use a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="81721-238">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="81721-239">`Set-Service` Só é possível controlar os serviços quando o usuário atual tem permissões para gerenciar serviços.</span><span class="sxs-lookup"><span data-stu-id="81721-239">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="81721-240">Se um comando não funcionar corretamente, talvez você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="81721-240">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="81721-241">Para localizar o nome do serviço ou nome de exibição do serviço, use `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="81721-241">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="81721-242">Os nomes de serviço estão na coluna **nome** e os nomes de exibição estão na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="81721-242">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="81721-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="81721-243">RELATED LINKS</span></span>

[<span data-ttu-id="81721-244">Get-Service</span><span class="sxs-lookup"><span data-stu-id="81721-244">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="81721-245">New-Service</span><span class="sxs-lookup"><span data-stu-id="81721-245">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="81721-246">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="81721-246">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="81721-247">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="81721-247">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="81721-248">Start-Service</span><span class="sxs-lookup"><span data-stu-id="81721-248">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="81721-249">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="81721-249">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="81721-250">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="81721-250">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="81721-251">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="81721-251">Remove-Service</span></span>](Remove-Service.md)
