---
ms.date: 01/15/2019
ms.topic: reference
title: Como gravar um cmdlet simples
description: Como gravar um cmdlet simples
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646485"
---
# <a name="how-to-write-a-cmdlet"></a>Como escrever um cmdlet

Este artigo mostra como escrever um cmdlet. O `Send-Greeting` cmdlet usa um único nome de usuário como entrada e, em seguida, grava uma saudação para esse usuário. Embora o cmdlet não faça muito trabalho, este exemplo demonstra as principais seções de um cmdlet.

## <a name="steps-to-write-a-cmdlet"></a>Etapas para gravar um cmdlet

1. Para declarar a classe como um cmdlet, use o atributo **cmdlet** . O atributo **cmdlet** especifica o verbo e o substantivo para o nome do cmdlet.

   Para obter mais informações sobre o atributo de **cmdlet** , consulte [declaração de CmdletAttribute](cmdlet-attribute-declaration.md).

2. Especifique o nome da classe.

3. Especifique que o cmdlet deriva de qualquer uma das seguintes classes:

   * [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)
   * [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

4. Para definir os parâmetros para o cmdlet, use o atributo **Parameter** . Nesse caso, apenas um parâmetro obrigatório é especificado.

   Para obter mais informações sobre o atributo **Parameter** , consulte a [declaração ParameterAttribute](parameter-attribute-declaration.md).

5. Substitua o método de processamento de entrada que processa a entrada. Nesse caso, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído.

6. Para gravar a saudação, use o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).
   A saudação é exibida no seguinte formato:

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a>Exemplo

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>Confira também

[System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)

[System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[Declaração de CmdletAttribute](cmdlet-attribute-declaration.md)

[Declaração de ParameterAttribute](parameter-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
