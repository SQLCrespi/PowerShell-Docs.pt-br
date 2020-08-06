---
title: Aliases de cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fed4055f09e01c5f3fa87584d48551918606f4eb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784530"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="c4a4a-102">Aliases de cmdlet</span><span class="sxs-lookup"><span data-stu-id="c4a4a-102">Cmdlet Aliases</span></span>

<span data-ttu-id="c4a4a-103">Você pode usar aliases de cmdlet para melhorar a experiência do usuário do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="c4a4a-104">Você pode adicionar aliases a cmdlets usados com frequência para reduzir a digitação e facilitar a conclusão das tarefas rapidamente.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="c4a4a-105">Você pode incluir aliases internos em seus cmdlets ou os usuários podem definir seus próprios aliases personalizados.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="c4a4a-106">Por exemplo, o cmdlet [Get-Command](/powershell/module/microsoft.powershell.core/get-command) tem um `gcm` alias interno.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="c4a4a-107">Você também pode usar aliases para adicionar nomes de comando de outros idiomas para que os usuários não precisem aprender novos comandos.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="c4a4a-108">Diretrizes de alias</span><span class="sxs-lookup"><span data-stu-id="c4a4a-108">Alias Guidelines</span></span>

<span data-ttu-id="c4a4a-109">Siga estas diretrizes ao criar aliases internos para seus cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c4a4a-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="c4a4a-110">Antes de atribuir aliases, inicie o Windows PowerShell e execute o cmdlet [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) para ver os aliases que já foram usados.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="c4a4a-111">Inclua um prefixo de alias que referencie o verbo do nome do cmdlet e um sufixo de alias que referencie o substantivo do nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="c4a4a-112">Por exemplo, o alias para o `Import-Module` cmdlet é "ipmo".</span><span class="sxs-lookup"><span data-stu-id="c4a4a-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="c4a4a-113">Para obter uma lista de todos os verbos e seus aliases, consulte [verbos de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="c4a4a-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="c4a4a-114">Para os cmdlets que têm o mesmo verbo, inclua o mesmo prefixo de alias.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="c4a4a-115">Por exemplo, os aliases para todos os cmdlets do Windows PowerShell que têm o verbo "Get" em seu nome usam o prefixo "g".</span><span class="sxs-lookup"><span data-stu-id="c4a4a-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="c4a4a-116">Para os cmdlets que têm o mesmo substantivo, inclua o mesmo sufixo de alias.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="c4a4a-117">Por exemplo, os aliases para todos os cmdlets do Windows PowerShell que têm o substantivo "Session" em seu nome usam o sufixo "SN".</span><span class="sxs-lookup"><span data-stu-id="c4a4a-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="c4a4a-118">Para cmdlets equivalentes a comandos em outros idiomas, use o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="c4a4a-119">Em geral, torne os aliases o mais curto possível.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="c4a4a-120">Verifique se o alias tem pelo menos um caractere distinto para o verbo e um caractere distinto para o substantivo.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="c4a4a-121">Adicione mais caracteres conforme necessário para tornar o alias exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c4a4a-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4a4a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4a4a-122">See Also</span></span>

[<span data-ttu-id="c4a4a-123">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4a4a-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
