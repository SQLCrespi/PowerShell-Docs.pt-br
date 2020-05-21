---
title: Escrevendo um snap-in personalizado do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.assetid: 55c8b5cb-8ee2-4080-afc4-3f09c9f20128
caps.latest.revision: 6
ms.openlocfilehash: 9cf4499ec2992c6cfea83fc5d0bf51d0bbfaa96a
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83556845"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="0a985-102">Escrever um snap-in personalizado do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a985-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="0a985-103">Este exemplo mostra como escrever um snap-in do Windows PowerShell que registra cmdlets específicos.</span><span class="sxs-lookup"><span data-stu-id="0a985-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="0a985-104">Com esse tipo de snap-in, você especifica quais cmdlets, provedores, tipos ou formatos registrar.</span><span class="sxs-lookup"><span data-stu-id="0a985-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="0a985-105">Para obter mais informações sobre como escrever um snap-in que registra todos os cmdlets e provedores em um assembly, consulte [escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="0a985-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="0a985-106">Para gravar um snap-in do Windows PowerShell que registra cmdlets específicos.</span><span class="sxs-lookup"><span data-stu-id="0a985-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="0a985-107">Adicione o atributo RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="0a985-107">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="0a985-108">Crie uma classe pública que derive da classe [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="0a985-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="0a985-109">Neste exemplo, o nome da classe é "CustomPSSnapinTest".</span><span class="sxs-lookup"><span data-stu-id="0a985-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="0a985-110">Adicione uma propriedade pública para o nome do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="0a985-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="0a985-111">Ao nomear snap-ins, não use nenhum dos seguintes caracteres:,,,,,,,, `#` `.` `,` `(` `)` `{` `}` `[` `]` , `&` , `-` ,,, `/` `\` `$` , `;` ,,,,, `:` `"` `'` `<` `>` , `|` , `?` `@` `` ` `` ,,,`*`</span><span class="sxs-lookup"><span data-stu-id="0a985-111">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="0a985-112">Neste exemplo, o nome do snap-in é "CustomPSSnapInTest".</span><span class="sxs-lookup"><span data-stu-id="0a985-112">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="0a985-113">Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="0a985-113">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="0a985-114">Neste exemplo, o fornecedor é "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="0a985-114">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="0a985-115">Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="0a985-115">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="0a985-116">Neste exemplo, o recurso do fornecedor é "CustomPSSnapInTest, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="0a985-116">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="0a985-117">Adicione uma propriedade pública para a descrição do snap-in (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="0a985-117">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="0a985-118">Neste exemplo, a descrição é: "Este é um snap-in personalizado do Windows PowerShell que inclui os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e".</span><span class="sxs-lookup"><span data-stu-id="0a985-118">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="0a985-119">Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).</span><span class="sxs-lookup"><span data-stu-id="0a985-119">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="0a985-120">Neste exemplo, o recurso do fornecedor é:</span><span class="sxs-lookup"><span data-stu-id="0a985-120">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="0a985-121">CustomPSSnapInTest, esse é um snap-in personalizado do Windows PowerShell que inclui os cmdlets Test-HelloWorld e Test-CustomSnapinTest ".</span><span class="sxs-lookup"><span data-stu-id="0a985-121">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="0a985-122">Especifique os cmdlets que pertencem ao snap-in personalizado (opcional) usando a classe [System. Management. Automation. Runspaces. Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) .</span><span class="sxs-lookup"><span data-stu-id="0a985-122">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="0a985-123">As informações adicionadas aqui incluem o nome do cmdlet, seu tipo .NET e o nome do arquivo de ajuda do cmdlet (o formato do nome do arquivo de ajuda do cmdlet deve ser `name.dll-help.xml` ).</span><span class="sxs-lookup"><span data-stu-id="0a985-123">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="0a985-124">Este exemplo adiciona os cmdlets Test-HelloWorld e TestCustomSnapinTest.</span><span class="sxs-lookup"><span data-stu-id="0a985-124">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="0a985-125">Especifique os provedores que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="0a985-125">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="0a985-126">Este exemplo não especifica nenhum provedor.</span><span class="sxs-lookup"><span data-stu-id="0a985-126">This example does not specify any providers.</span></span>

10. <span data-ttu-id="0a985-127">Especifique os tipos que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="0a985-127">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="0a985-128">Este exemplo não especifica nenhum tipo.</span><span class="sxs-lookup"><span data-stu-id="0a985-128">This example does not specify any types.</span></span>

11. <span data-ttu-id="0a985-129">Especifique os formatos que pertencem ao snap-in personalizado (opcional).</span><span class="sxs-lookup"><span data-stu-id="0a985-129">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="0a985-130">Este exemplo não especifica nenhum formato.</span><span class="sxs-lookup"><span data-stu-id="0a985-130">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="0a985-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0a985-131">Example</span></span>

<span data-ttu-id="0a985-132">Este exemplo mostra como gravar um snap-in personalizado do Windows PowerShell que pode ser usado para registrar os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="0a985-132">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="0a985-133">Lembre-se de que, neste exemplo, o assembly completo pode conter outros cmdlets e provedores que não seriam registrados por esse snap-in.</span><span class="sxs-lookup"><span data-stu-id="0a985-133">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

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

<span data-ttu-id="0a985-134">Para obter mais informações sobre como registrar snap-ins, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)) no [Guia do programador do Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0a985-134">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a985-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a985-135">See Also</span></span>

<span data-ttu-id="0a985-136">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0a985-136">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="0a985-137">SDK do shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a985-137">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
