---
description: Lista os cmdlets que foram projetados para uso com provedores do PowerShell.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 1f023c5a66265f561ef6644afdc45cd0149f35b7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603775"
---
# <a name="about-core-commands"></a>Sobre os comandos principais

## <a name="short-description"></a>DESCRIÇÃO BREVE
Lista os cmdlets que foram projetados para uso com provedores do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O PowerShell inclui um conjunto de cmdlets projetados especificamente para gerenciar os itens nos armazenamentos de dados que são expostos por provedores do PowerShell.
Você pode usar esses cmdlets da mesma maneira para gerenciar todos os diferentes tipos de dados que os provedores disponibilizam para você. Para obter mais informações sobre provedores, digite "Get-Help about_providers".

Por exemplo, você pode usar o cmdlet Get-ChildItem para listar os arquivos em um diretório do sistema de arquivos, as chaves em uma chave do registro ou os itens que são expostos por um provedor que você escreve ou baixa.

Veja a seguir uma lista dos cmdlets do PowerShell que foram projetados para uso com provedores:

Cmdlets ChildItem

- Get-ChildItem

Cmdlets de conteúdo

- Add-Content
- Clear-Content
- Get-Content
- Set-Content

Cmdlets de item

- Clear-Item
- Copy-Item
- Get-Item
- Invoke-Item
- Move-Item
- New-Item
- Remove-Item
- Rename-Item
- Set-Item

Cmdlets ItemProperty

- Clear-ItemProperty
- Copy-ItemProperty
- Get-ItemProperty
- Move-ItemProperty
- New-ItemProperty
- Remove-ItemProperty
- Rename-ItemProperty
- Set-ItemProperty

Cmdlets de local

- Get-Location
- Pop-Location
- Push-Location
- Set-Location

Cmdlets de caminho

- Join-Path
- Convert-Path
- Split-Path
- Resolve-Path
- Test-Path

Cmdlets PSDrive

- Get-PSDrive
- New-PSDrive
- Remove-PSDrive

Cmdlets PSProvider

- Get-PSProvider

Para obter mais informações sobre um cmdlet, digite `get-help <cmdlet-name>` .

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Providers](about_Providers.md)

