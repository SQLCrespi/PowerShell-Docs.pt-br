---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 0963e90f1f994a9bd6f3f61e80bf56eebff09384
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343106"
---
# <span data-ttu-id="8918d-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-103">New-Service</span></span>

## <span data-ttu-id="8918d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8918d-104">SYNOPSIS</span></span>
<span data-ttu-id="8918d-105">Cria um novo serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="8918d-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="8918d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8918d-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8918d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8918d-107">DESCRIPTION</span></span>

<span data-ttu-id="8918d-108">O `New-Service` cmdlet cria uma nova entrada para um serviço do Windows no registro e no banco de dados de serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="8918d-109">Um novo serviço requer um arquivo executável que é executado durante o serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="8918d-110">Os parâmetros desse cmdlet permitem definir o nome de exibição, a descrição, o tipo de inicialização e as dependências do serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="8918d-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8918d-111">EXAMPLES</span></span>

### <span data-ttu-id="8918d-112">Exemplo 1: criar um serviço</span><span class="sxs-lookup"><span data-stu-id="8918d-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="8918d-113">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="8918d-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="8918d-114">Exemplo 2: criar um serviço que inclui descrição, tipo de inicialização e nome de exibição</span><span class="sxs-lookup"><span data-stu-id="8918d-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="8918d-115">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="8918d-115">This command creates a service named TestService.</span></span> <span data-ttu-id="8918d-116">Ele usa os parâmetros de `New-Service` para especificar uma descrição, um tipo de inicialização e um nome de exibição para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="8918d-117">Exemplo 3: exibir o novo serviço</span><span class="sxs-lookup"><span data-stu-id="8918d-117">Example 3: View the new service</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

<span data-ttu-id="8918d-118">Esse comando usa `Get-CimInstance` para obter o objeto de **Win32_Service** para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="8918d-119">Este objeto inclui o modo de início e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="8918d-120">Exemplo 4: definir o SecurityDescriptor de um serviço ao criar.</span><span class="sxs-lookup"><span data-stu-id="8918d-120">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="8918d-121">Este exemplo adiciona o **SecurityDescriptor** do serviço que está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="8918d-121">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="8918d-122">O **SecurityDescriptor** é armazenado na `$SDDLToSet` variável.</span><span class="sxs-lookup"><span data-stu-id="8918d-122">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="8918d-123">O parâmetro **SecurityDescriptorSddl** usa `$SDDL` para definir o **SecurityDescriptor** do novo serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-123">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="8918d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8918d-124">PARAMETERS</span></span>

### <span data-ttu-id="8918d-125">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="8918d-125">-BinaryPathName</span></span>

<span data-ttu-id="8918d-126">Especifica o caminho do arquivo executável para o serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="8918d-127">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="8918d-127">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8918d-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="8918d-128">-Credential</span></span>

<span data-ttu-id="8918d-129">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="8918d-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="8918d-130">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8918d-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8918d-131">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="8918d-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="8918d-132">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="8918d-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="8918d-133">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="8918d-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="8918d-134">-Depende</span><span class="sxs-lookup"><span data-stu-id="8918d-134">-DependsOn</span></span>

<span data-ttu-id="8918d-135">Especifica os nomes de outros serviços dos quais o novo serviço depende.</span><span class="sxs-lookup"><span data-stu-id="8918d-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="8918d-136">Para digitar vários nomes de serviço, use uma vírgula para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="8918d-136">To enter multiple service names, use a comma to separate the names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8918d-137">-Description</span><span class="sxs-lookup"><span data-stu-id="8918d-137">-Description</span></span>

<span data-ttu-id="8918d-138">Especifica uma descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="8918d-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="8918d-139">-DisplayName</span></span>

<span data-ttu-id="8918d-140">Especifica um nome de exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="8918d-141">-Name</span><span class="sxs-lookup"><span data-stu-id="8918d-141">-Name</span></span>

<span data-ttu-id="8918d-142">Especifica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-142">Specifies the name of the service.</span></span> <span data-ttu-id="8918d-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="8918d-143">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8918d-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="8918d-144">-StartupType</span></span>

<span data-ttu-id="8918d-145">Define o tipo de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-145">Sets the startup type of the service.</span></span> <span data-ttu-id="8918d-146">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="8918d-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8918d-147">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="8918d-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="8918d-148">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="8918d-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="8918d-149">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="8918d-149">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="8918d-150">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8918d-150">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="8918d-151">**Inválidos** -esse valor não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="8918d-151">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="8918d-152">O uso desse valor resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="8918d-152">Using this value results in an error.</span></span>
- <span data-ttu-id="8918d-153">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8918d-153">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="8918d-154">O valor padrão é **automático**.</span><span class="sxs-lookup"><span data-stu-id="8918d-154">The default value is **Automatic**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8918d-155">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="8918d-155">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="8918d-156">Especifica o **SecurityDescriptor** para o serviço no formato **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="8918d-156">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="8918d-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8918d-157">-Confirm</span></span>

<span data-ttu-id="8918d-158">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8918d-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8918d-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8918d-159">-WhatIf</span></span>

<span data-ttu-id="8918d-160">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8918d-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8918d-161">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8918d-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8918d-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8918d-162">CommonParameters</span></span>

<span data-ttu-id="8918d-163">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8918d-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8918d-164">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8918d-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8918d-165">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8918d-165">INPUTS</span></span>

### <span data-ttu-id="8918d-166">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8918d-166">None</span></span>

<span data-ttu-id="8918d-167">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8918d-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8918d-168">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8918d-168">OUTPUTS</span></span>

### <span data-ttu-id="8918d-169">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="8918d-169">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="8918d-170">Esse cmdlet retorna um objeto que representa o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="8918d-170">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="8918d-171">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8918d-171">NOTES</span></span>

<span data-ttu-id="8918d-172">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="8918d-172">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="8918d-173">Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="8918d-173">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="8918d-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8918d-174">RELATED LINKS</span></span>

[<span data-ttu-id="8918d-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="8918d-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="8918d-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="8918d-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="8918d-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="8918d-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="8918d-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-181">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="8918d-182">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="8918d-182">Remove-Service</span></span>](Remove-Service.md)
