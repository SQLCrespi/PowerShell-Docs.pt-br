---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193655"
---
# Invoke-AsWorkflow

## SINOPSE
Executa um comando ou uma expressão como um Fluxo de Trabalho do Windows PowerShell.

## SYNTAX

### Comando (padrão)

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### Expression

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-AsWorkflow` fluxo de trabalho executa qualquer comando ou expressão como um script embutido em um fluxo de trabalho.
Esses fluxos de trabalho usam a semântica do fluxo de trabalho padrão, têm todos os parâmetros comuns de fluxo de trabalho e todos os benefícios dos fluxos de trabalho, incluindo a capacidade de parar, reiniciar e recuperar.

Fluxos de trabalho são criados para comandos de longa execução que coletam dados críticos, mas podem ser usados para executar qualquer comando.
Para obter mais informações, consulte [about_Workflows](../PSWorkflow/About/about_Workflows.md).

Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando.
Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)

Este fluxo de trabalho é introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: executar um cmdlet como um fluxo de trabalho

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

Esse comando executa o `Get-ExecutionPolicy` cmdlet como um fluxo de trabalho em centenas de computadores.

O comando utiliza o parâmetro **CommandName** para especificar o cmdlet que é executado no fluxo de trabalho.
Ele usa o parâmetro comum de fluxo de trabalho **PSComputerName** para especificar os computadores em que o comando é executado.
O valor do parâmetro **PSComputerName** é um `Get-Content` comando que obtém uma lista de nomes de computador do arquivo de Servers.txt.
O valor do parâmetro é colocado entre parênteses para direcionar o Windows PowerShell a executar o `Get-Command` comando antes de usar o valor.

Assim como acontece com todos os comandos remotos, se o comando é executado no computador local, (se o valor do parâmetro PSComputerName inclui o computador local), você deve iniciar o Windows PowerShell com a opção "Executar como administrador".

### Exemplo 2: executar um cmdlet com parâmetros

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

O primeiro comando usa o `Import-Csv` cmdlet para criar um objeto do conteúdo no arquivo de Servers.csv. O comando usa o `Header` parâmetro para criar uma `ServerName` propriedade para a coluna que contém os nomes dos computadores de destino, também conhecidos como "nós remotos". O comando salva o resultado na `$s` variável.

O segundo comando usa o `Invoke-AsWorkflow` fluxo de trabalho para executar um `Get-ExecutionPolicy` comando nos computadores do arquivo de Servers.csv. O comando usa o parâmetro **CommandName** de `Invoke-AsWorkflow`  para especificar o comando a ser executado no fluxo de trabalho. Ele usa o `Parameter` parâmetro de `Invoke-AsWorkflow` para especificar o `Scope` parâmetro do `Get-ExecutionPolicy` cmdlet com um valor de **process** . O comando também usa o `PSConnectionRetryCount` parâmetro comum do fluxo de trabalho para limitar o comando a cinco tentativas em cada computador e o `PSComputerName` parâmetro comum do fluxo de trabalho para especificar os nomes dos nós remotos (computadores de destino). O valor do `PSComputerName` parâmetro é uma expressão que obtém a `ServerName` propriedade de cada objeto na `$s` variável.

Esses comandos executam um `Get-ExecutionPolicy` comando como um fluxo de trabalho em centenas de computadores.
O comando usa o `Scope` parâmetro do `Get-ExecutionPolicy` cmdlet com um valor de **processo** para obter a política de execução na sessão atual.

### Exemplo 3: executar uma expressão como um fluxo de trabalho

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

Esse comando usa o `Invoke-AsWorkflow` fluxo de trabalho para executar um comando ipconfig como um job de workflow nos computadores listados no arquivo de DomainControllers.txt.

O comando usa o `Expression` parâmetro para especificar a expressão a ser executada.
Ele usa o `PSComputerName` parâmetro Common do fluxo de trabalho para especificar os nomes dos nós remotos (computadores de destino).

O comando também usa os `AsJob` parâmetros comuns do e do `JobName` fluxo de trabalho para executar o workflow como uma tarefa em segundo plano em cada computador com o nome do trabalho "ipconfig".

O comando retorna um `ContainerParentJob` objeto ( `System.Management.Automation.ContainerParentJob` ) que contém os trabalhos de fluxo de trabalho em cada computador.

## PARAMETERS

### -CommandName

Executa o cmdlet especificado ou função avançada como um fluxo de trabalho.
Insira o nome do cmdlet ou da função, como `Update-Help` , `Set-ExecutionPolicy` ou `Set-NetFirewallRule` .

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expressão

Especifica a expressão que esse cmdlet executa como um fluxo de trabalho.
Insira a expressão como uma cadeia de caracteres, como `"ipconfig /all"` .
Se a expressão incluir espaços ou caracteres especiais, coloque-a entre aspas.

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Parâmetros do 

Especifica os parâmetros e os valores de parâmetro do comando especificado no `CommandName` parâmetro.
Insira uma tabela de hash na qual cada chave seja um nome de parâmetro e seu valor seja o valor do parâmetro, como `@{ExecutionPolicy="AllSigned"}` .

Para obter informações sobre tabelas de hash, consulte [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Usado para permitir a entrada do pipeline.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

### WorkflowCommonParameters

Esse cmdlet também dá suporte a parâmetros comuns específicos de fluxo de trabalho.
Para obter informações, consulte [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).

## ENTRADAS

### System.Object

É possível canalizar qualquer objeto para o `InputObject` parâmetro.

## SAÍDAS

### Nenhum

Esse comando não gera nenhuma saída.
No entanto, ele executa o fluxo de trabalho que pode gerar uma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[New-PSWorkflowSession](../PSWorkflow/New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_Workflow_Common_Parameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)
