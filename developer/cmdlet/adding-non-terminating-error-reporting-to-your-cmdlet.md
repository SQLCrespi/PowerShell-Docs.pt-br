---
title: Adicionando relatórios de erros não conclusivos ao cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: a4426abec96cd922360aeef8c157b4e9f41a15b9
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322865"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a>Adicionar relatórios de erros de não encerramento ao seu cmdlet

Os cmdlets podem relatar erros não conclusivos chamando o método [System. Management. Automation. cmdlet. WriteError][] e ainda continuam a operar no objeto de entrada atual ou em outros objetos de pipeline de entrada.
Esta seção explica como criar um cmdlet que relata erros não conclusivos de seus métodos de processamento de entrada.

Para erros de não encerramento (bem como erros de encerramento), o cmdlet deve passar um objeto [System. Management. Automation. ErrorRecord][] identificando o erro.
Cada registro de erro é identificado por uma cadeia de caracteres exclusiva chamada "identificador de erro".
Além do identificador, a categoria de cada erro é especificada por constantes definidas por uma enumeração [System. Management. Automation. ErrorCategory][] .
O usuário pode exibir erros com base em sua categoria definindo a `$ErrorView` variável como "CategoryView".

Para obter mais informações sobre registros de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).

## <a name="defining-the-cmdlet"></a>Definindo o cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.
Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get".
(Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](approved-verbs-for-windows-powershell-commands.md).

A seguir está a definição para esse cmdlet Get-proc.
Detalhes dessa definição são fornecidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a>Definindo parâmetros

Se necessário, o cmdlet deve definir parâmetros para processar a entrada.
Esse cmdlet Get-proc define um parâmetro de **nome** conforme descrito em [adicionando parâmetros que processam a entrada de linha de comando](adding-parameters-that-process-command-line-input.md).

Aqui está a declaração de parâmetro para o parâmetro **Name** deste cmdlet Get-proc.

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

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

## <a name="overriding-input-processing-methods"></a>Substituindo métodos de processamento de entrada

Todos os cmdlets devem substituir pelo menos um dos métodos de processamento de entrada fornecidos pela classe [System. Management. Automation. cmdlet][] .
Esses métodos são discutidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).

> [!NOTE]
> Seu cmdlet deve tratar cada registro da maneira mais independente possível.

Esse cmdlet Get-proc substitui o método [System. Management. Automation. cmdlet. ProcessRecord][] para manipular o parâmetro **Name** para a entrada fornecida pelo usuário ou um script.
Esse método obterá os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido.
Os detalhes dessa substituição são fornecidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).

### <a name="things-to-remember-when-reporting-errors"></a>Itens a serem lembrados ao relatar erros

O objeto [System. Management. Automation. ErrorRecord][] que o cmdlet passa ao gravar um erro requer uma exceção em seu núcleo.
Siga as diretrizes do .NET ao determinar a exceção a ser usada.
Basicamente, se o erro for semanticamente o mesmo que uma exceção existente, o cmdlet deverá usar ou derivar dessa exceção.
Caso contrário, ele deve derivar uma nova hierarquia de exceção ou exceção diretamente da classe [System. Exception][] .

Ao criar identificadores de erro (acessados por meio da propriedade FullyQualifiedErrorId da classe ErrorRecord), tenha em mente o seguinte.

- Use cadeias de caracteres destinadas a fins de diagnóstico para que, ao inspecionar o identificador totalmente qualificado, você possa determinar qual é o erro e de onde veio o erro.

- Um identificador de erro totalmente qualificado bem formado pode ser o seguinte.

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

Observe que, no exemplo anterior, o identificador de erro (o primeiro token) designa o que é o erro e a parte restante indica de onde veio o erro.

- Para cenários mais complexos, o identificador de erro pode ser um token separado por ponto que pode ser analisado na inspeção.
  Isso permite uma ramificação demais nas partes do identificador de erro, bem como o identificador de erro e a categoria de erro.

O cmdlet deve atribuir identificadores de erro específicos a caminhos de código diferentes.
Tenha em mente as seguintes informações para a atribuição de identificadores de erro:

- Um identificador de erro deve permanecer constante ao longo do ciclo de vida do cmdlet.
  Não altere a semântica de um identificador de erro entre as versões do cmdlet.

- Use o texto para um identificador de erro que tersely corresponde ao erro que está sendo relatado.
  Não use espaço em branco ou pontuação.

- Faça com que o cmdlet gere apenas identificadores de erro que podem ser reproduzidos.
  Por exemplo, ele não deve gerar um identificador que inclua um identificador de processo.
  Os identificadores de erro são úteis para um usuário somente quando eles correspondem a identificadores que são vistos por outros usuários que estão tendo o mesmo problema.

As exceções sem tratamento não são detectadas pelo PowerShell nas seguintes condições:

- Se um cmdlet criar um novo thread e o código em execução nesse thread gerar uma exceção sem tratamento, o PowerShell não detectará o erro e encerrará o processo.

- Se um objeto tiver código em seu destruidor ou métodos Dispose que causam uma exceção sem tratamento, o PowerShell não detectará o erro e encerrará o processo.

## <a name="reporting-nonterminating-errors"></a>Relatando erros de não encerramento

Qualquer um dos métodos de processamento de entrada pode relatar um erro de não encerramento para o fluxo de saída usando o método [System. Management. Automation. cmdlet. WriteError][] .

Aqui está um exemplo de código desse cmdlet Get-proc que ilustra a chamada para [System. Management. Automation. cmdlet. WriteError][] de dentro da substituição do método [System. Management. Automation. cmdlet. ProcessRecord][] .
Nesse caso, a chamada será feita se o cmdlet não encontrar um processo para um identificador de processo especificado.

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a>Coisas a serem lembradas sobre a gravação de erros de não encerramento

Para um erro de não encerramento, o cmdlet deve gerar um identificador de erro específico para cada objeto de entrada específico.

Geralmente, um cmdlet precisa modificar a ação do PowerShell produzida por um erro de não encerramento.
Isso pode fazer isso definindo os `ErrorAction` parâmetros e. `ErrorVariable`
Se definir o `ErrorAction` parâmetro, o cmdlet apresentará as opções de usuário [System. Management. Automation. preferência][], você também pode influenciar diretamente a ação definindo `$ErrorActionPreference` a variável.

O cmdlet pode salvar erros não conclusivos em uma variável usando `ErrorVariable` o parâmetro, que não é afetado pela configuração de `ErrorAction`.
As falhas podem ser acrescentadas a uma variável de erro existente adicionando um sinal de adição (+) à frente do nome da variável.

## <a name="code-sample"></a>Exemplo de código

Para obter o C# código de exemplo completo, consulte [exemplo de GetProcessSample04](./getprocesssample04-sample.md).

## <a name="define-object-types-and-formatting"></a>Definir tipos de objeto e formatação

O PowerShell passa informações entre os cmdlets usando objetos .NET.
Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.
Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell.
Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o PowerShell, você poderá testá-lo executando-o na linha de comando.
Vamos testar o cmdlet Get-proc de exemplo para ver se ele relata um erro:

- Inicie o PowerShell e use o cmdlet Get-proc para recuperar os processos chamados "TEST".

    ```powershell
    PS> get-proc -name test
    ```

A saída a seguir é exibida.

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a>Consulte também

[Adicionando parâmetros que processam a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md)

[Adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md)

[Criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)

[Estendendo tipos de objeto e formatação](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Como registrar cmdlets, provedores e aplicativos host](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Referência do Windows PowerShell](../windows-powershell-reference.md)

[Exemplos de cmdlet](./cmdlet-samples.md)

[System. Exception]: /dotnet/api/System.Exception
[System. Management. Automation. preferência]: /dotnet/api/System.Management.Automation.ActionPreference
[System. Management. Automation. cmdlet. ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System. Management. Automation. cmdlet. WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Management. Automation. cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System. Management. Automation. ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System. Management. Automation. ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
