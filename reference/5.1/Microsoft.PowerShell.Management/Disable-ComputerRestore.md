---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194190"
---
# <span data-ttu-id="bade9-103">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bade9-103">Disable-ComputerRestore</span></span>

## <span data-ttu-id="bade9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bade9-104">SYNOPSIS</span></span>
<span data-ttu-id="bade9-105">Desabilita o recurso de Restauração de sistema na unidade de sistema de arquivos especificada.</span><span class="sxs-lookup"><span data-stu-id="bade9-105">Disables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="bade9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bade9-106">SYNTAX</span></span>

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bade9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bade9-107">DESCRIPTION</span></span>
<span data-ttu-id="bade9-108">O cmdlet **Disable-ComputerRestore** desativa o recurso de restauração do sistema em uma ou mais unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bade9-108">The **Disable-ComputerRestore** cmdlet turns off the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="bade9-109">Como resultado, tentativas de restaurar o computador não afetam a unidade especificada.</span><span class="sxs-lookup"><span data-stu-id="bade9-109">As a result, attempts to restore the computer do not affect the specified drive.</span></span>

<span data-ttu-id="bade9-110">Para desabilitar a Restauração do sistema em uma determinada unidade, é necessário desabilitá-la primeiro ou simultaneamente na unidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="bade9-110">To disable System Restore on any drive, it must be disabled on the system drive, either first or concurrently.</span></span>

<span data-ttu-id="bade9-111">Para ativar novamente a Restauração do sistema, use o cmdlet Enable-ComputerRestore.</span><span class="sxs-lookup"><span data-stu-id="bade9-111">To re-enable System Restore, use the Enable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="bade9-112">Para descobrir o estado de Restauração do sistema para cada unidade, use o Rstrui.exe.</span><span class="sxs-lookup"><span data-stu-id="bade9-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="bade9-113">Pontos de restauração do sistema e os cmdlets ComputerRestore têm suporte apenas em sistemas operacionais de cliente, como o Windows 7, Windows Vista e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="bade9-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="bade9-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bade9-114">EXAMPLES</span></span>

### <span data-ttu-id="bade9-115">Exemplo 1: desabilitar a restauração do sistema na unidade especificada</span><span class="sxs-lookup"><span data-stu-id="bade9-115">Example 1: Disable System Restore on the specified drive</span></span>

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="bade9-116">Este comando desabilita a Restauração do sistema na unidade C:.</span><span class="sxs-lookup"><span data-stu-id="bade9-116">This command disables System Restore on the C: drive.</span></span>

### <span data-ttu-id="bade9-117">Exemplo 2: desabilitar a restauração do sistema em várias unidades</span><span class="sxs-lookup"><span data-stu-id="bade9-117">Example 2: Disable System Restore on multiple drives</span></span>

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

<span data-ttu-id="bade9-118">Este comando desabilita a Restauração do sistema nas unidades C: e D:.</span><span class="sxs-lookup"><span data-stu-id="bade9-118">This command disables System Restore on the C: and D: drives.</span></span>
<span data-ttu-id="bade9-119">O comando usa o parâmetro *drive* , mas omite o nome do parâmetro da unidade.</span><span class="sxs-lookup"><span data-stu-id="bade9-119">The command uses the *Drive* parameter, but it omits the Drive parameter name.</span></span>

## <span data-ttu-id="bade9-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bade9-120">PARAMETERS</span></span>

### <span data-ttu-id="bade9-121">-Unidade</span><span class="sxs-lookup"><span data-stu-id="bade9-121">-Drive</span></span>
<span data-ttu-id="bade9-122">Especifica as unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bade9-122">Specifies the file system drives.</span></span>
<span data-ttu-id="bade9-123">Insira uma ou mais letras de unidade do sistema de arquivos, cada uma seguida por dois-pontos e uma barra invertida e entre aspas, como C:\ ou D:\.</span><span class="sxs-lookup"><span data-stu-id="bade9-123">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="bade9-124">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="bade9-124">This parameter is required.</span></span>

<span data-ttu-id="bade9-125">Você não pode usar este cmdlet para desabilitar a Restauração do sistema em uma unidade de rede remota, mesmo que a unidade esteja mapeada para o computador local; você também não pode desabilitar a Restauração do sistema em unidades que não estão qualificadas para essa operação, como unidades externas.</span><span class="sxs-lookup"><span data-stu-id="bade9-125">You cannot use this cmdlet to disable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot disable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="bade9-126">Para desabilitar a Restauração do sistema em uma determinada unidade, é necessário desabilitá-la primeiro ou simultaneamente na unidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="bade9-126">To disable System Restore on any drive, System Restore must be disabled on the system drive, either before or concurrently.</span></span>

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

### <span data-ttu-id="bade9-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bade9-127">-Confirm</span></span>
<span data-ttu-id="bade9-128">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bade9-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bade9-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bade9-129">-WhatIf</span></span>
<span data-ttu-id="bade9-130">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bade9-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bade9-131">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bade9-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bade9-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bade9-132">CommonParameters</span></span>
<span data-ttu-id="bade9-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bade9-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bade9-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bade9-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bade9-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bade9-135">INPUTS</span></span>

### <span data-ttu-id="bade9-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bade9-136">None</span></span>
<span data-ttu-id="bade9-137">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bade9-137">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bade9-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bade9-138">OUTPUTS</span></span>

### <span data-ttu-id="bade9-139">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bade9-139">None</span></span>
<span data-ttu-id="bade9-140">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="bade9-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bade9-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bade9-141">NOTES</span></span>

* <span data-ttu-id="bade9-142">Para executar esse cmdlet no Windows Vista e em versões posteriores do Windows, abra o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="bade9-142">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="bade9-143">Para localizar as unidades do sistema de arquivos elegíveis para a restauração do sistema, em sistema no painel de controle, consulte a guia proteção do sistema. Para abrir essa guia no Windows PowerShell, digite `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="bade9-143">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="bade9-144">Esse cmdlet usa Instrumentação de Gerenciamento do Windows a classe **SystemRestore** (WMI).</span><span class="sxs-lookup"><span data-stu-id="bade9-144">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="bade9-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bade9-145">RELATED LINKS</span></span>

[<span data-ttu-id="bade9-146">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bade9-146">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bade9-147">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bade9-147">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="bade9-148">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="bade9-148">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="bade9-149">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bade9-149">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="bade9-150">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bade9-150">Restore-Computer</span></span>](Restore-Computer.md)
