---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193710"
---
# <span data-ttu-id="a3673-103">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3673-103">Test-DscConfiguration</span></span>

## <span data-ttu-id="a3673-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a3673-104">SYNOPSIS</span></span>
<span data-ttu-id="a3673-105">Testa se a configuração real nos nós corresponde à configuração desejada.</span><span class="sxs-lookup"><span data-stu-id="a3673-105">Tests whether the actual configuration on the nodes matches the desired configuration.</span></span>

## <span data-ttu-id="a3673-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3673-106">SYNTAX</span></span>

### <span data-ttu-id="a3673-107">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="a3673-107">ComputerNameSet (Default)</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### <span data-ttu-id="a3673-108">ComputerNameAndPathSet</span><span class="sxs-lookup"><span data-stu-id="a3673-108">ComputerNameAndPathSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="a3673-109">ComputerNameAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="a3673-109">ComputerNameAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="a3673-110">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="a3673-110">CimSessionAndPathSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="a3673-111">CimSessionAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="a3673-111">CimSessionAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="a3673-112">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="a3673-112">CimSessionSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## <span data-ttu-id="a3673-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3673-113">DESCRIPTION</span></span>
<span data-ttu-id="a3673-114">O cmdlet **Test-DscConfiguration** testa se a configuração real nos nós corresponde à configuração desejada.</span><span class="sxs-lookup"><span data-stu-id="a3673-114">The **Test-DscConfiguration** cmdlet tests whether the actual configuration on the nodes matches the desired configuration.</span></span>
<span data-ttu-id="a3673-115">Especifique os computadores para os quais você deseja testar as configurações usando nomes de computador ou sessões de modelo CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="a3673-115">Specify which computers for which you want to test configurations by using computer names or Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="a3673-116">Se você não especificar um computador de destino, o cmdlet testará a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="a3673-116">If you do not specify a target computer, the cmdlet tests configuration of the local computer.</span></span>

<span data-ttu-id="a3673-117">Se as configurações desejadas e reais corresponderem, o cmdlet retornará um valor de cadeia de caracteres de ' true '.</span><span class="sxs-lookup"><span data-stu-id="a3673-117">If the desired and actual configurations match, the cmdlet returns a string value of 'True'.</span></span>
<span data-ttu-id="a3673-118">Caso contrário, ele retornará um valor de cadeia de caracteres de ' false '.</span><span class="sxs-lookup"><span data-stu-id="a3673-118">Otherwise, it returns a string value of 'False'.</span></span>

## <span data-ttu-id="a3673-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a3673-119">EXAMPLES</span></span>

### <span data-ttu-id="a3673-120">Exemplo 1: testar a configuração do computador local</span><span class="sxs-lookup"><span data-stu-id="a3673-120">Example 1: Test configuration for the local computer</span></span>

```
PS C:\> Test-DscConfiguration
```

<span data-ttu-id="a3673-121">Esse comando testa a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="a3673-121">This command tests configuration for the local computer.</span></span>

### <span data-ttu-id="a3673-122">Exemplo 2: testar a configuração de um computador especificado</span><span class="sxs-lookup"><span data-stu-id="a3673-122">Example 2: Test configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

<span data-ttu-id="a3673-123">Esse exemplo testa a configuração de um computador especificado por uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="a3673-123">This example test configuration from a computer specified by a CIM session.</span></span>
<span data-ttu-id="a3673-124">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a3673-124">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="a3673-125">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="a3673-125">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="a3673-126">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="a3673-126">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="a3673-127">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="a3673-127">The command prompts you for a password.</span></span>
<span data-ttu-id="a3673-128">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="a3673-128">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="a3673-129">O segundo comando testa a configuração dos computadores identificados pelos objetos **CimSession** armazenados na variável $Session, nesse caso, o computador denominado Server01.</span><span class="sxs-lookup"><span data-stu-id="a3673-129">The second command tests configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

### <span data-ttu-id="a3673-130">Exemplo 3: testar configurações com resultados detalhados</span><span class="sxs-lookup"><span data-stu-id="a3673-130">Example 3: Test configurations with detailed results</span></span>

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

<span data-ttu-id="a3673-131">Esse comando testa as configurações de um conjunto de computadores especificado pelo parâmetro *ComputerName* e retorna informações detalhadas que incluem o estado geral, os recursos que estão no estado desejado, os recursos que não estão no estado desejado e no nome do computador.</span><span class="sxs-lookup"><span data-stu-id="a3673-131">This command tests configurations for a set of computers specified by the *ComputerName* parameter and returns detailed information that includes the overall state, resources that are in the desired state, resources that are not in the desired state and computer name.</span></span>

### <span data-ttu-id="a3673-132">Exemplo 4: testar as configurações especificadas em uma pasta</span><span class="sxs-lookup"><span data-stu-id="a3673-132">Example 4: Test configurations specified in a folder</span></span>

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

<span data-ttu-id="a3673-133">Esse comando testa as configurações definidas em uma pasta especificada pelo parâmetro *path* .</span><span class="sxs-lookup"><span data-stu-id="a3673-133">This command tests configurations that are defined in a folder specified by the *Path* parameter.</span></span>
<span data-ttu-id="a3673-134">As configurações são testadas em relação a um conjunto de computadores, cada um identificado pelo nome de arquivo do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="a3673-134">The configurations are tested against a set of computers, each identified by the file name of the configuration file.</span></span>

### <span data-ttu-id="a3673-135">Exemplo 5: testar as configurações especificadas em um arquivo</span><span class="sxs-lookup"><span data-stu-id="a3673-135">Example 5: Test configurations specified in a file</span></span>

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

<span data-ttu-id="a3673-136">Esse comando testa uma configuração definida em um arquivo em relação a um conjunto de computadores especificado pelo parâmetro *ComputerName* .</span><span class="sxs-lookup"><span data-stu-id="a3673-136">This command tests a configuration defined in a file against a set of computers specified by the *ComputerName* parameter.</span></span>

## <span data-ttu-id="a3673-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3673-137">PARAMETERS</span></span>

### <span data-ttu-id="a3673-138">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a3673-138">-AsJob</span></span>
<span data-ttu-id="a3673-139">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a3673-139">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="a3673-140">Se você especificar o parâmetro *AsJob* , o comando retornará um objeto que representa o trabalho e, em seguida, exibirá o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="a3673-140">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="a3673-141">Você pode continuar a trabalhar na sessão até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="a3673-141">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="a3673-142">O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="a3673-142">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="a3673-143">Para gerenciar o trabalho, use os cmdlets Job.</span><span class="sxs-lookup"><span data-stu-id="a3673-143">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="a3673-144">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="a3673-144">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a3673-145">Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e no Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="a3673-145">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="a3673-146">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3673-146">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="a3673-147">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a3673-147">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="a3673-148">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a3673-148">-CimSession</span></span>
<span data-ttu-id="a3673-149">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a3673-149">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="a3673-150">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="a3673-150">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="a3673-151">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="a3673-151">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a3673-152">-ComputerName</span></span>
<span data-ttu-id="a3673-153">Especifica uma matriz de nomes de computador em que esse cmdlet testa a configuração.</span><span class="sxs-lookup"><span data-stu-id="a3673-153">Specifies an array of computer names on which this cmdlet tests the configuration.</span></span>
<span data-ttu-id="a3673-154">O cmdlet testa o documento de configuração no local especificado pelo parâmetro *path* para esses computadores.</span><span class="sxs-lookup"><span data-stu-id="a3673-154">The cmdlet tests the configuration document in the location specified by the *Path* parameter to these computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="a3673-155">-Credential</span></span>
<span data-ttu-id="a3673-156">Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="a3673-156">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="a3673-157">Para obter um objeto **PSCredential** , use o cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="a3673-157">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="a3673-158">Para obter mais informações, digite `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="a3673-158">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-159">-Detailed</span><span class="sxs-lookup"><span data-stu-id="a3673-159">-Detailed</span></span>
<span data-ttu-id="a3673-160">Indica que esse cmdlet retorna um resultado detalhado da comparação do documento de configuração com o estado desejado dos nós.</span><span class="sxs-lookup"><span data-stu-id="a3673-160">Indicates that this cmdlet returns a detailed result of comparing the configuration document with the desired state of the nodes.</span></span>
<span data-ttu-id="a3673-161">O resultado inclui informações como o estado geral, os recursos que estão no estado desejado, os recursos que não estão no estado desejado e o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="a3673-161">The result includes information such as overall state, resources that are in the desired state, resources that are not in desired state, and computer name.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-162">-Path</span><span class="sxs-lookup"><span data-stu-id="a3673-162">-Path</span></span>
<span data-ttu-id="a3673-163">Especifica o caminho de uma pasta que contém arquivos de documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="a3673-163">Specifies the path of a folder that contains configuration document files.</span></span>
<span data-ttu-id="a3673-164">O cmdlet testa a configuração em relação ao estado desejado dos computadores especificados pelo parâmetro *ComputerName* ou *CimSession* .</span><span class="sxs-lookup"><span data-stu-id="a3673-164">The cmdlet tests the configuration against the desired state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-165">-ReferenceConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3673-165">-ReferenceConfiguration</span></span>
<span data-ttu-id="a3673-166">Especifica o caminho do arquivo de documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="a3673-166">Specifies the path of the configuration document file.</span></span>
<span data-ttu-id="a3673-167">Esse cmdlet testa a configuração em relação ao estado real dos computadores especificados pelo parâmetro *ComputerName* ou *CimSession* .</span><span class="sxs-lookup"><span data-stu-id="a3673-167">This cmdlet tests the configuration against the actual state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3673-168">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a3673-168">-ThrottleLimit</span></span>
<span data-ttu-id="a3673-169">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a3673-169">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="a3673-170">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="a3673-170">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="a3673-171">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="a3673-171">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a3673-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3673-172">CommonParameters</span></span>
<span data-ttu-id="a3673-173">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3673-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3673-174">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3673-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3673-175">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a3673-175">INPUTS</span></span>

## <span data-ttu-id="a3673-176">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a3673-176">OUTPUTS</span></span>

## <span data-ttu-id="a3673-177">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a3673-177">NOTES</span></span>

## <span data-ttu-id="a3673-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a3673-178">RELATED LINKS</span></span>

[<span data-ttu-id="a3673-179">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3673-179">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a3673-180">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3673-180">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a3673-181">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a3673-181">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="a3673-182">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3673-182">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="a3673-183">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3673-183">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)
