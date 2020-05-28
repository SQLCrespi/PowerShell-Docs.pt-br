---
ms.date: 05/22/2020
keywords: powershell, cmdlet
title: O que é o PowerShell?
ms.openlocfilehash: 267b2938a0892c99c3a961bc7107f573df40a683
ms.sourcegitcommit: 38215ad49e237b219e62bb5a5f0eb3b6b048df1e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "83868472"
---
# <a name="what-is-powershell"></a>O que é o PowerShell?

O PowerShell é uma estrutura multiplataforma de gerenciamento de configuração e de automação de tarefas, que consiste em um shell de linha de comando e em uma linguagem de script. Ao contrário da maioria dos shells, que aceitam e retornam texto, o PowerShell é criado com base no CLR (Common Language Runtime) do .NET e aceita e retorna objetos .NET. Essa mudança fundamental traz ferramentas e métodos totalmente novos para a automação.

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a>A saída é baseada em objeto

Ao contrário de interfaces de linha de comando tradicionais, os cmdlets do PowerShell são projetados para lidar com objetos.
Um objeto representa informações estruturadas que vão além da uma cadeia de caracteres exibida na tela. A saída do comando sempre acompanha informações extras que poderão ser usadas quando necessário.

Se você já usou ferramentas de processamento de texto para processar dados, perceberá que elas se comportam de maneira diferente quando usadas no PowerShell. Na maioria dos casos, você não precisa de ferramentas de processamento de texto para extrair informações específicas. Você acessa diretamente partes dos dados usando a sintaxe de objeto padrão do PowerShell.

## <a name="the-command-family-is-extensible"></a>A família de comandos é extensível

Interfaces como a do `cmd.exe` não fornecem uma forma de estender diretamente o conjunto de comandos internos. Você pode criar ferramentas de linha de comando externas que são executadas no `cmd.exe`. Mas essas ferramentas externas não têm serviços, como a integração com a Ajuda. O `cmd.exe` não sabe automaticamente que essas ferramentas externas são comandos válidos.

Os comandos no PowerShell são conhecidos como _cmdlets_. Você pode usar cada cmdlet separadamente, mas o potencial deles é atingido quando você os combina para executar tarefas complexas. Como muitos shells, o PowerShell fornece acesso ao sistema de arquivos no computador. Os _provedores_ do PowerShell permitem que você acesse outros armazenamentos de dados, como o Registro e os repositórios de certificados, com tanta facilidade quanto o sistema de arquivos.

Você pode criar módulos de cmdlet e de função usando código compilado ou scripts. Os módulos podem adicionar cmdlets e provedores ao shell. O PowerShell também dá suporte a scripts que são análogos aos scripts de shell do UNIX e aos arquivos em lotes do `cmd.exe`.

## <a name="support-for-command-aliases"></a>Suporte para aliases de comando

O PowerShell dá suporte a aliases para se referir aos comandos por nomes alternativos. Usar alias permite que usuários com experiência em outros shells utilizem nomes de comando comuns que já conhecem para operações semelhantes no PowerShell.

O alias associa um novo nome a outro comando. Por exemplo, o PowerShell tem uma função interna denominada `Clear-Host` que limpa a janela de saída. Você pode digitar o alias `cls` ou `clear` em um prompt de comando. O PowerShell interpreta esses aliases e executa a função `Clear-Host`.

Esse recurso ajuda os usuários a aprender sobre o PowerShell. Primeiro, a maioria dos usuários do `cmd.exe` e do UNIX tem um grande repertório de comandos conhecidos por nome. Talvez os equivalentes do PowerShell não produzam resultados idênticos. No entanto, os resultados são bem parecidos, e os usuários podem fazer o trabalho sem conhecer o nome de comando do PowerShell. A "memória muscular" é outra grande fonte de frustração ao aprender um novo shell de comando. Caso você use o `cmd.exe` há anos, é possível que você digite inconscientemente o comando `cls` para limpar a tela. Sem o alias para `Clear-Host`, você receberá uma mensagem de erro e não saberá o que fazer para limpar a saída.

## <a name="powershell-handles-console-input-and-display"></a>O PowerShell manipula a exibição e a entrada do console

Quando você digita um comando, o PowerShell sempre processa a linha de comando de entrada diretamente. O PowerShell também formata a saída exibida na tela. Essa diferença é considerável porque reduz o trabalho necessário em cada cmdlet. Isso garante que você possa fazer as coisas sempre da mesma maneira com qualquer cmdlet. Os desenvolvedores de cmdlet não precisam escrever códigos para analisar os argumentos de linha de comando ou formatar a saída.

Ferramentas de linha de comando tradicionais têm seus próprios esquemas para solicitar e exibir a Ajuda. Algumas ferramentas de linha de comando usam `/?` para disparar a exibição da Ajuda; outras usam `-?`, `/H` ou até mesmo `//`. Algumas delas exibem a Ajuda em uma janela GUI em vez de na exibição do console. Se você usar o parâmetro errado, a ferramenta poderá ignorar o que você digitou e começar a executar uma tarefa automaticamente.
Como o PowerShell analisa e processa a linha de comando automaticamente, o parâmetro `-?` sempre significa "mostre-me a Ajuda para este comando".

> [!NOTE]
> Se você executar um aplicativo gráfico no PowerShell, a janela do aplicativo se abrirá.
> O PowerShell intervém apenas no processamento da entrada da linha de comando que você fornece ou quando a saída do aplicativo retorna para a janela do console. Ele não afeta a maneira como o aplicativo funciona internamente.

## <a name="powershell-has-a-pipeline"></a>O PowerShell tem um pipeline

Pipelines são possivelmente o conceito mais valioso usado nas interfaces de linha de comando. Quando usados adequadamente, os pipelines facilitam o uso de comandos complexos e a visualização do fluxo de trabalho. Cada comando em um pipeline passa sua saída, item por item, para o próximo comando. Os comandos não precisam lidar com mais de um item por vez. O resultado são o consumo reduzido de recursos e a capacidade de obter uma saída imediatamente.

A notação usada para pipelines é semelhante à notação usada em outros shells. À primeira vista, talvez seja aparente como os pipelines são diferentes no PowerShell. Embora você veja o texto na tela, o PowerShell redireciona objetos, e não o texto, entre comandos.

Por exemplo, se você usar o cmdlet `Out-Host` para forçar uma exibição de página a página da saída de outro comando, a saída parecerá ser apenas o texto normal exibido na tela, dividida em páginas:

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

A paginação também reduz a utilização da CPU, pois o processamento muda para o cmdlet `Out-Host` quando há uma página completa pronta para exibição. Os cmdlets que a precedem no pipeline pausam a execução até que a próxima página de saída esteja disponível.

### <a name="objects-in-the-pipeline"></a>Objetos no pipeline

Quando você executa um cmdlet no PowerShell, vê a saída de texto porque é necessário representar objetos como texto em uma janela de console. A saída de texto não pode exibir todas as propriedades do objeto mostrado.

Por exemplo, considere o cmdlet `Get-Location`. A saída de texto é um resumo das informações, não uma representação completa do objeto retornado por `Get-Location`. O título na saída é adicionado pelo processo que formata os dados para exibição na tela.

```powershell
Get-Location
```

```Output
Path
----
C:\
```

O redirecionamento da saída para o cmdlet `Get-Member` exibe informações sobre o objeto retornado por `Get-Location`.

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

`Get-Location` retorna um objeto **PathInfo** que contém o caminho atual e outras informações.

## <a name="built-in-help-system"></a>Sistema de ajuda interno

Semelhante às páginas `man` do UNIX, o PowerShell inclui artigos de ajuda detalhados que explicam os conceitos e a sintaxe de comando do PowerShell. Use o cmdlet [Get-Help][] para exibir esses artigos no prompt de comando ou confira as versões mais atualizadas deles na documentação online do PowerShell.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre o PowerShell, confira a seção **Aprendendo a usar o PowerShell** deste site.

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
