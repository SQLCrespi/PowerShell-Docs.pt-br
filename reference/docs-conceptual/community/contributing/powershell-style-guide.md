---
title: Guia de estilo do PowerShell no Docs
description: Este artigo fornece as regras de estilo para escrever a documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 964536c5195c3bb8abd98b5996a96fc7b9362489
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402573"
---
# <a name="powershell-docs-style-guide"></a>Guia de estilo do PowerShell no Docs

Este artigo fornece orientações de estilo específicas de conteúdo do PowerShell-Docs. Ele se baseia nas informações descritas na [Visão geral](overview.md#get-started-writing-docs).

## <a name="product-terminology"></a>Terminologia do produto

O PowerShell tem diversas variantes.
Esta tabela define alguns dos vários termos usados para definir o PowerShell.

- **PowerShell** – é o termo padrão. A partir de agora, consideraremos o PowerShell 7 e versões posteriores o verdadeiro PowerShell.

- **PowerShell Core** – PowerShell criado com base no .NET Core. O uso do termo **Core** deve se limitar aos casos em que é necessário haver diferenciação do Windows PowerShell.

- **Windows PowerShell** – PowerShell criado no .NET Framework. O Windows PowerShell é fornecido apenas no Windows e requer o Framework completo.

Em geral, as referências ao "Windows PowerShell" na documentação podem ser alteradas para "PowerShell".
O "Windows PowerShell" **não** deve ser alterado quando a tecnologia específica do Windows está sendo abordada.

## <a name="markdown-specifics"></a>Especificações de Markdown

O Microsoft OPS (Open Publishing SystemS), que cria nossa documentação, usa [markdig][] para processar os documentos em Markdown. O markdig analisa os documentos com base nas regras de especificação do [CommonMark][] mais recentes.

A nova especificação do CommonMark é muito mais rigorosa quanto à construção de alguns elementos de Markdown. Preste muita atenção aos detalhes fornecidos neste documento.

### <a name="blank-lines-spaces-and-tabs"></a>Linhas em branco, espaços e tabulações

Remova linhas em branco duplicadas. Se houver muitas linhas em branco, elas serão processadas como uma única linha em branco no HTML, portanto, não há finalidade para o uso de várias linhas em branco.

As linhas em branco também sinalizam o fim de um bloco em Markdown. Deve haver um espaço em branco único entre os blocos de Markdown de diferentes tipos (por exemplo, entre um parágrafo e uma lista ou cabeçalho).

> [!NOTE]
> O espaçamento é importante em Markdown. Use sempre espaços em vez de tabulação. Remova espaços extras no final das linhas.

### <a name="titles-and-headings"></a>Títulos e cabeçalhos

Use somente [cabeçalhos ATX][atx] (estilo #, em vez de cabeçalhos de estilo `=` ou `-` ).

- Uso de maiúsculas e minúsculas – apenas nomes próprios e a primeira letra de um título ou cabeçalho devem ser escritos em maiúsculas
- Deve haver um único espaço entre `#` e a primeira letra do cabeçalho
- Os títulos devem estar rodeados por uma única linha em branco
- Apenas um H1 por documento
- Os níveis do cabeçalho devem ser incrementados por um. Não pule os níveis
- Não use negrito ou outra marcação nos títulos

### <a name="limit-line-length-to-100-characters"></a>Limite o comprimento da linha a 100 caracteres

Isso se aplica a artigos conceituais e à referência de cmdlet. Os tópicos Sobre são limitados a 80 caracteres.
Limitar o comprimento da linha melhora a legibilidade de comparações e histórico do git. Também facilita a contribuição de outros escritores.

Use a extensão [Reflow Markdown][reflow] no Visual Studio Code para refluir parágrafos com facilidade e ajustar o comprimento da linha prescrita.

### <a name="lists"></a>Listas

Caso sua lista contenha várias frases ou parágrafos, considere usar um cabeçalho de subnível, em vez de uma lista.

A lista deve estar rodeada por uma única linha em branco.

#### <a name="unordered-lists"></a>Listas não ordenadas

Não encerre os itens da lista com um ponto, a menos que eles tenham várias sentenças. Use o caractere de hífen (`-`) para marcadores de itens de lista. Isso evita confusão com marcações em negrito ou itálico que usem o asterisco [`*`]. Para incluir um parágrafo ou outros elementos em um item de marcador, insira uma quebra de linha e alinhe o recuo com o primeiro caractere após o marcador.

Por exemplo:

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

Esta é uma lista que contém subelementos em um item de marcador.

- Primeiro item de marcador

  Frase explicando o primeiro marcador.

  - Item de sub-marcador

    Frase explicando o submarcador.

- Segundo item de marcador
- Terceiro item de marcador

#### <a name="ordered-lists"></a>Listas ordenadas

Para incluir um parágrafo ou outros elementos em um item numerado, alinhe o recuo com o primeiro caractere após o número do item. Todos os itens em uma lista numerada devem usar o número `1.` em vez de incrementar cada item. A renderização de Markdown incrementa o valor automaticamente. Isso facilita a reorganização dos itens e padroniza o recuo do conteúdo subordinado.

Por exemplo:

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

O Markdown resultante é renderizado da seguinte maneira:

1. No primeiro elemento, insira um único espaço após o 1. Frases longas devem ser quebradas na próxima linha e devem ser alinhadas com o primeiro caractere após o marcador de lista numerada.

   Para incluir um segundo elemento (como este), insira uma quebra de linha após a primeira e alinhe os recuos. O recuo do segundo elemento deve ser alinhado com o primeiro caractere após o marcador de lista numerada. Para itens com dígito único, como este, alinhe o recuo na coluna 4. Para itens com dois dígitos, por exemplo, item número 10, alinhe o recuo na coluna 5.

1. O próximo item numerado começa aqui.

### <a name="formatting-command-syntax-elements"></a>Formatação de elementos de sintaxe de comando

- Sempre use o nome completo, sem abreviações, para cmdlets e parâmetros. Evite usar aliases, a menos que você esteja demonstrando o alias especificamente.

- Em um parágrafo, palavras-chave de linguagem, nomes de cmdlet, variáveis e caminhos de arquivo devem ser colocados entre aspas invertidas (`` ` ``). Os nomes de propriedades, parâmetros e classes devem estar em **negrito**.

  Por exemplo:

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

- Ao se referir a um parâmetro por nome, o nome deve estar em **negrito**. Ao ilustrar o uso de um parâmetro com o prefixo de hífen, o parâmetro deve estar entre aspas invertidas. Por exemplo:

  ```markdown
  The parameter's name is **Name**, but it is typed as `-Name` when used on the command
  line as a parameter.
  ```

- Ao se referir a comandos externos (EXEs, scripts etc.), o nome do comando deve estar em negrito, em letras minúsculas (ou maiúsculas, se estiver no início de uma frase) e incluir a extensão de arquivo apropriada. Por exemplo:

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- Ao mostrar o exemplo de uso de um comando externo, o exemplo deve estar entre aspas invertidas.
  Quando houver uma colisão de nomes com um alias, você deve incluir a extensão do arquivo no exemplo de comando. Por exemplo:

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- Ao escrever um artigo conceitual (em vez de um conteúdo de referência), a primeira instância de um nome de cmdlet deve ser vinculada à documentação do cmdlet. Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.

  Por exemplo:

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  Para obter mais informações, confira a seção [Hiperlinks](#hyperlinks) deste artigo.

### <a name="images"></a>Imagens

A sintaxe que deve ser incluída em uma imagem é:

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

Em que `alt text` é uma breve descrição da imagem, e `<folder path>` é um caminho relativo para a imagem. O texto alternativo é obrigatório em leitores de tela para deficientes visuais. Ele também é útil em casos de bug no site que faça com que a imagem não seja renderizada.

As imagens devem ser armazenadas em uma pasta `media/<article-name>` dentro de outra pasta que contém o artigo.
As imagens não devem ser compartilhadas entre os artigos. Crie uma pasta que corresponda ao nome de arquivo do artigo na pasta `media`. Copie as imagens desse artigo para a nova pasta. Se uma imagem for usada por vários artigos, cada pasta de imagem deverá ter uma cópia desse arquivo de imagem. Essa prática evita que a alteração de uma imagem em um artigo afete outro.

Os seguintes tipos de arquivos de imagem são compatíveis: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`

### <a name="markdown-extensions-supported-by-open-publishing"></a>Extensões de Markdown para as quais o Open Publishing dá suporte

O [Pacote de Criação do Microsoft Docs](/contribute/how-to-write-docs-auth-pack) contém ferramentas que oferecem suporte a recursos exclusivos do nosso sistema de publicação. Os alertas são uma extensão do Markdown para criar citações em bloco que são renderizadas no docs.microsoft.com com cores e ícones que indicam o significado do conteúdo. Há suporte para os seguintes tipos de alerta:

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

Esses alertas ficam da seguinte forma no docs.microsoft.com:

> [!NOTE]
> Informações que o usuário deve conseguir notar mesmo que esteja correndo o texto.

> [!TIP]
> Informações opcionais para ajudar um usuário a ter mais sucesso.

> [!IMPORTANT]
> Informações essenciais necessárias para o sucesso do usuário.

> [!CAUTION]
> Possíveis consequências negativas de uma ação.

> [!WARNING]
> Consequências perigosas de uma ação.

## <a name="hyperlinks"></a>Hiperlinks

- Evite usar URLs simples. Os links devem usar a sintaxe do Markdown `[friendlyname](url-or-path)`
- URLs simples podem ser usadas quando necessário, mas devem estar entre aspas invertidas. Por exemplo:

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

- Os links de URL devem ser HTTPS quando possível.
- Os links devem ter um nome amigável, geralmente o título do tópico vinculado
- Todos os itens da seção "links relacionados" na parte inferior devem ser hiperlinks.
- Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.

### <a name="linking-to-other-content"></a>Vincular a outros conteúdos

Existem dois tipos de hiperlinks compatíveis com o sistema de publicação: Links de arquivos e URLs.

Um link de URL pode ser um caminho de URL que é relativo à raiz do docs.microsoft.com. Ou uma URL absoluta que inclua a sintaxe completa da URL. (Por exemplo, `https:/github.com/MicrosoftDocs/PowerShell-Docs`)

- Use links de URL ao vincular conteúdo fora do PowerShell-Docs ou entre a referência de cmdlet e artigos conceituais no PowerShell-Docs.
- A maneira mais simples de criar um link relativo é copiar a URL do seu navegador e remover `https://docs.microsoft.com/en-us` do valor colado no Markdown.
   - Não inclua localidades em URLs nas propriedades da Microsoft (por exemplo: remova "/en-us" da URL).
- Todas as URLs para sites externos devem usar HTTPS, a menos que isso não seja válido para o site de destino.

Um link de arquivo é usado para vincular um artigo de referência a outro ou um artigo conceitual a outro. Se você precisar criar um link para um artigo de referência de uma versão específica do PowerShell, use um link de URL.

- Os links de arquivo contêm um caminho de arquivo relativo (por exemplo: `../folder/file.md`)
- Todos os caminhos de arquivo usam caracteres de barra (`/`)

## <a name="formatting-code-samples"></a>Exemplos de código de formatação

O Markdown dá suporte a dois estilos de código diferentes:

- Extensão de código (embutido) – marcada por um único caractere de aspas invertidas (`` ` ``). Usado dentro de um parágrafo, e não como um bloco independente.
- Blocos de código – um bloco de várias linhas cercado por cadeias de caracteres com aspas triplas (`` ``` ``). Os blocos de código também podem ter um rótulo de linguagem após as aspas invertidas. O rótulo de linguagem habilita o destaque da sintaxe para o conteúdo do bloco de código.

### <a name="using-code-blocks"></a>Usar blocos de código

O Markdown permite que o recuo simbolize um bloco de código, mas esse padrão pode gerar problemas e deve ser evitado. Todos os blocos de código devem estar contidos em um limite de códigos. Um limite de código é um bloco de código cercado por cadeias de caracteres de aspas triplas (`` ``` ``). Os marcadores de limite de código devem estar em sua própria linha antes e depois do exemplo de código. O marcador no início do bloco de código pode ter um rótulo de linguagem opcional. O OPS (Open Publishing System) da Microsoft usa o rótulo de linguagem para oferecer suporte ao recurso de destaque da sintaxe.

O OPS também adiciona um botão **Copiar** que copia o conteúdo do bloco de código para a área de transferência. Isso permite colar rapidamente o código em um script para testar o exemplo de código. No entanto, nem todos os exemplos em nossa documentação devem ser executados. Alguns blocos de código são ilustrações simples de um conceito do PowerShell.

Existem dois tipos de blocos de código usados em nossa documentação:

1. Exemplos ilustrativos
2. Exemplos executáveis

### <a name="syntax-code-blocks"></a>Blocos de código de sintaxe

Este exemplo ilustra todos os parâmetros possíveis do cmdlet `Get-Command`.

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

Este exemplo descreve a instrução `for` em termos generalizados:

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a>Exemplos ilustrativos

Exemplos ilustrativos são usados para explicar um conceito do PowerShell. Eles não devem ser copiados para a área de transferência a fim de serem executados. Eles são mais comumente usados como exemplos simples e fáceis de digitar.
Também são usados como exemplos de sintaxe em que se está ilustrando a sintaxe de um comando. O bloco de código pode conter a saída de exemplo do comando que está sendo ilustrado.

Confira um exemplo simples que ilustra os operadores de comparação do PowerShell:

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

Observe que esse exemplo tem o prompt simplificado do PowerShell e mostra a saída resultante. Nesse caso, não pretendemos que o leitor copie nem execute esse exemplo.

### <a name="executable-examples"></a>Exemplos executáveis

Exemplos mais complexos ou que são destinados à cópia e execução devem usar a seguinte marcação no estilo de bloco:

~~~markdown
```powershell
<PowerShell code goes here>
```
~~~

A saída exibida pelos comandos do PowerShell deve ser colocadas entre blocos de código de **Saída**, para evitar o destaque da sintaxe. Por exemplo:

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

O rótulo do código de **Saída** não é uma "linguagem" oficial à qual o sistema de destaque de sintaxe dá suporte.
No entanto, esse rótulo é útil porque o OPS adiciona o rótulo de "Saída" ao quadro da caixa de código na página da Web. A caixa de código de "Saída" não possui destaque de sintaxe.

## <a name="coding-style-rules"></a>Regras de estilo de codificação

### <a name="avoid-line-continuation-in-code-samples"></a>Evitar a continuação de linha em exemplos de código

Evite usar caracteres de continuação de linha (`` ` ``) nos exemplos de código do PowerShell. Eles são difíceis de ver e podem causar problemas caso haja espaços extras no final da linha.

- Use os nivelamento do PowerShell para reduzir o comprimento da linha de cmdlets com muitos parâmetros.
- Aproveite as quebras naturais de linha do PowerShell, como caracteres após a barra vertical (`|`), chaves, parênteses e colchetes.

### <a name="avoid-using-powershell-prompts-in-examples"></a>Evitar o uso de prompts do PowerShell em exemplos

O uso da cadeia de caracteres de prompt é desencorajado e deve ser limitado a cenários que ilustram o uso da linha de comando. Para a maioria desses exemplos, a cadeia de caracteres de prompt deve ser `PS>`. Esse prompt é independente dos indicadores específicos do sistema operacional.

Os prompts são necessários para dar exemplos ilustrativos dos comandos que os alteram ou quando o caminho exibido é significativo para o cenário que está sendo ilustrado. O exemplo a seguir ilustra como o prompt é alterado ao usar o provedor de Registro.

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a>Não usar aliases em exemplos

Use sempre o nome completo de todos os cmdlets e parâmetros, a menos que esteja falando especificamente sobre o alias. Os nomes de cmdlets e parâmetros devem usar a ortografia adequada definida no código.

### <a name="using-parameters-in-examples"></a>Usar parâmetros em exemplos

Evite usar parâmetros posicionais. De maneira geral, sempre inclua o nome do parâmetro em um exemplo, mesmo que o parâmetro seja posicional. Isso reduz a chance de confusão nos seus exemplos.

## <a name="next-steps"></a>Próximas etapas

[Editar a referência de cmdlet](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
