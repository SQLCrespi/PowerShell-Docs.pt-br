---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: e81302a442294a7eeab81c6e8e1c6b7fd0cfb5fe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597215"
---
# <span data-ttu-id="e64aa-102">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="e64aa-102">Get-PSSessionCapability</span></span>

## <span data-ttu-id="e64aa-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e64aa-103">SYNOPSIS</span></span>
<span data-ttu-id="e64aa-104">Obtém os recursos de um usuário específico em uma configuração de sessão restrita.</span><span class="sxs-lookup"><span data-stu-id="e64aa-104">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="e64aa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e64aa-105">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="e64aa-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e64aa-106">DESCRIPTION</span></span>

<span data-ttu-id="e64aa-107">O cmdlet **Get-PSSessionCapability** Obtém os recursos de um usuário específico em uma configuração de sessão restrita.</span><span class="sxs-lookup"><span data-stu-id="e64aa-107">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="e64aa-108">Use este cmdlet para auditar configurações de sessão personalizadas para usuários.</span><span class="sxs-lookup"><span data-stu-id="e64aa-108">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="e64aa-109">A partir do Windows PowerShell 5,0, você pode usar a propriedade **RoleDefinitions** em um arquivo de configuração de sessão (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="e64aa-109">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="e64aa-110">O uso dessa propriedade permite que você conceda aos usuários recursos diferentes em um único ponto de extremidade restrito com base na associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="e64aa-110">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="e64aa-111">O cmdlet **Get-PSSessionCapability** reduz a complexidade ao auditar esses pontos de extremidade, permitindo que você determine os recursos exatos concedidos a um usuário.</span><span class="sxs-lookup"><span data-stu-id="e64aa-111">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="e64aa-112">Por padrão, o cmdlet **Get-PSSessionCapability** retorna uma lista de comandos que o usuário especificado pode executar no ponto de extremidade especificado.</span><span class="sxs-lookup"><span data-stu-id="e64aa-112">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="e64aa-113">Isso é equivalente ao usuário que está executando **Get-Command** no ponto de extremidade especificado.</span><span class="sxs-lookup"><span data-stu-id="e64aa-113">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="e64aa-114">Quando executado com o parâmetro *Full* , esse cmdlet retorna um objeto **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="e64aa-114">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="e64aa-115">Este objeto contém detalhes sobre o runspace do PowerShell que o usuário especificado interagiria com o ponto de extremidade especificado.</span><span class="sxs-lookup"><span data-stu-id="e64aa-115">This object contains details about the PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="e64aa-116">Ele inclui informações como o modo de linguagem, a política de execução e as variáveis ambientais.</span><span class="sxs-lookup"><span data-stu-id="e64aa-116">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="e64aa-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e64aa-117">EXAMPLES</span></span>

### <span data-ttu-id="e64aa-118">Exemplo 1: obter os comandos disponíveis para um usuário</span><span class="sxs-lookup"><span data-stu-id="e64aa-118">Example 1: Get commands available for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="e64aa-119">Este exemplo retorna os comandos disponíveis para o usuário CONTOSO\User ao se conectar ao ponto de extremidade restrito do Endpoint1 no computador local.</span><span class="sxs-lookup"><span data-stu-id="e64aa-119">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="e64aa-120">Exemplo 2: obter detalhes sobre um runspace para um usuário</span><span class="sxs-lookup"><span data-stu-id="e64aa-120">Example 2: Get details about a runspace for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="e64aa-121">Este exemplo retorna detalhes sobre o runspace ao qual o usuário CONTOSO\User interagiria ao se conectar ao ponto de extremidade restrito de Endpoint1.</span><span class="sxs-lookup"><span data-stu-id="e64aa-121">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="e64aa-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e64aa-122">PARAMETERS</span></span>

### <span data-ttu-id="e64aa-123">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e64aa-123">-ConfigurationName</span></span>

<span data-ttu-id="e64aa-124">Especifica a configuração de sessão restrita (ponto de extremidade) que você está inspecionando.</span><span class="sxs-lookup"><span data-stu-id="e64aa-124">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

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

### <span data-ttu-id="e64aa-125">-Full</span><span class="sxs-lookup"><span data-stu-id="e64aa-125">-Full</span></span>

<span data-ttu-id="e64aa-126">Indica que esse cmdlet retorna o estado de sessão inicial inteiro para o usuário especificado no ponto de extremidade restrito especificado.</span><span class="sxs-lookup"><span data-stu-id="e64aa-126">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

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

### <span data-ttu-id="e64aa-127">-Username</span><span class="sxs-lookup"><span data-stu-id="e64aa-127">-Username</span></span>

<span data-ttu-id="e64aa-128">Especifica o usuário cujos recursos você está inspecionando.</span><span class="sxs-lookup"><span data-stu-id="e64aa-128">Specifies the user whose capabilities you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e64aa-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e64aa-129">CommonParameters</span></span>

<span data-ttu-id="e64aa-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e64aa-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e64aa-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e64aa-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e64aa-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e64aa-132">INPUTS</span></span>

## <span data-ttu-id="e64aa-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e64aa-133">OUTPUTS</span></span>

### <span data-ttu-id="e64aa-134">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="e64aa-134">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="e64aa-135">System. Management. Automation. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="e64aa-135">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="e64aa-136">System.Management.Automation.Runspaces.InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="e64aa-136">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="e64aa-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e64aa-137">NOTES</span></span>

## <span data-ttu-id="e64aa-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e64aa-138">RELATED LINKS</span></span>

[<span data-ttu-id="e64aa-139">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="e64aa-139">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)

