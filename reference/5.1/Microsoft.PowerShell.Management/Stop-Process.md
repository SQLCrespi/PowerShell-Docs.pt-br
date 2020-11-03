---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: 4efa22e8f2a7339e381d92270c1b127054c219cb
ms.sourcegitcommit: 11abf355ac545531c2b04217a08ebe6be609c0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "93195335"
---
# Stop-Process

## SINOPSE
Interrompe um ou mais processos em execução.

## SYNTAX

### ID (padrão)

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Stop-Process** interrompe um ou mais processos em execução.
Você pode especificar um processo por nome do processo ou ID do processo (PID) ou passar um objeto de processo para **Stop-Process** .
**Stop-Process** funciona apenas em processos em execução no computador local.

No Windows Vista e versões posteriores do sistema operacional Windows, para interromper um processo que não pertence ao usuário atual, você deve iniciar o PowerShell usando a opção Executar como administrador.
Além disso, não será solicitada a confirmação, a menos que você especifique o parâmetro *Confirm* .

## EXEMPLOS

### Exemplo 1: parar todas as instâncias de um processo

```
PS C:\> Stop-Process -Name "notepad"
```

Este comando interrompe todas as instâncias do processo do Bloco de notas no computador.
Cada instância do bloco de notas é executada em seu próprio processo.
Ele usa o parâmetro *Name* para especificar os processos, todos com o mesmo nome.
Se você usar o parâmetro *ID* para interromper os mesmos processos, precisaria listar as IDs de processo de cada instância do bloco de notas.

### Exemplo 2: parar uma instância específica de um processo

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

Este comando interrompe uma instância específica do processo do Bloco de notas.
Ele usa a ID do processo, 3952, para identificá-lo.
O parâmetro *Confirm* direciona o PowerShell para avisá-lo antes de parar o processo.
Como o prompt inclui o nome do processo, além de sua ID, essa é a melhor prática.
O parâmetro *PassThru* passa o objeto de processo para o formatador para exibição.
Sem esse parâmetro, não haveria nenhuma exibição após um comando **Stop-Process** .

### Exemplo 3: parar um processo e detectar que ele foi interrompido

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

Essa série de comandos inicia e interrompe o processo de cálculo e, em seguida, detecta os processos que foram interrompidos.

O primeiro comando inicia uma instância da calculadora.

O segundo comando usa **Get-Process** Obtém um objeto que representa o processo Calc e, em seguida, o armazena na variável $p.

O terceiro comando interrompe o processo de cálculo.
Ele usa o parâmetro *InputObject* para passar o objeto para **Stop-Process** .

O último comando obtém todos os processos no computador que estavam em execução, mas que agora são interrompidos.
Ele usa o **Get-Process** para obter todos os processos no computador.
O operador de pipeline (|) passa os resultados para o cmdlet Where-Object, que seleciona aqueles em que o valor da propriedade **HasExited** é $true.
**HasExited** é apenas uma propriedade de objetos de processo.
Para localizar todas as propriedades, digite `Get-Process | Get-Member` .

### Exemplo 4: parar um processo que não pertence ao usuário atual

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

Esses comandos mostram o efeito de usar *Force* para interromper um processo que não pertence ao usuário.

O primeiro comando usa **Get-Process** para obter o processo do Lsass.
Um operador de pipeline envia o processo para **Stop-Process** para interrompê-lo.
Conforme mostrado na saída de exemplo, o primeiro comando falha com uma mensagem de acesso negado, pois esse processo pode ser interrompido somente por um membro do grupo de administradores no computador.

Quando o PowerShell é aberto usando a opção Executar como administrador e o comando é repetido, o PowerShell solicita sua confirmação.

O segundo comando especifica *Force* para suprimir o prompt.
Como resultado, o processo é interrompido sem confirmação.

## PARAMETERS

### -Force

Interrompe os processos especificados sem pedir confirmação.
Por padrão, **Stop-Process** solicita confirmação antes de interromper qualquer processo que não pertence ao usuário atual.

Para localizar o proprietário de um processo, use o `Get-CimInstance` cmdlet para obter um **Win32_Process** objeto que representa o processo e, em seguida, use o método **GetOwner** do objeto.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica as IDs de processo dos processos a serem interrompidos.
Para especificar IDs múltiplas, use vírgulas para separá-las.
Para localizar o PID de um processo, digite `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos de processo a serem interrompidos.
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de processo dos processos a serem interrompidos.
Você pode digitar vários nomes de processo, separados por vírgulas, ou usar caracteres curinga.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Retorna um objeto que representa o processo.
Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Diagnostics.Process

É possível canalizar um objeto de processo para esse cmdlet.

## SAÍDAS

### Nenhum, System. Diagnostics. Process

Esse cmdlet retorna um objeto **System. Diagnostics. Process** que representa o processo interrompido, se você especificar o parâmetro *PassThru* .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Você também pode fazer referência a **Stop-Process** por seus aliases internos, **Kill** e **SPPS** . Para obter mais informações, consulte about_Aliases.

  Você também pode usar as propriedades e métodos do objeto Instrumentação de Gerenciamento do Windows (WMI) **Win32_Process** no Windows PowerShell.
Para obter mais informações, consulte `Get-CimInstance` e o SDK do WMI.

* Ao parar os processos, perceba que parar um processo pode parar o processo e os serviços que dependem do processo.
Em casos extremos, interromper um processo pode parar o funcionamento do Windows.

## LINKS RELACIONADOS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
