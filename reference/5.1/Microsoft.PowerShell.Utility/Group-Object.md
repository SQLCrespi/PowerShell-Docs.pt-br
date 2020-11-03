---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: df06d5cd83472c80a395e3dcf63c4d331c5da6bb
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195156"
---
# Group-Object

## SINOPSE
Objetos de grupos que contêm o mesmo valor para as propriedades especificadas.

## SYNTAX

### Tabela

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

O `Group-Object` cmdlet exibe objetos em grupos com base no valor de uma propriedade especificada.
`Group-Object` Retorna uma tabela com uma linha para cada valor de propriedade e uma coluna que exibe o número de itens com esse valor.

Se você especificar mais de uma propriedade, `Group-Object` primeiro as agrupará pelos valores da primeira propriedade e, em seguida, dentro de cada grupo de propriedades, ela agrupará pelo valor da próxima propriedade.

## EXEMPLOS

### Exemplo 1: agrupar arquivos por extensão

Este exemplo obtém recursivamente os arquivos em `$PSHOME` e os agrupa por extensão de nome de arquivo. A saída é enviada para o `Sort-Object` cmdlet, que os classifica pela contagem de arquivos encontrados para a extensão fornecida. O **nome** vazio representa diretórios.

Este exemplo usa o parâmetro **NoElement** para omitir os membros do grupo.

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### Exemplo 2: agrupar inteiros por chances e até mesmo

Este exemplo mostra como usar blocos de script como o valor do parâmetro **Property** . Esse comando exibe os inteiros de 1 a 20, agrupados por chances e até mesmo.

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### Exemplo 3: agrupar eventos de log de eventos por EntryType

Este exemplo exibe as 1.000 entradas mais recentes no log de eventos do sistema, agrupadas por **EntryType** .

Na saída, a coluna **Count** representa o número de entradas em cada grupo. A coluna **nome** representa os valores **EventType** que definem um grupo. A coluna **grupo** representa os objetos em cada grupo.

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### Exemplo 4: agrupar processos por classe de prioridade

Este exemplo demonstra o efeito do parâmetro **NoElement** . Esses comandos agrupam os processos no computador por classe de prioridade.

O primeiro comando usa o `Get-Process` cmdlet para obter os processos no computador e envia os objetos por meio do pipeline. `Group-Object`agrupa os objetos pelo valor da propriedade **PriorityClass** do processo.

O segundo exemplo usa o parâmetro **NoElement** para eliminar os membros do grupo da saída. O resultado é uma tabela com apenas o valor da propriedade **Count** e **Name** .

Os resultados são mostrados na seguinte saída de exemplo.

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### Exemplo 5: agrupar processos por nome

O exemplo a seguir usa `Group-Object` para agrupar várias instâncias de processos em execução no computador local. `Where-Object` exibe os processos com mais de uma instância.

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### Exemplo 6: agrupar objetos em uma tabela de hash

Este exemplo usa os parâmetros **AsHashTable** e **AsString** para retornar os grupos em uma tabela de hash, como uma coleção de pares chave-valor.

Na tabela de hash resultante, cada valor de propriedade é uma chave e os elementos de grupo são os valores.
Como cada chave é uma propriedade do objeto de tabela de hash, você pode usar a notação de ponto para exibir os valores.

O primeiro comando obtém os `Get` `Set` cmdlets e na sessão, agrupa-os por verbo, retorna os grupos como uma tabela de hash e salva a tabela de hash na `$A` variável.

O segundo comando exibe a tabela de hash no `$A` . Há dois pares chave-valor, um para os `Get` cmdlets e um para os `Set` cmdlets.

O terceiro comando usa a notação de ponto `$A.Get` para exibir os valores da chave **Get** em `$A` . Os valores são objeto **CmdletInfo** . O parâmetro **AsString** não converte os objetos nos grupos para cadeias de caracteres.

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation       2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                2.0.0.0    AppLocker
...
```

## PARAMETERS

### -AsHashTable

Indica que esse cmdlet retorna o grupo como uma tabela de hash. As chaves da tabela de hash são os valores de propriedade pelos quais os objetos são agrupados. Os valores da tabela de hash são os objetos que têm o valor da propriedade.

Por si só, o parâmetro **AsHashTable** retorna cada tabela de hash na qual cada chave é uma instância do objeto agrupado. Quando usado com o parâmetro **AsString** , as chaves na tabela de hash são cadeias de caracteres.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Indica que esse cmdlet converte as chaves da tabela de hash em cadeias de caracteres. Por padrão, as chaves de tabela de hash são instâncias de objeto agrupado. Esse parâmetro é válido somente quando usado com o parâmetro **AsHashTable** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaseSensitive

Indica que esse cmdlet torna o agrupamento diferencia maiúsculas de minúsculas. Sem esse parâmetro, os valores de propriedade dos objetos em um grupo podem ter diferentes casos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Especifica a cultura a ser usada ao comparar cadeias de caracteres.

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

### -InputObject

Especifica os objetos ao grupo. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Group-Object` , o `Group-Object` recebe um objeto que representa a coleção. Como resultado, ele cria um único grupo com esse objeto como seu membro.

Para agrupar os objetos em uma coleção, redirecione os objetos para `Group-Object` .

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

### -NoElement

Indica que esse cmdlet omite os membros de um grupo dos resultados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Especifica as propriedades de agrupamento. Os objetos são organizados em grupos com base no valor da propriedade especificada.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Expressão- `<string>` ou `<script block>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Group-Object` .

## SAÍDAS

### Microsoft. PowerShell. Commands. GroupInfo ou System. Collections. Hashtable

Quando você usa o parâmetro **AsHashTable** , o `Group-Object` retorna um objeto **Hashtable** .
Caso contrário, ele retorna um objeto **GroupInfo** .

## OBSERVAÇÕES

Você pode usar o parâmetro **GroupBy** dos cmdlets de formatação, como `Format-Table` e `Format-List` , para agrupar objetos. Ao contrário de `Group-Object` , que cria uma única tabela com uma linha para cada valor de propriedade, os parâmetros **GroupBy** criam uma tabela para cada valor de propriedade com uma linha para cada item que tem o valor da propriedade.

`Group-Object` não exige que os objetos que estão sendo agrupados sejam do mesmo tipo de estrutura Microsoft .NET. Ao agrupar objetos de diferentes tipos de .NET Framework, `Group-Object` o usa as seguintes regras:

- Mesmos nomes e tipos de propriedade.

  Se os objetos têm uma propriedade com o nome especificado e os valores de propriedade o mesmo tipo .NET Framework, os valores de propriedade são agrupados usando as mesmas regras que devem ser usadas para objetos do mesmo tipo.

- Mesmos nomes de propriedade, tipos diferentes.

  Se os objetos tiverem uma propriedade com o nome especificado, mas os valores de propriedade tiverem um tipo de .NET Framework diferente em objetos diferentes, o `Group-Object` usará o tipo de .NET Framework da primeira ocorrência da propriedade como o tipo de .NET Framework para esse grupo de propriedades. Quando um objeto tem uma propriedade com um tipo diferente, o valor da propriedade é convertido no tipo daquele grupo. Se a conversão de tipo falhar, o objeto não está incluído no grupo.

- Propriedades ausentes.

  Objetos que não têm uma propriedade especificada não podem ser agrupados. Os objetos que não são agrupados aparecem na saída final do objeto **GroupInfo** em um grupo chamado `AutomationNull.Value` .

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
