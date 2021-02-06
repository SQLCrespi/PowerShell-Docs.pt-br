---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: e35e164f3116304efd52c71c1715ba70711f6253
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597817"
---
# <span data-ttu-id="31f51-102">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="31f51-102">Disable-ExperimentalFeature</span></span>

## <span data-ttu-id="31f51-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="31f51-103">SYNOPSIS</span></span>
<span data-ttu-id="31f51-104">Desabilite um recurso experimental na inicialização da nova instância do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31f51-104">Disable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="31f51-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31f51-105">SYNTAX</span></span>

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="31f51-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31f51-106">DESCRIPTION</span></span>

<span data-ttu-id="31f51-107">O `Disable-ExperimentalFeature` cmdlet desabilita os recursos experimentais removendo os recursos experimentais nomeados do `powershell.config.json` arquivo de configurações ler na inicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31f51-107">The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named experimental features from the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="31f51-108">Esse cmdlet foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="31f51-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="31f51-109">Todas as alterações no estado do recurso experimental só entrarão em vigor na reinicialização do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31f51-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="31f51-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="31f51-110">EXAMPLES</span></span>

### <span data-ttu-id="31f51-111">Exemplo 1: desabilitar um recurso experimental</span><span class="sxs-lookup"><span data-stu-id="31f51-111">Example 1: Disable an experimental feature</span></span>

<span data-ttu-id="31f51-112">Neste exemplo, se esse recurso experimental tiver sido habilitado anteriormente, o `powershell.config.json` arquivo será atualizado para que o usuário não habilite esse recurso depois que o PowerShell for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="31f51-112">In this example, if this experimental feature was previously enabled, then the `powershell.config.json` file is updated for the user to not enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="31f51-113">Após o êxito, nada é apresentado para o pipeline e apenas uma mensagem de aviso é exibida.</span><span class="sxs-lookup"><span data-stu-id="31f51-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="31f51-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31f51-114">PARAMETERS</span></span>

### <span data-ttu-id="31f51-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="31f51-115">-Confirm</span></span>

<span data-ttu-id="31f51-116">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="31f51-116">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31f51-117">-Name</span><span class="sxs-lookup"><span data-stu-id="31f51-117">-Name</span></span>

<span data-ttu-id="31f51-118">O nome ou os nomes dos recursos experimentais a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="31f51-118">The name or names of the experimental features to disable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="31f51-119">-Escopo</span><span class="sxs-lookup"><span data-stu-id="31f51-119">-Scope</span></span>

<span data-ttu-id="31f51-120">Determina qual `powershell.config.json` atualizar se ele afeta todos os usuários ou apenas o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="31f51-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31f51-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="31f51-121">-WhatIf</span></span>

<span data-ttu-id="31f51-122">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="31f51-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="31f51-123">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="31f51-123">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31f51-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31f51-124">CommonParameters</span></span>

<span data-ttu-id="31f51-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31f51-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31f51-126">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31f51-126">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31f51-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="31f51-127">INPUTS</span></span>

### <span data-ttu-id="31f51-128">ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="31f51-128">ExperimentalFeature</span></span>

<span data-ttu-id="31f51-129">Instâncias de pipe de ExperimentalFeature do `Get-ExperimentalFeature` cmdlet a ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="31f51-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to disable.</span></span>

## <span data-ttu-id="31f51-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="31f51-130">OUTPUTS</span></span>

### <span data-ttu-id="31f51-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="31f51-131">None</span></span>

<span data-ttu-id="31f51-132">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="31f51-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="31f51-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="31f51-133">NOTES</span></span>

<span data-ttu-id="31f51-134">As alterações no estado de um recurso experimental só entram em vigor na reinicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31f51-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="31f51-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="31f51-135">RELATED LINKS</span></span>

[<span data-ttu-id="31f51-136">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="31f51-136">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)

[<span data-ttu-id="31f51-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="31f51-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

