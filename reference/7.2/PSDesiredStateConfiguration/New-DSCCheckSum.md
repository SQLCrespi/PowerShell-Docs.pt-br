---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 8b8d0c545cdb36b6184a0670a52a5a30aa33a465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596995"
---
# <span data-ttu-id="28f5e-102">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="28f5e-102">New-DscChecksum</span></span>

## <span data-ttu-id="28f5e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="28f5e-103">SYNOPSIS</span></span>
<span data-ttu-id="28f5e-104">Cria arquivos de soma de verificação para documentos DSC e recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="28f5e-104">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="28f5e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28f5e-105">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="28f5e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28f5e-106">DESCRIPTION</span></span>

<span data-ttu-id="28f5e-107">O cmdlet **New-DSCCheckSum** gera arquivos de soma de verificação para documentos de DSC (configuração de estado desejado) do PowerShell e recursos de DSC compactados.</span><span class="sxs-lookup"><span data-stu-id="28f5e-107">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="28f5e-108">Esse cmdlet gera um arquivo de soma de verificação para cada configuração e recurso a ser usado no modo de pull.</span><span class="sxs-lookup"><span data-stu-id="28f5e-108">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="28f5e-109">O serviço DSC usa as somas de verificação para verificar se a configuração e os recursos corretos existem no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="28f5e-109">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="28f5e-110">Coloque as somas de verificação junto com os documentos DSC associados e os recursos de DSC compactados no armazenamento do serviço DSC.</span><span class="sxs-lookup"><span data-stu-id="28f5e-110">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="28f5e-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="28f5e-111">EXAMPLES</span></span>

### <span data-ttu-id="28f5e-112">Exemplo 1: criar arquivos de soma de verificação para todas as configurações em um caminho específico</span><span class="sxs-lookup"><span data-stu-id="28f5e-112">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="28f5e-113">Este comando cria arquivos de soma de verificação para todas as configurações no caminho C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="28f5e-113">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="28f5e-114">Todos os arquivos de soma de verificação que já existem são ignorados.</span><span class="sxs-lookup"><span data-stu-id="28f5e-114">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="28f5e-115">Exemplo 2: criar arquivos de soma de verificação para todas as configurações em um caminho específico e substituir os arquivos de soma de verificação existentes</span><span class="sxs-lookup"><span data-stu-id="28f5e-115">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="28f5e-116">Este comando cria novos arquivos de soma de verificação para todas as configurações no caminho C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="28f5e-116">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="28f5e-117">A especificação do parâmetro *Force* faz com que o comando Substitua todos os arquivos de soma de verificação que já existem.</span><span class="sxs-lookup"><span data-stu-id="28f5e-117">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="28f5e-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28f5e-118">PARAMETERS</span></span>

### <span data-ttu-id="28f5e-119">-Confirm</span><span class="sxs-lookup"><span data-stu-id="28f5e-119">-Confirm</span></span>

<span data-ttu-id="28f5e-120">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28f5e-120">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="28f5e-121">-Force</span><span class="sxs-lookup"><span data-stu-id="28f5e-121">-Force</span></span>

<span data-ttu-id="28f5e-122">Indica que o cmdlet substitui o arquivo de saída especificado se ele já existir.</span><span class="sxs-lookup"><span data-stu-id="28f5e-122">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="28f5e-123">-OutPath</span><span class="sxs-lookup"><span data-stu-id="28f5e-123">-OutPath</span></span>

<span data-ttu-id="28f5e-124">Especifica o caminho e o nome do arquivo de soma de verificação de saída.</span><span class="sxs-lookup"><span data-stu-id="28f5e-124">Specifies the path and file name of the output checksum file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28f5e-125">-Path</span><span class="sxs-lookup"><span data-stu-id="28f5e-125">-Path</span></span>

<span data-ttu-id="28f5e-126">Especifica o caminho do arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="28f5e-126">Specifies the path of the input file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28f5e-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="28f5e-127">-WhatIf</span></span>

<span data-ttu-id="28f5e-128">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="28f5e-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="28f5e-129">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="28f5e-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="28f5e-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28f5e-130">CommonParameters</span></span>

<span data-ttu-id="28f5e-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28f5e-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28f5e-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28f5e-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28f5e-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="28f5e-133">INPUTS</span></span>

### <span data-ttu-id="28f5e-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="28f5e-134">None</span></span>

## <span data-ttu-id="28f5e-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="28f5e-135">OUTPUTS</span></span>

### <span data-ttu-id="28f5e-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="28f5e-136">System.Object</span></span>

## <span data-ttu-id="28f5e-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="28f5e-137">NOTES</span></span>

## <span data-ttu-id="28f5e-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="28f5e-138">RELATED LINKS</span></span>

[<span data-ttu-id="28f5e-139">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28f5e-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

