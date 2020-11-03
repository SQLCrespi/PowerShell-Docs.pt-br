---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 3249ce91a63417f2790997d37e2420c6fcb374d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193967"
---
# <span data-ttu-id="18351-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="18351-103">New-Service</span></span>

## <span data-ttu-id="18351-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="18351-104">SYNOPSIS</span></span>
<span data-ttu-id="18351-105">Cria um novo serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="18351-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="18351-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18351-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="18351-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18351-107">DESCRIPTION</span></span>

<span data-ttu-id="18351-108">O `New-Service` cmdlet cria uma nova entrada para um serviço do Windows no registro e no banco de dados de serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="18351-109">Um novo serviço requer um arquivo executável que é executado durante o serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="18351-110">Os parâmetros desse cmdlet permitem definir o nome de exibição, a descrição, o tipo de inicialização e as dependências do serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="18351-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="18351-111">EXAMPLES</span></span>

### <span data-ttu-id="18351-112">Exemplo 1: criar um serviço</span><span class="sxs-lookup"><span data-stu-id="18351-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="18351-113">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="18351-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="18351-114">Exemplo 2: criar um serviço que inclui descrição, tipo de inicialização e nome de exibição</span><span class="sxs-lookup"><span data-stu-id="18351-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="18351-115">Este comando cria um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="18351-115">This command creates a service named TestService.</span></span> <span data-ttu-id="18351-116">Ele usa os parâmetros de `New-Service` para especificar uma descrição, um tipo de inicialização e um nome de exibição para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="18351-117">Exemplo 3: exibir o novo serviço</span><span class="sxs-lookup"><span data-stu-id="18351-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="18351-118">Esse comando usa `Get-CimInstance` para obter o objeto de **Win32_Service** para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="18351-119">Este objeto inclui o modo de início e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="18351-120">Exemplo 4: excluir um serviço</span><span class="sxs-lookup"><span data-stu-id="18351-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="18351-121">Este exemplo mostra duas maneiras de excluir o serviço TestService.</span><span class="sxs-lookup"><span data-stu-id="18351-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="18351-122">O primeiro comando usa a opção Delete de `Sc.exe` .</span><span class="sxs-lookup"><span data-stu-id="18351-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="18351-123">O segundo comando usa o método **delete** do **Win32_Service** objetos que `Get-CimInstance` retorna.</span><span class="sxs-lookup"><span data-stu-id="18351-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="18351-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18351-124">PARAMETERS</span></span>

### <span data-ttu-id="18351-125">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="18351-125">-BinaryPathName</span></span>

<span data-ttu-id="18351-126">Especifica o caminho do arquivo executável para o serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="18351-127">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="18351-127">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18351-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="18351-128">-Credential</span></span>

<span data-ttu-id="18351-129">Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="18351-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="18351-130">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18351-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="18351-131">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="18351-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="18351-132">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="18351-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="18351-133">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="18351-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="18351-134">-Depende</span><span class="sxs-lookup"><span data-stu-id="18351-134">-DependsOn</span></span>

<span data-ttu-id="18351-135">Especifica os nomes de outros serviços dos quais o novo serviço depende.</span><span class="sxs-lookup"><span data-stu-id="18351-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="18351-136">Para digitar vários nomes de serviço, use uma vírgula para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="18351-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="18351-137">-Description</span><span class="sxs-lookup"><span data-stu-id="18351-137">-Description</span></span>

<span data-ttu-id="18351-138">Especifica uma descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="18351-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="18351-139">-DisplayName</span></span>

<span data-ttu-id="18351-140">Especifica um nome de exibição para o serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="18351-141">-Name</span><span class="sxs-lookup"><span data-stu-id="18351-141">-Name</span></span>

<span data-ttu-id="18351-142">Especifica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-142">Specifies the name of the service.</span></span>
<span data-ttu-id="18351-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="18351-143">This parameter is required.</span></span>

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

### <span data-ttu-id="18351-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="18351-144">-StartupType</span></span>

<span data-ttu-id="18351-145">Define o tipo de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-145">Sets the startup type of the service.</span></span> <span data-ttu-id="18351-146">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="18351-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="18351-147">**Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="18351-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="18351-148">Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="18351-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="18351-149">**Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18351-149">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="18351-150">**Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18351-150">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="18351-151">**Inicialização** -indica que o serviço é um driver de dispositivo iniciado pelo carregador do sistema.</span><span class="sxs-lookup"><span data-stu-id="18351-151">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="18351-152">Esse valor é válido somente para drivers de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="18351-152">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="18351-153">**Sistema** -indica que o serviço é um driver de dispositivo iniciado pela função ' IOInitSystem () '.</span><span class="sxs-lookup"><span data-stu-id="18351-153">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="18351-154">Esse valor é válido somente para drivers de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="18351-154">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="18351-155">O valor padrão é **automático** .</span><span class="sxs-lookup"><span data-stu-id="18351-155">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18351-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="18351-156">-Confirm</span></span>

<span data-ttu-id="18351-157">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18351-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="18351-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="18351-158">-WhatIf</span></span>

<span data-ttu-id="18351-159">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="18351-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="18351-160">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="18351-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="18351-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="18351-161">CommonParameters</span></span>

<span data-ttu-id="18351-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="18351-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18351-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="18351-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18351-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="18351-164">INPUTS</span></span>

### <span data-ttu-id="18351-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18351-165">None</span></span>

<span data-ttu-id="18351-166">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18351-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="18351-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="18351-167">OUTPUTS</span></span>

### <span data-ttu-id="18351-168">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="18351-168">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="18351-169">Esse cmdlet retorna um objeto que representa o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-169">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="18351-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="18351-170">NOTES</span></span>

<span data-ttu-id="18351-171">Para executar esse cmdlet no Windows Vista e em versões posteriores do sistema operacional Windows, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="18351-171">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="18351-172">Para excluir um serviço, use Sc.exe ou use o `Get-CimInstance` cmdlet para obter o **Win32_Service** objeto que representa o serviço e, em seguida, use o método **delete** para excluir o serviço.</span><span class="sxs-lookup"><span data-stu-id="18351-172">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="18351-173">O objeto que `Get-Service` retorna não tem um método Delete.</span><span class="sxs-lookup"><span data-stu-id="18351-173">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="18351-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="18351-174">RELATED LINKS</span></span>

[<span data-ttu-id="18351-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="18351-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="18351-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="18351-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="18351-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="18351-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="18351-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="18351-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="18351-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="18351-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="18351-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="18351-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="18351-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="18351-181">Suspend-Service</span></span>](Suspend-Service.md)
