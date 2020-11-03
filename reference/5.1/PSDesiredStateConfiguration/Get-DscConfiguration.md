---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194155"
---
# <span data-ttu-id="aa5cc-103">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa5cc-103">Get-DscConfiguration</span></span>

## <span data-ttu-id="aa5cc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa5cc-104">SYNOPSIS</span></span>
<span data-ttu-id="aa5cc-105">Obtém a configuração atual dos nós.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-105">Gets the current configuration of the nodes.</span></span>

## <span data-ttu-id="aa5cc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa5cc-106">SYNTAX</span></span>

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="aa5cc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa5cc-107">DESCRIPTION</span></span>
<span data-ttu-id="aa5cc-108">O cmdlet **Get-DscConfiguration** Obtém a configuração atual dos nós, se a configuração existir.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-108">The **Get-DscConfiguration** cmdlet gets the current configuration of the nodes, if the configuration exists.</span></span>
<span data-ttu-id="aa5cc-109">Especifique computadores usando sessões CIM (Common Information Model).</span><span class="sxs-lookup"><span data-stu-id="aa5cc-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="aa5cc-110">Se você não especificar um computador de destino, o cmdlet obtém a configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-110">If you do not specify a target computer, the cmdlet gets the configuration from the local computer.</span></span>

## <span data-ttu-id="aa5cc-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa5cc-111">EXAMPLES</span></span>

### <span data-ttu-id="aa5cc-112">Exemplo 1: obter a configuração para o computador local</span><span class="sxs-lookup"><span data-stu-id="aa5cc-112">Example 1: Get the configuration for the local computer</span></span>

```
PS C:\> Get-DscConfiguration
```

<span data-ttu-id="aa5cc-113">Esse comando obtém o estado atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-113">This command gets the current state for the local computer.</span></span>

### <span data-ttu-id="aa5cc-114">Exemplo 2: obter a configuração para um computador especificado</span><span class="sxs-lookup"><span data-stu-id="aa5cc-114">Example 2: Get the configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

<span data-ttu-id="aa5cc-115">Este exemplo obtém o estado atual de um computador especificado por uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-115">This example gets the current state from a computer specified by a CIM session.</span></span>
<span data-ttu-id="aa5cc-116">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-116">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="aa5cc-117">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-117">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="aa5cc-118">O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável **$Session** .</span><span class="sxs-lookup"><span data-stu-id="aa5cc-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the **$Session** variable.</span></span>
<span data-ttu-id="aa5cc-119">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-119">The command prompts you for a password.</span></span>
<span data-ttu-id="aa5cc-120">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="aa5cc-121">O segundo comando obtém a configuração atual dos computadores identificados pelos objetos **CimSession** armazenados na variável **$Session** , nesse caso, o computador chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-121">The second command gets the current configuration for the computers identified by the **CimSession** objects stored in the **$Session** variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="aa5cc-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa5cc-122">PARAMETERS</span></span>

### <span data-ttu-id="aa5cc-123">-AsJob</span><span class="sxs-lookup"><span data-stu-id="aa5cc-123">-AsJob</span></span>
<span data-ttu-id="aa5cc-124">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-124">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="aa5cc-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="aa5cc-125">-CimSession</span></span>
<span data-ttu-id="aa5cc-126">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="aa5cc-127">Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="aa5cc-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="aa5cc-128">O padrão é a sessão atual do computador local.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="aa5cc-129">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="aa5cc-129">-ThrottleLimit</span></span>
<span data-ttu-id="aa5cc-130">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-130">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="aa5cc-131">Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-131">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="aa5cc-132">O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-132">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="aa5cc-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa5cc-133">CommonParameters</span></span>
<span data-ttu-id="aa5cc-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa5cc-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa5cc-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa5cc-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa5cc-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa5cc-136">INPUTS</span></span>

## <span data-ttu-id="aa5cc-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa5cc-137">OUTPUTS</span></span>

## <span data-ttu-id="aa5cc-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa5cc-138">NOTES</span></span>

## <span data-ttu-id="aa5cc-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa5cc-139">RELATED LINKS</span></span>

[<span data-ttu-id="aa5cc-140">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa5cc-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="aa5cc-141">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="aa5cc-141">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="aa5cc-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa5cc-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="aa5cc-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa5cc-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="aa5cc-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa5cc-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
