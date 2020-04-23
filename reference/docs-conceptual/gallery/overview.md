---
ms.date: 06/12/2017
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery,psget
title: A Galeria do PowerShell
ms.openlocfilehash: e489d2dd4db087b53eb07d2a8793c8f586c9b210
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500574"
---
# <a name="the-powershell-gallery"></a>A Galeria do PowerShell

A Galeria do PowerShell é o repositório central de conteúdo do PowerShell. Nela, você pode encontrar módulos úteis do PowerShell que contêm comandos do PowerShell e recursos de DSC (Configuração de Estado Desejado).
Você também pode encontrar scripts do PowerShell, alguns dos quais podem conter fluxos de trabalho do PowerShell e que descrevem um conjunto de tarefas e fornecem o sequenciamento para essas tarefas. Alguns desses pacotes são criados pela Microsoft e outros são criados pela comunidade do PowerShell.

## <a name="powershellget-overview"></a>Visão geral do PowerShellGet

O módulo do PowerShellGet contém cmdlets para descoberta, instalação, atualização e publicação de pacotes PowerShell que contêm artefatos como Módulos, Recursos de DSC, Funcionalidades de Função e Scripts da [Galeria do PowerShell](https://www.PowerShellGallery.com) e outros repositórios privados.

## <a name="getting-started-with-the-gallery"></a>Introdução à Galeria

A instalação de pacotes da Galeria requer a versão mais recente do módulo PowerShellGet. Confira [Instalando o PowerShellGet](installing-psget.md) para obter instruções completas.

Confira a página [Introdução](getting-started.md) para obter mais informações sobre como usar os comandos PowerShellGet com a Galeria. Também é possível executar *Update-Help -Module PowerShellGet* para instalar a ajuda local para esses comandos.

## <a name="supported-operating-systems"></a>Sistemas operacionais com suporte

O módulo **PowerShellGet** exige o **PowerShell 3.0 ou mais recente**.

O **PowerShellGet** requer o .NET Framework 4.5 ou posterior. Você pode instalar o .NET Framework 4.5 ou acima acessando [aqui](https://msdn.microsoft.com/library/5a4x27ek.aspx).

Como **PowerShell Core** é uma plataforma cruzada, o que significa que funciona no Windows, Linux e MacOS, ele também deixa **PowerShellGet** disponível nesses sistemas. Para obter uma lista completa de sistemas compatíveis com **PowerShell Core**, consulte [Instalação do PowerShell](/powershell/scripting/install/installing-powershell).

Muitos módulos hospedados na galeria darão suporte a sistemas operacionais diferentes e têm outros requisitos.
Consulte a documentação dos módulos para saber mais.

## <a name="got-a-question-have-feedback"></a>Tem alguma pergunta? Deseja fazer comentários?

Encontre mais informações sobre a Galeria do PowerShell e o PowerShellGet na página [Introdução](getting-started.md). Forneça comentários e relate problemas usando o [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).
