---
description: A `enum` instrução é usada para declarar uma enumeração. Uma enumeração é um tipo distinto que consiste em um conjunto de rótulos nomeados chamado lista de enumeradores.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 0b1959ba009119769535c3d39231ff8dab9dc5de
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196215"
---
# <a name="about-enum"></a><span data-ttu-id="7ffe4-105">Sobre enum</span><span class="sxs-lookup"><span data-stu-id="7ffe4-105">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="7ffe4-106">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="7ffe4-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7ffe4-107">A `enum` instrução é usada para declarar uma enumeração.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-107">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="7ffe4-108">Uma enumeração é um tipo distinto que consiste em um conjunto de rótulos nomeados chamado lista de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-108">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="7ffe4-109">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="7ffe4-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="7ffe4-110">A `enum` instrução permite que você crie um conjunto de rótulos fortemente tipado.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-110">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="7ffe4-111">Essa enumeração pode ser usada no código sem precisar analisar ou verificar erros de ortografia.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-111">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="7ffe4-112">As enumerações são representadas internamente como inteiros com um valor inicial igual a zero.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-112">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="7ffe4-113">O valor zero é atribuído ao primeiro rótulo da lista.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-113">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="7ffe4-114">Os rótulos restantes são atribuídos com números consecutivos.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-114">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="7ffe4-115">Na definição, os rótulos podem receber qualquer valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-115">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="7ffe4-116">Rótulos sem valor atribuído usam o próximo valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-116">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="7ffe4-117">Sintaxe (básica)</span><span class="sxs-lookup"><span data-stu-id="7ffe4-117">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="7ffe4-118">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="7ffe4-118">Usage example</span></span>

<span data-ttu-id="7ffe4-119">O exemplo a seguir mostra uma enumeração de objetos que podem ser vistos como arquivos de mídia.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-119">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="7ffe4-120">A definição atribui valores explícitos aos valores subjacentes de `music` , `picture` , `video` .</span><span class="sxs-lookup"><span data-stu-id="7ffe4-120">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="7ffe4-121">Os rótulos imediatamente após uma atribuição explícita obtêm o próximo valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-121">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="7ffe4-122">Os sinônimos podem ser criados atribuindo o mesmo valor a outro rótulo; consulte os valores construídos para: `ogg` , `oga` , `mogg` , ou `jpg` , `jpeg` , ou `mpg` , `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="7ffe4-122">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

```powershell
enum MediaTypes {
    unknown
    music = 10
    mp3
    aac
    ogg = 15
    oga = 15
    mogg = 15
    picture = 20
    jpg
    jpeg = 21
    png
    video = 40
    mpg
    mpeg = 41
    avi
    m4v
}
```

<span data-ttu-id="7ffe4-123">O `GetEnumNames()` método retorna a lista de rótulos para a enumeração.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-123">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumNames()
unknown
music
mp3
aac
ogg
oga
mogg
picture
jpg
jpeg
png
video
mpg
mpeg
avi
m4v
```

<span data-ttu-id="7ffe4-124">O `GetEnumValues()` método retorna a lista de valores para a enumeração.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-124">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumValues()
unknown
music
mp3
aac
oga
oga
oga
picture
jpeg
jpeg
png
video
mpeg
mpeg
avi
m4v
```

<span data-ttu-id="7ffe4-125">**Observação** : GetEnumNames () e GetEnumValues () parecem retornar os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-125">**Note** : GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="7ffe4-126">No entanto, internamente, o PowerShell está alterando valores em rótulos.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-126">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="7ffe4-127">Leia a lista com cuidado e você observará que `oga` e `mogg` são mencionados nos resultados de ' Get names ', mas não na saída similar ' Get Values ' para `jpg` , `jpeg` e `mpg` , `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="7ffe4-127">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

```powershell
[MediaTypes].GetEnumName(15)
oga

[MediaTypes].GetEnumNames() | ForEach-Object {
  "{0,-10} {1}" -f $_,[int]([MediaTypes]::$_)
}
unknown    0
music      10
mp3        11
aac        12
ogg        15
oga        15
mogg       15
picture    20
jpg        21
jpeg       21
png        22
video      40
mpg        41
mpeg       41
avi        42
m4v        43
```

## <a name="enumerations-as-flags"></a><span data-ttu-id="7ffe4-128">Enumerações como sinalizadores</span><span class="sxs-lookup"><span data-stu-id="7ffe4-128">Enumerations as flags</span></span>

<span data-ttu-id="7ffe4-129">As enumerações podem ser definidas como uma coleção de sinalizadores de bit.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-129">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="7ffe4-130">Onde, em qualquer momento determinado, a enumeração representa um ou mais desses sinalizadores ativados.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-130">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="7ffe4-131">Para enumerações como sinalizadores funcionarem corretamente, cada rótulo deve ter uma potência de dois valores.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-131">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="7ffe4-132">Sintaxe (flags)</span><span class="sxs-lookup"><span data-stu-id="7ffe4-132">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="7ffe4-133">Exemplo de uso de sinalizadores</span><span class="sxs-lookup"><span data-stu-id="7ffe4-133">Flags usage example</span></span>

<span data-ttu-id="7ffe4-134">No exemplo a seguir, a enumeração *FileAttributes* é criada.</span><span class="sxs-lookup"><span data-stu-id="7ffe4-134">In the following example the *FileAttributes* enumeration is created.</span></span>

```powershell
[Flags()] enum FileAttributes {
    Archive = 1
    Compressed = 2
    Device = 4
    Directory = 8
    Encrypted = 16
    Hidden = 32
}

[FileAttributes]$file1 = [FileAttributes]::Archive
[FileAttributes]$file1 +=[FileAttributes]::Compressed
[FileAttributes]$file1 +=  [FileAttributes]::Device
"file1 attributes are: $file1"

[FileAttributes]$file2 = [FileAttributes]28 ## => 16 + 8 + 4
"file2 attributes are: $file2"
```

```output
file1 attributes are: Archive, Compressed, Device
file2 attributes are: Device, Directory, Encrypted
```

<span data-ttu-id="7ffe4-135">Para testar se um específico está definido, você pode usar o operador de comparação binária `-band` .</span><span class="sxs-lookup"><span data-stu-id="7ffe4-135">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="7ffe4-136">Neste exemplo, testamos o **dispositivo** e os atributos de **arquivo** no valor de `$file2` .</span><span class="sxs-lookup"><span data-stu-id="7ffe4-136">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```
