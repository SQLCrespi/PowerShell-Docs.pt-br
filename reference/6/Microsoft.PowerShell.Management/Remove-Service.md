---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: c55a7ef01171e63e8c64ee03446ca1bdcd838e2a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194551"
---
# <span data-ttu-id="87446-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="87446-103">Remove-Service</span></span>

## <span data-ttu-id="87446-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="87446-104">SYNOPSIS</span></span>
<span data-ttu-id="87446-105">Remove um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="87446-105">Removes a Windows service.</span></span>

## <span data-ttu-id="87446-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87446-106">SYNTAX</span></span>

### <span data-ttu-id="87446-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="87446-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="87446-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="87446-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="87446-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="87446-109">DESCRIPTION</span></span>

<span data-ttu-id="87446-110">O `Remove-Service` cmdlet Remove um serviço do Windows no registro e no banco de dados do serviço.</span><span class="sxs-lookup"><span data-stu-id="87446-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="87446-111">O `Remove-Service` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="87446-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="87446-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="87446-112">EXAMPLES</span></span>

### <span data-ttu-id="87446-113">Exemplo 1: remover um serviço</span><span class="sxs-lookup"><span data-stu-id="87446-113">Example 1: Remove a service</span></span>

<span data-ttu-id="87446-114">Isso remove um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="87446-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="87446-115">Exemplo 2: remover um serviço usando o nome de exibição</span><span class="sxs-lookup"><span data-stu-id="87446-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="87446-116">Este exemplo remove um serviço chamado TestService.</span><span class="sxs-lookup"><span data-stu-id="87446-116">This example removes a service named TestService.</span></span> <span data-ttu-id="87446-117">O comando usa `Get-Service` para obter um objeto que representa o serviço TestService usando o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="87446-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="87446-118">O operador de pipeline ( `|` ) canaliza o objeto para `Remove-Service` , que remove o serviço.</span><span class="sxs-lookup"><span data-stu-id="87446-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="87446-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87446-119">PARAMETERS</span></span>

### <span data-ttu-id="87446-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="87446-120">-InputObject</span></span>

<span data-ttu-id="87446-121">Especifica objetos **ServiceController** que representam os serviços a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="87446-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="87446-122">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="87446-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="87446-123">-Name</span><span class="sxs-lookup"><span data-stu-id="87446-123">-Name</span></span>

<span data-ttu-id="87446-124">Especifica os nomes de serviço dos serviços a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="87446-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="87446-125">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="87446-125">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="87446-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="87446-126">-Confirm</span></span>

<span data-ttu-id="87446-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="87446-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="87446-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="87446-128">-WhatIf</span></span>

<span data-ttu-id="87446-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="87446-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="87446-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="87446-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="87446-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="87446-131">CommonParameters</span></span>

<span data-ttu-id="87446-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="87446-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87446-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="87446-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87446-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="87446-134">INPUTS</span></span>

### <span data-ttu-id="87446-135">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="87446-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="87446-136">É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém o nome de um serviço para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="87446-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="87446-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="87446-137">OUTPUTS</span></span>

### <span data-ttu-id="87446-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="87446-138">None</span></span>

<span data-ttu-id="87446-139">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="87446-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="87446-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="87446-140">NOTES</span></span>

<span data-ttu-id="87446-141">Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="87446-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="87446-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="87446-142">RELATED LINKS</span></span>

[<span data-ttu-id="87446-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="87446-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="87446-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="87446-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="87446-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="87446-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="87446-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="87446-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="87446-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="87446-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="87446-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="87446-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="87446-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="87446-149">Suspend-Service</span></span>](Suspend-Service.md)
