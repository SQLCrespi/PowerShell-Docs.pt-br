---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 39c03ec53056c5ec8e2d68f9b71a17a6f4a8ea8a
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890409"
---
# <span data-ttu-id="40134-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="40134-103">New-Service</span></span>

## <span data-ttu-id="40134-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="40134-104">SYNOPSIS</span></span>
<span data-ttu-id="40134-105">Cria um novo serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="40134-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="40134-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40134-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="40134-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40134-107">DESCRIPTION</span></span>

<span data-ttu-id="40134-108">O `New-Service` cmdlet cria uma nova entrada para um serviço do Windows no registro e no banco de dados de serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="40134-109">Um novo serviço requer um arquivo executável que é executado durante o serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="40134-110">Os parâmetros desse cmdlet permitem definir o nome de exibição, a descrição, o tipo de inicialização e as dependências do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="40134-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="40134-111">EXAMPLES</span></span>

### <span data-ttu-id="40134-112">Exemplo 1: criar um serviço</span><span class="sxs-lookup"><span data-stu-id="40134-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="40134-113">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="40134-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="40134-114">Exemplo 2: criar um serviço que inclui descrição, tipo de inicialização e nome de exibição</span><span class="sxs-lookup"><span data-stu-id="40134-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="40134-115">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="40134-115">This command creates a service named TestService.</span></span> <span data-ttu-id="40134-116">Ele usa os parâmetros de `New-Service` para especificar uma descrição, um tipo de inicialização e um nome de exibição para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="40134-117">Exemplo 3: exibir o novo serviço</span><span class="sxs-lookup"><span data-stu-id="40134-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="40134-118">Esse comando usa `Get-CimInstance` para obter o objeto de **Win32_Service** para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="40134-119">Este objeto inclui o modo de início e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="40134-120">Exemplo 4: definir o SecurityDescriptor de um serviço ao criar.</span><span class="sxs-lookup"><span data-stu-id="40134-120">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="40134-121">Este exemplo adiciona o **SecurityDescriptor** do serviço que está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="40134-121">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="40134-122">O **SecurityDescriptor** é armazenado na `$SDDLToSet` variável.</span><span class="sxs-lookup"><span data-stu-id="40134-122">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="40134-123">O parâmetro **SecurityDescriptorSddl** usa `$SDDL` para definir o **SecurityDescriptor** do novo serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-123">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="40134-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40134-124">PARAMETERS</span></span>

### <span data-ttu-id="40134-125">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="40134-125">-BinaryPathName</span></span>

<span data-ttu-id="40134-126">Especifica o caminho do arquivo executável para o serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="40134-127">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="40134-127">This parameter is required.</span></span>

<span data-ttu-id="40134-128">O caminho totalmente qualificado para o arquivo binário do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-128">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="40134-129">Se o caminho contiver um espaço, ele deverá estar entre aspas para que seja interpretado corretamente.</span><span class="sxs-lookup"><span data-stu-id="40134-129">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="40134-130">Por exemplo, `d:\my share\myservice.exe` deve ser especificado como `'"d:\my share\myservice.exe"'` .</span><span class="sxs-lookup"><span data-stu-id="40134-130">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="40134-131">O caminho também pode incluir argumentos para um serviço de início automático.</span><span class="sxs-lookup"><span data-stu-id="40134-131">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="40134-132">Por exemplo, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span><span class="sxs-lookup"><span data-stu-id="40134-132">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="40134-133">Esses argumentos são passados para o ponto de entrada de serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-133">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="40134-134">Para obter mais informações, consulte o parâmetro **lpBinaryPathName** da API [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) .</span><span class="sxs-lookup"><span data-stu-id="40134-134">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

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

### <span data-ttu-id="40134-135">-Credential</span><span class="sxs-lookup"><span data-stu-id="40134-135">-Credential</span></span>

<span data-ttu-id="40134-136">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="40134-136">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="40134-137">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40134-137">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="40134-138">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="40134-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="40134-139">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="40134-139">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="40134-140">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="40134-140">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="40134-141">-Depende</span><span class="sxs-lookup"><span data-stu-id="40134-141">-DependsOn</span></span>

<span data-ttu-id="40134-142">Especifica os nomes de outros serviços dos quais o novo serviço depende.</span><span class="sxs-lookup"><span data-stu-id="40134-142">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="40134-143">Para digitar vários nomes de serviço, use uma vírgula para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="40134-143">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="40134-144">-Description</span><span class="sxs-lookup"><span data-stu-id="40134-144">-Description</span></span>

<span data-ttu-id="40134-145">Especifica uma descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-145">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="40134-146">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="40134-146">-DisplayName</span></span>

<span data-ttu-id="40134-147">Especifica um nome de exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-147">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="40134-148">-Name</span><span class="sxs-lookup"><span data-stu-id="40134-148">-Name</span></span>

<span data-ttu-id="40134-149">Especifica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-149">Specifies the name of the service.</span></span> <span data-ttu-id="40134-150">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="40134-150">This parameter is required.</span></span>

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

### <span data-ttu-id="40134-151">-StartupType</span><span class="sxs-lookup"><span data-stu-id="40134-151">-StartupType</span></span>

<span data-ttu-id="40134-152">Define o tipo de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-152">Sets the startup type of the service.</span></span> <span data-ttu-id="40134-153">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="40134-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="40134-154">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="40134-154">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="40134-155">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="40134-155">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="40134-156">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="40134-156">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="40134-157">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="40134-157">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="40134-158">**Inválidos** -esse valor não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="40134-158">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="40134-159">O uso desse valor resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="40134-159">Using this value results in an error.</span></span>
- <span data-ttu-id="40134-160">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="40134-160">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="40134-161">O valor padrão é **automático**.</span><span class="sxs-lookup"><span data-stu-id="40134-161">The default value is **Automatic**.</span></span>

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

### <span data-ttu-id="40134-162">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="40134-162">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="40134-163">Especifica o **SecurityDescriptor** para o serviço no formato **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="40134-163">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="40134-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="40134-164">-Confirm</span></span>

<span data-ttu-id="40134-165">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40134-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="40134-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="40134-166">-WhatIf</span></span>

<span data-ttu-id="40134-167">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="40134-167">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="40134-168">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="40134-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="40134-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40134-169">CommonParameters</span></span>

<span data-ttu-id="40134-170">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40134-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40134-171">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40134-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40134-172">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="40134-172">INPUTS</span></span>

### <span data-ttu-id="40134-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="40134-173">None</span></span>

<span data-ttu-id="40134-174">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40134-174">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="40134-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="40134-175">OUTPUTS</span></span>

### <span data-ttu-id="40134-176">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="40134-176">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="40134-177">Esse cmdlet retorna um objeto que representa o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="40134-177">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="40134-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="40134-178">NOTES</span></span>

<span data-ttu-id="40134-179">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="40134-179">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="40134-180">Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="40134-180">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="40134-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="40134-181">RELATED LINKS</span></span>

[<span data-ttu-id="40134-182">Get-Service</span><span class="sxs-lookup"><span data-stu-id="40134-182">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="40134-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="40134-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="40134-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="40134-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="40134-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="40134-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="40134-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="40134-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="40134-187">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="40134-187">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="40134-188">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="40134-188">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="40134-189">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="40134-189">Remove-Service</span></span>](Remove-Service.md)
