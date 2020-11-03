---
description: Descreve os snap-ins do Windows PowerShell e mostra como usá-los e gerenciá-los.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: cc22f8de0b9d8a55dcfa12f3b47f3852d891e67b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196000"
---
# <a name="about-pssnapins"></a>Sobre os PSSnapins

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os snap-ins do Windows PowerShell e mostra como usá-los e gerenciá-los.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Um snap-in do Windows PowerShell é um assembly Microsoft .NET Framework que contém os provedores do Windows PowerShell e \/ ou cmdlets. O Windows PowerShell inclui um conjunto de snap-ins básicos, mas você pode estender o poder e o valor do Windows PowerShell adicionando snap-ins que contêm provedores e cmdlets que você cria ou obtém de outras pessoas.

Quando você adiciona um snap-in, os cmdlets e provedores que ele contém estão imediatamente disponíveis para uso na sessão atual, mas a alteração afeta apenas a sessão atual.

Para adicionar o snap-in a todas as sessões futuras, salve-o em seu perfil do Windows PowerShell. Você também pode usar o cmdlet Export-Console para salvar os nomes de snap-in em um arquivo de console e, em seguida, usá-lo em sessões futuras. Você pode até mesmo salvar vários arquivos de console, cada um com um conjunto diferente de snap-ins.

Observação: os snap-ins (PSSnapins) do Windows PowerShell estão disponíveis para uso no Windows PowerShell 3,0 e no Windows PowerShell 2,0. Eles podem ser alterados ou indisponíveis nas versões subsequentes. Para compactar provedores e cmdlets do Windows PowerShell, use módulos. Para obter informações sobre como criar módulos e converter snap-ins em módulos, consulte [escrevendo um módulo do Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

### <a name="finding-snap-ins"></a>LOCALIZANDO SNAP-INS

Para obter uma lista dos snap-ins do Windows PowerShell em seu computador, digite:

```powershell
Get-PSSnapin
```

Para obter o snap-in para cada provedor do Windows PowerShell, digite:

```powershell
Get-PSProvider | Format-List name, pssnapin
```

Para obter uma lista dos cmdlets em um snap-in do Windows PowerShell, digite:

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a>INSTALANDO UM SNAP-IN

Os snap-ins internos são registrados no sistema e adicionados à sessão padrão quando você inicia o Windows PowerShell. No entanto, você precisa registrar snap-ins que você cria ou obtém de outros e, em seguida, adicionar os snap-ins à sua sessão.

### <a name="registering-a-snap-in"></a>REGISTRANDO UM SNAP-IN

Um snap-in do Windows PowerShell é um programa escrito em uma linguagem .NET Framework que é compilada em um arquivo. dll. Para usar os provedores e os cmdlets em um snap-in, você deve primeiro registrar o snap-in (adicioná-lo ao registro).

A maioria dos snap-ins inclui um programa de instalação (um arquivo. exe ou. msi) que registra o arquivo. dll para você. No entanto, se você receber um snap-in como um arquivo. dll, poderá registrá-lo em seu sistema. Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](https://go.microsoft.com/fwlink/?LinkID=143619) na biblioteca MSDN.

Para obter todos os snap-ins registrados no seu sistema ou para verificar se um snap-in está registrado, digite:

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a>ADICIONANDO O SNAP-IN À SESSÃO ATUAL

Para adicionar um snap-in registrado à sessão atual, use o cmdlet Add-PsSnapin. Por exemplo, para adicionar o snap-in Microsoft SQL Server à sessão, digite:

```powershell
Add-PSSnapin sql
```

Depois que o comando for concluído, os provedores e os cmdlets no snap-in estarão disponíveis na sessão. No entanto, eles estão disponíveis apenas na sessão atual, a menos que você os salve.

### <a name="saving-the-snap-ins"></a>SALVANDO OS SNAP-INS

Para usar um snap-in em sessões futuras do Windows PowerShell, adicione o comando Add-PsSnapin ao seu perfil do Windows PowerShell. Ou então, exporte os nomes de snap-in para um arquivo de console.

Se você adicionar o comando Add-PSSnapin ao seu perfil, ele estará disponível em todas as sessões futuras do Windows PowerShell. Se você exportar os nomes dos snap-ins em sua sessão, poderá usar o arquivo de exportação somente quando precisar dos snap-ins.

Para adicionar o comando Add-PsSnapin ao seu perfil do Windows PowerShell, abra seu perfil, Cole ou digite o comando e, em seguida, salve o perfil. Para obter mais informações, consulte about_Profiles.

Para salvar os snap-ins de uma sessão no arquivo de console (. psc1), use o cmdlet Export-Console. Por exemplo, para salvar os snap-ins na configuração de sessão atual para o arquivo NewConsole. psc1 no diretório atual, digite:

```powershell
Export-Console NewConsole
```

Para obter mais informações, consulte Export-Console.

### <a name="opening-windows-powershell-with-a-console-file"></a>ABRINDO O WINDOWS POWERSHELL COM UM ARQUIVO DE CONSOLE

Para usar um arquivo de console que inclui o snap-in, inicie o Windows PowerShell (PowerShell.exe) no prompt de comando no Cmd.exe ou em outra sessão do Windows PowerShell. Use o parâmetro PsConsoleFile para especificar o arquivo de console que inclui o snap-in do. Por exemplo, o comando a seguir inicia o Windows PowerShell com o arquivo de console NewConsole. psc1:

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

Os provedores e cmdlets no snap-in agora estão disponíveis para uso na sessão.

### <a name="removing-a-snap-in"></a>REMOVENDO UM SNAP-IN

Para remover um snap-in do Windows PowerShell da sessão atual, use o cmdlet Remove-PsSnapin. Por exemplo, para remover o snap-in SQL Server da sessão atual, digite:

```powershell
Remove-PSSnapin sql
```

Esse cmdlet Remove o snap-in da sessão. O snap-in ainda está carregado, mas os provedores e os cmdlets aos quais ele dá suporte não estão mais disponíveis.

### <a name="built-in-commands"></a>COMANDOS INTERNOS

No Windows PowerShell 2,0 e em programas de host de estilo mais antigo no Windows PowerShell 3,0 e posteriores, os comandos internos instalados com o Windows PowerShell são empacotados em snap-ins que são adicionados automaticamente a todas as sessões do Windows PowerShell.

A partir do Windows PowerShell 3,0, em programas de host de estilo mais recente, aqueles que iniciam sessões usando o método InitialSessionState. CreateDefault2 – os comandos internos são empacotados em módulos. A exceção é Microsoft. PowerShell. Core, que sempre aparece como um snap-in. O snap-in principal está incluído em cada sessão por padrão. Os módulos internos são carregados automaticamente no primeiro uso.

Observação: as sessões remotas, incluindo as sessões iniciadas usando o cmdlet New-PSSession, são sessões de estilo mais antigas nas quais os comandos internos são empacotados em snap-ins.

Os seguintes snap-ins (ou módulos) são instalados com o Windows PowerShell.

- Microsoft. PowerShell. Core-contém provedores e cmdlets usados para gerenciar os recursos básicos do Windows PowerShell. Ele inclui o sistema de arquivos, o registro, o alias, o ambiente, a função e os provedores de variáveis e os cmdlets básicos, como Get-Help, Get-Command e Get-History.

- Microsoft. PowerShell. host-contém cmdlets usados pelo host do Windows PowerShell, como Start-Transcript e Stop-transcrição.

- Microsoft. PowerShell. Management-contém cmdlets como Get-Service e Get-ChildItem que são usados para gerenciar recursos baseados no Windows.

- Microsoft. PowerShell. Security-contém o provedor de certificados e os cmdlets usados para gerenciar a segurança do Windows PowerShell, como Get-ACL, Get-AuthenticodeSignature e ConvertTo-SecureString.

- Microsoft. PowerShell. Utility-contém cmdlets usados para manipular objetos e dados, como Get-Member, write-host e Format-List.

- Microsoft. WSMan. Management-contém o provedor WSMan e os cmdlets que gerenciam o Serviço Gerenciamento Remoto do Windows, como Connect-WSMan e Enable-WSManCredSSP.

## <a name="logging-snap-in-events"></a>REGISTRANDO EVENTOS DE SNAP-IN

A partir do Windows PowerShell 3,0, você pode registrar eventos de execução para os cmdlets em módulos do Windows PowerShell e snap-ins definindo a propriedade LogPipelineExecutionDetails de módulos e snap-ins como TRUE. Para obter mais informações, consulte [about_EventLogs](about_EventLogs.md).

## <a name="see-also"></a>CONSULTE TAMBÉM

[Add-PsSnapin](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[Get-PsSnapin](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[Remove-PsSnapin](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[Export-Console](xref:Microsoft.PowerShell.Core.Export-Console)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[about_Profiles](about_Profiles.md)

[about_Modules](about_Modules.md)

## <a name="keywords"></a>Palavras-chave

about_Snapins, about_Snap_ins, about_Snap-ins
