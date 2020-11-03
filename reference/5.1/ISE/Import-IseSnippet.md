---
external help file: ISE-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193412"
---
# Import-IseSnippet

## SINOPSE
Importa snippets ISE para a sessão atual

## SYNTAX

### FromFolder (padrão)

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### FromModule

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

O `Import-IseSnippet` cmdlet importa o texto reutilizável "trechos" de um módulo ou um diretório para a sessão atual. Os trechos de código estão imediatamente disponíveis para uso no ISE do Windows PowerShell. Esse cmdlet funciona apenas em Ambiente de Script Integrado do Windows PowerShell (ISE).

Para exibir e usar os trechos importados, no menu ISE do Windows PowerShell **Editar** , clique em **Iniciar trechos de código** ou pressione <kbd>Ctrl</kbd> + <kbd>J</kbd>.

Os snippets importados estão disponíveis apenas na sessão atual. Para importar os trechos de código em todas as sessões de ISE do Windows PowerShell, adicione um `Import-IseSnippet` comando ao seu perfil do Windows PowerShell ou copie os arquivos de trecho para o diretório de trechos de código local `$home\Documents\WindowsPowershell\Snippets` .

Para importar trechos de código, eles devem ser formatados corretamente no trecho de código XML para ISE do Windows PowerShell trechos de código e salvos em arquivos XML Snippet.ps1. Para criar trechos de código qualificados, use o `New-IseSnippet` cmdlet. `New-IseSnippet` Cria um `<SnippetTitle>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório. Você pode mover ou copiar os snippets para o diretório de snippets de um módulo do Windows PowerShell ou para qualquer outro diretório.

O `Get-IseSnippet` cmdlet, que obtém trechos de código criados pelo usuário no diretório de trechos de código local, não obtém trechos de código importados.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: importar trechos de um diretório

Este exemplo importa os trechos de código do `\\Server01\Public\Snippets` diretório para a sessão atual. Ele usa o parâmetro **recurse** para obter trechos de todos os subdiretórios do diretório Snippets.

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### Exemplo 2: importar trechos de código de um módulo

Este exemplo importa os trechos de código do módulo **SnippetModule** . O comando usa o parâmetro **listAvailable** para importar os trechos de código mesmo se o módulo **SnippetModule** não for importado para a sessão do usuário quando o comando for executado.

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### Exemplo 3: localizar trechos de código em módulos

Este exemplo obtém trechos de código em todos os módulos instalados na variável de ambiente PSModulePath.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### Exemplo 4: importar todos os trechos de módulo

Este exemplo importa todos os trechos de todos os módulos instalados para a sessão atual. Normalmente, você não precisa executar um comando como esse porque os módulos que têm trechos de código usarão o `Import-IseSnippet` cmdlet para importá-los para você quando o módulo for importado.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### Exemplo 5: copiar todos os trechos de módulo

Este exemplo copia os arquivos de trecho de todos os módulos instalados para o diretório de trechos de código do usuário atual. Ao contrário de snippets importados, que afetam apenas a sessão atual, snippets copiados estão disponíveis em cada sessão do ISE do Windows PowerShell.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## PARAMETERS

### -ListAvailable

Indica que esse cmdlet obtém trechos de módulos que estão instalados no computador, mesmo que os módulos não sejam importados para a sessão atual. Se esse parâmetro for omitido e o módulo especificado pelo parâmetro de **módulo** não for importado para a sessão atual, a tentativa de obter os trechos de código do módulo falhará.

Esse parâmetro será válido somente quando o parâmetro **Module** for usado no comando.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Módulo

Importa os snippets do módulo especificado para a sessão atual. Não há suporte para caracteres curinga.

Esse parâmetro importa trechos de Snippet.ps1arquivos XML no subdiretório Snippets no caminho do módulo, como `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` .

Esse parâmetro foi projetado para ser usado por autores de módulo em um script de inicialização, como um script especificado na chave **ScriptsToProcess** de um manifesto de módulo. Trechos de código em um módulo não são importados automaticamente com o módulo, mas você pode usar um `Import-IseSnippet` comando para importá-los.

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para o diretório de trechos de código no qual este cmdlet importa trechos.

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Recurse

Indica que este cmdlet importa trechos de todos os subdiretórios do valor do parâmetro **path** .

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

### Nenhum

Este cmdlet não recebe entrada do pipeline.

## SAÍDAS

### Nenhum

Esse cmdlet não gera saída.

## OBSERVAÇÕES

- Você não pode usar o `Get-IseSnippet` cmdlet para obter trechos de código importados. `Get-IseSnippet` Obtém apenas trechos de código no `$home\Documents\WindowsPowerShell\Snippets` diretório.
- `Import-IseSnippet` usa o método estático **Load** de objetos **Microsoft. PowerShell. host. ISE. ISESnippetCollection** . Você também pode usar o método **Load** de trechos de código no modelo de objeto ISE do Windows PowerShell: `$psISE.CurrentPowerShellTab.Snippets.Load()`
- O `New-IseSnippet` cmdlet armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados. Dessa forma, o Windows PowerShell não pode carregá-los em uma sessão em que a diretiva de execução seja **AllSigned** ou **Restricted** . Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.

  Para usar trechos de código criados pelo usuário não assinados que o `Import-IseSnippet` cmdlet retorna, altere a política de execução e reinicie ISE do Windows PowerShell.

  Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## LINKS RELACIONADOS

[Get-IseSnippet](Get-IseSnippet.md)

[New-IseSnippet](New-IseSnippet.md)
