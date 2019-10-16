---
title: Aliases de parâmetro | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369585"
---
# <a name="parameter-aliases"></a><span data-ttu-id="54ff6-102">Aliases de parâmetro</span><span class="sxs-lookup"><span data-stu-id="54ff6-102">Parameter Aliases</span></span>

<span data-ttu-id="54ff6-103">Parâmetros de cmdlet também podem ter aliases.</span><span class="sxs-lookup"><span data-stu-id="54ff6-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="54ff6-104">Você pode usar os aliases em vez dos nomes de parâmetro ao digitar ou especificar o parâmetro em um comando.</span><span class="sxs-lookup"><span data-stu-id="54ff6-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="54ff6-105">Benefícios do uso de aliases</span><span class="sxs-lookup"><span data-stu-id="54ff6-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="54ff6-106">A adição de aliases a parâmetros oferece os seguintes benefícios.</span><span class="sxs-lookup"><span data-stu-id="54ff6-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="54ff6-107">Você pode fornecer um atalho para que o usuário não precise usar o nome completo do parâmetro quando o cmdlet for chamado.</span><span class="sxs-lookup"><span data-stu-id="54ff6-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="54ff6-108">Por exemplo, você pode usar o alias "CN" em vez do nome do parâmetro "computername".</span><span class="sxs-lookup"><span data-stu-id="54ff6-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="54ff6-109">Você pode definir vários aliases se desejar fornecer nomes diferentes para o mesmo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54ff6-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="54ff6-110">Talvez você queira definir vários aliases se precisar trabalhar com vários grupos de usuários que se referem aos mesmos dados de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="54ff6-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="54ff6-111">Você pode fornecer compatibilidade com versões anteriores para scripts existentes se o nome de um parâmetro for alterado.</span><span class="sxs-lookup"><span data-stu-id="54ff6-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="54ff6-112">Usando o atributo alias junto com o atributo ValueFromPipelineByName, você pode definir um parâmetro que permite que o cmdlet se vincule a diferentes tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="54ff6-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="54ff6-113">Por exemplo, digamos que você tivesse dois objetos de tipos diferentes e o primeiro objeto tinha uma propriedade de gravador e o segundo objeto tinha uma propriedade de editor.</span><span class="sxs-lookup"><span data-stu-id="54ff6-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="54ff6-114">Se o cmdlet tivesse um parâmetro que tinha aliases de gravador e editor e o cmdlet aceitou a entrada de pipeline com base em nomes de propriedade, seu cmdlet poderá se associar a ambos os objetos usando os dois aliases de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54ff6-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="54ff6-115">Para obter mais informações sobre aliases que podem ser usados com parâmetros específicos, consulte [nomes de parâmetro comuns](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="54ff6-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="54ff6-116">Definindo aliases de parâmetro</span><span class="sxs-lookup"><span data-stu-id="54ff6-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="54ff6-117">Para definir um alias para um parâmetro, declare o atributo Alias, conforme mostrado na declaração de parâmetro a seguir.</span><span class="sxs-lookup"><span data-stu-id="54ff6-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="54ff6-118">Neste exemplo, vários aliases são definidos para o mesmo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54ff6-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="54ff6-119">(Para obter mais informações, consulte[How to declare cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span><span class="sxs-lookup"><span data-stu-id="54ff6-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

```csharp
[Alias("UN","Writer","Editor")]
[Parameter()]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="see-also"></a><span data-ttu-id="54ff6-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54ff6-120">See Also</span></span>

[<span data-ttu-id="54ff6-121">Nomes de parâmetro comuns</span><span class="sxs-lookup"><span data-stu-id="54ff6-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="54ff6-122">Como declarar parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="54ff6-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

<span data-ttu-id="54ff6-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="54ff6-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
