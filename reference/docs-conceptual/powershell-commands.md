---
title: O que é um comando do PowerShell?
description: O PowerShell permite executar qualquer comando disponível no sistema e inclui o comando específico do PowerShell conhecido como cmdlets.
ms.date: 03/31/2021
ms.openlocfilehash: b6e54349ec15df3327c1f0525dce1a30ad35a6ac
ms.sourcegitcommit: eeedd4472b6cc6158494296c355579791e688baa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106104007"
---
# <a name="powershell-commands"></a>Comandos do PowerShell

O PowerShell permite executar qualquer comando disponível no sistema, incluindo comandos específicos do PowerShell conhecidos como cmdlets (pronunciado "command-lets").

## <a name="what-is-a-cmdlet"></a>O que é um cmdlet?

O cmdlet é um comando único que participa da semântica de pipeline do PowerShell e geralmente retorna um objeto .NET. Os cmdlets são comandos nativos do PowerShell, não executáveis autônomos. Eles são coletados em módulos do PowerShell que podem ser carregados sob demanda. Os cmdlets podem ser gravados em qualquer linguagem .NET compilada ou na própria linguagem de script do PowerShell.

## <a name="cmdlet-names"></a>Nomes dos cmdlets

O PowerShell usa um par de nomes _verbo-substantivo_ para nomear cmdlets. Por exemplo, o cmdlet `Get-Command` incluído no PowerShell é usado para obter todos os cmdlets registrados no shell de comando. O verbo identifica a ação que o cmdlet executa, e o substantivo identifica o recurso no qual o cmdlet realiza sua ação.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre o PowerShell e como encontrar outros cmdlets, confira o tutorial do PowerShell Bits [Descobrir o PowerShell](learn/tutorials/01-discover-powershell.md).

Para saber mais sobre como criar seus cmdlets, confira os seguintes recursos:

Cmdlets baseados em script

- [about_Functions_Advanced](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [about_Functions_CmdletBindingAttribute](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [about_Functions_Advanced_Methods](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

Cmdlets compilados (documentos do SDK do PowerShell)

- [Visão geral do cmdlet](developer/cmdlet/cmdlet-overview.md)
