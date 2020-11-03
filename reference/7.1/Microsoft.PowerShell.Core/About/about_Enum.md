---
description: A `enum` instrução é usada para declarar uma enumeração. Uma enumeração é um tipo distinto que consiste em um conjunto de rótulos nomeados chamado lista de enumeradores.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 1ffb18ab98fbd40b407abfe32c71027315b69621
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195860"
---
# <a name="about-enum"></a>Sobre enum

## <a name="short-description"></a>DESCRIÇÃO BREVE
A `enum` instrução é usada para declarar uma enumeração. Uma enumeração é um tipo distinto que consiste em um conjunto de rótulos nomeados chamado lista de enumeradores.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A `enum` instrução permite que você crie um conjunto de rótulos fortemente tipado. Essa enumeração pode ser usada no código sem precisar analisar ou verificar erros de ortografia.

As enumerações são representadas internamente como inteiros com um valor inicial igual a zero. O valor zero é atribuído ao primeiro rótulo da lista. Os rótulos restantes são atribuídos com números consecutivos.

Na definição, os rótulos podem receber qualquer valor inteiro. Rótulos sem valor atribuído usam o próximo valor inteiro.

## <a name="syntax-basic"></a>Sintaxe (básica)

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a>Exemplo de uso

O exemplo a seguir mostra uma enumeração de objetos que podem ser vistos como arquivos de mídia. A definição atribui valores explícitos aos valores subjacentes de `music` , `picture` , `video` . Os rótulos imediatamente após uma atribuição explícita obtêm o próximo valor inteiro. Os sinônimos podem ser criados atribuindo o mesmo valor a outro rótulo; consulte os valores construídos para: `ogg` , `oga` , `mogg` , ou `jpg` , `jpeg` , ou `mpg` , `mpeg` .

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

O `GetEnumNames()` método retorna a lista de rótulos para a enumeração.

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

O `GetEnumValues()` método retorna a lista de valores para a enumeração.

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

**Observação** : GetEnumNames () e GetEnumValues () parecem retornar os mesmos resultados.
No entanto, internamente, o PowerShell está alterando valores em rótulos. Leia a lista com cuidado e você observará que `oga` e `mogg` são mencionados nos resultados de ' Get names ', mas não na saída similar ' Get Values ' para `jpg` , `jpeg` e `mpg` , `mpeg` .

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

## <a name="enumerations-as-flags"></a>Enumerações como sinalizadores

As enumerações podem ser definidas como uma coleção de sinalizadores de bit.
Onde, em qualquer momento determinado, a enumeração representa um ou mais desses sinalizadores ativados.

Para enumerações como sinalizadores funcionarem corretamente, cada rótulo deve ter uma potência de dois valores.

## <a name="syntax-flags"></a>Sintaxe (flags)

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a>Exemplo de uso de sinalizadores

No exemplo a seguir, a enumeração *FileAttributes* é criada.

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

Para testar se um específico está definido, você pode usar o operador de comparação binária `-band` . Neste exemplo, testamos o **dispositivo** e os atributos de **arquivo** no valor de `$file2` .

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```

