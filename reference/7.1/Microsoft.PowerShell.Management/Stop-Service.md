---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: fae0ac83c86bb6e1767bcc9b48ce492e8068139c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347560"
---
# <span data-ttu-id="15bab-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-103">Stop-Service</span></span>

## <span data-ttu-id="15bab-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="15bab-104">SYNOPSIS</span></span>
<span data-ttu-id="15bab-105">Interrompe um ou mais serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="15bab-105">Stops one or more running services.</span></span>

## <span data-ttu-id="15bab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15bab-106">SYNTAX</span></span>

### <span data-ttu-id="15bab-107">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="15bab-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15bab-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="15bab-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15bab-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="15bab-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="15bab-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15bab-110">DESCRIPTION</span></span>

<span data-ttu-id="15bab-111">O `Stop-Service` cmdlet envia uma mensagem de parada para o controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="15bab-111">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="15bab-112">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa o serviço que você deseja parar.</span><span class="sxs-lookup"><span data-stu-id="15bab-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="15bab-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="15bab-113">EXAMPLES</span></span>

### <span data-ttu-id="15bab-114">Exemplo 1: parar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="15bab-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="15bab-115">Esse comando para os Alertas e Logs de Desempenho (SysmonLog) do serviço no computador local.</span><span class="sxs-lookup"><span data-stu-id="15bab-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="15bab-116">Exemplo 2: parar um serviço usando o nome de exibição</span><span class="sxs-lookup"><span data-stu-id="15bab-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="15bab-117">Esse comando para o serviço Telnet no computador local.</span><span class="sxs-lookup"><span data-stu-id="15bab-117">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="15bab-118">O comando usa `Get-Service` para obter um objeto que representa o serviço Telnet.</span><span class="sxs-lookup"><span data-stu-id="15bab-118">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="15bab-119">O operador de pipeline ( `|` ) canaliza o objeto para `Stop-Service` , o que interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="15bab-119">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="15bab-120">Exemplo 3: parar um serviço que tem serviços dependentes</span><span class="sxs-lookup"><span data-stu-id="15bab-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="15bab-121">Este exemplo interrompe o serviço IISAdmin no computador local.</span><span class="sxs-lookup"><span data-stu-id="15bab-121">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="15bab-122">Como a interrupção desse serviço também interrompe os serviços que dependem do serviço IISAdmin, é melhor preceder `Stop-Service` um comando que lista os serviços que dependem do serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="15bab-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="15bab-123">O primeiro comando lista os serviços que dependem do IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="15bab-123">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="15bab-124">Ele usa `Get-Service` para obter um objeto que representa o serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="15bab-124">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="15bab-125">O operador de pipeline ( `|` ) passa o resultado para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15bab-125">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="15bab-126">O comando usa o parâmetro **Property** de `Format-List` para listar apenas as propriedades **Name** e **DependentServices** do serviço.</span><span class="sxs-lookup"><span data-stu-id="15bab-126">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="15bab-127">O segundo comando interrompe o serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="15bab-127">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="15bab-128">O parâmetro **Force** é necessário para interromper um serviço que tem serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="15bab-128">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="15bab-129">O comando usa o parâmetro **Confirm** para solicitar a confirmação do usuário antes de parar cada serviço.</span><span class="sxs-lookup"><span data-stu-id="15bab-129">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="15bab-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15bab-130">PARAMETERS</span></span>

### <span data-ttu-id="15bab-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="15bab-131">-DisplayName</span></span>

<span data-ttu-id="15bab-132">Especifica os nomes de exibição dos serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="15bab-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="15bab-134">-Excluir</span><span class="sxs-lookup"><span data-stu-id="15bab-134">-Exclude</span></span>

<span data-ttu-id="15bab-135">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="15bab-135">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="15bab-136">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="15bab-136">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="15bab-137">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="15bab-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="15bab-138">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="15bab-139">-Force</span><span class="sxs-lookup"><span data-stu-id="15bab-139">-Force</span></span>

<span data-ttu-id="15bab-140">Força o cmdlet a parar um serviço mesmo que esse serviço tenha serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="15bab-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="15bab-141">-Incluir</span><span class="sxs-lookup"><span data-stu-id="15bab-141">-Include</span></span>

<span data-ttu-id="15bab-142">Especifica os serviços que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="15bab-142">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="15bab-143">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="15bab-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="15bab-144">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="15bab-144">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="15bab-145">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="15bab-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="15bab-146">-InputObject</span></span>

<span data-ttu-id="15bab-147">Especifica objetos **ServiceController** que representam os serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-147">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="15bab-148">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="15bab-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="15bab-149">-Name</span><span class="sxs-lookup"><span data-stu-id="15bab-149">-Name</span></span>

<span data-ttu-id="15bab-150">Especifica os nomes de serviço dos serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-150">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="15bab-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="15bab-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="15bab-152">-Nowait</span><span class="sxs-lookup"><span data-stu-id="15bab-152">-NoWait</span></span>

<span data-ttu-id="15bab-153">Indica que esse cmdlet usa a opção sem espera.</span><span class="sxs-lookup"><span data-stu-id="15bab-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="15bab-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="15bab-154">-PassThru</span></span>

<span data-ttu-id="15bab-155">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="15bab-155">Returns an object that represents the service.</span></span> <span data-ttu-id="15bab-156">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="15bab-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="15bab-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="15bab-157">-Confirm</span></span>

<span data-ttu-id="15bab-158">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15bab-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="15bab-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="15bab-159">-WhatIf</span></span>

<span data-ttu-id="15bab-160">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="15bab-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="15bab-161">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="15bab-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="15bab-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15bab-162">CommonParameters</span></span>

<span data-ttu-id="15bab-163">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15bab-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15bab-164">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15bab-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15bab-165">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="15bab-165">INPUTS</span></span>

### <span data-ttu-id="15bab-166">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="15bab-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="15bab-167">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém o nome de um serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15bab-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="15bab-168">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="15bab-168">OUTPUTS</span></span>

### <span data-ttu-id="15bab-169">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="15bab-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="15bab-170">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você usar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="15bab-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="15bab-171">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="15bab-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="15bab-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="15bab-172">NOTES</span></span>

<span data-ttu-id="15bab-173">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="15bab-173">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="15bab-174">Você também pode consultar `Stop-Service` por seu alias interno, **spsv**.</span><span class="sxs-lookup"><span data-stu-id="15bab-174">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="15bab-175">Para obter mais informações, consulte about_Aliases.</span><span class="sxs-lookup"><span data-stu-id="15bab-175">For more information, see about_Aliases.</span></span>

<span data-ttu-id="15bab-176">`Stop-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="15bab-176">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="15bab-177">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="15bab-177">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="15bab-178">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="15bab-178">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="15bab-179">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="15bab-179">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="15bab-180">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="15bab-180">RELATED LINKS</span></span>

[<span data-ttu-id="15bab-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="15bab-182">New-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-182">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="15bab-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="15bab-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="15bab-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="15bab-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="15bab-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="15bab-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="15bab-188">Remove-Service</span></span>](Remove-Service.md)
