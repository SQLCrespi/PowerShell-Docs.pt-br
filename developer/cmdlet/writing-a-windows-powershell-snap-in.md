---
title: Escrevendo um snap-in do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], PSSnapin example
ms.assetid: 875024f4-e02b-4416-80b9-af5e5b50aad6
caps.latest.revision: 7
ms.openlocfilehash: 465ab9e8fa29716ce0f46ad0dcf01d0ddd615bcd
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322932"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="40461-102">Escrever um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40461-102">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="40461-103">Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar todos os cmdlets e provedores do Windows PowerShell em um assembly.</span><span class="sxs-lookup"><span data-stu-id="40461-103">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="40461-104">Com esse tipo de snap-in, você não seleciona quais cmdlets e provedores você deseja registrar.</span><span class="sxs-lookup"><span data-stu-id="40461-104">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="40461-105">Para gravar um snap-in que permite selecionar o que está registrado, consulte [escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="40461-105">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="40461-106">Escrever um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40461-106">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="40461-107">Adicione o atributo RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="40461-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="40461-108">Crie uma classe pública que derive da classe [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="40461-108">Create a public class that derives from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="40461-109">Neste exemplo, o nome da classe é "GetProcPSSnapIn01".</span><span class="sxs-lookup"><span data-stu-id="40461-109">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="40461-110">Adicione uma propriedade pública para o nome do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="40461-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="40461-111">Ao nomear snap-ins, não use nenhum dos seguintes caracteres: #.</span><span class="sxs-lookup"><span data-stu-id="40461-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="40461-112">, () {} [] &-/\ $; : "' \< >;?</span><span class="sxs-lookup"><span data-stu-id="40461-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > ; ?</span></span> <span data-ttu-id="40461-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="40461-113">@ \` \*</span></span>

    <span data-ttu-id="40461-114">Neste exemplo, o nome do snap-in é "GetProcPSSnapIn01".</span><span class="sxs-lookup"><span data-stu-id="40461-114">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="40461-115">Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="40461-115">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="40461-116">Neste exemplo, o fornecedor é "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="40461-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="40461-117">Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="40461-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="40461-118">Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="40461-118">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="40461-119">Adicione uma propriedade pública para a descrição do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="40461-119">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="40461-120">Neste exemplo, a descrição é "Este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".</span><span class="sxs-lookup"><span data-stu-id="40461-120">In this example, the description is "This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

7. <span data-ttu-id="40461-121">Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="40461-121">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="40461-122">Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".</span><span class="sxs-lookup"><span data-stu-id="40461-122">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="40461-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="40461-123">Example</span></span>

<span data-ttu-id="40461-124">Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar o cmdlet Get-proc no Shell do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40461-124">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="40461-125">Lembre-se de que, neste exemplo, o assembly completo conteria apenas a classe de snap-in GetProcPSSnapIn01 e a classe cmdlet Get-proc.</span><span class="sxs-lookup"><span data-stu-id="40461-125">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the Get-Proc cmdlet class.</span></span>

```csharp
[RunInstaller(true)]
public class GetProcPSSnapIn01 : PSSnapIn
{
  /// <summary>
  /// Create an instance of the GetProcPSSnapIn01 class.
  /// </summary>
  public GetProcPSSnapIn01()
         : base()
  {
  }

  /// <summary>
  /// Specify the name of the PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "GetProcPSSnapIn01";
    }
  }

  /// <summary>
  /// Specify the vendor for the PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,VendorName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
      return "GetProcPSSnapIn01,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
      return "GetProcPSSnapIn01,This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="40461-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="40461-126">See Also</span></span>

[<span data-ttu-id="40461-127">Como registrar cmdlets, provedores e aplicativos host</span><span class="sxs-lookup"><span data-stu-id="40461-127">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="40461-128">SDK do shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40461-128">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
