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
# <span data-ttu-id="fd895-103">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="fd895-103">Import-IseSnippet</span></span>

## <span data-ttu-id="fd895-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fd895-104">SYNOPSIS</span></span>
<span data-ttu-id="fd895-105">Importa snippets ISE para a sessão atual</span><span class="sxs-lookup"><span data-stu-id="fd895-105">Imports ISE snippets into the current session</span></span>

## <span data-ttu-id="fd895-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd895-106">SYNTAX</span></span>

### <span data-ttu-id="fd895-107">FromFolder (padrão)</span><span class="sxs-lookup"><span data-stu-id="fd895-107">FromFolder (Default)</span></span>

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### <span data-ttu-id="fd895-108">FromModule</span><span class="sxs-lookup"><span data-stu-id="fd895-108">FromModule</span></span>

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="fd895-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd895-109">DESCRIPTION</span></span>

<span data-ttu-id="fd895-110">O `Import-IseSnippet` cmdlet importa o texto reutilizável "trechos" de um módulo ou um diretório para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-110">The `Import-IseSnippet` cmdlet imports reusable text "snippets" from a module or a directory into the current session.</span></span> <span data-ttu-id="fd895-111">Os trechos de código estão imediatamente disponíveis para uso no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd895-111">The snippets are immediately available for use in Windows PowerShell ISE.</span></span> <span data-ttu-id="fd895-112">Esse cmdlet funciona apenas em Ambiente de Script Integrado do Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="fd895-112">This cmdlet works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="fd895-113">Para exibir e usar os trechos importados, no menu ISE do Windows PowerShell **Editar** , clique em **Iniciar trechos de código** ou pressione <kbd>Ctrl</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fd895-113">To view and use the imported snippets, from the Windows PowerShell ISE **Edit** menu, click **Start Snippets** or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="fd895-114">Os snippets importados estão disponíveis apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-114">Imported snippets are available only in the current session.</span></span> <span data-ttu-id="fd895-115">Para importar os trechos de código em todas as sessões de ISE do Windows PowerShell, adicione um `Import-IseSnippet` comando ao seu perfil do Windows PowerShell ou copie os arquivos de trecho para o diretório de trechos de código local `$home\Documents\WindowsPowershell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="fd895-115">To import the snippets into all Windows PowerShell ISE sessions, add an `Import-IseSnippet` command to your Windows PowerShell profile or copy the snippet files to your local snippets directory `$home\Documents\WindowsPowershell\Snippets`.</span></span>

<span data-ttu-id="fd895-116">Para importar trechos de código, eles devem ser formatados corretamente no trecho de código XML para ISE do Windows PowerShell trechos de código e salvos em arquivos XML Snippet.ps1.</span><span class="sxs-lookup"><span data-stu-id="fd895-116">To import snippets, they must be properly formatted in the snippet XML for Windows PowerShell ISE snippets and saved in Snippet.ps1xml files.</span></span> <span data-ttu-id="fd895-117">Para criar trechos de código qualificados, use o `New-IseSnippet` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd895-117">To create eligible snippets, use the `New-IseSnippet` cmdlet.</span></span> <span data-ttu-id="fd895-118">`New-IseSnippet` Cria um `<SnippetTitle>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório.</span><span class="sxs-lookup"><span data-stu-id="fd895-118">`New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span> <span data-ttu-id="fd895-119">Você pode mover ou copiar os snippets para o diretório de snippets de um módulo do Windows PowerShell ou para qualquer outro diretório.</span><span class="sxs-lookup"><span data-stu-id="fd895-119">You can move or copy the snippets to the Snippets directory of a Windows PowerShell module, or to any other directory.</span></span>

<span data-ttu-id="fd895-120">O `Get-IseSnippet` cmdlet, que obtém trechos de código criados pelo usuário no diretório de trechos de código local, não obtém trechos de código importados.</span><span class="sxs-lookup"><span data-stu-id="fd895-120">The `Get-IseSnippet` cmdlet, which gets user-created snippets in the local snippets directory, does not get imported snippets.</span></span>

<span data-ttu-id="fd895-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fd895-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fd895-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fd895-122">EXAMPLES</span></span>

### <span data-ttu-id="fd895-123">Exemplo 1: importar trechos de um diretório</span><span class="sxs-lookup"><span data-stu-id="fd895-123">Example 1: Import snippets from a directory</span></span>

<span data-ttu-id="fd895-124">Este exemplo importa os trechos de código do `\\Server01\Public\Snippets` diretório para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-124">This example imports the snippets from the `\\Server01\Public\Snippets` directory into the current session.</span></span> <span data-ttu-id="fd895-125">Ele usa o parâmetro **recurse** para obter trechos de todos os subdiretórios do diretório Snippets.</span><span class="sxs-lookup"><span data-stu-id="fd895-125">It uses the **Recurse** parameter to get snippets from all subdirectories of the Snippets directory.</span></span>

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### <span data-ttu-id="fd895-126">Exemplo 2: importar trechos de código de um módulo</span><span class="sxs-lookup"><span data-stu-id="fd895-126">Example 2: Import snippets from a module</span></span>

<span data-ttu-id="fd895-127">Este exemplo importa os trechos de código do módulo **SnippetModule** .</span><span class="sxs-lookup"><span data-stu-id="fd895-127">This example imports the snippets from the **SnippetModule** module.</span></span> <span data-ttu-id="fd895-128">O comando usa o parâmetro **listAvailable** para importar os trechos de código mesmo se o módulo **SnippetModule** não for importado para a sessão do usuário quando o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="fd895-128">The command uses the **ListAvailable** parameter to import the snippets even if the **SnippetModule** module is not imported into the user's session when the command runs.</span></span>

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### <span data-ttu-id="fd895-129">Exemplo 3: localizar trechos de código em módulos</span><span class="sxs-lookup"><span data-stu-id="fd895-129">Example 3: Find snippets in modules</span></span>

<span data-ttu-id="fd895-130">Este exemplo obtém trechos de código em todos os módulos instalados na variável de ambiente PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="fd895-130">This example gets snippets in all installed modules in the PSModulePath environment variable.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### <span data-ttu-id="fd895-131">Exemplo 4: importar todos os trechos de módulo</span><span class="sxs-lookup"><span data-stu-id="fd895-131">Example 4: Import all module snippets</span></span>

<span data-ttu-id="fd895-132">Este exemplo importa todos os trechos de todos os módulos instalados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-132">This example imports all snippets from all installed modules into the current session.</span></span> <span data-ttu-id="fd895-133">Normalmente, você não precisa executar um comando como esse porque os módulos que têm trechos de código usarão o `Import-IseSnippet` cmdlet para importá-los para você quando o módulo for importado.</span><span class="sxs-lookup"><span data-stu-id="fd895-133">Typically, you don't need to run a command like this because modules that have snippets will use the `Import-IseSnippet` cmdlet to import them for you when the module is imported.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### <span data-ttu-id="fd895-134">Exemplo 5: copiar todos os trechos de módulo</span><span class="sxs-lookup"><span data-stu-id="fd895-134">Example 5: Copy all module snippets</span></span>

<span data-ttu-id="fd895-135">Este exemplo copia os arquivos de trecho de todos os módulos instalados para o diretório de trechos de código do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-135">This example copies the snippet files from all installed modules into the Snippets directory of the current user.</span></span> <span data-ttu-id="fd895-136">Ao contrário de snippets importados, que afetam apenas a sessão atual, snippets copiados estão disponíveis em cada sessão do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd895-136">Unlike imported snippets, which affect only the current session, copied snippets are available in every Windows PowerShell ISE session.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## <span data-ttu-id="fd895-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd895-137">PARAMETERS</span></span>

### <span data-ttu-id="fd895-138">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="fd895-138">-ListAvailable</span></span>

<span data-ttu-id="fd895-139">Indica que esse cmdlet obtém trechos de módulos que estão instalados no computador, mesmo que os módulos não sejam importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-139">Indicates that this cmdlet gets snippets from modules that are installed on the computer, even if the modules are not imported into the current session.</span></span> <span data-ttu-id="fd895-140">Se esse parâmetro for omitido e o módulo especificado pelo parâmetro de **módulo** não for importado para a sessão atual, a tentativa de obter os trechos de código do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="fd895-140">If this parameter is omitted, and the module that is specified by the **Module** parameter is not imported into the current session, the attempt to get the snippets from the module fails.</span></span>

<span data-ttu-id="fd895-141">Esse parâmetro será válido somente quando o parâmetro **Module** for usado no comando.</span><span class="sxs-lookup"><span data-stu-id="fd895-141">This parameter is valid only when the **Module** parameter is used in the command.</span></span>

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

### <span data-ttu-id="fd895-142">-Módulo</span><span class="sxs-lookup"><span data-stu-id="fd895-142">-Module</span></span>

<span data-ttu-id="fd895-143">Importa os snippets do módulo especificado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd895-143">Imports snippets from the specified module into the current session.</span></span> <span data-ttu-id="fd895-144">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="fd895-144">Wildcard characters are not supported.</span></span>

<span data-ttu-id="fd895-145">Esse parâmetro importa trechos de Snippet.ps1arquivos XML no subdiretório Snippets no caminho do módulo, como `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="fd895-145">This parameter imports snippets from Snippet.ps1xml files in the Snippets subdirectory in the module path, such as `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets`.</span></span>

<span data-ttu-id="fd895-146">Esse parâmetro foi projetado para ser usado por autores de módulo em um script de inicialização, como um script especificado na chave **ScriptsToProcess** de um manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="fd895-146">This parameter is designed to be used by module authors in a startup script, such as a script specified in the **ScriptsToProcess** key of a module manifest.</span></span> <span data-ttu-id="fd895-147">Trechos de código em um módulo não são importados automaticamente com o módulo, mas você pode usar um `Import-IseSnippet` comando para importá-los.</span><span class="sxs-lookup"><span data-stu-id="fd895-147">Snippets in a module are not automatically imported with the module, but you can use an `Import-IseSnippet` command to import them.</span></span>

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

### <span data-ttu-id="fd895-148">-Path</span><span class="sxs-lookup"><span data-stu-id="fd895-148">-Path</span></span>

<span data-ttu-id="fd895-149">Especifica o caminho para o diretório de trechos de código no qual este cmdlet importa trechos.</span><span class="sxs-lookup"><span data-stu-id="fd895-149">Specifies the path to the snippets directory in which this cmdlet imports snippets.</span></span>

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

### <span data-ttu-id="fd895-150">-Recurse</span><span class="sxs-lookup"><span data-stu-id="fd895-150">-Recurse</span></span>

<span data-ttu-id="fd895-151">Indica que este cmdlet importa trechos de todos os subdiretórios do valor do parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="fd895-151">Indicates that this cmdlet imports snippets from all subdirectories of the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="fd895-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd895-152">CommonParameters</span></span>

<span data-ttu-id="fd895-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd895-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd895-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd895-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd895-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fd895-155">INPUTS</span></span>

### <span data-ttu-id="fd895-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fd895-156">None</span></span>

<span data-ttu-id="fd895-157">Este cmdlet não recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="fd895-157">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="fd895-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fd895-158">OUTPUTS</span></span>

### <span data-ttu-id="fd895-159">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fd895-159">None</span></span>

<span data-ttu-id="fd895-160">Esse cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="fd895-160">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="fd895-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fd895-161">NOTES</span></span>

- <span data-ttu-id="fd895-162">Você não pode usar o `Get-IseSnippet` cmdlet para obter trechos de código importados.</span><span class="sxs-lookup"><span data-stu-id="fd895-162">You cannot use the `Get-IseSnippet` cmdlet to get imported snippets.</span></span> <span data-ttu-id="fd895-163">`Get-IseSnippet` Obtém apenas trechos de código no `$home\Documents\WindowsPowerShell\Snippets` diretório.</span><span class="sxs-lookup"><span data-stu-id="fd895-163">`Get-IseSnippet` gets only snippets in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
- <span data-ttu-id="fd895-164">`Import-IseSnippet` usa o método estático **Load** de objetos **Microsoft. PowerShell. host. ISE. ISESnippetCollection** .</span><span class="sxs-lookup"><span data-stu-id="fd895-164">`Import-IseSnippet` uses the **Load** static method of **Microsoft.PowerShell.Host.ISE.ISESnippetCollection** objects.</span></span> <span data-ttu-id="fd895-165">Você também pode usar o método **Load** de trechos de código no modelo de objeto ISE do Windows PowerShell: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span><span class="sxs-lookup"><span data-stu-id="fd895-165">You can also use the **Load** method of snippets in the Windows PowerShell ISE object model: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span></span>
- <span data-ttu-id="fd895-166">O `New-IseSnippet` cmdlet armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados.</span><span class="sxs-lookup"><span data-stu-id="fd895-166">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="fd895-167">Dessa forma, o Windows PowerShell não pode carregá-los em uma sessão em que a diretiva de execução seja **AllSigned** ou **Restricted** .</span><span class="sxs-lookup"><span data-stu-id="fd895-167">As such, Windows PowerShell cannot load them into a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="fd895-168">Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd895-168">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="fd895-169">Para usar trechos de código criados pelo usuário não assinados que o `Import-IseSnippet` cmdlet retorna, altere a política de execução e reinicie ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd895-169">To use unsigned user-created snippets that the `Import-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="fd895-170">Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="fd895-170">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="fd895-171">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fd895-171">RELATED LINKS</span></span>

[<span data-ttu-id="fd895-172">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="fd895-172">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="fd895-173">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="fd895-173">New-IseSnippet</span></span>](New-IseSnippet.md)
