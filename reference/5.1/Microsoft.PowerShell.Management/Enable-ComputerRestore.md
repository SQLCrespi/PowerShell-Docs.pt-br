---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194189"
---
# <span data-ttu-id="74c47-103">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="74c47-103">Enable-ComputerRestore</span></span>

## <span data-ttu-id="74c47-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="74c47-104">SYNOPSIS</span></span>
<span data-ttu-id="74c47-105">Habilita o recurso de Restauração do Sistema na unidade de sistema de arquivos especificada.</span><span class="sxs-lookup"><span data-stu-id="74c47-105">Enables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="74c47-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74c47-106">SYNTAX</span></span>

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="74c47-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74c47-107">DESCRIPTION</span></span>
<span data-ttu-id="74c47-108">O cmdlet **Enable-ComputerRestore** ativa o recurso de restauração do sistema em uma ou mais unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="74c47-108">The **Enable-ComputerRestore** cmdlet turns on the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="74c47-109">Como resultado, você pode usar ferramentas, como o cmdlet Restore-Computer, para restaurar o computador a um estado anterior.</span><span class="sxs-lookup"><span data-stu-id="74c47-109">As a result, you can use tools, such as the Restore-Computer cmdlet, to restore the computer to a previous state.</span></span>

<span data-ttu-id="74c47-110">Por padrão, a Restauração do Sistema está habilitada em todas as unidades qualificadas, mas você pode desabilitá-la, por exemplo, usando o cmdlet Disable-ComputerRestore.</span><span class="sxs-lookup"><span data-stu-id="74c47-110">By default, System Restore is enabled on all eligible drives, but you can disable it, such as by using the Disable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="74c47-111">Para habilitar (ou reabilitar) a Restauração do Sistema em qualquer unidade, ela deve estar habilitada na unidade do sistema, primeiro ou simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="74c47-111">To enable (or re-enable) System Restore on any drive, it must be enabled on the system drive, either first or concurrently.</span></span>
<span data-ttu-id="74c47-112">Para descobrir o estado de Restauração do sistema para cada unidade, use o Rstrui.exe.</span><span class="sxs-lookup"><span data-stu-id="74c47-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="74c47-113">Pontos de restauração do sistema e os cmdlets ComputerRestore têm suporte apenas em sistemas operacionais de cliente, como o Windows 7, Windows Vista e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="74c47-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="74c47-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="74c47-114">EXAMPLES</span></span>

### <span data-ttu-id="74c47-115">Exemplo 1: habilitar a restauração do sistema na unidade especificada</span><span class="sxs-lookup"><span data-stu-id="74c47-115">Example 1: Enable System Restore on the specified drive</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="74c47-116">Este comando habilita a Restauração do Sistema na unidade C: do computador local.</span><span class="sxs-lookup"><span data-stu-id="74c47-116">This command enables System Restore on the C: drive of the local computer.</span></span>

### <span data-ttu-id="74c47-117">Exemplo 2: habilitar a restauração do sistema em várias unidades</span><span class="sxs-lookup"><span data-stu-id="74c47-117">Example 2: Enable System Restore on multiple drives</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

<span data-ttu-id="74c47-118">Este comando habilita a Restauração do Sistema nas unidades C: e D: do computador local.</span><span class="sxs-lookup"><span data-stu-id="74c47-118">This command enables System Restore on the C: and D: drives of the local computer.</span></span>

## <span data-ttu-id="74c47-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74c47-119">PARAMETERS</span></span>

### <span data-ttu-id="74c47-120">-Unidade</span><span class="sxs-lookup"><span data-stu-id="74c47-120">-Drive</span></span>
<span data-ttu-id="74c47-121">Especifica as unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="74c47-121">Specifies the file system drives.</span></span>
<span data-ttu-id="74c47-122">Insira uma ou mais letras de unidade do sistema de arquivos, cada uma seguida por dois-pontos e uma barra invertida e entre aspas, como C:\ ou D:\.</span><span class="sxs-lookup"><span data-stu-id="74c47-122">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="74c47-123">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="74c47-123">This parameter is required.</span></span>

<span data-ttu-id="74c47-124">Você não pode usar este cmdlet para ativar a Restauração do Sistema em uma unidade de rede remota, mesmo que a unidade esteja mapeada para o computador local; você também não pode ativar a Restauração do Sistema em unidades que não estão qualificadas para essa operação, como unidades externas.</span><span class="sxs-lookup"><span data-stu-id="74c47-124">You cannot use this cmdlet to enable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot enable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="74c47-125">Para ativar a Restauração do sistema em uma determinada unidade, é necessário ativá-la primeiro ou simultaneamente na unidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="74c47-125">To enable System Restore on any drive, System Restore must be enabled on the system drive, either before or concurrently.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="74c47-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="74c47-126">-Confirm</span></span>
<span data-ttu-id="74c47-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74c47-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="74c47-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="74c47-128">-WhatIf</span></span>
<span data-ttu-id="74c47-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="74c47-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="74c47-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="74c47-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="74c47-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="74c47-131">CommonParameters</span></span>
<span data-ttu-id="74c47-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="74c47-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74c47-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="74c47-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74c47-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="74c47-134">INPUTS</span></span>

### <span data-ttu-id="74c47-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="74c47-135">None</span></span>
<span data-ttu-id="74c47-136">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74c47-136">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="74c47-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="74c47-137">OUTPUTS</span></span>

### <span data-ttu-id="74c47-138">Nenhum</span><span class="sxs-lookup"><span data-stu-id="74c47-138">None</span></span>
<span data-ttu-id="74c47-139">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="74c47-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="74c47-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="74c47-140">NOTES</span></span>

* <span data-ttu-id="74c47-141">Para executar esse cmdlet no Windows Vista e em versões posteriores do Windows, abra o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="74c47-141">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="74c47-142">Para localizar as unidades do sistema de arquivos elegíveis para a restauração do sistema, em sistema no painel de controle, consulte a guia proteção do sistema. Para abrir essa guia no Windows PowerShell, digite `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="74c47-142">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="74c47-143">Esse cmdlet usa Instrumentação de Gerenciamento do Windows a classe **SystemRestore** (WMI).</span><span class="sxs-lookup"><span data-stu-id="74c47-143">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="74c47-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="74c47-144">RELATED LINKS</span></span>

[<span data-ttu-id="74c47-145">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="74c47-145">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="74c47-146">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="74c47-146">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="74c47-147">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="74c47-147">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="74c47-148">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="74c47-148">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="74c47-149">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="74c47-149">Restore-Computer</span></span>](Restore-Computer.md)
