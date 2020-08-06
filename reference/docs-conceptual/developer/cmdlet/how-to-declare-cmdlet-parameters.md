---
title: Como declarar parâmetros de cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 97e86a1eb715f149a8383a1a4529c00da4f0eba8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774381"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="eb18f-102">Como declarar parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb18f-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="eb18f-103">Esses exemplos mostram como declarar parâmetros nomeados, posicionais, obrigatórios, opcionais e de comutação.</span><span class="sxs-lookup"><span data-stu-id="eb18f-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="eb18f-104">Esses exemplos também mostram como definir um alias de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eb18f-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="eb18f-105">Como declarar um parâmetro nomeado</span><span class="sxs-lookup"><span data-stu-id="eb18f-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="eb18f-106">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb18f-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="eb18f-107">Quando você adicionar o atributo de parâmetro, omita a `Position` palavra-chave do atributo.</span><span class="sxs-lookup"><span data-stu-id="eb18f-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="eb18f-108">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb18f-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="eb18f-109">Como declarar um parâmetro posicional</span><span class="sxs-lookup"><span data-stu-id="eb18f-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="eb18f-110">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb18f-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="eb18f-111">Ao adicionar o atributo de parâmetro, defina a `Position` palavra-chave como a posição do argumento.</span><span class="sxs-lookup"><span data-stu-id="eb18f-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="eb18f-112">Um valor de 0 indica a primeira posição.</span><span class="sxs-lookup"><span data-stu-id="eb18f-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="eb18f-113">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb18f-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="eb18f-114">Como declarar um parâmetro obrigatório</span><span class="sxs-lookup"><span data-stu-id="eb18f-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="eb18f-115">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb18f-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="eb18f-116">Ao adicionar o atributo de parâmetro, defina a `Mandatory` palavra-chave como `true` .</span><span class="sxs-lookup"><span data-stu-id="eb18f-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="eb18f-117">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb18f-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="eb18f-118">Como declarar um parâmetro opcional</span><span class="sxs-lookup"><span data-stu-id="eb18f-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="eb18f-119">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb18f-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="eb18f-120">Quando você adicionar o atributo de parâmetro, omita a `Mandatory` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="eb18f-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="eb18f-121">Como declarar um parâmetro de opção</span><span class="sxs-lookup"><span data-stu-id="eb18f-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="eb18f-122">Defina uma propriedade pública como tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)e, em seguida, declare o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb18f-122">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="eb18f-123">Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb18f-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="eb18f-124">Como declarar um parâmetro com aliases</span><span class="sxs-lookup"><span data-stu-id="eb18f-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="eb18f-125">Defina uma propriedade pública, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb18f-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="eb18f-126">Adicione um atributo de alias que liste os aliases para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eb18f-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="eb18f-127">Neste exemplo, três aliases são definidos para o mesmo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eb18f-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="eb18f-128">O primeiro alias fornece um atalho.</span><span class="sxs-lookup"><span data-stu-id="eb18f-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="eb18f-129">O segundo e o terceiro aliases fornecem nomes que você pode usar para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="eb18f-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="eb18f-130">Para obter mais informações sobre o atributo Alias, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb18f-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb18f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb18f-131">See Also</span></span>

[<span data-ttu-id="eb18f-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="eb18f-132">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="eb18f-133">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="eb18f-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="eb18f-134">Declaração de atributo de alias</span><span class="sxs-lookup"><span data-stu-id="eb18f-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="eb18f-135">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb18f-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
