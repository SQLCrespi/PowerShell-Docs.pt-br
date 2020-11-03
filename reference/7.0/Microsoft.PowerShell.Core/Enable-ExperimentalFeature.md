---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-experimentalfeature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ExperimentalFeature
ms.openlocfilehash: 79884c73bc6e010eb218f1b722d26e0aaa05ef53
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193062"
---
# <span data-ttu-id="f1772-102">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="f1772-102">Enable-ExperimentalFeature</span></span>

## <span data-ttu-id="f1772-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f1772-103">SYNOPSIS</span></span>
<span data-ttu-id="f1772-104">Habilite um recurso experimental na inicialização da nova instância do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1772-104">Enable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="f1772-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1772-105">SYNTAX</span></span>

```
Enable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f1772-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1772-106">DESCRIPTION</span></span>

<span data-ttu-id="f1772-107">O `Enable-ExperimentalFeature` cmdlet habilita recursos experimentais adicionando os recursos experimentais nomeados ao `powershell.config.json` arquivo de configurações ler na inicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1772-107">The `Enable-ExperimentalFeature` cmdlet enables experimental features by adding the named experimental features to the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="f1772-108">Esse cmdlet foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="f1772-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="f1772-109">Todas as alterações no estado do recurso experimental só entrarão em vigor na reinicialização do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1772-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="f1772-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f1772-110">EXAMPLES</span></span>

### <span data-ttu-id="f1772-111">Exemplo 1: habilitar um recurso experimental</span><span class="sxs-lookup"><span data-stu-id="f1772-111">Example 1: Enable an experimental feature</span></span>

<span data-ttu-id="f1772-112">Neste exemplo, se esse recurso experimental tiver sido desabilitado anteriormente, o `powershell.config.json` arquivo será atualizado para que o usuário habilite esse recurso depois que o PowerShell for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f1772-112">In this example, if this experimental feature was previously disabled, then the `powershell.config.json` file is updated for the user to enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="f1772-113">Após o êxito, nada é apresentado para o pipeline e apenas uma mensagem de aviso é exibida.</span><span class="sxs-lookup"><span data-stu-id="f1772-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
Enable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="f1772-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1772-114">PARAMETERS</span></span>

### <span data-ttu-id="f1772-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f1772-115">-Confirm</span></span>

<span data-ttu-id="f1772-116">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1772-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f1772-117">-Name</span><span class="sxs-lookup"><span data-stu-id="f1772-117">-Name</span></span>

<span data-ttu-id="f1772-118">O nome ou os nomes dos recursos experimentais a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="f1772-118">The name or names of the experimental features to enable.</span></span>

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

### <span data-ttu-id="f1772-119">-Escopo</span><span class="sxs-lookup"><span data-stu-id="f1772-119">-Scope</span></span>

<span data-ttu-id="f1772-120">Determina qual `powershell.config.json` atualizar se ele afeta todos os usuários ou apenas o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1772-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

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

### <span data-ttu-id="f1772-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f1772-121">-WhatIf</span></span>

<span data-ttu-id="f1772-122">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f1772-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f1772-123">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f1772-123">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f1772-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1772-124">CommonParameters</span></span>

<span data-ttu-id="f1772-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1772-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1772-126">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1772-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1772-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f1772-127">INPUTS</span></span>

### <span data-ttu-id="f1772-128">ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="f1772-128">ExperimentalFeature</span></span>

<span data-ttu-id="f1772-129">Instâncias de pipe de ExperimentalFeature do `Get-ExperimentalFeature` cmdlet para habilitar.</span><span class="sxs-lookup"><span data-stu-id="f1772-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to enable.</span></span>

## <span data-ttu-id="f1772-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f1772-130">OUTPUTS</span></span>

### <span data-ttu-id="f1772-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f1772-131">None</span></span>

<span data-ttu-id="f1772-132">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f1772-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="f1772-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f1772-133">NOTES</span></span>

<span data-ttu-id="f1772-134">As alterações no estado de um recurso experimental só entram em vigor na reinicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1772-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="f1772-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f1772-135">RELATED LINKS</span></span>

[<span data-ttu-id="f1772-136">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="f1772-136">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="f1772-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="f1772-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)
