---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 0216c7fae722121ead1c8e9ba122fbc3f1713725
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597412"
---
# <span data-ttu-id="611b8-102">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-102">Stop-Service</span></span>

## <span data-ttu-id="611b8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="611b8-103">SYNOPSIS</span></span>
<span data-ttu-id="611b8-104">Interrompe um ou mais serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="611b8-104">Stops one or more running services.</span></span>

## <span data-ttu-id="611b8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="611b8-105">SYNTAX</span></span>

### <span data-ttu-id="611b8-106">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="611b8-106">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="611b8-107">Padrão</span><span class="sxs-lookup"><span data-stu-id="611b8-107">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="611b8-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="611b8-108">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="611b8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="611b8-109">DESCRIPTION</span></span>

<span data-ttu-id="611b8-110">O `Stop-Service` cmdlet envia uma mensagem de parada para o controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="611b8-110">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="611b8-111">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa o serviço que você deseja parar.</span><span class="sxs-lookup"><span data-stu-id="611b8-111">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="611b8-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="611b8-112">EXAMPLES</span></span>

### <span data-ttu-id="611b8-113">Exemplo 1: parar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="611b8-113">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="611b8-114">Esse comando para os Alertas e Logs de Desempenho (SysmonLog) do serviço no computador local.</span><span class="sxs-lookup"><span data-stu-id="611b8-114">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="611b8-115">Exemplo 2: parar um serviço usando o nome de exibição</span><span class="sxs-lookup"><span data-stu-id="611b8-115">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="611b8-116">Esse comando para o serviço Telnet no computador local.</span><span class="sxs-lookup"><span data-stu-id="611b8-116">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="611b8-117">O comando usa `Get-Service` para obter um objeto que representa o serviço Telnet.</span><span class="sxs-lookup"><span data-stu-id="611b8-117">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="611b8-118">O operador de pipeline ( `|` ) canaliza o objeto para `Stop-Service` , o que interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="611b8-118">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="611b8-119">Exemplo 3: parar um serviço que tem serviços dependentes</span><span class="sxs-lookup"><span data-stu-id="611b8-119">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="611b8-120">Este exemplo interrompe o serviço IISAdmin no computador local.</span><span class="sxs-lookup"><span data-stu-id="611b8-120">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="611b8-121">Como a interrupção desse serviço também interrompe os serviços que dependem do serviço IISAdmin, é melhor preceder `Stop-Service` um comando que lista os serviços que dependem do serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="611b8-121">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="611b8-122">O primeiro comando lista os serviços que dependem do IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="611b8-122">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="611b8-123">Ele usa `Get-Service` para obter um objeto que representa o serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="611b8-123">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="611b8-124">O operador de pipeline ( `|` ) passa o resultado para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="611b8-124">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="611b8-125">O comando usa o parâmetro **Property** de `Format-List` para listar apenas as propriedades **Name** e **DependentServices** do serviço.</span><span class="sxs-lookup"><span data-stu-id="611b8-125">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="611b8-126">O segundo comando interrompe o serviço IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="611b8-126">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="611b8-127">O parâmetro **Force** é necessário para interromper um serviço que tem serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="611b8-127">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="611b8-128">O comando usa o parâmetro **Confirm** para solicitar a confirmação do usuário antes de parar cada serviço.</span><span class="sxs-lookup"><span data-stu-id="611b8-128">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="611b8-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="611b8-129">PARAMETERS</span></span>

### <span data-ttu-id="611b8-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="611b8-130">-DisplayName</span></span>

<span data-ttu-id="611b8-131">Especifica os nomes de exibição dos serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-131">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="611b8-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="611b8-133">-Excluir</span><span class="sxs-lookup"><span data-stu-id="611b8-133">-Exclude</span></span>

<span data-ttu-id="611b8-134">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="611b8-134">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="611b8-135">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="611b8-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="611b8-136">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="611b8-136">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="611b8-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="611b8-138">-Force</span><span class="sxs-lookup"><span data-stu-id="611b8-138">-Force</span></span>

<span data-ttu-id="611b8-139">Força o cmdlet a parar um serviço mesmo que esse serviço tenha serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="611b8-139">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="611b8-140">-Incluir</span><span class="sxs-lookup"><span data-stu-id="611b8-140">-Include</span></span>

<span data-ttu-id="611b8-141">Especifica os serviços que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="611b8-141">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="611b8-142">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="611b8-142">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="611b8-143">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="611b8-143">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="611b8-144">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-144">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="611b8-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="611b8-145">-InputObject</span></span>

<span data-ttu-id="611b8-146">Especifica objetos **ServiceController** que representam os serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-146">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="611b8-147">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="611b8-147">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="611b8-148">-Name</span><span class="sxs-lookup"><span data-stu-id="611b8-148">-Name</span></span>

<span data-ttu-id="611b8-149">Especifica os nomes de serviço dos serviços a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-149">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="611b8-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="611b8-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="611b8-151">-Nowait</span><span class="sxs-lookup"><span data-stu-id="611b8-151">-NoWait</span></span>

<span data-ttu-id="611b8-152">Indica que esse cmdlet usa a opção sem espera.</span><span class="sxs-lookup"><span data-stu-id="611b8-152">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="611b8-153">-PassThru</span><span class="sxs-lookup"><span data-stu-id="611b8-153">-PassThru</span></span>

<span data-ttu-id="611b8-154">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="611b8-154">Returns an object that represents the service.</span></span> <span data-ttu-id="611b8-155">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="611b8-155">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="611b8-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="611b8-156">-Confirm</span></span>

<span data-ttu-id="611b8-157">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="611b8-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="611b8-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="611b8-158">-WhatIf</span></span>

<span data-ttu-id="611b8-159">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="611b8-159">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="611b8-160">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="611b8-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="611b8-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="611b8-161">CommonParameters</span></span>

<span data-ttu-id="611b8-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="611b8-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="611b8-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="611b8-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="611b8-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="611b8-164">INPUTS</span></span>

### <span data-ttu-id="611b8-165">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="611b8-165">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="611b8-166">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém o nome de um serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="611b8-166">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="611b8-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="611b8-167">OUTPUTS</span></span>

### <span data-ttu-id="611b8-168">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="611b8-168">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="611b8-169">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você usar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="611b8-169">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="611b8-170">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="611b8-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="611b8-171">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="611b8-171">NOTES</span></span>

<span data-ttu-id="611b8-172">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="611b8-172">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="611b8-173">Você também pode consultar `Stop-Service` por seu alias interno, **spsv**.</span><span class="sxs-lookup"><span data-stu-id="611b8-173">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="611b8-174">Para obter mais informações, consulte about_Aliases.</span><span class="sxs-lookup"><span data-stu-id="611b8-174">For more information, see about_Aliases.</span></span>

<span data-ttu-id="611b8-175">`Stop-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="611b8-175">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="611b8-176">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="611b8-176">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="611b8-177">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="611b8-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="611b8-178">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="611b8-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="611b8-179">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="611b8-179">RELATED LINKS</span></span>

[<span data-ttu-id="611b8-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="611b8-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="611b8-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="611b8-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="611b8-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="611b8-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="611b8-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-186">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="611b8-187">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="611b8-187">Remove-Service</span></span>](Remove-Service.md)
