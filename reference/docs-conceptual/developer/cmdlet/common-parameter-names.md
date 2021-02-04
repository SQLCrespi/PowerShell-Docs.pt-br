---
ms.date: 09/13/2016
ms.topic: reference
title: Nomes de parâmetro comuns
description: Nomes de parâmetro comuns
ms.openlocfilehash: 506aab290abdb97a6e26c340ac4bd0051244f54b
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860872"
---
# <a name="common-parameter-names"></a>Nomes de parâmetro comuns

Os parâmetros descritos neste tópico são chamados de **parâmetros comuns**. Eles são adicionados aos cmdlets pelo tempo de execução do Windows PowerShell e não podem ser declarados pelo cmdlet.

> [!NOTE]
> Esses parâmetros também são adicionados aos cmdlets do provedor e às funções que são decoradas com o `CmdletBinding` atributo.

## <a name="general-common-parameters"></a>Parâmetros gerais comuns

Os parâmetros a seguir são adicionados a todos os cmdlets e podem ser acessados sempre que o cmdlet é executado.
Esses parâmetros são definidos pela classe [System. Management. Automation. Internal. CommonParameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters) .

### <a name="confirm-alias-cf"></a>Confirmar (alias: CF)

Tipo de dados: SwitchParameter

Esse parâmetro especifica se o cmdlet exibe um prompt que pergunta se o usuário tem certeza de que deseja continuar.

### <a name="debug-alias-db"></a>Depurar (alias: DB)

Tipo de dados: SwitchParameter

Esse parâmetro especifica se as mensagens de depuração no nível do programador que podem ser exibidas na linha de comando. Essas mensagens destinam-se à solução de problemas da operação do cmdlet e são geradas por chamadas para o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) . As mensagens de depuração não precisam ser localizadas.

### <a name="erroraction-alias-ea"></a>ErrorAction (alias: ea)

Tipo de dados: enumeração

Esse parâmetro especifica a ação que deve ocorrer quando ocorre um erro. Os valores possíveis para esse parâmetro são definidos pela enumeração [System. Management. Automation. preferência](/dotnet/api/System.Management.Automation.ActionPreference) .

### <a name="errorvariable-alias-ev"></a>ErrorVariable (alias: EV)

Tipo de dados: cadeia de caracteres

Esse parâmetro especifica a variável na qual os objetos são colocados quando ocorre um erro. Para acrescentar a essa variável, use +_VarName_ em vez de limpar e definir a variável.

### <a name="outbuffer-alias-ob"></a>OutBuffer (alias: OB)

Tipo de dados: Int32

Esse parâmetro define o número de objetos a serem armazenados no buffer de saída antes que qualquer objeto seja passado para o pipeline. Por padrão, os objetos são passados imediatamente para baixo no pipeline.

### <a name="outvariable-alias-ov"></a>Outvariance (alias: OV)

Tipo de dados: cadeia de caracteres

Esse parâmetro especifica a variável na qual todos os objetos de saída gerados pelo cmdlet são colocados.
Para acrescentar a essa variável, use +_VarName_ em vez de limpar e definir a variável.

### <a name="pipelinevariable-alias-pv"></a>PipelineVariable (alias: VP)

Tipo de dados: cadeia de caracteres

Esse parâmetro armazena o valor do elemento do pipeline atual como uma variável para qualquer comando nomeado conforme ele flui pelo pipeline.

## <a name="verbose-alias-vb"></a>Verbose (alias: VB)

Tipo de dados: SwitchParameter

Esse parâmetro especifica se o cmdlet grava mensagens explicativas que podem ser exibidas na linha de comando. Essas mensagens destinam-se a fornecer ajuda adicional para o usuário e são geradas por chamadas para o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .

### <a name="warningaction-alias-wa"></a>Avisoaction (alias: WA)

Tipo de dados: enumeração

Esse parâmetro especifica a ação que deve ocorrer quando o cmdlet grava uma mensagem de aviso. Os valores possíveis para esse parâmetro são definidos pela enumeração [System. Management. Automation. preferência](/dotnet/api/System.Management.Automation.ActionPreference) .

### <a name="warningvariable-alias-wv"></a>WarningVariable (alias: WV)

Tipo de dados: cadeia de caracteres

Esse parâmetro especifica a variável na qual as mensagens de aviso podem ser salvas. Para acrescentar a essa variável, use +_VarName_ em vez de limpar e definir a variável.

## <a name="risk-mitigation-parameters"></a>Risk-Mitigation parâmetros

Os parâmetros a seguir são adicionados aos cmdlets que solicitam confirmação antes de executarem suas ações. Para obter mais informações sobre solicitações de confirmação, consulte [solicitando confirmação](./requesting-confirmation-from-cmdlets.md).
Esses parâmetros são definidos pela classe [System. Management. Automation. Internal. Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters) .

### <a name="whatif-alias-wi"></a>WhatIf (alias: Wi)

Tipo de dados: SwitchParameter

Esse parâmetro especifica se o cmdlet grava uma mensagem que descreve os efeitos da execução do cmdlet sem realmente executar nenhuma ação.

## <a name="transaction-parameters"></a>Parâmetros de transação

O parâmetro a seguir é adicionado aos cmdlets que dão suporte a transações. Esses parâmetros são definidos pela classe [System. Management. Automation. Internal. transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters) . O suporte à transação foi introduzido no PowerShell 3,0 e foi descontinuado no PowerShell 6,0.

### <a name="usetransaction-alias-usetx"></a>UseTransaction (alias: UseTx)

Tipo de dados: SwitchParameter

Esse parâmetro especifica se o cmdlet usará a transação atual para executar sua ação.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Internal. CommonParameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[System. Management. Automation. Internal. Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[System. Management. Automation. Internal. transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
