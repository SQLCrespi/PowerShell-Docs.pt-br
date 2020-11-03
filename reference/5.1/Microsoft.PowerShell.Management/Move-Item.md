---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: d3637825e7570e5fb0f3ff77efbc89e9d93974a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193973"
---
# Move-Item

## SINOPSE
Move um item de um local para outro.

## SYNTAX

### Caminho (padrão)

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

### LiteralPath

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## DESCRIPTION

O `Move-Item` cmdlet Move um item, incluindo suas propriedades, conteúdo e itens filho, de um local para outro local.
Os locais devem ter suporte no mesmo provedor.
Por exemplo, ele pode mover um arquivo ou um subdiretório de um diretório para outro ou mover uma subchave do registro de uma chave para outra.
Quando você move um item, ele é adicionado ao novo local e excluído do seu local original.

## EXEMPLOS

### Exemplo 1: mover um arquivo para outro diretório e renomeá-lo

Esse comando move o arquivo "Test.txt" da `C:` unidade para o diretório "E:\temp" e o renomeia de "test.txt" para "tst.txt".

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### Exemplo 2: mover um diretório e seu conteúdo para outro diretório

Esse comando move o diretório "C:\Temp" e seu conteúdo para o diretório "C:\Logs".
O diretório "Temp" e todos os seus subdiretórios e arquivos, em seguida, aparecem no diretório "logs".

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### Exemplo 3: mover todos os arquivos de uma extensão especificada do diretório atual para outro diretório

Esse comando move todos os arquivos de texto ("*. txt") no diretório atual (representado por um ponto ('. ')) para o diretório "C:\Logs".

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### Exemplo 4: mover recursivamente todos os arquivos de uma extensão especificada do diretório atual para outro diretório

Esse comando move todos os arquivos de texto do diretório atual e de todos os subdiretórios, recursivamente, para o diretório "C:\TextFiles".

O comando usa o `Get-ChildItem` cmdlet para obter todos os itens filho no diretório atual (representado pelo ponto \[ \] ) e seus subdiretórios que têm uma *extensão de nome de arquivo ". txt". Ele usa o parâmetro **recurse** para tornar a recuperação recursiva e o parâmetro include para limitar a recuperação a arquivos "* . txt".

O operador de pipeline ( `|` ) envia os resultados desse comando para `Move-Item` , que move os arquivos de texto para o diretório "textfiles".

Se os arquivos que devem ser movidos para "C:\Textfiles" tiverem o mesmo nome, o `Move-Item` exibirá um erro e continuará, mas moverá apenas um arquivo com cada nome para "C:\Textfiles".
Os outros arquivos permanecerão em seus diretórios originais.

Se o diretório "textfiles" (ou qualquer outro elemento do caminho de destino) não existir, o comando falhará.
O diretório ausente não é criado para você, mesmo se você usar o parâmetro **Force** .
`Move-Item` move o primeiro item para um arquivo chamado "textfiles" e, em seguida, exibe um erro explicando que o arquivo já existe.

Além disso, por padrão, `Get-ChildItem` o não move arquivos ocultos.
Para mover arquivos ocultos, use o parâmetro **Force** com `Get-ChildItem` .

Observação: no Windows PowerShell 2,0, ao usar o parâmetro **recurse** do `Get-ChildItem` cmdlet, o valor do parâmetro **Path** deve ser um contêiner.
Use o parâmetro **include** para especificar o filtro de extensão de nome de arquivo. txt ( `Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles` ).

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

### Exemplo 5: mover as chaves e valores do registro para outra chave

Esse comando move as chaves do registro e os valores na chave do registro "MyCompany" em "HKLM\Software" para a chave "MyNewCompany".
O caractere curinga (' * ') indica que o conteúdo da chave "MyCompany" deve ser movido, não a chave em si.
Nesse comando, os nomes de parâmetro de **destino** e **caminho** opcionais são omitidos.

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### Exemplo 6: mover um diretório e seu conteúdo para um subdiretório do diretório especificado

Esse comando move o diretório " \[ logs \` \] de 29 de setembro" (e seu conteúdo) para o \[ diretório "logs 2006 \] ".

O parâmetro **LiteralPath** é usado em vez de **Path** , porque o nome do diretório original inclui colchetes à esquerda e colchetes à direita (" \[ " e " \] ").
O caminho também é colocado entre aspas simples (' '), para que o símbolo de acento grave ( \` ) não seja interpretado incorretamente.

O parâmetro de **destino** não requer um caminho literal, pois a variável de destino também deve ser colocada entre aspas simples, pois inclui colchetes que podem ser interpretados incorretamente.

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

## PARAMETERS

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.
> Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

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

### -Destino

Especifica o caminho para o local onde os itens são movidos.
O padrão é o diretório atual.
Caracteres curinga são permitidos, mas o resultado deve especificar um único local.

Para renomear o item que está sendo movido, especifique um novo nome no valor do parâmetro de **destino** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Accept wildcard characters: True
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

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.
A implementação varia de provedor para provedor.
Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet Move na operação.
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
Accept wildcard characters: True
```

### -LiteralPath

Especifica o caminho para o local atual dos itens.
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

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

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

### -Path

Especifica o caminho para o local atual dos itens.
O padrão é o diretório atual.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UseTransaction

Inclui o comando na transação ativa.
Este parâmetro é válido somente quando uma transação está em andamento.
Para obter mais informações, consulte about_Transactions.

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

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.

## SAÍDAS

### Nenhum ou um objeto que representa o item movido.

Quando você usa o parâmetro *PassThru* , esse cmdlet gera um objeto que representa o item movido.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet moverá arquivos entre unidades com suporte no mesmo provedor, mas moverá os diretórios somente dentro da mesma unidade.

Como um `Move-Item` comando move as propriedades, o conteúdo e os itens filho de um item, todas as movimentações são recursivas por padrão.

Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.
Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .
Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
