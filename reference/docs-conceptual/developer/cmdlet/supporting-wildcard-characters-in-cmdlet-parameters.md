---
title: Suporte a caracteres curinga em parâmetros de cmdlet
ms.date: 08/26/2019
ms.openlocfilehash: 062e3d50dddd0bc84e57f5254a93289acbabe38b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786400"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a>Suporte a caracteres curinga em parâmetros de cmdlet

Muitas vezes, você precisará criar um cmdlet para ser executado em um grupo de recursos em vez de em um único recurso. Por exemplo, um cmdlet pode precisar localizar todos os arquivos em um repositório de dados que tenham o mesmo nome ou extensão. Você deve fornecer suporte para caracteres curinga ao projetar um cmdlet que será executado em um grupo de recursos.

> [!NOTE]
> O uso de caracteres curinga às vezes é chamado de *mascaramento*.

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a>Cmdlets do Windows PowerShell que usam Curingas

 Muitos cmdlets do Windows PowerShell dão suporte a caracteres curinga para seus valores de parâmetro. Por exemplo, quase todos os cmdlets que têm um `Name` `Path` parâmetro ou oferecem suporte a caracteres curinga para esses parâmetros. (Embora a maioria dos cmdlets que têm um `Path` parâmetro também tenha um `LiteralPath` parâmetro que não ofereça suporte a caracteres curinga.) O comando a seguir mostra como um caractere curinga é usado para retornar todos os cmdlets na sessão atual cujo nome contém o verbo Get.

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a>Caracteres curinga com suporte

O Windows PowerShell dá suporte aos seguintes caracteres curinga.

| Curinga |                             Descrição                             |  Exemplo   |     Corresponde a      | Não corresponde a |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | Corresponde a zero ou mais caracteres, começando na posição especificada | `a*`       | A, AG, Apple     |                |
| ?        | Corresponde a qualquer caractere na posição especificada                     | `?n`       | Um, em, em       | executa            |
| [ ]      | Corresponde a um intervalo de caracteres                                       | `[a-l]ook` | livro, Cook, look | Nook, levou     |
| [ ]      | Corresponde aos caracteres especificados                                    | `[bn]ook`  | livro, Nook       | Cook, olhe     |

Ao criar cmdlets que dão suporte a caracteres curinga, permita combinações de caracteres curinga. Por exemplo, o comando a seguir usa o `Get-ChildItem` cmdlet para recuperar todos os arquivos. txt que estão na pasta c:\techdocs e que começam com as letras "a" até "l".

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

O comando anterior usa o curinga de intervalo `[a-l]` para especificar que o nome do arquivo deve começar com os caracteres "a" por meio de "l" e usa o `*` caractere curinga como um espaço reservado para qualquer caractere entre a primeira letra do nome do arquivo e a extensão **. txt** .

O exemplo a seguir usa um padrão de curinga de intervalo que exclui a letra "d", mas inclui todas as outras letras de "a" até "f".

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a>Manipulando caracteres literais em padrões curinga

Se o padrão curinga especificado contiver caracteres literais que não devem ser interpretados como caracteres curinga, use o caractere de acento grave ( `` ` `` ) como um caractere de escape. Quando você especifica caracteres literais int a API do PowerShell, use uma única marca de seleção. Quando você especificar caracteres literais no prompt de comando do PowerShell, use duas marcas de escala.

Por exemplo, o padrão a seguir contém dois colchetes que devem ser usados literalmente.

Quando usado na API do PowerShell, use:

- "John Smith \` [* ']"

Quando usado no prompt de comando do PowerShell:

- "John Smith \` \` [* \` ']"

Esse padrão corresponde a "John Smith [marketing]" ou "John Smith [desenvolvimento]". Por exemplo:

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a>Saída de cmdlet e caracteres curinga

Quando os parâmetros de cmdlet dão suporte a caracteres curinga, a operação geralmente gera uma saída de matriz.
Ocasionalmente, não faz sentido oferecer suporte a uma saída de matriz porque o usuário pode usar apenas um único item. Por exemplo, o `Set-Location` cmdlet não oferece suporte à saída de matriz porque o usuário define apenas um único local. Nessa instância, o cmdlet ainda dá suporte a caracteres curinga, mas força a resolução para um único local.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Classe WildcardPattern](/dotnet/api/system.management.automation.wildcardpattern)
