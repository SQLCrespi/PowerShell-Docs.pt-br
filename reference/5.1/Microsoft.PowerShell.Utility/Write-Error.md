---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: 51698fa0ac5b12a76dec10717d01ef1ec188221c
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196410"
---
# Write-Error

## SINOPSE
Grava um objeto no fluxo de erros.

## SYNTAX

### Noexception (padrão)

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### COMException

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### ErrorRecord

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Write-Error` cmdlet declara um erro de não finalização. Por padrão, os erros serão enviados no fluxo de erros para o programa do host para serem exibidos, juntamente com a saída.

Para gravar um erro não fatal, digite uma cadeia de caracteres de mensagem de erro, um objeto **ErrorRecord** ou um **Exception** . Use os outros parâmetros do `Write-Error` para popular o registro de erro.

Erros não fatais gravam um erro no fluxo de erros, mas não param o processamento do comando.
Se um erro não fatal for declarado em um item em uma coleção de itens de entrada, o comando continuará a processar os outros itens na coleção.

Para declarar um erro de encerramento, use a `Throw` palavra-chave.
Para obter mais informações, consulte [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).

## EXEMPLOS

### Exemplo 1: gravar um erro para o objeto RegistryKey

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

Esse comando declara um erro de não finalização quando o `Get-ChildItem` cmdlet retorna um `Microsoft.Win32.RegistryKey` objeto, como os objetos nas `HKLM:` `HKCU:` unidades ou do provedor de registro do PowerShell.

### Exemplo 2: gravar uma mensagem de erro no console

```powershell
Write-Error "Access denied."
```

Esse comando declara um erro não fatal e grava um erro "Acesso negado". O comando usa o parâmetro **Message** para especificar a mensagem, mas omite o nome do parâmetro **Message** opcional.

### Exemplo 3: gravar um erro no console e especificar a categoria

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

Esse comando declara um erro não fatal e especifica uma categoria de erro.

### Exemplo 4: gravar um erro usando um objeto de exceção

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

Este comando usa um objeto **Exception** para declarar um erro não fatal.

O primeiro comando usa uma tabela de hash para criar o objeto **System.Exception** . Ele salva o objeto de exceção na `$E` variável. Você pode usar uma tabela de hash para criar qualquer objeto de um tipo que possui um construtor nulo.

O segundo comando usa o `Write-Error` cmdlet para declarar um erro de não finalização. O valor do parâmetro de **exceção** é o objeto de **exceção** na `$E` variável.

## PARAMETERS

### -Categoria

Especifica a categoria do erro. O valor padrão não é **especificado** . Os valores aceitáveis para esse parâmetro são:

- NotSpecified
- OpenError
- CloseError
- DeviceError
- DeadlockDetected
- InvalidArgument
- InvalidData
- InvalidOperation
- InvalidResult
- Invalidartype
- MetadataError
- NotImplemented
- Não instalado
- ObjectNotFound
- OperationStopped
- OperationTimeout
- SyntaxError
- ParserError
- PermissionDenied
- ResourceBusy
- ResourceExists
- ResourceUnavailable
- ReadError
- WriteError
- FromStdErr
- SecurityError
- ProtocolError
- ConnectionError
- AuthenticationError
- LimitsExceeded
- QuotaExceeded
- Não habilitado

Para obter informações sobre as categorias de erro, consulte [Enumeração ErrorCategory](https://go.microsoft.com/fwlink/?LinkId=143600).

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### -CategoryActivity

Especifica a ação que causou o erro.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CategoryReason

Especifica como ou por que a atividade causou o erro.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CategoryTargetName

Especifica o nome do objeto que estava sendo processado quando o erro ocorreu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CategoryTargetType

Especifica o tipo do objeto que estava sendo processado quando o erro ocorreu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorID

Especifica uma cadeia de caracteres de identificação para identificar o erro. A cadeia de caracteres deve ser exclusiva para o erro.

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorRecord

Especifica um objeto de registro de erro que representa o erro. Usa as propriedades do objeto para descrever o erro.

Para criar um objeto de registro de erro, use o `New-Object` cmdlet ou obtenha um objeto de registro de erro da matriz na `$Error` variável automática.

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exceção

Especifica um objeto de exceção que representa o erro. Usa as propriedades do objeto para descrever o erro.

Para criar um objeto de exceção, use uma tabela de hash ou use o `New-Object` cmdlet.

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mensagem

Especifica o texto da mensagem de erro. Se a expressão incluir espaços ou caracteres especiais, coloque-a entre aspas. Você também pode canalizar uma cadeia de caracteres de mensagem para `Write-Error` .

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Recomendadoaction

Especifica a ação que o usuário deve executar para resolver ou impedir o erro.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetObject

Especifica o objeto que estava sendo processado quando o erro ocorreu. Insira o objeto, uma variável que contém o objeto ou um comando que obtém o objeto.

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
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

É possível canalizar uma cadeia de caracteres que contém uma mensagem de erro para `Write-Error` .

## SAÍDAS

### Objeto de erro

`Write-Error` grava somente no fluxo de erro. Ele não retorna nenhum objeto.

## OBSERVAÇÕES

`Write-Error` Não altera o valor da `$?` variável automática, portanto, não sinaliza uma condição de erro de encerramento. Para sinalizar um erro de encerramento, use o método [$PSCmdlet. WriteError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) .

## LINKS RELACIONADOS

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
