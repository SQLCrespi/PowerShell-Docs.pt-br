---
description: Descreve como usar métodos para executar ações em objetos no PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: c52afed005965512b16e6869dd32f21d9f72740c
ms.sourcegitcommit: 15f759ca68d17acecab46b52250298d4f2037c4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "103575535"
---
# <a name="about-methods"></a>Sobre métodos

## <a name="short-description"></a>Descrição breve
Descreve como usar métodos para executar ações em objetos no PowerShell.

## <a name="long-description"></a>Descrição longa

O PowerShell usa objetos para representar os itens em armazenamentos de dados ou o estado do computador. Por exemplo, os objetos FileInfo representam os arquivos em unidades do sistema de arquivos e os objetos ProcessInfo representam os processos no computador.

Os objetos têm propriedades, que armazenam dados sobre o objeto e métodos que permitem alterar o objeto.

Um "método" é um conjunto de instruções que especificam uma ação que você pode executar no objeto. Por exemplo, o `FileInfo` objeto inclui o `CopyTo` método que copia o arquivo que o `FileInfo` objeto representa.

Para obter os métodos de qualquer objeto, use o `Get-Member` cmdlet. Use sua propriedade **MemberType** com um valor de "Method". O comando a seguir obtém os métodos de objetos de processo.

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

Para executar ou "invocar" um método de um objeto, digite um ponto (.), o nome do método e um conjunto de parênteses "()". Se o método tiver argumentos, coloque os valores de argumento dentro dos parênteses. Os parênteses são necessários para cada chamada de método, mesmo quando não há argumentos. Se o método usar vários argumentos, eles deverão ser separados por vírgulas.

Por exemplo, o comando a seguir invoca o método Kill de processos para encerrar o processo do bloco de notas no computador.

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

Este exemplo pode ser reduzido com a combinação das instruções acima.

```powershell
(Get-Process Notepad).Kill()
```

O `Get-Process` comando é colocado entre parênteses para garantir que ele seja executado antes que o método Kill seja invocado. O `Kill` método é invocado no objeto retornado `Process` .

Outro método muito útil é o `Replace` método de cadeias de caracteres. O `Replace` método substitui o texto em uma cadeia de caracteres. No exemplo a seguir, o ponto (.) pode ser colocado imediatamente após a aspa de término da cadeia de caracteres.

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

Conforme mostrado nos exemplos anteriores, você pode invocar um método em um objeto que você obtém usando um comando, um objeto em uma variável ou qualquer coisa que resulte em um objeto (como uma cadeia de caracteres entre aspas).

A partir do PowerShell 4,0, a invocação de método usando nomes de métodos dinâmicos é suportada.

## <a name="learning-about-methods"></a>Aprendendo sobre métodos

Para localizar definições dos métodos de um objeto, acesse o tópico da ajuda para o tipo de objeto e procure sua página de métodos. Por exemplo, a página a seguir descreve os métodos de Process Objects [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods).

Para determinar os argumentos de um método, examine a definição do método, que é como o diagrama de sintaxe de um cmdlet do PowerShell.

Uma definição de método pode ter uma ou mais assinaturas de método, que são como os conjuntos de parâmetros de cmdlets do PowerShell. As assinaturas mostram todos os formatos válidos de comandos para invocar o método.

Por exemplo, o `CopyTo` método da `FileInfo` classe contém as duas assinaturas de método a seguir:

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

A primeira assinatura do método usa o nome do arquivo de destino (e um caminho). O exemplo a seguir usa o primeiro `CopyTo` método para copiar o `Final.txt` arquivo para o `C:\Bin` diretório.

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> Ao contrário do modo de _argumento_ do PowerShell, os métodos de objeto são executados no modo de _expressão_ , que é uma passagem para o .NET Framework no qual o PowerShell se baseia. No modo de _expressão_ , argumentos **bareword** (cadeias de caracteres sem aspas) não são permitidos. Você pode ver essa diferença ao usar um caminho como um parâmetro, versus o caminho como um argumento. Você pode ler mais sobre os modos de análise no [about_Parsing](about_Parsing.md)

A assinatura do segundo método usa um nome de arquivo de destino e um valor booliano que determina se o arquivo de destino deve ser substituído, caso ele já exista.

O exemplo a seguir usa o segundo `CopyTo` método para copiar o `Final.txt` arquivo para o `C:\Bin` diretório e substituir os arquivos existentes.

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

## <a name="methods-of-scalar-objects-and-collections"></a>Métodos de coleções e objetos escalares

Os métodos de um objeto ("escalar") de um tipo específico geralmente são diferentes dos métodos de uma coleção de objetos do mesmo tipo.

Por exemplo, cada processo tem um `Kill` método, mas uma coleção de processos não tem um método Kill.

A partir do PowerShell 3,0, o PowerShell tenta evitar erros de script que resultam de diferentes métodos de coleções e objetos escalares.

Se você enviar uma coleção, mas solicitar um método que existe somente em objetos únicos ("escalares"), o PowerShell invocará o método em cada objeto na coleção.

Se o método existir nos objetos individuais e na coleção, somente o método da coleção será invocado.

Esse recurso também funciona em Propriedades de coleções e objetos escalares. Para obter mais informações, consulte [about_Properties](about_Properties.md).

### <a name="examples"></a>Exemplos

O exemplo a seguir executa o método **Kill** de objetos de processo individuais em uma coleção de objetos.

O primeiro comando inicia três instâncias do processo do bloco de notas. `Get-Process` Obtém todas as três instâncias do processo do bloco de notas e as salva na `$p` variável.

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

O comando a seguir executa o método **Kill** em todos os três processos na `$p` variável. Esse comando funciona mesmo que uma coleção de processos não tenha um `Kill` método.

```powershell
$p.Kill()
Get-Process Notepad
```

O `Get-Process` comando confirma que o `Kill` método funcionou.

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

Este exemplo é funcionalmente equivalente a usar o `Foreach-Object` cmdlet para executar o método em cada objeto na coleção.

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a>Métodos ForEach e where

A partir do PowerShell 4,0, há suporte para a filtragem de coleção usando uma sintaxe de método. Isso permite o uso de dois novos métodos ao lidar com coleções `ForEach` e `Where` .

Leia mais sobre esses métodos em [about_arrays](about_arrays.md)

## <a name="calling-a-specific-method-when-multiple-overloads-exist"></a>Chamando um método específico quando há várias sobrecargas

Considere o cenário a seguir ao chamar métodos .NET. Se um método usa um objeto, mas tem uma sobrecarga por meio de uma interface usando um tipo mais específico, o PowerShell escolhe o método que aceita o objeto, a menos que você o converta explicitamente nessa interface.

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

Neste exemplo, a sobrecarga menos específica `object` do método **bar** foi escolhida.

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

Neste exemplo, vamos converter o método para a interface **IFoo** para selecionar a sobrecarga mais específica do método **bar** .

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="using-net-methods-that-take-filesystem-paths"></a>Usando métodos .NET que usam caminhos do sistema de arquivos

O PowerShell dá suporte a vários Runspaces por processo. Cada runspace tem seu próprio _diretório atual_. Isso não é o mesmo que o diretório de trabalho do processo atual: `[System.Environment]::CurrentDirectory` .

Os métodos do .NET usam o diretório de trabalho do processo. Os cmdlets do PowerShell usam o local do runspace. Além disso, os métodos .NET só funcionam com caminhos de sistema de arquivos nativos, não com objetos de caminho do PowerShell. Para usar caminhos do PowerShell com métodos .NET, você deve resolver o caminho para um caminho nativo do sistema de arquivos antes de passá-lo para o método .NET.

## <a name="see-also"></a>Consulte Também

[about_Objects](about_Objects.md)

[about_Properties](about_Properties.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
