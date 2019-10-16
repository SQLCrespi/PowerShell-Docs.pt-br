---
title: Declarando propriedades como parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f71ea35d-cff5-4e44-a5c6-3a747ed4c4d9
caps.latest.revision: 9
ms.openlocfilehash: 6f6640afb15b3608669538f9b5f53d7a8a5c380d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365745"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="7dae3-102">Declarar propriedades como parâmetros</span><span class="sxs-lookup"><span data-stu-id="7dae3-102">Declaring Properties as Parameters</span></span>

<span data-ttu-id="7dae3-103">Este tópico fornece informações básicas que você deve entender antes de declarar os parâmetros de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7dae3-103">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="7dae3-104">Para declarar os parâmetros de um cmdlet dentro de sua classe de cmdlet, defina as propriedades públicas que representam cada parâmetro e, em seguida, adicione um ou mais atributos de parâmetro a cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="7dae3-104">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="7dae3-105">O tempo de execução do Windows PowerShell usa os atributos de parâmetro para identificar a propriedade como um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7dae3-105">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="7dae3-106">A sintaxe básica para declarar o atributo de parâmetro é `[Parameter()]`.</span><span class="sxs-lookup"><span data-stu-id="7dae3-106">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="7dae3-107">Aqui está um exemplo de uma propriedade definida como um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="7dae3-107">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="7dae3-108">Aqui estão algumas coisas para se lembrar dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7dae3-108">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="7dae3-109">Um parâmetro deve ser explicitamente marcado como público.</span><span class="sxs-lookup"><span data-stu-id="7dae3-109">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="7dae3-110">Parâmetros que não estão marcados como padrão público para interno e não serão encontrados pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dae3-110">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="7dae3-111">Os parâmetros devem ser definidos como Microsoft .NET tipos de estrutura para fornecer melhor validação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7dae3-111">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="7dae3-112">Por exemplo, parâmetros que são restritos a um valor de um conjunto de valores devem ser definidos como um tipo de enumeração.</span><span class="sxs-lookup"><span data-stu-id="7dae3-112">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="7dae3-113">Os parâmetros que usam um valor de Uniform Resource Identifier (URI) devem ser do tipo [System. URI](/dotnet/api/System.Uri).</span><span class="sxs-lookup"><span data-stu-id="7dae3-113">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="7dae3-114">Evite parâmetros de cadeia de caracteres básicos para todas as propriedades de texto de forma livre.</span><span class="sxs-lookup"><span data-stu-id="7dae3-114">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="7dae3-115">Você pode adicionar um parâmetro a qualquer número de conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7dae3-115">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="7dae3-116">Para obter mais informações sobre conjuntos de parâmetros, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7dae3-116">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="7dae3-117">O Windows PowerShell também fornece um conjunto de parâmetros comuns que estão disponíveis automaticamente para todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7dae3-117">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="7dae3-118">Para obter mais informações sobre esses parâmetros e seus aliases, consulte [parâmetros comuns do cmdlet](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="7dae3-118">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7dae3-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dae3-119">See Also</span></span>

[<span data-ttu-id="7dae3-120">Parâmetros comuns do cmdlet</span><span class="sxs-lookup"><span data-stu-id="7dae3-120">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="7dae3-121">Tipos de parâmetro de cmdlet</span><span class="sxs-lookup"><span data-stu-id="7dae3-121">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

<span data-ttu-id="7dae3-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="7dae3-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
