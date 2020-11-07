---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: ee44a29c4b657828accc2d8b5e5773b5c1ea6086
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345146"
---
# <span data-ttu-id="7b368-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-103">Resume-Service</span></span>

## <span data-ttu-id="7b368-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7b368-104">SYNOPSIS</span></span>
<span data-ttu-id="7b368-105">Retoma um ou mais serviços suspensos (pausados).</span><span class="sxs-lookup"><span data-stu-id="7b368-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="7b368-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b368-106">SYNTAX</span></span>

### <span data-ttu-id="7b368-107">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="7b368-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7b368-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="7b368-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="7b368-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7b368-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7b368-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7b368-110">DESCRIPTION</span></span>

<span data-ttu-id="7b368-111">O `Resume-Service` cmdlet envia uma mensagem de retomada para o controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="7b368-111">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="7b368-112">Se um serviço for suspenso, ele será retomado.</span><span class="sxs-lookup"><span data-stu-id="7b368-112">If a service is suspended, it resumes.</span></span> <span data-ttu-id="7b368-113">Se estiver em execução no momento, a mensagem será ignorada.</span><span class="sxs-lookup"><span data-stu-id="7b368-113">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="7b368-114">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa os serviços que você deseja retomar.</span><span class="sxs-lookup"><span data-stu-id="7b368-114">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="7b368-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7b368-115">EXAMPLES</span></span>

### <span data-ttu-id="7b368-116">Exemplo 1: retomar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="7b368-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="7b368-117">Esse comando retoma o serviço de notificação de eventos do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="7b368-117">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="7b368-118">O nome do serviço é representado no comando pelo sens.</span><span class="sxs-lookup"><span data-stu-id="7b368-118">The service name is represented in the command by sens.</span></span> <span data-ttu-id="7b368-119">O comando usa o parâmetro **Name** para especificar o nome do serviço do serviço, mas o comando omite o nome do parâmetro porque o nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="7b368-119">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="7b368-120">Exemplo 2: retomar todos os serviços suspensos</span><span class="sxs-lookup"><span data-stu-id="7b368-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="7b368-121">Esse comando retoma todos os serviços suspensos no computador.</span><span class="sxs-lookup"><span data-stu-id="7b368-121">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="7b368-122">O `Get-Service` comando do cmdlet obtém todos os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="7b368-122">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="7b368-123">O operador de pipeline ( `|` ) passa os resultados para o `Where-Object` cmdlet, que seleciona os serviços que têm uma propriedade **status** em pausa.</span><span class="sxs-lookup"><span data-stu-id="7b368-123">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="7b368-124">O próximo operador de pipeline envia os resultados para `Resume-Service` , o que retoma os serviços em pausa.</span><span class="sxs-lookup"><span data-stu-id="7b368-124">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="7b368-125">Na prática, você usaria o parâmetro **WhatIf** para determinar o efeito do comando antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="7b368-125">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="7b368-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b368-126">PARAMETERS</span></span>

### <span data-ttu-id="7b368-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="7b368-127">-DisplayName</span></span>

<span data-ttu-id="7b368-128">Especifica os nomes de exibição dos serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="7b368-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="7b368-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b368-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7b368-130">-Excluir</span><span class="sxs-lookup"><span data-stu-id="7b368-130">-Exclude</span></span>

<span data-ttu-id="7b368-131">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="7b368-131">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="7b368-132">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="7b368-132">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7b368-133">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="7b368-133">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="7b368-134">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b368-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7b368-135">-Incluir</span><span class="sxs-lookup"><span data-stu-id="7b368-135">-Include</span></span>

<span data-ttu-id="7b368-136">Especifica os serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="7b368-136">Specifies services to resume.</span></span> <span data-ttu-id="7b368-137">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="7b368-137">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="7b368-138">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="7b368-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="7b368-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b368-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7b368-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7b368-140">-InputObject</span></span>

<span data-ttu-id="7b368-141">Especifica objetos **ServiceController** que representam os serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="7b368-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="7b368-142">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="7b368-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7b368-143">-Name</span><span class="sxs-lookup"><span data-stu-id="7b368-143">-Name</span></span>

<span data-ttu-id="7b368-144">Especifica os nomes de serviço dos serviços a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="7b368-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="7b368-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7b368-145">-PassThru</span></span>

<span data-ttu-id="7b368-146">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="7b368-146">Returns an object that represents the service.</span></span> <span data-ttu-id="7b368-147">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7b368-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7b368-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7b368-148">-Confirm</span></span>

<span data-ttu-id="7b368-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7b368-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7b368-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7b368-150">-WhatIf</span></span>

<span data-ttu-id="7b368-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7b368-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7b368-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7b368-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7b368-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7b368-153">CommonParameters</span></span>

<span data-ttu-id="7b368-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7b368-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7b368-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7b368-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7b368-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7b368-156">INPUTS</span></span>

### <span data-ttu-id="7b368-157">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="7b368-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="7b368-158">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7b368-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="7b368-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7b368-159">OUTPUTS</span></span>

### <span data-ttu-id="7b368-160">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="7b368-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="7b368-161">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço retomado, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="7b368-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="7b368-162">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="7b368-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7b368-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7b368-163">NOTES</span></span>

<span data-ttu-id="7b368-164">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="7b368-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="7b368-165">O status dos serviços que foram suspensos está em pausa.</span><span class="sxs-lookup"><span data-stu-id="7b368-165">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="7b368-166">Quando os serviços são retomados, seu status é em execução.</span><span class="sxs-lookup"><span data-stu-id="7b368-166">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="7b368-167">`Resume-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="7b368-167">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="7b368-168">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="7b368-168">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="7b368-169">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="7b368-169">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="7b368-170">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="7b368-170">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="7b368-171">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7b368-171">RELATED LINKS</span></span>

[<span data-ttu-id="7b368-172">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-172">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="7b368-173">New-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-173">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="7b368-174">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-174">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="7b368-175">Set-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-175">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="7b368-176">Start-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-176">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="7b368-177">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-177">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="7b368-178">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-178">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="7b368-179">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="7b368-179">Remove-Service</span></span>](Remove-Service.md)
