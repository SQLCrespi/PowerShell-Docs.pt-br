---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: f15902c1c6c298dd02db3edf061d56e1446ecb1f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595772"
---
# <span data-ttu-id="fa7ce-102">Write-Information</span><span class="sxs-lookup"><span data-stu-id="fa7ce-102">Write-Information</span></span>

## <span data-ttu-id="fa7ce-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fa7ce-103">SYNOPSIS</span></span>

<span data-ttu-id="fa7ce-104">Especifica como o PowerShell lida com dados de fluxo de informações para um comando.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-104">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="fa7ce-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa7ce-105">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="fa7ce-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa7ce-106">DESCRIPTION</span></span>

<span data-ttu-id="fa7ce-107">O `Write-Information` cmdlet especifica como o PowerShell lida com dados de fluxo de informações para um comando.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-107">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="fa7ce-108">O Windows PowerShell 5,0 apresenta um fluxo de informações novo e estruturado.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-108">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="fa7ce-109">Você pode usar esse fluxo para transmitir dados estruturados entre um script e seus chamadores ou o aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-109">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="fa7ce-110">`Write-Information` permite que você adicione uma mensagem informativa ao fluxo e especifique como o PowerShell lida com dados de fluxo de informações para um comando.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-110">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="fa7ce-111">Os fluxos de informações também funcionam para o `PowerShell.Streams` , trabalhos e tarefas agendadas.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-111">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="fa7ce-112">O fluxo de informações não segue a convenção padrão de prefixar suas mensagens com "[nome do fluxo]:".</span><span class="sxs-lookup"><span data-stu-id="fa7ce-112">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="fa7ce-113">Isso foi desenvolvido para fins de brevidade e Visual limpeza.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-113">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="fa7ce-114">O `$InformationPreference` valor da variável de preferência determina se a mensagem que você fornece para `Write-Information` é exibida no ponto esperado na operação de um script.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-114">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="fa7ce-115">Como o valor padrão dessa variável é `SilentlyContinue` , por padrão, as mensagens informativas não são mostradas.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-115">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="fa7ce-116">Se você não quiser alterar o valor de `$InformationPreference` , poderá substituir seu valor adicionando o `InformationAction` parâmetro comum ao comando.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-116">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="fa7ce-117">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) e [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="fa7ce-117">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa7ce-118">A partir do Windows PowerShell 5,0, `Write-Host` é um wrapper para `Write-Information` isso permite que você use `Write-Host` para emitir a saída para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-118">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="fa7ce-119">Isso permite a **captura** ou **supressão** de dados gravados usando `Write-Host` enquanto preserva a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-119">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="fa7ce-120">Para obter mais informações, consulte [write-host](Write-Host.md)</span><span class="sxs-lookup"><span data-stu-id="fa7ce-120">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="fa7ce-121">`Write-Information` também é uma atividade de fluxo de trabalho com suporte no PowerShell 5. x.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-121">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="fa7ce-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fa7ce-122">EXAMPLES</span></span>

### <span data-ttu-id="fa7ce-123">Exemplo 1: gravar informações para Get-Results</span><span class="sxs-lookup"><span data-stu-id="fa7ce-123">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="fa7ce-124">Neste exemplo, você mostra uma mensagem informativa, "obteve seus recursos!", depois de executar o `Get-WindowsFeature` comando para localizar todos os recursos que têm um valor de nome que começa com ' p '.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-124">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="fa7ce-125">Como a `$InformationPreference` variável ainda está definida como seu padrão, `SilentlyContinue` , você adiciona o `InformationAction` parâmetro para substituir o `$InformationPreference` valor e mostra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-125">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="fa7ce-126">O `InformationAction` valor é Continue, o que significa que a mensagem é mostrada, mas o script ou comando continua, se ainda não tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-126">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="fa7ce-127">Exemplo 2: gravar informações e marcá-las</span><span class="sxs-lookup"><span data-stu-id="fa7ce-127">Example 2: Write information and tag it</span></span>

<span data-ttu-id="fa7ce-128">Neste exemplo, você usa `Write-Information` o para permitir que os usuários saibam que eles precisarão executar outro comando depois de terminarem a execução do comando atual.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-128">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="fa7ce-129">O exemplo adiciona as instruções de marca à mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-129">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="fa7ce-130">Depois de executar esse comando, se você pesquisar as mensagens marcadas no fluxo de informações, a mensagem especificada aqui estaria entre os resultados.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-130">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="fa7ce-131">Exemplo 3: gravar informações em um arquivo</span><span class="sxs-lookup"><span data-stu-id="fa7ce-131">Example 3: Write information to a file</span></span>

<span data-ttu-id="fa7ce-132">Neste exemplo, você redirecionará o fluxo de informações na função para um `Info.txt` usando o código `6>` .</span><span class="sxs-lookup"><span data-stu-id="fa7ce-132">In this example, you redirect the information stream in the function to a `Info.txt` using the code `6>`.</span></span> <span data-ttu-id="fa7ce-133">Ao abrir o `Info.txt` arquivo, você verá o texto "aqui".</span><span class="sxs-lookup"><span data-stu-id="fa7ce-133">When you open the `Info.txt` file, you see the text, "Here you go."</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

### <span data-ttu-id="fa7ce-134">Exemplo 4: passar objeto para gravar informações</span><span class="sxs-lookup"><span data-stu-id="fa7ce-134">Example 4: Pass object to write information</span></span>

<span data-ttu-id="fa7ce-135">Neste exemplo, você pode usar `Write-Information` para gravar os 10 maiores processos de utilização da CPU da `Get-Process` saída do objeto que passa por vários pipelines.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-135">In this example, you can use `Write-Information` to write the top 10 highest CPU utilization processes from the `Get-Process` object output that has passes through multiple pipelines.</span></span>

```powershell
Get-Process | Sort-Object CPU -Descending |
    Select-Object Id, ProcessName, CPU -First 10 |
        Write-Information -InformationAction Continue
```

```Output
@{Id=12692; ProcessName=chrome; CPU=39431.296875}
@{Id=21292; ProcessName=OUTLOOK; CPU=23991.875}
@{Id=10548; ProcessName=CefSharp.BrowserSubprocess; CPU=20546.203125}
@{Id=312848; ProcessName=Taskmgr; CPU=13173.1875}
@{Id=10848; ProcessName=SnapClient; CPU=7014.265625}
@{Id=9760; ProcessName=Receiver; CPU=6792.359375}
@{Id=12040; ProcessName=Teams; CPU=5605.578125}
@{Id=498388; ProcessName=chrome; CPU=3062.453125}
@{Id=6900; ProcessName=chrome; CPU=2546.9375}
@{Id=9044; ProcessName=explorer; CPU=2358.765625}
```

## <span data-ttu-id="fa7ce-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa7ce-136">PARAMETERS</span></span>

### <span data-ttu-id="fa7ce-137">-MessageData</span><span class="sxs-lookup"><span data-stu-id="fa7ce-137">-MessageData</span></span>

<span data-ttu-id="fa7ce-138">Especifica uma mensagem informativa que você deseja exibir aos usuários à medida que eles executam um script ou comando.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-138">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="fa7ce-139">Para obter melhores resultados, coloque a mensagem informativa entre aspas.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-139">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fa7ce-140">-Marcas</span><span class="sxs-lookup"><span data-stu-id="fa7ce-140">-Tags</span></span>

<span data-ttu-id="fa7ce-141">Especifica uma cadeia de caracteres simples que você pode usar para classificar e filtrar mensagens que você adicionou ao fluxo de informações com `Write-Information` .</span><span class="sxs-lookup"><span data-stu-id="fa7ce-141">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="fa7ce-142">Esse parâmetro funciona de forma semelhante ao parâmetro **Tags** no `New-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="fa7ce-142">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa7ce-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fa7ce-143">CommonParameters</span></span>

<span data-ttu-id="fa7ce-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa7ce-145">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fa7ce-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa7ce-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fa7ce-146">INPUTS</span></span>

### <span data-ttu-id="fa7ce-147">System.Object</span><span class="sxs-lookup"><span data-stu-id="fa7ce-147">System.Object</span></span>

<span data-ttu-id="fa7ce-148">`Write-Information` o aceita objetos piped para passar para o fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="fa7ce-148">`Write-Information` accepts piped objects to pass to the information stream.</span></span>

## <span data-ttu-id="fa7ce-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fa7ce-149">OUTPUTS</span></span>

### <span data-ttu-id="fa7ce-150">System. Management. Automation. InformationRecord</span><span class="sxs-lookup"><span data-stu-id="fa7ce-150">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="fa7ce-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fa7ce-151">NOTES</span></span>

## <span data-ttu-id="fa7ce-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fa7ce-152">RELATED LINKS</span></span>

[<span data-ttu-id="fa7ce-153">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="fa7ce-153">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="fa7ce-154">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="fa7ce-154">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="fa7ce-155">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fa7ce-155">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="fa7ce-156">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="fa7ce-156">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="fa7ce-157">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="fa7ce-157">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="fa7ce-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="fa7ce-158">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="fa7ce-159">Write-Host</span><span class="sxs-lookup"><span data-stu-id="fa7ce-159">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="fa7ce-160">Write-Information</span><span class="sxs-lookup"><span data-stu-id="fa7ce-160">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="fa7ce-161">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="fa7ce-161">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="fa7ce-162">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="fa7ce-162">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="fa7ce-163">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="fa7ce-163">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="fa7ce-164">Write-Output</span><span class="sxs-lookup"><span data-stu-id="fa7ce-164">Write-Output</span></span>](Write-Output.md)
