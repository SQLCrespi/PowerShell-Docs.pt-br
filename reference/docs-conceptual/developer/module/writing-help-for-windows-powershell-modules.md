---
title: Gravando ajuda para módulos do PowerShell
ms.date: 04/10/2020
ms.openlocfilehash: 496b7e6cadff4d2db15b6452e9d38efcdf1739ec
ms.sourcegitcommit: 8f55c0157280afa4598fe385a706faf330e723a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81219652"
---
# <a name="writing-help-for-powershell-modules"></a>Gravando ajuda para módulos do PowerShell

Os módulos do PowerShell podem incluir tópicos de ajuda sobre o módulo e sobre os membros do módulo, como cmdlets, provedores, funções e scripts. O `Get-Help` cmdlet exibe os tópicos de ajuda do módulo no mesmo formato que exibe a ajuda para outros itens do PowerShell, e os `Get-Help` usuários usam comandos padrão para obter os tópicos da ajuda.

Este documento explica o formato e o posicionamento correto dos tópicos de ajuda do módulo e sugere diretrizes para o conteúdo da ajuda do módulo.

## <a name="types-of-module-help"></a>Tipos de ajuda do módulo

Um módulo pode incluir os seguintes tipos de ajuda.

- **Ajuda do cmdlet**. Os tópicos de ajuda que descrevem os cmdlets em um módulo são arquivos XML que usam o esquema de ajuda de comando

- **Ajuda do provedor**. Os tópicos de ajuda que descrevem provedores em um módulo são arquivos XML que usam o esquema de ajuda do provedor.

- **Ajuda da função**. Os tópicos de ajuda que descrevem as funções em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários dentro da função, ou o script ou o módulo de script

- **Ajuda do script**. Os tópicos de ajuda que descrevem scripts em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários no módulo script ou script.

- **Ajuda conceitual ("sobre")**. Você pode usar um tópico de ajuda conceitual ("sobre") para descrever o módulo e seus membros e explicar como os membros podem ser usados juntos para executar tarefas.
  Os tópicos de ajuda conceitual são arquivos de texto com codificação Unicode (UTF-8). O nome do arquivo deve usar `about_<name>.help.txt` o formato, como `about_MyModule.help.txt`. Por padrão, o PowerShell inclui mais de 100 desses conceitos conceituais sobre tópicos de ajuda e eles são formatados como o exemplo a seguir.

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
      Text-only references for further reading. Hyperlinks cannot work in the PowerShell console.

  ```

Todos os arquivos de esquema podem ser encontrados na `$PSHOME\Schemas\PSMaml` pasta.

## <a name="placement-of-module-help"></a>Posicionamento da ajuda do módulo

O `Get-Help` cmdlet procura arquivos de tópico da ajuda do módulo em subdiretórios específicos do idioma do diretório do módulo.

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
> No `<ModulePath>` exemplo, o espaço reservado representa um dos caminhos na variável de `PSModulePath` ambiente, como `$HOME\Documents\Modules`, `$PSHOME\Modules`ou um caminho personalizado que o usuário especifica.

## <a name="getting-module-help"></a>Obtendo ajuda do módulo

Quando um usuário importa um módulo para uma sessão, os tópicos de ajuda para esse módulo são importados para a sessão junto com o módulo. Você pode listar os arquivos de tópico da ajuda no valor da chave FileList no manifesto do módulo, mas os tópicos da `Export-ModuleMember` ajuda não são afetados pelo cmdlet.

Você pode fornecer tópicos de ajuda de módulo em diferentes idiomas. O `Get-Help` cmdlet exibe automaticamente tópicos de ajuda do módulo no idioma especificado para o usuário atual no item opções regionais e de idioma no painel de controle. No Windows Vista e versões posteriores do Windows `Get-Help` , o procura os tópicos da ajuda em subdiretórios específicos do idioma do diretório do módulo de acordo com os padrões de fallback de linguagem estabelecidos para o Windows.

A partir do PowerShell 3,0, a `Get-Help` execução de um comando para um cmdlet ou função dispara a importação automática do módulo. O `Get-Help` cmdlet exibe imediatamente o conteúdo dos tópicos da ajuda no módulo.

Se o módulo não contiver tópicos de ajuda e não houver tópicos de ajuda para os comandos no módulo no computador do usuário, `Get-Help` o exibirá a ajuda gerada automaticamente. A ajuda gerada automaticamente inclui a sintaxe do comando, os parâmetros e os tipos de entrada e saída, mas não inclui nenhuma descrição. A ajuda gerada automaticamente inclui texto que orienta o usuário a tentar usar o `Update-Help` cmdlet para baixar a ajuda do comando da Internet ou de um compartilhamento de arquivos. Ele também recomenda o uso do parâmetro **online** do `Get-Help` cmdlet para obter a versão online do tópico da ajuda.

## <a name="supporting-updatable-help"></a>Suporte à ajuda atualizável

Os usuários do PowerShell 3,0 e versões posteriores do PowerShell podem baixar e instalar arquivos de ajuda atualizados para um módulo da Internet ou de um compartilhamento de arquivos local. Os `Update-Help` cmdlets e `Save-Help` ocultam os detalhes de gerenciamento do usuário. Os usuários executam o `Update-Help` cmdlet e, `Get-Help` em seguida, usam o cmdlet para ler os arquivos de ajuda mais recentes do módulo no prompt de comando do PowerShell.
Os usuários não precisam reiniciar o Windows ou o PowerShell.

Os usuários atrás de firewalls e aqueles sem acesso à Internet também podem usar a ajuda atualizável.
Os administradores com acesso à Internet `Save-Help` usam o cmdlet para baixar e instalar os arquivos de ajuda mais recentes em um compartilhamento de arquivos. Em seguida, os usuários **Path** usam o parâmetro Path `Update-Help` do cmdlet para obter os arquivos de ajuda mais recentes do compartilhamento de arquivos.

Os autores de módulo podem incluir arquivos de ajuda no módulo e usar a ajuda atualizável para atualizar os arquivos de ajuda ou omitir os arquivos de ajuda do módulo e usar a ajuda atualizável para instalar e atualizá-los.

Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).

## <a name="supporting-online-help"></a>Suporte à ajuda online

Os usuários que não podem ou não instalar arquivos de ajuda atualizados em seus computadores geralmente dependem da versão online dos tópicos de ajuda do módulo. O parâmetro **online** do `Get-Help` cmdlet abre a versão online de um cmdlet ou tópico de ajuda de função avançada para o usuário em seu navegador de Internet padrão.

O `Get-Help` cmdlet usa o valor da propriedade **HelpUri** do cmdlet ou da função para localizar a versão online do tópico da ajuda.

A partir do PowerShell 3,0, você pode ajudar os usuários a localizar a versão online dos tópicos de ajuda do cmdlet e da função definindo o atributo HelpUri na classe cmdlet ou a propriedade **HelpUri** do atributo **CmdletBinding** . O valor do atributo é o valor da propriedade **HelpUri** do cmdlet ou da função.

Para obter mais informações, consulte [suporte à ajuda online](./supporting-online-help.md).

## <a name="see-also"></a>Consulte Também

[Escrevendo um módulo do PowerShell](./writing-a-windows-powershell-module.md)

[Suporte à ajuda atualizável](./supporting-updatable-help.md)

[Suporte à ajuda online](./supporting-online-help.md)
