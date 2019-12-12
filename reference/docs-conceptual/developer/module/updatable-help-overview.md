---
title: Visão geral da ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: 3f7388a9-9fa8-42bc-b294-538c9a01e30a
caps.latest.revision: 12
ms.openlocfilehash: f2dfb9642ba2dde38124142b659b425bbbb00f37
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366955"
---
# <a name="updatable-help-overview"></a>Visão geral da ajuda atualizável

Este documento fornece uma introdução básica ao design e operação do recurso de ajuda atualizável do Windows PowerShell. Ele foi projetado para autores de módulo e outros que fornecem tópicos de ajuda do Windows PowerShell para os usuários.

## <a name="introduction"></a>Introdução

Os tópicos de ajuda do Windows PowerShell são parte integrante da experiência do Windows PowerShell. Assim como os módulos do Windows PowerShell, os tópicos da ajuda são continuamente atualizados e aprimorados pelos autores e pelas contribuições da comunidade de usuários do Windows PowerShell.

O recurso de *ajuda atualizável* , introduzido no Windows PowerShell 3,0, garante que os usuários tenham as versões mais recentes dos tópicos da ajuda no prompt de comando, mesmo para comandos internos do Windows PowerShell, sem baixar novos módulos ou executar Windows Update. A ajuda atualizável torna a atualização simples, fornecendo cmdlets que baixam as versões mais recentes dos tópicos de ajuda da Internet e as instalam nos subdiretórios corretos no computador local do usuário. Até mesmo os usuários que estão atrás de firewalls podem usar os novos cmdlets para obter ajuda atualizada de um compartilhamento de arquivos interno.

A ajuda atualizável tem suporte total de todos os módulos do Windows PowerShell no Windows® 8 e do Windows Server® 2012, e seus recursos estão disponíveis para todos os autores de módulo do Windows PowerShell. A ajuda atualizável dá suporte apenas a arquivos de ajuda baseados em XML. Ele não oferece suporte à ajuda baseada em comentários.

A ajuda atualizável inclui os seguintes recursos.

- O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) , que determina se os usuários têm os arquivos de ajuda mais recentes para um módulo e, caso contrário, baixa os arquivos de ajuda mais recentes da Internet, os descompactam e os instala nos subdiretórios de módulo corretos no computador do usuário.
  Os usuários podem usar o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) para exibir imediatamente os tópicos da ajuda recém-instalados.
  Eles não precisam reiniciar o PowerShell.

- O cmdlet [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) , que baixa os arquivos de ajuda mais recentes da Internet e os salva em um diretório do sistema de arquivos. Os usuários podem usar o cmdlet `Update-Help` para obter arquivos de ajuda do diretório do sistema de arquivos e descompactá-los e instalá-los nos subdiretórios do módulo no computador do usuário. O cmdlet `Save-Help` foi projetado para usuários que têm acesso limitado ou sem Internet e para empresas que preferem limitar o acesso à Internet.

- **Ajuda para um módulo**. Os arquivos de ajuda para um módulo são gerenciados e entregues como uma unidade, para que os usuários possam obter todos os arquivos de ajuda para os módulos que usam. A ajuda atualizável tem suporte apenas para módulos, não para snap-ins do Windows PowerShell.

- **Suporte à versão**. A ajuda atualizável usa quatro posições padrão (N1. N2. N3. N4) números de versão. A ajuda atualizável baixa arquivos de ajuda quando o número de versão dos arquivos de ajuda no computador do usuário (ou no diretório `Save-Help`) é menor do que o número de versão dos arquivos de ajuda no local da Internet.

- **Suporte a vários idiomas**. A ajuda atualizável oferece suporte a arquivos de ajuda de módulo em várias culturas de interface do usuário. Nomes de arquivo de ajuda atualizáveis incluem códigos de idioma padrão, como "en-US" e "ja-JP", e os cmdlets `Update-Help` e `Save-Help` colocam os arquivos de ajuda em subdiretórios específicos do idioma do diretório do módulo.

- **Ajuda gerada automaticamente**. O cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) exibe a ajuda básica para comandos que não têm arquivos de ajuda. A ajuda gerada automaticamente inclui a sintaxe e os aliases de comando e instruções para usar a ajuda online e a ajuda atualizável.

- **Ajuda online aprimorada**. O acesso fácil à ajuda online não requer mais arquivos de ajuda. O parâmetro **online** do cmdlet `Get-Help` agora Obtém a URL de um tópico da ajuda online do valor da propriedade **HelpUri** de qualquer comando, se não for possível encontrar a URL da ajuda online em um arquivo de ajuda. Você pode preencher a propriedade **HelpUri** adicionando um atributo **HelpUri** ao código de cmdlets, funções e comandos CIM, ou usando o **. Vincular** diretiva de ajuda baseada em comentário em fluxos de trabalho e scripts.

  Para tornar os arquivos de ajuda atualizáveis, os módulos do Windows PowerShell no Windows 8 e no Windows Server vNext não vêm com os arquivos de ajuda. Os usuários podem usar a ajuda atualizável para instalar os arquivos de ajuda e atualizá-los. Os autores de outros módulos podem incluir arquivos de ajuda em módulos ou omiti-los. O suporte para a ajuda atualizável é opcional, mas recomendado.
