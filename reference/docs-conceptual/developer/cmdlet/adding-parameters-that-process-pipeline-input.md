---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar parâmetros que processam a entrada de pipeline
description: Adicionar parâmetros que processam a entrada de pipeline
ms.openlocfilehash: b150d5be93207d9c010a6d2d4de901b4526f1d79
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668347"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>Adicionar parâmetros que processam a entrada de pipeline

Uma fonte de entrada para um cmdlet é um objeto no pipeline originado de um cmdlet upstream. Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)) para que o cmdlet possa processar objetos de pipeline.

Esse cmdlet Get-Proc usa um `Name` parâmetro que aceita entrada de um objeto de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, exibe informações sobre os processos na linha de comando.

## <a name="defining-the-cmdlet-class"></a>Definindo a classe do cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet. Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get". (Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

A seguir está a definição para este Get-Proc cmdlet. Detalhes dessa definição são fornecidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a>Definindo a entrada do pipeline

Esta seção descreve como definir a entrada do pipeline para um cmdlet. Esse cmdlet Get-Proc define uma propriedade que representa o `Name` parâmetro, conforme descrito em [adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md).
(Consulte esse tópico para obter informações gerais sobre como declarar parâmetros.)

No entanto, quando um cmdlet precisa processar a entrada do pipeline, ele deve ter seus parâmetros associados aos valores de entrada pelo tempo de execução do Windows PowerShell. Para fazer isso, você deve adicionar a `ValueFromPipeline` palavra-chave ou adicionar a `ValueFromPipelineByProperty` palavra-chave à declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) . Especifique a `ValueFromPipeline` palavra-chave se o cmdlet acessar o objeto de entrada completo. Especifique `ValueFromPipelineByProperty` se o cmdlet acessa apenas uma propriedade do objeto.

Aqui está a declaração de parâmetro para o `Name` parâmetro desse Get-Proc cmdlet que aceita a entrada do pipeline.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

A declaração anterior define a `ValueFromPipeline` palavra-chave para para `true` que o tempo de execução do Windows PowerShell vincule o parâmetro ao objeto de entrada se o objeto for do mesmo tipo que o parâmetro, ou se ele puder ser forçado para o mesmo tipo. A `ValueFromPipelineByPropertyName` palavra-chave também é definida como para `true` que o tempo de execução do Windows PowerShell Verifique se há uma propriedade no objeto de entrada `Name` . Se o objeto de entrada tiver tal propriedade, o tempo de execução associará o `Name` parâmetro à `Name` Propriedade do objeto de entrada.

> [!NOTE]
> A configuração da `ValueFromPipeline` palavra-chave Attribute para um parâmetro tem precedência sobre a configuração da `ValueFromPipelineByPropertyName` palavra-chave.

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

Se o cmdlet for manipular a entrada de pipeline, ele precisará substituir os métodos de processamento de entrada apropriados. Os métodos básicos de processamento de entrada são introduzidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).

Esse cmdlet Get-Proc substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para manipular a `Name` entrada de parâmetro fornecida pelo usuário ou um script. Esse método obterá os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido. Observe que em [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), a chamada para [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) é o mecanismo de saída para enviar objetos de saída para o pipeline. O segundo parâmetro dessa chamada, `enumerateCollection` , é definido como `true` para informar ao tempo de execução do Windows PowerShell para enumerar a matriz de objetos de processo e gravar um processo por vez na linha de comando.

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
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo em C#, consulte [exemplo de GetProcessSample03](./getprocesssample03-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .net. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, teste-o executando-o na linha de comando. Por exemplo, teste o código para o cmdlet de exemplo. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- No prompt do Windows PowerShell, insira os seguintes comandos para recuperar os nomes de processo por meio do pipeline.

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  A saída a seguir aparece.

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- Insira as linhas a seguir para obter os objetos de processo que têm uma `Name` propriedade dos processos chamados "iexplore". Este exemplo usa o `Get-Process` cmdlet (fornecido pelo Windows PowerShell) como um comando upstream para recuperar os processos de "iexplore".

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  A saída a seguir aparece.

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a>Consulte Também

[Adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md)

[Criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[Referência do Windows PowerShell](../windows-powershell-reference.md)

[Amostras de cmdlet](./cmdlet-samples.md)
