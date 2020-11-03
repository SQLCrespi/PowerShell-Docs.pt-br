---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194171"
---
# Get-ItemProperty

## SINOPSE
Obtém as propriedades de um item especificado.

## SYNTAX

### Caminho (padrão)

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

O `Get-ItemProperty` cmdlet obtém as propriedades dos itens especificados.
Por exemplo, você pode usar este cmdlet para obter o valor da propriedade LastAccessTime de um objeto de arquivo.
Você também pode usar este cmdlet para exibir entradas do registro e seus valores.

## EXEMPLOS

### Exemplo 1: obter informações sobre um diretório específico

Esse comando obtém informações sobre o diretório "C:\Windows".

```powershell
Get-ItemProperty C:\Windows
```

### Exemplo 2: obter as propriedades de um arquivo específico

Esse comando obtém as propriedades do arquivo "C:\Test\Weather.xls".
O resultado é canalizado para o `Format-List` cmdlet a fim de exibir a saída como uma lista.

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### Exemplo 3: exibir o nome do valor e os dados das entradas do registro em uma subchave do registro

Esse comando exibe o nome do valor e os dados de cada uma das entradas do registro contidas na subchave do registro "CurrentVersion".
Observe que o comando requer que haja uma unidade do PowerShell denominada `HKLM:` que seja mapeada para o hive "HKEY_LOCAL_MACHINE" do registro.
Uma unidade com esse nome e mapeamento está disponível no PowerShell por padrão.
Como alternativa, o caminho para essa subchave de registro pode ser especificado usando o seguinte caminho alternativo que começa com o nome do provedor seguido por dois-pontos duplos:

"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### Exemplo 4: obter o nome do valor e os dados de uma entrada do registro em uma subchave do registro

Esse comando obtém o nome do valor e os dados da entrada do registro "ProgramFilesDir" na subchave do registro "CurrentVersion".
O comando usa o parâmetro **path** para especificar a subchave e o parâmetro Name para especificar o nome do valor da entrada.

O comando usa uma marca de fundo ou acento grave ( \` ), o caractere de continuação do PowerShell, para continuar o comando na segunda linha.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### Exemplo 5: obter os nomes de valor e os dados das entradas do registro em uma chave do registro

Esse comando obtém os nomes de valor e os dados das entradas do registro na chave do registro "PowerShellEngine".
Os resultados são mostrados na seguinte saída de exemplo.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### Exemplo 6: obter, Formatar e exibir os resultados de valores e dados do registro

Este exemplo mostra como formatar a saída de um `Get-ItemProperty` comando em uma lista para facilitar a visualização dos valores e dados do registro e facilitar a interpretação dos resultados.

O primeiro comando usa o `Get-ItemProperty` cmdlet para obter as entradas do registro na subchave **Microsoft. PowerShell** .
Essa subchave armazena opções para o shell padrão do PowerShell.
Os resultados são mostrados na seguinte saída de exemplo.

A saída mostra que há duas entradas de registro, "Path" e "ExecutionPolicy".
Quando uma chave do registro contém menos de cinco entradas, por padrão, ela é exibida em uma tabela, mas é mais fácil exibir em uma lista.

O segundo comando usa o mesmo `Get-ItemProperty` comando.
No entanto, desta vez, o comando usa um operador de pipeline ( `|` ) para enviar os resultados do comando para o `Format-List` cmdlet.
O `Format-List` comando usa o parâmetro Property com um valor de ' * ' (All) para exibir todas as propriedades dos objetos em uma lista.
Os resultados são mostrados na seguinte saída de exemplo.

A exibição resultante mostra as entradas do registro "Path" e "ExecutionPolicy", juntamente com várias propriedades menos familiares do objeto de chave do registro.
As outras propriedades, prefixadas com o PS, são propriedades de objetos personalizados do PowerShell, como os objetos que representam as chaves do registro.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## PARAMETERS

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação.
O padrão é o usuário atual.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.
Se você digitar um nome de usuário, uma senha será solicitada.

> [!WARNING]
> Nenhum provedor instalado com o Windows PowerShell dá suporte a esse parâmetro.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui da operação.
O valor deste parâmetro qualifica o parâmetro **Path** .
Insira um padrão ou elemento de caminho, como "*.txt".
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Especifica um filtro no formato ou idioma do provedor.
O valor deste parâmetro qualifica o parâmetro **Path** .

A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.
Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.
O valor deste parâmetro qualifica o parâmetro **Path** .
Insira um padrão ou elemento de caminho, como "*.txt".
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para o local atual da propriedade.
Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica o nome da propriedade ou propriedades para recuperar.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o(s) item(ns).

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction

Inclui o comando na transação ativa.
Este parâmetro é válido somente quando uma transação está em andamento.
Para obter mais informações, consulte inclui o comando na transação ativa.
Este parâmetro é válido somente quando uma transação está em andamento.
Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ItemProperty` .

## SAÍDAS

### System. booliano, System. String, System. DateTime

`Get-ItemProperty` Retorna um objeto para cada propriedade de item obtida.
O tipo de objeto depende do objeto que é recuperado.
Por exemplo, em uma unidade de sistema de arquivos, ele pode retornar um arquivo ou pasta.

## OBSERVAÇÕES

O `Get-ItemProperty` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite " `Get-PSProvider` ". Para obter mais informações, consulte about_Providers.

## LINKS RELACIONADOS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)
