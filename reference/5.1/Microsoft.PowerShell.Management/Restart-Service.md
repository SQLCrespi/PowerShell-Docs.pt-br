---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: b5af4f55166993e54048dd76bb8345550718c170
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193936"
---
# <span data-ttu-id="557c4-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-103">Restart-Service</span></span>

## <span data-ttu-id="557c4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="557c4-104">SYNOPSIS</span></span>
<span data-ttu-id="557c4-105">Interrompe e inicia um ou mais serviços.</span><span class="sxs-lookup"><span data-stu-id="557c4-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="557c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="557c4-106">SYNTAX</span></span>

### <span data-ttu-id="557c4-107">Inputobject (padrão)</span><span class="sxs-lookup"><span data-stu-id="557c4-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="557c4-108">Padrão</span><span class="sxs-lookup"><span data-stu-id="557c4-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="557c4-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="557c4-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="557c4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="557c4-110">DESCRIPTION</span></span>

<span data-ttu-id="557c4-111">O cmdlet **Restart-Service** envia uma mensagem de parada e, em seguida, uma mensagem de início para o controlador de serviço do Windows para um serviço especificado.</span><span class="sxs-lookup"><span data-stu-id="557c4-111">The **Restart-Service** cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span>
<span data-ttu-id="557c4-112">Se um serviço já foi interrompido, ele é iniciado sem notificá-lo de um erro.</span><span class="sxs-lookup"><span data-stu-id="557c4-112">If a service was already stopped, it is started without notifying you of an error.</span></span>
<span data-ttu-id="557c4-113">Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro *InputObject* para passar um objeto que representa cada serviço que você deseja reiniciar.</span><span class="sxs-lookup"><span data-stu-id="557c4-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="557c4-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="557c4-114">EXAMPLES</span></span>

### <span data-ttu-id="557c4-115">Exemplo 1: reiniciar um serviço no computador local</span><span class="sxs-lookup"><span data-stu-id="557c4-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="557c4-116">Este comando reinicia o serviço de instrumentação de gerenciamento do Windows (WinMgmt) no computador local.</span><span class="sxs-lookup"><span data-stu-id="557c4-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="557c4-117">Exemplo 2: excluir um serviço</span><span class="sxs-lookup"><span data-stu-id="557c4-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="557c4-118">Esse comando reinicia os serviços que têm um nome de exibição que começa com net, exceto pelo serviço de logon de rede.</span><span class="sxs-lookup"><span data-stu-id="557c4-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="557c4-119">Exemplo 3: iniciar todos os serviços de rede interrompidos</span><span class="sxs-lookup"><span data-stu-id="557c4-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="557c4-120">Esse comando inicia todos os serviços de rede interrompidos no computador.</span><span class="sxs-lookup"><span data-stu-id="557c4-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="557c4-121">Esse comando usa o cmdlet Get-Service para obter objetos que representam os serviços cujo nome do serviço começa com net.</span><span class="sxs-lookup"><span data-stu-id="557c4-121">This command uses the Get-Service cmdlet to get objects that represent the services whose service name starts with net.</span></span>
<span data-ttu-id="557c4-122">O operador de pipeline (|) envia o objeto de serviços para o cmdlet Where-Object, que seleciona apenas os serviços que têm um status de parado.</span><span class="sxs-lookup"><span data-stu-id="557c4-122">The pipeline operator (|) sends the services object to the Where-Object cmdlet, which selects only the services that have a status of stopped.</span></span>
<span data-ttu-id="557c4-123">Outro operador de pipeline envia os serviços selecionados para **Restart-Service** .</span><span class="sxs-lookup"><span data-stu-id="557c4-123">Another pipeline operator sends the selected services to **Restart-Service** .</span></span>

<span data-ttu-id="557c4-124">Na prática, você usaria o parâmetro *WhatIf* para determinar o efeito do comando antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="557c4-124">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="557c4-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="557c4-125">PARAMETERS</span></span>

### <span data-ttu-id="557c4-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="557c4-126">-DisplayName</span></span>

<span data-ttu-id="557c4-127">Especifica os nomes de exibição dos serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="557c4-127">Specifies the display names of services to restarted.</span></span>
<span data-ttu-id="557c4-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="557c4-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="557c4-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="557c4-129">-Exclude</span></span>

<span data-ttu-id="557c4-130">Especifica os serviços que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="557c4-130">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="557c4-131">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="557c4-131">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="557c4-132">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="557c4-132">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="557c4-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="557c4-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="557c4-134">-Force</span><span class="sxs-lookup"><span data-stu-id="557c4-134">-Force</span></span>

<span data-ttu-id="557c4-135">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="557c4-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="557c4-136">-Incluir</span><span class="sxs-lookup"><span data-stu-id="557c4-136">-Include</span></span>

<span data-ttu-id="557c4-137">Especifica os serviços que este cmdlet reinicia.</span><span class="sxs-lookup"><span data-stu-id="557c4-137">Specifies services that this cmdlet restarts.</span></span>
<span data-ttu-id="557c4-138">O valor desse parâmetro qualifica o parâmetro de *nome* .</span><span class="sxs-lookup"><span data-stu-id="557c4-138">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="557c4-139">Insira um elemento de nome ou padrão, como s \*.</span><span class="sxs-lookup"><span data-stu-id="557c4-139">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="557c4-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="557c4-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="557c4-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="557c4-141">-InputObject</span></span>

<span data-ttu-id="557c4-142">Especifica objetos **ServiceController** que representam os serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="557c4-142">Specifies **ServiceController** objects that represent the services to restart.</span></span>
<span data-ttu-id="557c4-143">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="557c4-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="557c4-144">-Name</span><span class="sxs-lookup"><span data-stu-id="557c4-144">-Name</span></span>

<span data-ttu-id="557c4-145">Especifica os nomes de serviço dos serviços a serem reiniciados.</span><span class="sxs-lookup"><span data-stu-id="557c4-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="557c4-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="557c4-146">-PassThru</span></span>

<span data-ttu-id="557c4-147">Retorna um objeto que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="557c4-147">Returns an object that represents the service.</span></span>
<span data-ttu-id="557c4-148">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="557c4-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="557c4-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="557c4-149">-Confirm</span></span>

<span data-ttu-id="557c4-150">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="557c4-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="557c4-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="557c4-151">-WhatIf</span></span>

<span data-ttu-id="557c4-152">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="557c4-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="557c4-153">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="557c4-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="557c4-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="557c4-154">CommonParameters</span></span>

<span data-ttu-id="557c4-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="557c4-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="557c4-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="557c4-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="557c4-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="557c4-157">INPUTS</span></span>

### <span data-ttu-id="557c4-158">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="557c4-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="557c4-159">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="557c4-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="557c4-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="557c4-160">OUTPUTS</span></span>

### <span data-ttu-id="557c4-161">Nenhum, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="557c4-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="557c4-162">Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço reiniciado, se você especificar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="557c4-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="557c4-163">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="557c4-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="557c4-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="557c4-164">NOTES</span></span>

* <span data-ttu-id="557c4-165">**Restart-Service** pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="557c4-165">**Restart-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="557c4-166">Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="557c4-166">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="557c4-167">Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite **Get-Service** ".</span><span class="sxs-lookup"><span data-stu-id="557c4-167">To find the service names and display names of the services on your system, type **Get-Service** ".</span></span> <span data-ttu-id="557c4-168">Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="557c4-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="557c4-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="557c4-169">RELATED LINKS</span></span>

[<span data-ttu-id="557c4-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="557c4-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="557c4-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="557c4-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="557c4-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="557c4-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="557c4-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="557c4-176">Suspend-Service</span></span>](Suspend-Service.md)
