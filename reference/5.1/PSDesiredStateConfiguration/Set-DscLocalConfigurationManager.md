---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "93194838"
---
# <span data-ttu-id="e4187-103">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="e4187-103">Set-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="e4187-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e4187-104">SYNOPSIS</span></span>

<span data-ttu-id="e4187-105">Aplica as configurações de Configuration Manager local (LCM) a nós.</span><span class="sxs-lookup"><span data-stu-id="e4187-105">Applies Local Configuration Manager (LCM) settings to nodes.</span></span>

## <span data-ttu-id="e4187-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4187-106">SYNTAX</span></span>

### <span data-ttu-id="e4187-107">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="e4187-107">ComputerNameSet (Default)</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4187-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="e4187-108">CimSessionSet</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e4187-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4187-109">DESCRIPTION</span></span>

<span data-ttu-id="e4187-110">O `Set-DscLocalConfigurationManager` cmdlet aplica as configurações do LCM, ou metaconfiguração, aos nós.</span><span class="sxs-lookup"><span data-stu-id="e4187-110">The `Set-DscLocalConfigurationManager` cmdlet applies LCM settings, or meta-configuration, to nodes.</span></span> <span data-ttu-id="e4187-111">Especifique computadores especificando nomes de computador ou por meio de sessões CIM (Modelo de Informações Comuns).</span><span class="sxs-lookup"><span data-stu-id="e4187-111">Specify computers by specifying computer names or by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="e4187-112">Se você não especificar um computador de destino, o cmdlet aplicará as configurações ao computador local.</span><span class="sxs-lookup"><span data-stu-id="e4187-112">If you do not specify a target computer, the cmdlet applies settings to the local computer.</span></span>

## <span data-ttu-id="e4187-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e4187-113">EXAMPLES</span></span>

### <span data-ttu-id="e4187-114">Exemplo 1: aplicar as configurações do LCM</span><span class="sxs-lookup"><span data-stu-id="e4187-114">Example 1: Apply LCM settings</span></span>

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="e4187-115">Esse comando aplica as configurações do LCM a partir dos `C:\DSC\Configurations\` nós de destino.</span><span class="sxs-lookup"><span data-stu-id="e4187-115">This command applies the LCM settings from `C:\DSC\Configurations\` to the targeted nodes.</span></span> <span data-ttu-id="e4187-116">Depois de receber as configurações, o LCM as processa.</span><span class="sxs-lookup"><span data-stu-id="e4187-116">After receiving the settings, LCM processes them.</span></span>

> [!WARNING]
> <span data-ttu-id="e4187-117">Se houver vários meta MOFs para o mesmo computador armazenado na pasta especificada, somente o primeiro meta MOF será aplicado.</span><span class="sxs-lookup"><span data-stu-id="e4187-117">If there are multiple meta mofs for the same computer stored in the specified folder, only the first meta mof will be applied.</span></span>

### <span data-ttu-id="e4187-118">Exemplo 2: aplicar as configurações do LCM usando uma sessão CIM</span><span class="sxs-lookup"><span data-stu-id="e4187-118">Example 2: Apply LCM settings by using a CIM session</span></span>

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="e4187-119">Este exemplo aplica as configurações do LCM a um computador e aplica as configurações.</span><span class="sxs-lookup"><span data-stu-id="e4187-119">This example applies LCM settings to a computer and applies the settings.</span></span> <span data-ttu-id="e4187-120">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4187-120">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span> <span data-ttu-id="e4187-121">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="e4187-121">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="e4187-122">O primeiro comando cria uma sessão CIM usando o `New-CimSession` cmdlet e, em seguida, armazena o objeto **CimSession** na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="e4187-122">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the `$Session` variable.</span></span> <span data-ttu-id="e4187-123">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="e4187-123">The command prompts you for a password.</span></span> <span data-ttu-id="e4187-124">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="e4187-124">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="e4187-125">O segundo comando aplica as configurações do LCM para o nó de destino do `C:\DSC\Configurations\` ao computador identificado pelos objetos **CimSession** armazenados na `$Session` variável.</span><span class="sxs-lookup"><span data-stu-id="e4187-125">The second command applies LCM settings for the targeted node from `C:\DSC\Configurations\` to the computer identified by the **CimSession** objects stored in the `$Session` variable.</span></span> <span data-ttu-id="e4187-126">Neste exemplo, a `$Session` variável contém uma sessão CIM somente para o computador chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="e4187-126">In this example, the `$Session` variable contains a CIM session only for the computer named Server01.</span></span> <span data-ttu-id="e4187-127">O comando aplica as configurações.</span><span class="sxs-lookup"><span data-stu-id="e4187-127">The command applies the settings.</span></span> <span data-ttu-id="e4187-128">Depois de receber as configurações, o LCM as processa.</span><span class="sxs-lookup"><span data-stu-id="e4187-128">After receiving the settings, LCM processes them.</span></span>

## <span data-ttu-id="e4187-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4187-129">PARAMETERS</span></span>

### <span data-ttu-id="e4187-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="e4187-130">-CimSession</span></span>

<span data-ttu-id="e4187-131">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e4187-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="e4187-132">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) ou [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) .</span><span class="sxs-lookup"><span data-stu-id="e4187-132">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.</span></span>
<span data-ttu-id="e4187-133">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="e4187-133">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="e4187-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e4187-134">-ComputerName</span></span>

<span data-ttu-id="e4187-135">Especifica uma matriz de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="e4187-135">Specifies an array of computer names.</span></span> <span data-ttu-id="e4187-136">Esse parâmetro restringe os computadores que têm documentos de metaconfiguração no parâmetro **path** para aqueles especificados na matriz.</span><span class="sxs-lookup"><span data-stu-id="e4187-136">This parameter restricts the computers that have meta-configuration documents in the **Path** parameter to those specified in the array.</span></span>

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

### <span data-ttu-id="e4187-137">-Credential</span><span class="sxs-lookup"><span data-stu-id="e4187-137">-Credential</span></span>

<span data-ttu-id="e4187-138">Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="e4187-138">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span> <span data-ttu-id="e4187-139">Para obter um objeto **PSCredential** , use o cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="e4187-139">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span> <span data-ttu-id="e4187-140">Para obter mais informações, digite `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="e4187-140">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="e4187-141">-Force</span><span class="sxs-lookup"><span data-stu-id="e4187-141">-Force</span></span>

<span data-ttu-id="e4187-142">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4187-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e4187-143">-Path</span><span class="sxs-lookup"><span data-stu-id="e4187-143">-Path</span></span>

<span data-ttu-id="e4187-144">Especifica um caminho de arquivo de uma pasta que contém arquivos de definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="e4187-144">Specifies a file path of a folder that contains configuration settings files.</span></span> <span data-ttu-id="e4187-145">O cmdlet publica e aplica essas configurações de LCM a computadores que têm arquivos de configurações no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="e4187-145">The cmdlet publishes and applies these LCM settings to computers that have settings files in the specified path.</span></span> <span data-ttu-id="e4187-146">Cada nó de destino deve ter um arquivo de configurações do seguinte formato: `NetBIOS Name.meta.mof` .</span><span class="sxs-lookup"><span data-stu-id="e4187-146">Each target node must have a settings file of the following format: `NetBIOS Name.meta.mof`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4187-147">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="e4187-147">-ThrottleLimit</span></span>

<span data-ttu-id="e4187-148">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4187-148">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span> <span data-ttu-id="e4187-149">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="e4187-149">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="e4187-150">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="e4187-150">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="e4187-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4187-151">-Confirm</span></span>

<span data-ttu-id="e4187-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e4187-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e4187-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4187-153">-WhatIf</span></span>

<span data-ttu-id="e4187-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e4187-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e4187-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e4187-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e4187-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4187-156">CommonParameters</span></span>

<span data-ttu-id="e4187-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4187-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4187-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4187-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4187-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e4187-159">INPUTS</span></span>

## <span data-ttu-id="e4187-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e4187-160">OUTPUTS</span></span>

## <span data-ttu-id="e4187-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e4187-161">NOTES</span></span>

## <span data-ttu-id="e4187-162">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e4187-162">RELATED LINKS</span></span>

[<span data-ttu-id="e4187-163">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4187-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="e4187-164">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="e4187-164">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)
