---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros dinâmicos de cmdlet
description: Parâmetros dinâmicos de cmdlet
ms.openlocfilehash: b44dda2354e8b689e419c7bf4deefadfc4edcb07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653434"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="9d2b2-103">Parâmetros dinâmicos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="9d2b2-103">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="9d2b2-104">Os cmdlets podem definir parâmetros que estão disponíveis para o usuário em condições especiais, como quando o argumento de outro parâmetro é um valor específico.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-104">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="9d2b2-105">Esses parâmetros são adicionados em tempo de execução e são chamados de parâmetros dinâmicos porque são adicionados apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-105">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="9d2b2-106">Por exemplo, você pode criar um cmdlet que adiciona vários parâmetros somente quando um parâmetro de opção específico é especificado.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-106">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="9d2b2-107">Provedores e funções do PowerShell também podem definir parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-107">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="9d2b2-108">Parâmetros dinâmicos nos cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d2b2-108">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="9d2b2-109">O PowerShell usa parâmetros dinâmicos em vários dos seus cmdlets de provedor.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-109">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="9d2b2-110">Por exemplo, os `Get-Item` `Get-ChildItem` cmdlets e adicionam um parâmetro **CodeSigningCert** em tempo de execução quando o parâmetro **Path** especifica o caminho do provedor de **certificado** .</span><span class="sxs-lookup"><span data-stu-id="9d2b2-110">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="9d2b2-111">Se o parâmetro **path** especificar um caminho para um provedor diferente, o parâmetro **CodeSigningCert** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-111">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="9d2b2-112">Os exemplos a seguir mostram como o parâmetro **CodeSigningCert** é adicionado em tempo de execução quando `Get-Item` é executado.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-112">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="9d2b2-113">Neste exemplo, o tempo de execução do PowerShell adicionou o parâmetro e o cmdlet foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-113">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="9d2b2-114">Neste exemplo, uma unidade de **sistema de arquivos** é especificada e um erro é retornado.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-114">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="9d2b2-115">A mensagem de erro indica que o parâmetro **CodeSigningCert** não pode ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-115">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="9d2b2-116">Suporte para parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="9d2b2-116">Support for dynamic parameters</span></span>

<span data-ttu-id="9d2b2-117">Para dar suporte a parâmetros dinâmicos, os elementos a seguir devem ser incluídos no código do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-117">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="9d2b2-118">Interface</span><span class="sxs-lookup"><span data-stu-id="9d2b2-118">Interface</span></span>

<span data-ttu-id="9d2b2-119">[System. Management. Automation. IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="9d2b2-119">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="9d2b2-120">Essa interface fornece o método que recupera os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-120">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="9d2b2-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-121">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="9d2b2-122">Método</span><span class="sxs-lookup"><span data-stu-id="9d2b2-122">Method</span></span>

<span data-ttu-id="9d2b2-123">[System. Management. Automation. IDynamicParameters. Getdynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="9d2b2-123">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="9d2b2-124">Esse método recupera o objeto que contém as definições de parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-124">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="9d2b2-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-125">For example:</span></span>

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a><span data-ttu-id="9d2b2-126">Classe</span><span class="sxs-lookup"><span data-stu-id="9d2b2-126">Class</span></span>

<span data-ttu-id="9d2b2-127">Uma classe que define os parâmetros dinâmicos a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-127">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="9d2b2-128">Essa classe deve incluir um atributo de **parâmetro** para cada parâmetro e qualquer **alias** opcional e atributos de **validação** que são necessários para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-128">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="9d2b2-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-129">For example:</span></span>

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

<span data-ttu-id="9d2b2-130">Para obter um exemplo completo de um cmdlet que dá suporte a parâmetros dinâmicos, consulte [como declarar parâmetros dinâmicos](./how-to-declare-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9d2b2-130">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d2b2-131">Veja também</span><span class="sxs-lookup"><span data-stu-id="9d2b2-131">See also</span></span>

[<span data-ttu-id="9d2b2-132">System. Management. Automation. IDynamicParameters</span><span class="sxs-lookup"><span data-stu-id="9d2b2-132">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="9d2b2-133">System. Management. Automation. IDynamicParameters. getdynamicparameters</span><span class="sxs-lookup"><span data-stu-id="9d2b2-133">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="9d2b2-134">Como declarar parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="9d2b2-134">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

<span data-ttu-id="9d2b2-135">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-135">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
