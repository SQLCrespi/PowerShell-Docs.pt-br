---
title: Escrevendo um snap-in do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], PSSnapin example
ms.openlocfilehash: 02603c54fb9852a8b78ecf68e3ee387d1fd418fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779097"
---
# <a name="writing-a-windows-powershell-snap-in"></a>Escrever um snap-in do Windows PowerShell

Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar todos os cmdlets e provedores do Windows PowerShell em um assembly.

Com esse tipo de snap-in, você não seleciona quais cmdlets e provedores você deseja registrar. Para gravar um snap-in que permite selecionar o que está registrado, consulte [escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md).

### <a name="writing-a-windows-powershell-snap-in"></a>Escrever um snap-in do Windows PowerShell

1. Adicione o atributo RunInstallerAttribute.

2. Crie uma classe pública que derive da classe [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) .

    Neste exemplo, o nome da classe é "GetProcPSSnapIn01".

3. Adicione uma propriedade pública para o nome do snap-in (obrigatório). Ao nomear snap-ins, não use nenhum dos seguintes caracteres:,,,,,,,, `#` `.` `,` `(` `)` `{` `}` `[` `]` , `&` , `-` ,,, `/` `\` `$` , `;` ,,,,, `:` `"` `'` `<` `>` , `|` , `?` `@` `` ` `` ,,,`*`

    Neste exemplo, o nome do snap-in é "GetProcPSSnapIn01".

4. Adicione uma propriedade pública para o fornecedor do snap-in (obrigatório).

    Neste exemplo, o fornecedor é "Microsoft".

5. Adicione uma propriedade pública para o recurso de fornecedor do snap-in (opcional).

    Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, Microsoft".

6. Adicione uma propriedade pública para a descrição do snap-in (obrigatório).

    Neste exemplo, a descrição é "Este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".

7. Adicione uma propriedade pública para o recurso de descrição do snap-in (opcional).

    Neste exemplo, o recurso do fornecedor é "GetProcPSSnapIn01, este é um snap-in do Windows PowerShell que registra o cmdlet Get-proc".

## <a name="example"></a>Exemplo

Este exemplo mostra como escrever um snap-in do Windows PowerShell que pode ser usado para registrar o cmdlet Get-proc no Shell do Windows PowerShell. Lembre-se de que, neste exemplo, o assembly completo conteria apenas a classe de snap-in GetProcPSSnapIn01 e a `Get-Proc` classe cmdlet.

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

## <a name="see-also"></a>Consulte Também

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[SDK do shell do Windows PowerShell](../windows-powershell-reference.md)
