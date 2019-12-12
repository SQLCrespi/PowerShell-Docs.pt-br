---
title: Parâmetros dinâmicos de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 19d31f6b619dff23e7e35bb53d2397f4f41eb728
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369875"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="86f5c-102">Parâmetros dinâmicos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="86f5c-102">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="86f5c-103">Os cmdlets podem definir parâmetros que estão disponíveis para o usuário em condições especiais, como quando o argumento de outro parâmetro é um valor específico.</span><span class="sxs-lookup"><span data-stu-id="86f5c-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="86f5c-104">Esses parâmetros são adicionados em tempo de execução e são chamados de parâmetros dinâmicos porque são adicionados apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="86f5c-104">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="86f5c-105">Por exemplo, você pode criar um cmdlet que adiciona vários parâmetros somente quando um parâmetro de opção específico é especificado.</span><span class="sxs-lookup"><span data-stu-id="86f5c-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="86f5c-106">Provedores e funções do PowerShell também podem definir parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="86f5c-106">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="86f5c-107">Parâmetros dinâmicos nos cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="86f5c-107">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="86f5c-108">O PowerShell usa parâmetros dinâmicos em vários dos seus cmdlets de provedor.</span><span class="sxs-lookup"><span data-stu-id="86f5c-108">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="86f5c-109">Por exemplo, os cmdlets `Get-Item` e `Get-ChildItem` adicionam um parâmetro **CodeSigningCert** em tempo de execução quando o parâmetro **Path** especifica o caminho do provedor de **certificado** .</span><span class="sxs-lookup"><span data-stu-id="86f5c-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="86f5c-110">Se o parâmetro **path** especificar um caminho para um provedor diferente, o parâmetro **CodeSigningCert** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="86f5c-110">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="86f5c-111">Os exemplos a seguir mostram como o parâmetro **CodeSigningCert** é adicionado em tempo de execução quando `Get-Item` é executado.</span><span class="sxs-lookup"><span data-stu-id="86f5c-111">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="86f5c-112">Neste exemplo, o tempo de execução do PowerShell adicionou o parâmetro e o cmdlet foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="86f5c-112">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="86f5c-113">Neste exemplo, uma unidade de **sistema de arquivos** é especificada e um erro é retornado.</span><span class="sxs-lookup"><span data-stu-id="86f5c-113">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="86f5c-114">A mensagem de erro indica que o parâmetro **CodeSigningCert** não pode ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="86f5c-114">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

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

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="86f5c-115">Suporte para parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="86f5c-115">Support for dynamic parameters</span></span>

<span data-ttu-id="86f5c-116">Para dar suporte a parâmetros dinâmicos, os elementos a seguir devem ser incluídos no código do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86f5c-116">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="86f5c-117">Interface</span><span class="sxs-lookup"><span data-stu-id="86f5c-117">Interface</span></span>

<span data-ttu-id="86f5c-118">[System. Management. Automation. IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="86f5c-118">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="86f5c-119">Essa interface fornece o método que recupera os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="86f5c-119">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="86f5c-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86f5c-120">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="86f5c-121">Método</span><span class="sxs-lookup"><span data-stu-id="86f5c-121">Method</span></span>

<span data-ttu-id="86f5c-122">[System. Management. Automation. IDynamicParameters. Getdynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="86f5c-122">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="86f5c-123">Esse método recupera o objeto que contém as definições de parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="86f5c-123">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="86f5c-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86f5c-124">For example:</span></span>

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

### <a name="class"></a><span data-ttu-id="86f5c-125">Classe</span><span class="sxs-lookup"><span data-stu-id="86f5c-125">Class</span></span>

<span data-ttu-id="86f5c-126">Uma classe que define os parâmetros dinâmicos a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="86f5c-126">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="86f5c-127">Essa classe deve incluir um atributo de **parâmetro** para cada parâmetro e qualquer **alias** opcional e atributos de **validação** que são necessários para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86f5c-127">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="86f5c-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86f5c-128">For example:</span></span>

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

<span data-ttu-id="86f5c-129">Para obter um exemplo completo de um cmdlet que dá suporte a parâmetros dinâmicos, consulte [como declarar parâmetros dinâmicos](./how-to-declare-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="86f5c-129">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="86f5c-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="86f5c-130">See also</span></span>

[<span data-ttu-id="86f5c-131">System. Management. Automation. IDynamicParameters</span><span class="sxs-lookup"><span data-stu-id="86f5c-131">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="86f5c-132">System. Management. Automation. IDynamicParameters. getdynamicparameters</span><span class="sxs-lookup"><span data-stu-id="86f5c-132">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="86f5c-133">Como declarar parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="86f5c-133">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

<span data-ttu-id="86f5c-134">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="86f5c-134">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
