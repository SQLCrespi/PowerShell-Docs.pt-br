---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193935"
---
# <span data-ttu-id="164a2-103">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="164a2-103">Restore-Computer</span></span>

## <span data-ttu-id="164a2-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="164a2-104">SYNOPSIS</span></span>
<span data-ttu-id="164a2-105">Inicia uma restauração do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="164a2-105">Starts a system restore on the local computer.</span></span>

## <span data-ttu-id="164a2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="164a2-106">SYNTAX</span></span>

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="164a2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="164a2-107">DESCRIPTION</span></span>
<span data-ttu-id="164a2-108">O cmdlet **Restore-Computer** restaura o computador local para o ponto de restauração do sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="164a2-108">The **Restore-Computer** cmdlet restores the local computer to the specified system restore point.</span></span>

<span data-ttu-id="164a2-109">**Restaurar – o computador** reinicia o computador.</span><span class="sxs-lookup"><span data-stu-id="164a2-109">**Restore-Computer** restarts the computer.</span></span>
<span data-ttu-id="164a2-110">A restauração é concluída durante a operação de reinício.</span><span class="sxs-lookup"><span data-stu-id="164a2-110">The restore is completed during the restart operation.</span></span>

<span data-ttu-id="164a2-111">Pontos de restauração do sistema e **Restore-Computer** têm suporte apenas em sistemas operacionais cliente, como o Windows 7, o Windows Vista e o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="164a2-111">System restore points and **Restore-Computer** are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="164a2-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="164a2-112">EXAMPLES</span></span>

### <span data-ttu-id="164a2-113">Exemplo 1: restaurar o computador local</span><span class="sxs-lookup"><span data-stu-id="164a2-113">Example 1: Restore the local computer</span></span>

```
PS C:\> Restore-Computer -RestorePoint 253
```

<span data-ttu-id="164a2-114">Este comando restaura o computador local para o ponto de restauração que tem o número de sequência 253.</span><span class="sxs-lookup"><span data-stu-id="164a2-114">This command restores the local computer to the restore point that has sequence number 253.</span></span>

### <span data-ttu-id="164a2-115">Exemplo 2: restaurar o computador local com confirmação</span><span class="sxs-lookup"><span data-stu-id="164a2-115">Example 2: Restore the local computer with confirmation</span></span>

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="164a2-116">Este comando restaura o computador local para o ponto de restauração que tem o número de sequência 255.</span><span class="sxs-lookup"><span data-stu-id="164a2-116">This command restores the local computer to the restore point that has sequence number 255.</span></span>
<span data-ttu-id="164a2-117">Ele usa o parâmetro *Confirm* para avisar o usuário antes de realmente executar a operação.</span><span class="sxs-lookup"><span data-stu-id="164a2-117">It uses the *Confirm* parameter to prompt the user before actually performing the operation.</span></span>

### <span data-ttu-id="164a2-118">Exemplo 3: restaurar um computador e verificar o status</span><span class="sxs-lookup"><span data-stu-id="164a2-118">Example 3: Restore a computer and check the status</span></span>

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

<span data-ttu-id="164a2-119">Estes comandos executam uma restauração do sistema e verificam seu status.</span><span class="sxs-lookup"><span data-stu-id="164a2-119">These commands run a system restore and then check its status.</span></span>

<span data-ttu-id="164a2-120">O primeiro comando usa **Get-ComputerRestorePoint** para obter os pontos de restauração no computador local.</span><span class="sxs-lookup"><span data-stu-id="164a2-120">The first command uses **Get-ComputerRestorePoint** to get the restore points on the local computer.</span></span>

<span data-ttu-id="164a2-121">O segundo comando restaura o computador para o ponto de restauração com o número de sequência 255.</span><span class="sxs-lookup"><span data-stu-id="164a2-121">The second command restores the computer to the restore point with sequence number 255.</span></span>

<span data-ttu-id="164a2-122">O terceiro comando usa o parâmetro *LastStatus* do cmdlet *Get-ComputerRestorePoint* para verificar o status da operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="164a2-122">The third command uses the *LastStatus* parameter of *Get-ComputerRestorePoint* cmdlet to check the status of the restore operation.</span></span>
<span data-ttu-id="164a2-123">Como **Restore-Computer** força uma reinicialização, esse comando seria inserido após a reinicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="164a2-123">Because **Restore-Computer** forces a restart, this command would be entered after the computer restarts.</span></span>

## <span data-ttu-id="164a2-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="164a2-124">PARAMETERS</span></span>

### <span data-ttu-id="164a2-125">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="164a2-125">-RestorePoint</span></span>
<span data-ttu-id="164a2-126">Especifica o número de sequência do ponto de restauração.</span><span class="sxs-lookup"><span data-stu-id="164a2-126">Specifies the sequence number of the restore point.</span></span>
<span data-ttu-id="164a2-127">Para localizar o número de sequência, use o cmdlet Get-ComputerRestorePoint.</span><span class="sxs-lookup"><span data-stu-id="164a2-127">To find the sequence number, use the Get-ComputerRestorePoint cmdlet.</span></span>
<span data-ttu-id="164a2-128">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="164a2-128">This parameter is required.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="164a2-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="164a2-129">-Confirm</span></span>
<span data-ttu-id="164a2-130">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="164a2-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="164a2-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="164a2-131">-WhatIf</span></span>
<span data-ttu-id="164a2-132">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="164a2-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="164a2-133">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="164a2-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="164a2-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="164a2-134">CommonParameters</span></span>
<span data-ttu-id="164a2-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="164a2-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="164a2-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="164a2-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="164a2-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="164a2-137">INPUTS</span></span>

### <span data-ttu-id="164a2-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="164a2-138">None</span></span>
<span data-ttu-id="164a2-139">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="164a2-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="164a2-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="164a2-140">OUTPUTS</span></span>

### <span data-ttu-id="164a2-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="164a2-141">None</span></span>
<span data-ttu-id="164a2-142">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="164a2-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="164a2-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="164a2-143">NOTES</span></span>

* <span data-ttu-id="164a2-144">Para executar um comando Restore-Computer no Windows Vista e em versões posteriores do sistema operacional Windows, abra o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="164a2-144">To run a Restore-Computer command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="164a2-145">Esse cmdlet usa Instrumentação de Gerenciamento do Windows a classe **SystemRestore** (WMI).</span><span class="sxs-lookup"><span data-stu-id="164a2-145">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

## <span data-ttu-id="164a2-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="164a2-146">RELATED LINKS</span></span>

[<span data-ttu-id="164a2-147">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="164a2-147">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="164a2-148">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="164a2-148">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="164a2-149">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="164a2-149">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="164a2-150">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="164a2-150">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="164a2-151">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="164a2-151">Restart-Computer</span></span>](Restart-Computer.md)
