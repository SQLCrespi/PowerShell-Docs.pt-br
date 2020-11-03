---
external help file: ISE-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194860"
---
# Get-IseSnippet

## SINOPSE
Obtém snippets criados pelo usuário.

## SYNTAX

```
Get-IseSnippet [<CommonParameters>]
```

## DESCRIPTION

O `Get-IseSnippet` cmdlet obtém os arquivos ps1xml que contêm trechos de texto reutilizáveis que o usuário criou. Ele funciona apenas em Ambiente de Script Integrado do Windows PowerShell (ISE).

Quando você usa o `New-IseSnippet` cmdlet para criar um trecho de código, o `New-IseSnippet` cria um `<SnippetTitle>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório.
`Get-IseSnippet` Obtém os arquivos de trecho de código no diretório de trechos de código.

Esse cmdlet não obtém trechos de código ou trechos de código internos que são importados de módulos por meio do `Import-IseSnippet` cmdlet.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: obter todos os trechos de código definidos pelo usuário

Este exemplo obtém todos os trechos de código definidos pelo usuário no diretório Snippets.

```powershell
Get-IseSnippet
```

### Exemplo 2: copiar todos os trechos de código definidos pelo usuário de computadores remotos para um diretório compartilhado

Este exemplo copia todos os trechos de código criados pelo usuário de um grupo de computadores remotos para um diretório de trechos de código compartilhado.

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

`Invoke-Command` é executado `Get-IseSnippet` nos computadores do `Servers.txt` arquivo. Um operador de pipeline ( `|` ) envia os arquivos de trecho para o `Copy-Item` cmdlet, que os copia para o diretório especificado pelo parâmetro de **destino** .

### Exemplo 3: exibir o título e o texto de cada trecho em um computador local

Este exemplo usa os `Get-IseSnippet` `Select-Xml` cmdlets e para exibir o título e o texto de cada trecho no computador local.

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### Exemplo 4: exibir o título e a descrição de todos os trechos de código na sessão

Este exemplo exibe o título e a descrição de todos os trechos de código na sessão, incluindo trechos de código internos, trechos de código definidos pelo usuário e trechos importados.

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

A `$PSISE` variável representa o programa host ISE do Windows PowerShell. A propriedade **CurrentPowerShellTab** da `$PSISE` variável representa a sessão atual. A propriedade **Snippets** representa snippets na sessão atual.

O `$PSISE.CurrentPowerShellTab.Snippets` comando retorna um objeto **Microsoft. PowerShell. host. ISE. ISESnippet** que representa um trecho de código, ao contrário do `Get-IseSnippet` cmdlet. `Get-IseSnippet` Retorna um objeto File (System. IO. FileInfo) que representa um arquivo de trecho de código.

O `Format-Table` cmdlet exibe as propriedades **DisplayTitle** e **Description** dos trechos de código em uma tabela.

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### System. IO. FileInfo

Esse cmdlet retorna um objeto de arquivo que representa o arquivo de trecho de código.

## OBSERVAÇÕES

* O `New-IseSnippet` cmdlet armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados. Desse modo, o Windows PowerShell não pode adicioná-los a uma sessão em que a diretiva de execução é **AllSigned** ou **Restricted** . Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.

  Para usar trechos de código criados pelo usuário não assinados que o `Get-IseSnippet` cmdlet retorna, altere a política de execução e reinicie ISE do Windows PowerShell.

  Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## LINKS RELACIONADOS

[New-IseSnippet](New-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
