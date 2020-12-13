---
ms.date: 08/26/2019
ms.topic: reference
title: Suporte a caracteres curinga em parâmetros de cmdlet
description: Suporte a caracteres curinga em parâmetros de cmdlet
ms.openlocfilehash: 06693c62cd2613050bdeb9d6b12ad6e9597a9894
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646392"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="3d50a-103">Suporte a caracteres curinga em parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="3d50a-103">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="3d50a-104">Muitas vezes, você precisará criar um cmdlet para ser executado em um grupo de recursos em vez de em um único recurso.</span><span class="sxs-lookup"><span data-stu-id="3d50a-104">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="3d50a-105">Por exemplo, um cmdlet pode precisar localizar todos os arquivos em um repositório de dados que tenham o mesmo nome ou extensão.</span><span class="sxs-lookup"><span data-stu-id="3d50a-105">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="3d50a-106">Você deve fornecer suporte para caracteres curinga ao projetar um cmdlet que será executado em um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="3d50a-106">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="3d50a-107">O uso de caracteres curinga às vezes é chamado de *mascaramento*.</span><span class="sxs-lookup"><span data-stu-id="3d50a-107">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="3d50a-108">Cmdlets do Windows PowerShell que usam Curingas</span><span class="sxs-lookup"><span data-stu-id="3d50a-108">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="3d50a-109">Muitos cmdlets do Windows PowerShell dão suporte a caracteres curinga para seus valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3d50a-109">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="3d50a-110">Por exemplo, quase todos os cmdlets que têm um `Name` `Path` parâmetro ou oferecem suporte a caracteres curinga para esses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3d50a-110">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="3d50a-111">(Embora a maioria dos cmdlets que têm um `Path` parâmetro também tenha um `LiteralPath` parâmetro que não ofereça suporte a caracteres curinga.) O comando a seguir mostra como um caractere curinga é usado para retornar todos os cmdlets na sessão atual cujo nome contém o verbo Get.</span><span class="sxs-lookup"><span data-stu-id="3d50a-111">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="3d50a-112">Caracteres curinga com suporte</span><span class="sxs-lookup"><span data-stu-id="3d50a-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="3d50a-113">O Windows PowerShell dá suporte aos seguintes caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3d50a-113">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="3d50a-114">Curinga</span><span class="sxs-lookup"><span data-stu-id="3d50a-114">Wildcard</span></span> |                             <span data-ttu-id="3d50a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d50a-115">Description</span></span>                             |  <span data-ttu-id="3d50a-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3d50a-116">Example</span></span>   |     <span data-ttu-id="3d50a-117">Corresponde a</span><span class="sxs-lookup"><span data-stu-id="3d50a-117">Matches</span></span>      | <span data-ttu-id="3d50a-118">Não corresponde a</span><span class="sxs-lookup"><span data-stu-id="3d50a-118">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="3d50a-119">Corresponde a zero ou mais caracteres, começando na posição especificada</span><span class="sxs-lookup"><span data-stu-id="3d50a-119">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="3d50a-120">A, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="3d50a-120">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="3d50a-121">?</span><span class="sxs-lookup"><span data-stu-id="3d50a-121">?</span></span>        | <span data-ttu-id="3d50a-122">Corresponde a qualquer caractere na posição especificada</span><span class="sxs-lookup"><span data-stu-id="3d50a-122">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="3d50a-123">Um, em, em</span><span class="sxs-lookup"><span data-stu-id="3d50a-123">An, in, on</span></span>       | <span data-ttu-id="3d50a-124">executa</span><span class="sxs-lookup"><span data-stu-id="3d50a-124">ran</span></span>            |
| <span data-ttu-id="3d50a-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="3d50a-125">[ ]</span></span>      | <span data-ttu-id="3d50a-126">Corresponde a um intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="3d50a-126">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="3d50a-127">livro, Cook, look</span><span class="sxs-lookup"><span data-stu-id="3d50a-127">book, cook, look</span></span> | <span data-ttu-id="3d50a-128">Nook, levou</span><span class="sxs-lookup"><span data-stu-id="3d50a-128">nook, took</span></span>     |
| <span data-ttu-id="3d50a-129">[ ]</span><span class="sxs-lookup"><span data-stu-id="3d50a-129">[ ]</span></span>      | <span data-ttu-id="3d50a-130">Corresponde aos caracteres especificados</span><span class="sxs-lookup"><span data-stu-id="3d50a-130">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="3d50a-131">livro, Nook</span><span class="sxs-lookup"><span data-stu-id="3d50a-131">book, nook</span></span>       | <span data-ttu-id="3d50a-132">Cook, olhe</span><span class="sxs-lookup"><span data-stu-id="3d50a-132">cook, look</span></span>     |

<span data-ttu-id="3d50a-133">Ao criar cmdlets que dão suporte a caracteres curinga, permita combinações de caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3d50a-133">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="3d50a-134">Por exemplo, o comando a seguir usa o `Get-ChildItem` cmdlet para recuperar todos os arquivos. txt que estão na pasta c:\techdocs e que começam com as letras "a" até "l".</span><span class="sxs-lookup"><span data-stu-id="3d50a-134">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="3d50a-135">O comando anterior usa o curinga de intervalo `[a-l]` para especificar que o nome do arquivo deve começar com os caracteres "a" por meio de "l" e usa o `*` caractere curinga como um espaço reservado para qualquer caractere entre a primeira letra do nome do arquivo e a extensão **. txt** .</span><span class="sxs-lookup"><span data-stu-id="3d50a-135">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="3d50a-136">O exemplo a seguir usa um padrão de curinga de intervalo que exclui a letra "d", mas inclui todas as outras letras de "a" até "f".</span><span class="sxs-lookup"><span data-stu-id="3d50a-136">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="3d50a-137">Manipulando caracteres literais em padrões curinga</span><span class="sxs-lookup"><span data-stu-id="3d50a-137">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="3d50a-138">Se o padrão curinga especificado contiver caracteres literais que não devem ser interpretados como caracteres curinga, use o caractere de acento grave ( `` ` `` ) como um caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="3d50a-138">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="3d50a-139">Quando você especifica caracteres literais int a API do PowerShell, use uma única marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="3d50a-139">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="3d50a-140">Quando você especificar caracteres literais no prompt de comando do PowerShell, use duas marcas de escala.</span><span class="sxs-lookup"><span data-stu-id="3d50a-140">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="3d50a-141">Por exemplo, o padrão a seguir contém dois colchetes que devem ser usados literalmente.</span><span class="sxs-lookup"><span data-stu-id="3d50a-141">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="3d50a-142">Quando usado na API do PowerShell, use:</span><span class="sxs-lookup"><span data-stu-id="3d50a-142">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="3d50a-143">"John Smith \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="3d50a-143">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="3d50a-144">Quando usado no prompt de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d50a-144">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="3d50a-145">"John Smith \` \` [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="3d50a-145">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="3d50a-146">Esse padrão corresponde a "John Smith [marketing]" ou "John Smith [desenvolvimento]".</span><span class="sxs-lookup"><span data-stu-id="3d50a-146">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="3d50a-147">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d50a-147">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="3d50a-148">Saída de cmdlet e caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="3d50a-148">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="3d50a-149">Quando os parâmetros de cmdlet dão suporte a caracteres curinga, a operação geralmente gera uma saída de matriz.</span><span class="sxs-lookup"><span data-stu-id="3d50a-149">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="3d50a-150">Ocasionalmente, não faz sentido oferecer suporte a uma saída de matriz porque o usuário pode usar apenas um único item.</span><span class="sxs-lookup"><span data-stu-id="3d50a-150">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="3d50a-151">Por exemplo, o `Set-Location` cmdlet não oferece suporte à saída de matriz porque o usuário define apenas um único local.</span><span class="sxs-lookup"><span data-stu-id="3d50a-151">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="3d50a-152">Nessa instância, o cmdlet ainda dá suporte a caracteres curinga, mas força a resolução para um único local.</span><span class="sxs-lookup"><span data-stu-id="3d50a-152">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d50a-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d50a-153">See Also</span></span>

[<span data-ttu-id="3d50a-154">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d50a-154">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="3d50a-155">Classe WildcardPattern</span><span class="sxs-lookup"><span data-stu-id="3d50a-155">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
