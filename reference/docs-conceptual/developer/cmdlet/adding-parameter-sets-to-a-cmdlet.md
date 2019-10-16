---
title: Adicionando conjuntos de parâmetros a um cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: 59db96cf03ff7086e8c89fb45bc96fd805078ac8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364585"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a>Adicionar conjuntos de parâmetros como um cmdlet

## <a name="things-to-know-about-parameter-sets"></a>Coisas a saber sobre conjuntos de parâmetros

O Windows PowerShell define um parâmetro definido como um grupo de parâmetros que operam juntos. Ao agrupar os parâmetros de um cmdlet, você pode criar um único cmdlet que pode alterar sua funcionalidade com base em qual grupo de parâmetros o usuário especifica.

Um exemplo de um cmdlet que usa dois conjuntos de parâmetros para definir funcionalidades diferentes é o cmdlet `Get-EventLog` fornecido pelo Windows PowerShell. Esse cmdlet retorna informações diferentes quando o usuário especifica o parâmetro `List` ou `LogName`. Se o parâmetro `LogName` for especificado, o cmdlet retornará informações sobre os eventos em um determinado log de eventos. Se o parâmetro `List` for especificado, o cmdlet retornará informações sobre os arquivos de log em si (não as informações de evento que eles contêm). Nesse caso, os parâmetros `List` e `LogName` identificam dois conjuntos de parâmetros separados.

Duas coisas importantes a serem lembradas sobre conjuntos de parâmetros é que o tempo de execução do Windows PowerShell usa apenas um conjunto de parâmetros para uma entrada específica e que cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo para esse conjunto de parâmetros.

Para ilustrar esse último ponto, esse cmdlet Stop-proc usa três conjuntos de parâmetros: `ProcessName`, `ProcessId` e `InputObject`. Cada um desses conjuntos de parâmetros tem um parâmetro que não está nos outros conjuntos de parâmetros. Os conjuntos de parâmetros podem compartilhar outros parâmetros, mas o cmdlet usa os parâmetros exclusivos `ProcessName`, `ProcessId` e `InputObject` para identificar qual conjunto de parâmetros deve ser usado pelo tempo de execução do Windows PowerShell.

## <a name="declaring-the-cmdlet-class"></a>Declarando a classe cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet. Para esse cmdlet, o verbo de ciclo de vida "Stop" é usado porque o cmdlet para os processos do sistema. O nome do substantivo "proc" é usado porque o cmdlet funciona em processos. Na declaração abaixo, observe que o verbo do cmdlet e o nome do substantivo são refletidos no nome da classe do cmdlet.

> [!NOTE]
> Para obter mais informações sobre nomes de verbo de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

O código a seguir é a definição de classe para esse cmdlet Stop-proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a>Declarando os parâmetros do cmdlet

Esse cmdlet define três parâmetros necessários como entrada para o cmdlet (esses parâmetros também definem os conjuntos de parâmetros), bem como um parâmetro `Force` que gerencia o que o cmdlet faz e um parâmetro `PassThru` que determina se o cmdlet envia um objeto de saída por meio do pipeline. Por padrão, esse cmdlet não passa um objeto por meio do pipeline. Para obter mais informações sobre esses dois últimos parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

### <a name="declaring-the-name-parameter"></a>Declarando o parâmetro Name

Esse parâmetro de entrada permite que o usuário especifique os nomes dos processos a serem interrompidos. Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o conjunto de parâmetros `ProcessName` para esse parâmetro.

[!code-csharp[StopProcessSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

Observe também que o alias "ProcessName" é fornecido a esse parâmetro.

### <a name="declaring-the-id-parameter"></a>Declarando o parâmetro ID

Esse parâmetro de entrada permite que o usuário especifique os identificadores dos processos a serem interrompidos. Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o conjunto de parâmetros `ProcessId`.

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

Observe também que o alias "ProcessId" é fornecido para esse parâmetro.

### <a name="declaring-the-inputobject-parameter"></a>Declarando o parâmetro InputObject

Esse parâmetro de entrada permite que o usuário especifique um objeto de entrada que contém informações sobre os processos a serem interrompidos. Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o conjunto de parâmetros `InputObject` para esse parâmetro.

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

Observe também que esse parâmetro não tem nenhum alias.

### <a name="declaring-parameters-in-multiple-parameter-sets"></a>Declarando parâmetros em vários conjuntos de parâmetros

Embora seja necessário haver um parâmetro exclusivo para cada conjunto de parâmetros, os parâmetros podem pertencer a mais de um conjunto de parâmetros. Nesses casos, forneça ao parâmetro compartilhado uma declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) para cada conjunto ao qual o parâmetro pertence. Se um parâmetro estiver em todos os conjuntos de parâmetros, você só precisará declarar o atributo de parâmetro uma vez e não precisará especificar o nome do conjunto de parâmetros.

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

Cada cmdlet deve substituir um método de processamento de entrada, com mais frequência esse será o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . Nesse cmdlet, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído para que o cmdlet possa processar qualquer número de processos. Ele contém uma instrução SELECT que chama um método diferente com base no conjunto de parâmetros especificado pelo usuário.

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

Os métodos auxiliares chamados pela instrução SELECT não são descritos aqui, mas você pode ver sua implementação no exemplo de código completo na próxima seção.

## <a name="code-sample"></a>Exemplo de código

Para obter o C# código de exemplo completo, consulte [exemplo de StopProcessSample04](./stopprocesssample04-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .NET. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, teste-o executando-o na linha de comando. Aqui estão alguns testes que mostram como os parâmetros `ProcessId` e `InputObject` podem ser usados para testar seus conjuntos de parâmetros para interromper um processo.

- Com o Windows PowerShell iniciado, execute o cmdlet Stop-proc com o parâmetro `ProcessId` definido para interromper um processo com base em seu identificador. Nesse caso, o cmdlet está usando o parâmetro `ProcessId` definido para parar o processo.

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Com o Windows PowerShell iniciado, execute o cmdlet Stop-proc com o parâmetro `InputObject` definido para parar os processos no objeto do bloco de notas recuperado pelo comando `Get-Process`.

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>Consulte Também

[Criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)

[Como criar um cmdlet do Windows PowerShell](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[SDK do Windows PowerShell](../windows-powershell-reference.md)
