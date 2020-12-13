---
ms.date: 09/13/2016
ms.topic: reference
title: Escrever um snap-in do Windows PowerShell
description: Escrever um snap-in do Windows PowerShell
ms.openlocfilehash: f658c2fa1211bfb77d2e8edd3999ce7f92df13bb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659453"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="e7d53-103">Escrever um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7d53-103">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="e7d53-104">Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar todos os cmdlets e provedores do Windows PowerShell em um assembly.</span><span class="sxs-lookup"><span data-stu-id="e7d53-104">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="e7d53-105">Com esse tipo de snap-in, você não seleciona quais cmdlets e provedores você deseja registrar.</span><span class="sxs-lookup"><span data-stu-id="e7d53-105">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="e7d53-106">Para gravar um snap-in que permite selecionar o que está registrado, consulte [escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="e7d53-106">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="e7d53-107">Escrever um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7d53-107">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="e7d53-108">Adicione o atributo RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="e7d53-108">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="e7d53-109">Crie uma classe pública que derive da classe [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="e7d53-109">Create a public class that derives from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="e7d53-110">Neste exemplo, o nome da classe é "GetProcPSSnapIn01".</span><span class="sxs-lookup"><span data-stu-id="e7d53-110">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="e7d53-111">Adicione uma propriedade pública para o nome do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="e7d53-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="e7d53-112">Ao nomear snap-ins, não use nenhum dos seguintes caracteres:,,,,,,,, `#` `.` `,` `(` `)` `{` `}` `[` `]` , `&` , `-` ,,, `/` `\` `$` , `;` ,,,,, `:` `"` `'` `<` `>` , `|` , `?` `@` `` ` `` ,,, `*`</span><span class="sxs-lookup"><span data-stu-id="e7d53-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

    <span data-ttu-id="e7d53-113">Neste exemplo, o nome do snap-in é "GetProcPSSnapIn01".</span><span class="sxs-lookup"><span data-stu-id="e7d53-113">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="e7d53-114">Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="e7d53-114">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="e7d53-115">Neste exemplo, o fornecedor é "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="e7d53-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="e7d53-116">Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="e7d53-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="e7d53-117">Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="e7d53-117">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="e7d53-118">Adicione uma propriedade pública para a descrição do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="e7d53-118">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="e7d53-119">Neste exemplo, a descrição é "Este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".</span><span class="sxs-lookup"><span data-stu-id="e7d53-119">In this example, the description is "This is a Windows PowerShell snap-in that registers the  get-proc cmdlet".</span></span>

7. <span data-ttu-id="e7d53-120">Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="e7d53-120">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="e7d53-121">Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".</span><span class="sxs-lookup"><span data-stu-id="e7d53-121">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in  that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="e7d53-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7d53-122">Example</span></span>

<span data-ttu-id="e7d53-123">Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar o cmdlet Get-Proc no Shell do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7d53-123">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="e7d53-124">Lembre-se de que, neste exemplo, o assembly completo conteria apenas a classe de snap-in GetProcPSSnapIn01 e a `Get-Proc` classe cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7d53-124">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the `Get-Proc` cmdlet class.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e7d53-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7d53-125">See Also</span></span>

<span data-ttu-id="e7d53-126">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e7d53-126">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e7d53-127">SDK do Shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7d53-127">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
