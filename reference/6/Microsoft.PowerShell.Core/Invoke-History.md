---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 6745ceb3e6106bacf45d0c20fc916951316139dc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194431"
---
# <span data-ttu-id="15732-103">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="15732-103">Invoke-History</span></span>

## <span data-ttu-id="15732-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="15732-104">SYNOPSIS</span></span>
<span data-ttu-id="15732-105">Executa comandos do histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-105">Runs commands from the session history.</span></span>

## <span data-ttu-id="15732-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15732-106">SYNTAX</span></span>

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="15732-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15732-107">DESCRIPTION</span></span>

<span data-ttu-id="15732-108">O `Invoke-History` cmdlet executa comandos do histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-108">The `Invoke-History` cmdlet runs commands from the session history.</span></span> <span data-ttu-id="15732-109">Você pode passar objetos que representam os comandos de Get-History para `Invoke-History` , ou pode identificar comandos no histórico atual usando seu número de **ID** .</span><span class="sxs-lookup"><span data-stu-id="15732-109">You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number.</span></span> <span data-ttu-id="15732-110">Para localizar o número de identificação de um comando, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15732-110">To find the identification number of a command, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="15732-111">O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="15732-111">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="15732-112">Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="15732-112">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="15732-113">Esse cmdlet funciona apenas com o histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-113">This cmdlet only works with the session history.</span></span> <span data-ttu-id="15732-114">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="15732-114">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="15732-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="15732-115">EXAMPLES</span></span>

### <span data-ttu-id="15732-116">Exemplo 1: executar o comando mais recente no histórico</span><span class="sxs-lookup"><span data-stu-id="15732-116">Example 1: Run the most recent command in the history</span></span>

<span data-ttu-id="15732-117">Este exemplo executa o comando Last, ou mais recente, no histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-117">This example runs the last, or most recent, command in the session history.</span></span> <span data-ttu-id="15732-118">Você pode abreviar este comando como `r` , o alias para `Invoke-History` .</span><span class="sxs-lookup"><span data-stu-id="15732-118">You can abbreviate this command as `r`, the alias for `Invoke-History`.</span></span>

```powershell
Invoke-History
```

### <span data-ttu-id="15732-119">Exemplo 2: executar o comando que tem uma ID especificada</span><span class="sxs-lookup"><span data-stu-id="15732-119">Example 2: Run the command that has a specified ID</span></span>

<span data-ttu-id="15732-120">Este exemplo executa o comando no histórico de sessão com **Id** 132.</span><span class="sxs-lookup"><span data-stu-id="15732-120">This example runs the command in the session history with **Id** 132.</span></span> <span data-ttu-id="15732-121">Como o nome do parâmetro **ID** é opcional, você pode abreviar este comando como o seguinte: `Invoke-History 132` , `ihy 132` ou `r 132` .</span><span class="sxs-lookup"><span data-stu-id="15732-121">Because the name of the **Id** parameter is optional, you can abbreviate this command as the following: `Invoke-History 132`, `ihy 132`, or `r 132`.</span></span>

```powershell
Invoke-History -Id 132
```

### <span data-ttu-id="15732-122">Exemplo 3: executar o comando mais recente usando o texto do comando</span><span class="sxs-lookup"><span data-stu-id="15732-122">Example 3: Run the most recent command by using the command text</span></span>

<span data-ttu-id="15732-123">Este exemplo executa o comando mais recente `Get-Process` no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-123">This example runs the most recent `Get-Process` command in the session history.</span></span> <span data-ttu-id="15732-124">Quando você digita caracteres para o parâmetro **ID** , `Invoke-History` o executa o primeiro comando que ele encontra que corresponde ao padrão, começando com os comandos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="15732-124">When you type characters for the **Id** parameter, `Invoke-History` runs the first command that it finds that matches the pattern, starting with the most recent commands.</span></span>

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> <span data-ttu-id="15732-125">A correspondência de padrões não diferencia maiúsculas de minúsculas, mas o padrão corresponde ao início da linha.</span><span class="sxs-lookup"><span data-stu-id="15732-125">Pattern matching is case-insensitive, but the pattern matches the beginning of the line.</span></span>

### <span data-ttu-id="15732-126">Exemplo 4: executar uma sequência de comandos do histórico</span><span class="sxs-lookup"><span data-stu-id="15732-126">Example 4: Run a sequence of commands from the history</span></span>

<span data-ttu-id="15732-127">Este exemplo executa os comandos 16 a 24.</span><span class="sxs-lookup"><span data-stu-id="15732-127">This example runs commands 16 through 24.</span></span> <span data-ttu-id="15732-128">Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .</span><span class="sxs-lookup"><span data-stu-id="15732-128">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command one time for each **Id** value.</span></span>

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### <span data-ttu-id="15732-129">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="15732-129">Example 5</span></span>

<span data-ttu-id="15732-130">Este exemplo executa os sete comandos no histórico que terminam com o comando 255 (249 a 255).</span><span class="sxs-lookup"><span data-stu-id="15732-130">This example runs the seven commands in the history that end with command 255 (249 through 255).</span></span> <span data-ttu-id="15732-131">Ele usa o `Get-History` cmdlet para recuperar os comandos.</span><span class="sxs-lookup"><span data-stu-id="15732-131">It uses the `Get-History` cmdlet to retrieve the commands.</span></span> <span data-ttu-id="15732-132">Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .</span><span class="sxs-lookup"><span data-stu-id="15732-132">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command once for each **Id** value.</span></span>

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## <span data-ttu-id="15732-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15732-133">PARAMETERS</span></span>

### <span data-ttu-id="15732-134">-Id</span><span class="sxs-lookup"><span data-stu-id="15732-134">-Id</span></span>

<span data-ttu-id="15732-135">Especifica a **ID** de um comando no histórico.</span><span class="sxs-lookup"><span data-stu-id="15732-135">Specifies the **Id** of a command in the history.</span></span> <span data-ttu-id="15732-136">Você pode digitar o número de **ID** do comando ou os primeiros caracteres do comando.</span><span class="sxs-lookup"><span data-stu-id="15732-136">You can type the **Id** number of the command or the first few characters of the command.</span></span>

<span data-ttu-id="15732-137">Se você digitar caracteres, `Invoke-History` o corresponderá primeiro aos comandos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="15732-137">If you type characters, `Invoke-History` matches the most recent commands first.</span></span> <span data-ttu-id="15732-138">Se você omitir esse parâmetro, `Invoke-History` o executará o último comando ou o mais recente.</span><span class="sxs-lookup"><span data-stu-id="15732-138">If you omit this parameter, `Invoke-History` runs the last, or most recent, command.</span></span> <span data-ttu-id="15732-139">Para localizar o número de **ID** de um comando, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15732-139">To find the **Id** number of a command, use the `Get-History` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="15732-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="15732-140">-Confirm</span></span>

<span data-ttu-id="15732-141">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15732-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="15732-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="15732-142">-WhatIf</span></span>

<span data-ttu-id="15732-143">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="15732-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="15732-144">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="15732-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="15732-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15732-145">CommonParameters</span></span>

<span data-ttu-id="15732-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15732-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15732-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15732-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15732-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="15732-148">INPUTS</span></span>

### <span data-ttu-id="15732-149">System.String</span><span class="sxs-lookup"><span data-stu-id="15732-149">System.String</span></span>

<span data-ttu-id="15732-150">É possível canalizar uma **ID** de histórico para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15732-150">You can pipe a history **Id** to this cmdlet.</span></span>

## <span data-ttu-id="15732-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="15732-151">OUTPUTS</span></span>

### <span data-ttu-id="15732-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="15732-152">None</span></span>

<span data-ttu-id="15732-153">Esse cmdlet não gera nenhuma saída, mas a saída pode ser gerada pelos comandos que são `Invoke-History` executados.</span><span class="sxs-lookup"><span data-stu-id="15732-153">This cmdlet does not generate any output, but output might be generated by the commands that `Invoke-History` runs.</span></span>

## <span data-ttu-id="15732-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="15732-154">NOTES</span></span>

<span data-ttu-id="15732-155">O histórico da sessão é uma lista dos comandos inseridos durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="15732-155">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="15732-156">O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="15732-156">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="15732-157">À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="15732-157">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="15732-158">Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="15732-158">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="15732-159">Você também pode consultar `Invoke-History` por seus aliases internos `r` e `ihy` .</span><span class="sxs-lookup"><span data-stu-id="15732-159">You can also refer to `Invoke-History` by its built-in aliases, `r` and `ihy`.</span></span> <span data-ttu-id="15732-160">Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="15732-160">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="15732-161">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="15732-161">RELATED LINKS</span></span>

[<span data-ttu-id="15732-162">Add-History</span><span class="sxs-lookup"><span data-stu-id="15732-162">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="15732-163">Clear-History</span><span class="sxs-lookup"><span data-stu-id="15732-163">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="15732-164">Get-History</span><span class="sxs-lookup"><span data-stu-id="15732-164">Get-History</span></span>](Get-History.md)
