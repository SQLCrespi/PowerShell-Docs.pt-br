---
external help file: ISE-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193411"
---
# New-IseSnippet

## SINOPSE
Cria um snippet de código do ISE do Windows PowerShell.

## SYNTAX

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

O `New-ISESnippet` cmdlet cria um "Trecho" de texto reutilizável para ISE do Windows PowerShell. Você pode usar snippets para adicionar texto ao painel Script ou painel Comando no ISE do Windows PowerShell. Este cmdlet está disponível apenas no ISE do Windows PowerShell.

A partir do Windows PowerShell 3.0, o ISE do Windows PowerShell inclui uma coleção de snippets internos. O `New-ISESnippet` cmdlet permite que você crie seus próprios trechos de código para adicionar à coleção interna. Você pode exibir, alterar, adicionar, excluir e compartilhar arquivos de snippet e incluí-los em módulos do Windows PowerShell. Para ver os trechos de código no ISE do Windows PowerShell, no menu **Editar** , selecione **Iniciar trechos de código** ou pressione <kbd>Ctrl</kbd> + <kbd>J</kbd>.

O `New-ISESnippet` cmdlet cria um `<Title>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório com o título que você especificar. Para incluir um arquivo de snippet em um módulo que você está criando, adicione o arquivo de snippet a um subdiretório Snippets do seu diretório do módulo.

Você não pode usar trechos de código criados pelo usuário em uma sessão na qual a política de execução é **restrita** ou **AllSigned** .

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: criar um trecho de Comment-Based ajuda

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

Este comando cria um snippet Comment-BasedHelp para o ISE do Windows PowerShell. Ele cria um arquivo chamado `Comment-BasedHelp.snippets.ps1xml` no diretório trechos de código do usuário `$home\Documents\WindowsPowerShell\Snippets` .

### Exemplo 2: criar um trecho de código obrigatório

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

Este exemplo cria um trecho de código chamado **obrigatório** para ISE do Windows PowerShell. O primeiro comando salva o texto do trecho na `$M` variável. O segundo comando usa o `New-ISESnippet` cmdlet para criar o trecho de código. O comando usa o parâmetro **Force** para substituir um snippet anterior com o mesmo nome.

### Exemplo 3: copiar um trecho obrigatório de uma pasta para uma pasta de destino

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

Esse comando usa o `Copy-Item` cmdlet para copiar o trecho **obrigatório** da pasta onde `New-ISESnippet` o coloca no compartilhamento de arquivos Server\Share.

## PARAMETERS

### -Autor

Especifica o autor do trecho de código. O campo autor aparece no arquivo de snippet, mas ele não aparece quando você clica no nome do snippet no ISE do Windows PowerShell.

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

### -CaretOffset

Especifica o caractere do texto de trecho de código no qual esse cmdlet coloca o cursor. Insira um número inteiro que representa a posição do cursor, com "1" representando o primeiro caractere de texto. O valor padrão, 0 (zero), posiciona o cursor imediatamente antes do primeiro caractere de texto. Este parâmetro não recua o texto do snippet.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Especifica uma descrição do trecho de código. O valor de descrição é exibido quando você clica no nome do snippet no ISE do Windows PowerShell. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet substitui arquivos de trecho de código com o mesmo nome no mesmo local. Por padrão, `New-ISESnippet` o não substitui arquivos.

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

### -Texto

Especifica o valor de texto que é adicionado quando você seleciona o snippet. O texto do snippet é exibido quando você clica no nome desse snippet, no ISE do Windows PowerShell. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Especifica um título ou nome para o snippet. O título também nomeia o arquivo de snippet. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Este cmdlet não recebe entrada do pipeline.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

`New-IseSnippet` armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados. Desse modo, o Windows PowerShell não pode adicioná-los a uma sessão em que a diretiva de execução é **AllSigned** ou **Restricted** . Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.

Se você usar o `New-IseSnippet` cmdlet em uma sessão **restrita** ou **AllSigned** , o trecho será criado, mas uma mensagem de erro será exibida quando o Windows PowerShell tentar adicionar o trecho recém-criado à sessão. Para usar o novo snippet (e outros snippets não assinados criados pelo usuário), altere a diretiva de execução e, em seguida, reinicie o ISE do Windows PowerShell.

Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte about_Execution_Policies.

- Para alterar um trecho de código, edite o arquivo de trecho de código. Você pode editar arquivos de trecho de código no painel de script de ISE do Windows PowerShell.
- Para excluir um trecho de código que você adicionou, exclua o arquivo de trecho de código.
- Não é possível excluir um trecho de código interno, mas você pode ocultar todos os trechos de código internos usando o "$psise. Options. ShowDefaultSnippets = $false ".
- Você pode criar um trecho de código que tenha o mesmo nome de um trecho de código interno. Os dois snippets aparecem no menu de snippet, no ISE do Windows PowerShell.

## LINKS RELACIONADOS

[Get-IseSnippet](Get-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
