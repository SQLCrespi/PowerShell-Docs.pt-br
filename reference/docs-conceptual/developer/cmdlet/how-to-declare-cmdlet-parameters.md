---
ms.date: 09/13/2016
ms.topic: reference
title: Como declarar parâmetros de cmdlet
description: Como declarar parâmetros de cmdlet
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667089"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="95591-103">Como declarar parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="95591-103">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="95591-104">Esses exemplos mostram como declarar parâmetros nomeados, posicionais, obrigatórios, opcionais e de comutação.</span><span class="sxs-lookup"><span data-stu-id="95591-104">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="95591-105">Esses exemplos também mostram como definir um alias de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="95591-105">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="95591-106">Como declarar um parâmetro nomeado</span><span class="sxs-lookup"><span data-stu-id="95591-106">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="95591-107">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="95591-107">Define a public property as shown in the following code.</span></span> <span data-ttu-id="95591-108">Quando você adicionar o atributo de parâmetro, omita a `Position` palavra-chave do atributo.</span><span class="sxs-lookup"><span data-stu-id="95591-108">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="95591-109">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="95591-109">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="95591-110">Como declarar um parâmetro posicional</span><span class="sxs-lookup"><span data-stu-id="95591-110">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="95591-111">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="95591-111">Define a public property as shown in the following code.</span></span> <span data-ttu-id="95591-112">Ao adicionar o atributo de parâmetro, defina a `Position` palavra-chave como a posição do argumento.</span><span class="sxs-lookup"><span data-stu-id="95591-112">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="95591-113">Um valor de 0 indica a primeira posição.</span><span class="sxs-lookup"><span data-stu-id="95591-113">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="95591-114">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="95591-114">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="95591-115">Como declarar um parâmetro obrigatório</span><span class="sxs-lookup"><span data-stu-id="95591-115">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="95591-116">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="95591-116">Define a public property as shown in the following code.</span></span> <span data-ttu-id="95591-117">Ao adicionar o atributo de parâmetro, defina a `Mandatory` palavra-chave como `true` .</span><span class="sxs-lookup"><span data-stu-id="95591-117">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="95591-118">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="95591-118">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="95591-119">Como declarar um parâmetro opcional</span><span class="sxs-lookup"><span data-stu-id="95591-119">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="95591-120">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="95591-120">Define a public property as shown in the following code.</span></span> <span data-ttu-id="95591-121">Quando você adicionar o atributo de parâmetro, omita a `Mandatory` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="95591-121">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="95591-122">Como declarar um parâmetro de opção</span><span class="sxs-lookup"><span data-stu-id="95591-122">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="95591-123">Defina uma propriedade pública como tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)e, em seguida, declare o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="95591-123">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="95591-124">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="95591-124">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="95591-125">Como declarar um parâmetro com aliases</span><span class="sxs-lookup"><span data-stu-id="95591-125">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="95591-126">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="95591-126">Define a public property as shown in the following code.</span></span> <span data-ttu-id="95591-127">Adicione um atributo de alias que liste os aliases para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="95591-127">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="95591-128">Neste exemplo, três aliases são definidos para o mesmo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="95591-128">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="95591-129">O primeiro alias fornece um atalho.</span><span class="sxs-lookup"><span data-stu-id="95591-129">The first alias provides a shortcut.</span></span> <span data-ttu-id="95591-130">O segundo e o terceiro aliases fornecem nomes que você pode usar para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="95591-130">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="95591-131">Para obter mais informações sobre o atributo Alias, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="95591-131">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="95591-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95591-132">See Also</span></span>

[<span data-ttu-id="95591-133">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="95591-133">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="95591-134">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="95591-134">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="95591-135">Declaração de atributo de alias</span><span class="sxs-lookup"><span data-stu-id="95591-135">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

<span data-ttu-id="95591-136">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="95591-136">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
