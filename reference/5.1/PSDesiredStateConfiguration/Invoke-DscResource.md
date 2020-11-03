---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194144"
---
# <span data-ttu-id="031dc-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="031dc-103">Invoke-DscResource</span></span>

## <span data-ttu-id="031dc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="031dc-104">SYNOPSIS</span></span>
<span data-ttu-id="031dc-105">Executa um método de um recurso de DSC especificado.</span><span class="sxs-lookup"><span data-stu-id="031dc-105">Runs a method of a specified DSC resource.</span></span>

## <span data-ttu-id="031dc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="031dc-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## <span data-ttu-id="031dc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="031dc-107">DESCRIPTION</span></span>
<span data-ttu-id="031dc-108">O cmdlet **Invoke-DscResource** executa um método de um recurso de DSC (configuração de estado desejado) do Windows PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="031dc-108">The **Invoke-DscResource** cmdlet runs a method of a specified Windows PowerShell Desired State Configuration (DSC) resource.</span></span>
<span data-ttu-id="031dc-109">Antes de executar este cmdlet, defina o modo de atualização do Configuration Manager local (LCM) como desabilitado.</span><span class="sxs-lookup"><span data-stu-id="031dc-109">Before you run this cmdlet, set the refresh mode of the Local Configuration Manager (LCM) to Disabled.</span></span>

<span data-ttu-id="031dc-110">Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="031dc-110">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span>
<span data-ttu-id="031dc-111">Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows usando recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="031dc-111">Using this cmdlet, configuration management products can manage windows by using DSC resources.</span></span>
<span data-ttu-id="031dc-112">Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC ou o LCM está em execução com a depuração habilitada.</span><span class="sxs-lookup"><span data-stu-id="031dc-112">This cmdlet also enables debugging of resources when the DSC engine or LCM is running with debugging enabled.</span></span>

## <span data-ttu-id="031dc-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="031dc-113">EXAMPLES</span></span>

### <span data-ttu-id="031dc-114">Exemplo 1: invocar o método set de um recurso especificando suas propriedades obrigatórias</span><span class="sxs-lookup"><span data-stu-id="031dc-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="031dc-115">Esse comando invoca o método **set** de um recurso chamado log e especifica uma propriedade de **mensagem** para ele.</span><span class="sxs-lookup"><span data-stu-id="031dc-115">This command invokes the **Set** method of a resource named Log and specifies a **Message** property for it.</span></span>

### <span data-ttu-id="031dc-116">Exemplo 2: invocar o método de teste de um recurso para um módulo especificado</span><span class="sxs-lookup"><span data-stu-id="031dc-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="031dc-117">Esse comando invoca o método de **teste** de um recurso chamado WindowsProcess, que está no módulo chamado PSDesiredStateConfiguration.</span><span class="sxs-lookup"><span data-stu-id="031dc-117">This command invokes the **Test** method of a resource named WindowsProcess, which is in the module named PSDesiredStateConfiguration.</span></span>

## <span data-ttu-id="031dc-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="031dc-118">PARAMETERS</span></span>

### <span data-ttu-id="031dc-119">-Método</span><span class="sxs-lookup"><span data-stu-id="031dc-119">-Method</span></span>
<span data-ttu-id="031dc-120">Especifica o método do recurso que esse cmdlet invoca.</span><span class="sxs-lookup"><span data-stu-id="031dc-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="031dc-121">Os valores aceitáveis para esse parâmetro são: Get, set e Test.</span><span class="sxs-lookup"><span data-stu-id="031dc-121">The acceptable values for this parameter are: Get, Set, and Test.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="031dc-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="031dc-122">-ModuleName</span></span>
<span data-ttu-id="031dc-123">Especifica o nome do módulo do qual este cmdlet invoca o recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="031dc-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="031dc-124">-Name</span><span class="sxs-lookup"><span data-stu-id="031dc-124">-Name</span></span>
<span data-ttu-id="031dc-125">Especifica o nome do recurso DSC a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="031dc-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="031dc-126">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="031dc-126">-Property</span></span>
<span data-ttu-id="031dc-127">Especifica o nome da propriedade de recurso e seu valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="031dc-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="031dc-128">Use o cmdlet **Get-DscResource** para descobrir as propriedades de recurso e seus tipos.</span><span class="sxs-lookup"><span data-stu-id="031dc-128">Use the **Get-DscResource** cmdlet to discover resource properties and their types.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="031dc-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="031dc-129">CommonParameters</span></span>
<span data-ttu-id="031dc-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="031dc-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="031dc-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="031dc-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="031dc-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="031dc-132">INPUTS</span></span>

## <span data-ttu-id="031dc-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="031dc-133">OUTPUTS</span></span>

### <span data-ttu-id="031dc-134">Microsoft. Management. Infrastructure. CimInstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="031dc-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="031dc-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="031dc-135">NOTES</span></span>

## <span data-ttu-id="031dc-136">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="031dc-136">RELATED LINKS</span></span>

[<span data-ttu-id="031dc-137">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="031dc-137">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="031dc-138">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="031dc-138">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="031dc-139">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="031dc-139">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="031dc-140">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="031dc-140">Get-DscResource</span></span>](Get-DscResource.md)

[<span data-ttu-id="031dc-141">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="031dc-141">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="031dc-142">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="031dc-142">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)

[<span data-ttu-id="031dc-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="031dc-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="031dc-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="031dc-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
