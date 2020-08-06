---
title: Adicionando parâmetros que processam a entrada de linha de comando | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.openlocfilehash: 6ccc873d9c6b93546b3dae8c0d2e406763fdfb8a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784564"
---
# <a name="adding-parameters-that-process-command-line-input"></a>Adicionar parâmetros que processam a entrada de linha de comando

Uma fonte de entrada para um cmdlet é a linha de comando. Este tópico descreve como adicionar um parâmetro ao `Get-Proc` cmdlet (que é descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)) para que o cmdlet possa processar a entrada do computador local com base em objetos explícitos passados para o cmdlet. O `Get-Proc` cmdlet descrito aqui recupera os processos com base em seus nomes e, em seguida, exibe informações sobre os processos em um prompt de comando.

## <a name="defining-the-cmdlet-class"></a>Definindo a classe do cmdlet

A primeira etapa na criação de cmdlet é a nomenclatura de cmdlets e a declaração da classe .NET Framework que implementa o cmdlet. Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get". (Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

Aqui está a declaração de classe para o `Get-Proc` cmdlet. Detalhes sobre essa definição são fornecidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a>Declarando parâmetros

Um parâmetro de cmdlet permite que o usuário forneça entrada para o cmdlet. No exemplo a seguir, `Get-Proc` e `Get-Member` são os nomes de cmdlets de pipeline e `MemberType` é um parâmetro para o `Get-Member` cmdlet. O parâmetro tem o argumento "Property".

**PS> Get-proc; `get-member`-Propriedade MemberType**

Para declarar parâmetros para um cmdlet, você deve primeiro definir as propriedades que representam os parâmetros. No `Get-Proc` cmdlet, o único parâmetro é `Name` , que, nesse caso, representa o nome do objeto de processo de .NET Framework a ser recuperado. Portanto, a classe cmdlet define uma propriedade do tipo cadeia de caracteres para aceitar uma matriz de nomes.

Aqui está a declaração de parâmetro para o `Name` parâmetro do `Get-Proc` cmdlet.

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

Para informar ao tempo de execução do Windows PowerShell que essa propriedade é o `Name` parâmetro, um atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) é adicionado à definição de propriedade. A sintaxe básica para declarar esse atributo é `[Parameter()]` .

> [!NOTE]
> Um parâmetro deve ser explicitamente marcado como público. Parâmetros que não são marcados como padrão público para interno e não são encontrados pelo tempo de execução do Windows PowerShell.

Esse cmdlet usa uma matriz de cadeias de caracteres para o `Name` parâmetro. Se possível, o cmdlet também deve definir um parâmetro como uma matriz, pois isso permite que o cmdlet aceite mais de um item.

#### <a name="things-to-remember-about-parameter-definitions"></a>Coisas a serem lembradas sobre definições de parâmetros

- Os nomes de parâmetro e tipos de dados predefinidos do Windows PowerShell devem ser reutilizados o máximo possível para garantir que o cmdlet seja compatível com os cmdlets do Windows PowerShell. Por exemplo, se todos os cmdlets usarem o nome de parâmetro predefinido `Id` para identificar um recurso, o usuário entenderá facilmente o significado do parâmetro, independentemente do cmdlet que estiver usando. Basicamente, os nomes de parâmetro seguem as mesmas regras que as usadas para nomes de variáveis no Common Language Runtime (CLR). Para obter mais informações sobre a nomenclatura de parâmetros, consulte [nomes de parâmetro de cmdlet](/previous-versions/ms714468(v=vs.85)).

- O Windows PowerShell reserva alguns nomes de parâmetro para fornecer uma experiência de usuário consistente. Não use esses nomes de parâmetro: `WhatIf` ,,,,, `Confirm` `Verbose` `Debug` `Warn` `ErrorAction` , `ErrorVariable` , `OutVariable` e `OutBuffer` . Além disso, os aliases a seguir para esses nomes de parâmetro são reservados:,,,, `vb` `db` `ea` `ev` `ov` e `ob` .

- `Name`é um nome de parâmetro simples e comum, recomendado para uso em seus cmdlets. É melhor escolher um nome de parâmetro como este de um nome complexo que seja exclusivo para um cmdlet específico e difícil de lembrar.

- Os parâmetros não diferenciam maiúsculas de minúsculas no Windows PowerShell, embora por padrão o Shell preserve o caso. Diferenciar maiúsculas de minúsculas dos argumentos depende da operação do cmdlet. Os argumentos são passados para um parâmetro conforme especificado na linha de comando.

- Para obter exemplos de outras declarações de parâmetro, consulte [parâmetros de cmdlet](./cmdlet-parameters.md).

## <a name="declaring-parameters-as-positional-or-named"></a>Declarando parâmetros como posicionais ou nomeados

Um cmdlet deve definir cada parâmetro como um parâmetro posicional ou nomeado. Os dois tipos de parâmetros aceitam argumentos únicos, vários argumentos separados por vírgulas e configurações boolianas. Um parâmetro booliano, também chamado de *switch*, trata apenas das configurações boolianas. A opção é usada para determinar a presença do parâmetro. O padrão recomendado é `false` .

O cmdlet de exemplo `Get-Proc` define o `Name` parâmetro como um parâmetro posicional com Position
0. Isso significa que o primeiro argumento que o usuário insere na linha de comando é inserido automaticamente para esse parâmetro. Se você quiser definir um parâmetro nomeado, para o qual o usuário deve especificar o nome do parâmetro na linha de comando, deixe a `Position` palavra-chave fora da declaração do atributo.

> [!NOTE]
> A menos que os parâmetros devam ser nomeados, recomendamos que você crie os parâmetros mais usados posicionais para que os usuários não precisem digitar o nome do parâmetro.

## <a name="declaring-parameters-as-mandatory-or-optional"></a>Declarando parâmetros como obrigatórios ou opcionais

Um cmdlet deve definir cada parâmetro como um parâmetro opcional ou obrigatório. No cmdlet de exemplo `Get-Proc` , o `Name` parâmetro é definido como opcional porque a `Mandatory` palavra-chave não está definida na declaração de atributo.

## <a name="supporting-parameter-validation"></a>Validação de parâmetro de suporte

O cmdlet de exemplo `Get-Proc` adiciona um atributo de validação de entrada, [System. Management. Automation. Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), ao `Name` parâmetro para habilitar a validação de que a entrada não é `null` nem vazia. Esse atributo é um dos vários atributos de validação fornecidos pelo Windows PowerShell. Para obter exemplos de outros atributos de validação, consulte [validando a entrada de parâmetro](./validating-parameter-input.md).

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

Se o cmdlet for manipular a entrada de linha de comando, ele deverá substituir os métodos de processamento de entrada apropriados. Os métodos básicos de processamento de entrada são introduzidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).

O `Get-Proc` cmdlet substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para manipular a `Name` entrada de parâmetro fornecida pelo usuário ou um script. Esse método obtém os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido. Observe que em [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), a chamada para [System. Management. Automation. cmdlet. WriteObject% 28System. Object% 2CSystem. booliano %29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) é o mecanismo de saída para enviar objetos de saída para o pipeline. O segundo parâmetro dessa chamada, `enumerateCollection` , é definido como `true` para informar o tempo de execução do Windows PowerShell para enumerar a matriz de saída de objetos de processo e gravar um processo por vez na linha de comando.

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
    // Write the processes to the pipeline making them available
    // to the next cmdlet. The second argument of this call tells
    // PowerShell to enumerate the array, and send one process at a
    // time to the pipeline.
    WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo em C#, consulte [exemplo de GetProcessSample02](./getprocesssample02-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando .NET Framework objetos. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou um cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions/ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell usando um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet estiver registrado no Windows PowerShell, você poderá testá-lo executando-o na linha de comando. Aqui estão duas maneiras de testar o código para o cmdlet de exemplo. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- No prompt do Windows PowerShell, use o comando a seguir para listar o processo do Internet Explorer, denominado "iexplore".

  ```powershell
  get-proc -name iexplore
  ```

  A saída a seguir aparece.

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- Para listar os processos do Internet Explorer, Outlook e bloco de notas denominados "iexplore", "OUTLOOK," e "bloco de notas", use o comando a seguir. Se houver vários processos, todos eles serão exibidos.

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  A saída a seguir aparece.

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a>Consulte Também

[Adicionar parâmetros que processam a entrada de pipeline](./adding-parameters-that-process-pipeline-input.md)

[Criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)

[Estendendo tipos de objeto e formatação](/previous-versions/ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[Referência do Windows PowerShell](../windows-powershell-reference.md)

[Amostras de cmdlet](./cmdlet-samples.md)
