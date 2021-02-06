---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 8ce2182117167d93c8f7abd86eeb2c79abdf09c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595982"
---
# <span data-ttu-id="86603-102">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="86603-102">Resume-Service</span></span>

## <span data-ttu-id="86603-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="86603-103">SYNOPSIS</span></span>
<span data-ttu-id="86603-104">Retoma um ou mais serviços suspensos (pausados).</span><span class="sxs-lookup"><span data-stu-id="86603-104">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="86603-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="86603-105">SYNTAX</span></span>

### <span data-ttu-id="86603-106">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="86603-106">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="86603-107">Padrão</span><span class="sxs-lookup"><span data-stu-id="86603-107">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="86603-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="86603-108">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="86603-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="86603-109">DESCRIPTION</span></span>

<span data-ttu-id="86603-110">O `Resume-Service` cmdlet envia uma mensagem de retomada para o controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="86603-110">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="86603-111">Se um serviço for suspenso, ele será retomado.</span><span class="sxs-lookup"><span data-stu-id="86603-111">If a service is suspended, it resumes.</span></span> <span data-ttu-id="86603-112">Se estiver em execução no momento, a mensagem será ignorada.</span><span class="sxs-lookup"><span data-stu-id="86603-112">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="86603-113">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa os serviços que você deseja retomar.</span><span class="sxs-lookup"><span data-stu-id="86603-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="86603-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="86603-114">EXAMPLES</span></span>

### <span data-ttu-id="86603-115">Exemplo 1: retomar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="86603-115">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="86603-116">Esse comando retoma o serviço de notificação de eventos do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="86603-116">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="86603-117">O nome do serviço é representado no comando pelo sens.</span><span class="sxs-lookup"><span data-stu-id="86603-117">The service name is represented in the command by sens.</span></span> <span data-ttu-id="86603-118">O comando usa o parâmetro **Name** para especificar o nome do serviço do serviço, mas o comando omite o nome do parâmetro porque o nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="86603-118">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="86603-119">Exemplo 2: retomar todos os serviços suspensos</span><span class="sxs-lookup"><span data-stu-id="86603-119">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="86603-120">Esse comando retoma todos os serviços suspensos no computador.</span><span class="sxs-lookup"><span data-stu-id="86603-120">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="86603-121">O `Get-Service` comando do cmdlet obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="86603-121">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="86603-122">O operador de pipeline ( `|` ) passa os resultados para o `Where-Object` cmdlet, que seleciona os serviços que têm uma propriedade **status** em pausa.</span><span class="sxs-lookup"><span data-stu-id="86603-122">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="86603-123">O próximo operador de pipeline envia os resultados para `Resume-Service` , o que retoma os serviços em pausa.</span><span class="sxs-lookup"><span data-stu-id="86603-123">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="86603-124">Na prática, você usaria o parâmetro **WhatIf** para determinar o efeito do comando antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="86603-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="86603-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="86603-125">PARAMETERS</span></span>

### <span data-ttu-id="86603-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="86603-126">-DisplayName</span></span>

<span data-ttu-id="86603-127">Especifica os nomes de exibição dos serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="86603-127">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="86603-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="86603-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="86603-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="86603-129">-Exclude</span></span>

<span data-ttu-id="86603-130">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="86603-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="86603-131">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="86603-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="86603-132">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="86603-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="86603-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="86603-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="86603-134">-Incluir</span><span class="sxs-lookup"><span data-stu-id="86603-134">-Include</span></span>

<span data-ttu-id="86603-135">Especifica os serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="86603-135">Specifies services to resume.</span></span> <span data-ttu-id="86603-136">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="86603-136">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="86603-137">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="86603-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="86603-138">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="86603-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="86603-139">-InputObject</span><span class="sxs-lookup"><span data-stu-id="86603-139">-InputObject</span></span>

<span data-ttu-id="86603-140">Especifica objetos **ServiceController** que representam os serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="86603-140">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="86603-141">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="86603-141">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="86603-142">-Name</span><span class="sxs-lookup"><span data-stu-id="86603-142">-Name</span></span>

<span data-ttu-id="86603-143">Especifica os nomes de serviço dos serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="86603-143">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="86603-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="86603-144">-PassThru</span></span>

<span data-ttu-id="86603-145">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="86603-145">Returns an object that represents the service.</span></span> <span data-ttu-id="86603-146">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="86603-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="86603-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="86603-147">-Confirm</span></span>

<span data-ttu-id="86603-148">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86603-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="86603-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="86603-149">-WhatIf</span></span>

<span data-ttu-id="86603-150">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="86603-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="86603-151">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="86603-151">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="86603-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="86603-152">CommonParameters</span></span>

<span data-ttu-id="86603-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="86603-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="86603-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="86603-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="86603-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="86603-155">INPUTS</span></span>

### <span data-ttu-id="86603-156">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="86603-156">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="86603-157">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86603-157">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="86603-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="86603-158">OUTPUTS</span></span>

### <span data-ttu-id="86603-159">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="86603-159">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="86603-160">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço retomado, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="86603-160">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="86603-161">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="86603-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="86603-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="86603-162">NOTES</span></span>

<span data-ttu-id="86603-163">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="86603-163">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="86603-164">O status dos serviços que foram suspensos está em pausa.</span><span class="sxs-lookup"><span data-stu-id="86603-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="86603-165">Quando os serviços são retomados, seu status é em execução.</span><span class="sxs-lookup"><span data-stu-id="86603-165">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="86603-166">`Resume-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="86603-166">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="86603-167">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="86603-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="86603-168">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="86603-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="86603-169">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="86603-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="86603-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="86603-170">RELATED LINKS</span></span>

[<span data-ttu-id="86603-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="86603-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="86603-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="86603-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="86603-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="86603-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="86603-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="86603-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="86603-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="86603-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="86603-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="86603-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="86603-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="86603-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="86603-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="86603-178">Remove-Service</span></span>](Remove-Service.md)
