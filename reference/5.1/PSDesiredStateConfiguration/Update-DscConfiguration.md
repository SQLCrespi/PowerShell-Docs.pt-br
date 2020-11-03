---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193709"
---
# <span data-ttu-id="981e1-103">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-103">Update-DscConfiguration</span></span>

## <span data-ttu-id="981e1-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="981e1-104">SYNOPSIS</span></span>
<span data-ttu-id="981e1-105">Verifica se há uma configuração atualizada no servidor de pull e o aplica.</span><span class="sxs-lookup"><span data-stu-id="981e1-105">Checks the pull server for an updated configuration and applies it.</span></span>

## <span data-ttu-id="981e1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="981e1-106">SYNTAX</span></span>

### <span data-ttu-id="981e1-107">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="981e1-107">ComputerNameSet (Default)</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="981e1-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="981e1-108">CimSessionSet</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="981e1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="981e1-109">DESCRIPTION</span></span>
<span data-ttu-id="981e1-110">O `Update-DscConfiguration` cmdlet se conecta a um servidor de pull, baixa a configuração se diferir do que está atual no nó e, em seguida, aplica a configuração ao computador.</span><span class="sxs-lookup"><span data-stu-id="981e1-110">The `Update-DscConfiguration` cmdlet connects to a pull server, downloads the configuration if it differs from what is current on the node, and then applies the configuration to the computer.</span></span>

<span data-ttu-id="981e1-111">Esse cmdlet está disponível somente como parte do [pacote cumulativo de atualizações de novembro de 2014 para Windows RT 8,1, Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) da biblioteca suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="981e1-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="981e1-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="981e1-112">EXAMPLES</span></span>

### <span data-ttu-id="981e1-113">Exemplo 1: atualizar uma configuração</span><span class="sxs-lookup"><span data-stu-id="981e1-113">Example 1: Update a configuration</span></span>

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

<span data-ttu-id="981e1-114">Depois de executar esse comando, o servidor se conectará ao serviço de pull registrado, baixará a configuração mais recente atribuída e, em seguida, a aplicará.</span><span class="sxs-lookup"><span data-stu-id="981e1-114">After running this command, the server will connect to the registered pull service, download the latest assigned configuration, and then apply it.</span></span>
<span data-ttu-id="981e1-115">Os parâmetros-Wait e-Verbose são opcionais.</span><span class="sxs-lookup"><span data-stu-id="981e1-115">The -Wait and -Verbose parameters are optional.</span></span>
<span data-ttu-id="981e1-116">Ao trabalhar interativamente, esses parâmetros combinam os comentários em tempo real sobre o progresso e o êxito ou falha ao aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="981e1-116">When working interactively, these parameters combined enable real-time feedback about progress and success or failure when applying the configuration.</span></span>

### <span data-ttu-id="981e1-117">Exemplo 2: atualizar uma configuração conectando-se por uma sessão CIM</span><span class="sxs-lookup"><span data-stu-id="981e1-117">Example 2: Update a configuration by connecting over a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

<span data-ttu-id="981e1-118">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="981e1-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="981e1-119">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="981e1-119">The command prompts you for a password.</span></span>
<span data-ttu-id="981e1-120">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="981e1-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="981e1-121">O segundo comando atualiza o computador especificado no **CimSession** armazenado em $Session.</span><span class="sxs-lookup"><span data-stu-id="981e1-121">The second command updates the computer specified in the **CimSession** stored in $Session.</span></span>
<span data-ttu-id="981e1-122">O comando especifica o parâmetro *Wait* .</span><span class="sxs-lookup"><span data-stu-id="981e1-122">The command specifies the *Wait* parameter.</span></span>
<span data-ttu-id="981e1-123">O console do não aceita comandos adicionais até que o comando atual seja concluído.</span><span class="sxs-lookup"><span data-stu-id="981e1-123">The console does not accept additional commands until the current command finishes.</span></span>

## <span data-ttu-id="981e1-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="981e1-124">PARAMETERS</span></span>

### <span data-ttu-id="981e1-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="981e1-125">-CimSession</span></span>
<span data-ttu-id="981e1-126">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="981e1-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="981e1-127">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="981e1-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="981e1-128">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="981e1-128">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="981e1-129">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="981e1-129">-ComputerName</span></span>
<span data-ttu-id="981e1-130">Especifica uma matriz de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="981e1-130">Specifies an array of computer names.</span></span>
<span data-ttu-id="981e1-131">O cmdlet aplica as definições de configuração aos computadores que esse parâmetro especifica.</span><span class="sxs-lookup"><span data-stu-id="981e1-131">The cmdlet applies the configuration settings to the computers that this parameter specifies.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="981e1-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="981e1-132">-Credential</span></span>
<span data-ttu-id="981e1-133">Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="981e1-133">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="981e1-134">Para obter um objeto **PSCredential** , use o cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="981e1-134">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="981e1-135">Para obter mais informações, digite `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="981e1-135">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="981e1-136">-JobName</span><span class="sxs-lookup"><span data-stu-id="981e1-136">-JobName</span></span>
<span data-ttu-id="981e1-137">Especifica um nome amigável para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="981e1-137">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="981e1-138">Se você especificar esse parâmetro, o cmdlet será executado como um trabalho e retorna um objeto **Job** .</span><span class="sxs-lookup"><span data-stu-id="981e1-138">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="981e1-139">Por padrão, o Windows PowerShell atribui o nome JobN onde N é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="981e1-139">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="981e1-140">Se você especificar o parâmetro *Wait* , não especifique esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="981e1-140">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="981e1-141">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="981e1-141">-ThrottleLimit</span></span>
<span data-ttu-id="981e1-142">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="981e1-142">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="981e1-143">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="981e1-143">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="981e1-144">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="981e1-144">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="981e1-145">-Wait</span><span class="sxs-lookup"><span data-stu-id="981e1-145">-Wait</span></span>
<span data-ttu-id="981e1-146">Indica que o cmdlet bloqueia o console até que ele termine todas as tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="981e1-146">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="981e1-147">Se você especificar esse parâmetro, não especifique o parâmetro *JobName* .</span><span class="sxs-lookup"><span data-stu-id="981e1-147">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="981e1-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="981e1-148">-Confirm</span></span>
<span data-ttu-id="981e1-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="981e1-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="981e1-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="981e1-150">-WhatIf</span></span>
<span data-ttu-id="981e1-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="981e1-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="981e1-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="981e1-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="981e1-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="981e1-153">CommonParameters</span></span>
<span data-ttu-id="981e1-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="981e1-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="981e1-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="981e1-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="981e1-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="981e1-156">INPUTS</span></span>

## <span data-ttu-id="981e1-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="981e1-157">OUTPUTS</span></span>

## <span data-ttu-id="981e1-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="981e1-158">NOTES</span></span>

## <span data-ttu-id="981e1-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="981e1-159">RELATED LINKS</span></span>

[<span data-ttu-id="981e1-160">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="981e1-160">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="981e1-161">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-161">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="981e1-162">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="981e1-162">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="981e1-163">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-163">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="981e1-164">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-164">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="981e1-165">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-165">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="981e1-166">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="981e1-166">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
