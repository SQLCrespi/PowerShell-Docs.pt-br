---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: be47925211c57760ddbd0bd4c8e985e161d24593
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597391"
---
# <span data-ttu-id="80ca5-102">Get-History</span><span class="sxs-lookup"><span data-stu-id="80ca5-102">Get-History</span></span>

## <span data-ttu-id="80ca5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="80ca5-103">SYNOPSIS</span></span>
<span data-ttu-id="80ca5-104">Obtém uma lista dos comandos inseridos durante a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="80ca5-104">Gets a list of the commands entered during the current session.</span></span>

## <span data-ttu-id="80ca5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80ca5-105">SYNTAX</span></span>

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="80ca5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80ca5-106">DESCRIPTION</span></span>

<span data-ttu-id="80ca5-107">O `Get-History` cmdlet obtém o histórico de sessão, ou seja, a lista de comandos inseridos durante a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="80ca5-107">The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="80ca5-108">O PowerShell mantém automaticamente um histórico de cada sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-108">PowerShell automatically maintains a history of each session.</span></span> <span data-ttu-id="80ca5-109">O número de entradas no histórico de sessão é determinado pelo valor da variável de `$MaximumHistoryCount` preferência.</span><span class="sxs-lookup"><span data-stu-id="80ca5-109">The number of entries in the session history is determined by the value of the `$MaximumHistoryCount` preference variable.</span></span> <span data-ttu-id="80ca5-110">A partir do Windows PowerShell 3,0, o valor padrão é `4096` .</span><span class="sxs-lookup"><span data-stu-id="80ca5-110">Beginning in Windows PowerShell 3.0, the default value is `4096`.</span></span> <span data-ttu-id="80ca5-111">Por padrão, os arquivos de histórico são salvos na pasta raiz, mas você pode salvá-lo em qualquer local.</span><span class="sxs-lookup"><span data-stu-id="80ca5-111">By default, history files are saved in the home directory, but you can save the file in any location.</span></span> <span data-ttu-id="80ca5-112">Para obter mais informações sobre os recursos de histórico no PowerShell, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="80ca5-112">For more information about the history features in PowerShell, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="80ca5-113">O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="80ca5-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="80ca5-114">Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="80ca5-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="80ca5-115">Esse cmdlet funciona apenas com o histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="80ca5-116">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="80ca5-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="80ca5-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="80ca5-117">EXAMPLES</span></span>

### <span data-ttu-id="80ca5-118">Exemplo 1: obter o histórico de sessão</span><span class="sxs-lookup"><span data-stu-id="80ca5-118">Example 1: Get the session history</span></span>

<span data-ttu-id="80ca5-119">Este exemplo obtém as entradas no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-119">This example gets the entries in the session history.</span></span> <span data-ttu-id="80ca5-120">A exibição padrão mostra cada comando e sua ID, que indica a ordem em que eles foram executados.</span><span class="sxs-lookup"><span data-stu-id="80ca5-120">The default display shows each command and its ID, which indicates the order in which they ran.</span></span>

```powershell
Get-History
```

### <span data-ttu-id="80ca5-121">Exemplo 2: obter entradas que incluem uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="80ca5-121">Example 2: Get entries that include a string</span></span>

<span data-ttu-id="80ca5-122">Este exemplo obtém entradas no histórico de comandos que incluem o serviço de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="80ca5-122">This example gets entries in the command history that include the string service.</span></span> <span data-ttu-id="80ca5-123">O primeiro comando obtém todas as entradas no histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-123">The first command gets all entries in the session history.</span></span> <span data-ttu-id="80ca5-124">O operador de pipeline ( `|` ) passa os resultados para o `Where-Object` cmdlet, que seleciona apenas os comandos que incluem o serviço.</span><span class="sxs-lookup"><span data-stu-id="80ca5-124">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects only the commands that include service.</span></span>

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### <span data-ttu-id="80ca5-125">Exemplo 3: exportar entradas de histórico até uma ID específica</span><span class="sxs-lookup"><span data-stu-id="80ca5-125">Example 3: Export history entries up to a specific ID</span></span>

<span data-ttu-id="80ca5-126">Este exemplo obtém as cinco entradas de histórico mais recentes que terminam com a entrada 7.</span><span class="sxs-lookup"><span data-stu-id="80ca5-126">This example gets the five most recent history entries ending with entry 7.</span></span> <span data-ttu-id="80ca5-127">O operador de pipeline passa o resultado para o `Export-Csv` cmdlet, que formata o histórico como texto separado por vírgula e o salva no arquivo de History.csv.</span><span class="sxs-lookup"><span data-stu-id="80ca5-127">The pipeline operator passes the result to the `Export-Csv` cmdlet, which formats the history as comma-separated text and saves it in the History.csv file.</span></span> <span data-ttu-id="80ca5-128">O arquivo inclui os dados que são exibidos quando você formata o histórico como uma lista.</span><span class="sxs-lookup"><span data-stu-id="80ca5-128">The file includes the data that is displayed when you format the history as a list.</span></span> <span data-ttu-id="80ca5-129">Isso inclui as horas de status e de início e de término do comando.</span><span class="sxs-lookup"><span data-stu-id="80ca5-129">This includes the status and start and end times of the command.</span></span>

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### <span data-ttu-id="80ca5-130">Exemplo 4: exibir o comando mais recente</span><span class="sxs-lookup"><span data-stu-id="80ca5-130">Example 4: Display the most recent command</span></span>

<span data-ttu-id="80ca5-131">Este exemplo obtém o último comando no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="80ca5-131">This example gets the last command in the command history.</span></span> <span data-ttu-id="80ca5-132">O último comando é o comando inserido mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="80ca5-132">The last command is the most recently entered command.</span></span> <span data-ttu-id="80ca5-133">Esse comando usa o parâmetro **Count** para exibir apenas um comando.</span><span class="sxs-lookup"><span data-stu-id="80ca5-133">This command uses the **Count** parameter to display just one command.</span></span> <span data-ttu-id="80ca5-134">Por padrão, `Get-History` o Obtém os comandos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="80ca5-134">By default, `Get-History` gets the most recent commands.</span></span> <span data-ttu-id="80ca5-135">Este comando pode ser abreviado como "h - c 1" e é equivalente a pressionar a tecla de seta para cima.</span><span class="sxs-lookup"><span data-stu-id="80ca5-135">This command can be abbreviated to "h -c 1" and is equivalent to pressing the up-arrow key.</span></span>

```powershell
Get-History -Count 1
```

### <span data-ttu-id="80ca5-136">Exemplo 5: exibir todas as propriedades das entradas no histórico</span><span class="sxs-lookup"><span data-stu-id="80ca5-136">Example 5: Display all the properties of the entries in the history</span></span>

<span data-ttu-id="80ca5-137">Este exemplo exibe todas as propriedades de entradas no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-137">This example displays all of the properties of entries in the session history.</span></span> <span data-ttu-id="80ca5-138">O operador de pipeline passa os resultados de um `Get-History` comando para o `Format-List` cmdlet, que exibe todas as propriedades de cada entrada de histórico.</span><span class="sxs-lookup"><span data-stu-id="80ca5-138">The pipeline operator passes the results of a `Get-History` command to the `Format-List` cmdlet, which displays all of the properties of each history entry.</span></span> <span data-ttu-id="80ca5-139">Isso inclui a ID, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="80ca5-139">This includes the ID, status, and start and end times of the command.</span></span>

```powershell
Get-History | Format-List -Property *
```

## <span data-ttu-id="80ca5-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80ca5-140">PARAMETERS</span></span>

### <span data-ttu-id="80ca5-141">-Contagem</span><span class="sxs-lookup"><span data-stu-id="80ca5-141">-Count</span></span>

<span data-ttu-id="80ca5-142">Especifica o número das entradas de histórico mais recentes que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="80ca5-142">Specifies the number of the most recent history entries that this cmdlet gets.</span></span> <span data-ttu-id="80ca5-143">Por padrão, o `Get-History` obtém todas as entradas no histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-143">By, default, `Get-History` gets all entries in the session history.</span></span> <span data-ttu-id="80ca5-144">Se você usar ambos os parâmetros **Count** e **Id** em um comando, a exibição é encerrada com o comando especificado pelo parâmetro **Id**.</span><span class="sxs-lookup"><span data-stu-id="80ca5-144">If you use both the **Count** and **Id** parameters in a command, the display ends with the command that is specified by the **Id** parameter.</span></span>

<span data-ttu-id="80ca5-145">No Windows PowerShell 2,0, por padrão, `Get-History` o Obtém as 32 entradas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="80ca5-145">In Windows PowerShell 2.0, by default, `Get-History` gets the 32 most recent entries.</span></span>

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

### <span data-ttu-id="80ca5-146">-Id</span><span class="sxs-lookup"><span data-stu-id="80ca5-146">-Id</span></span>

<span data-ttu-id="80ca5-147">Especifica uma matriz de IDs de entradas no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-147">Specifies an array of the IDs of entries in the session history.</span></span> <span data-ttu-id="80ca5-148">`Get-History` Obtém apenas as entradas especificadas.</span><span class="sxs-lookup"><span data-stu-id="80ca5-148">`Get-History` gets only specified entries.</span></span> <span data-ttu-id="80ca5-149">Se você usar os parâmetros **ID** e **Count** em um comando, `Get-History` o obterá as entradas mais recentes terminando com a entrada especificada pelo parâmetro **ID** .</span><span class="sxs-lookup"><span data-stu-id="80ca5-149">If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the most recent entries ending with the entry specified by the **Id** parameter.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="80ca5-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="80ca5-150">CommonParameters</span></span>

<span data-ttu-id="80ca5-151">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="80ca5-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80ca5-152">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="80ca5-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80ca5-153">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="80ca5-153">INPUTS</span></span>

### <span data-ttu-id="80ca5-154">System.Int64</span><span class="sxs-lookup"><span data-stu-id="80ca5-154">System.Int64</span></span>

<span data-ttu-id="80ca5-155">É possível canalizar uma ID de histórico para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80ca5-155">You can pipe a history ID to this cmdlet.</span></span>

## <span data-ttu-id="80ca5-156">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="80ca5-156">OUTPUTS</span></span>

### <span data-ttu-id="80ca5-157">Microsoft. PowerShell. Commands. HistoryInfo</span><span class="sxs-lookup"><span data-stu-id="80ca5-157">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="80ca5-158">Esse cmdlet retorna um objeto de histórico para cada item de histórico que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="80ca5-158">This cmdlet returns a history object for each history item that it gets.</span></span>

## <span data-ttu-id="80ca5-159">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="80ca5-159">NOTES</span></span>

<span data-ttu-id="80ca5-160">O histórico da sessão é uma lista dos comandos inseridos durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="80ca5-160">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="80ca5-161">O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="80ca5-161">The session history represents the run order, the status, and the start and end times of the command.</span></span> <span data-ttu-id="80ca5-162">À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="80ca5-162">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="80ca5-163">Para obter mais informações sobre o histórico de comandos, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="80ca5-163">For more information about the command history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="80ca5-164">A partir do Windows PowerShell 3,0, o valor padrão da `$MaximumHistoryCount` variável de preferência é `4096` .</span><span class="sxs-lookup"><span data-stu-id="80ca5-164">Starting in Windows PowerShell 3.0, the default value of the `$MaximumHistoryCount` preference variable is `4096`.</span></span> <span data-ttu-id="80ca5-165">No Windows PowerShell 2,0, o valor padrão é `64` .</span><span class="sxs-lookup"><span data-stu-id="80ca5-165">In Windows PowerShell 2.0, the default value is `64`.</span></span> <span data-ttu-id="80ca5-166">Para obter mais informações sobre a `$MaximumHistoryCount` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="80ca5-166">For more information about the `$MaximumHistoryCount` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="80ca5-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="80ca5-167">RELATED LINKS</span></span>

[<span data-ttu-id="80ca5-168">Add-History</span><span class="sxs-lookup"><span data-stu-id="80ca5-168">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="80ca5-169">Clear-History</span><span class="sxs-lookup"><span data-stu-id="80ca5-169">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="80ca5-170">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="80ca5-170">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="80ca5-171">about_History</span><span class="sxs-lookup"><span data-stu-id="80ca5-171">about_History</span></span>](About/about_History.md)
