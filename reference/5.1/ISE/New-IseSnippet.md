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
# <span data-ttu-id="23542-103">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="23542-103">New-IseSnippet</span></span>

## <span data-ttu-id="23542-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="23542-104">SYNOPSIS</span></span>
<span data-ttu-id="23542-105">Cria um snippet de código do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-105">Creates a Windows PowerShell ISE code snippet.</span></span>

## <span data-ttu-id="23542-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23542-106">SYNTAX</span></span>

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="23542-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23542-107">DESCRIPTION</span></span>

<span data-ttu-id="23542-108">O `New-ISESnippet` cmdlet cria um "Trecho" de texto reutilizável para ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-108">The `New-ISESnippet` cmdlet creates a reusable text "snippet" for Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-109">Você pode usar snippets para adicionar texto ao painel Script ou painel Comando no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-109">You can use snippets to add text to the Script pane or Command pane in Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-110">Este cmdlet está disponível apenas no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-110">This cmdlet is available only in Windows PowerShell ISE.</span></span>

<span data-ttu-id="23542-111">A partir do Windows PowerShell 3.0, o ISE do Windows PowerShell inclui uma coleção de snippets internos.</span><span class="sxs-lookup"><span data-stu-id="23542-111">Beginning in Windows PowerShell 3.0, Windows PowerShell ISE includes a collection of built-in snippets.</span></span> <span data-ttu-id="23542-112">O `New-ISESnippet` cmdlet permite que você crie seus próprios trechos de código para adicionar à coleção interna.</span><span class="sxs-lookup"><span data-stu-id="23542-112">The `New-ISESnippet` cmdlet lets you create your own snippets to add to the built-in collection.</span></span> <span data-ttu-id="23542-113">Você pode exibir, alterar, adicionar, excluir e compartilhar arquivos de snippet e incluí-los em módulos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-113">You can view, change, add, delete, and share snippet files and include them in Windows PowerShell modules.</span></span> <span data-ttu-id="23542-114">Para ver os trechos de código no ISE do Windows PowerShell, no menu **Editar** , selecione **Iniciar trechos de código** ou pressione <kbd>Ctrl</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="23542-114">To see snippets in Windows PowerShell ISE, from the **Edit** menu, select **Start Snippets** or press <kbd>CTRL</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="23542-115">O `New-ISESnippet` cmdlet cria um `<Title>.Snippets.ps1xml` arquivo no `$home\Documents\WindowsPowerShell\Snippets` diretório com o título que você especificar.</span><span class="sxs-lookup"><span data-stu-id="23542-115">The `New-ISESnippet` cmdlet creates a `<Title>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory with the title that you specify.</span></span> <span data-ttu-id="23542-116">Para incluir um arquivo de snippet em um módulo que você está criando, adicione o arquivo de snippet a um subdiretório Snippets do seu diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="23542-116">To include a snippet file in a module that you are authoring, add the snippet file to a Snippets subdirectory of your module directory.</span></span>

<span data-ttu-id="23542-117">Você não pode usar trechos de código criados pelo usuário em uma sessão na qual a política de execução é **restrita** ou **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="23542-117">You cannot use user-created snippets in a session in which the execution policy is **Restricted** or **AllSigned** .</span></span>

<span data-ttu-id="23542-118">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="23542-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="23542-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="23542-119">EXAMPLES</span></span>

### <span data-ttu-id="23542-120">Exemplo 1: criar um trecho de Comment-Based ajuda</span><span class="sxs-lookup"><span data-stu-id="23542-120">Example 1: Create a Comment-Based help snippet</span></span>

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

<span data-ttu-id="23542-121">Este comando cria um snippet Comment-BasedHelp para o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-121">This command creates a Comment-BasedHelp snippet for Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-122">Ele cria um arquivo chamado `Comment-BasedHelp.snippets.ps1xml` no diretório trechos de código do usuário `$home\Documents\WindowsPowerShell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="23542-122">It creates a file named `Comment-BasedHelp.snippets.ps1xml` in the user's Snippets directory `$home\Documents\WindowsPowerShell\Snippets`.</span></span>

### <span data-ttu-id="23542-123">Exemplo 2: criar um trecho de código obrigatório</span><span class="sxs-lookup"><span data-stu-id="23542-123">Example 2: Create a mandatory snippet</span></span>

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

<span data-ttu-id="23542-124">Este exemplo cria um trecho de código chamado **obrigatório** para ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-124">This example creates a snippet named **Mandatory** for Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-125">O primeiro comando salva o texto do trecho na `$M` variável.</span><span class="sxs-lookup"><span data-stu-id="23542-125">The first command saves the snippet text in the `$M` variable.</span></span> <span data-ttu-id="23542-126">O segundo comando usa o `New-ISESnippet` cmdlet para criar o trecho de código.</span><span class="sxs-lookup"><span data-stu-id="23542-126">The second command uses the `New-ISESnippet` cmdlet to create the snippet.</span></span> <span data-ttu-id="23542-127">O comando usa o parâmetro **Force** para substituir um snippet anterior com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="23542-127">The command uses the **Force** parameter to overwrite a previous snippet with the same name.</span></span>

### <span data-ttu-id="23542-128">Exemplo 3: copiar um trecho obrigatório de uma pasta para uma pasta de destino</span><span class="sxs-lookup"><span data-stu-id="23542-128">Example 3: Copy a mandatory snippet from a folder to a destination folder</span></span>

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

<span data-ttu-id="23542-129">Esse comando usa o `Copy-Item` cmdlet para copiar o trecho **obrigatório** da pasta onde `New-ISESnippet` o coloca no compartilhamento de arquivos Server\Share.</span><span class="sxs-lookup"><span data-stu-id="23542-129">This command uses the `Copy-Item` cmdlet to copy the **Mandatory** snippet from the folder where `New-ISESnippet` places it to the Server\Share file share.</span></span>

## <span data-ttu-id="23542-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23542-130">PARAMETERS</span></span>

### <span data-ttu-id="23542-131">-Autor</span><span class="sxs-lookup"><span data-stu-id="23542-131">-Author</span></span>

<span data-ttu-id="23542-132">Especifica o autor do trecho de código.</span><span class="sxs-lookup"><span data-stu-id="23542-132">Specifies the author of the snippet.</span></span> <span data-ttu-id="23542-133">O campo autor aparece no arquivo de snippet, mas ele não aparece quando você clica no nome do snippet no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-133">The author field appears in the snippet file, but it does not appear when you click the snippet name in Windows PowerShell ISE.</span></span>

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

### <span data-ttu-id="23542-134">-CaretOffset</span><span class="sxs-lookup"><span data-stu-id="23542-134">-CaretOffset</span></span>

<span data-ttu-id="23542-135">Especifica o caractere do texto de trecho de código no qual esse cmdlet coloca o cursor.</span><span class="sxs-lookup"><span data-stu-id="23542-135">Specifies the character of the snippet text that this cmdlet places the cursor on.</span></span> <span data-ttu-id="23542-136">Insira um número inteiro que representa a posição do cursor, com "1" representando o primeiro caractere de texto.</span><span class="sxs-lookup"><span data-stu-id="23542-136">Enter an integer that represents the cursor position, with "1" representing the first character of text.</span></span> <span data-ttu-id="23542-137">O valor padrão, 0 (zero), posiciona o cursor imediatamente antes do primeiro caractere de texto.</span><span class="sxs-lookup"><span data-stu-id="23542-137">The default value, 0 (zero), places the cursor immediately before the first character of text.</span></span> <span data-ttu-id="23542-138">Este parâmetro não recua o texto do snippet.</span><span class="sxs-lookup"><span data-stu-id="23542-138">This parameter does not indent the snippet text.</span></span>

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

### <span data-ttu-id="23542-139">-Description</span><span class="sxs-lookup"><span data-stu-id="23542-139">-Description</span></span>

<span data-ttu-id="23542-140">Especifica uma descrição do trecho de código.</span><span class="sxs-lookup"><span data-stu-id="23542-140">Specifies a description of the snippet.</span></span> <span data-ttu-id="23542-141">O valor de descrição é exibido quando você clica no nome do snippet no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-141">The description value appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-142">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="23542-142">This parameter is required.</span></span>

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

### <span data-ttu-id="23542-143">-Force</span><span class="sxs-lookup"><span data-stu-id="23542-143">-Force</span></span>

<span data-ttu-id="23542-144">Indica que esse cmdlet substitui arquivos de trecho de código com o mesmo nome no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="23542-144">Indicates that this cmdlet overwrites snippet files with the same name in the same location.</span></span> <span data-ttu-id="23542-145">Por padrão, `New-ISESnippet` o não substitui arquivos.</span><span class="sxs-lookup"><span data-stu-id="23542-145">By default, `New-ISESnippet` does not overwrite files.</span></span>

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

### <span data-ttu-id="23542-146">-Texto</span><span class="sxs-lookup"><span data-stu-id="23542-146">-Text</span></span>

<span data-ttu-id="23542-147">Especifica o valor de texto que é adicionado quando você seleciona o snippet.</span><span class="sxs-lookup"><span data-stu-id="23542-147">Specifies the text value that is added when you select the snippet.</span></span> <span data-ttu-id="23542-148">O texto do snippet é exibido quando você clica no nome desse snippet, no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-148">The snippet text appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="23542-149">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="23542-149">This parameter is required.</span></span>

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

### <span data-ttu-id="23542-150">-Title</span><span class="sxs-lookup"><span data-stu-id="23542-150">-Title</span></span>

<span data-ttu-id="23542-151">Especifica um título ou nome para o snippet.</span><span class="sxs-lookup"><span data-stu-id="23542-151">Specifies a title or name for the snippet.</span></span> <span data-ttu-id="23542-152">O título também nomeia o arquivo de snippet.</span><span class="sxs-lookup"><span data-stu-id="23542-152">The title also names the snippet file.</span></span> <span data-ttu-id="23542-153">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="23542-153">This parameter is required.</span></span>

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

### <span data-ttu-id="23542-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23542-154">CommonParameters</span></span>

<span data-ttu-id="23542-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23542-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23542-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23542-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23542-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="23542-157">INPUTS</span></span>

### <span data-ttu-id="23542-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23542-158">None</span></span>

<span data-ttu-id="23542-159">Este cmdlet não recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="23542-159">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="23542-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="23542-160">OUTPUTS</span></span>

### <span data-ttu-id="23542-161">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23542-161">None</span></span>

<span data-ttu-id="23542-162">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="23542-162">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="23542-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="23542-163">NOTES</span></span>

<span data-ttu-id="23542-164">`New-IseSnippet` armazena novos trechos de código criados pelo usuário em arquivos. ps1xml não assinados.</span><span class="sxs-lookup"><span data-stu-id="23542-164">`New-IseSnippet` stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="23542-165">Desse modo, o Windows PowerShell não pode adicioná-los a uma sessão em que a diretiva de execução é **AllSigned** ou **Restricted** .</span><span class="sxs-lookup"><span data-stu-id="23542-165">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="23542-166">Em uma sessão **Restricted** ou **AllSigned** , você pode criar, obter e importar snippets criados pelo usuário não assinados, mas não pode usá-los na sessão.</span><span class="sxs-lookup"><span data-stu-id="23542-166">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

<span data-ttu-id="23542-167">Se você usar o `New-IseSnippet` cmdlet em uma sessão **restrita** ou **AllSigned** , o trecho será criado, mas uma mensagem de erro será exibida quando o Windows PowerShell tentar adicionar o trecho recém-criado à sessão.</span><span class="sxs-lookup"><span data-stu-id="23542-167">If you use the `New-IseSnippet` cmdlet in a **Restricted** or **AllSigned** session, the snippet is created, but an error message appears when Windows PowerShell tries to add the newly created snippet to the session.</span></span> <span data-ttu-id="23542-168">Para usar o novo snippet (e outros snippets não assinados criados pelo usuário), altere a diretiva de execução e, em seguida, reinicie o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-168">To use the new snippet (and other unsigned user-created snippets), change the execution policy, and then restart Windows PowerShell ISE.</span></span>

<span data-ttu-id="23542-169">Para obter mais informações sobre as diretivas de execução do Windows PowerShell, consulte about_Execution_Policies.</span><span class="sxs-lookup"><span data-stu-id="23542-169">For more information about Windows PowerShell execution policies, see about_Execution_Policies.</span></span>

- <span data-ttu-id="23542-170">Para alterar um trecho de código, edite o arquivo de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="23542-170">To change a snippet, edit the snippet file.</span></span> <span data-ttu-id="23542-171">Você pode editar arquivos de trecho de código no painel de script de ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-171">You can edit snippet files in the Script pane of Windows PowerShell ISE.</span></span>
- <span data-ttu-id="23542-172">Para excluir um trecho de código que você adicionou, exclua o arquivo de trecho de código.</span><span class="sxs-lookup"><span data-stu-id="23542-172">To delete a snippet that you added, delete the snippet file.</span></span>
- <span data-ttu-id="23542-173">Não é possível excluir um trecho de código interno, mas você pode ocultar todos os trechos de código internos usando o "$psise. Options. ShowDefaultSnippets = $false ".</span><span class="sxs-lookup"><span data-stu-id="23542-173">You cannot delete a built-in snippet, but you can hide all built-in snippets by using the "$psise.Options.ShowDefaultSnippets=$false" command.</span></span>
- <span data-ttu-id="23542-174">Você pode criar um trecho de código que tenha o mesmo nome de um trecho de código interno.</span><span class="sxs-lookup"><span data-stu-id="23542-174">You can create a snippet that has the same name as a built-in snippet.</span></span> <span data-ttu-id="23542-175">Os dois snippets aparecem no menu de snippet, no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23542-175">Both snippets appear in the snippet menu in Windows PowerShell ISE.</span></span>

## <span data-ttu-id="23542-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="23542-176">RELATED LINKS</span></span>

[<span data-ttu-id="23542-177">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="23542-177">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="23542-178">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="23542-178">Import-IseSnippet</span></span>](Import-IseSnippet.md)
