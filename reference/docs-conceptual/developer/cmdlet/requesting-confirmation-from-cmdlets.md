---
title: Solicitando confirmação de cmdlets | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.assetid: 37d6e87f-57b7-40bd-b645-392cf0b6e88e
caps.latest.revision: 13
ms.openlocfilehash: 0c0517ef7fbd5ae6434773a2dfe276f3a8c35f39
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369525"
---
# <a name="requesting-confirmation-from-cmdlets"></a>Solicitar confirmação por meio de cmdlets

Os cmdlets devem solicitar confirmação quando estão prestes a fazer uma alteração no sistema que está fora do ambiente do Windows PowerShell. Por exemplo, se um cmdlet estiver prestes a adicionar uma conta de usuário ou parar um processo, o cmdlet deverá exigir confirmação do usuário antes de continuar. Por outro lado, se um cmdlet estiver prestes a alterar uma variável do Windows PowerShell, o cmdlet não precisará exigir confirmação.

Para fazer uma solicitação de confirmação, o cmdlet deve indicar que ele dá suporte a solicitações de confirmação e deve chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (opcional) para exibir uma mensagem de solicitação de confirmação.

## <a name="supporting-confirmation-requests"></a>Suporte a solicitações de confirmação

Para dar suporte a solicitações de confirmação, o cmdlet deve definir o parâmetro `SupportsShouldProcess` do atributo cmdlet como `true`. Isso habilita os parâmetros de cmdlet `Confirm` e `WhatIf` fornecidos pelo Windows PowerShell. O parâmetro `Confirm` permite que o usuário controle se a solicitação de confirmação é exibida. O parâmetro `WhatIf` permite que o usuário determine se o cmdlet deve exibir uma mensagem ou executar sua ação. Não adicione manualmente os parâmetros `Confirm` e `WhatIf` a um cmdlet.

O exemplo a seguir mostra uma declaração de atributo de cmdlet que dá suporte a solicitações de confirmação.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>Chamando os métodos de solicitação de confirmação

No código do cmdlet, chame o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) antes que a operação que altera o sistema seja executada. Projete o cmdlet para que, se a chamada retornar um valor de `false`, a operação não seja executada e o cmdlet processe a próxima operação.

## <a name="calling-the-shouldcontinue-method"></a>Chamando o método ShouldContinue

A maioria dos cmdlets solicita confirmação usando apenas o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . No entanto, alguns casos podem exigir confirmação adicional. Nesses casos, complemente a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) com uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) . Isso permite que o cmdlet ou o provedor controle mais minuciosamente o escopo do **Sim para todas as** respostas ao prompt de confirmação.

Se um cmdlet chama o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , o cmdlet também deve fornecer um parâmetro de opção `Force`. Se o usuário especificar `Force` quando o usuário chamar o cmdlet, o cmdlet ainda deverá chamar [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), mas deverá ignorar a chamada para [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

[System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) gerará uma exceção quando for chamado a partir de um ambiente não interativo em que o usuário não pode ser solicitado. A adição de um parâmetro de `Force` garante que o comando ainda possa ser executado quando for invocado em um ambiente não interativo.

O exemplo a seguir mostra como chamar [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

O comportamento de uma chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) pode variar dependendo do ambiente no qual o cmdlet é invocado. Usar as diretrizes anteriores ajudará a garantir que o cmdlet se comporta de forma consistente com outros cmdlets, independentemente do ambiente de host.

Para obter um exemplo de como chamar o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , consulte [como solicitar confirmações](./how-to-request-confirmations.md).

## <a name="specify-the-impact-level"></a>Especificar o nível de impacto

Ao criar o cmdlet, especifique o nível de impacto (a severidade) da alteração. Para fazer isso, defina o valor do parâmetro `ConfirmImpact` do atributo cmdlet como alto, médio ou baixo. Você pode especificar um valor para `ConfirmImpact` somente quando você também especificar o parâmetro `SupportsShouldProcess` para o cmdlet.

Para a maioria dos cmdlets, você não precisa especificar explicitamente `ConfirmImpact`.  Em vez disso, use a configuração padrão do parâmetro, que é médio. Se você definir `ConfirmImpact` como alta, a operação será confirmada por padrão. Reserve essa configuração para ações altamente perturbadoras, como reformatar um volume de disco rígido.

## <a name="calling-non-confirmation-methods"></a>Chamando métodos que não são de confirmação

Se o cmdlet ou o provedor precisar enviar uma mensagem, mas não a confirmação de solicitação, ele poderá chamar os três métodos a seguir. Evite usar o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) para enviar mensagens desses tipos porque a saída de [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) é mesclada com a saída normal do seu cmdlet ou provedor, o que dificulta a gravação do script.

- Para ter cuidado com o usuário e continuar com a operação, o cmdlet ou o provedor pode chamar o método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) .

- Para fornecer informações adicionais que o usuário pode recuperar usando o parâmetro `Verbose`, o cmdlet ou o provedor pode chamar o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .

- Para fornecer detalhes de nível de depuração para outros desenvolvedores ou para o suporte do produto, o cmdlet ou o provedor pode chamar o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) . O usuário pode recuperar essas informações usando o parâmetro `Debug`.

Os cmdlets e os provedores primeiro chamam os seguintes métodos para solicitar confirmação antes de tentarem executar uma operação que altera um sistema fora do Windows PowerShell:

- [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [System. Management. Automation. Provider. Cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

Eles fazem isso chamando o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , que solicita ao usuário que confirme a operação com base em como o usuário invocou o comando.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
