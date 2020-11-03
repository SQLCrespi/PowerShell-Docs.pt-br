---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 431b768ba909ddbd3671f03fc52789ae56c01019
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193795"
---
# Get-TypeData

## Sinopse
Obtém os dados de tipo estendido na sessão atual.

## Sintaxe

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## Descrição

O `Get-TypeData` cmdlet obtém os dados de tipo estendido na sessão atual. Isso inclui dados de tipo que foram adicionados à sessão por `Types.ps1xml` arquivo e dados de tipo dinâmico que foram adicionados usando o parâmetro do `Update-TypeData` cmdlet.

Você pode usar os dados de tipo estendido que o `Get-TypeData` retorna para examinar os dados de tipo na sessão e enviá-los aos `Update-TypeData` `Remove-TypeData` cmdlets e.

Dados de tipo estendido adiciona propriedades e métodos a objetos no PowerShell. Você pode usar as propriedades e métodos adicionados da mesma maneira que usaria as propriedades e métodos definidos no tipo de objeto. No entanto, ao escrever scripts, lembre-se de que as propriedades e os métodos adicionados podem não estar presentes em todas as sessões do PowerShell.

Para obter mais informações sobre `Types.ps1xml` arquivos, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md). Para obter mais informações sobre os dados de tipo dinâmico que o `Update-TypeData` cmdlet adiciona, consulte `Update-TypeData` .

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## Exemplos

### Exemplo 1: obter todos os dados de tipo estendido

Este exemplo obtém todos os dados de tipo estendido na sessão atual.

 ```powershell
Get-TypeData
```

### Exemplo 2: obter tipos por nome

Este exemplo obtém todos os tipos na sessão atual que têm nomes que contêm eventos.

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### Exemplo 3: obter o bloco de script que cria um valor de propriedade

Este exemplo obtém o bloco de script que cria o valor da propriedade **EventID** de objetos **EventLogEntry** .

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### Exemplo 4: obter o bloco de script que define uma propriedade para um objeto especificado

Este exemplo obtém o bloco de script que define a propriedade **DateTime** de objetos **System. DateTime** no PowerShell.

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

O comando usa o `Get-TypeData` cmdlet para obter os dados de tipo estendido para o tipo **System. DataTime** . O comando obtém a propriedade **Members** do objeto **TypeData** .

A propriedade **Members** contém uma tabela de hash de propriedades e métodos que são definidos por dados de tipo estendido. Cada chave na tabela de hash Members é um nome de propriedade ou método, e cada valor é a definição do valor de propriedade ou método.

O comando obtém a chave **DateTime** em **Membros** e seu valor de propriedade **getscriptblock** .

A saída mostra o bloco de script que cria o valor da propriedade **DateTime** de cada objeto **System. DateTime** no PowerShell.

## Parâmetros

### -TypeName

Especifica os dados de tipo como uma matriz somente para os tipos com os nomes especificados. Por padrão, o `Get-TypeData` Obtém todos os tipos na sessão.

Insira nomes de tipo ou padrões de nome. Os nomes completos ou padrões de nome com caracteres curinga são necessários, mesmo para tipos no namespace System. Há suporte para curingas e o nome do parâmetro **TypeName** é opcional. Você também pode canalizar nomes de tipo para `Get-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System.String

Você pode canalizar nomes de tipo para `Get-TypeData` .

## Saídas

### System. Management. Automation. Runspaces. TypeData

## Observações

`Get-TypeData` Obtém somente os dados de tipo estendido na sessão atual. Ele não gera dados de tipo estendido presentes no computador mas que não foram adicionados à sessão atual, como tipos estendidos que são definidos em módulos que não foram importados para a sessão atual.

## Links relacionados

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Remove-TypeData](Remove-TypeData.md)

[Update-TypeData](Update-TypeData.md)
