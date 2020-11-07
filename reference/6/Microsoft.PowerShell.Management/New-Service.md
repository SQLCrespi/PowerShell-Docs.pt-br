---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: aadb0d53ad180ba1e88d31e5d008c6090ae0c9b3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345214"
---
# <span data-ttu-id="01b6b-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-103">New-Service</span></span>

## <span data-ttu-id="01b6b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="01b6b-104">SYNOPSIS</span></span>
<span data-ttu-id="01b6b-105">Cria um novo serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="01b6b-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="01b6b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01b6b-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartupType>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="01b6b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01b6b-107">DESCRIPTION</span></span>

<span data-ttu-id="01b6b-108">O `New-Service` cmdlet cria uma nova entrada para um serviço do Windows no registro e no banco de dados de serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="01b6b-109">Um novo serviço requer um arquivo executável que é executado durante o serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="01b6b-110">Os parâmetros desse cmdlet permitem definir o nome de exibição, a descrição, o tipo de inicialização e as dependências do serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="01b6b-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="01b6b-111">EXAMPLES</span></span>

### <span data-ttu-id="01b6b-112">Exemplo 1: criar um serviço</span><span class="sxs-lookup"><span data-stu-id="01b6b-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="01b6b-113">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="01b6b-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="01b6b-114">Exemplo 2: criar um serviço que inclui descrição, tipo de inicialização e nome de exibição</span><span class="sxs-lookup"><span data-stu-id="01b6b-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="01b6b-115">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="01b6b-115">This command creates a service named TestService.</span></span> <span data-ttu-id="01b6b-116">Ele usa os parâmetros de `New-Service` para especificar uma descrição, um tipo de inicialização e um nome de exibição para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="01b6b-117">Exemplo 3: exibir o novo serviço</span><span class="sxs-lookup"><span data-stu-id="01b6b-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="01b6b-118">Esse comando usa `Get-CimInstance` para obter o objeto de **Win32_Service** para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="01b6b-119">Este objeto inclui o modo de início e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-119">This object includes the start mode and the service description.</span></span>

## <span data-ttu-id="01b6b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01b6b-120">PARAMETERS</span></span>

### <span data-ttu-id="01b6b-121">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="01b6b-121">-BinaryPathName</span></span>

<span data-ttu-id="01b6b-122">Especifica o caminho do arquivo executável para o serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-122">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="01b6b-123">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="01b6b-123">This parameter is required.</span></span>

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

### <span data-ttu-id="01b6b-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="01b6b-124">-Credential</span></span>

<span data-ttu-id="01b6b-125">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="01b6b-125">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="01b6b-126">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01b6b-126">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="01b6b-127">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="01b6b-127">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="01b6b-128">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="01b6b-128">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="01b6b-129">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="01b6b-129">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="01b6b-130">-Depende</span><span class="sxs-lookup"><span data-stu-id="01b6b-130">-DependsOn</span></span>

<span data-ttu-id="01b6b-131">Especifica os nomes de outros serviços dos quais o novo serviço depende.</span><span class="sxs-lookup"><span data-stu-id="01b6b-131">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="01b6b-132">Para digitar vários nomes de serviço, use uma vírgula para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="01b6b-132">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="01b6b-133">-Description</span><span class="sxs-lookup"><span data-stu-id="01b6b-133">-Description</span></span>

<span data-ttu-id="01b6b-134">Especifica uma descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-134">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="01b6b-135">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="01b6b-135">-DisplayName</span></span>

<span data-ttu-id="01b6b-136">Especifica um nome de exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-136">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="01b6b-137">-Name</span><span class="sxs-lookup"><span data-stu-id="01b6b-137">-Name</span></span>

<span data-ttu-id="01b6b-138">Especifica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-138">Specifies the name of the service.</span></span> <span data-ttu-id="01b6b-139">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="01b6b-139">This parameter is required.</span></span>

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

### <span data-ttu-id="01b6b-140">-StartupType</span><span class="sxs-lookup"><span data-stu-id="01b6b-140">-StartupType</span></span>

<span data-ttu-id="01b6b-141">Define o tipo de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-141">Sets the startup type of the service.</span></span> <span data-ttu-id="01b6b-142">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="01b6b-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="01b6b-143">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="01b6b-143">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="01b6b-144">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="01b6b-144">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="01b6b-145">**AutomaticDelayedStart** -inicia logo após a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="01b6b-145">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="01b6b-146">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01b6b-146">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="01b6b-147">**Inválidos** -esse valor não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="01b6b-147">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="01b6b-148">O uso desse valor resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="01b6b-148">Using this value results in an error.</span></span>
- <span data-ttu-id="01b6b-149">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01b6b-149">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="01b6b-150">O valor padrão é **automático**.</span><span class="sxs-lookup"><span data-stu-id="01b6b-150">The default value is **Automatic**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01b6b-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="01b6b-151">-Confirm</span></span>

<span data-ttu-id="01b6b-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01b6b-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="01b6b-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="01b6b-153">-WhatIf</span></span>

<span data-ttu-id="01b6b-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="01b6b-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="01b6b-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="01b6b-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="01b6b-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="01b6b-156">CommonParameters</span></span>

<span data-ttu-id="01b6b-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01b6b-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01b6b-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01b6b-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01b6b-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="01b6b-159">INPUTS</span></span>

### <span data-ttu-id="01b6b-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="01b6b-160">None</span></span>

<span data-ttu-id="01b6b-161">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01b6b-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="01b6b-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="01b6b-162">OUTPUTS</span></span>

### <span data-ttu-id="01b6b-163">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="01b6b-163">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="01b6b-164">Esse cmdlet retorna um objeto que representa o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="01b6b-164">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="01b6b-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="01b6b-165">NOTES</span></span>

<span data-ttu-id="01b6b-166">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="01b6b-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="01b6b-167">Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="01b6b-167">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="01b6b-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="01b6b-168">RELATED LINKS</span></span>

[<span data-ttu-id="01b6b-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-169">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="01b6b-170">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-170">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="01b6b-171">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-171">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="01b6b-172">Set-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-172">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="01b6b-173">Start-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-173">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="01b6b-174">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-174">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="01b6b-175">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-175">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="01b6b-176">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="01b6b-176">Remove-Service</span></span>](Remove-Service.md)
