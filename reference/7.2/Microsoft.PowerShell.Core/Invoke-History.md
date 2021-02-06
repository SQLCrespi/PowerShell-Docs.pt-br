---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 7fb4341a84706f7d31d463bb527a1a31f387c2ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595778"
---
# <span data-ttu-id="6ecfc-102">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="6ecfc-102">Invoke-History</span></span>

## <span data-ttu-id="6ecfc-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6ecfc-103">SYNOPSIS</span></span>
<span data-ttu-id="6ecfc-104">Executa comandos do histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-104">Runs commands from the session history.</span></span>

## <span data-ttu-id="6ecfc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ecfc-105">SYNTAX</span></span>

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6ecfc-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ecfc-106">DESCRIPTION</span></span>

<span data-ttu-id="6ecfc-107">O `Invoke-History` cmdlet executa comandos do histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-107">The `Invoke-History` cmdlet runs commands from the session history.</span></span> <span data-ttu-id="6ecfc-108">Você pode passar objetos que representam os comandos de Get-History para `Invoke-History` , ou pode identificar comandos no histórico atual usando seu número de **ID** .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-108">You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number.</span></span> <span data-ttu-id="6ecfc-109">Para localizar o número de identificação de um comando, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-109">To find the identification number of a command, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="6ecfc-110">O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-110">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="6ecfc-111">Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-111">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="6ecfc-112">Esse cmdlet funciona apenas com o histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-112">This cmdlet only works with the session history.</span></span> <span data-ttu-id="6ecfc-113">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="6ecfc-113">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="6ecfc-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6ecfc-114">EXAMPLES</span></span>

### <span data-ttu-id="6ecfc-115">Exemplo 1: executar o comando mais recente no histórico</span><span class="sxs-lookup"><span data-stu-id="6ecfc-115">Example 1: Run the most recent command in the history</span></span>

<span data-ttu-id="6ecfc-116">Este exemplo executa o comando Last, ou mais recente, no histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-116">This example runs the last, or most recent, command in the session history.</span></span> <span data-ttu-id="6ecfc-117">Você pode abreviar este comando como `r` , o alias para `Invoke-History` .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-117">You can abbreviate this command as `r`, the alias for `Invoke-History`.</span></span>

```powershell
Invoke-History
```

### <span data-ttu-id="6ecfc-118">Exemplo 2: executar o comando que tem uma ID especificada</span><span class="sxs-lookup"><span data-stu-id="6ecfc-118">Example 2: Run the command that has a specified ID</span></span>

<span data-ttu-id="6ecfc-119">Este exemplo executa o comando no histórico de sessão com **Id** 132.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-119">This example runs the command in the session history with **Id** 132.</span></span> <span data-ttu-id="6ecfc-120">Como o nome do parâmetro **ID** é opcional, você pode abreviar este comando como o seguinte: `Invoke-History 132` , `ihy 132` ou `r 132` .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-120">Because the name of the **Id** parameter is optional, you can abbreviate this command as the following: `Invoke-History 132`, `ihy 132`, or `r 132`.</span></span>

```powershell
Invoke-History -Id 132
```

### <span data-ttu-id="6ecfc-121">Exemplo 3: executar o comando mais recente usando o texto do comando</span><span class="sxs-lookup"><span data-stu-id="6ecfc-121">Example 3: Run the most recent command by using the command text</span></span>

<span data-ttu-id="6ecfc-122">Este exemplo executa o comando mais recente `Get-Process` no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-122">This example runs the most recent `Get-Process` command in the session history.</span></span> <span data-ttu-id="6ecfc-123">Quando você digita caracteres para o parâmetro **ID** , `Invoke-History` o executa o primeiro comando que ele encontra que corresponde ao padrão, começando com os comandos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-123">When you type characters for the **Id** parameter, `Invoke-History` runs the first command that it finds that matches the pattern, starting with the most recent commands.</span></span>

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> <span data-ttu-id="6ecfc-124">A correspondência de padrões não diferencia maiúsculas de minúsculas, mas o padrão corresponde ao início da linha.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-124">Pattern matching is case-insensitive, but the pattern matches the beginning of the line.</span></span>

### <span data-ttu-id="6ecfc-125">Exemplo 4: executar uma sequência de comandos do histórico</span><span class="sxs-lookup"><span data-stu-id="6ecfc-125">Example 4: Run a sequence of commands from the history</span></span>

<span data-ttu-id="6ecfc-126">Este exemplo executa os comandos 16 a 24.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-126">This example runs commands 16 through 24.</span></span> <span data-ttu-id="6ecfc-127">Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-127">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command one time for each **Id** value.</span></span>

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### <span data-ttu-id="6ecfc-128">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="6ecfc-128">Example 5</span></span>

<span data-ttu-id="6ecfc-129">Este exemplo executa os sete comandos no histórico que terminam com o comando 255 (249 a 255).</span><span class="sxs-lookup"><span data-stu-id="6ecfc-129">This example runs the seven commands in the history that end with command 255 (249 through 255).</span></span> <span data-ttu-id="6ecfc-130">Ele usa o `Get-History` cmdlet para recuperar os comandos.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-130">It uses the `Get-History` cmdlet to retrieve the commands.</span></span> <span data-ttu-id="6ecfc-131">Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-131">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command once for each **Id** value.</span></span>

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## <span data-ttu-id="6ecfc-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ecfc-132">PARAMETERS</span></span>

### <span data-ttu-id="6ecfc-133">-Id</span><span class="sxs-lookup"><span data-stu-id="6ecfc-133">-Id</span></span>

<span data-ttu-id="6ecfc-134">Especifica a **ID** de um comando no histórico.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-134">Specifies the **Id** of a command in the history.</span></span> <span data-ttu-id="6ecfc-135">Você pode digitar o número de **ID** do comando ou os primeiros caracteres do comando.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-135">You can type the **Id** number of the command or the first few characters of the command.</span></span>

<span data-ttu-id="6ecfc-136">Se você digitar caracteres, `Invoke-History` o corresponderá primeiro aos comandos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-136">If you type characters, `Invoke-History` matches the most recent commands first.</span></span> <span data-ttu-id="6ecfc-137">Se você omitir esse parâmetro, `Invoke-History` o executará o último comando ou o mais recente.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-137">If you omit this parameter, `Invoke-History` runs the last, or most recent, command.</span></span> <span data-ttu-id="6ecfc-138">Para localizar o número de **ID** de um comando, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-138">To find the **Id** number of a command, use the `Get-History` cmdlet.</span></span>

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

### <span data-ttu-id="6ecfc-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6ecfc-139">-Confirm</span></span>

<span data-ttu-id="6ecfc-140">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6ecfc-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6ecfc-141">-WhatIf</span></span>

<span data-ttu-id="6ecfc-142">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6ecfc-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6ecfc-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6ecfc-144">CommonParameters</span></span>

<span data-ttu-id="6ecfc-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ecfc-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ecfc-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ecfc-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6ecfc-147">INPUTS</span></span>

### <span data-ttu-id="6ecfc-148">System.String</span><span class="sxs-lookup"><span data-stu-id="6ecfc-148">System.String</span></span>

<span data-ttu-id="6ecfc-149">É possível canalizar uma **ID** de histórico para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-149">You can pipe a history **Id** to this cmdlet.</span></span>

## <span data-ttu-id="6ecfc-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6ecfc-150">OUTPUTS</span></span>

### <span data-ttu-id="6ecfc-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6ecfc-151">None</span></span>

<span data-ttu-id="6ecfc-152">Esse cmdlet não gera nenhuma saída, mas a saída pode ser gerada pelos comandos que são `Invoke-History` executados.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-152">This cmdlet does not generate any output, but output might be generated by the commands that `Invoke-History` runs.</span></span>

## <span data-ttu-id="6ecfc-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6ecfc-153">NOTES</span></span>

<span data-ttu-id="6ecfc-154">O histórico da sessão é uma lista dos comandos inseridos durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-154">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="6ecfc-155">O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-155">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="6ecfc-156">À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="6ecfc-156">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="6ecfc-157">Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="6ecfc-157">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="6ecfc-158">Você também pode consultar `Invoke-History` por seus aliases internos `r` e `ihy` .</span><span class="sxs-lookup"><span data-stu-id="6ecfc-158">You can also refer to `Invoke-History` by its built-in aliases, `r` and `ihy`.</span></span> <span data-ttu-id="6ecfc-159">Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="6ecfc-159">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="6ecfc-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6ecfc-160">RELATED LINKS</span></span>

[<span data-ttu-id="6ecfc-161">Add-History</span><span class="sxs-lookup"><span data-stu-id="6ecfc-161">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="6ecfc-162">Clear-History</span><span class="sxs-lookup"><span data-stu-id="6ecfc-162">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="6ecfc-163">Get-History</span><span class="sxs-lookup"><span data-stu-id="6ecfc-163">Get-History</span></span>](Get-History.md)

