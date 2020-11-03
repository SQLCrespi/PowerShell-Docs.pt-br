---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193716"
---
# <span data-ttu-id="a6ae4-103">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-103">Stop-DscConfiguration</span></span>

## <span data-ttu-id="a6ae4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a6ae4-104">SYNOPSIS</span></span>
<span data-ttu-id="a6ae4-105">Interrompe um trabalho de configuração que está em execução.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-105">Stops a configuration job that is running.</span></span>

## <span data-ttu-id="a6ae4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6ae4-106">SYNTAX</span></span>

### <span data-ttu-id="a6ae4-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="a6ae4-107">All</span></span>

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a6ae4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6ae4-108">DESCRIPTION</span></span>

<span data-ttu-id="a6ae4-109">O `Stop-DscConfiguration` cmdlet interrompe um trabalho de configuração que está em execução.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-109">The `Stop-DscConfiguration` cmdlet stops a configuration job that is running.</span></span> <span data-ttu-id="a6ae4-110">Especifique a quais computadores este cmdlet se aplica usando sessões de modelo CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="a6ae4-110">Specify which computers this cmdlet applies to by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="a6ae4-111">Se não houver nenhum trabalho de configuração em execução, esse cmdlet retornará uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-111">If there's no configuration job running, this cmdlet returns a warning message.</span></span>

<span data-ttu-id="a6ae4-112">`Stop-DscConfiguration` Só está disponível como parte do [pacote cumulativo de atualizações de novembro de 2014 para Windows RT 8,1, Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) da biblioteca suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-112">`Stop-DscConfiguration` is only available as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span> <span data-ttu-id="a6ae4-113">Antes de usar este cmdlet, examine as informações em [novidades do Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span><span class="sxs-lookup"><span data-stu-id="a6ae4-113">Before you use this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span></span>

## <span data-ttu-id="a6ae4-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a6ae4-114">EXAMPLES</span></span>

### <span data-ttu-id="a6ae4-115">Exemplo 1: parar um trabalho de configuração</span><span class="sxs-lookup"><span data-stu-id="a6ae4-115">Example 1: Stop a configuration job</span></span>

<span data-ttu-id="a6ae4-116">Neste exemplo, uma sessão CIM é criada usando o `New-CimSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-116">In this example, a CIM session is created using the `New-CimSession` cmdlet.</span></span> <span data-ttu-id="a6ae4-117">O objeto **CimSession** é usado para interromper um trabalho de configuração em execução.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-117">The **CimSession** object is used to stop a running configuration job.</span></span>

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

<span data-ttu-id="a6ae4-118">`New-CimSession` usa o parâmetro **ComputerName** para especificar o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-118">`New-CimSession` uses the **ComputerName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="a6ae4-119">O parâmetro **Credential** especifica a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-119">The **Credential** parameter specifies the user account.</span></span> <span data-ttu-id="a6ae4-120">O objeto **CimSession** é armazenado na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-120">The **CimSession** object is stored in the `$Session` variable.</span></span> <span data-ttu-id="a6ae4-121">Quando o comando for executado, você será solicitado a fornecer a senha da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-121">When the command is run, you're prompted for the user account's password.</span></span>

<span data-ttu-id="a6ae4-122">`Stop-DscConfiguration` usa o parâmetro **CimSession** e o objeto armazenado em `$Session` para interromper o trabalho de configuração.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-122">`Stop-DscConfiguration` uses the **CimSession** parameter and the object stored in `$Session` to stop the configuration job.</span></span>

## <span data-ttu-id="a6ae4-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6ae4-123">PARAMETERS</span></span>

### <span data-ttu-id="a6ae4-124">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a6ae4-124">-AsJob</span></span>

<span data-ttu-id="a6ae4-125">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-125">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="a6ae4-126">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a6ae4-126">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="a6ae4-127">Para usar o parâmetro **AsJob** , os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-127">To use the **AsJob** parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="a6ae4-128">No Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="a6ae4-128">On Windows Vista and later versions of the Windows operating system, you must open PowerShell with the **Run as administrator** option.</span></span> <span data-ttu-id="a6ae4-129">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6ae4-129">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6ae4-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a6ae4-130">-CimSession</span></span>

<span data-ttu-id="a6ae4-131">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="a6ae4-132">Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` ou `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="a6ae4-132">Enter a computer name or a session object, such as the output from `New-CimSession` or `Get-CimSession`.</span></span>

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

### <span data-ttu-id="a6ae4-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a6ae4-133">-Confirm</span></span>

<span data-ttu-id="a6ae4-134">`Stop-DscConfiguration` Não dá suporte ao parâmetro **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="a6ae4-134">`Stop-DscConfiguration` doesn't support the **Confirm** parameter.</span></span> <span data-ttu-id="a6ae4-135">Se o parâmetro **Confirm** for usado, será exibido um erro.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-135">If the **Confirm** parameter is used, an error is displayed.</span></span>

<span data-ttu-id="a6ae4-136">Para os cmdlets do PowerShell que dão suporte à **confirmação** , usar o parâmetro solicita a verificação antes de executar um comando.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-136">For PowerShell cmdlets that support **Confirm** , using the parameter prompts you for verification before a command is run.</span></span>

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

### <span data-ttu-id="a6ae4-137">-Force</span><span class="sxs-lookup"><span data-stu-id="a6ae4-137">-Force</span></span>

<span data-ttu-id="a6ae4-138">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-138">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6ae4-139">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a6ae4-139">-ThrottleLimit</span></span>

<span data-ttu-id="a6ae4-140">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-140">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

<span data-ttu-id="a6ae4-141">Se esse parâmetro for omitido ou um valor de `0` for inserido, o PowerShell calculará um limite de aceleração ideal com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-141">If this parameter is omitted or a value of `0` is entered, PowerShell calculates an optimum throttle limit based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="a6ae4-142">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-142">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a6ae4-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a6ae4-143">-WhatIf</span></span>

<span data-ttu-id="a6ae4-144">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a6ae4-145">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a6ae4-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a6ae4-146">CommonParameters</span></span>

<span data-ttu-id="a6ae4-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6ae4-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6ae4-148">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6ae4-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6ae4-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a6ae4-149">INPUTS</span></span>

### <span data-ttu-id="a6ae4-150">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a6ae4-150">None</span></span>

## <span data-ttu-id="a6ae4-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a6ae4-151">OUTPUTS</span></span>

### <span data-ttu-id="a6ae4-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a6ae4-152">None</span></span>

## <span data-ttu-id="a6ae4-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a6ae4-153">NOTES</span></span>

## <span data-ttu-id="a6ae4-154">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a6ae4-154">RELATED LINKS</span></span>

[<span data-ttu-id="a6ae4-155">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="a6ae4-155">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="a6ae4-156">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-156">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a6ae4-157">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a6ae4-157">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="a6ae4-158">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="a6ae4-158">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="a6ae4-159">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-159">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="a6ae4-160">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-160">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="a6ae4-161">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-161">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="a6ae4-162">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ae4-162">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)

[<span data-ttu-id="a6ae4-163">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6ae4-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)
