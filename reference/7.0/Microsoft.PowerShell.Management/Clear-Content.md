---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 9ffe7510745e92c6863cf08d143f89e214ae9133
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692982"
---
# Clear-Content

## SINOPSE
Exclui o conteúdo de um item, mas não exclui o item.

## SYNTAX

### Caminho (padrão)

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### LiteralPath

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Clear-Content` cmdlet exclui o conteúdo de um item, como excluir o texto de um arquivo, mas ele não exclui o item.
Como resultado, o item existe, mas fica vazio.
O `Clear-Content` é semelhante a `Clear-Item` , mas funciona em itens com conteúdo, em vez de itens com valores.

## EXEMPLOS

### Exemplo 1: excluir todo o conteúdo de um diretório

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

Esse comando exclui todo o conteúdo dos arquivos "init.txt" em todos os subdiretórios do diretório SmpUsers.
Os arquivos não serão excluídos, mas ficam vazios.

### Exemplo 2: excluir o conteúdo de todos os arquivos com um curinga

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

Esse comando exclui o conteúdo de todos os arquivos no diretório atual com a extensão de nome de arquivo ".log", incluindo arquivos com o atributo somente leitura. O asterisco ( \* ) no caminho representa todos os itens no diretório atual. O parâmetro **Force** torna o comando efetivo em arquivos somente leitura. Usando um filtro para restringir o comando a arquivos com a extensão de nome de arquivo. log em vez de especificar \* . log no caminho torna a operação mais rápida.

### Exemplo 3: limpar todos os dados de um fluxo

Este exemplo mostra como o `Clear-Content` cmdlet limpa o conteúdo de um fluxo de dados alternativo, deixando o fluxo intacto.

O primeiro comando usa o `Get-Content` cmdlet para obter o conteúdo do `Zone.Identifier` fluxo no arquivo de Copy-Script.ps1, que foi baixado da Internet.

O segundo comando usa o `Clear-Content` cmdlet para limpar o conteúdo.

O terceiro comando repete o primeiro comando. Ele verifica se o conteúdo está limpo, mas o fluxo permanece. Se o fluxo foi excluído, o comando geraria um erro.

Você pode usar um método como este para limpar o conteúdo de um fluxo de dados alternativo. No entanto, não é a maneira recomendada para eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## PARAMETERS

### -Fluxo

> [!NOTE]
> Esse parâmetro só está disponível no Windows.

Especifica um fluxo de dados alternativo para o conteúdo. Se o fluxo não existir, esse cmdlet o criará. Não há suporte para caracteres curinga.

Stream é um parâmetro dinâmico que o provedor FileSystem adiciona `Clear-Content` .
Esse parâmetro funciona somente em unidades de sistema de arquivos.

Você pode usar o `Clear-Content` cmdlet para alterar o conteúdo do fluxo de dados alternativo Amy, como `Zone.Identifier` . No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet. Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.

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

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell. Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use Invoke-Command.

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

Especifica, como uma matriz de cadeia de caracteres, que esse cmdlet omite do caminho para o conteúdo. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um padrão ou elemento de caminho, como "*.txt". Caracteres curinga são permitidos.

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

Especifica um filtro no formato ou linguagem do provedor. O valor deste parâmetro qualifica o parâmetro **Path**. A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor. Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao recuperar os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

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

Especifica, como uma matriz de cadeia de caracteres, o conteúdo que esse cmdlet limpa. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um padrão ou elemento de caminho, como "*.txt". Caracteres curinga são permitidos.

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

Especifica os caminhos para os itens dos quais o conteúdo é excluído. Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples dizem que o PowerShell não interpreta nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica os caminhos para os itens dos quais o conteúdo é excluído. Caracteres curinga são permitidos. Os caminhos devem ser caminhos para itens, não para contêineres. Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório. Caracteres curinga são permitidos. Este parâmetro é obrigatório, mas o nome do parâmetro ("Path") é opcional.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### Nenhum

Não é possível canalizar objetos para `Clear-Content` .

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhum objeto.

## OBSERVAÇÕES

Você pode usar `Clear-Content` o com o provedor de sistema de arquivos do PowerShell e outros provedores que manipulam conteúdo. Para limpar os itens que não são considerados conteúdo, como itens gerenciados pelo certificado do PowerShell ou pelos provedores de registro, use `Clear-Item` .

O `Clear-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.
Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .
Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Add-Content](Add-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[Set-Content](Set-Content.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
