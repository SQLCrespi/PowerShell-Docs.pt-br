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
# Write-Information

## SINOPSE

Especifica como o PowerShell lida com dados de fluxo de informações para um comando.

## SYNTAX

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Write-Information` cmdlet especifica como o PowerShell lida com dados de fluxo de informações para um comando.

O Windows PowerShell 5,0 apresenta um fluxo de informações novo e estruturado. Você pode usar esse fluxo para transmitir dados estruturados entre um script e seus chamadores ou o aplicativo host.
`Write-Information` permite que você adicione uma mensagem informativa ao fluxo e especifique como o PowerShell lida com dados de fluxo de informações para um comando. Os fluxos de informações também funcionam para o `PowerShell.Streams` , trabalhos e tarefas agendadas.

> [!NOTE]
> O fluxo de informações não segue a convenção padrão de prefixar suas mensagens com "[nome do fluxo]:". Isso foi desenvolvido para fins de brevidade e Visual limpeza.

O `$InformationPreference` valor da variável de preferência determina se a mensagem que você fornece para `Write-Information` é exibida no ponto esperado na operação de um script. Como o valor padrão dessa variável é `SilentlyContinue` , por padrão, as mensagens informativas não são mostradas. Se você não quiser alterar o valor de `$InformationPreference` , poderá substituir seu valor adicionando o `InformationAction` parâmetro comum ao comando. Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) e [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

> [!NOTE]
> A partir do Windows PowerShell 5,0, `Write-Host` é um wrapper para `Write-Information` isso permite que você use `Write-Host` para emitir a saída para o fluxo de informações. Isso permite a **captura** ou **supressão** de dados gravados usando `Write-Host` enquanto preserva a compatibilidade com versões anteriores. Para obter mais informações, consulte [write-host](Write-Host.md)

`Write-Information` também é uma atividade de fluxo de trabalho com suporte no PowerShell 5. x.

## EXEMPLOS

### Exemplo 1: gravar informações para Get-Results

Neste exemplo, você mostra uma mensagem informativa, "obteve seus recursos!", depois de executar o `Get-WindowsFeature` comando para localizar todos os recursos que têm um valor de nome que começa com ' p '.
Como a `$InformationPreference` variável ainda está definida como seu padrão, `SilentlyContinue` , você adiciona o `InformationAction` parâmetro para substituir o `$InformationPreference` valor e mostra a mensagem. O `InformationAction` valor é Continue, o que significa que a mensagem é mostrada, mas o script ou comando continua, se ainda não tiver terminado.

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

### Exemplo 2: gravar informações e marcá-las

Neste exemplo, você usa `Write-Information` o para permitir que os usuários saibam que eles precisarão executar outro comando depois de terminarem a execução do comando atual. O exemplo adiciona as instruções de marca à mensagem informativa. Depois de executar esse comando, se você pesquisar as mensagens marcadas no fluxo de informações, a mensagem especificada aqui estaria entre os resultados.

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

### Exemplo 3: gravar informações em um arquivo

Neste exemplo, você redirecionará o fluxo de informações na função para um `Info.txt` usando o código `6>` . Ao abrir o `Info.txt` arquivo, você verá o texto "aqui".

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

### Exemplo 4: passar objeto para gravar informações

Neste exemplo, você pode usar `Write-Information` para gravar os 10 maiores processos de utilização da CPU da `Get-Process` saída do objeto que passa por vários pipelines.

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

## PARAMETERS

### -MessageData

Especifica uma mensagem informativa que você deseja exibir aos usuários à medida que eles executam um script ou comando. Para obter melhores resultados, coloque a mensagem informativa entre aspas.

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

### -Marcas

Especifica uma cadeia de caracteres simples que você pode usar para classificar e filtrar mensagens que você adicionou ao fluxo de informações com `Write-Information` . Esse parâmetro funciona de forma semelhante ao parâmetro **Tags** no `New-ModuleManifest` .

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Object

`Write-Information` o aceita objetos piped para passar para o fluxo de informações.

## SAÍDAS

### System. Management. Automation. InformationRecord

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)

[Write-Output](Write-Output.md)
