---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: a33cd0957fb37ce93334c08d21ef1b805188492f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342494"
---
# <span data-ttu-id="5dd51-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-103">Suspend-Service</span></span>

## <span data-ttu-id="5dd51-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5dd51-104">SYNOPSIS</span></span>
<span data-ttu-id="5dd51-105">Suspende (pausa) um ou mais serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="5dd51-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="5dd51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5dd51-106">SYNTAX</span></span>

### <span data-ttu-id="5dd51-107">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="5dd51-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5dd51-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="5dd51-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5dd51-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5dd51-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5dd51-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5dd51-110">DESCRIPTION</span></span>

<span data-ttu-id="5dd51-111">O `Suspend-Service` cmdlet envia uma mensagem de suspensão ao controlador de serviço do Windows para cada um dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="5dd51-111">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="5dd51-112">Enquanto estiver suspenso, o serviço ainda estará em execução, mas sua ação será interrompida até ser retomada, por exemplo, pelo `Resume-Service` cmdlet usando.</span><span class="sxs-lookup"><span data-stu-id="5dd51-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="5dd51-113">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa os serviços que você deseja suspender.</span><span class="sxs-lookup"><span data-stu-id="5dd51-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="5dd51-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5dd51-114">EXAMPLES</span></span>

### <span data-ttu-id="5dd51-115">Exemplo 1: suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="5dd51-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="5dd51-116">Este comando suspende o serviço Telnet (Tlntsvr) no computador local.</span><span class="sxs-lookup"><span data-stu-id="5dd51-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="5dd51-117">Exemplo 2: exibir o que aconteceria se você suspender os serviços</span><span class="sxs-lookup"><span data-stu-id="5dd51-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="5dd51-118">Esse comando informa o que aconteceria se você suspendesse os serviços que têm um nome de serviço que começa com o LANMAN.</span><span class="sxs-lookup"><span data-stu-id="5dd51-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="5dd51-119">Para suspender os serviços, execute novamente o comando sem o parâmetro **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-119">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="5dd51-120">Exemplo 3: obter e suspender um serviço</span><span class="sxs-lookup"><span data-stu-id="5dd51-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="5dd51-121">Esse comando usa o `Get-Service` cmdlet para obter um objeto que representa o serviço de Agendador de tarefas (agenda) no computador.</span><span class="sxs-lookup"><span data-stu-id="5dd51-121">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="5dd51-122">O operador de pipeline ( `|` ) passa o resultado para `Suspend-Service` , que suspende o serviço.</span><span class="sxs-lookup"><span data-stu-id="5dd51-122">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="5dd51-123">Exemplo 4: suspender todos os serviços que podem ser suspensos</span><span class="sxs-lookup"><span data-stu-id="5dd51-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="5dd51-124">Este comando suspende todos os serviços no computador que podem ser suspensos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-124">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="5dd51-125">Ele usa `Get-Service` para obter objetos que representam os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="5dd51-125">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="5dd51-126">O operador de pipeline passa os resultados para o `Where-Object` cmdlet, que seleciona apenas os serviços que têm um valor de `$True` para a propriedade **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-126">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="5dd51-127">Outro operador de pipeline passa os resultados para `Suspend-Service` .</span><span class="sxs-lookup"><span data-stu-id="5dd51-127">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="5dd51-128">O parâmetro **Confirm** solicita sua confirmação antes de suspender cada um dos serviços.</span><span class="sxs-lookup"><span data-stu-id="5dd51-128">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="5dd51-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5dd51-129">PARAMETERS</span></span>

### <span data-ttu-id="5dd51-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="5dd51-130">-DisplayName</span></span>

<span data-ttu-id="5dd51-131">Especifica os nomes de exibição dos serviços a serem suspensos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-131">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="5dd51-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5dd51-133">-Excluir</span><span class="sxs-lookup"><span data-stu-id="5dd51-133">-Exclude</span></span>

<span data-ttu-id="5dd51-134">Especifica os serviços a serem omitidos dos serviços especificados.</span><span class="sxs-lookup"><span data-stu-id="5dd51-134">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="5dd51-135">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="5dd51-136">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="5dd51-136">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="5dd51-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5dd51-138">-Incluir</span><span class="sxs-lookup"><span data-stu-id="5dd51-138">-Include</span></span>

<span data-ttu-id="5dd51-139">Especifica os serviços a serem suspensos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-139">Specifies services to suspend.</span></span> <span data-ttu-id="5dd51-140">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="5dd51-141">Insira um elemento Name ou padrão, como "\*s".</span><span class="sxs-lookup"><span data-stu-id="5dd51-141">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="5dd51-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5dd51-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5dd51-143">-InputObject</span></span>

<span data-ttu-id="5dd51-144">Especifica objetos **ServiceController** que representam os serviços a serem suspensos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="5dd51-145">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="5dd51-146">-Name</span><span class="sxs-lookup"><span data-stu-id="5dd51-146">-Name</span></span>

<span data-ttu-id="5dd51-147">Especifica os nomes de serviço dos serviços a serem suspensos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-147">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="5dd51-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5dd51-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="5dd51-149">O nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="5dd51-149">The parameter name is optional.</span></span> <span data-ttu-id="5dd51-150">Você pode usar o **nome** ou seu alias **,** ServiceName ou pode omitir o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5dd51-150">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="5dd51-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5dd51-151">-PassThru</span></span>

<span data-ttu-id="5dd51-152">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="5dd51-152">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="5dd51-153">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5dd51-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5dd51-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5dd51-154">-Confirm</span></span>

<span data-ttu-id="5dd51-155">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5dd51-155">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5dd51-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5dd51-156">-WhatIf</span></span>

<span data-ttu-id="5dd51-157">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5dd51-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5dd51-158">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5dd51-158">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5dd51-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5dd51-159">CommonParameters</span></span>

<span data-ttu-id="5dd51-160">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5dd51-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5dd51-161">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5dd51-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5dd51-162">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5dd51-162">INPUTS</span></span>

### <span data-ttu-id="5dd51-163">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="5dd51-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="5dd51-164">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5dd51-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="5dd51-165">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5dd51-165">OUTPUTS</span></span>

### <span data-ttu-id="5dd51-166">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="5dd51-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="5dd51-167">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="5dd51-168">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5dd51-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5dd51-169">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5dd51-169">NOTES</span></span>

- <span data-ttu-id="5dd51-170">`Suspend-Service` pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5dd51-170">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="5dd51-171">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="5dd51-171">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="5dd51-172">`Suspend-Service` o pode suspender apenas os serviços que dão suporte à suspensão e retomada.</span><span class="sxs-lookup"><span data-stu-id="5dd51-172">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="5dd51-173">Para determinar se um serviço específico pode ser suspenso, use o `Get-Service` cmdlet junto com a propriedade **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-173">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="5dd51-174">Por exemplo, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span><span class="sxs-lookup"><span data-stu-id="5dd51-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="5dd51-175">Para localizar todos os serviços no computador que podem ser suspensos, digite `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .</span><span class="sxs-lookup"><span data-stu-id="5dd51-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="5dd51-176">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="5dd51-176">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="5dd51-177">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="5dd51-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="5dd51-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5dd51-178">RELATED LINKS</span></span>

[<span data-ttu-id="5dd51-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="5dd51-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="5dd51-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="5dd51-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="5dd51-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="5dd51-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="5dd51-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="5dd51-185">Stop-Service</span></span>](Stop-Service.md)
