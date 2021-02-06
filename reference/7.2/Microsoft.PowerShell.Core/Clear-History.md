---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 1b465779f56c6bd71d7adfa7ffb5b391f5402656
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603779"
---
# <span data-ttu-id="886f8-102">Clear-History</span><span class="sxs-lookup"><span data-stu-id="886f8-102">Clear-History</span></span>

## <span data-ttu-id="886f8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="886f8-103">SYNOPSIS</span></span>
<span data-ttu-id="886f8-104">Exclui entradas do histórico de comandos de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-104">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="886f8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="886f8-105">SYNTAX</span></span>

### <span data-ttu-id="886f8-106">IDParameter (padrão)</span><span class="sxs-lookup"><span data-stu-id="886f8-106">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="886f8-107">CommandLineParameter</span><span class="sxs-lookup"><span data-stu-id="886f8-107">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="886f8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="886f8-108">DESCRIPTION</span></span>

<span data-ttu-id="886f8-109">`Clear-History` exclui o histórico de comandos de uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-109">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="886f8-110">Cada sessão do PowerShell tem seu próprio histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-110">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="886f8-111">Para exibir o histórico de comandos, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="886f8-111">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="886f8-112">Por padrão, `Clear-History` exclui o histórico de comandos inteiro de uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-112">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="886f8-113">Você pode usar parâmetros com `Clear-History` para excluir os comandos selecionados.</span><span class="sxs-lookup"><span data-stu-id="886f8-113">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="886f8-114">`Clear-History` não limpa o `PSReadLine` arquivo de histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-114">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="886f8-115">O `PSReadLine` módulo armazena um arquivo de histórico que contém cada comando do PowerShell de cada sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-115">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="886f8-116">Em um prompt do PowerShell, use as setas para cima e para baixo no teclado para percorrer o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-116">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="886f8-117">Para exibir a `PSReadLine` configuração para o histórico de comandos, use `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="886f8-117">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="886f8-118">`PSReadLine` fornecido com o PowerShell 5,0 e superior.</span><span class="sxs-lookup"><span data-stu-id="886f8-118">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="886f8-119">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="886f8-119">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="886f8-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="886f8-120">EXAMPLES</span></span>

### <span data-ttu-id="886f8-121">Exemplo 1: excluir o histórico de comandos de uma sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="886f8-121">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="886f8-122">Esse comando exclui todos os comandos do histórico de uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-122">This command deletes all of the commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

<span data-ttu-id="886f8-123">O `Get-History` cmdlet exibe o histórico da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-123">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="886f8-124">`Clear-History` exclui o histórico de comandos inteiro.</span><span class="sxs-lookup"><span data-stu-id="886f8-124">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="886f8-125">`Get-History` exibe o histórico de comandos atualizados e confirma que o histórico anterior foi excluído.</span><span class="sxs-lookup"><span data-stu-id="886f8-125">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="886f8-126">Exemplo 2: excluir os comandos mais recentes</span><span class="sxs-lookup"><span data-stu-id="886f8-126">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="886f8-127">Esse comando usa os parâmetros **Count** e **mais recentes** para excluir os comandos mais recentes do histórico de uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-127">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

<span data-ttu-id="886f8-128">O `Get-History` cmdlet exibe o histórico da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-128">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="886f8-129">`Clear-History` é usado para excluir o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-129">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="886f8-130">O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. O parâmetro **mais recente** especifica que os comandos mais recentes são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="886f8-130">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="886f8-131">`Get-History`exibe o histórico de comandos atualizados e confirma que os cinco comandos mais recentes foram excluídos, ID **6** ID  -  **10**.</span><span class="sxs-lookup"><span data-stu-id="886f8-131">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10**.</span></span>

### <span data-ttu-id="886f8-132">Exemplo 3: excluir comandos que correspondem a critérios específicos</span><span class="sxs-lookup"><span data-stu-id="886f8-132">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="886f8-133">Este comando exclui os comandos que correspondem aos critérios específicos definidos pelo parâmetro **CommandLine** .</span><span class="sxs-lookup"><span data-stu-id="886f8-133">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

<span data-ttu-id="886f8-134">O `Get-History` cmdlet exibe o histórico da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-134">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="886f8-135">`Clear-History` exclui o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-135">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="886f8-136">O parâmetro **CommandLine** Especifica comandos que contêm **ajuda** ou terminam com **sintaxe**.</span><span class="sxs-lookup"><span data-stu-id="886f8-136">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax**.</span></span> <span data-ttu-id="886f8-137">`Get-History` exibe o histórico de comandos atualizados e confirma que os comandos **ID 3**, **ID 5**, **ID 6** e **ID 7** foram excluídos.</span><span class="sxs-lookup"><span data-stu-id="886f8-137">`Get-History` displays the updated command history and confirms that commands **Id 3**, **Id 5**, **Id 6**, and **Id 7** were deleted.</span></span>

### <span data-ttu-id="886f8-138">Exemplo 4: excluir comandos por número de ID</span><span class="sxs-lookup"><span data-stu-id="886f8-138">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="886f8-139">Este comando exclui itens de histórico específicos usando a **ID**. Para excluir vários comandos, envie uma lista separada por vírgulas de números de **ID** .</span><span class="sxs-lookup"><span data-stu-id="886f8-139">This command deletes specific history items using the **Id**. To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

<span data-ttu-id="886f8-140">O `Get-History` cmdlet exibe o histórico da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-140">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="886f8-141">`Clear-History` exclui o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-141">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="886f8-142">O parâmetro **ID** especifica quais comandos excluir.</span><span class="sxs-lookup"><span data-stu-id="886f8-142">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="886f8-143">`Get-History` exibe o histórico de comandos atualizados e confirma que a **ID 3** e a **ID 5** foram excluídas.</span><span class="sxs-lookup"><span data-stu-id="886f8-143">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="886f8-144">Exemplo 5: excluir comandos por número de ID e contagem</span><span class="sxs-lookup"><span data-stu-id="886f8-144">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="886f8-145">Esse comando usa os parâmetros **ID** e **Count** para excluir o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-145">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="886f8-146">Os comandos são excluídos da **ID** especificada na ordem inversa, o mais recente para o mais antigo.</span><span class="sxs-lookup"><span data-stu-id="886f8-146">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

<span data-ttu-id="886f8-147">O `Get-History` cmdlet exibe o histórico da sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-147">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="886f8-148">`Clear-History` exclui o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="886f8-148">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="886f8-149">O parâmetro **ID** especifica o início da **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="886f8-149">The **Id** parameter specifies to begin with **Id 7**.</span></span> <span data-ttu-id="886f8-150">O parâmetro **Count** especifica a exclusão de cinco comandos, inclusive da **ID** especificada. `Get-History`exibe o histórico de comandos atualizados e confirma que cinco comandos foram excluídos, **ID 3** ID  -  **7**.</span><span class="sxs-lookup"><span data-stu-id="886f8-150">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id**. `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7**.</span></span>

## <span data-ttu-id="886f8-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="886f8-151">PARAMETERS</span></span>

### <span data-ttu-id="886f8-152">-Linha de comando</span><span class="sxs-lookup"><span data-stu-id="886f8-152">-CommandLine</span></span>

<span data-ttu-id="886f8-153">Exclui o histórico de comandos de uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-153">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="886f8-154">A cadeia de caracteres deve ser uma correspondência exata ou usar curingas para corresponder comandos no histórico de sessão do PowerShell exibido pelo `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="886f8-154">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="886f8-155">Se você inserir mais de uma cadeia de caracteres, o `Clear-History` excluirá os comandos que correspondem a qualquer uma das cadeias.</span><span class="sxs-lookup"><span data-stu-id="886f8-155">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="886f8-156">O parâmetro **CommandLine** pode ser usado com **Count**.</span><span class="sxs-lookup"><span data-stu-id="886f8-156">The **CommandLine** parameter can be used with **Count**.</span></span>

<span data-ttu-id="886f8-157">Para cadeias de caracteres com um espaço, use aspas simples.</span><span class="sxs-lookup"><span data-stu-id="886f8-157">For strings with a space, use single quotations.</span></span> <span data-ttu-id="886f8-158">Para obter mais informações, consulte [about_Quoting_Rules](About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="886f8-158">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="886f8-159">-Contagem</span><span class="sxs-lookup"><span data-stu-id="886f8-159">-Count</span></span>

<span data-ttu-id="886f8-160">Especifica o número de entradas de histórico que o `Clear-History` exclui.</span><span class="sxs-lookup"><span data-stu-id="886f8-160">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="886f8-161">Os comandos são excluídos na ordem, começando com a entrada mais antiga no histórico.</span><span class="sxs-lookup"><span data-stu-id="886f8-161">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="886f8-162">Os parâmetros **Count** e **ID** podem ser usados juntos.</span><span class="sxs-lookup"><span data-stu-id="886f8-162">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="886f8-163">O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. A partir da **ID** especificada, os comandos são excluídos na ordem sequencial inversa.</span><span class="sxs-lookup"><span data-stu-id="886f8-163">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="886f8-164">Por exemplo, se a **ID** for 30 e a **contagem** for 10, o `Clear-History` excluirá os itens 21 a 30.</span><span class="sxs-lookup"><span data-stu-id="886f8-164">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="886f8-165">Os parâmetros **Count** e **CommandLine** podem ser usados juntos.</span><span class="sxs-lookup"><span data-stu-id="886f8-165">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="886f8-166">**Count** especifica o número de comandos a serem excluídos que correspondem ao valor do parâmetro **CommandLine** .</span><span class="sxs-lookup"><span data-stu-id="886f8-166">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="886f8-167">Os comandos são excluídos em ordem sequencial.</span><span class="sxs-lookup"><span data-stu-id="886f8-167">The commands are deleted in sequential order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="886f8-168">-Id</span><span class="sxs-lookup"><span data-stu-id="886f8-168">-Id</span></span>

<span data-ttu-id="886f8-169">Especifica a **ID** do histórico de comandos que o `Clear-History` exclui.</span><span class="sxs-lookup"><span data-stu-id="886f8-169">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="886f8-170">Para exibir números de **ID** , use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="886f8-170">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="886f8-171">Os números de **ID** são sequenciais e os comandos mantêm seu número de **ID** em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-171">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="886f8-172">O parâmetro **ID** pode ser usado com **Count** e **mais recente**.</span><span class="sxs-lookup"><span data-stu-id="886f8-172">The **Id** parameter can be used with **Count** and **Newest**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="886f8-173">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="886f8-173">-Newest</span></span>

<span data-ttu-id="886f8-174">Quando o parâmetro **mais recente** for usado, `Clear-History` o excluirá as entradas mais recentes no histórico.</span><span class="sxs-lookup"><span data-stu-id="886f8-174">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="886f8-175">Por padrão, `Clear-History` o exclui as entradas mais antigas no histórico.</span><span class="sxs-lookup"><span data-stu-id="886f8-175">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="886f8-176">O parâmetro **mais recente** pode ser usado com **ID** e **contagem**.</span><span class="sxs-lookup"><span data-stu-id="886f8-176">The **Newest** parameter can be used with **Id** and **Count**.</span></span> <span data-ttu-id="886f8-177">O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. A partir da **ID** especificada, os comandos são excluídos em ordem sequencial.</span><span class="sxs-lookup"><span data-stu-id="886f8-177">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in sequential order.</span></span> <span data-ttu-id="886f8-178">Por exemplo, se a **ID** for 30 e a **contagem** for 10, o `Clear-History` excluirá os itens 30 a 39.</span><span class="sxs-lookup"><span data-stu-id="886f8-178">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

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

### <span data-ttu-id="886f8-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="886f8-179">-Confirm</span></span>

<span data-ttu-id="886f8-180">Solicita a confirmação antes de executar o `Clear-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="886f8-180">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

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

### <span data-ttu-id="886f8-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="886f8-181">-WhatIf</span></span>

<span data-ttu-id="886f8-182">Mostra o que aconteceria se o `Clear-History` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="886f8-182">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="886f8-183">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="886f8-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="886f8-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="886f8-184">CommonParameters</span></span>

<span data-ttu-id="886f8-185">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="886f8-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="886f8-186">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="886f8-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="886f8-187">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="886f8-187">INPUTS</span></span>

### <span data-ttu-id="886f8-188">Nenhum</span><span class="sxs-lookup"><span data-stu-id="886f8-188">None</span></span>

<span data-ttu-id="886f8-189">Não é possível canalizar objetos para `Clear-History` .</span><span class="sxs-lookup"><span data-stu-id="886f8-189">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="886f8-190">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="886f8-190">OUTPUTS</span></span>

### <span data-ttu-id="886f8-191">Nenhum</span><span class="sxs-lookup"><span data-stu-id="886f8-191">None</span></span>

<span data-ttu-id="886f8-192">`Clear-History` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="886f8-192">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="886f8-193">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="886f8-193">NOTES</span></span>

<span data-ttu-id="886f8-194">O histórico de sessões do PowerShell é uma lista dos comandos inseridos durante uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="886f8-194">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="886f8-195">Você pode exibir o histórico, adicionar comandos de exclusão e executar comandos por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="886f8-195">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="886f8-196">Para obter mais informações, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="886f8-196">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="886f8-197">O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="886f8-197">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="886f8-198">Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="886f8-198">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="886f8-199">Esse cmdlet funciona apenas com o histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="886f8-199">This cmdlet only works with the session history.</span></span> <span data-ttu-id="886f8-200">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="886f8-200">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="886f8-201">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="886f8-201">RELATED LINKS</span></span>

[<span data-ttu-id="886f8-202">about_History</span><span class="sxs-lookup"><span data-stu-id="886f8-202">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="886f8-203">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="886f8-203">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="886f8-204">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="886f8-204">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="886f8-205">Add-History</span><span class="sxs-lookup"><span data-stu-id="886f8-205">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="886f8-206">Get-History</span><span class="sxs-lookup"><span data-stu-id="886f8-206">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="886f8-207">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="886f8-207">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="886f8-208">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="886f8-208">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="886f8-209">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="886f8-209">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

