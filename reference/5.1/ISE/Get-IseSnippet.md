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
# <span data-ttu-id="5ad6f-103">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="5ad6f-103">Get-IseSnippet</span></span>

## <span data-ttu-id="5ad6f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5ad6f-104">SYNOPSIS</span></span>
<span data-ttu-id="5ad6f-105">Obtém snippets criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-105">Gets snippets that the user created.</span></span>

## <span data-ttu-id="5ad6f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5ad6f-106">SYNTAX</span></span>

```
Get-IseSnippet [<CommonParameters>]
```

## <span data-ttu-id="5ad6f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5ad6f-107">DESCRIPTION</span></span>

<span data-ttu-id="5ad6f-108">O `Get-IseSnippet` cmdlet obtém os arquivos ps1xml que contêm trechos de texto reutilizáveis que o usuário criou.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-108">The `Get-IseSnippet` cmdlet gets the PS1XML files that contain reusable text snippets that the user created.</span></span> <span data-ttu-id="5ad6f-109">Ele funciona apenas em Ambiente de Script Integrado do Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="5ad6f-109">It works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="5ad6f-110">Quando você usa o `New-IseSnippet` cmdlet para criar um trecho de código, o `New-IseSnippet` cria um `<SnippetTitle>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-110">When you use the `New-IseSnippet` cmdlet to create a snippet, `New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
<span data-ttu-id="5ad6f-111">`Get-IseSnippet` Obtém os arquivos de trecho de código no diretório de trechos de código.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-111">`Get-IseSnippet` gets the snippet files in the Snippets directory.</span></span>

<span data-ttu-id="5ad6f-112">Esse cmdlet não obtém trechos de código ou trechos de código internos que são importados de módulos por meio do `Import-IseSnippet` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-112">This cmdlet does not get built-in snippets or snippets that are imported from modules through the `Import-IseSnippet` cmdlet.</span></span>

<span data-ttu-id="5ad6f-113">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="5ad6f-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5ad6f-114">EXAMPLES</span></span>

### <span data-ttu-id="5ad6f-115">Exemplo 1: obter todos os trechos de código definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5ad6f-115">Example 1: Get all user-defined snippets</span></span>

<span data-ttu-id="5ad6f-116">Este exemplo obtém todos os trechos de código definidos pelo usuário no diretório Snippets.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-116">This example gets all user-define snippets in the Snippets directory.</span></span>

```powershell
Get-IseSnippet
```

### <span data-ttu-id="5ad6f-117">Exemplo 2: copiar todos os trechos de código definidos pelo usuário de computadores remotos para um diretório compartilhado</span><span class="sxs-lookup"><span data-stu-id="5ad6f-117">Example 2: Copy all user-defined snippets from remote computers to a shared directory</span></span>

<span data-ttu-id="5ad6f-118">Este exemplo copia todos os trechos de código criados pelo usuário de um grupo de computadores remotos para um diretório de trechos de código compartilhado.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-118">This example copies all of the user-created snippets from a group of remote computers to a shared Snippets directory.</span></span>

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

<span data-ttu-id="5ad6f-119">`Invoke-Command` é executado `Get-IseSnippet` nos computadores do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-119">`Invoke-Command` runs `Get-IseSnippet` on the computers in the `Servers.txt` file.</span></span> <span data-ttu-id="5ad6f-120">Um operador de pipeline ( `|` ) envia os arquivos de trecho para o `Copy-Item` cmdlet, que os copia para o diretório especificado pelo parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="5ad6f-120">A pipeline operator (`|`) sends the snippet files to the `Copy-Item` cmdlet, which copies them to the directory that is specified by the **Destination** parameter.</span></span>

### <span data-ttu-id="5ad6f-121">Exemplo 3: exibir o título e o texto de cada trecho em um computador local</span><span class="sxs-lookup"><span data-stu-id="5ad6f-121">Example 3: Display the title and text of each snippet on a local computer</span></span>

<span data-ttu-id="5ad6f-122">Este exemplo usa os `Get-IseSnippet` `Select-Xml` cmdlets e para exibir o título e o texto de cada trecho no computador local.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-122">This example uses the `Get-IseSnippet` and `Select-Xml` cmdlets to display the title and text of each snippet on the local computer.</span></span>

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

### <span data-ttu-id="5ad6f-123">Exemplo 4: exibir o título e a descrição de todos os trechos de código na sessão</span><span class="sxs-lookup"><span data-stu-id="5ad6f-123">Example 4: Display the title and description of all snippets in the session</span></span>

<span data-ttu-id="5ad6f-124">Este exemplo exibe o título e a descrição de todos os trechos de código na sessão, incluindo trechos de código internos, trechos de código definidos pelo usuário e trechos importados.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-124">This example displays the title and description of all snippets in the session, including built-in snippets, user-defined snippets, and imported snippets.</span></span>

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

<span data-ttu-id="5ad6f-125">A `$PSISE` variável representa o programa host ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-125">The `$PSISE` variable represents the Windows PowerShell ISE host program.</span></span> <span data-ttu-id="5ad6f-126">A propriedade **CurrentPowerShellTab** da `$PSISE` variável representa a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-126">The **CurrentPowerShellTab** property of the `$PSISE` variable represent the current session.</span></span> <span data-ttu-id="5ad6f-127">A propriedade **Snippets** representa snippets na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-127">The **Snippets** property represents snippets in the current session.</span></span>

<span data-ttu-id="5ad6f-128">O `$PSISE.CurrentPowerShellTab.Snippets` comando retorna um objeto **Microsoft. PowerShell. host. ISE. ISESnippet** que representa um trecho de código, ao contrário do `Get-IseSnippet` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-128">The `$PSISE.CurrentPowerShellTab.Snippets` command returns a **Microsoft.PowerShell.Host.ISE.ISESnippet** object that represents a snippet, unlike the `Get-IseSnippet` cmdlet.</span></span> <span data-ttu-id="5ad6f-129">`Get-IseSnippet` Retorna um objeto File (System. IO. FileInfo) que representa um arquivo de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-129">`Get-IseSnippet` returns a file object (System.Io.FileInfo) that represents a snippet file.</span></span>

<span data-ttu-id="5ad6f-130">O `Format-Table` cmdlet exibe as propriedades **DisplayTitle** e **Description** dos trechos de código em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-130">The `Format-Table` cmdlet displays the **DisplayTitle** and **Description** properties of the snippets in a table.</span></span>

## <span data-ttu-id="5ad6f-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5ad6f-131">PARAMETERS</span></span>

### <span data-ttu-id="5ad6f-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5ad6f-132">CommonParameters</span></span>

<span data-ttu-id="5ad6f-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5ad6f-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5ad6f-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5ad6f-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5ad6f-135">INPUTS</span></span>

## <span data-ttu-id="5ad6f-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5ad6f-136">OUTPUTS</span></span>

### <span data-ttu-id="5ad6f-137">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="5ad6f-137">System.IO.FileInfo</span></span>

<span data-ttu-id="5ad6f-138">Esse cmdlet retorna um objeto de arquivo que representa o arquivo de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-138">This cmdlet returns a file object that represents the snippet file.</span></span>

## <span data-ttu-id="5ad6f-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5ad6f-139">NOTES</span></span>

* <span data-ttu-id="5ad6f-140">O `New-IseSnippet` cmdlet armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-140">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="5ad6f-141">Desse modo, o Windows PowerShell não pode adicioná-los a uma sessão em que a diretiva de execução é **AllSigned** ou **Restricted** .</span><span class="sxs-lookup"><span data-stu-id="5ad6f-141">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="5ad6f-142">Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-142">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="5ad6f-143">Para usar trechos de código criados pelo usuário não assinados que o `Get-IseSnippet` cmdlet retorna, altere a política de execução e reinicie ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ad6f-143">To use unsigned user-created snippets that the `Get-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="5ad6f-144">Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="5ad6f-144">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="5ad6f-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5ad6f-145">RELATED LINKS</span></span>

[<span data-ttu-id="5ad6f-146">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="5ad6f-146">New-IseSnippet</span></span>](New-IseSnippet.md)

[<span data-ttu-id="5ad6f-147">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="5ad6f-147">Import-IseSnippet</span></span>](Import-IseSnippet.md)
