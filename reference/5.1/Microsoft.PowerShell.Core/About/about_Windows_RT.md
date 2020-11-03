---
description: Explica as limitações do Windows PowerShell 4,0 no Windows RT 8,1.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195943"
---
# <a name="about-windows-rt"></a>Sobre o Windows RT

## <a name="short-description"></a>DESCRIÇÃO BREVE

Explica as limitações do Windows PowerShell 4,0 no Windows RT 8,1.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O sistema operacional Windows RT 8,1 é instalado em computadores e dispositivos (como o Microsoft Surface 2, no qual é o sistema operacional fornecido com o computador) que usam processadores ARM (Advanced RISC Machine).

O Windows PowerShell 4,0 está incluído no Windows RT 8,1. Todos os cmdlets, provedores e módulos e a maioria dos scripts projetados para o Windows PowerShell 2,0 e versões posteriores são executados no Windows RT 8,1 sem alterações.

Como o Windows RT 8,1 não inclui todos os recursos do Windows, alguns recursos do Windows PowerShell funcionam de maneira diferente ou não funcionam em dispositivos baseados no Windows RT. A lista a seguir explica as diferenças.

- O ISE do Windows PowerShell não está incluído no e não pode ser executado no Windows RT 8,1.
  ISE do Windows PowerShell requer Windows Presentation Foundation, que não está incluído no Windows RT 8,1.

- A comunicação remota do Windows PowerShell e o serviço WinRM são desabilitados por padrão.
  Para habilitar a comunicação remota, execute o cmdlet Enable-PSRemoting. Além disso, execute o cmdlet Set-Service para definir o tipo de inicialização do serviço WinRM como automático ou automático (início atrasado).

  Embora a comunicação remota esteja desabilitada, você pode usar a comunicação remota do Windows PowerShell para executar comandos em outros computadores, mas outros computadores não podem executar comandos no dispositivo Windows RT. Além disso, comunicação remota implícita, ou seja, a comunicação remota que é interna a um cmdlet ou script, e não explicitamente solicitada com parâmetros adicionados
  - o não funciona no Windows PowerShell em execução no Windows RT 8,1.

- A computação ingressada no domínio e a autenticação Kerberos não têm suporte no Windows RT 8,1. Você não pode usar o Windows PowerShell para adicionar ou gerenciar esses recursos.

- Microsoft .NET classes do Framework que não têm suporte no Windows RT 8,1 também não são suportadas pelo Windows PowerShell no Windows RT 8,1.

- As transações não estão habilitadas no Windows RT 8,1. Os cmdlets de transação, como a transação inicial e os parâmetros de transação, como UseTransaction, não funcionam corretamente.

- Todas as sessões do Windows PowerShell em dispositivos Windows RT 8,1 usam o modo de linguagem ConstrainedLanguage. O modo de linguagem ConstrainedLanguage é um complemento à integridade de código do modo de usuário (UMCI). Ele permite todos os cmdlets do Windows e elementos de linguagem do Windows PowerShell, mas restringe os tipos para garantir que os usuários não possam usar o Windows PowerShell para burlar ou violar as proteções UMCI.

Para obter mais informações sobre o modo de linguagem ConstrainedLanguage, consulte [about_Language_Modes](about_Language_Modes.md).

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Language_Modes](about_Language_Modes.md)

[about_Remote](about_Remote.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)
