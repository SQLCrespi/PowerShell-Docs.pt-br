---
title: Criando um cmdlet que modifica o sistema | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- should process [PowerShell Programmer's Guide]
- should continue [PowerShell Programmer's Guide]
- user feedback [PowerShell Programmer's Guide]
- confirm impact [PowerShell Programmer's Guide]
ms.assetid: 59be4120-1700-4d92-a308-ef4a32ccf11a
caps.latest.revision: 8
ms.openlocfilehash: 8a65915b88a04e36e773853b903528a65fe11e99
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365755"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="ae30f-102">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="ae30f-102">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="ae30f-103">Às vezes, um cmdlet deve modificar o estado de execução do sistema, não apenas o estado do tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae30f-103">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="ae30f-104">Nesses casos, o cmdlet deve permitir que o usuário tenha a chance de confirmar se deseja ou não fazer a alteração.</span><span class="sxs-lookup"><span data-stu-id="ae30f-104">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="ae30f-105">Para dar suporte à confirmação, um cmdlet deve fazer duas coisas.</span><span class="sxs-lookup"><span data-stu-id="ae30f-105">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="ae30f-106">Declare que o cmdlet dá suporte à confirmação quando você especifica o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) definindo a palavra-chave SupportsShouldProcess como `true`.</span><span class="sxs-lookup"><span data-stu-id="ae30f-106">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="ae30f-107">Chame [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) durante a execução do cmdlet (conforme mostrado no exemplo a seguir).</span><span class="sxs-lookup"><span data-stu-id="ae30f-107">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="ae30f-108">Ao dar suporte à confirmação, um cmdlet expõe os parâmetros `Confirm` e `WhatIf` fornecidos pelo Windows PowerShell e também atende às diretrizes de desenvolvimento para cmdlets (para obter mais informações sobre diretrizes de desenvolvimento de cmdlets, consulte [diretrizes de desenvolvimento de cmdlets](./cmdlet-development-guidelines.md)).</span><span class="sxs-lookup"><span data-stu-id="ae30f-108">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="ae30f-109">Alterando o sistema</span><span class="sxs-lookup"><span data-stu-id="ae30f-109">Changing the System</span></span>

<span data-ttu-id="ae30f-110">O ato de "alterar o sistema" refere-se a qualquer cmdlet que potencialmente altere o estado do sistema fora do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae30f-110">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="ae30f-111">Por exemplo, parar um processo, habilitar ou desabilitar uma conta de usuário ou adicionar uma linha a uma tabela de banco de dados são todas as alterações no sistema que devem ser confirmadas.</span><span class="sxs-lookup"><span data-stu-id="ae30f-111">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span> <span data-ttu-id="ae30f-112">Por outro lado, as operações que lêem dados ou estabelecem conexões transitórias não alteram o sistema e geralmente não exigem confirmação.</span><span class="sxs-lookup"><span data-stu-id="ae30f-112">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="ae30f-113">A confirmação também não é necessária para ações cujo efeito está limitado a dentro do tempo de execução do Windows PowerShell, como `set-variable`.</span><span class="sxs-lookup"><span data-stu-id="ae30f-113">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="ae30f-114">Os cmdlets que podem ou não fazer uma alteração persistente devem declarar `SupportsShouldProcess` e chamar [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) somente se eles estiverem prestes a fazer uma alteração persistente.</span><span class="sxs-lookup"><span data-stu-id="ae30f-114">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="ae30f-115">A confirmação de ShouldProcess aplica-se somente a cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ae30f-115">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="ae30f-116">Se um comando ou script modificar o estado de execução de um sistema chamando diretamente métodos ou propriedades do .NET ou chamando aplicativos fora do Windows PowerShell, essa forma de confirmação não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="ae30f-116">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="ae30f-117">O cmdlet StopProc</span><span class="sxs-lookup"><span data-stu-id="ae30f-117">The StopProc Cmdlet</span></span>

<span data-ttu-id="ae30f-118">Este tópico descreve um cmdlet Stop-proc que tenta interromper processos que são recuperados usando o cmdlet Get-proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="ae30f-118">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="ae30f-119">Definindo o cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae30f-119">Defining the Cmdlet</span></span>

<span data-ttu-id="ae30f-120">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ae30f-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="ae30f-121">Como você está escrevendo um cmdlet para alterar o sistema, ele deve ser nomeado de acordo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-121">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="ae30f-122">Esse cmdlet interrompe os processos do sistema, portanto, o nome do verbo escolhido aqui é "Stop", definido pela classe [System. Management. Automation. Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , com o substantivo "proc" para indicar que o cmdlet interrompe os processos.</span><span class="sxs-lookup"><span data-stu-id="ae30f-122">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="ae30f-123">Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="ae30f-123">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="ae30f-124">A seguir está a definição de classe para este cmdlet Stop-proc.</span><span class="sxs-lookup"><span data-stu-id="ae30f-124">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="ae30f-125">Lembre-se de que na Declaração [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , a palavra-chave do atributo `SupportsShouldProcess` é definida como `true` para permitir que o cmdlet faça chamadas para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="ae30f-125">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="ae30f-126">Sem essa palavra-chave definida, os parâmetros `Confirm` e `WhatIf` não estarão disponíveis para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae30f-126">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="ae30f-127">Ações extremamente destrutivas</span><span class="sxs-lookup"><span data-stu-id="ae30f-127">Extremely Destructive Actions</span></span>

<span data-ttu-id="ae30f-128">Algumas operações são extremamente destrutivas, como reformatar uma partição de disco rígido ativa.</span><span class="sxs-lookup"><span data-stu-id="ae30f-128">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="ae30f-129">Nesses casos, o cmdlet deve definir `ConfirmImpact` = `ConfirmImpact.High` ao declarar o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .</span><span class="sxs-lookup"><span data-stu-id="ae30f-129">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="ae30f-130">Essa configuração força o cmdlet a solicitar a confirmação do usuário mesmo quando o usuário não tiver especificado o parâmetro `Confirm`.</span><span class="sxs-lookup"><span data-stu-id="ae30f-130">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="ae30f-131">No entanto, os desenvolvedores de cmdlets devem evitar a superutilização de `ConfirmImpact` para operações que são potencialmente destrutivos, como excluir uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ae30f-131">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="ae30f-132">Lembre-se de que, se `ConfirmImpact` estiver definido como [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span><span class="sxs-lookup"><span data-stu-id="ae30f-132">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span></span>

<span data-ttu-id="ae30f-133">Da mesma forma, é improvável que algumas operações sejam destrutivas, embora elas, na teoria, modifiquem o estado de execução de um sistema fora do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae30f-133">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="ae30f-134">Esses cmdlets podem definir `ConfirmImpact` para [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="ae30f-134">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span></span> <span data-ttu-id="ae30f-135">Isso irá ignorar as solicitações de confirmação em que o usuário solicitou a confirmação somente de operações de impacto médio e de alto impacto.</span><span class="sxs-lookup"><span data-stu-id="ae30f-135">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="ae30f-136">Definindo parâmetros para a modificação do sistema</span><span class="sxs-lookup"><span data-stu-id="ae30f-136">Defining Parameters for System Modification</span></span>

<span data-ttu-id="ae30f-137">Esta seção descreve como definir os parâmetros de cmdlet, incluindo os que são necessários para dar suporte à modificação do sistema.</span><span class="sxs-lookup"><span data-stu-id="ae30f-137">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="ae30f-138">Consulte [adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md) se você precisar de informações gerais sobre como definir parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ae30f-138">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="ae30f-139">O cmdlet Stop-proc define três parâmetros: `Name`, `Force`e `PassThru`.</span><span class="sxs-lookup"><span data-stu-id="ae30f-139">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="ae30f-140">O parâmetro `Name` corresponde à propriedade `Name` do objeto de entrada do processo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-140">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="ae30f-141">Lembre-se de que o parâmetro `Name` neste exemplo é obrigatório, pois o cmdlet falhará se ele não tiver um processo nomeado para parar.</span><span class="sxs-lookup"><span data-stu-id="ae30f-141">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="ae30f-142">O parâmetro `Force` permite que o usuário substitua as chamadas para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="ae30f-142">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="ae30f-143">Na verdade, qualquer cmdlet que chama [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) deve ter um parâmetro `Force` para que, quando `Force` for especificado, o cmdlet ignore a chamada para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) e continue com a operação.</span><span class="sxs-lookup"><span data-stu-id="ae30f-143">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="ae30f-144">Lembre-se de que isso não afeta as chamadas para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span><span class="sxs-lookup"><span data-stu-id="ae30f-144">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="ae30f-145">O parâmetro `PassThru` permite que o usuário indique se o cmdlet passa um objeto de saída por meio do pipeline, nesse caso, depois que um processo é interrompido.</span><span class="sxs-lookup"><span data-stu-id="ae30f-145">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="ae30f-146">Lembre-se de que esse parâmetro está vinculado ao próprio cmdlet, em vez de a uma propriedade do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="ae30f-146">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="ae30f-147">Aqui está a declaração de parâmetro para o cmdlet Stop-proc.</span><span class="sxs-lookup"><span data-stu-id="ae30f-147">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="ae30f-148">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="ae30f-148">Overriding an Input Processing Method</span></span>

<span data-ttu-id="ae30f-149">O cmdlet deve substituir um método de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="ae30f-149">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="ae30f-150">O código a seguir ilustra a substituição [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) usada no cmdlet Stop-proc de exemplo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-150">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="ae30f-151">Para cada nome de processo solicitado, esse método garante que o processo não seja um processo especial, tente interromper o processo e, em seguida, enviará um objeto de saída se o parâmetro `PassThru` for especificado.</span><span class="sxs-lookup"><span data-stu-id="ae30f-151">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

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

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="ae30f-152">Chamando o método ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="ae30f-152">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="ae30f-153">O método de processamento de entrada do seu cmdlet deve chamar o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) para confirmar a execução de uma operação antes que uma alteração (por exemplo, exclusão de arquivos) seja feita no estado de execução do sistema.</span><span class="sxs-lookup"><span data-stu-id="ae30f-153">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="ae30f-154">Isso permite que o tempo de execução do Windows PowerShell forneça o comportamento correto de "WhatIf" e "confirmar" no Shell.</span><span class="sxs-lookup"><span data-stu-id="ae30f-154">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="ae30f-155">Se um cmdlet indicar que ele dá suporte deve processar e falhar ao fazer a chamada de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , o usuário poderá modificar o sistema inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="ae30f-155">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="ae30f-156">A chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell levando em conta quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ae30f-156">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="ae30f-157">O exemplo a seguir mostra a chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) no cmdlet Stop-proc de exemplo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-157">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="ae30f-158">Chamando o método ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="ae30f-158">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="ae30f-159">A chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) envia uma mensagem secundária para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae30f-159">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="ae30f-160">Essa chamada é feita após a chamada para [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) retornar `true` e se o parâmetro `Force` não tiver sido definido como `true`.</span><span class="sxs-lookup"><span data-stu-id="ae30f-160">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="ae30f-161">Em seguida, o usuário pode fornecer comentários para dizer se a operação deve continuar.</span><span class="sxs-lookup"><span data-stu-id="ae30f-161">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="ae30f-162">Seu cmdlet chama [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema ou quando você deseja fornecer opções Sim para tudo e não para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae30f-162">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="ae30f-163">O exemplo a seguir mostra a chamada para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) no cmdlet Stop-proc de exemplo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-163">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

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

## <a name="stopping-input-processing"></a><span data-ttu-id="ae30f-164">Parando o processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="ae30f-164">Stopping Input Processing</span></span>

<span data-ttu-id="ae30f-165">O método de processamento de entrada de um cmdlet que faz modificações no sistema deve fornecer uma maneira de parar o processamento da entrada.</span><span class="sxs-lookup"><span data-stu-id="ae30f-165">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="ae30f-166">No caso desse cmdlet Stop-proc, é feita uma chamada do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para o método [System. Diagnostics. Process. Kill \*](/dotnet/api/System.Diagnostics.Process.Kill) .</span><span class="sxs-lookup"><span data-stu-id="ae30f-166">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="ae30f-167">Como o parâmetro `PassThru` é definido como `true`, [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) também chama [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) para enviar o objeto de processo para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="ae30f-167">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ae30f-168">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="ae30f-168">Code Sample</span></span>

<span data-ttu-id="ae30f-169">Para obter o C# código de exemplo completo, consulte [exemplo de StopProcessSample01](./stopprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ae30f-169">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="ae30f-170">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="ae30f-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="ae30f-171">O Windows PowerShell passa informações entre os cmdlets usando objetos .net.</span><span class="sxs-lookup"><span data-stu-id="ae30f-171">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="ae30f-172">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ae30f-172">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="ae30f-173">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ae30f-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="ae30f-174">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae30f-174">Building the Cmdlet</span></span>

<span data-ttu-id="ae30f-175">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae30f-175">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="ae30f-176">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ae30f-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="ae30f-177">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae30f-177">Testing the Cmdlet</span></span>

<span data-ttu-id="ae30f-178">Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ae30f-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="ae30f-179">Aqui estão vários testes que testam o cmdlet Stop-proc.</span><span class="sxs-lookup"><span data-stu-id="ae30f-179">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="ae30f-180">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae30f-180">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="ae30f-181">Inicie o Windows PowerShell e use o cmdlet Stop-proc para parar o processamento, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="ae30f-181">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="ae30f-182">Como o cmdlet especifica o parâmetro `Name` como obrigatório, o cmdlet consulta o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ae30f-182">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="ae30f-183">A saída a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="ae30f-183">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="ae30f-184">Agora, vamos usar o cmdlet para parar o processo chamado "NOTEPAD".</span><span class="sxs-lookup"><span data-stu-id="ae30f-184">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="ae30f-185">O cmdlet solicita que você confirme a ação.</span><span class="sxs-lookup"><span data-stu-id="ae30f-185">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

<span data-ttu-id="ae30f-186">A saída a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="ae30f-186">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="ae30f-187">Use Stop-proc conforme mostrado para interromper o processo crítico chamado "WINLOGON".</span><span class="sxs-lookup"><span data-stu-id="ae30f-187">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="ae30f-188">Você será solicitado e avisado sobre a execução dessa ação, pois isso fará com que o sistema operacional seja reinicializado.</span><span class="sxs-lookup"><span data-stu-id="ae30f-188">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

<span data-ttu-id="ae30f-189">A saída a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="ae30f-189">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="ae30f-190">Agora, vamos tentar parar o processo WINLOGON sem receber um aviso.</span><span class="sxs-lookup"><span data-stu-id="ae30f-190">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="ae30f-191">Lembre-se de que essa entrada de comando usa o parâmetro `Force` para substituir o aviso.</span><span class="sxs-lookup"><span data-stu-id="ae30f-191">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

<span data-ttu-id="ae30f-192">A saída a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="ae30f-192">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="ae30f-193">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ae30f-193">See Also</span></span>

[<span data-ttu-id="ae30f-194">Adicionando parâmetros que processam a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="ae30f-194">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="ae30f-195">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ae30f-195">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="ae30f-196">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ae30f-196">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="ae30f-197">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae30f-197">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="ae30f-198">Exemplos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae30f-198">Cmdlet Samples</span></span>](./cmdlet-samples.md)