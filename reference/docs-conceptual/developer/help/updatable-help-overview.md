---
title: Visão geral da ajuda atualizável
ms.date: 03/22/2012
ms.openlocfilehash: 142bac764c93728d302707504d6d3fb2d50a3a7b
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892312"
---
# <a name="updatable-help-overview"></a>Visão geral da ajuda atualizável

Este documento fornece uma introdução básica ao design e operação do recurso de ajuda atualizável do PowerShell. Ele foi projetado para autores de módulo e outros que fornecem tópicos de ajuda do Windows PowerShell para os usuários.

## <a name="introduction"></a>Introdução

Os tópicos de ajuda do PowerShell são parte integrante da experiência do PowerShell. Como os módulos do PowerShell, os tópicos de ajuda são continuamente atualizados e aprimorados pelos autores e pelas contribuições da comunidade de usuários do PowerShell.

O recurso de *ajuda atualizável* , introduzido no Windows PowerShell 3,0, garante que os usuários tenham as versões mais recentes dos tópicos da ajuda no prompt de comando, mesmo para comandos internos do PowerShell, sem baixar novos módulos ou executar Windows Update. A ajuda atualizável torna a atualização simples, fornecendo cmdlets que baixam as versões mais recentes dos tópicos de ajuda da Internet e as instalam nos subdiretórios corretos no computador local do usuário. Até mesmo os usuários que estão atrás de firewalls podem usar os novos cmdlets para obter ajuda atualizada de um compartilhamento de arquivos interno.

A ajuda atualizável tem suporte total de todos os módulos do Windows PowerShell no Windows 8 e no Windows Server 2012, e seus recursos estão disponíveis para todos os autores de módulo do Windows PowerShell. A ajuda atualizável dá suporte apenas a arquivos de ajuda baseados em XML. Ele não oferece suporte à ajuda baseada em comentários.

A ajuda atualizável inclui os seguintes recursos.

- O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) , que determina se os usuários têm os arquivos de ajuda mais recentes para um módulo e, caso contrário, baixa os arquivos de ajuda mais recentes da Internet, os descompactam e os instala nos subdiretórios de módulo corretos no computador do usuário. Os usuários podem usar o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) para exibir imediatamente os tópicos da ajuda recém-instalados. Eles não precisam reiniciar o PowerShell.

- O cmdlet [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) , que baixa os arquivos de ajuda mais recentes da Internet e os salva em um diretório do sistema de arquivos. Os usuários podem usar o `Update-Help` cmdlet para obter arquivos de ajuda do diretório do sistema de arquivos e descompactá-los e instalá-los nos subdiretórios do módulo no computador do usuário. O `Save-Help` cmdlet é projetado para usuários que têm acesso limitado ou sem Internet e para empresas que preferem limitar o acesso à Internet.

- **Ajuda para um módulo**. Os arquivos de ajuda para um módulo são gerenciados e entregues como uma unidade, para que os usuários possam obter todos os arquivos de ajuda para os módulos que usam. A ajuda atualizável tem suporte apenas para módulos, não para snap-ins do Windows PowerShell.

- **Suporte à versão**. A ajuda atualizável usa quatro posições padrão (N1. N2. N3. N4) números de versão.
  A ajuda atualizável baixa arquivos de ajuda quando o número de versão dos arquivos de ajuda no computador do usuário (ou no `Save-Help` diretório) é menor do que o número de versão dos arquivos de ajuda no local da Internet.

- **Suporte a vários idiomas**. A ajuda atualizável oferece suporte a arquivos de ajuda de módulo em várias culturas de interface do usuário.
  Os nomes de arquivo de ajuda atualizáveis incluem códigos de idioma padrão, como "en-US" e "ja-JP", e os `Update-Help` `Save-Help` cmdlets e colocam os arquivos de ajuda em subdiretórios específicos do idioma do diretório do módulo.

- **Ajuda gerada automaticamente**. O cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) exibe a ajuda básica para comandos que não têm arquivos de ajuda. A ajuda gerada automaticamente inclui a sintaxe e os aliases de comando e instruções para usar a ajuda online e a ajuda atualizável.

- **Ajuda online aprimorada**. O acesso fácil à ajuda online não requer mais arquivos de ajuda. O parâmetro **online** do `Get-Help` cmdlet agora Obtém a URL de um tópico da ajuda online do valor da propriedade **HelpUri** de qualquer comando, se não for possível encontrar a URL da ajuda online em um arquivo de ajuda. Você pode preencher a propriedade **HelpUri** adicionando um atributo **HelpUri** ao código de cmdlets, funções e comandos CIM, ou usando o **. Vincular** diretiva de ajuda baseada em comentário em fluxos de trabalho e scripts.

  Para tornar os arquivos de ajuda atualizáveis, os módulos do Windows PowerShell no Windows 8 e no Windows Server vNext não vêm com os arquivos de ajuda. Os usuários podem usar a ajuda atualizável para instalar os arquivos de ajuda e atualizá-los. Os autores de outros módulos podem incluir arquivos de ajuda em módulos ou omiti-los. O suporte para a ajuda atualizável é opcional, mas recomendado.
