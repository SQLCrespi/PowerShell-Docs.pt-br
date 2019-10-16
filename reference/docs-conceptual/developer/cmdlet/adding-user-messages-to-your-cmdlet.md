---
title: Adicionando mensagens de usuário ao cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 1e048f6ae94ac226218c18c8f8f7590a4db26226
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370065"
---
# <a name="adding-user-messages-to-your-cmdlet"></a>Adicionar mensagens de usuário para o cmdlet

Os cmdlets podem gravar vários tipos de mensagens que podem ser exibidas para o usuário pelo tempo de execução do Windows PowerShell. Essas mensagens incluem os seguintes tipos:

- Mensagens detalhadas que contêm informações gerais do usuário.

- Mensagens de depuração que contêm informações de solução de problemas.

- Mensagens de aviso que contêm uma notificação de que o cmdlet está prestes a executar uma operação que pode ter resultados inesperados.

- Mensagens de relatório de progresso que contêm informações sobre a quantidade de trabalho que o cmdlet concluiu ao executar uma operação que leva muito tempo.

Não há limites para o número de mensagens que seu cmdlet pode gravar ou o tipo de mensagens que seu cmdlet grava. Cada mensagem é escrita fazendo uma chamada específica de dentro do método de processamento de entrada do seu cmdlet.

## <a name="defining-the-cmdlet"></a>Definindo o cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet. Qualquer tipo de cmdlet pode gravar notificações de usuário de seus métodos de processamento de entrada; Portanto, em geral, você pode nomear esse cmdlet usando qualquer verbo que indique quais modificações do sistema o cmdlet executa. Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

O cmdlet Stop-proc foi projetado para modificar o sistema; Portanto, a Declaração [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) para a classe .NET deve incluir a palavra-chave de atributo `SupportsShouldProcess` e ser definida como `true`.

O código a seguir é a definição para essa classe de cmdlet Stop-proc. Para obter mais informações sobre essa definição, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Definindo parâmetros para a modificação do sistema

O cmdlet Stop-proc define três parâmetros: `Name`, `Force` e `PassThru`. Para obter mais informações sobre como definir esses parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

Aqui está a declaração de parâmetro para o cmdlet Stop-proc.

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

O cmdlet deve substituir um método de processamento de entrada, geralmente ele será [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). Esse cmdlet Stop-proc substitui o método de processamento de entrada [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . Nessa implementação do cmdlet Stop-proc, são feitas chamadas para gravar mensagens detalhadas, depurar mensagens e mensagens de aviso.

> [!NOTE]
> Para obter mais informações sobre como esse método chama os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="writing-a-verbose-message"></a>Escrevendo uma mensagem detalhada

O método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) é usado para gravar informações gerais em nível de usuário que não estão relacionadas a condições de erro específicas. O administrador do sistema pode usar essas informações para continuar processando outros comandos. Além disso, todas as informações escritas usando esse método devem ser localizadas conforme necessário.

O código a seguir desse cmdlet Stop-proc mostra duas chamadas para o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a>Gravando uma mensagem de depuração

O método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) é usado para gravar mensagens de depuração que podem ser usadas para solucionar problemas da operação do cmdlet. A chamada é feita de um método de processamento de entrada.

> [!NOTE]
> O Windows PowerShell também define um parâmetro `Debug` que apresenta informações detalhadas e de depuração. Se o cmdlet der suporte a esse parâmetro, ele não precisará chamar [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) no mesmo código que chama [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).

As duas seções de código a seguir do cmdlet Stop-proc de exemplo mostram chamadas para o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

Essa mensagem de depuração é gravada imediatamente antes de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) ser chamado.

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

Essa mensagem de depuração é gravada imediatamente antes de [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) ser chamado.

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

O Windows PowerShell roteia automaticamente quaisquer chamadas [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) para a infraestrutura de rastreamento e os cmdlets. Isso permite que as chamadas de método sejam rastreadas para o aplicativo de hospedagem, um arquivo ou um depurador sem a necessidade de fazer qualquer trabalho de desenvolvimento extra dentro do cmdlet. A seguinte entrada de linha de comando implementa uma operação de rastreamento.

**PS > Trace-expressão Stop-proc-File proc. log-Command Stop-proc bloco de notas**

## <a name="writing-a-warning-message"></a>Gravando uma mensagem de aviso

O método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) é usado para gravar um aviso quando o cmdlet está prestes a executar uma operação que pode ter um resultado inesperado, por exemplo, substituindo um arquivo somente leitura.

O código a seguir do cmdlet Stop-proc de exemplo mostra a chamada para o método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a>Gravando uma mensagem de progresso

O [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) é usado para gravar mensagens de progresso quando as operações de cmdlet demoram um longo período de tempo para serem concluídas. Uma chamada para [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passa um objeto [System. Management. Automation. ProgressRecord](/dotnet/api/System.Management.Automation.ProgressRecord) que é enviado ao aplicativo de hospedagem para renderização para o usuário.

> [!NOTE]
> Este cmdlet Stop-proc não inclui uma chamada para o método [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

O código a seguir é um exemplo de uma mensagem de progresso escrita por um cmdlet que está tentando copiar um item.

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a>Exemplo de código

Para obter o C# código de exemplo completo, consulte [exemplo de StopProcessSample02](./stopprocesssample02-sample.md).

## <a name="define-object-types-and-formatting"></a>Definir tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .NET. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando. Vamos testar o cmdlet Stop-proc de exemplo. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- A seguinte entrada de linha de comando usa Stop-proc para interromper o processo chamado "NOTEPAD", fornecer notificações detalhadas e imprimir informações de depuração.

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

A saída a seguir é exibida.

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a>Consulte Também

[Criar um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)

[Como criar um cmdlet do Windows PowerShell](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[SDK do Windows PowerShell](../windows-powershell-reference.md)
