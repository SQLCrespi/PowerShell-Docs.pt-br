---
title: Como declarar conjuntos de parâmetros | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e6d06a9a78356693fe7a338dc5c9207044b23441
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784156"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="96789-102">Como declarar conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="96789-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="96789-103">Este exemplo mostra como definir dois conjuntos de parâmetros quando você declara os parâmetros para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96789-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="96789-104">Cada conjunto de parâmetros tem um parâmetro exclusivo e um parâmetro compartilhado que é usado por ambos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="96789-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="96789-105">Para obter mais informações sobre conjuntos de parâmetros, incluindo como especificar o conjunto de parâmetros padrão, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="96789-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96789-106">Sempre que possível, defina o parâmetro exclusivo de um conjunto de parâmetros como um parâmetro necessário.</span><span class="sxs-lookup"><span data-stu-id="96789-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="96789-107">No entanto, se você quiser que o cmdlet seja executado sem especificar parâmetros, o parâmetro exclusivo poderá ser um parâmetro opcional.</span><span class="sxs-lookup"><span data-stu-id="96789-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="96789-108">Por exemplo, o parâmetro exclusivo do `Get-Command` cmdlet é opcional.</span><span class="sxs-lookup"><span data-stu-id="96789-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="96789-109">Como definir dois conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="96789-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="96789-110">Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do primeiro conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="96789-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="96789-111">Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do segundo conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="96789-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="96789-112">Para o parâmetro que pertence a ambos os conjuntos de parâmetros, adicione um atributo de parâmetro para cada conjunto de parâmetros e, em seguida, adicione a `ParameterSet` palavra-chave a cada conjunto.</span><span class="sxs-lookup"><span data-stu-id="96789-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="96789-113">Em cada atributo de parâmetro, você pode especificar como esse parâmetro é definido.</span><span class="sxs-lookup"><span data-stu-id="96789-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="96789-114">Um parâmetro pode ser opcional em um conjunto e obrigatório em outro.</span><span class="sxs-lookup"><span data-stu-id="96789-114">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="96789-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96789-115">See Also</span></span>

[<span data-ttu-id="96789-116">Conjuntos de parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="96789-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="96789-117">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96789-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
