---
title: Tipos de parâmetros de cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e704aae6e23568be9935e228752f652929863a98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786366"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="a636b-102">Tipos de parâmetros de cmdlet</span><span class="sxs-lookup"><span data-stu-id="a636b-102">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="a636b-103">Este tópico descreve os diferentes tipos de parâmetros que você pode declarar em cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a636b-103">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="a636b-104">Os parâmetros de cmdlet podem ser posicionais, nomeados, obrigatórios, opcionais ou parâmetros de switch.</span><span class="sxs-lookup"><span data-stu-id="a636b-104">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="a636b-105">Parâmetros posicionais e nomeados</span><span class="sxs-lookup"><span data-stu-id="a636b-105">Positional and Named Parameters</span></span>

<span data-ttu-id="a636b-106">Todos os parâmetros de cmdlet são parâmetros nomeados ou posicionais.</span><span class="sxs-lookup"><span data-stu-id="a636b-106">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="a636b-107">Um parâmetro nomeado requer que você digite o nome do parâmetro e o argumento ao chamar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a636b-107">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="a636b-108">Um parâmetro posicional requer apenas que você digite os argumentos em ordem relativa.</span><span class="sxs-lookup"><span data-stu-id="a636b-108">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="a636b-109">Em seguida, o sistema mapeia o primeiro argumento sem nome para o primeiro parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="a636b-109">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="a636b-110">O sistema mapeia o segundo argumento sem nome para o segundo parâmetro sem nome e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a636b-110">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="a636b-111">Por padrão, todos os parâmetros de cmdlet são parâmetros nomeados.</span><span class="sxs-lookup"><span data-stu-id="a636b-111">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="a636b-112">Para definir um parâmetro nomeado, omita a `Position` palavra-chave na declaração de atributo de **parâmetro** , conforme mostrado na declaração de parâmetro a seguir.</span><span class="sxs-lookup"><span data-stu-id="a636b-112">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="a636b-113">Para definir um parâmetro posicional, adicione a `Position` palavra-chave na declaração de atributo de parâmetro e, em seguida, especifique uma posição.</span><span class="sxs-lookup"><span data-stu-id="a636b-113">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="a636b-114">No exemplo a seguir, o `UserName` parâmetro é declarado como um parâmetro posicional com a posição 0.</span><span class="sxs-lookup"><span data-stu-id="a636b-114">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="a636b-115">Isso significa que o primeiro argumento da chamada será associado automaticamente a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a636b-115">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> <span data-ttu-id="a636b-116">Um bom design de cmdlet recomenda que os parâmetros mais usados sejam declarados como parâmetros posicionais para que o usuário não precise inserir o nome do parâmetro quando o cmdlet for executado.</span><span class="sxs-lookup"><span data-stu-id="a636b-116">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="a636b-117">Os parâmetros posicionais e nomeados aceitam argumentos únicos ou vários argumentos separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a636b-117">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="a636b-118">Vários argumentos são permitidos somente se o parâmetro aceita uma coleção, como uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a636b-118">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="a636b-119">Você pode misturar os parâmetros posicionais e nomeados no mesmo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a636b-119">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="a636b-120">Nesse caso, o sistema recupera os argumentos nomeados primeiro e, em seguida, tenta mapear os argumentos não nomeados restantes para os parâmetros posicionais.</span><span class="sxs-lookup"><span data-stu-id="a636b-120">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="a636b-121">Os comandos a seguir mostram as diferentes maneiras pelas quais você pode especificar argumentos únicos e múltiplos para os parâmetros do `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a636b-121">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="a636b-122">Observe que nos dois últimos exemplos, **-Name** não precisa ser especificado porque o `Name` parâmetro é definido como um parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="a636b-122">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="a636b-123">Parâmetros obrigatórios e opcionais</span><span class="sxs-lookup"><span data-stu-id="a636b-123">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="a636b-124">Você também pode definir parâmetros de cmdlet como parâmetros obrigatórios ou opcionais.</span><span class="sxs-lookup"><span data-stu-id="a636b-124">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="a636b-125">(Um parâmetro obrigatório deve ser especificado antes de o tempo de execução do Windows PowerShell invocar o cmdlet.)  Por padrão, os parâmetros são definidos como opcionais.</span><span class="sxs-lookup"><span data-stu-id="a636b-125">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="a636b-126">Para definir um parâmetro obrigatório, adicione a `Mandatory` palavra-chave na declaração de atributo de parâmetro e defina-a `true` como, conforme mostrado na declaração de parâmetro a seguir.</span><span class="sxs-lookup"><span data-stu-id="a636b-126">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="a636b-127">Para definir um parâmetro opcional, omita a `Mandatory` palavra-chave na declaração de atributo de **parâmetro** , conforme mostrado na declaração de parâmetro a seguir.</span><span class="sxs-lookup"><span data-stu-id="a636b-127">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="a636b-128">Parâmetros de comutação</span><span class="sxs-lookup"><span data-stu-id="a636b-128">Switch Parameters</span></span>

<span data-ttu-id="a636b-129">O Windows PowerShell fornece um tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) que permite que você defina um parâmetro cujo valor é definido automaticamente como `false` se o parâmetro não for especificado quando o cmdlet for chamado.</span><span class="sxs-lookup"><span data-stu-id="a636b-129">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="a636b-130">Sempre que possível, use parâmetros de opção no lugar de parâmetros boolianos.</span><span class="sxs-lookup"><span data-stu-id="a636b-130">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="a636b-131">Considere o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a636b-131">Consider the following sample.</span></span> <span data-ttu-id="a636b-132">Por padrão, vários cmdlets do Windows PowerShell não passam um objeto de saída para baixo no pipeline.</span><span class="sxs-lookup"><span data-stu-id="a636b-132">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="a636b-133">No entanto, esses cmdlets têm um `PassThru` parâmetro de opção que substitui o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="a636b-133">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="a636b-134">Se o `PassThru` parâmetro for especificado quando esses cmdlets forem chamados, o cmdlet retornará um objeto de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="a636b-134">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="a636b-135">Se você precisar que o parâmetro tenha um valor padrão `true` quando o parâmetro não for especificado na chamada, considere reverter a noção do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a636b-135">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="a636b-136">Por exemplo, em vez de definir o atributo de parâmetro como um valor booliano de `true` , declare a propriedade como o tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) e, em seguida, defina o valor padrão do parâmetro como `false` .</span><span class="sxs-lookup"><span data-stu-id="a636b-136">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="a636b-137">Para definir um parâmetro de opção, declare a propriedade como o tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a636b-137">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="a636b-138">Para fazer com que o cmdlet atue no parâmetro quando ele for especificado, use a seguinte estrutura dentro de um dos métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="a636b-138">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a><span data-ttu-id="a636b-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a636b-139">See Also</span></span>

[<span data-ttu-id="a636b-140">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a636b-140">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
