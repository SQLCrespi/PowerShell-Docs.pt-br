---
description: Descreve como interpretar e formatar a saída de comandos remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: c5636a301017111adf97b6332237e737b4bf0716
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196153"
---
# <a name="about-remote-output"></a>Sobre a saída remota

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve como interpretar e formatar a saída de comandos remotos.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A saída de um comando que foi executado em um computador remoto pode parecer com a saída do mesmo comando executada em um computador local, mas há algumas diferenças significativas.

Este tópico explica como interpretar, Formatar e exibir a saída de comandos que são executados em computadores remotos.

## <a name="displaying-the-computer-name"></a>EXIBINDO O NOME DO COMPUTADOR

Quando você usa o cmdlet Invoke-Command para executar um comando em um computador remoto, o comando retorna um objeto que inclui o nome do computador que gerou os dados. O nome do computador remoto é armazenado na propriedade PSComputerName.

Para muitos comandos, o PSComputerName é exibido por padrão. Por exemplo, o comando a seguir executa um comando Get-Culture em dois computadores remotos, Server01 e Server02. A saída, que aparece abaixo, inclui os nomes dos computadores remotos nos quais o comando foi executado.

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

Você pode usar o parâmetro HideComputerName de Invoke-Command para ocultar a propriedade PSComputerName. Esse parâmetro é projetado para comandos que coletam dados de apenas um computador remoto.

O comando a seguir executa um comando Get-Culture no computador remoto Server01. Ele usa o parâmetro HideComputerName para ocultar a propriedade PSComputerName e as propriedades relacionadas.

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

Você também pode exibir a propriedade PSComputerName se ela não for exibida por padrão.

Por exemplo, os comandos a seguir usam o cmdlet Format-Table para adicionar a propriedade PSComputerName à saída de um comando de Get-Date remoto.

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a>EXIBINDO A PROPRIEDADE MACHINENAME

Vários cmdlets, incluindo Get-Process, Get-Service e Get-EventLog, têm um parâmetro ComputerName que obtém os objetos em um computador remoto.
Esses cmdlets não usam a comunicação remota do Windows PowerShell para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota no Windows PowerShell.

Os objetos que esses cmdlets retornam armazenam o nome do computador remoto na propriedade MachineName. (Esses objetos não têm uma propriedade PSComputerName.)

Por exemplo, esse comando obtém o processo do PowerShell nos computadores remotos Server01 e Server02. A exibição padrão não inclui a propriedade MachineName.

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

Você pode usar o cmdlet Format-Table para exibir a propriedade MachineName dos objetos de processo.

Por exemplo, o comando a seguir salva os processos na variável $p e, em seguida, usa um operador de pipeline (|) para enviar os processos em $p para o comando Format-Table. O comando usa o parâmetro Property de Format-Table para incluir a propriedade MachineName na exibição.

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

O comando mais complexo a seguir adiciona a propriedade MachineName à exibição do processo padrão. Ele usa tabelas de hash para especificar propriedades calculadas. Felizmente, você não precisa entender isso para usá-lo.

(Observe que o acento grave ['] é o caractere de continuação.)

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a>OBJETOS DESSERIALIZADOS

Quando você executa comandos remotos que geram saída, a saída do comando é transmitida pela rede de volta para o computador local.

Como a maioria dos objetos do Live Microsoft .NET Framework (como os objetos retornados pelos cmdlets do Windows PowerShell) não pode ser transmitida pela rede, os objetos dinâmicos são "serializados". Em outras palavras, os objetos dinâmicos são convertidos em representações XML do objeto e suas propriedades. Em seguida, o objeto serializado baseado em XML é transmitido pela rede.

No computador local, o Windows PowerShell recebe o objeto serializado baseado em XML e o "desserializa" convertendo o objeto baseado em XML em um objeto de .NET Framework padrão.

No entanto, o objeto desserializado não é um objeto dinâmico. É um instantâneo do objeto no momento em que ele foi serializado e inclui propriedades, mas nenhum método. Você pode usar e gerenciar esses objetos no Windows PowerShell, incluindo passá-los em pipelines, exibir as propriedades selecionadas e formatá-los.

A maioria dos objetos desserializados são automaticamente formatados para exibição por entradas no Types.ps1XML ou Format.ps1arquivos XML. No entanto, o computador local pode não ter arquivos de formatação para todos os objetos desserializados que foram gerados em um computador remoto. Quando os objetos não são formatados, todas as propriedades de cada objeto aparecem no console do em uma lista de streaming.

Quando os objetos não são formatados automaticamente, você pode usar os cmdlets de formatação, como Format-Table ou Format-List, para formatar e exibir as propriedades selecionadas. Ou, você pode usar o cmdlet Out-GridView para exibir os objetos em uma tabela.

Além disso, se você executar um comando em um computador remoto que usa cmdlets que não tem em seu computador local, os objetos que o comando retorna podem não estar formatados corretamente porque você não tem os arquivos de formatação para esses objetos em seu computador. Para obter dados de formatação de outro computador, use os cmdlets Get-FormatData e Export-FormatData.

Alguns tipos de objeto, como objetos DirectoryInfo e GUIDs, são convertidos de volta em objetos dinâmicos quando eles são recebidos. Esses objetos não precisam de tratamento ou formatação especial.

## <a name="ordering-the-results"></a>ORDENANDO OS RESULTADOS

A ordem dos nomes de computador no parâmetro ComputerName de cmdlets determina a ordem na qual o Windows PowerShell se conecta aos computadores remotos. No entanto, os resultados aparecem na ordem em que o computador local os recebe, o que pode ser uma ordem diferente.

Para alterar a ordem dos resultados, use o cmdlet Sort-Object. Você pode classificar na propriedade PSComputerName ou MachineName. Você também pode classificar outra Propriedade do objeto para que os resultados de diferentes computadores sejam intercalados.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-Process](xref:Microsoft.PowerShell.Management.Get-Process)

[Get-Service](xref:Microsoft.PowerShell.Management.Get-Service)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Out-GridView](xref:Microsoft.PowerShell.Utility.Out-GridView)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)
