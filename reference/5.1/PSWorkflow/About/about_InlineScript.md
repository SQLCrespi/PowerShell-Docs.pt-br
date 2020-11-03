---
description: Descreve a `InlineScript` atividade, que executa comandos do PowerShell em um fluxo de trabalho.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195810"
---
# <a name="about-inlinescript"></a>Sobre o InlineScript

## <a name="short-description"></a>Descrição breve

Descreve a `InlineScript` atividade, que executa comandos do PowerShell em um fluxo de trabalho.

## <a name="long-description"></a>Descrição longa

A `InlineScript` atividade executa comandos em um fluxo de trabalho de sessão do PowerShell compartilhado. `InlineScript` Só é válido em fluxos de trabalho.

## <a name="syntax"></a>Syntax

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a>Descrição detalhada

A `InlineScript` atividade executa comandos em uma sessão do PowerShell compartilhada. Você pode incluí-lo em um fluxo de trabalho para executar comandos que compartilham dados e comandos que, de outra forma, não são válidos em um fluxo de trabalho.

O `InlineScript` bloco de script pode incluir todos os comandos e expressões do PowerShell válidos. Como os comandos e as expressões em um `InlineScript` bloco de script são executados na mesma sessão, eles compartilham todos os Estados e dados, incluindo os módulos importados e os valores das variáveis.

Você pode colocar uma `InlineScript` atividade em qualquer lugar em um fluxo de trabalho ou em um fluxo de trabalho aninhado, incluindo dentro de um loop ou instrução de controle ou um bloco de script paralelo ou de sequência.

A `InlineScript` atividade tem os parâmetros comuns da atividade, incluindo **PSPersist** . No entanto, os comandos e expressões em um `InlineScript` bloco de script não têm os recursos de fluxo de trabalho, como ponto de verificação, persistência e parâmetros comuns de fluxo de trabalho ou atividade. Para obter mais informações, consulte [about_ActivityCommonParameters](about_ActivityCommonParameters.md).

## <a name="inlinescript-variables"></a>Variáveis InlineScript

Por padrão, as variáveis definidas em um fluxo de trabalho não são visíveis para os comandos no `InlineScript` bloco de script. Para tornar as variáveis de fluxo de trabalho visíveis para o `InlineScript` , use o `$Using` modificador de escopo. O `$Using` modificador de escopo é necessário apenas uma vez para cada variável no `InlineScript` .

Para obter mais informações sobre o `$Using` modificador de escopo, consulte [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

O exemplo a seguir mostra que o `$Using` modificador de escopo torna o valor da `$a` variável de fluxo de trabalho de nível superior disponível para os comandos no bloco de `InlineScript` script.

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a>Retornando variáveis em InlineScript

`InlineScript` os comandos podem alterar o valor da variável que foi importada do escopo do fluxo de trabalho, mas as alterações não são visíveis no escopo do fluxo de trabalho. Para torná-las visíveis, retorne o valor alterado para o escopo do fluxo de trabalho, conforme exibido no exemplo a seguir.

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> Uma instrução com o `$Using` modificador de escopo deve aparecer antes de qualquer uso da variável no `InlineScript` bloco de script.

## <a name="running-in-process"></a>Executando em processo

Para melhorar a confiabilidade, os comandos no `InlineScript` bloco de script são executados em seu próprio processo, separados do processo no qual o fluxo de trabalho é executado e, em seguida, retornam a saída para o processo de fluxo de trabalho.

Para direcionar o PowerShell para executar a `InlineScript` atividade no processo de fluxo de trabalho, remova o `InlineScript` valor da propriedade **OutOfProcessActivity** da configuração de sessão, como usando o `New-PSWorkflowExecutionOption` cmdlet.

### <a name="example"></a>Exemplo

O `InlineScript` no fluxo de trabalho a seguir inclui comandos que são válidos no PowerShell, mas não são válidos em fluxos de trabalho. Por exemplo, o `New-Object` cmdlet com o parâmetro **ComObject** .

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a>Confira também

[about_ActivityCommonParameters](about_ActivityCommonParameters.md)

[about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

Cmdlets [PSWorkflow](xref:PSWorkflow)

[Guia de fluxos de trabalho](/previous-versions/powershell/scripting/components/workflows-guide)

[Escrevendo um Fluxo de Trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
