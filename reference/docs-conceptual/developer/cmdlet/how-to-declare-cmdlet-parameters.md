---
title: Como declarar parâmetros de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c0509cc-5a50-49ad-a74f-5527023d0270
caps.latest.revision: 10
ms.openlocfilehash: 80e3e27bcf72b078c192525a843a3b3afb306529
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365675"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="7bad6-102">Como declarar parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="7bad6-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="7bad6-103">Esses exemplos mostram como declarar parâmetros nomeados, posicionais, obrigatórios, opcionais e de comutação.</span><span class="sxs-lookup"><span data-stu-id="7bad6-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="7bad6-104">Esses exemplos também mostram como definir um alias de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7bad6-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="7bad6-105">Como declarar um parâmetro nomeado</span><span class="sxs-lookup"><span data-stu-id="7bad6-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="7bad6-106">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bad6-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="7bad6-107">Ao adicionar o atributo de parâmetro, omita a palavra-chave `Position` do atributo.</span><span class="sxs-lookup"><span data-stu-id="7bad6-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="7bad6-108">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7bad6-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="7bad6-109">Como declarar um parâmetro posicional</span><span class="sxs-lookup"><span data-stu-id="7bad6-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="7bad6-110">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bad6-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="7bad6-111">Ao adicionar o atributo de parâmetro, defina a palavra-chave `Position` como a posição do argumento.</span><span class="sxs-lookup"><span data-stu-id="7bad6-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="7bad6-112">Um valor de 0 indica a primeira posição.</span><span class="sxs-lookup"><span data-stu-id="7bad6-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="7bad6-113">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7bad6-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="7bad6-114">Como declarar um parâmetro obrigatório</span><span class="sxs-lookup"><span data-stu-id="7bad6-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="7bad6-115">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bad6-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="7bad6-116">Ao adicionar o atributo de parâmetro, defina a palavra-chave `Mandatory` como `true`.</span><span class="sxs-lookup"><span data-stu-id="7bad6-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="7bad6-117">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7bad6-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="7bad6-118">Como declarar um parâmetro opcional</span><span class="sxs-lookup"><span data-stu-id="7bad6-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="7bad6-119">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bad6-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="7bad6-120">Ao adicionar o atributo de parâmetro, omita a palavra-chave `Mandatory`.</span><span class="sxs-lookup"><span data-stu-id="7bad6-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="7bad6-121">Como declarar um parâmetro de opção</span><span class="sxs-lookup"><span data-stu-id="7bad6-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="7bad6-122">Defina uma propriedade pública como tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)e, em seguida, declare o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="7bad6-122">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="7bad6-123">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7bad6-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="7bad6-124">Como declarar um parâmetro com aliases</span><span class="sxs-lookup"><span data-stu-id="7bad6-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="7bad6-125">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bad6-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="7bad6-126">Adicione um atributo de alias que liste os aliases para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7bad6-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="7bad6-127">Neste exemplo, três aliases são definidos para o mesmo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7bad6-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="7bad6-128">O primeiro alias fornece um atalho.</span><span class="sxs-lookup"><span data-stu-id="7bad6-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="7bad6-129">O segundo e o terceiro aliases fornecem nomes que você pode usar para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="7bad6-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="7bad6-130">Para obter mais informações sobre o atributo Alias, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7bad6-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7bad6-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7bad6-131">See Also</span></span>

[<span data-ttu-id="7bad6-132">System. Management. Automation. SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7bad6-132">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="7bad6-133">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="7bad6-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="7bad6-134">Declaração de atributo de alias</span><span class="sxs-lookup"><span data-stu-id="7bad6-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

<span data-ttu-id="7bad6-135">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="7bad6-135">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
