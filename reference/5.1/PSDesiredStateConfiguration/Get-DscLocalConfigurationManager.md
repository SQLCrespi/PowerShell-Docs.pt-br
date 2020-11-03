---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194145"
---
# <span data-ttu-id="71ca2-103">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="71ca2-103">Get-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="71ca2-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="71ca2-104">SYNOPSIS</span></span>

<span data-ttu-id="71ca2-105">Obtém as configurações e os Estados do LCM (Configuration Manager local) para o nó.</span><span class="sxs-lookup"><span data-stu-id="71ca2-105">Gets Local Configuration Manager (LCM) settings and states for the node.</span></span>

## <span data-ttu-id="71ca2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71ca2-106">SYNTAX</span></span>

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="71ca2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71ca2-107">DESCRIPTION</span></span>

<span data-ttu-id="71ca2-108">O `Get-DscLocalConfigurationManager` cmdlet obtém as configurações do LCM, ou a metaconfiguração, e os Estados do LCM para o nó.</span><span class="sxs-lookup"><span data-stu-id="71ca2-108">The `Get-DscLocalConfigurationManager` cmdlet gets LCM settings, or meta-configuration, and the states of LCM for the node.</span></span> <span data-ttu-id="71ca2-109">Especifique computadores usando sessões CIM (Common Information Model).</span><span class="sxs-lookup"><span data-stu-id="71ca2-109">Specify computers by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="71ca2-110">Se você não especificar um computador de destino, o cmdlet obterá as definições de configuração do computador local.</span><span class="sxs-lookup"><span data-stu-id="71ca2-110">If you do not specify a target computer, the cmdlet gets the configuration settings from the local computer.</span></span>

## <span data-ttu-id="71ca2-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="71ca2-111">EXAMPLES</span></span>

### <span data-ttu-id="71ca2-112">Exemplo 1: obter as configurações do LCM para o computador local</span><span class="sxs-lookup"><span data-stu-id="71ca2-112">Example 1: Get LCM settings for the local computer</span></span>

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

<span data-ttu-id="71ca2-113">Esse comando obtém as configurações do LCM para o computador local.</span><span class="sxs-lookup"><span data-stu-id="71ca2-113">This command gets LCM settings for the local computer.</span></span>

<span data-ttu-id="71ca2-114">Para obter mais informações sobre os atributos individuais da saída, consulte a documentação [Configurando a Configuration Manager local](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) .</span><span class="sxs-lookup"><span data-stu-id="71ca2-114">For more information on the individual attributes of the output, see the [Configuring the Local Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) documentation.</span></span>

### <span data-ttu-id="71ca2-115">Exemplo 2: obter as configurações do LCM para um computador especificado</span><span class="sxs-lookup"><span data-stu-id="71ca2-115">Example 2: Get LCM settings for a specified computer</span></span>

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

<span data-ttu-id="71ca2-116">Este exemplo obtém as configurações do LCM para um computador especificado por uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="71ca2-116">This example gets LCM settings for a computer specified by a CIM session.</span></span>
<span data-ttu-id="71ca2-117">O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71ca2-117">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="71ca2-118">Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="71ca2-118">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="71ca2-119">O primeiro comando cria uma sessão CIM usando o `New-CimSession` cmdlet e, em seguida, armazena o objeto **CimSession** na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="71ca2-119">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span> <span data-ttu-id="71ca2-120">O comando solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="71ca2-120">The command prompts you for a password.</span></span> <span data-ttu-id="71ca2-121">Para obter mais informações, digite `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="71ca2-121">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="71ca2-122">O segundo comando obtém as configurações de Configuration Manager locais para os computadores identificados pelos objetos **CimSession** armazenados na variável $Session.</span><span class="sxs-lookup"><span data-stu-id="71ca2-122">The second command gets Local Configuration Manager settings for the computers identified by the **CimSession** objects stored in the $Session variable.</span></span> <span data-ttu-id="71ca2-123">Nesse caso, o computador chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="71ca2-123">In this case, the computer named Server01.</span></span>

## <span data-ttu-id="71ca2-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71ca2-124">PARAMETERS</span></span>

### <span data-ttu-id="71ca2-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="71ca2-125">-AsJob</span></span>

<span data-ttu-id="71ca2-126">Indica que esse cmdlet executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="71ca2-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="71ca2-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="71ca2-127">-CimSession</span></span>

<span data-ttu-id="71ca2-128">Executa o cmdlet em uma sessão remota ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="71ca2-128">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="71ca2-129">Insira um nome de computador ou um objeto de sessão, como a saída de `New-CimSession` um `Get-CimSession` cmdlet ou.</span><span class="sxs-lookup"><span data-stu-id="71ca2-129">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

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

### <span data-ttu-id="71ca2-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="71ca2-130">-ThrottleLimit</span></span>

<span data-ttu-id="71ca2-131">Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71ca2-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="71ca2-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="71ca2-132">CommonParameters</span></span>

<span data-ttu-id="71ca2-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71ca2-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71ca2-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="71ca2-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71ca2-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="71ca2-135">INPUTS</span></span>

## <span data-ttu-id="71ca2-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="71ca2-136">OUTPUTS</span></span>

## <span data-ttu-id="71ca2-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="71ca2-137">NOTES</span></span>

## <span data-ttu-id="71ca2-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="71ca2-138">RELATED LINKS</span></span>

[<span data-ttu-id="71ca2-139">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71ca2-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="71ca2-140">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="71ca2-140">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)
