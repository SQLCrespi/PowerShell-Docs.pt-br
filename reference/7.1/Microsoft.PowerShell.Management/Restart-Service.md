---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: fee113e20b178c2b86b8f95cd3147f991aed8efe
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346625"
---
# <span data-ttu-id="59d88-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-103">Restart-Service</span></span>

## <span data-ttu-id="59d88-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="59d88-104">SYNOPSIS</span></span>
<span data-ttu-id="59d88-105">Interrompe e inicia um ou mais serviços.</span><span class="sxs-lookup"><span data-stu-id="59d88-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="59d88-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59d88-106">SYNTAX</span></span>

### <span data-ttu-id="59d88-107">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="59d88-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="59d88-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="59d88-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="59d88-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="59d88-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="59d88-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59d88-110">DESCRIPTION</span></span>

<span data-ttu-id="59d88-111">O `Restart-Service` cmdlet envia uma mensagem de parada e, em seguida, uma mensagem de início para o controlador de serviço do Windows para um serviço especificado.</span><span class="sxs-lookup"><span data-stu-id="59d88-111">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="59d88-112">Se um serviço já foi interrompido, ele é iniciado sem notificá-lo de um erro.</span><span class="sxs-lookup"><span data-stu-id="59d88-112">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="59d88-113">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto que representa cada serviço que você deseja reiniciar.</span><span class="sxs-lookup"><span data-stu-id="59d88-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="59d88-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="59d88-114">EXAMPLES</span></span>

### <span data-ttu-id="59d88-115">Exemplo 1: reiniciar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="59d88-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="59d88-116">Este comando reinicia o serviço de instrumentação de gerenciamento do Windows (WinMgmt) no computador local.</span><span class="sxs-lookup"><span data-stu-id="59d88-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="59d88-117">Exemplo 2: excluir um serviço</span><span class="sxs-lookup"><span data-stu-id="59d88-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="59d88-118">Esse comando reinicia os serviços que têm um nome de exibição que começa com net, exceto pelo serviço de logon de rede.</span><span class="sxs-lookup"><span data-stu-id="59d88-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="59d88-119">Exemplo 3: iniciar todos os serviços de rede interrompidos</span><span class="sxs-lookup"><span data-stu-id="59d88-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="59d88-120">Esse comando inicia todos os serviços de rede interrompidos no computador.</span><span class="sxs-lookup"><span data-stu-id="59d88-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="59d88-121">Esse comando usa o `Get-Service` cmdlet para obter objetos que representam os serviços cujo nome do serviço começa com net.</span><span class="sxs-lookup"><span data-stu-id="59d88-121">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="59d88-122">O operador de pipeline ( `|` ) envia o objeto de serviços para o `Where-Object` cmdlet, que seleciona apenas os serviços que têm um status de parado.</span><span class="sxs-lookup"><span data-stu-id="59d88-122">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="59d88-123">Outro operador de pipeline envia os serviços selecionados para `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="59d88-123">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="59d88-124">Na prática, você usaria o parâmetro **WhatIf** para determinar o efeito do comando antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="59d88-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="59d88-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59d88-125">PARAMETERS</span></span>

### <span data-ttu-id="59d88-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="59d88-126">-DisplayName</span></span>

<span data-ttu-id="59d88-127">Especifica os nomes de exibição dos serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="59d88-127">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="59d88-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="59d88-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59d88-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="59d88-129">-Exclude</span></span>

<span data-ttu-id="59d88-130">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="59d88-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="59d88-131">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="59d88-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="59d88-132">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="59d88-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="59d88-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="59d88-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59d88-134">-Force</span><span class="sxs-lookup"><span data-stu-id="59d88-134">-Force</span></span>

<span data-ttu-id="59d88-135">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="59d88-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="59d88-136">-Incluir</span><span class="sxs-lookup"><span data-stu-id="59d88-136">-Include</span></span>

<span data-ttu-id="59d88-137">Especifica os serviços que este cmdlet reinicia.</span><span class="sxs-lookup"><span data-stu-id="59d88-137">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="59d88-138">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="59d88-138">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="59d88-139">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="59d88-139">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="59d88-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="59d88-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59d88-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="59d88-141">-InputObject</span></span>

<span data-ttu-id="59d88-142">Especifica objetos **ServiceController** que representam os serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="59d88-142">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="59d88-143">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="59d88-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="59d88-144">-Name</span><span class="sxs-lookup"><span data-stu-id="59d88-144">-Name</span></span>

<span data-ttu-id="59d88-145">Especifica os nomes de serviço dos serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="59d88-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="59d88-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="59d88-146">-PassThru</span></span>

<span data-ttu-id="59d88-147">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="59d88-147">Returns an object that represents the service.</span></span> <span data-ttu-id="59d88-148">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="59d88-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="59d88-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="59d88-149">-Confirm</span></span>

<span data-ttu-id="59d88-150">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59d88-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="59d88-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="59d88-151">-WhatIf</span></span>

<span data-ttu-id="59d88-152">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="59d88-152">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="59d88-153">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="59d88-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="59d88-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59d88-154">CommonParameters</span></span>

<span data-ttu-id="59d88-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59d88-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59d88-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59d88-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59d88-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="59d88-157">INPUTS</span></span>

### <span data-ttu-id="59d88-158">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="59d88-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="59d88-159">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59d88-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="59d88-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="59d88-160">OUTPUTS</span></span>

### <span data-ttu-id="59d88-161">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="59d88-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="59d88-162">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço reiniciado, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="59d88-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="59d88-163">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="59d88-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="59d88-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="59d88-164">NOTES</span></span>

<span data-ttu-id="59d88-165">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="59d88-165">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="59d88-166">`Restart-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="59d88-166">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="59d88-167">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="59d88-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="59d88-168">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` ".</span><span class="sxs-lookup"><span data-stu-id="59d88-168">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="59d88-169">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="59d88-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="59d88-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="59d88-170">RELATED LINKS</span></span>

[<span data-ttu-id="59d88-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="59d88-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="59d88-173">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-173">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="59d88-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="59d88-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="59d88-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="59d88-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="59d88-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="59d88-178">Remove-Service</span></span>](Remove-Service.md)
