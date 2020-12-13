---
ms.date: 09/13/2016
ms.topic: reference
title: Como declarar conjuntos de parâmetros
description: Como declarar conjuntos de parâmetros
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667055"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="5a5a3-103">Como declarar conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="5a5a3-103">How to Declare Parameter Sets</span></span>

<span data-ttu-id="5a5a3-104">Este exemplo mostra como definir dois conjuntos de parâmetros quando você declara os parâmetros para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-104">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="5a5a3-105">Cada conjunto de parâmetros tem um parâmetro exclusivo e um parâmetro compartilhado que é usado por ambos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-105">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="5a5a3-106">Para obter mais informações sobre conjuntos de parâmetros, incluindo como especificar o conjunto de parâmetros padrão, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5a5a3-106">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a5a3-107">Sempre que possível, defina o parâmetro exclusivo de um conjunto de parâmetros como um parâmetro necessário.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-107">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="5a5a3-108">No entanto, se você quiser que o cmdlet seja executado sem especificar parâmetros, o parâmetro exclusivo poderá ser um parâmetro opcional.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-108">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="5a5a3-109">Por exemplo, o parâmetro exclusivo do `Get-Command` cmdlet é opcional.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-109">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="5a5a3-110">Como definir dois conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="5a5a3-110">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="5a5a3-111">Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do primeiro conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. <span data-ttu-id="5a5a3-112">Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do segundo conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-112">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. <span data-ttu-id="5a5a3-113">Para o parâmetro que pertence a ambos os conjuntos de parâmetros, adicione um atributo de parâmetro para cada conjunto de parâmetros e, em seguida, adicione a `ParameterSet` palavra-chave a cada conjunto.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-113">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="5a5a3-114">Em cada atributo de parâmetro, você pode especificar como esse parâmetro é definido.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-114">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="5a5a3-115">Um parâmetro pode ser opcional em um conjunto e obrigatório em outro.</span><span class="sxs-lookup"><span data-stu-id="5a5a3-115">A parameter can be optional in one set and mandatory in another.</span></span>

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a><span data-ttu-id="5a5a3-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a5a3-116">See Also</span></span>

[<span data-ttu-id="5a5a3-117">Conjuntos de parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="5a5a3-117">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

<span data-ttu-id="5a5a3-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="5a5a3-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
