---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: fb069e6c8e47266a34a7ab46e2ecb61fdcdb25fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193766"
---
# <span data-ttu-id="aa3be-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="aa3be-103">New-TemporaryFile</span></span>

## <span data-ttu-id="aa3be-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa3be-104">SYNOPSIS</span></span>
<span data-ttu-id="aa3be-105">Cria um arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="aa3be-105">Creates a temporary file.</span></span>

## <span data-ttu-id="aa3be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa3be-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="aa3be-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa3be-107">DESCRIPTION</span></span>

<span data-ttu-id="aa3be-108">Esse cmdlet cria arquivos temporários que você pode usar em scripts.</span><span class="sxs-lookup"><span data-stu-id="aa3be-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="aa3be-109">O `New-TemporaryFile` cmdlet cria um arquivo vazio que tem a `.tmp` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa3be-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="aa3be-110">Esse cmdlet nomeia o arquivo `tmp<NNNN>.tmp` , em que `<NNNN>` é um número hexadecimal aleatório.</span><span class="sxs-lookup"><span data-stu-id="aa3be-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="aa3be-111">O cmdlet cria o arquivo em sua pasta **temporária** .</span><span class="sxs-lookup"><span data-stu-id="aa3be-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="aa3be-112">Esse cmdlet usa o método [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) para localizar a pasta **Temp** .</span><span class="sxs-lookup"><span data-stu-id="aa3be-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="aa3be-113">Esse método verifica a existência de variáveis de ambiente na seguinte ordem e usa o primeiro caminho encontrado:</span><span class="sxs-lookup"><span data-stu-id="aa3be-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="aa3be-114">Em plataformas Windows:</span><span class="sxs-lookup"><span data-stu-id="aa3be-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="aa3be-115">O caminho especificado pela variável de ambiente TMP.</span><span class="sxs-lookup"><span data-stu-id="aa3be-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="aa3be-116">O caminho especificado pela variável de ambiente TEMP.</span><span class="sxs-lookup"><span data-stu-id="aa3be-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="aa3be-117">O caminho especificado pela variável de ambiente USERPROFILE.</span><span class="sxs-lookup"><span data-stu-id="aa3be-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="aa3be-118">O diretório do Windows.</span><span class="sxs-lookup"><span data-stu-id="aa3be-118">The Windows directory.</span></span>

- <span data-ttu-id="aa3be-119">Em plataformas não Windows: usa o caminho especificado pela variável de ambiente TMPDIR.</span><span class="sxs-lookup"><span data-stu-id="aa3be-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="aa3be-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa3be-120">EXAMPLES</span></span>

### <span data-ttu-id="aa3be-121">Exemplo 1: criar um arquivo temporário</span><span class="sxs-lookup"><span data-stu-id="aa3be-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="aa3be-122">Esse comando gera um `.tmp` arquivo em sua pasta temporária e, em seguida, armazena uma referência para o arquivo na `$TempFile` variável.</span><span class="sxs-lookup"><span data-stu-id="aa3be-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="aa3be-123">Você pode usar esse arquivo posteriormente em seu script.</span><span class="sxs-lookup"><span data-stu-id="aa3be-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="aa3be-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa3be-124">PARAMETERS</span></span>

### <span data-ttu-id="aa3be-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aa3be-125">-Confirm</span></span>

<span data-ttu-id="aa3be-126">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa3be-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="aa3be-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aa3be-127">-WhatIf</span></span>

<span data-ttu-id="aa3be-128">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="aa3be-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="aa3be-129">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="aa3be-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="aa3be-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa3be-130">CommonParameters</span></span>

<span data-ttu-id="aa3be-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa3be-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa3be-132">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="aa3be-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="aa3be-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa3be-133">INPUTS</span></span>

## <span data-ttu-id="aa3be-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa3be-134">OUTPUTS</span></span>

### <span data-ttu-id="aa3be-135">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="aa3be-135">System.IO.FileInfo</span></span>

<span data-ttu-id="aa3be-136">Esse cmdlet retorna um objeto **FileInfo** que representa o arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="aa3be-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="aa3be-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa3be-137">NOTES</span></span>

## <span data-ttu-id="aa3be-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa3be-138">RELATED LINKS</span></span>
