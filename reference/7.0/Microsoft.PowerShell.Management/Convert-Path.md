---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: fa66e42e182a7dea830ab30373682e4d1e6601e3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192973"
---
# <span data-ttu-id="da95f-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-103">Convert-Path</span></span>

## <span data-ttu-id="da95f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="da95f-104">SYNOPSIS</span></span>
<span data-ttu-id="da95f-105">Converte um caminho de um caminho do PowerShell para um caminho de provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da95f-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="da95f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da95f-106">SYNTAX</span></span>

### <span data-ttu-id="da95f-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="da95f-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="da95f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="da95f-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="da95f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da95f-109">DESCRIPTION</span></span>

<span data-ttu-id="da95f-110">O `Convert-Path` cmdlet converte um caminho de um caminho do PowerShell para um caminho de provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da95f-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="da95f-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="da95f-111">EXAMPLES</span></span>

### <span data-ttu-id="da95f-112">Exemplo 1: converter o diretório de trabalho em um caminho de sistema de arquivos padrão</span><span class="sxs-lookup"><span data-stu-id="da95f-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="da95f-113">Este exemplo converte o diretório de trabalho atual, que é representado por um ponto ( `.` ), em um caminho de sistema de arquivos padrão.</span><span class="sxs-lookup"><span data-stu-id="da95f-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="da95f-114">Exemplo 2: converter um caminho de provedor para um caminho de registro padrão</span><span class="sxs-lookup"><span data-stu-id="da95f-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="da95f-115">Este exemplo converte o caminho do provedor do PowerShell em um caminho de registro padrão.</span><span class="sxs-lookup"><span data-stu-id="da95f-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="da95f-116">Exemplo 3: converter um caminho para uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="da95f-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="da95f-117">Este exemplo converte o caminho para o diretório base do provedor atual, que é o provedor FileSystem, para uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="da95f-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="da95f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da95f-118">PARAMETERS</span></span>

### <span data-ttu-id="da95f-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="da95f-119">-LiteralPath</span></span>

<span data-ttu-id="da95f-120">Especifica, como uma matriz de cadeia de caracteres, o caminho a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="da95f-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="da95f-121">O valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="da95f-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="da95f-122">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="da95f-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="da95f-123">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="da95f-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="da95f-124">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="da95f-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da95f-125">-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-125">-Path</span></span>

<span data-ttu-id="da95f-126">Especifica o caminho do PowerShell a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="da95f-126">Specifies the PowerShell path to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="da95f-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="da95f-127">CommonParameters</span></span>

<span data-ttu-id="da95f-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="da95f-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da95f-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="da95f-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da95f-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="da95f-130">INPUTS</span></span>

### <span data-ttu-id="da95f-131">System.String</span><span class="sxs-lookup"><span data-stu-id="da95f-131">System.String</span></span>

<span data-ttu-id="da95f-132">É possível canalizar um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="da95f-132">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="da95f-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="da95f-133">OUTPUTS</span></span>

### <span data-ttu-id="da95f-134">System.String</span><span class="sxs-lookup"><span data-stu-id="da95f-134">System.String</span></span>

<span data-ttu-id="da95f-135">Esse cmdlet retorna uma cadeia de caracteres que contém o caminho convertido.</span><span class="sxs-lookup"><span data-stu-id="da95f-135">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="da95f-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="da95f-136">NOTES</span></span>

<span data-ttu-id="da95f-137">Os cmdlets que contêm o caminho substantivo manipulam nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar.</span><span class="sxs-lookup"><span data-stu-id="da95f-137">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="da95f-138">Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="da95f-138">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="da95f-139">Use-os como você usaria **dirname** , **Normpath** , **realpath** , **Join** ou outros manipuladores de caminho.</span><span class="sxs-lookup"><span data-stu-id="da95f-139">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="da95f-140">Você pode usar os cmdlets Path com vários provedores, incluindo os provedores de sistema de arquivos, registro e certificado.</span><span class="sxs-lookup"><span data-stu-id="da95f-140">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="da95f-141">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="da95f-141">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="da95f-142">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="da95f-142">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="da95f-143">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="da95f-143">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="da95f-144">`Convert-Path` converte apenas os caminhos existentes.</span><span class="sxs-lookup"><span data-stu-id="da95f-144">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="da95f-145">Ele não pode ser usado para converter um local que ainda não existe.</span><span class="sxs-lookup"><span data-stu-id="da95f-145">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="da95f-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="da95f-146">RELATED LINKS</span></span>

[<span data-ttu-id="da95f-147">Join-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-147">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="da95f-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-148">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="da95f-149">Split-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-149">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="da95f-150">Test-Path</span><span class="sxs-lookup"><span data-stu-id="da95f-150">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="da95f-151">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="da95f-151">Get-PSProvider</span></span>](Get-PSProvider.md)
