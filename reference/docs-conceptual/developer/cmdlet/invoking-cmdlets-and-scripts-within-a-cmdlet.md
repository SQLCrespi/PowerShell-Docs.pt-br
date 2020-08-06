---
title: Invocando cmdlets e scripts dentro de um cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786570"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="7f97b-102">Invocar cmdlets e scripts dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f97b-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="7f97b-103">Um cmdlet pode invocar outros cmdlets e scripts de dentro do método de processamento de entrada do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f97b-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="7f97b-104">Isso permite que você adicione a funcionalidade de cmdlets e scripts existentes ao seu cmdlet sem precisar reescrever o código.</span><span class="sxs-lookup"><span data-stu-id="7f97b-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="7f97b-105">O método Invoke</span><span class="sxs-lookup"><span data-stu-id="7f97b-105">The Invoke Method</span></span>

<span data-ttu-id="7f97b-106">Todos os cmdlets podem invocar um cmdlet existente chamando o método [System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) de dentro de um método de processamento de entrada, como [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), que é substituído pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f97b-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="7f97b-107">No entanto, você pode invocar somente os cmdlets que derivam diretamente da classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="7f97b-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="7f97b-108">Não é possível invocar um cmdlet derivado da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="7f97b-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="7f97b-109">O método [System. Management. Automation. cmdlet. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) tem as variantes a seguir.</span><span class="sxs-lookup"><span data-stu-id="7f97b-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="7f97b-110">[System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) esta variante invoca o objeto cmdlet e retorna uma coleção de objetos de tipo "T".</span><span class="sxs-lookup"><span data-stu-id="7f97b-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="7f97b-111">[System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) esta variante invoca o objeto cmdlet e retorna um emumerator com rigidez de tipos.</span><span class="sxs-lookup"><span data-stu-id="7f97b-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="7f97b-112">Essa variante permite que o usuário use os objetos na coleção para executar operações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7f97b-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="7f97b-113">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7f97b-113">Examples</span></span>

|<span data-ttu-id="7f97b-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7f97b-114">Example</span></span>|<span data-ttu-id="7f97b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="7f97b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f97b-116">Invocando cmdlets dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f97b-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="7f97b-117">Este exemplo mostra como invocar um cmdlet de dentro de outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f97b-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="7f97b-118">Invocando scripts dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f97b-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="7f97b-119">Este exemplo mostra como invocar um script que é fornecido para o cmdlet de dentro de outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f97b-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7f97b-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f97b-120">See Also</span></span>

[<span data-ttu-id="7f97b-121">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f97b-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
