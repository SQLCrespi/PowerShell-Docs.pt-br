---
description: Descreve como as funções que especificam o `CmdletBinding` atributo podem usar os métodos e as propriedades que estão disponíveis para cmdlets compilados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 260dab1937715da34b9191ff2765dee7d2ac3ec5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196209"
---
# <a name="about-functions-advanced-methods"></a>Sobre os métodos avançados do Functions

## <a name="short-description"></a>Descrição breve

Descreve como as funções que especificam o `CmdletBinding` atributo podem usar os métodos e as propriedades que estão disponíveis para cmdlets compilados.

## <a name="long-description"></a>Descrição longa

As funções que especificam o `CmdletBinding` atributo podem acessar vários métodos e propriedades por meio da `$PSCmdlet` variável. Esses métodos incluem os seguintes métodos:

- Métodos de processamento de entrada que os cmdlets compilados usam para realizar seu trabalho.
- Os `ShouldProcess` `ShouldContinue` métodos e que são usados para obter comentários do usuário antes que uma ação seja executada.
- O `ThrowTerminatingError` método para gerar registros de erro.
- Vários `Write` métodos que retornam tipos diferentes de saída.

Todos os métodos e propriedades da classe **PSCmdlet** estão disponíveis para funções avançadas. Para obter mais informações, consulte [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Para obter mais informações sobre o `CmdletBinding` atributo, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).
Para a classe **CmdletBindingAttribute** , consulte [System. Management. Automation. cmdlet. CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).

### <a name="input-processing-methods"></a>Métodos de processamento de entrada

Os métodos descritos nesta seção são chamados de métodos de processamento de entrada. Para funções, esses três métodos são representados pelos `Begin` `Process` blocos, e `End` da função. Você não precisa usar nenhum desses blocos em suas funções.

> [!NOTE]
> Esses blocos também estão disponíveis para funções que não usam o `CmdletBinding` atributo.

#### <a name="begin"></a>Começar

Esse bloco é usado para fornecer um pré-processamento de uso único opcional para a função.
O tempo de execução do PowerShell usa o código nesse bloco uma vez para cada instância da função no pipeline.

#### <a name="process"></a>Processar

Esse bloco é usado para fornecer processamento de registro por registro para a função. Você pode usar um `Process` bloco sem definir os outros blocos. O número de `Process` execuções de bloco depende de como você usa a função e a entrada que a função recebe.

A variável automática `$_` ou `$PSItem` contém o objeto atual no pipeline para uso no `Process` bloco. A `$input` variável automática contém um enumerador que só está disponível para funções e blocos de script.
Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

- Chamar a função no início ou fora de um pipeline executa o `Process` bloco uma vez.
- Em um pipeline, o `Process` bloco é executado uma vez para cada objeto de entrada que atinge a função.
- Se a entrada do pipeline que atinge a função estiver vazia, o `Process` bloco **não será** executado.
  - Os `Begin` `End` blocos e ainda são executados.

> [!IMPORTANT]
> Se um parâmetro de função for definido para aceitar a entrada de pipeline e um `Process` bloco não estiver definido, o processamento de registro por registro falhará. Nesse caso, sua função será executada apenas uma vez, independentemente da entrada.

#### <a name="end"></a>End

Esse bloco é usado para fornecer um pós-processamento único opcional para a função.

O exemplo a seguir mostra o contorno de uma função que contém um `Begin` bloco para o pré-processamento único, um `Process` bloco para o processamento de vários registros e um `End` bloco para o pós-processamento único.

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> O uso de `Begin` um `End` bloco ou requer que você defina todos os três blocos. Ao usar todos os três blocos, todo o código do PowerShell deve estar dentro de um dos blocos.

### <a name="confirmation-methods"></a>Métodos de confirmação

#### <a name="shouldprocess"></a>ShouldProcess

Esse método é chamado para solicitar a confirmação do usuário antes que a função execute uma ação que altere o sistema. A função pode continuar com base no valor booliano retornado pelo método. Esse método só pode ser chamado somente de dentro do `Process{}` bloco da função. O `CmdletBinding` atributo também deve declarar que a função dá suporte `ShouldProcess` (conforme mostrado no exemplo anterior).

Para obter mais informações sobre esse método, consulte [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).

Para obter mais informações sobre como solicitar confirmação, consulte [solicitando confirmação](/powershell/scripting/developer/cmdlet/requesting-confirmation).

#### <a name="shouldcontinue"></a>ShouldContinue

Esse método é chamado para solicitar uma segunda mensagem de confirmação. Ele deve ser chamado quando o `ShouldProcess` método retornar `$true` . Para obter mais informações sobre esse método, consulte [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).

### <a name="error-methods"></a>Métodos de erro

As funções podem chamar dois métodos diferentes quando ocorrem erros. Quando ocorre um erro de não finalização, a função deve chamar o `WriteError` método, que é descrito na `Write` seção métodos. Quando ocorre um erro de encerramento e a função não pode continuar, ele deve chamar o `ThrowTerminatingError` método. Você também pode usar a `Throw` instrução para erros de encerramento e o cmdlet [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) para erros de não encerramento.

Para obter mais informações, consulte [System. Management. Automation. cmdlet. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).

### <a name="write-methods"></a>Métodos de gravação

Uma função pode chamar os métodos a seguir para retornar tipos diferentes de saída.
Observe que nem toda a saída vai para o próximo comando no pipeline. Você também pode usar os vários `Write` cmdlets, como `Write-Error` .

#### <a name="writecommanddetail"></a>WriteCommandDetail

Para obter informações sobre o `WriteCommandDetails` método, consulte [System. Management. Automation. cmdlet. WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).

#### <a name="writedebug"></a>WriteDebug

Para fornecer informações que podem ser usadas para solucionar problemas de uma função, faça com que a função chame o `WriteDebug` método. O `WriteDebug` método exibe mensagens de depuração para o usuário. Para obter mais informações, consulte [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).

#### <a name="writeerror"></a>WriteError

As funções devem chamar esse método quando ocorrerem erros de não encerramento e a função for projetada para continuar processando registros. Para obter mais informações, consulte [System. Management. Automation. cmdlet. WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).

> [!NOTE]
> Se ocorrer um erro de encerramento, a função deverá chamar o método [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) .

#### <a name="writeobject"></a>WriteObject

O `WriteObject` método permite que a função envie um objeto para o próximo comando no pipeline. Na maioria dos casos, `WriteObject` é o método a ser usado quando a função retorna dados. Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).

#### <a name="writeprogress"></a>WriteProgress

Para funções com ações que levam muito tempo para serem concluídas, esse método permite que a função chame o `WriteProgress` método para que as informações de progresso sejam exibidas. Por exemplo, você pode exibir a porcentagem concluída.
Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).

#### <a name="writeverbose"></a>WriteVerbose

Para fornecer informações detalhadas sobre o que a função está fazendo, faça com que a função chame o `WriteVerbose` método para exibir mensagens detalhadas ao usuário. Por padrão, as mensagens detalhadas não são exibidas. Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).

#### <a name="writewarning"></a>WriteWarning

Para fornecer informações sobre condições que podem causar resultados inesperados, faça com que a função chame o método WriteWarning para exibir mensagens de aviso ao usuário. Por padrão, as mensagens de aviso são exibidas. Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).

> [!NOTE]
> Você também pode exibir mensagens de aviso Configurando a `$WarningPreference` variável ou usando `Verbose` as `Debug` Opções de linha de comando e. para obter mais informações sobre a `$WarningPreference` variável, consulte [about_Preference_Variables](about_Preference_Variables.md).

### <a name="other-methods-and-properties"></a>Outros métodos e propriedades

Para obter informações sobre os outros métodos e propriedades que podem ser acessados por meio da `$PSCmdlet` variável, consulte [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Por exemplo, a propriedade [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) permite que você veja o conjunto de parâmetros que está sendo usado. Os conjuntos de parâmetros permitem que você crie uma função que executa diferentes tarefas com base nos parâmetros especificados quando a função é executada.

## <a name="see-also"></a>Confira também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Preference_Variables](about_Preference_Variables.md)
