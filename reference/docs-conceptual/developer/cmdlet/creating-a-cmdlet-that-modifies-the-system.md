---
ms.date: 09/13/2016
ms.topic: reference
title: Criar um cmdlet que modifica o sistema
description: Criar um cmdlet que modifica o sistema
ms.openlocfilehash: 757f2c97bb4b5dcf2fb633cd35fe52bc5f6c5cf9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355537"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>Criar um cmdlet que modifica o sistema

Às vezes, um cmdlet deve modificar o estado de execução do sistema, não apenas o estado do tempo de execução do Windows PowerShell. Nesses casos, o cmdlet deve permitir que o usuário tenha a chance de confirmar se deseja ou não fazer a alteração.

Para dar suporte à confirmação, um cmdlet deve fazer duas coisas.

- Declare que o cmdlet dá suporte à confirmação quando você especifica o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) definindo a palavra-chave SupportsShouldProcess como `true` .

- Chame [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) durante a execução do cmdlet (conforme mostrado no exemplo a seguir).

Ao dar suporte à confirmação, um cmdlet expõe os `Confirm` `WhatIf` parâmetros e fornecidos pelo Windows PowerShell e também atende às diretrizes de desenvolvimento para cmdlets (para obter mais informações sobre diretrizes de desenvolvimento de cmdlets, consulte [diretrizes de desenvolvimento de cmdlets](./cmdlet-development-guidelines.md)).

## <a name="changing-the-system"></a>Alterando o sistema

O ato de "alterar o sistema" refere-se a qualquer cmdlet que potencialmente altere o estado do sistema fora do Windows PowerShell. Por exemplo, parar um processo, habilitar ou desabilitar uma conta de usuário ou adicionar uma linha a uma tabela de banco de dados são todas as alterações no sistema que devem ser confirmadas.
Por outro lado, as operações que lêem dados ou estabelecem conexões transitórias não alteram o sistema e geralmente não exigem confirmação. A confirmação também não é necessária para ações cujo efeito está limitado a dentro do tempo de execução do Windows PowerShell, como `set-variable` . Os cmdlets que podem ou não fazer uma alteração persistente devem declarar `SupportsShouldProcess` e chamar [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) somente se eles estiverem prestes a fazer uma alteração persistente.

> [!NOTE]
> A confirmação de ShouldProcess aplica-se somente a cmdlets. Se um comando ou script modificar o estado de execução de um sistema chamando diretamente métodos ou propriedades do .NET ou chamando aplicativos fora do Windows PowerShell, essa forma de confirmação não estará disponível.

## <a name="the-stopproc-cmdlet"></a>O cmdlet StopProc

Este tópico descreve um Stop-Proc cmdlet que tenta interromper processos recuperados usando o cmdlet Get-Proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Definindo o cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet. Como você está escrevendo um cmdlet para alterar o sistema, ele deve ser nomeado de acordo. Esse cmdlet interrompe os processos do sistema, portanto, o nome do verbo escolhido aqui é "Stop", definido pela classe [System. Management. Automation. Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , com o substantivo "proc" para indicar que o cmdlet interrompe os processos. Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

A seguir está a definição de classe para este Stop-Proc cmdlet.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

Lembre-se de que na Declaração [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , a `SupportsShouldProcess` palavra-chave Attribute é definida como `true` para permitir que o cmdlet faça chamadas para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).
Sem essa palavra-chave definida, os `Confirm` `WhatIf` parâmetros e não estarão disponíveis para o usuário.

### <a name="extremely-destructive-actions"></a>Ações extremamente destrutivas

Algumas operações são extremamente destrutivas, como reformatar uma partição de disco rígido ativa. Nesses casos, o cmdlet deve ser definido `ConfirmImpact`  =  `ConfirmImpact.High` ao declarar o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) . Essa configuração força o cmdlet a solicitar a confirmação do usuário mesmo quando o usuário não tiver especificado o `Confirm` parâmetro. No entanto, os desenvolvedores de cmdlets devem evitar o superuso `ConfirmImpact` de operações que são potencialmente destrutivos, como excluir uma conta de usuário. Lembre-se de que se `ConfirmImpact` é definido como [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **High**.

Da mesma forma, é improvável que algumas operações sejam destrutivas, embora elas, na teoria, modifiquem o estado de execução de um sistema fora do Windows PowerShell. Esses cmdlets podem `ConfirmImpact` ser definidos como [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact).
Isso irá ignorar as solicitações de confirmação em que o usuário solicitou a confirmação somente de operações de impacto médio e de alto impacto.

## <a name="defining-parameters-for-system-modification"></a>Definindo parâmetros para a modificação do sistema

Esta seção descreve como definir os parâmetros de cmdlet, incluindo os que são necessários para dar suporte à modificação do sistema. Consulte [adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md) se você precisar de informações gerais sobre como definir parâmetros.

O cmdlet Stop-Proc define três parâmetros: `Name` , `Force` e `PassThru` .

O `Name` parâmetro corresponde à `Name` Propriedade do objeto de entrada do processo. Lembre-se de que o `Name` parâmetro neste exemplo é obrigatório, pois o cmdlet falhará se não tiver um processo nomeado para parar.

O `Force` parâmetro permite que o usuário substitua as chamadas para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).
Na verdade, qualquer cmdlet que chama [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) deve ter um `Force` parâmetro para que `Force` , quando for especificado, o cmdlet ignore a chamada para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) e continue com a operação. Lembre-se de que isso não afeta as chamadas para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).

O `PassThru` parâmetro permite que o usuário indique se o cmdlet passa um objeto de saída por meio do pipeline, nesse caso, depois que um processo é interrompido. Lembre-se de que esse parâmetro está vinculado ao próprio cmdlet, em vez de a uma propriedade do objeto de entrada.

Aqui está a declaração de parâmetro para o cmdlet Stop-Proc.

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

O cmdlet deve substituir um método de processamento de entrada. O código a seguir ilustra a substituição de [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) usada no Cmdlet de Stop-Proc de exemplo. Para cada nome de processo solicitado, esse método garante que o processo não seja um processo especial, tente interromper o processo e, em seguida, enviará um objeto de saída se o `PassThru` parâmetro for especificado.

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a>Chamando o método ShouldProcess

O método de processamento de entrada do seu cmdlet deve chamar o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) para confirmar a execução de uma operação antes que uma alteração (por exemplo, exclusão de arquivos) seja feita no estado de execução do sistema. Isso permite que o tempo de execução do Windows PowerShell forneça o comportamento correto de "WhatIf" e "confirmar" no Shell.

> [!NOTE]
> Se um cmdlet indicar que ele dá suporte deve processar e falhar ao fazer a chamada de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , o usuário poderá modificar o sistema inesperadamente.

A chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell levando em conta quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido ao usuário.

O exemplo a seguir mostra a chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) no cmdlet de Stop-Proc de exemplo.

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>Chamando o método ShouldContinue

A chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) envia uma mensagem secundária para o usuário. Essa chamada é feita depois que a chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) retorna `true` e se o `Force` parâmetro não foi definido como `true` . Em seguida, o usuário pode fornecer comentários para dizer se a operação deve continuar. Seu cmdlet chama [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema ou quando você deseja fornecer opções Sim para tudo e não para o usuário.

O exemplo a seguir mostra a chamada para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) no cmdlet de Stop-Proc de exemplo.

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a>Parando o processamento de entrada

O método de processamento de entrada de um cmdlet que faz modificações no sistema deve fornecer uma maneira de parar o processamento da entrada. No caso desse Stop-Proc cmdlet, é feita uma chamada do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para o método [System. Diagnostics. Process. Kill *](/dotnet/api/System.Diagnostics.Process.Kill) . Como o `PassThru` parâmetro é definido como `true` , [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) também chama [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) para enviar o objeto de processo para o pipeline.

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo em C#, consulte [exemplo de StopProcessSample01](./stopprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .net. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando. Aqui estão vários testes que testam o cmdlet Stop-Proc. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Inicie o Windows PowerShell e use o cmdlet Stop-Proc para parar o processamento, conforme mostrado abaixo. Como o cmdlet especifica o `Name` parâmetro como obrigatório, o cmdlet consulta o parâmetro.

    ```powershell
    PS> stop-proc
    ```

    A saída a seguir aparece.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- Agora, vamos usar o cmdlet para parar o processo chamado "NOTEPAD". O cmdlet solicita que você confirme a ação.

    ```powershell
    PS> stop-proc -Name notepad
    ```

    A saída a seguir aparece.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Use Stop-Proc conforme mostrado para interromper o processo crítico chamado "WINLOGON". Você será solicitado e avisado sobre a execução dessa ação, pois isso fará com que o sistema operacional seja reinicializado.

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    A saída a seguir aparece.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- Agora, vamos tentar parar o processo WINLOGON sem receber um aviso. Lembre-se de que essa entrada de comando usa o `Force` parâmetro para substituir o aviso.

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    A saída a seguir aparece.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>Consulte Também

[Adicionando parâmetros que processam Command-Line entrada](./adding-parameters-that-process-command-line-input.md)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[SDK do Windows PowerShell](../windows-powershell-reference.md)

[Amostras de cmdlet](./cmdlet-samples.md)
