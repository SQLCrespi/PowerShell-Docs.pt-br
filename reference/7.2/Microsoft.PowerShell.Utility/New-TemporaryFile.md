---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 1c66cd3b1cc2fccc58cd75c367b41c445deb1e72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598412"
---
# <span data-ttu-id="200e3-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="200e3-102">New-TemporaryFile</span></span>

## <span data-ttu-id="200e3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="200e3-103">SYNOPSIS</span></span>
<span data-ttu-id="200e3-104">Cria um arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="200e3-104">Creates a temporary file.</span></span>

## <span data-ttu-id="200e3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="200e3-105">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="200e3-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="200e3-106">DESCRIPTION</span></span>

<span data-ttu-id="200e3-107">Esse cmdlet cria arquivos temporários que você pode usar em scripts.</span><span class="sxs-lookup"><span data-stu-id="200e3-107">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="200e3-108">O `New-TemporaryFile` cmdlet cria um arquivo vazio que tem a `.tmp` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="200e3-108">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="200e3-109">Esse cmdlet nomeia o arquivo `tmp<NNNN>.tmp` , em que `<NNNN>` é um número hexadecimal aleatório.</span><span class="sxs-lookup"><span data-stu-id="200e3-109">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="200e3-110">O cmdlet cria o arquivo em sua pasta **temporária** .</span><span class="sxs-lookup"><span data-stu-id="200e3-110">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="200e3-111">Esse cmdlet usa o método [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) para localizar a pasta **Temp** .</span><span class="sxs-lookup"><span data-stu-id="200e3-111">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="200e3-112">Esse método verifica a existência de variáveis de ambiente na seguinte ordem e usa o primeiro caminho encontrado:</span><span class="sxs-lookup"><span data-stu-id="200e3-112">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="200e3-113">Em plataformas Windows:</span><span class="sxs-lookup"><span data-stu-id="200e3-113">On Windows platforms:</span></span>

  1. <span data-ttu-id="200e3-114">O caminho especificado pela variável de ambiente TMP.</span><span class="sxs-lookup"><span data-stu-id="200e3-114">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="200e3-115">O caminho especificado pela variável de ambiente TEMP.</span><span class="sxs-lookup"><span data-stu-id="200e3-115">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="200e3-116">O caminho especificado pela variável de ambiente USERPROFILE.</span><span class="sxs-lookup"><span data-stu-id="200e3-116">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="200e3-117">O diretório do Windows.</span><span class="sxs-lookup"><span data-stu-id="200e3-117">The Windows directory.</span></span>

- <span data-ttu-id="200e3-118">Em plataformas não Windows: usa o caminho especificado pela variável de ambiente TMPDIR.</span><span class="sxs-lookup"><span data-stu-id="200e3-118">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="200e3-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="200e3-119">EXAMPLES</span></span>

### <span data-ttu-id="200e3-120">Exemplo 1: criar um arquivo temporário</span><span class="sxs-lookup"><span data-stu-id="200e3-120">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="200e3-121">Esse comando gera um `.tmp` arquivo em sua pasta temporária e, em seguida, armazena uma referência para o arquivo na `$TempFile` variável.</span><span class="sxs-lookup"><span data-stu-id="200e3-121">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="200e3-122">Você pode usar esse arquivo posteriormente em seu script.</span><span class="sxs-lookup"><span data-stu-id="200e3-122">You can use this file later in your script.</span></span>

## <span data-ttu-id="200e3-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="200e3-123">PARAMETERS</span></span>

### <span data-ttu-id="200e3-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="200e3-124">-Confirm</span></span>

<span data-ttu-id="200e3-125">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="200e3-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="200e3-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="200e3-126">-WhatIf</span></span>

<span data-ttu-id="200e3-127">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="200e3-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="200e3-128">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="200e3-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="200e3-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="200e3-129">CommonParameters</span></span>

<span data-ttu-id="200e3-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="200e3-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="200e3-131">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="200e3-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="200e3-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="200e3-132">INPUTS</span></span>

## <span data-ttu-id="200e3-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="200e3-133">OUTPUTS</span></span>

### <span data-ttu-id="200e3-134">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="200e3-134">System.IO.FileInfo</span></span>

<span data-ttu-id="200e3-135">Esse cmdlet retorna um objeto **FileInfo** que representa o arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="200e3-135">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="200e3-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="200e3-136">NOTES</span></span>

## <span data-ttu-id="200e3-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="200e3-137">RELATED LINKS</span></span>

