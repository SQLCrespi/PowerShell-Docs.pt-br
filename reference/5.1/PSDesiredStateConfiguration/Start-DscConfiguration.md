---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194138"
---
# <span data-ttu-id="c14ab-103">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-103">Start-DscConfiguration</span></span>

## <span data-ttu-id="c14ab-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c14ab-104">SYNOPSIS</span></span>
<span data-ttu-id="c14ab-105">Aplica configuração a nós.</span><span class="sxs-lookup"><span data-stu-id="c14ab-105">Applies configuration to nodes.</span></span>

## <span data-ttu-id="c14ab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c14ab-106">SYNTAX</span></span>

### <span data-ttu-id="c14ab-107">ComputerNameAndPathSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="c14ab-107">ComputerNameAndPathSet (Default)</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c14ab-108">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="c14ab-108">CimSessionAndPathSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c14ab-109">ComputerNameAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="c14ab-109">ComputerNameAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c14ab-110">CimSessionAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="c14ab-110">CimSessionAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c14ab-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c14ab-111">DESCRIPTION</span></span>
<span data-ttu-id="c14ab-112">O cmdlet **Start-DscConfiguration** aplica configuração aos nós.</span><span class="sxs-lookup"><span data-stu-id="c14ab-112">The **Start-DscConfiguration** cmdlet applies configuration to nodes.</span></span>
<span data-ttu-id="c14ab-113">Quando usado com o parâmetro *UseExisting* , a configuração existente no computador de destino é aplicada.</span><span class="sxs-lookup"><span data-stu-id="c14ab-113">When used with the *UseExisting* parameter, the existing configuration on the target computer is applied.</span></span>
<span data-ttu-id="c14ab-114">Especifique os computadores aos quais você deseja aplicar a configuração especificando nomes de computador ou usando sessões de modelo CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="c14ab-114">Specify which computers that you want to apply configuration to by specifying computer names or by using Common Information Model (CIM) sessions.</span></span>

<span data-ttu-id="c14ab-115">Por padrão, esse cmdlet cria um trabalho e retorna um objeto **Job** .</span><span class="sxs-lookup"><span data-stu-id="c14ab-115">By default, this cmdlet creates a job and returns a **Job** object.</span></span>
<span data-ttu-id="c14ab-116">Para obter mais informações sobre trabalhos em segundo plano, digite `Get-Help about_Jobs` .</span><span class="sxs-lookup"><span data-stu-id="c14ab-116">For more information about background jobs, type `Get-Help about_Jobs`.</span></span>
<span data-ttu-id="c14ab-117">Para usar esse cmdlet interativamente, especifique o parâmetro *Wait* .</span><span class="sxs-lookup"><span data-stu-id="c14ab-117">To use this cmdlet interactively, specify the *Wait* parameter.</span></span>

<span data-ttu-id="c14ab-118">Especifique o parâmetro *Verbose* para ver os detalhes do que o cmdlet faz ao aplicar as definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="c14ab-118">Specify the *Verbose* parameter to see details of what the cmdlet does when it applies configuration settings.</span></span>

## <span data-ttu-id="c14ab-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c14ab-119">EXAMPLES</span></span>

### <span data-ttu-id="c14ab-120">Exemplo 1: aplicar definições de configuração</span><span class="sxs-lookup"><span data-stu-id="c14ab-120">Example 1: Apply configuration settings</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="c14ab-121">Esse comando aplica as configurações de C:\DSC\Configurations\ a cada computador que tem as configurações nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="c14ab-121">This command applies the configuration settings from C:\DSC\Configurations\ to the every computer that has settings in that folder.</span></span>
<span data-ttu-id="c14ab-122">O comando retorna objetos **Job** para cada nó de destino implantado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-122">The command returns **Job** objects for each target node deployed to.</span></span>

### <span data-ttu-id="c14ab-123">Exemplo 2: aplicar definições de configuração e aguardar a conclusão da configuração</span><span class="sxs-lookup"><span data-stu-id="c14ab-123">Example 2: Apply configuration settings and wait for configuration to complete</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

<span data-ttu-id="c14ab-124">Este comando aplica a configuração de C:\DSC\Configurations\ ao computador local.</span><span class="sxs-lookup"><span data-stu-id="c14ab-124">This command applies the configuration from C:\DSC\Configurations\ to the local computer.</span></span>
<span data-ttu-id="c14ab-125">O comando retorna objetos **Job** para cada nó de destino implantado, nesse caso, apenas o computador local.</span><span class="sxs-lookup"><span data-stu-id="c14ab-125">The command returns **Job** objects for each target node deployed to, in this case, just the local computer.</span></span>
<span data-ttu-id="c14ab-126">Este exemplo especifica o parâmetro *Verbose* .</span><span class="sxs-lookup"><span data-stu-id="c14ab-126">This example specifies the *Verbose* parameter.</span></span>
<span data-ttu-id="c14ab-127">Portanto, o comando envia mensagens para o console conforme ele prossegue.</span><span class="sxs-lookup"><span data-stu-id="c14ab-127">Therefore, the command sends messages to the console as it proceeds.</span></span>
<span data-ttu-id="c14ab-128">O comando inclui o parâmetro *Wait* .</span><span class="sxs-lookup"><span data-stu-id="c14ab-128">The command includes the *Wait* parameter.</span></span>
<span data-ttu-id="c14ab-129">Portanto, você não pode usar o console do até que o comando conclua todas as tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="c14ab-129">Therefore, you cannot use the console until the command finishes all configuration tasks.</span></span>

### <span data-ttu-id="c14ab-130">Exemplo 3: aplicar definições de configuração usando uma sessão CIM</span><span class="sxs-lookup"><span data-stu-id="c14ab-130">Example 3: Apply configuration settings by using a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="c14ab-131">Este exemplo aplica configurações a um computador especificado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-131">This example applies configuration settings to a specified computer.</span></span>
<span data-ttu-id="c14ab-132">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c14ab-132">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="c14ab-133">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="c14ab-133">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="c14ab-134">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="c14ab-134">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="c14ab-135">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="c14ab-135">The command prompts you for a password.</span></span>
<span data-ttu-id="c14ab-136">Para obter mais informações, digite `Get-Help NewCimSession`.</span><span class="sxs-lookup"><span data-stu-id="c14ab-136">For more information, type `Get-Help NewCimSession`.</span></span>

<span data-ttu-id="c14ab-137">O segundo comando aplica os parâmetros de configuração de C:\DSC\Configurations\ aos computadores identificados pelos objetos **CimSession** armazenados na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="c14ab-137">The second command applies the configuration settings from C:\DSC\Configurations\ to the computers identified by the **CimSession** objects stored in the $Session variable.</span></span>
<span data-ttu-id="c14ab-138">Neste exemplo, a variável $Session contém uma sessão CIM apenas para o computador denominado Server01.</span><span class="sxs-lookup"><span data-stu-id="c14ab-138">In this example, the $Session variable contains a CIM session only for the computer named Server01.</span></span>
<span data-ttu-id="c14ab-139">O comando aplica a configuração.</span><span class="sxs-lookup"><span data-stu-id="c14ab-139">The command applies the configuration.</span></span>
<span data-ttu-id="c14ab-140">O comando cria objetos **Job** para cada computador configurado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-140">The command creates **Job** objects for each configured computer.</span></span>

## <span data-ttu-id="c14ab-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c14ab-141">PARAMETERS</span></span>

### <span data-ttu-id="c14ab-142">-CimSession</span><span class="sxs-lookup"><span data-stu-id="c14ab-142">-CimSession</span></span>
<span data-ttu-id="c14ab-143">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c14ab-143">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="c14ab-144">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="c14ab-144">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="c14ab-145">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="c14ab-145">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c14ab-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c14ab-146">-ComputerName</span></span>
<span data-ttu-id="c14ab-147">Especifica uma matriz de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="c14ab-147">Specifies an array of computer names.</span></span>
<span data-ttu-id="c14ab-148">Esse parâmetro restringe os computadores que têm documentos de configuração no parâmetro *path* para os especificados na matriz.</span><span class="sxs-lookup"><span data-stu-id="c14ab-148">This parameter restricts the computers that have configuration documents in the *Path* parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c14ab-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="c14ab-149">-Credential</span></span>
<span data-ttu-id="c14ab-150">Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="c14ab-150">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="c14ab-151">Para obter um objeto **PSCredential** , use o cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="c14ab-151">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="c14ab-152">Para obter mais informações, digite `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="c14ab-152">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c14ab-153">-Force</span><span class="sxs-lookup"><span data-stu-id="c14ab-153">-Force</span></span>
<span data-ttu-id="c14ab-154">Interrompe a operação de configuração atualmente em execução no computador de destino e inicia a nova operação de Start-Configuration.</span><span class="sxs-lookup"><span data-stu-id="c14ab-154">Stops the configuration operation currently running on the target computer and begins the new Start-Configuration operation.</span></span>
<span data-ttu-id="c14ab-155">Se a propriedade **RefreshMode** do Configuration Manager local for definida como **pull** , a especificação desse parâmetro o alterará para **Push** .</span><span class="sxs-lookup"><span data-stu-id="c14ab-155">If the **RefreshMode** property of the Local Configuration Manager is set to **Pull** , specifying this parameter changes it to **Push** .</span></span>

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

### <span data-ttu-id="c14ab-156">-JobName</span><span class="sxs-lookup"><span data-stu-id="c14ab-156">-JobName</span></span>
<span data-ttu-id="c14ab-157">Especifica um nome amigável para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="c14ab-157">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="c14ab-158">Se você especificar esse parâmetro, o cmdlet será executado como um trabalho e retorna um objeto **Job** .</span><span class="sxs-lookup"><span data-stu-id="c14ab-158">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="c14ab-159">Por padrão, o Windows PowerShell atribui o nome JobN onde N é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="c14ab-159">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="c14ab-160">Se você especificar o parâmetro *Wait* , não especifique esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c14ab-160">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

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

### <span data-ttu-id="c14ab-161">-Path</span><span class="sxs-lookup"><span data-stu-id="c14ab-161">-Path</span></span>
<span data-ttu-id="c14ab-162">Especifica um caminho de arquivo de uma pasta que contém arquivos de definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="c14ab-162">Specifies a file path of a folder that contains configuration settings files.</span></span>
<span data-ttu-id="c14ab-163">Esse cmdlet publica e aplica essas definições de configuração a computadores que têm arquivos de configurações no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-163">This cmdlet publishes and applies these configuration settings to computers that have settings files in the specified path.</span></span>
<span data-ttu-id="c14ab-164">Cada nó de destino deve ter um arquivo de configurações do seguinte formato: NetBIOS Name. mof.</span><span class="sxs-lookup"><span data-stu-id="c14ab-164">Each target node must have a settings file of the following format: NetBIOS Name.mof.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c14ab-165">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c14ab-165">-ThrottleLimit</span></span>
<span data-ttu-id="c14ab-166">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c14ab-166">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="c14ab-167">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="c14ab-167">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="c14ab-168">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="c14ab-168">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="c14ab-169">-UseExisting</span><span class="sxs-lookup"><span data-stu-id="c14ab-169">-UseExisting</span></span>
<span data-ttu-id="c14ab-170">Indica que este cmdlet aplica a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="c14ab-170">Indicates that this cmdlet applies the existing configuration.</span></span>
<span data-ttu-id="c14ab-171">A configuração pode existir no computador de destino por aplicação usando **Start-DscConfiguration** ou por publicação usando o cmdlet Publish-DscConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c14ab-171">The configuration can exist on the target computer by enactment using **Start-DscConfiguration** or by publication using the Publish-DscConfiguration cmdlet.</span></span>

<span data-ttu-id="c14ab-172">Antes de especificar esse parâmetro para esse cmdlet, examine as informações em [novidades no Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span><span class="sxs-lookup"><span data-stu-id="c14ab-172">Before you specify this parameter for this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c14ab-173">-Wait</span><span class="sxs-lookup"><span data-stu-id="c14ab-173">-Wait</span></span>
<span data-ttu-id="c14ab-174">Indica que o cmdlet bloqueia o console até que ele termine todas as tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="c14ab-174">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="c14ab-175">Se você especificar esse parâmetro, não especifique o parâmetro *JobName* .</span><span class="sxs-lookup"><span data-stu-id="c14ab-175">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="c14ab-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c14ab-176">-Confirm</span></span>
<span data-ttu-id="c14ab-177">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c14ab-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c14ab-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c14ab-178">-WhatIf</span></span>
<span data-ttu-id="c14ab-179">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c14ab-180">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c14ab-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c14ab-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c14ab-181">CommonParameters</span></span>
<span data-ttu-id="c14ab-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c14ab-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c14ab-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c14ab-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c14ab-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c14ab-184">INPUTS</span></span>

## <span data-ttu-id="c14ab-185">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c14ab-185">OUTPUTS</span></span>

## <span data-ttu-id="c14ab-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c14ab-186">NOTES</span></span>

## <span data-ttu-id="c14ab-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c14ab-187">RELATED LINKS</span></span>

[<span data-ttu-id="c14ab-188">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14ab-188">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="c14ab-189">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-189">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="c14ab-190">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="c14ab-190">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="c14ab-191">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-191">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="c14ab-192">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-192">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="c14ab-193">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-193">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="c14ab-194">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c14ab-194">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)
