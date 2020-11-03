---
description: Fornece uma breve introdução ao recurso de fluxo de trabalho do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195796"
---
# <a name="about-workflows"></a>Sobre fluxos de trabalho

## <a name="short-description"></a>Descrição breve

Fornece uma breve introdução ao recurso de fluxo de trabalho do PowerShell.

## <a name="long-description"></a>Descrição longa

O fluxo de trabalho do PowerShell traz os benefícios do [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) para o PowerShell e permite que você escreva e execute fluxos de trabalho.

O fluxo de trabalho do PowerShell foi introduzido no PowerShell 3,0 e o módulo está disponível até o PowerShell 5,1. Para obter mais informações sobre o fluxo de trabalho do PowerShell, consulte o [Guia de fluxos de trabalho](/previous-versions/powershell/scripting/components/workflows-guide) e [gravando um fluxo de trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).

## <a name="about-workflows"></a>Sobre fluxos de trabalho

Os fluxos de trabalho são comandos que consistem em uma sequência ordenada de atividades relacionadas. Normalmente, eles são executados por um longo período de tempo, coletando dados e fazendo alterações em centenas de computadores, geralmente em ambientes heterogêneos.

Os fluxos de trabalho podem ser escritos em XAML, a linguagem usada em Windows Workflow Foundation ou na linguagem do PowerShell. Os fluxos de trabalho normalmente são empacotados em módulos e incluem tópicos de ajuda. Para obter mais informações, consulte [visão geral de XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).

Os fluxos de trabalho são críticos em um ambiente de ti porque podem sobreviver a reinicializações e recuperação automáticas de falhas comuns. Você pode desconectar e reconectar-se de sessões e computadores que executam fluxos de trabalho sem interromper o processamento de fluxo de trabalho e suspender e retomar fluxos de trabalho de forma transparente sem perda de dados. Cada atividade em um fluxo de trabalho pode ser registrada em log e auditada para referência.
Os fluxos de trabalho podem ser executados como trabalhos e podem ser agendados usando o recurso trabalhos agendados do PowerShell.

O estado e os dados em um fluxo de trabalho são salvos ou persistidos no início e no final do fluxo de trabalho e em pontos que você especificar. Os pontos de persistência do fluxo de trabalho funcionam como instantâneos do banco de dados ou pontos de verificação do programa para proteger o fluxo de trabalho contra os efeitos de interrupções e falhas. Se o fluxo de trabalho não puder se recuperar de uma falha, você poderá usar os dados persistentes e retomar o último ponto de persistência, em vez de executar um fluxo de trabalho extensivo desde o início.

## <a name="workflow-requirements-and-configuration"></a>Requisitos e configuração de fluxo de trabalho

Uma configuração de fluxo de trabalho do PowerShell consiste nos seguintes elementos:

- Um computador cliente, que executa o fluxo de trabalho.
- Uma sessão de fluxo de trabalho, **PSSession** , no computador cliente ou em um computador remoto.
- Nós gerenciados, os computadores de destino que são afetados pelas atividades de fluxo de trabalho.

A sessão de fluxo de trabalho não é necessária, mas é recomendada. As **PSSessions** podem aproveitar os recursos de recuperação robusta e de sessões desconectadas do PowerShell para recuperar sessões de fluxo de trabalho desconectadas. Para obter mais informações, consulte [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)

Como o computador cliente e o computador no qual a sessão de fluxo de trabalho é executada podem ser nós gerenciados, você pode executar um fluxo de trabalho em um único computador que atenda a todas as funções.

O computador cliente e o computador no qual a sessão de fluxo de trabalho é executada deve executar o PowerShell 3,0. Todos os sistemas qualificados têm suporte, incluindo as opções de instalação Server Core dos sistemas operacionais Windows Server.

Para executar fluxos de trabalho que incluem cmdlets, os nós gerenciados devem ter o Windows PowerShell 2,0 ou posterior. Nós gerenciados não exigem o PowerShell, a menos que o fluxo de trabalho inclua cmdlets. Você pode executar fluxos de trabalho que incluem comandos Instrumentação de Gerenciamento do Windows (WMI) e modelo CIM (CIM) em computadores que não têm o PowerShell.

## <a name="how-to-get-workflows"></a>Como obter fluxos de trabalho

Os fluxos de trabalho normalmente são empacotados em módulos. Para importar o módulo que inclui um fluxo de trabalho, use qualquer comando no módulo ou use o `Import-Module` cmdlet.
Os módulos são importados automaticamente no primeiro uso de qualquer comando no módulo.

Para localizar os fluxos de trabalho nos módulos instalados no seu computador, use o `Get-Command` parâmetro **CommandType** do cmdlet.

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a>Como executar fluxos de trabalho

Para executar um fluxo de trabalho, use o procedimento a seguir.

1. Quando o nó gerenciado é o computador local, essa etapa não é necessária.
   Caso contrário, no computador cliente, inicie o PowerShell com a opção **Executar como administrador** .

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. Habilite a comunicação remota do PowerShell no computador que executa a sessão de fluxo de trabalho e em nós gerenciados afetados por fluxos de trabalho que incluem cmdlets.

   Você só precisa fazer essa etapa uma vez em cada computador participante.

   Esta etapa é necessária somente ao executar fluxos de trabalho que incluem cmdlets. Você não precisa habilitar a comunicação remota no computador cliente, a menos que a sessão de fluxos de trabalho seja executada no computador cliente ou em qualquer nó gerenciado que esteja executando o PowerShell 3,0.

   Para habilitar a comunicação remota, use o `Enable-PSRemoting` cmdlet.

   ```powershell
   Enable-PSRemoting -Force
   ```

   Você pode habilitar a comunicação remota usando a configuração ativar Política de Grupo de **execução de script** . Para obter mais informações, consulte [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) e [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

1. Use os `New-PSWorkflowSession` `New-PSSession` cmdlets ou para criar a sessão de fluxo de trabalho.

   O `New-PSWorkflowSession` cmdlet inicia uma sessão que usa a configuração de sessão interna **Microsoft. PowerShell. Workflow** no computador de destino. Essa configuração de sessão inclui scripts, tipos e formatação de arquivos e opções projetadas para fluxos de trabalho.

   Ou use o `New-PSSession` cmdlet. Use o parâmetro **ConfigurationName** para especificar a configuração de sessão **Microsoft. PowerShell. Workflow** . Esse comando é o mesmo que usar o `New-PSWorkflowSession` cmdlet.

   Uma alternativa é usar o `New-PSSession` cmdlet. Use o parâmetro **ConfigurationName** para especificar a configuração de sessão **Microsoft. PowerShell. Workflow** .

   No computador local:

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   Em um computador remoto:

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   Se você for um administrador no computador da sessão de fluxo de trabalho, poderá usar o `New-PSWorkflowExecutionOption` cmdlet para criar configurações de opção personalizada para a configuração da sessão de fluxo de trabalho. E use o `Set-PSSessionConfiguration` cmdlet para alterar a configuração da sessão.

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. Execute o fluxo de trabalho na sessão de fluxo de trabalho. Para especificar os nomes dos nós gerenciados, os computadores de destino, use o parâmetro comum de fluxo de trabalho **PSComputerName** .

   Os exemplos a seguir executam o fluxo de trabalho chamado **Test-Workflow** .

   Onde o nó gerenciado é o computador que hospeda a sessão de fluxo de trabalho:

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   Onde os nós gerenciados são computadores remotos.

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   O exemplo a seguir executa o **fluxo de trabalho de teste** em centenas de computadores. O `Get-Content` cmdlet obtém os nomes de computador de um arquivo de texto e os salva `$Servers` na variável no computador local.

   `Invoke-Command` usa o `$Using` modificador de escopo para definir a `$Servers` variável na sessão local. Para obter mais informações sobre o `$Using` modificador de escopo, consulte [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a>Usando parâmetros comuns de fluxo de trabalho

Os parâmetros comuns do fluxo de trabalho são um conjunto de parâmetros que o PowerShell adiciona automaticamente a todos os fluxos de trabalho. O PowerShell adiciona os parâmetros comuns do cmdlet a todos os fluxos de trabalho, mesmo que o fluxo de trabalho não use o atributo **CmdletBinding** .

Por exemplo, o fluxo de trabalho a seguir não define nenhum parâmetro. No entanto, quando você executa o fluxo de trabalho, ele tem **CommonParameters** e **WorkflowCommonParameters** .

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

Os parâmetros comuns do fluxo de trabalho incluem vários parâmetros que são essenciais para a execução de fluxos de trabalho. Por exemplo, o parâmetro comum **PSComputerName** especifica os nós gerenciados que o fluxo de trabalho afeta.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

O parâmetro Common do fluxo de trabalho **PSPersist** determina quando os dados do fluxo de trabalho são persistidos. Ele permite que você adicione um ponto de persistência entre atividades a fluxos de trabalho que não definem pontos de persistência.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

Outros parâmetros comuns de fluxo de trabalho permitem especificar as características da conexão remota para os nós gerenciados. Seus nomes e funcionalidades são semelhantes aos parâmetros de cmdlets de comunicação remota, incluindo `Invoke-Command` .

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

Tome cuidado para distinguir os parâmetros de comunicação remota que definem a conexão para a sessão de fluxo de trabalho dos parâmetros comuns de fluxo de trabalho do **PS-prefixado** que definem a conexão com os nós gerenciados.

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

Alguns parâmetros comuns de fluxo de trabalho são exclusivos de fluxos de trabalho, como o parâmetro **PSParameterCollection** , que permite especificar valores de parâmetros comuns de fluxo de trabalho diferentes para nós remotos diferentes. Para obter uma lista e uma descrição dos parâmetros comuns do fluxo de trabalho, consulte [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).

## <a name="see-also"></a>Confira também

[Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

Cmdlets [PSWorkflow](xref:PSWorkflow)

[Guia de fluxos de trabalho](/previous-versions/powershell/scripting/components/workflows-guide)

[Escrevendo um Fluxo de Trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
