---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: 4e6d7e584350d25816dbc32ea35a50d916d9ffe4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193788"
---
# Import-Clixml

## SINOPSE
Importa um arquivo CLIXML e cria objetos correspondentes no PowerShell.

## SYNTAX

### ByPath (padrão)

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### ByLiteralPath

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Import-Clixml` cmdlet importa um arquivo XML Common Language Infrastructure (CLI) com dados que representam Microsoft .net objetos do Framework e cria os objetos do PowerShell. Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).

Um uso valioso do `Import-Clixml` em computadores Windows é importar credenciais e proteger as cadeias de caracteres que foram exportadas como XML seguro usando o `Export-Clixml` . Para obter um exemplo, consulte o exemplo 2.

`Import-Clixml` usa a BOM (marca de ordem de byte) para detectar o formato de codificação do arquivo. Se o arquivo não tiver uma BOM, ele assumirá que a codificação é UTF8.

## EXEMPLOS

### Exemplo 1: importar um arquivo serializado e recriar um objeto

Este exemplo usa o `Export-Clixml` cmdlet para salvar uma cópia serializada das informações do processo retornadas pelo `Get-Process` . `Import-Clixml` Recupera o conteúdo do arquivo serializado e recria um objeto que é armazenado na `$Processes` variável.

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### Exemplo 2: importar um objeto de credencial de segurança

Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.

> [!IMPORTANT]
> `Export-Clixml` o só exporta credenciais criptografadas no Windows. Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas em texto sem formatação.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows.
A criptografia garante que apenas sua conta de usuário possa descriptografar o conteúdo do objeto de credencial. O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.

No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` . Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.

Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.

Para importar a credencial automaticamente para o script, execute os dois comandos finais. Execute `Import-Clixml` para importar o objeto de credencial protegido para o script. Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.

## PARAMETERS

### -Primeiro

Obtém somente o número especificado de objetos. Insira o número de objetos a obter.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTotalCount

Relata o número total de objetos no conjunto de dados seguido pelos objetos selecionados. Se o cmdlet não puder determinar a contagem total, ele exibirá a **contagem total desconhecida** . O inteiro tem uma propriedade de **precisão** que indica a confiabilidade do valor total da contagem. O valor de **precisão** varia de `0.0` até `1.0` onde `0.0` significa que o cmdlet não pôde contar os objetos, `1.0` significa que a contagem é exata e um valor entre `0.0` e `1.0` indica uma estimativa cada vez mais confiável.

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

### -LiteralPath

Especifica o caminho para os arquivos XML. Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho para os arquivos XML.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Ignorar

Ignora o número especificado de objetos e obtém os objetos restantes. Insira o número de objetos a ignorar.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

Você pode canalizar uma cadeia de caracteres que contém um caminho para `Import-Clixml` .

## SAÍDAS

### PSObject

`Import-Clixml` retorna objetos que foram desserializados dos arquivos XML armazenados.

## OBSERVAÇÕES

Ao especificar vários valores para um parâmetro, use vírgulas para separá-los. Por exemplo, `<parameter-name> <value1>, <value2>`.

## LINKS RELACIONADOS

[Export-Clixml](Export-Clixml.md)

[Apresentando a serialização XML](/dotnet/standard/serialization/introducing-xml-serialization)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Armazenar credenciais com segurança no disco](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[Usar o PowerShell para passar credenciais para sistemas herdados](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)
