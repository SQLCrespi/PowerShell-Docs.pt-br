---
title: Criar ajuda baseada em XML usando o PlatyPS
description: O uso do PlatyPS é uma forma rápida e eficiente de criar a ajuda baseada em XML.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972566"
---
# <a name="create-xml-based-help-using-platyps"></a><span data-ttu-id="92ccb-103">Criar ajuda baseada em XML usando o PlatyPS</span><span class="sxs-lookup"><span data-stu-id="92ccb-103">Create XML-based help using PlatyPS</span></span>

<span data-ttu-id="92ccb-104">Quando você cria um módulo do PowerShell, é sempre recomendável que você inclua ajuda detalhada para os cmdlets criados.</span><span class="sxs-lookup"><span data-stu-id="92ccb-104">When creating a PowerShell module, it is always recommended that you include detailed help for the cmdlets you create.</span></span> <span data-ttu-id="92ccb-105">Se os cmdlets forem implementados no código compilado, você precisará usar a ajuda baseada em XML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-105">If your cmdlets are implemented in compiled code, you must use the XML-based help.</span></span> <span data-ttu-id="92ccb-106">Esse formato XML é conhecido como MAML (Microsoft Assistance Markup Language).</span><span class="sxs-lookup"><span data-stu-id="92ccb-106">This XML format is known as the Microsoft Assistance Markup Language (MAML).</span></span>

<span data-ttu-id="92ccb-107">A documentação do SDK do PowerShell herdado aborda os detalhes da criação de ajuda para os cmdlets do PowerShell empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="92ccb-107">The legacy PowerShell SDK documentation covers the details of creating help for PowerShell cmdlets packaged into modules.</span></span> <span data-ttu-id="92ccb-108">No entanto, o PowerShell não fornece nenhuma ferramenta para criar a ajuda baseada em XML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-108">However, PowerShell does not provide any tools for creating the XML-based help.</span></span> <span data-ttu-id="92ccb-109">A documentação do SDK explica a estrutura da ajuda do MAML, mas deixa a você a tarefa de criar o conteúdo MAML complexo, e profundamente aninhado, manualmente.</span><span class="sxs-lookup"><span data-stu-id="92ccb-109">The SDK documentation explains the structure of MAML help, but leaves you the task of creating the complex, and deeply nested, MAML content by hand.</span></span>

<span data-ttu-id="92ccb-110">É aí que o módulo [PlatyPS][] pode ajudar.</span><span class="sxs-lookup"><span data-stu-id="92ccb-110">This is where the [PlatyPS][] module can help.</span></span>

## <a name="what-is-platyps"></a><span data-ttu-id="92ccb-111">O que é o PlatyPS?</span><span class="sxs-lookup"><span data-stu-id="92ccb-111">What is PlatyPS?</span></span>

<span data-ttu-id="92ccb-112">O PlatyPS é uma ferramenta de [software livre][platyps-repo] que começou como um projeto _hackathon_ para facilitar a criação e a manutenção do MAML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-112">PlatyPS is an [open-source][platyps-repo] tool that started as a _hackathon_ project to make the creation and maintenance of MAML easier.</span></span> <span data-ttu-id="92ccb-113">O PlatyPS documenta a sintaxe de conjuntos de parâmetros e os parâmetros individuais para cada cmdlet em seu módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-113">PlatyPS documents the syntax of parameter sets and the individual parameters for each cmdlet in your module.</span></span> <span data-ttu-id="92ccb-114">O PlatyPS cria arquivos [Markdown][] estruturados que contêm as informações de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="92ccb-114">PlatyPS creates structured [Markdown][] files that contain the syntax information.</span></span> <span data-ttu-id="92ccb-115">Ele não pode criar descrições nem fornecer exemplos.</span><span class="sxs-lookup"><span data-stu-id="92ccb-115">It can't create descriptions or provide examples.</span></span>

<span data-ttu-id="92ccb-116">O PlatyPS cria espaços reservados para que você preencha descrições e exemplos.</span><span class="sxs-lookup"><span data-stu-id="92ccb-116">PlatyPS creates placeholders for you to fill in descriptions and examples.</span></span> <span data-ttu-id="92ccb-117">Depois de adicionar as informações necessárias, o PlatyPS compila os arquivos Markdown em arquivos MAML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-117">After adding the required information, PlatyPS compiles the Markdown files into MAML files.</span></span> <span data-ttu-id="92ccb-118">O sistema de ajuda do PowerShell também permite arquivos de ajuda conceituais de texto sem formatação (sobre tópicos).</span><span class="sxs-lookup"><span data-stu-id="92ccb-118">PowerShell's help system also allows for plain-text conceptual help files (about topics).</span></span> <span data-ttu-id="92ccb-119">O PlatyPS tem um cmdlet para criar um modelo Markdown estruturado para um novo arquivo _sobre_ arquivo, mas esses arquivos `about_*.help.txt` precisam ser mantidos manualmente.</span><span class="sxs-lookup"><span data-stu-id="92ccb-119">PlatyPS has a cmdlet to create a structured Markdown template for a new _about_ file, but these `about_*.help.txt` files must be maintained manually.</span></span>

<span data-ttu-id="92ccb-120">Você pode incluir os arquivos de ajuda MAML e de Texto com seu módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-120">You can include the MAML and Text help files with your module.</span></span> <span data-ttu-id="92ccb-121">Você também pode usar o PlatyPS para compilar os arquivos de ajuda em um pacote CAB que pode ser hospedado para obter ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="92ccb-121">You can also use PlatyPS to compile the help files into a CAB package that can be hosted for updateable help.</span></span>

## <a name="get-started-using-platyps"></a><span data-ttu-id="92ccb-122">Introdução ao PlatyPS</span><span class="sxs-lookup"><span data-stu-id="92ccb-122">Get started using PlatyPS</span></span>

<span data-ttu-id="92ccb-123">Primeiro, você precisa instalar o PlatyPS do Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-123">First you must install PlatyPS from the PowerShell Gallery.</span></span>

```powershell
Install-Module platyps -Force
Import-Module platyps
```

<span data-ttu-id="92ccb-124">O fluxograma a seguir descreve o processo de criação ou atualização do conteúdo de referência do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-124">The following flowchart outlines the process for creating or updating PowerShell reference content.</span></span>

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="O fluxo de trabalho para criar a ajuda baseada em XML usando o PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a><span data-ttu-id="92ccb-126">Criar conteúdo do Markdown para um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="92ccb-126">Create Markdown content for a PowerShell module</span></span>

1. <span data-ttu-id="92ccb-127">Importe seu novo módulo na sessão.</span><span class="sxs-lookup"><span data-stu-id="92ccb-127">Import your new module into the session.</span></span> <span data-ttu-id="92ccb-128">Repita essa etapa para cada módulo que você precisa documentar.</span><span class="sxs-lookup"><span data-stu-id="92ccb-128">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="92ccb-129">Execute o seguinte comando para importar seus módulos:</span><span class="sxs-lookup"><span data-stu-id="92ccb-129">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="92ccb-130">Use o PlatyPS para gerar arquivos Markdown para a página de módulo e todos os cmdlets associados dentro do módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-130">Use PlatyPS to generate Markdown files for your module page and all associated cmdlets within the module.</span></span> <span data-ttu-id="92ccb-131">Repita essa etapa para cada módulo que você precisa documentar.</span><span class="sxs-lookup"><span data-stu-id="92ccb-131">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   <span data-ttu-id="92ccb-132">Se a pasta de saída não existir, `New-MarkdownHelp` a criará.</span><span class="sxs-lookup"><span data-stu-id="92ccb-132">If the output folder does not exist, `New-MarkdownHelp` creates it.</span></span> <span data-ttu-id="92ccb-133">Neste exemplo, `New-MarkdownHelp` cria um arquivo Markdown para cada cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-133">In this example, `New-MarkdownHelp` creates a Markdown file for each cmdlet in the module.</span></span> <span data-ttu-id="92ccb-134">Ele também cria a _página de módulo_ em um arquivo chamado `<ModuleName>.md`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-134">It also creates the _module page_ in a file named `<ModuleName>.md`.</span></span> <span data-ttu-id="92ccb-135">Esta página de módulo contém uma lista dos cmdlets contidos no módulo e espaços reservados para a descrição **Sinopse**.</span><span class="sxs-lookup"><span data-stu-id="92ccb-135">This module page contains a list of the cmdlets contained in the module and placeholders for the **Synopsis** description.</span></span> <span data-ttu-id="92ccb-136">Os metadados na página de módulo são provenientes do manifesto do módulo e são usados pelo PlatyPS para criar o arquivo XML HelpInfo (conforme explicado [abaixo](#creating-an-updateable-help-package)).</span><span class="sxs-lookup"><span data-stu-id="92ccb-136">The metadata in the module page comes from the module manifest and is used by PlatyPS to create the HelpInfo XML file (as explained [below](#creating-an-updateable-help-package)).</span></span>

   <span data-ttu-id="92ccb-137">`New-MarkdownAboutHelp` cria um arquivo _sobre_ chamado `about_topic_name.md`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-137">`New-MarkdownAboutHelp` creates a new _about_ file named `about_topic_name.md`.</span></span>

   <span data-ttu-id="92ccb-138">Para obter mais informações, confira [New-MarkdownHelp][] e [New-MarkdownAboutHelp][].</span><span class="sxs-lookup"><span data-stu-id="92ccb-138">For more information, see [New-MarkdownHelp][] and [New-MarkdownAboutHelp][].</span></span>

### <a name="update-existing-markdown-content-when-the-module-changes"></a><span data-ttu-id="92ccb-139">Atualizar o conteúdo do Markdown existente quando o módulo for alterado</span><span class="sxs-lookup"><span data-stu-id="92ccb-139">Update existing Markdown content when the module changes</span></span>

<span data-ttu-id="92ccb-140">O PlatyPS também pode atualizar arquivos Markdown existentes para um módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-140">PlatyPS can also update existing Markdown files for a module.</span></span> <span data-ttu-id="92ccb-141">Use esta etapa para atualizar os módulos existentes que têm novos cmdlets, novos parâmetros ou parâmetros que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="92ccb-141">Use this step to update existing modules that have new cmdlets, new parameters, or parameters that have changed.</span></span>

1. <span data-ttu-id="92ccb-142">Importe seu novo módulo na sessão.</span><span class="sxs-lookup"><span data-stu-id="92ccb-142">Import your new module into the session.</span></span> <span data-ttu-id="92ccb-143">Repita essa etapa para cada módulo que você precisa documentar.</span><span class="sxs-lookup"><span data-stu-id="92ccb-143">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="92ccb-144">Execute o seguinte comando para importar seus módulos:</span><span class="sxs-lookup"><span data-stu-id="92ccb-144">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="92ccb-145">Use o PlatyPS para gerar atualizar Markdown para a página de aterrissagem do módulo e todos os cmdlets associados dentro do módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-145">Use PlatyPS to update Markdown files for your module landing page and all associated cmdlets within the module.</span></span> <span data-ttu-id="92ccb-146">Repita essa etapa para cada módulo que você precisa documentar.</span><span class="sxs-lookup"><span data-stu-id="92ccb-146">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   <span data-ttu-id="92ccb-147">`Update-MarkdownHelpModule` atualiza os arquivos Markdown do módulo e cmdlet na pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="92ccb-147">`Update-MarkdownHelpModule` updates the cmdlet and module Markdown files in the specified folder.</span></span>
   <span data-ttu-id="92ccb-148">Ele não atualiza os arquivos `about_*.md`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-148">It does not update the `about_*.md` files.</span></span> <span data-ttu-id="92ccb-149">O arquivo de módulo (`ModuleName.md`) recebe qualquer texto **Sinopse** novo que foi adicionado aos arquivos cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92ccb-149">The module file (`ModuleName.md`) receives any new **Synopsis** text that has been added to the cmdlet files.</span></span> <span data-ttu-id="92ccb-150">As atualizações dos arquivos cmdlet incluem a seguinte alteração:</span><span class="sxs-lookup"><span data-stu-id="92ccb-150">Updates to cmdlet files include the following change:</span></span>

   - <span data-ttu-id="92ccb-151">Novos conjuntos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="92ccb-151">New parameter sets</span></span>
   - <span data-ttu-id="92ccb-152">Novos parâmetros</span><span class="sxs-lookup"><span data-stu-id="92ccb-152">New parameters</span></span>
   - <span data-ttu-id="92ccb-153">Metadados de parâmetro atualizados</span><span class="sxs-lookup"><span data-stu-id="92ccb-153">Updated parameter metadata</span></span>
   - <span data-ttu-id="92ccb-154">Informações atualizadas de tipo de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="92ccb-154">Updated input and output type information</span></span>

   <span data-ttu-id="92ccb-155">Para obter mais informações, confira [Update-MarkdownHelpModule][].</span><span class="sxs-lookup"><span data-stu-id="92ccb-155">For more information, see [Update-MarkdownHelpModule][].</span></span>

## <a name="edit-the-new-or-updated-markdown-files"></a><span data-ttu-id="92ccb-156">Editar os arquivos Markdown novos ou atualizados</span><span class="sxs-lookup"><span data-stu-id="92ccb-156">Edit the new or updated Markdown files</span></span>

<span data-ttu-id="92ccb-157">O PlatyPS documenta a sintaxe dos conjuntos de parâmetros e os parâmetros individuais.</span><span class="sxs-lookup"><span data-stu-id="92ccb-157">PlatyPS documents the syntax of the parameter sets and the individual parameters.</span></span> <span data-ttu-id="92ccb-158">Ele não pode criar descrições nem fornecer exemplos.</span><span class="sxs-lookup"><span data-stu-id="92ccb-158">It can't create descriptions or provide examples.</span></span> <span data-ttu-id="92ccb-159">As áreas específicas em que o conteúdo é necessário estão contidas entre chaves.</span><span class="sxs-lookup"><span data-stu-id="92ccb-159">The specific areas where content is needed are contained in curly braces.</span></span> <span data-ttu-id="92ccb-160">Por exemplo: `{{ Fill in the Description }}`</span><span class="sxs-lookup"><span data-stu-id="92ccb-160">For example: `{{ Fill in the Description }}`</span></span>

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Modelo de Markdown mostrando os espaços reservados no VS Code":::

<span data-ttu-id="92ccb-162">Você precisa adicionar uma sinopse, uma descrição do cmdlet, descrições para cada parâmetro e pelo menos um exemplo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-162">You need to add a synopsis, a description of the cmdlet, descriptions for each parameter, and at least one example.</span></span>

<span data-ttu-id="92ccb-163">Para obter informações detalhadas sobre como escrever conteúdo do PowerShell, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="92ccb-163">For detailed information about writing PowerShell content, see the following articles:</span></span>

- [<span data-ttu-id="92ccb-164">Guia de estilo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="92ccb-164">PowerShell style guide</span></span>](/powershell/scripting/community/contributing/powershell-style-guide)
- [<span data-ttu-id="92ccb-165">Como editar artigos de referência</span><span class="sxs-lookup"><span data-stu-id="92ccb-165">Editing reference articles</span></span>](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> <span data-ttu-id="92ccb-166">O PlatyPS tem um esquema específico usado para referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92ccb-166">PlatyPS has a specific schema that is uses for cmdlet reference.</span></span> <span data-ttu-id="92ccb-167">Esse esquema permite apenas certos blocos do Markdown em seções específicas do documento.</span><span class="sxs-lookup"><span data-stu-id="92ccb-167">That schema only allows certain Markdown blocks in specific sections of the document.</span></span> <span data-ttu-id="92ccb-168">Se você colocar o conteúdo no local errado, a etapa de build do PlatyPS falhará.</span><span class="sxs-lookup"><span data-stu-id="92ccb-168">If you put content in the wrong location, the PlatyPS build step fails.</span></span> <span data-ttu-id="92ccb-169">Para obter mais informações, confira a documentação de [esquema][] no repositório do PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="92ccb-169">For more information, see the [schema][] documentation in the PlatyPS repository.</span></span> <span data-ttu-id="92ccb-170">Para obter um exemplo completo de referência de cmdlet bem formado, confira [Get-Item][].</span><span class="sxs-lookup"><span data-stu-id="92ccb-170">For a complete example of well-formed cmdlet reference, see [Get-Item][].</span></span>

<span data-ttu-id="92ccb-171">Depois de fornecer o conteúdo necessário para cada um dos seus cmdlets, você precisará atualizar a página de aterrissagem do módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-171">After providing the required content for each of your cmdlets, you need to make sure that you update the module landing page.</span></span> <span data-ttu-id="92ccb-172">Verifique se o módulo tem os valores `Module Guid` e `Download Help Link` corretos nos metadados YAML do arquivo `<module-name>.md`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-172">Verify your module has the correct `Module Guid` and `Download Help Link` values in the YAML metadata of the `<module-name>.md` file.</span></span> <span data-ttu-id="92ccb-173">Adicione metadados ausentes.</span><span class="sxs-lookup"><span data-stu-id="92ccb-173">Add any missing metadata.</span></span>

<span data-ttu-id="92ccb-174">Além disso, você pode perceber que alguns cmdlets podem não ter uma **Sinopse** (_breve descrição_).</span><span class="sxs-lookup"><span data-stu-id="92ccb-174">Also, you may notice that some cmdlets may be missing a **Synopsis** (_short description_).</span></span> <span data-ttu-id="92ccb-175">O comando a seguir atualiza a página de aterrissagem do módulo com seu texto de descrição **Sinopse**.</span><span class="sxs-lookup"><span data-stu-id="92ccb-175">The following command updates the module landing page with your **Synopsis** description text.</span></span> <span data-ttu-id="92ccb-176">Abra a página de aterrissagem do módulo para verificar as descrições.</span><span class="sxs-lookup"><span data-stu-id="92ccb-176">Open the module landing page to verify the descriptions.</span></span>

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

<span data-ttu-id="92ccb-177">Agora que você inseriu todo o conteúdo, pode criar os arquivos de ajuda MAML exibidos pelo `Get-Help` no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-177">Now that you have entered all the content, you can create the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

## <a name="create-the-external-help-files"></a><span data-ttu-id="92ccb-178">Criar os arquivos de ajuda externos</span><span class="sxs-lookup"><span data-stu-id="92ccb-178">Create the external help files</span></span>

<span data-ttu-id="92ccb-179">Esta etapa cria os arquivos de ajuda MAML exibidos pelo `Get-Help` no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-179">This step creates the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

<span data-ttu-id="92ccb-180">Para criar os arquivos MAML, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="92ccb-180">To build the MAML files, run the following command:</span></span>

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

<span data-ttu-id="92ccb-181">`New-ExternalHelp` converte todos os arquivos Markdown do cmdlet em um ou mais arquivos MAML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-181">`New-ExternalHelp` converts all of the cmdlet Markdown files into one (or more) MAML files.</span></span> <span data-ttu-id="92ccb-182">Arquivos sobre são convertidos em arquivos de texto sem formatação com o seguinte formato de nome: `about_topic_name.help.txt`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-182">About files are converted to plain-text files with the following name format: `about_topic_name.help.txt`.</span></span>
<span data-ttu-id="92ccb-183">O conteúdo Markdown deve atender ao requisito do esquema PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="92ccb-183">The Markdown content must meet the requirement of the PlatyPS schema.</span></span> <span data-ttu-id="92ccb-184">`New-ExternalHelp` sairá com erros quando o conteúdo não seguir o esquema.</span><span class="sxs-lookup"><span data-stu-id="92ccb-184">`New-ExternalHelp` will exits with errors when the content does not follow the schema.</span></span> <span data-ttu-id="92ccb-185">Você precisa editar os arquivos para corrigir as violações de esquema.</span><span class="sxs-lookup"><span data-stu-id="92ccb-185">You must edit the files to fix the schema violations.</span></span>

> [!CAUTION]
> <span data-ttu-id="92ccb-186">O PlatyPS faz um trabalho insatisfatório ao converter os arquivos `about_*.md` em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="92ccb-186">PlatyPS does a poor job converting the `about_*.md` files to plain text.</span></span> <span data-ttu-id="92ccb-187">Você precisa usar um Markdown muito simples para obter resultados aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="92ccb-187">You must use very simple Markdown to get acceptable results.</span></span> <span data-ttu-id="92ccb-188">Talvez seja necessário manter os arquivos em formato `about_topic_name.help.txt` de texto sem formatação, em vez de permitir que PlatyPS os converta.</span><span class="sxs-lookup"><span data-stu-id="92ccb-188">You may want to maintain the files in plain-text `about_topic_name.help.txt` format, rather than allowing PlatyPS to convert them.</span></span>

<span data-ttu-id="92ccb-189">Após a conclusão dessa etapa, você verá os arquivos `*-help.xml` e `about_*.help.txt` na pasta de saída de destino.</span><span class="sxs-lookup"><span data-stu-id="92ccb-189">Once this step is complete, you will see `*-help.xml` and `about_*.help.txt` files in the target output folder.</span></span>

<span data-ttu-id="92ccb-190">Para obter mais informações, confira [New-ExternalHelp][]</span><span class="sxs-lookup"><span data-stu-id="92ccb-190">For more information, see [New-ExternalHelp][]</span></span>

### <a name="test-the-compiled-help-files"></a><span data-ttu-id="92ccb-191">Testar os arquivos de ajuda compilados</span><span class="sxs-lookup"><span data-stu-id="92ccb-191">Test the compiled help files</span></span>

<span data-ttu-id="92ccb-192">Você pode verificar o conteúdo com o cmdlet [Get-HelpPreview][]:</span><span class="sxs-lookup"><span data-stu-id="92ccb-192">You can verify the content with the [Get-HelpPreview][] cmdlet:</span></span>

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

<span data-ttu-id="92ccb-193">O cmdlet lê o arquivo MAML compilado e gera o conteúdo no mesmo formato que você receberia de `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="92ccb-193">The cmdlet reads the compiled MAML file and outputs the content in the same format you would receive from `Get-Help`.</span></span> <span data-ttu-id="92ccb-194">Isso permite inspecionar os resultados para verificar se os arquivos Markdown foram compilados corretamente e produzem os resultados desejados.</span><span class="sxs-lookup"><span data-stu-id="92ccb-194">This allows you to inspect the results to verify that the Markdown files compiled correctly and produce the desired results.</span></span> <span data-ttu-id="92ccb-195">Se você encontrar um erro, edite novamente os arquivos Markdown e recompile o MAML.</span><span class="sxs-lookup"><span data-stu-id="92ccb-195">If you find an error, re-edit the Markdown files and recompile the MAML.</span></span>

<span data-ttu-id="92ccb-196">Agora você está pronto para publicar seus arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="92ccb-196">Now you are ready to publish your help files.</span></span>

## <a name="publishing-your-help"></a><span data-ttu-id="92ccb-197">Como publicar sua ajuda</span><span class="sxs-lookup"><span data-stu-id="92ccb-197">Publishing your help</span></span>

<span data-ttu-id="92ccb-198">Agora que você compilou os arquivos Markdown nos arquivos de ajuda do PowerShell, você está pronto para disponibilizar os arquivos para os usuários.</span><span class="sxs-lookup"><span data-stu-id="92ccb-198">Now that you have compiled the Markdown files into PowerShell help files, you are ready to make the files available to users.</span></span> <span data-ttu-id="92ccb-199">Há duas opções para fornecer ajuda no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-199">There are two options for providing help in the PowerShell console.</span></span>

- <span data-ttu-id="92ccb-200">Empacotar os arquivos de ajuda com o módulo</span><span class="sxs-lookup"><span data-stu-id="92ccb-200">Package the help files with the module</span></span>
- <span data-ttu-id="92ccb-201">Criar um pacote de ajuda atualizável que os usuários instalam com o cmdlet `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="92ccb-201">Create an updateable help package that users install with the `Update-Help` cmdlet</span></span>

### <a name="packaging-help-with-the-module"></a><span data-ttu-id="92ccb-202">Como empacotar a ajuda com o módulo</span><span class="sxs-lookup"><span data-stu-id="92ccb-202">Packaging help with the module</span></span>

<span data-ttu-id="92ccb-203">Os arquivos de ajuda podem ser empacotados com seu módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-203">The help files can be packaged with your module.</span></span> <span data-ttu-id="92ccb-204">Confira [Como escrever ajuda para os módulos][] para obter detalhes da estrutura de pastas.</span><span class="sxs-lookup"><span data-stu-id="92ccb-204">See [Writing Help for Modules][] for details of the folder structure.</span></span> <span data-ttu-id="92ccb-205">Você deve incluir a lista de arquivos de ajuda no valor da chave de **FileList** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-205">You should include the list of Help files in the value of the **FileList** key in the module manifest.</span></span>

### <a name="creating-an-updateable-help-package"></a><span data-ttu-id="92ccb-206">Como criar um pacote de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="92ccb-206">Creating an updateable help package</span></span>

<span data-ttu-id="92ccb-207">Em um alto nível, as etapas para criar uma ajuda atualizável incluem:</span><span class="sxs-lookup"><span data-stu-id="92ccb-207">At a high level, the steps to create updateable help include:</span></span>

1. <span data-ttu-id="92ccb-208">Encontrar um site da Internet para hospedar seus arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="92ccb-208">Find an internet site to host your help files</span></span>
1. <span data-ttu-id="92ccb-209">Adicionar uma chave **HelpInfoURI** ao manifesto do módulo</span><span class="sxs-lookup"><span data-stu-id="92ccb-209">Add a **HelpInfoURI** key to your module manifest</span></span>
1. <span data-ttu-id="92ccb-210">Criar um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="92ccb-210">Create a HelpInfo XML file</span></span>
1. <span data-ttu-id="92ccb-211">Criar arquivos CAB</span><span class="sxs-lookup"><span data-stu-id="92ccb-211">Create CAB files</span></span>
1. <span data-ttu-id="92ccb-212">Carregar seus arquivos</span><span class="sxs-lookup"><span data-stu-id="92ccb-212">Upload your files</span></span>

<span data-ttu-id="92ccb-213">Para obter mais informações, confira [Como dar suporte à ajuda atualizável: passo a passo][step-by-step].</span><span class="sxs-lookup"><span data-stu-id="92ccb-213">For more information, see [Supporting Updateable Help: Step-by-step][step-by-step].</span></span>

<span data-ttu-id="92ccb-214">O PlatyPS ajuda você com algumas dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="92ccb-214">PlatyPS assists you with  some of these steps.</span></span>

<span data-ttu-id="92ccb-215">O **HelpInfoURI** é uma URL que aponta para o local em que os arquivos de ajuda estão hospedados na Internet.</span><span class="sxs-lookup"><span data-stu-id="92ccb-215">The **HelpInfoURI** is a URL that points to location where your help files are hosted on the internet.</span></span> <span data-ttu-id="92ccb-216">Esse valor é configurado no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-216">This value is configured in the module manifest.</span></span> <span data-ttu-id="92ccb-217">`Update-Help` lê o manifesto do módulo para obter essa URL e baixar o conteúdo da ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="92ccb-217">`Update-Help` reads the module manifest to get this URL and download the updateable help content.</span></span> <span data-ttu-id="92ccb-218">Essa URL só deve apontar para o local da pasta, e não para arquivos individuais.</span><span class="sxs-lookup"><span data-stu-id="92ccb-218">This URL should only point to the folder location and not to individual files.</span></span> <span data-ttu-id="92ccb-219">`Update-Help` constrói os nomes de arquivos a serem baixados com base em outras informações do manifesto do módulo e do arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-219">`Update-Help` constructs the filenames to download based on other information from the module manifest and the HelpInfo XML file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92ccb-220">O **HelpInfoURI** precisa terminar com um caractere de barra (`/`).</span><span class="sxs-lookup"><span data-stu-id="92ccb-220">The **HelpInfoURI** must end with a forward-slash character (`/`).</span></span> <span data-ttu-id="92ccb-221">Sem esse caractere, `Update-Help` não pode construir os caminhos de arquivo corretos para baixar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="92ccb-221">Without that character, `Update-Help` cannot construct the correct file paths to download the content.</span></span> <span data-ttu-id="92ccb-222">Além disso, a maioria dos serviços de arquivo baseados em HTTP diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="92ccb-222">Also, most HTTP-based file services are case-sensitive.</span></span> <span data-ttu-id="92ccb-223">É importante que os metadados do módulo no arquivo XML HelpInfo respeitem a diferença entre maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="92ccb-223">It is important that the module metadata in the HelpInfo XML file contains the proper letter case.</span></span>

<span data-ttu-id="92ccb-224">O cmdlet `New-ExternalHelp` cria o arquivo XML HelpInfo na pasta de saída.</span><span class="sxs-lookup"><span data-stu-id="92ccb-224">The `New-ExternalHelp` cmdlet creates the HelpInfo XML file in the output folder.</span></span> <span data-ttu-id="92ccb-225">O arquivo XML HelpInfo é criado usando os metadados YAML contidos nos arquivos Markdown do módulo (`ModuleName.md`).</span><span class="sxs-lookup"><span data-stu-id="92ccb-225">The HelpInfo XML file is built using YAML metadata contained in the module Markdown files (`ModuleName.md`).</span></span>

<span data-ttu-id="92ccb-226">O cmdlet `New-ExternalHelpCab` cria arquivos ZIP e CAB contendo os arquivos MAML e `about_*.help.txt` que você compilou.</span><span class="sxs-lookup"><span data-stu-id="92ccb-226">The `New-ExternalHelpCab` cmdlet creates ZIP and CAB files containing the MAML and `about_*.help.txt` files you compiled.</span></span> <span data-ttu-id="92ccb-227">Os arquivos CAB são compatíveis com todas as versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-227">CAB files are compatible with all versions of PowerShell.</span></span>
<span data-ttu-id="92ccb-228">O PowerShell 6 e versões superiores podem usar arquivos ZIP.</span><span class="sxs-lookup"><span data-stu-id="92ccb-228">PowerShell 6 and higher can use ZIP files.</span></span>

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

<span data-ttu-id="92ccb-229">Depois de criar os arquivos ZIP e CAB, carregue os arquivos XML HelpInfo, ZIP e CAB para o seu servidor de arquivos HTTP.</span><span class="sxs-lookup"><span data-stu-id="92ccb-229">After creating the ZIP and CAB files, upload the ZIP, CAB, and HelpInfo XML files to your HTTP file server.</span></span> <span data-ttu-id="92ccb-230">Coloque os arquivos no local indicado pelo **HelpInfoURI**.</span><span class="sxs-lookup"><span data-stu-id="92ccb-230">Put the files in the location indicated by the **HelpInfoURI**.</span></span>

<span data-ttu-id="92ccb-231">Para obter mais informações, confira [New-ExternalHelpCab][].</span><span class="sxs-lookup"><span data-stu-id="92ccb-231">For more information, see [New-ExternalHelpCab][].</span></span>

### <a name="other-publishing-options"></a><span data-ttu-id="92ccb-232">Outras opções de publicação</span><span class="sxs-lookup"><span data-stu-id="92ccb-232">Other publishing options</span></span>

<span data-ttu-id="92ccb-233">O Markdown é um formato versátil fácil de ser transformado em outros formatos para publicação.</span><span class="sxs-lookup"><span data-stu-id="92ccb-233">Markdown is a versatile format that is easy to transform to other formats for publishing.</span></span> <span data-ttu-id="92ccb-234">Usando uma ferramenta como [Pandoc][], você pode converter seus arquivos de ajuda Markdown em muitos formatos de documentos diferentes, incluindo formatos de documentos de texto sem formatação, HTML, PDF e Office.</span><span class="sxs-lookup"><span data-stu-id="92ccb-234">Using a tool like [Pandoc][], you can convert your Markdown help files to many different document formats, including plain text, HTML, PDF, and Office document formats.</span></span>

<span data-ttu-id="92ccb-235">Além disso, os cmdlets [ConvertFrom-Markdown][] e [Show-Markdown][] no PowerShell 6 e versões superiores podem ser usados para converter o Markdown em HTML ou criar uma exibição colorida no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92ccb-235">Also, the cmdlets [ConvertFrom-Markdown][] and [Show-Markdown][] in PowerShell 6 and higher can be used to convert Markdown to HTML or create a colorful display in the PowerShell console.</span></span>

## <a name="known-issues"></a><span data-ttu-id="92ccb-236">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="92ccb-236">Known issues</span></span>

<span data-ttu-id="92ccb-237">O PlatyPS é muito sensível ao [esquema][] para a estrutura dos arquivos Markdown que ele cria e compila.</span><span class="sxs-lookup"><span data-stu-id="92ccb-237">PlatyPS is very sensitive to the [schema][] for the structure of the Markdown files it creates and compiles.</span></span> <span data-ttu-id="92ccb-238">É muito fácil escrever um Markdown válido que viole esse esquema.</span><span class="sxs-lookup"><span data-stu-id="92ccb-238">It is very easy write valid Markdown that violates this schema.</span></span> <span data-ttu-id="92ccb-239">Para obter mais informações, consulte o [guia de estilo do PowerShell][] e [Como editar artigos de referência][].</span><span class="sxs-lookup"><span data-stu-id="92ccb-239">For more information, consult the [PowerShell style guide][] and [Editing reference articles][].</span></span>

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Guia de estilo do PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[PowerShell style guide]: /powershell/scripting/community/contributing/powershell-style-guide
[Como editar artigos de referência]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Editing reference articles]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Como escrever ajuda para módulos]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[Writing Help for Modules]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
