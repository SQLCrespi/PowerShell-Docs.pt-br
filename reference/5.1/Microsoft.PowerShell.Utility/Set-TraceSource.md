---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: c6bdb583917ac20ae9df7bd009836b7d1cb9518b
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184368"
---
# Set-TraceSource

## Sinopse
Configura, inicia e para um rastreamento de componentes do PowerShell.

## Sintaxe

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

## Descrição

O `Set-TraceSource` cmdlet configura, inicia e para um rastreamento de um componente do PowerShell. Você pode usá-lo para especificar quais componentes serão rastreados e para onde a saída de rastreamento é enviada.

## Exemplos

### Exemplo 1: rastrear o componente ParameterBinding

```
Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

Esse comando inicia o rastreamento para o componente ParameterBinding do PowerShell. Ele usa o parâmetro **Name** para especificar a origem do rastreamento, o parâmetro **Option** para selecionar os `ExecutionFlow` eventos de rastreamento e o parâmetro **PSHost** para selecionar o ouvinte do host do PowerShell, que envia a saída para o console. O parâmetro **ListenerOption** adiciona os `ProcessID` `TimeStamp` valores e ao prefixo da mensagem de rastreamento.

### Exemplo 2: parar um rastreamento

```
Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

Esse comando interrompe o rastreamento do componente **ParameterBinding** do PowerShell. Ele usa o parâmetro **Name** para identificar o componente que estava sendo rastreado e o parâmetro **RemoveListener** para identificar o ouvinte de rastreamento.

## Parâmetros

### -Depurador

Indica que o cmdlet envia a saída de rastreamento para o depurador. Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Microsoft Visual Studio. Esse parâmetro também seleciona o ouvinte de rastreamento padrão.

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

Especifica um arquivo para o qual este cmdlet envia a saída de rastreamento. Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo. Se você usar esse parâmetro para iniciar o rastreamento, use o parâmetro **RemoveFileListener** para interromper o rastreamento.

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

Indica que o cmdlet substitui um arquivo somente leitura. Use com o parâmetro **FilePath** .

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

Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída. Os valores aceitáveis para esse parâmetro são:

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

`None` é o padrão.

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro **ListenerOption** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

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

Especifica quais componentes são rastreados. Insira o nome da origem de rastreamento de cada componente.
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

Especifica o tipo de eventos que são rastreados. Os valores aceitáveis para esse parâmetro são:

- `None`
- `Constructor`
- `Dispose`
- `Finalizer`
- `Method`
- `Property`
- `Delegates`
- `Events`
- `Exception`
- `Lock`
- `Error`
- `Errors`
- `Warning`
- `Verbose`
- `WriteLine`
- `Data`
- `Scope`
- `ExecutionFlow`
- `Assert`
- `All`

`All` é o padrão.

Os seguintes valores são combinações de outros valores:

- `ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`
- `Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`
- `Errors`: `Error`, `Exception`

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

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

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

Indica que esse cmdlet envia a saída de rastreamento para o host do PowerShell. Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.

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

Interrompe o rastreamento, removendo o ouvinte de rastreamento do arquivo associado ao arquivo especificado. Digite o caminho e o nome do arquivo de saída de rastreamento.

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

Use os seguintes valores com **RemoveListener**:

- Para remover PSHost (console), digite `Host` .
- Para remover o depurador, digite `Debug` .
- Para remover todos os ouvintes de rastreamento, digite `*` .

Para remover o ouvinte de rastreamento de arquivo, use o parâmetro **RemoveFileListener** .

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

## Entradas

### System.String

É possível canalizar uma cadeia de caracteres que contém um nome para `Set-TraceSource` .

## Saídas

### Nenhum ou System. Management. Automation. PSTraceSource

Quando você usa o parâmetro **PassThru** , o `Set-TraceSource` gera um objeto **System. Management. Automation. PSTraceSource** que representa a sessão de rastreamento. Caso contrário, este cmdlet não gera nenhuma saída.

## Observações

- O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas. Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.

  Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários. Eles permitem monitorar quase todos os aspectos da funcionalidade do PowerShell.

  Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente. Para rastrear um componente, você deve identificar sua origem de rastreamento.

  Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário. Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .

- Para iniciar um rastreamento, use o parâmetro **Name** para especificar uma origem de rastreamento e os parâmetros **FilePath**, **Debugger** ou **PSHost** para especificar um ouvinte (um destino para a saída). Use o parâmetro **Options** para determinar os tipos de eventos que são rastreados e o parâmetro **ListenerOption** para configurar a saída de rastreamento.
- Para alterar a configuração de um rastreamento, insira um `Set-TraceSource` comando como você faria para iniciar um rastreamento. O PowerShell reconhece que a origem do rastreamento já está sendo rastreada. Ele interrompe o rastreamento, adiciona a nova configuração e inicia ou reinicia o rastreamento.
- Para interromper um rastreamento, use o parâmetro **RemoveListener** . Para interromper um rastreamento que usa o ouvinte de arquivo (um rastreamento iniciado usando o parâmetro **FilePath** ), use o parâmetro **RemoveFileListener** .
  Quando você remove o ouvinte, o rastreamento é interrompido.
- Para determinar quais componentes podem ser rastreados, use Get-TraceSource. As origens de rastreamento para cada módulo são carregadas automaticamente quando o componente está em uso e aparecem na saída de `Get-TraceSource` .

## Links Relacionados

[Get-TraceSource](Get-TraceSource.md)

[Trace-Command](Trace-Command.md)
