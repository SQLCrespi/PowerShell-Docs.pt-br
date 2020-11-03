---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194140"
---
# <span data-ttu-id="d8824-103">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d8824-103">Restore-DscConfiguration</span></span>

## <span data-ttu-id="d8824-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d8824-104">SYNOPSIS</span></span>
<span data-ttu-id="d8824-105">Reaplica a configuração anterior para o nó.</span><span class="sxs-lookup"><span data-stu-id="d8824-105">Reapplies the previous configuration for the node.</span></span>

## <span data-ttu-id="d8824-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8824-106">SYNTAX</span></span>

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="d8824-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8824-107">DESCRIPTION</span></span>
<span data-ttu-id="d8824-108">O cmdlet **Restore-DscConfiguration** reaplica a configuração anterior para o nó, se existir uma configuração anterior.</span><span class="sxs-lookup"><span data-stu-id="d8824-108">The **Restore-DscConfiguration** cmdlet reapplies the previous configuration for the node, if a previous configuration exists.</span></span>
<span data-ttu-id="d8824-109">Especifique computadores usando sessões CIM (Common Information Model).</span><span class="sxs-lookup"><span data-stu-id="d8824-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="d8824-110">Se você não especificar um computador de destino, o cmdlet restaurará a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="d8824-110">If you do not specify a target computer, the cmdlet restores the configuration of the local computer.</span></span>
<span data-ttu-id="d8824-111">Se não houver nenhuma configuração anterior para um nó específico, esse cmdlet retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="d8824-111">If there is no previous configuration for a particular node, this cmdlet returns an error message.</span></span>

<span data-ttu-id="d8824-112">Este cmdlet não oferece suporte ao parâmetro **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="d8824-112">This cmdlet does not support the **Confirm** parameter.</span></span>

## <span data-ttu-id="d8824-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d8824-113">EXAMPLES</span></span>

### <span data-ttu-id="d8824-114">Exemplo 1: restaurar a configuração do computador local</span><span class="sxs-lookup"><span data-stu-id="d8824-114">Example 1: Restore the configuration for the local computer</span></span>

```
PS C:\> Restore-DscConfiguration
```

<span data-ttu-id="d8824-115">Este comando restaura a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="d8824-115">This command restores the configuration for the local computer.</span></span>

### <span data-ttu-id="d8824-116">Exemplo 2: restaurar a configuração para um computador especificado</span><span class="sxs-lookup"><span data-stu-id="d8824-116">Example 2: Restore configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

<span data-ttu-id="d8824-117">Este exemplo restaura a configuração em um computador especificado por uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d8824-117">This example restores configuration on a computer specified by a CIM session.</span></span>
<span data-ttu-id="d8824-118">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8824-118">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="d8824-119">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="d8824-119">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="d8824-120">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="d8824-120">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="d8824-121">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="d8824-121">The command prompts you for a password.</span></span>
<span data-ttu-id="d8824-122">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="d8824-122">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="d8824-123">O segundo comando restaura a configuração atual dos computadores identificados pelos objetos **CimSession** armazenados na variável $Session, nesse caso, o computador chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="d8824-123">The second command restores the configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="d8824-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8824-124">PARAMETERS</span></span>

### <span data-ttu-id="d8824-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d8824-125">-AsJob</span></span>
<span data-ttu-id="d8824-126">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d8824-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="d8824-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="d8824-127">-CimSession</span></span>
<span data-ttu-id="d8824-128">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d8824-128">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="d8824-129">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet **New-CimSession** ou **Get-CimSession** .</span><span class="sxs-lookup"><span data-stu-id="d8824-129">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8824-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d8824-130">-ThrottleLimit</span></span>
<span data-ttu-id="d8824-131">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8824-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8824-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d8824-132">-Confirm</span></span>
<span data-ttu-id="d8824-133">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8824-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d8824-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d8824-134">-WhatIf</span></span>
<span data-ttu-id="d8824-135">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d8824-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d8824-136">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d8824-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d8824-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8824-137">CommonParameters</span></span>
<span data-ttu-id="d8824-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8824-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8824-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d8824-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8824-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d8824-140">INPUTS</span></span>

## <span data-ttu-id="d8824-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d8824-141">OUTPUTS</span></span>

## <span data-ttu-id="d8824-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d8824-142">NOTES</span></span>

## <span data-ttu-id="d8824-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d8824-143">RELATED LINKS</span></span>

[<span data-ttu-id="d8824-144">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8824-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="d8824-145">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d8824-145">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="d8824-146">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="d8824-146">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="d8824-147">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d8824-147">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="d8824-148">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d8824-148">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
