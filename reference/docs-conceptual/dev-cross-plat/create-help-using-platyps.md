---
title: Criar ajuda baseada em XML usando o PlatyPS
description: O uso do PlatyPS é uma forma rápida e eficiente de criar a ajuda baseada em XML.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972566"
---
# <a name="create-xml-based-help-using-platyps"></a>Criar ajuda baseada em XML usando o PlatyPS

Quando você cria um módulo do PowerShell, é sempre recomendável que você inclua ajuda detalhada para os cmdlets criados. Se os cmdlets forem implementados no código compilado, você precisará usar a ajuda baseada em XML. Esse formato XML é conhecido como MAML (Microsoft Assistance Markup Language).

A documentação do SDK do PowerShell herdado aborda os detalhes da criação de ajuda para os cmdlets do PowerShell empacotados em módulos. No entanto, o PowerShell não fornece nenhuma ferramenta para criar a ajuda baseada em XML. A documentação do SDK explica a estrutura da ajuda do MAML, mas deixa a você a tarefa de criar o conteúdo MAML complexo, e profundamente aninhado, manualmente.

É aí que o módulo [PlatyPS][] pode ajudar.

## <a name="what-is-platyps"></a>O que é o PlatyPS?

O PlatyPS é uma ferramenta de [software livre][platyps-repo] que começou como um projeto _hackathon_ para facilitar a criação e a manutenção do MAML. O PlatyPS documenta a sintaxe de conjuntos de parâmetros e os parâmetros individuais para cada cmdlet em seu módulo. O PlatyPS cria arquivos [Markdown][] estruturados que contêm as informações de sintaxe. Ele não pode criar descrições nem fornecer exemplos.

O PlatyPS cria espaços reservados para que você preencha descrições e exemplos. Depois de adicionar as informações necessárias, o PlatyPS compila os arquivos Markdown em arquivos MAML. O sistema de ajuda do PowerShell também permite arquivos de ajuda conceituais de texto sem formatação (sobre tópicos). O PlatyPS tem um cmdlet para criar um modelo Markdown estruturado para um novo arquivo _sobre_ arquivo, mas esses arquivos `about_*.help.txt` precisam ser mantidos manualmente.

Você pode incluir os arquivos de ajuda MAML e de Texto com seu módulo. Você também pode usar o PlatyPS para compilar os arquivos de ajuda em um pacote CAB que pode ser hospedado para obter ajuda atualizável.

## <a name="get-started-using-platyps"></a>Introdução ao PlatyPS

Primeiro, você precisa instalar o PlatyPS do Galeria do PowerShell.

```powershell
Install-Module platyps -Force
Import-Module platyps
```

O fluxograma a seguir descreve o processo de criação ou atualização do conteúdo de referência do PowerShell.

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="O fluxo de trabalho para criar a ajuda baseada em XML usando o PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a>Criar conteúdo do Markdown para um módulo do PowerShell

1. Importe seu novo módulo na sessão. Repita essa etapa para cada módulo que você precisa documentar.

   Execute o seguinte comando para importar seus módulos:

   ```powershell
   Import-Module <your module name>
   ```

1. Use o PlatyPS para gerar arquivos Markdown para a página de módulo e todos os cmdlets associados dentro do módulo. Repita essa etapa para cada módulo que você precisa documentar.

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   Se a pasta de saída não existir, `New-MarkdownHelp` a criará. Neste exemplo, `New-MarkdownHelp` cria um arquivo Markdown para cada cmdlet no módulo. Ele também cria a _página de módulo_ em um arquivo chamado `<ModuleName>.md`. Esta página de módulo contém uma lista dos cmdlets contidos no módulo e espaços reservados para a descrição **Sinopse**. Os metadados na página de módulo são provenientes do manifesto do módulo e são usados pelo PlatyPS para criar o arquivo XML HelpInfo (conforme explicado [abaixo](#creating-an-updateable-help-package)).

   `New-MarkdownAboutHelp` cria um arquivo _sobre_ chamado `about_topic_name.md`.

   Para obter mais informações, confira [New-MarkdownHelp][] e [New-MarkdownAboutHelp][].

### <a name="update-existing-markdown-content-when-the-module-changes"></a>Atualizar o conteúdo do Markdown existente quando o módulo for alterado

O PlatyPS também pode atualizar arquivos Markdown existentes para um módulo. Use esta etapa para atualizar os módulos existentes que têm novos cmdlets, novos parâmetros ou parâmetros que foram alterados.

1. Importe seu novo módulo na sessão. Repita essa etapa para cada módulo que você precisa documentar.

   Execute o seguinte comando para importar seus módulos:

   ```powershell
   Import-Module <your module name>
   ```

1. Use o PlatyPS para gerar atualizar Markdown para a página de aterrissagem do módulo e todos os cmdlets associados dentro do módulo. Repita essa etapa para cada módulo que você precisa documentar.

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   `Update-MarkdownHelpModule` atualiza os arquivos Markdown do módulo e cmdlet na pasta especificada.
   Ele não atualiza os arquivos `about_*.md`. O arquivo de módulo (`ModuleName.md`) recebe qualquer texto **Sinopse** novo que foi adicionado aos arquivos cmdlet. As atualizações dos arquivos cmdlet incluem a seguinte alteração:

   - Novos conjuntos de parâmetro
   - Novos parâmetros
   - Metadados de parâmetro atualizados
   - Informações atualizadas de tipo de entrada e saída

   Para obter mais informações, confira [Update-MarkdownHelpModule][].

## <a name="edit-the-new-or-updated-markdown-files"></a>Editar os arquivos Markdown novos ou atualizados

O PlatyPS documenta a sintaxe dos conjuntos de parâmetros e os parâmetros individuais. Ele não pode criar descrições nem fornecer exemplos. As áreas específicas em que o conteúdo é necessário estão contidas entre chaves. Por exemplo: `{{ Fill in the Description }}`

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Modelo de Markdown mostrando os espaços reservados no VS Code":::

Você precisa adicionar uma sinopse, uma descrição do cmdlet, descrições para cada parâmetro e pelo menos um exemplo.

Para obter informações detalhadas sobre como escrever conteúdo do PowerShell, confira os seguintes artigos:

- [Guia de estilo do PowerShell](/powershell/scripting/community/contributing/powershell-style-guide)
- [Como editar artigos de referência](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> O PlatyPS tem um esquema específico usado para referência de cmdlet. Esse esquema permite apenas certos blocos do Markdown em seções específicas do documento. Se você colocar o conteúdo no local errado, a etapa de build do PlatyPS falhará. Para obter mais informações, confira a documentação de [esquema][] no repositório do PlatyPS. Para obter um exemplo completo de referência de cmdlet bem formado, confira [Get-Item][].

Depois de fornecer o conteúdo necessário para cada um dos seus cmdlets, você precisará atualizar a página de aterrissagem do módulo. Verifique se o módulo tem os valores `Module Guid` e `Download Help Link` corretos nos metadados YAML do arquivo `<module-name>.md`. Adicione metadados ausentes.

Além disso, você pode perceber que alguns cmdlets podem não ter uma **Sinopse** (_breve descrição_). O comando a seguir atualiza a página de aterrissagem do módulo com seu texto de descrição **Sinopse**. Abra a página de aterrissagem do módulo para verificar as descrições.

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

Agora que você inseriu todo o conteúdo, pode criar os arquivos de ajuda MAML exibidos pelo `Get-Help` no console do PowerShell.

## <a name="create-the-external-help-files"></a>Criar os arquivos de ajuda externos

Esta etapa cria os arquivos de ajuda MAML exibidos pelo `Get-Help` no console do PowerShell.

Para criar os arquivos MAML, execute o seguinte comando:

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

`New-ExternalHelp` converte todos os arquivos Markdown do cmdlet em um ou mais arquivos MAML. Arquivos sobre são convertidos em arquivos de texto sem formatação com o seguinte formato de nome: `about_topic_name.help.txt`.
O conteúdo Markdown deve atender ao requisito do esquema PlatyPS. `New-ExternalHelp` sairá com erros quando o conteúdo não seguir o esquema. Você precisa editar os arquivos para corrigir as violações de esquema.

> [!CAUTION]
> O PlatyPS faz um trabalho insatisfatório ao converter os arquivos `about_*.md` em texto sem formatação. Você precisa usar um Markdown muito simples para obter resultados aceitáveis. Talvez seja necessário manter os arquivos em formato `about_topic_name.help.txt` de texto sem formatação, em vez de permitir que PlatyPS os converta.

Após a conclusão dessa etapa, você verá os arquivos `*-help.xml` e `about_*.help.txt` na pasta de saída de destino.

Para obter mais informações, confira [New-ExternalHelp][]

### <a name="test-the-compiled-help-files"></a>Testar os arquivos de ajuda compilados

Você pode verificar o conteúdo com o cmdlet [Get-HelpPreview][]:

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

O cmdlet lê o arquivo MAML compilado e gera o conteúdo no mesmo formato que você receberia de `Get-Help`. Isso permite inspecionar os resultados para verificar se os arquivos Markdown foram compilados corretamente e produzem os resultados desejados. Se você encontrar um erro, edite novamente os arquivos Markdown e recompile o MAML.

Agora você está pronto para publicar seus arquivos de ajuda.

## <a name="publishing-your-help"></a>Como publicar sua ajuda

Agora que você compilou os arquivos Markdown nos arquivos de ajuda do PowerShell, você está pronto para disponibilizar os arquivos para os usuários. Há duas opções para fornecer ajuda no console do PowerShell.

- Empacotar os arquivos de ajuda com o módulo
- Criar um pacote de ajuda atualizável que os usuários instalam com o cmdlet `Update-Help`

### <a name="packaging-help-with-the-module"></a>Como empacotar a ajuda com o módulo

Os arquivos de ajuda podem ser empacotados com seu módulo. Confira [Como escrever ajuda para os módulos][] para obter detalhes da estrutura de pastas. Você deve incluir a lista de arquivos de ajuda no valor da chave de **FileList** no manifesto do módulo.

### <a name="creating-an-updateable-help-package"></a>Como criar um pacote de ajuda atualizável

Em um alto nível, as etapas para criar uma ajuda atualizável incluem:

1. Encontrar um site da Internet para hospedar seus arquivos de ajuda
1. Adicionar uma chave **HelpInfoURI** ao manifesto do módulo
1. Criar um arquivo XML HelpInfo
1. Criar arquivos CAB
1. Carregar seus arquivos

Para obter mais informações, confira [Como dar suporte à ajuda atualizável: passo a passo][step-by-step].

O PlatyPS ajuda você com algumas dessas etapas.

O **HelpInfoURI** é uma URL que aponta para o local em que os arquivos de ajuda estão hospedados na Internet. Esse valor é configurado no manifesto do módulo. `Update-Help` lê o manifesto do módulo para obter essa URL e baixar o conteúdo da ajuda atualizável. Essa URL só deve apontar para o local da pasta, e não para arquivos individuais. `Update-Help` constrói os nomes de arquivos a serem baixados com base em outras informações do manifesto do módulo e do arquivo XML HelpInfo.

> [!IMPORTANT]
> O **HelpInfoURI** precisa terminar com um caractere de barra (`/`). Sem esse caractere, `Update-Help` não pode construir os caminhos de arquivo corretos para baixar o conteúdo. Além disso, a maioria dos serviços de arquivo baseados em HTTP diferencia maiúsculas de minúsculas. É importante que os metadados do módulo no arquivo XML HelpInfo respeitem a diferença entre maiúsculas e minúsculas.

O cmdlet `New-ExternalHelp` cria o arquivo XML HelpInfo na pasta de saída. O arquivo XML HelpInfo é criado usando os metadados YAML contidos nos arquivos Markdown do módulo (`ModuleName.md`).

O cmdlet `New-ExternalHelpCab` cria arquivos ZIP e CAB contendo os arquivos MAML e `about_*.help.txt` que você compilou. Os arquivos CAB são compatíveis com todas as versões do PowerShell.
O PowerShell 6 e versões superiores podem usar arquivos ZIP.

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

Depois de criar os arquivos ZIP e CAB, carregue os arquivos XML HelpInfo, ZIP e CAB para o seu servidor de arquivos HTTP. Coloque os arquivos no local indicado pelo **HelpInfoURI**.

Para obter mais informações, confira [New-ExternalHelpCab][].

### <a name="other-publishing-options"></a>Outras opções de publicação

O Markdown é um formato versátil fácil de ser transformado em outros formatos para publicação. Usando uma ferramenta como [Pandoc][], você pode converter seus arquivos de ajuda Markdown em muitos formatos de documentos diferentes, incluindo formatos de documentos de texto sem formatação, HTML, PDF e Office.

Além disso, os cmdlets [ConvertFrom-Markdown][] e [Show-Markdown][] no PowerShell 6 e versões superiores podem ser usados para converter o Markdown em HTML ou criar uma exibição colorida no console do PowerShell.

## <a name="known-issues"></a>Problemas conhecidos

O PlatyPS é muito sensível ao [esquema][] para a estrutura dos arquivos Markdown que ele cria e compila. É muito fácil escrever um Markdown válido que viole esse esquema. Para obter mais informações, consulte o [guia de estilo do PowerShell][] e [Como editar artigos de referência][].

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Guia de estilo do PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[Como editar artigos de referência]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Como escrever ajuda para módulos]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
