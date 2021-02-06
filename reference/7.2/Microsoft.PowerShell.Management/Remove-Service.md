---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: 645efc2d271a3b95801c8d0d264ee33ed788f15f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596189"
---
# <span data-ttu-id="09743-102">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="09743-102">Remove-Service</span></span>

## <span data-ttu-id="09743-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="09743-103">SYNOPSIS</span></span>
<span data-ttu-id="09743-104">Remove um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="09743-104">Removes a Windows service.</span></span>

## <span data-ttu-id="09743-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09743-105">SYNTAX</span></span>

### <span data-ttu-id="09743-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="09743-106">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="09743-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="09743-107">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="09743-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09743-108">DESCRIPTION</span></span>

<span data-ttu-id="09743-109">O `Remove-Service` cmdlet Remove um serviço do Windows no registro e no banco de dados do serviço.</span><span class="sxs-lookup"><span data-stu-id="09743-109">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="09743-110">O `Remove-Service` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="09743-110">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="09743-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="09743-111">EXAMPLES</span></span>

### <span data-ttu-id="09743-112">Exemplo 1: remover um serviço</span><span class="sxs-lookup"><span data-stu-id="09743-112">Example 1: Remove a service</span></span>

<span data-ttu-id="09743-113">Isso remove um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="09743-113">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="09743-114">Exemplo 2: remover um serviço usando o nome de exibição</span><span class="sxs-lookup"><span data-stu-id="09743-114">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="09743-115">Este exemplo remove um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="09743-115">This example removes a service named TestService.</span></span> <span data-ttu-id="09743-116">O comando usa `Get-Service` para obter um objeto que representa o serviço TestService usando o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="09743-116">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="09743-117">O operador de pipeline ( `|` ) canaliza o objeto para `Remove-Service` , que remove o serviço.</span><span class="sxs-lookup"><span data-stu-id="09743-117">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="09743-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09743-118">PARAMETERS</span></span>

### <span data-ttu-id="09743-119">-InputObject</span><span class="sxs-lookup"><span data-stu-id="09743-119">-InputObject</span></span>

<span data-ttu-id="09743-120">Especifica objetos **ServiceController** que representam os serviços a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="09743-120">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="09743-121">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="09743-121">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="09743-122">-Name</span><span class="sxs-lookup"><span data-stu-id="09743-122">-Name</span></span>

<span data-ttu-id="09743-123">Especifica os nomes de serviço dos serviços a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="09743-123">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="09743-124">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="09743-124">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="09743-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="09743-125">-Confirm</span></span>

<span data-ttu-id="09743-126">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09743-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="09743-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="09743-127">-WhatIf</span></span>

<span data-ttu-id="09743-128">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="09743-128">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="09743-129">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="09743-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="09743-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="09743-130">CommonParameters</span></span>

<span data-ttu-id="09743-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="09743-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09743-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="09743-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="09743-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="09743-133">INPUTS</span></span>

### <span data-ttu-id="09743-134">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="09743-134">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="09743-135">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém o nome de um serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09743-135">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="09743-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="09743-136">OUTPUTS</span></span>

### <span data-ttu-id="09743-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="09743-137">None</span></span>

<span data-ttu-id="09743-138">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="09743-138">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="09743-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="09743-139">NOTES</span></span>

<span data-ttu-id="09743-140">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="09743-140">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="09743-141">Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="09743-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="09743-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="09743-142">RELATED LINKS</span></span>

[<span data-ttu-id="09743-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="09743-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="09743-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="09743-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="09743-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="09743-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="09743-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="09743-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="09743-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="09743-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="09743-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="09743-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="09743-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="09743-149">Suspend-Service</span></span>](Suspend-Service.md)
