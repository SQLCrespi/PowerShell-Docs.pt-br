---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: 4fefb133416b3db6c19c71a916d73fe00f86f3a4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597808"
---
# Out-Host

## SINOPSE
Envia a saída para a linha de comando.

## SYNTAX

### Tudo

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `Out-Host` cmdlet envia a saída para o host do PowerShell para exibição. O host exibe a saída na linha de comando. Como `Out-Host` o é o padrão, você não precisa especificá-lo a menos que queira usar seus parâmetros.

`Out-Host` é automaticamente anexado a todos os comandos que são executados. Ele passa a saída do pipeline para o host que executa o comando. `Out-Host` ignora as sequências de escape ANSI. As sequências de escape são tratadas pelo host. `Out-Host` passa sequências de escape ANSI para o host sem tentar interpretá-las ou alterá-las.

## EXEMPLOS

### Exemplo 1: exibir uma página de saída por vez

Este exemplo exibe o sistema processa uma página por vez.

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

`Get-Process` Obtém os processos do sistema e envia os objetos por meio do pipeline. `Out-Host` usa o parâmetro **paging** para exibir uma página de dados de cada vez.

### Exemplo 2: usar uma variável como entrada

Este exemplo usa objetos armazenados em uma variável como entrada para `Out-Host` .

```powershell
$io = Get-History
Out-Host -InputObject $io
```

`Get-History` Obtém o histórico da sessão do PowerShell e armazena os objetos na `$io` variável.
`Out-Host` usa o parâmetro **InputObject** para especificar a `$io` variável e exibe o histórico.

## PARAMETERS

### -InputObject

Especifica os objetos que são gravados no console. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Paginação

Indica que `Out-Host` o exibe uma página de saída por vez e aguarda a entrada do usuário antes que as páginas restantes sejam exibidas. Por padrão, toda a saída é exibida em uma única página. O tamanho da página é determinado pelas características do host.

Pressione a barra de <kbd>espaço</kbd> para exibir a próxima página de saída ou a tecla <kbd>Enter</kbd> para exibir a próxima linha de saída. Pressione <kbd>Q</kbd> para sair.

A **paginação** é semelhante ao comando **more** .

> [!NOTE]
> O host do ISE do PowerShell não dá suporte ao parâmetro de **paginação** .

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode enviar objetos pelo pipeline para o `Out-Host` .

## SAÍDAS

### Nenhum

`Out-Host` não gera nenhuma saída. Ele envia objetos para o host para exibição.

## OBSERVAÇÕES

O parâmetro de **paginação** não tem suporte de todos os hosts do PowerShell. Por exemplo, se você usar o parâmetro de **paginação** no ISE do PowerShell, o seguinte erro será exibido: `out-lineoutput : The method or operation is not implemented.`

Os cmdlets que contêm o verbo **out** , `Out-` , não formatam objetos. Eles renderizam objetos e os enviam para o destino de exibição especificado. Se você enviar um objeto não formatado para um `Out-` cmdlet, o cmdlet o enviará a um cmdlet de formatação antes de renderizá-lo.

Os `Out-` cmdlets não têm parâmetros para nomes ou caminhos de arquivo. Para enviar dados a um `Out-` cmdlet, use o pipeline para enviar a saída de um comando do PowerShell para o cmdlet. Ou você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar os dados para o cmdlet.

`Out-Host` envia dados, mas não produz nenhum objeto de saída. Se você canalizar a saída do `Out-Host` para o `Get-Member` cmdlet, o `Get-Member` relatará que nenhum objeto foi especificado.

## LINKS RELACIONADOS

[Clear-Host](Clear-Host.md)

[Out-Default](Out-Default.md)

[Out-File](../Microsoft.PowerShell.Utility/Out-File.md)

[Out-Null](Out-Null.md)

[Out-Printer](../Microsoft.PowerShell.Utility/Out-Printer.md)

[Out-String](../Microsoft.PowerShell.Utility/Out-String.md)

[Write-Host](../Microsoft.PowerShell.Utility/Write-Host.md)

