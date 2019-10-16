---
title: Gravando ajuda para módulos do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360555"
---
# <a name="writing-help-for-windows-powershell-modules"></a>Escrever ajuda para módulos do Windows PowerShell

Os módulos do Windows PowerShell podem incluir tópicos de ajuda sobre o módulo e sobre os membros do módulo, como cmdlets, provedores, funções e scripts. O cmdlet `Get-Help` exibe os tópicos de ajuda do módulo no mesmo formato que exibe a ajuda para outros itens do Windows PowerShell, e os usuários usam comandos padrão do `Get-Help` para obter os tópicos da ajuda.

Este documento explica o formato e o posicionamento correto dos tópicos de ajuda do módulo e sugere diretrizes para o conteúdo da ajuda do módulo.

## <a name="types-of-module-help"></a>Tipos de ajuda do módulo

Um módulo pode incluir os seguintes tipos de ajuda.

- **Ajuda do cmdlet**. Os tópicos de ajuda que descrevem os cmdlets em um módulo são arquivos XML que usam o esquema de ajuda de comando

- **Ajuda do provedor**. Os tópicos de ajuda que descrevem provedores em um módulo são arquivos XML que usam o esquema de ajuda do provedor.

- **Ajuda da função**. Os tópicos de ajuda que descrevem as funções em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários dentro da função, ou o script ou o módulo de script

- **Ajuda do script**. Os tópicos de ajuda que descrevem scripts em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários no módulo script ou script.

- **Ajuda conceitual ("sobre")** . Você pode usar um tópico de ajuda conceitual ("sobre") para descrever o módulo e seus membros e explicar como os membros podem ser usados juntos para executar tarefas. Os tópicos de ajuda conceitual são arquivos de texto com codificação Unicode (UTF-8). O nome do arquivo deve usar o formato `about_<name>.help.txt`, como about_MyModule. help. txt. Por padrão, o Windows PowerShell inclui mais de 100 desses conceitos conceituais sobre tópicos de ajuda e eles são formatados como o exemplo a seguir.

  ```
  TOPIC
      about_<subject or module name>

  SHORT DESCRIPTION
      A short, one-line description of the topic contents.

  LONG DESCRIPTION
      A detailed, full description of the subject or purpose of the module.

  EXAMPLES
      Examples of how to use the module or how the subject feature works in practice.

  KEYWORDS
      Terms or titles on which you might expect your users to search for the information in this topic.

  SEE ALSO
      Text-only references for further reading. Hyperlinks cannot work in the Windows PowerShell console.

  ```

## <a name="placement-of-module-help"></a>Posicionamento da ajuda do módulo

O cmdlet `Get-Help` procura arquivos de tópico da ajuda do módulo em subdiretórios específicos do idioma do diretório do módulo.

Por exemplo, o diagrama de estrutura de diretório a seguir mostra o local dos tópicos de ajuda para o módulo SampleModule.

```
<ModulePath>
         \SampleModule
               \<en-US>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml
               \<fr-FR>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml

```

> [!NOTE]
> No exemplo, o espaço reservado *\<ModulePath >* representa um dos caminhos na variável de ambiente `PSModulePath`, como $Home \documents\modules, $pshome \modules ou um caminho personalizado que o usuário especifica.

## <a name="getting-module-help"></a>Obtendo ajuda do módulo

Quando um usuário importa um módulo para uma sessão, os tópicos de ajuda para esse módulo são importados para a sessão junto com o módulo. Você pode listar os arquivos de tópico da ajuda no valor da chave FileList no manifesto do módulo, mas os tópicos da ajuda não são afetados pelo cmdlet `Export-ModuleMember`.

Você pode fornecer tópicos de ajuda de módulo em diferentes idiomas. O cmdlet `Get-Help` exibe automaticamente tópicos de ajuda do módulo no idioma especificado para o usuário atual no item opções regionais e de idioma no painel de controle. No Windows Vista e versões posteriores do Windows, `Get-Help` pesquisa os tópicos da ajuda em subdiretórios específicos do idioma do diretório do módulo de acordo com os padrões de fallback de idioma estabelecidos para o Windows.

A partir do Windows PowerShell 3,0, a execução de um comando `Get-Help` para um cmdlet ou função dispara a importação automática do módulo. O cmdlet `Get-Help` exibe imediatamente o conteúdo dos tópicos da ajuda no módulo.

Se o módulo não contiver tópicos de ajuda e não houver tópicos de ajuda para os comandos no módulo no computador do usuário, `Get-Help` exibirá a ajuda gerada automaticamente. A ajuda gerada automaticamente inclui a sintaxe do comando, os parâmetros e os tipos de entrada e saída, mas não inclui nenhuma descrição. A ajuda gerada automaticamente inclui texto que orienta o usuário a tentar usar o cmdlet `Update-Help` para baixar a ajuda do comando da Internet ou de um compartilhamento de arquivos. Ele também recomenda o uso do parâmetro **online** do cmdlet `Get-Help` para obter a versão online do tópico da ajuda.

## <a name="supporting-updatable-help"></a>Suporte à ajuda atualizável

Os usuários do Windows PowerShell 3,0 e versões posteriores do Windows PowerShell podem baixar e instalar arquivos de ajuda atualizados para um módulo da Internet ou de um compartilhamento de arquivos local. Os cmdlets `Update-Help` e `Save-Help` ocultam os detalhes de gerenciamento do usuário. Os usuários executam o cmdlet `Update-Help` e, em seguida, usam o cmdlet `Get-Help` para ler os arquivos de ajuda mais recentes do módulo no prompt de comando do Windows PowerShell. Os usuários não precisam reiniciar o Windows ou o Windows PowerShell.

Os usuários atrás de firewalls e aqueles sem acesso à Internet também podem usar a ajuda atualizável. Os administradores com acesso à Internet usam o cmdlet `Save-Help` para baixar e instalar os arquivos de ajuda mais recentes em um compartilhamento de arquivos. Em seguida, os usuários usam o parâmetro **path** do cmdlet `Update-Help` para obter os arquivos de ajuda mais recentes do compartilhamento de arquivos.

Os autores de módulo podem incluir arquivos de ajuda no módulo e usar a ajuda atualizável para atualizar os arquivos de ajuda ou omitir os arquivos de ajuda do módulo e usar a ajuda atualizável para instalar e atualizá-los.

Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).

## <a name="supporting-online-help"></a>Suporte à ajuda online

Os usuários que não podem ou não instalar arquivos de ajuda atualizados em seus computadores geralmente dependem da versão online dos tópicos de ajuda do módulo. O parâmetro **online** do cmdlet `Get-Help` abre a versão online de um cmdlet ou tópico de ajuda de função avançada para o usuário em seu navegador de Internet padrão.

O cmdlet `Get-Help` usa o valor da propriedade **HelpUri** do cmdlet ou da função para localizar a versão online do tópico da ajuda.

A partir do Windows PowerShell 3,0, você pode ajudar os usuários a localizar a versão online dos tópicos de ajuda do cmdlet e da função definindo o atributo HelpUri na classe cmdlet ou a propriedade **HelpUri** do atributo **CmdletBinding** . O valor do atributo é o valor da propriedade **HelpUri** do cmdlet ou da função.

Para obter mais informações, consulte [suporte à ajuda online](./supporting-online-help.md).

## <a name="see-also"></a>Consulte Também

[Escrevendo um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)

[Suporte à ajuda atualizável](./supporting-updatable-help.md)

[Suporte à ajuda online](./supporting-online-help.md)