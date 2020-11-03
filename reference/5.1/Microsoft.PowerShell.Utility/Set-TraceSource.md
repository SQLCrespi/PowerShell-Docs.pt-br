---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: cef166404af546c35ccc3b0ffed4174515f74c15
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193739"
---
# Set-TraceSource

## SINOPSE
Configura, inicia e para um rastreamento de componentes do PowerShell.

## SYNTAX

### optionsset (padrão)

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### removeAllListenersSet

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### removeFileListenersSet

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **set-traceexception** configura, inicia e interrompe um rastreamento de um componente do PowerShell.
Você pode usá-lo para especificar quais componentes serão rastreados e para onde a saída de rastreamento é enviada.

## EXEMPLOS

### Exemplo 1: rastrear o componente ParameterBinding

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

Esse comando inicia o rastreamento para o componente ParameterBinding do PowerShell.
Ele usa o parâmetro *Name* para especificar a origem do rastreamento, o parâmetro *Option* para selecionar os eventos de rastreamento ExecutionFlow e o parâmetro *PSHost* para selecionar o ouvinte do host do PowerShell, que envia a saída para o console.
O parâmetro *ListenerOption* adiciona os valores de ProcessId e timestamp ao prefixo da mensagem de rastreamento.

### Exemplo 2: parar um rastreamento

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

Esse comando interrompe o rastreamento do componente ParameterBinding do PowerShell.
Ele usa o parâmetro *Name* para identificar o componente que estava sendo rastreado e o parâmetro *RemoveListener* para identificar o ouvinte de rastreamento.

## PARAMETERS

### -Depurador

Indica que o cmdlet envia a saída de rastreamento para o depurador.
Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Microsoft Visual Studio.
Esse parâmetro também seleciona o ouvinte de rastreamento padrão.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica um arquivo para o qual este cmdlet envia a saída de rastreamento.
Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.
Se você usar esse parâmetro para iniciar o rastreamento, use o parâmetro *RemoveFileListener* para interromper o rastreamento.

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que o cmdlet substitui um arquivo somente leitura.
Use com o parâmetro *FilePath* .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListenerOption

Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.
Os valores aceitáveis para esse parâmetro são:

- Nenhum
- LogicalOperationStack
- Datetime
- Timestamp
- ProcessId
- ThreadId
- Chamadas

None é o padrão.

Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "ProcessID ThreadID".

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica quais componentes são rastreados.
Insira o nome da origem de rastreamento de cada componente.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Opção

Especifica o tipo de eventos que são rastreados.
Os valores aceitáveis para esse parâmetro são:

- Nenhum
- Construtor
- Dispose
- Finalizer
- Método
- Propriedade
- Delegados
- Eventos
- Exceção
- Bloqueio
- Erro
- Errors
- Aviso
- Detalhado
- WriteLine
- Dados
- Escopo
- ExecutionFlow
- Assert
- Tudo

All é o padrão.

Os seguintes valores são combinações de outros valores:

- ExecutionFlow: (Construtor, descarte, finalizador, método, delegados, eventos e escopo)
- Dados: (constructor, Dispose, Finalizer, Property, Verbose e WriteLine)
- Erros: (erro e exceção).

Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "Constructor, Dispose".

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSHost

ndicates que esse cmdlet envia a saída de rastreamento para o host do PowerShell.
Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveFileListener

Interrompe o rastreamento, removendo o ouvinte de rastreamento do arquivo associado ao arquivo especificado.
Digite o caminho e o nome do arquivo de saída de rastreamento.

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveListener

Interrompe o rastreamento, removendo o ouvinte de rastreamento.

Use os seguintes valores com *RemoveListener* :

- Para remover PSHost (console), digite `Host` .
- Para remover o depurador, digite `Debug` .
- Para remover todos os ouvintes de rastreamento, digite `*` .

Para remover o ouvinte de rastreamento de arquivo, use o parâmetro *RemoveFileListener* .

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um nome para **set-tracename** .

## SAÍDAS

### Nenhum ou System. Management. Automation. PSTraceSource

Quando você usa o parâmetro *PassThru* , **set-tracename** gera um objeto **System. Management. Automation. PSTraceSource** que representa a sessão de rastreamento.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas. Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.

  Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.
Eles permitem monitorar quase todos os aspectos da funcionalidade do PowerShell.

  Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.
Para rastrear um componente, você deve identificar sua origem de rastreamento.

  Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.
Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .

* Para iniciar um rastreamento, use o parâmetro *Name* para especificar uma origem de rastreamento e os parâmetros *FilePath* , *Debugger* ou *PSHost* para especificar um ouvinte (um destino para a saída). Use o parâmetro *Options* para determinar os tipos de eventos que são rastreados e o parâmetro *ListenerOption* para configurar a saída de rastreamento.
* Para alterar a configuração de um rastreamento, insira um comando **set-Tracee** como você faria para iniciar um rastreamento. O PowerShell reconhece que a origem do rastreamento já está sendo rastreada. Ele interrompe o rastreamento, adiciona a nova configuração e inicia ou reinicia o rastreamento.
* Para interromper um rastreamento, use o parâmetro *RemoveListener* . Para interromper um rastreamento que usa o ouvinte de arquivo (um rastreamento iniciado usando o parâmetro *FilePath* ), use o parâmetro *RemoveFileListener* . Quando você remove o ouvinte, o rastreamento é interrompido.
* Para determinar quais componentes podem ser rastreados, use Get-TraceSource. As origens de rastreamento para cada módulo são carregadas automaticamente quando o componente está em uso e aparecem na saída de **Get-tracename** .

## LINKS RELACIONADOS

[Get-TraceSource](Get-TraceSource.md)

[Trace-Command](Trace-Command.md)
