---
ms.date: 09/13/2016
ms.topic: reference
title: Escrever um snap-in personalizado do Windows PowerShell
description: Escrever um snap-in personalizado do Windows PowerShell
ms.openlocfilehash: e79c0c3db583fa0add9287745e97958a71360592
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659530"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="6ea90-103">Escrever um snap-in personalizado do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ea90-103">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="6ea90-104">Este exemplo mostra como escrever um snap-in do Windows PowerShell que registra cmdlets específicos.</span><span class="sxs-lookup"><span data-stu-id="6ea90-104">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="6ea90-105">Com esse tipo de snap-in, você especifica quais cmdlets, provedores, tipos ou formatos registrar.</span><span class="sxs-lookup"><span data-stu-id="6ea90-105">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="6ea90-106">Para obter mais informações sobre como escrever um snap-in que registra todos os cmdlets e provedores em um assembly, consulte [escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="6ea90-106">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="6ea90-107">Para gravar um snap-in do Windows PowerShell que registra cmdlets específicos.</span><span class="sxs-lookup"><span data-stu-id="6ea90-107">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="6ea90-108">Adicione o atributo RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="6ea90-108">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="6ea90-109">Crie uma classe pública que derive da classe [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="6ea90-109">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="6ea90-110">Neste exemplo, o nome da classe é "CustomPSSnapinTest".</span><span class="sxs-lookup"><span data-stu-id="6ea90-110">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="6ea90-111">Adicione uma propriedade pública para o nome do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="6ea90-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="6ea90-112">Ao nomear snap-ins, não use nenhum dos seguintes caracteres:,,,,,,,, `#` `.` `,` `(` `)` `{` `}` `[` `]` , `&` , `-` ,,, `/` `\` `$` , `;` ,,,,, `:` `"` `'` `<` `>` , `|` , `?` `@` `` ` `` ,,, `*`</span><span class="sxs-lookup"><span data-stu-id="6ea90-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="6ea90-113">Neste exemplo, o nome do snap-in é "CustomPSSnapInTest".</span><span class="sxs-lookup"><span data-stu-id="6ea90-113">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="6ea90-114">Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="6ea90-114">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="6ea90-115">Neste exemplo, o fornecedor é "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="6ea90-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="6ea90-116">Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="6ea90-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="6ea90-117">Neste exemplo, o recurso do fornecedor é "CustomPSSnapInTest, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="6ea90-117">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="6ea90-118">Adicione uma propriedade pública para a descrição do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="6ea90-118">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="6ea90-119">Neste exemplo, a descrição é: "Este é um snap-in personalizado do Windows PowerShell que inclui os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e".</span><span class="sxs-lookup"><span data-stu-id="6ea90-119">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="6ea90-120">Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="6ea90-120">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="6ea90-121">Neste exemplo, o recurso do fornecedor é:</span><span class="sxs-lookup"><span data-stu-id="6ea90-121">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="6ea90-122">CustomPSSnapInTest, esse é um snap-in personalizado do Windows PowerShell que inclui os cmdlets Test-HelloWorld e Test-CustomSnapinTest ".</span><span class="sxs-lookup"><span data-stu-id="6ea90-122">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="6ea90-123">Especifique os cmdlets que pertencem ao snap-in personalizado (opcional) usando a classe [System. Management. Automation. Runspaces. Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) .</span><span class="sxs-lookup"><span data-stu-id="6ea90-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="6ea90-124">As informações adicionadas aqui incluem o nome do cmdlet, seu tipo .NET e o nome do arquivo de ajuda do cmdlet (o formato do nome do arquivo de ajuda do cmdlet deve ser `name.dll-help.xml` ).</span><span class="sxs-lookup"><span data-stu-id="6ea90-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="6ea90-125">Este exemplo adiciona os cmdlets Test-HelloWorld e TestCustomSnapinTest.</span><span class="sxs-lookup"><span data-stu-id="6ea90-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="6ea90-126">Especifique os provedores que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="6ea90-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="6ea90-127">Este exemplo não especifica nenhum provedor.</span><span class="sxs-lookup"><span data-stu-id="6ea90-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="6ea90-128">Especifique os tipos que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="6ea90-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="6ea90-129">Este exemplo não especifica nenhum tipo.</span><span class="sxs-lookup"><span data-stu-id="6ea90-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="6ea90-130">Especifique os formatos que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="6ea90-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="6ea90-131">Este exemplo não especifica nenhum formato.</span><span class="sxs-lookup"><span data-stu-id="6ea90-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="6ea90-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6ea90-132">Example</span></span>

<span data-ttu-id="6ea90-133">Este exemplo mostra como gravar um snap-in personalizado do Windows PowerShell que pode ser usado para registrar os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="6ea90-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="6ea90-134">Lembre-se de que, neste exemplo, o assembly completo pode conter outros cmdlets e provedores que não seriam registrados por esse snap-in.</span><span class="sxs-lookup"><span data-stu-id="6ea90-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
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
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
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
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="6ea90-135">Para obter mais informações sobre como registrar snap-ins, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)) no [Guia do programador do Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="6ea90-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ea90-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ea90-136">See Also</span></span>

<span data-ttu-id="6ea90-137">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="6ea90-137">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="6ea90-138">SDK do Shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ea90-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
