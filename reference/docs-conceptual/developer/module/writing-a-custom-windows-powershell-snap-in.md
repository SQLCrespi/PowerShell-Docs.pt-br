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
# <a name="writing-a-custom-windows-powershell-snap-in"></a>Escrever um snap-in personalizado do Windows PowerShell

Este exemplo mostra como escrever um snap-in do Windows PowerShell que registra cmdlets específicos.

Com esse tipo de snap-in, você especifica quais cmdlets, provedores, tipos ou formatos registrar. Para obter mais informações sobre como escrever um snap-in que registra todos os cmdlets e provedores em um assembly, consulte [escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md).

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a>Para gravar um snap-in do Windows PowerShell que registra cmdlets específicos.

1. Adicione o atributo RunInstallerAttribute.
2. Crie uma classe pública que derive da classe [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .

   Neste exemplo, o nome da classe é "CustomPSSnapinTest".

3. Adicione uma propriedade pública para o nome do snap-in (obrigatório). Ao nomear snap-ins, não use nenhum dos seguintes caracteres:,,,,,,,, `#` `.` `,` `(` `)` `{` `}` `[` `]` , `&` , `-` ,,, `/` `\` `$` , `;` ,,,,, `:` `"` `'` `<` `>` , `|` , `?` `@` `` ` `` ,,, `*`

   Neste exemplo, o nome do snap-in é "CustomPSSnapInTest".

4. Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).

   Neste exemplo, o fornecedor é "Microsoft".

5. Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).

   Neste exemplo, o recurso do fornecedor é "CustomPSSnapInTest, Microsoft".

6. Adicione uma propriedade pública para a descrição do snap-in (obrigatório).

   Neste exemplo, a descrição é: "Este é um snap-in personalizado do Windows PowerShell que inclui os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e".

7. Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).

   Neste exemplo, o recurso do fornecedor é:

   > CustomPSSnapInTest, esse é um snap-in personalizado do Windows PowerShell que inclui os cmdlets Test-HelloWorld e Test-CustomSnapinTest ".

8. Especifique os cmdlets que pertencem ao snap-in personalizado (opcional) usando a classe [System. Management. Automation. Runspaces. Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) . As informações adicionadas aqui incluem o nome do cmdlet, seu tipo .NET e o nome do arquivo de ajuda do cmdlet (o formato do nome do arquivo de ajuda do cmdlet deve ser `name.dll-help.xml` ).

   Este exemplo adiciona os cmdlets Test-HelloWorld e TestCustomSnapinTest.

9. Especifique os provedores que pertencem ao snap-in personalizado (opcional).

   Este exemplo não especifica nenhum provedor.

10. Especifique os tipos que pertencem ao snap-in personalizado (opcional).

    Este exemplo não especifica nenhum tipo.

11. Especifique os formatos que pertencem ao snap-in personalizado (opcional).

    Este exemplo não especifica nenhum formato.

## <a name="example"></a>Exemplo

Este exemplo mostra como gravar um snap-in personalizado do Windows PowerShell que pode ser usado para registrar os `Test-HelloWorld` `Test-CustomSnapinTest` cmdlets e. Lembre-se de que, neste exemplo, o assembly completo pode conter outros cmdlets e provedores que não seriam registrados por esse snap-in.

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

Para obter mais informações sobre como registrar snap-ins, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)) no [Guia do programador do Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).

## <a name="see-also"></a>Consulte Também

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[SDK do Shell do Windows PowerShell](../windows-powershell-reference.md)
