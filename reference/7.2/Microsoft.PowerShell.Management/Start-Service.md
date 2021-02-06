---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: b1df4490da501111ccb44dea2645a333fdf5c27e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603769"
---
# <span data-ttu-id="453dd-102">Start-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-102">Start-Service</span></span>

## <span data-ttu-id="453dd-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="453dd-103">SYNOPSIS</span></span>
<span data-ttu-id="453dd-104">Inicia um ou mais serviços interrompidos.</span><span class="sxs-lookup"><span data-stu-id="453dd-104">Starts one or more stopped services.</span></span>

## <span data-ttu-id="453dd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="453dd-105">SYNTAX</span></span>

### <span data-ttu-id="453dd-106">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="453dd-106">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="453dd-107">Padrão</span><span class="sxs-lookup"><span data-stu-id="453dd-107">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="453dd-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="453dd-108">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="453dd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="453dd-109">DESCRIPTION</span></span>

<span data-ttu-id="453dd-110">O `Start-Service` cmdlet envia uma mensagem de início para o controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="453dd-110">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="453dd-111">Se um serviço estiver sendo executado, a mensagem será ignorada sem erro.</span><span class="sxs-lookup"><span data-stu-id="453dd-111">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="453dd-112">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para fornecer um objeto de serviço que represente os serviços que você deseja iniciar.</span><span class="sxs-lookup"><span data-stu-id="453dd-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="453dd-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="453dd-113">EXAMPLES</span></span>

### <span data-ttu-id="453dd-114">Exemplo 1: iniciar um serviço usando seu nome</span><span class="sxs-lookup"><span data-stu-id="453dd-114">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="453dd-115">Este exemplo inicia o serviço EventLog no computador local.</span><span class="sxs-lookup"><span data-stu-id="453dd-115">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="453dd-116">O parâmetro **Name** identifica o serviço pelo nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="453dd-116">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="453dd-117">Exemplo 2: exibir informações sem iniciar um serviço</span><span class="sxs-lookup"><span data-stu-id="453dd-117">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="453dd-118">Este exemplo mostra o que aconteceria se você iniciasse os serviços que têm um nome de exibição que inclui "remoto".</span><span class="sxs-lookup"><span data-stu-id="453dd-118">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="453dd-119">O parâmetro **DisplayName** identifica os serviços por seu nome de exibição, em vez de seu nome de serviço.</span><span class="sxs-lookup"><span data-stu-id="453dd-119">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="453dd-120">O parâmetro **WhatIf** faz com que o cmdlet exiba o que aconteceria quando você executa o comando, mas não faz alterações.</span><span class="sxs-lookup"><span data-stu-id="453dd-120">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="453dd-121">Exemplo 3: iniciar um serviço e registrar a ação em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="453dd-121">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="453dd-122">Este exemplo inicia o serviço de Instrumentação de Gerenciamento do Windows (WMI) no computador e adiciona um registro da ação ao arquivo de services.txt.</span><span class="sxs-lookup"><span data-stu-id="453dd-122">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="453dd-123">Primeiro, usamos `Get-Service` para obter um objeto que representa o serviço WMI e armazená-lo `$s` na variável.</span><span class="sxs-lookup"><span data-stu-id="453dd-123">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="453dd-124">Em seguida, iniciamos o serviço.</span><span class="sxs-lookup"><span data-stu-id="453dd-124">Next, we start the service.</span></span> <span data-ttu-id="453dd-125">Sem o parâmetro **PassThru** , o não `Start-Service` cria nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="453dd-125">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="453dd-126">O operador de pipeline (|) passa a saída do objeto pelo `Start-Service` para o `Format-List` cmdlet para formatar o objeto como uma lista de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="453dd-126">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="453dd-127">O operador de redirecionamento de acréscimo ( \> \> ) redireciona a saída para o arquivo de services.txt.</span><span class="sxs-lookup"><span data-stu-id="453dd-127">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="453dd-128">A saída é adicionada ao final do arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="453dd-128">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="453dd-129">Exemplo 4: iniciar um serviço desabilitado</span><span class="sxs-lookup"><span data-stu-id="453dd-129">Example 4: Start a disabled service</span></span>

<span data-ttu-id="453dd-130">Este exemplo mostra como iniciar um serviço quando o tipo de início do serviço é **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="453dd-130">This example shows how to start a service when the start type of the service is **Disabled**.</span></span>

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

<span data-ttu-id="453dd-131">A primeira tentativa de iniciar o serviço Telnet (TlntSvr) falha.</span><span class="sxs-lookup"><span data-stu-id="453dd-131">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="453dd-132">O `Get-CimInstance` comando mostra que a propriedade **startMode** do serviço TlntSvr está **desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="453dd-132">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled**.</span></span> <span data-ttu-id="453dd-133">O `Set-Service` cmdlet altera o tipo de início para **manual**.</span><span class="sxs-lookup"><span data-stu-id="453dd-133">The `Set-Service` cmdlet changes the start type to **Manual**.</span></span> <span data-ttu-id="453dd-134">Agora, podemos enviar o comando novamente `Start-Service` .</span><span class="sxs-lookup"><span data-stu-id="453dd-134">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="453dd-135">Desta vez, o comando terá êxito.</span><span class="sxs-lookup"><span data-stu-id="453dd-135">This time, the command succeeds.</span></span> <span data-ttu-id="453dd-136">Para verificar se o comando foi bem-sucedido, execute `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="453dd-136">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="453dd-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="453dd-137">PARAMETERS</span></span>

### <span data-ttu-id="453dd-138">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="453dd-138">-DisplayName</span></span>

<span data-ttu-id="453dd-139">Especifica os nomes de exibição dos serviços a serem iniciados.</span><span class="sxs-lookup"><span data-stu-id="453dd-139">Specifies the display names of the services to start.</span></span> <span data-ttu-id="453dd-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="453dd-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="453dd-141">-Excluir</span><span class="sxs-lookup"><span data-stu-id="453dd-141">-Exclude</span></span>

<span data-ttu-id="453dd-142">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="453dd-142">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="453dd-143">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="453dd-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="453dd-144">Insira um elemento de nome ou padrão, como `s*` .</span><span class="sxs-lookup"><span data-stu-id="453dd-144">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="453dd-145">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="453dd-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="453dd-146">-Incluir</span><span class="sxs-lookup"><span data-stu-id="453dd-146">-Include</span></span>

<span data-ttu-id="453dd-147">Especifica os serviços que este cmdlet inicia.</span><span class="sxs-lookup"><span data-stu-id="453dd-147">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="453dd-148">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="453dd-148">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="453dd-149">Insira um elemento de nome ou padrão, como `s*` .</span><span class="sxs-lookup"><span data-stu-id="453dd-149">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="453dd-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="453dd-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="453dd-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="453dd-151">-InputObject</span></span>

<span data-ttu-id="453dd-152">Especifica objetos **ServiceController** que representam os serviços a serem iniciados.</span><span class="sxs-lookup"><span data-stu-id="453dd-152">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="453dd-153">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="453dd-153">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="453dd-154">-Name</span><span class="sxs-lookup"><span data-stu-id="453dd-154">-Name</span></span>

<span data-ttu-id="453dd-155">Especifica os nomes de serviço para o serviço a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="453dd-155">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="453dd-156">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="453dd-156">The parameter name is optional.</span></span> <span data-ttu-id="453dd-157">Você pode usar o **nome** ou seu alias **,** ServiceName ou pode omitir o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="453dd-157">You can use **Name** or its alias, **ServiceName**, or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="453dd-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="453dd-158">-PassThru</span></span>

<span data-ttu-id="453dd-159">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="453dd-159">Returns an object that represents the service.</span></span> <span data-ttu-id="453dd-160">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="453dd-160">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="453dd-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="453dd-161">-Confirm</span></span>

<span data-ttu-id="453dd-162">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="453dd-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="453dd-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="453dd-163">-WhatIf</span></span>

<span data-ttu-id="453dd-164">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="453dd-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="453dd-165">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="453dd-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="453dd-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="453dd-166">CommonParameters</span></span>

<span data-ttu-id="453dd-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="453dd-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="453dd-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="453dd-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="453dd-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="453dd-169">INPUTS</span></span>

### <span data-ttu-id="453dd-170">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="453dd-170">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="453dd-171">É possível canalizar objetos que representam os serviços ou cadeias de caracteres que contêm os nomes de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="453dd-171">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="453dd-172">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="453dd-172">OUTPUTS</span></span>

### <span data-ttu-id="453dd-173">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="453dd-173">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="453dd-174">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você especificar **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="453dd-174">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru**.</span></span> <span data-ttu-id="453dd-175">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="453dd-175">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="453dd-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="453dd-176">NOTES</span></span>

<span data-ttu-id="453dd-177">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="453dd-177">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="453dd-178">Você também pode consultar `Start-Service` por seu alias interno, `sasv` .</span><span class="sxs-lookup"><span data-stu-id="453dd-178">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="453dd-179">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="453dd-179">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="453dd-180">`Start-Service` pode controlar os serviços somente se o usuário atual tiver permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="453dd-180">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="453dd-181">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="453dd-181">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="453dd-182">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="453dd-182">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="453dd-183">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="453dd-183">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
- <span data-ttu-id="453dd-184">Você pode iniciar somente os serviços que têm um tipo de início manual, automático ou automático (início atrasado).</span><span class="sxs-lookup"><span data-stu-id="453dd-184">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="453dd-185">Você não pode iniciar os serviços que têm um tipo de início desabilitado.</span><span class="sxs-lookup"><span data-stu-id="453dd-185">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="453dd-186">Se um `Start-Service` comando falhar com a mensagem `Cannot start service \<service-name\> on computer` , use `Get-CimInstance` para localizar o tipo de início do serviço e, se necessário, use o `Set-Service` cmdlet para alterar o tipo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="453dd-186">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
- <span data-ttu-id="453dd-187">Alguns serviços, como Logs e Alertas de Desempenho (SysmonLog), serão interrompidos automaticamente se não tiverem nenhum trabalho a fazer.</span><span class="sxs-lookup"><span data-stu-id="453dd-187">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="453dd-188">Quando o PowerShell inicia um serviço que se interrompe quase imediatamente, ele exibe a seguinte mensagem: `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="453dd-188">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="453dd-189">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="453dd-189">RELATED LINKS</span></span>

[<span data-ttu-id="453dd-190">Get-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-190">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="453dd-191">New-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-191">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="453dd-192">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-192">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="453dd-193">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-193">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="453dd-194">Set-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-194">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="453dd-195">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-195">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="453dd-196">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-196">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="453dd-197">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="453dd-197">Remove-Service</span></span>](Remove-Service.md)
