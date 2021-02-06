---
title: Guia de estilo do PowerShell no Docs
description: Este artigo fornece as regras de estilo para escrever a documentação do PowerShell.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "99603321"
---
# <a name="powershell-docs-style-guide"></a>Guia de estilo do PowerShell no Docs

Este artigo fornece orientações de estilo específicas de conteúdo do PowerShell-Docs. Ele se baseia nas informações descritas na [visão geral](overview.md#get-started-writing-docs).

## <a name="product-terminology"></a>Terminologia do produto

O PowerShell tem diversas variantes.

- **PowerShell** – é o termo padrão. Consideramos o PowerShell 7 e superior para ser o verdadeiro PowerShell.
- **PowerShell Core** – PowerShell criado com base no .NET Core. O uso do termo **principal** deve ser limitado a casos em que é necessário diferenciá-los do Windows PowerShell.
- **Windows PowerShell** – PowerShell criado no .NET Framework. O Windows PowerShell é fornecido apenas no Windows e requer o Framework completo.

  Em geral, as referências a "Windows PowerShell" na documentação podem ser alteradas para o _PowerShell_.
  "Windows PowerShell" deve ser usado quando o comportamento específico do _Windows PowerShell_ está sendo discutido.

Produtos relacionados

- **Visual Studio Code (vs Code)** -este é o editor de código aberto gratuito da Microsoft. Na primeira menção, o nome completo deve ser usado. Depois disso, você poderá usar o **VS Code**. Não use "VSCode".
- **Extensão do PowerShell para Visual Studio Code** – a extensão transforma VS Code no IDE preferencial para o PowerShell. Na primeira menção, o nome completo deve ser usado. Depois disso, você poderá usar a **extensão do PowerShell**.
- **Azure PowerShell** – é a coleção de módulos do PowerShell usada para gerenciar os serviços do Azure.
- **Azure Stack** do PowerShell – é a coleção de módulos do PowerShell usada para gerenciar a solução de nuvem híbrida da Microsoft.

## <a name="markdown-specifics"></a>Especificações de Markdown

O Microsoft OPS (Open Publishing SystemS), que cria nossa documentação, usa [markdig][] para processar os documentos em Markdown. O markdig analisa os documentos com base nas regras de especificação do [CommonMark][] mais recentes.

A nova especificação do CommonMark é muito mais rigorosa quanto à construção de alguns elementos de Markdown. Preste muita atenção aos detalhes fornecidos neste documento.

### <a name="blank-lines-spaces-and-tabs"></a>Linhas em branco, espaços e tabulações

As linhas em branco também sinalizam o fim de um bloco em Markdown. Deve haver um espaço em branco único entre os blocos de Markdown de diferentes tipos (por exemplo, entre um parágrafo e uma lista ou cabeçalho).

Várias linhas em branco consecutivas são renderizadas como uma única linha em branco em HTML. Eles não atendem a nenhuma finalidade.
Dentro de um bloco de código, linhas em branco consecutivas quebram o bloco de código.

Remova espaços extras no final das linhas.

> [!NOTE]
> O espaçamento é importante em Markdown. Use sempre espaços em vez de tabulação. Os espaços à direita podem mudar a maneira como o Markdown é renderizado.

### <a name="titles-and-headings"></a>Títulos e cabeçalhos

Use somente [cabeçalhos ATX][atx] (estilo #, em vez de cabeçalhos de estilo `=` ou `-` ).

- Uso de maiúsculas e minúsculas – apenas nomes próprios e a primeira letra de um título ou cabeçalho devem ser escritos em maiúsculas
- Deve haver um único espaço entre `#` e a primeira letra do cabeçalho
- Os títulos devem estar rodeados por uma única linha em branco
- Apenas um H1 por documento
- Os níveis do cabeçalho devem ser incrementados por um. Não ignorar níveis
- Não usar negrito ou outra marcação nos cabeçalhos

### <a name="limit-line-length-to-100-characters"></a>Limite o comprimento da linha a 100 caracteres

Isso se aplica a artigos conceituais e à referência de cmdlet. Limitar o comprimento da linha melhora a legibilidade de comparações e histórico de git. Também facilita a contribuição de outros escritores.

Use a extensão [Reflow Markdown][reflow] no Visual Studio Code para refluir parágrafos com facilidade e ajustar o comprimento da linha prescrita.

Os tópicos Sobre são limitados a 80 caracteres. Para obter informações mais específicas, consulte [formatando About_ arquivos](#formatting-about_-files).

### <a name="lists"></a>Listas

Se sua lista contiver várias frases ou parágrafos, considere usar um cabeçalho de subnível em vez de uma lista.

A lista deve estar rodeada por uma única linha em branco.

#### <a name="unordered-lists"></a>Listas não ordenadas

Não Finalize os itens de lista com um período, a menos que eles contenham várias frases. Use o caractere de hífen (`-`) para marcadores de itens de lista. Isso evita confusão com marcações em negrito ou itálico que usem o asterisco [`*`]. Para incluir um parágrafo ou outros elementos em um item de marcador, insira uma quebra de linha e alinhe o recuo com o primeiro caractere após o marcador.

Por exemplo:

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

Esta é uma lista que contém elementos filho em um item de marcador.

- Primeiro item de marcador

  Frase explicando o primeiro marcador.

  - Item de marcador filho

    Frase explicando o marcador filho.

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

### <a name="images"></a>Imagens

A sintaxe que deve ser incluída em uma imagem é:

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

Em que `alt text` é uma breve descrição da imagem, e `<folder path>` é um caminho relativo para a imagem. O texto alternativo é obrigatório em leitores de tela para deficientes visuais.

As imagens devem ser armazenadas em uma `media/<article-name>` pasta dentro da pasta que contém o artigo.
Não compartilhe imagens entre artigos. Crie uma pasta que corresponda ao nome de arquivo do artigo na pasta `media`. Copie as imagens desse artigo para essa nova pasta. Se uma imagem for usada por vários artigos, cada pasta de imagem precisará ter uma cópia desse arquivo de imagem. Essa prática impede uma alteração em uma imagem de um artigo que afete outro artigo.

Há suporte para os seguintes tipos de arquivo de imagem:,,, `*.png` `*.gif` `*.jpeg` `*.jpg` , `*.svg`

### <a name="markdown-extensions-supported-by-open-publishing"></a>Extensões de Markdown com suporte por Open Publishing

O [pacote de criação do Microsoft docs](/contribute/how-to-write-docs-auth-pack) contém ferramentas que dão suporte a recursos exclusivos do nosso sistema de publicação. Alertas são uma extensão de redução para criar Blockquotes que são renderizadas em docs.microsoft.com com cores e ícones que realçam o significado do conteúdo. Os seguintes tipos de alerta tem suporte:

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

Esses alertas terão a seguinte aparência no docs.microsoft.com:

Bloco de observação

> [!NOTE]
> Information the user should notice even if skimming.

Bloco Tip

> [!TIP]
> Optional information to help a user be more successful.

Bloco importante

> [!IMPORTANT]
> Essential information required for user success.

Bloqueio de cuidado

> [!CAUTION]
> Negative potential consequences of an action.

Bloco de aviso

> [!WARNING]
> Determinadas consequências perigosas de uma ação.

### <a name="hyperlinks"></a>Hiperlinks

- Os hiperlinks devem usar a sintaxe de redução `[friendlyname](url-or-path)` . Há suporte para [referências de link][linkref] .
- O sistema de publicação dá suporte a três tipos de links:
  - Links de URL
  - Links de arquivo
  - Links de referência cruzada
- Links para outros artigos em docs.microsoft.com devem ser caminhos relativos a sites
- Todas as URLs para sites externos devem usar HTTPS, a menos que não seja válido para o site de destino.
- Os links devem ter um nome amigável, geralmente o título do artigo vinculado
- Todos os itens na seção _links relacionados_ na parte inferior devem ser hiperlinks
- Não use marcas de escala, negrito ou outra marcação dentro dos colchetes de um hiperlink.
- URLs Bare podem ser usadas quando você está documentando um URI específico. O URI deve ser colocado entre tiques. Por exemplo:

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a>Vinculando a outro conteúdo no docs.microsoft.com

- **Links de URL** para outros artigos em docs.Microsoft.com devem ser caminhos relativos a sites. A maneira mais simples de criar um link relativo é copiar a URL do navegador e, em seguida, remover `https://docs.microsoft.com/en-us` do valor que você colar em redução. Não inclua localidades em URLs nas propriedades da Microsoft (remover `/en-us` da URL). Remova os parâmetros de consulta desnecessários da URL. Exemplos que devem ser removidos:

  - `?view=powershell-5.1` -usado para vincular a uma versão específica do PowerShell
  - `?redirectedfrom=MSDN` -adicionado à URL quando você é Redirecionado de um artigo antigo para seu novo local

  Se você precisar vincular a uma versão específica de um documento, precisará adicionar o `&preserve_view=true` parâmetro à cadeia de caracteres de consulta. Por exemplo: `?view=powershell-5.1&preserve_view=true`

- Um **link de arquivo** é usado para vincular de um artigo de referência a outro, ou de um artigo conceitual para outro. Se você precisar vincular a um artigo de referência para uma versão específica do PowerShell, deverá usar um link de URL.

  - Os links de arquivo contêm um caminho de arquivo relativo (por exemplo: `../folder/file.md` )
  - Todos os caminhos de arquivo usam caracteres de barra ( `/` )

- **Links de referência cruzada** são um recurso especial suportado pelo sistema de publicação. Você pode usar links de referência cruzada em artigos conceituais para vincular a API .NET ou referência de cmdlet.

  Para obter links para a referência da API do .NET, consulte [usar links na documentação](/contribute/how-to-write-links#xref-cross-reference-links) no guia do colaborador central.

  Links para referência de cmdlet têm o seguinte formato: `xref:<module-name>.<cmdlet-name>` . Por exemplo, para vincular o `Get-Content` cmdlet no módulo **Microsoft. PowerShell. Management** .

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

A vinculação profunda é permitida em links de URL e de arquivo. Adicione a âncora ao final do caminho de destino.
Por exemplo:

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

Para obter mais informações, consulte [usar links na documentação](/contribute/how-to-write-links).

## <a name="formatting-command-syntax-elements"></a>Como formatar elementos da sintaxe de comando

- Sempre use o nome completo para cmdlets e parâmetros. Evite usar aliases, a menos que você esteja demonstrando especificamente o alias.

- Propriedade, parâmetro, objeto, nomes de tipo, nomes de classe, métodos de classe devem estar em **negrito**.
  - Os valores de propriedade e parâmetro devem ser encapsulados em acentos ( `` ` `` ).
  - Ao fazer referência a tipos usando o estilo entre colchetes, use marcas de escala. Por exemplo: `[System.Io.FileInfo]`

- Palavras-chave de idioma, nomes de cmdlet, funções, variáveis, EXEs nativos, caminhos de arquivo e exemplos de sintaxe embutida devem ser encapsulados em caracteres de acento grave ( `` ` `` ).

  Por exemplo:

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - Ao referenciar um parâmetro pelo nome, o nome deve estar em **negrito**. Ao ilustrar o uso de um parâmetro com o prefixo de hífen, o parâmetro deve ser encapsulado em acentos graves. Por exemplo:

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - Ao mostrar o uso de exemplo de um comando externo, o exemplo deve ser encapsulado em acentos graves.
    Inclua sempre a extensão de arquivo no comando nativo. Por exemplo:

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    A inclusão da extensão de arquivo garante que o comando correto seja executado de acordo com a precedência de comando do PowerShell.

- Ao redigir um artigo conceitual (em comparação com um conteúdo de referência), a primeira instância de um nome de cmdlet deve ser vinculada à documentação do cmdlet. Não use marcas de escala, negrito ou outra marcação dentro dos colchetes de um hiperlink.

  Por exemplo:

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  Para obter mais informações, consulte a seção [hiperlinks](#hyperlinks) deste artigo.

## <a name="markdown-for-code-samples"></a>Redução para exemplos de código

O Markdown dá suporte a dois estilos de código diferentes:

- **Trechos de código (embutidos)** – marcados por um único caractere de acento grave ( `` ` `` ). Usado em um parágrafo em vez de como um bloco autônomo.
- **Blocos de código** : um bloco de várias linhas circundado por cadeias de caracteres de backtick ( `` ``` `` ). Os blocos de código também podem ter um rótulo de idioma após as marcas de fim. O rótulo de idioma habilita o realce de sintaxe para o conteúdo do bloco de código.

Todos os blocos de código devem estar contidos em um limite de código. Nunca use recuo para blocos de código. A redução permite esse padrão, mas pode ser problemática e deve ser evitada.

Um bloco de código é uma ou mais linhas de código circundadas por um limite de código de tiques ( `` ``` `` ) triplo.
Os marcadores do limite de código precisam estar em sua própria linha antes e depois do exemplo de código. O marcador no início do bloco de código pode ter um rótulo de linguagem opcional. O OPS (Open Publishing System) da Microsoft usa o rótulo de linguagem para dar suporte ao recurso de realce de sintaxe.

Para obter uma lista completa de marcas de idioma com suporte, consulte [blocos de código em grade](/contribute/code-in-docs#fenced-code-blocks) no guia do colaborador centralizado.

O OPS também adiciona um botão **Copiar** que copia o conteúdo do bloco de código para a área de transferência. Isso permite que você cole rapidamente o código em um script para testar o exemplo de código. No entanto, nem todos os exemplos em nossa documentação devem ser executados no estado em que se encontram. Alguns blocos de código são ilustrações simples de um conceito do PowerShell.

Há três tipos de blocos de código usados em nossa documentação:

1. Blocos de sintaxe
1. Exemplos ilustrativos
1. Exemplos executáveis

### <a name="syntax-code-blocks"></a>Blocos de código de sintaxe

Os blocos de código de sintaxe são usados para descrever a estrutura sintática de um comando. Não use uma marca de idioma no limite de código. Este exemplo ilustra todos os parâmetros possíveis do cmdlet `Get-Command`.

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
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

Os exemplos ilustrativos são usados para explicar um conceito do PowerShell. Eles não devem ser copiados para a área de transferência para execução. Esses são mais comumente usados para exemplos simples que são fáceis de digitar e fáceis de entender. O bloco de código pode incluir o prompt do PowerShell e o exemplo de saída.

Veja um exemplo simples que ilustra os operadores de comparação do PowerShell. Nesse caso, não pretendemos que o leitor copie e execute este exemplo.

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a>Exemplos executáveis

Exemplos complexos, ou exemplos que devem ser copiados e executados, devem usar a seguinte marcação de estilo de bloco:

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

A saída exibida pelos comandos do PowerShell deve ser colocada em um bloco de código **Saída** para evitar o realce de sintaxe. Por exemplo:

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

O rótulo do código de **saída** não é um "idioma" oficial com suporte no sistema de realce de sintaxe.
No entanto, esse rótulo é útil porque o OPS adiciona o rótulo "saída" ao quadro da caixa de código na página da Web. A caixa de código "saída" não tem realce de sintaxe.

## <a name="coding-style-rules"></a>Regras de estilo de codificação

### <a name="avoid-line-continuation-in-code-samples"></a>Evite a continuação de linha em exemplos de código

Evite usar caracteres de continuação de linha (`` ` ``) em exemplos de código do PowerShell. Eles são difíceis de serem vistos e podem causar problemas se há espaços extras no final da linha.

- Use o nivelamento do PowerShell para reduzir o tamanho da linha para cmdlets que têm vários parâmetros.
- Aproveite as oportunidades de quebra de linha natural do PowerShell, como após os caracteres de pipe ( `|` ), chaves de abertura ( `{` ), parênteses ( `(` ) e colchetes ( `[` ).

### <a name="avoid-using-powershell-prompts-in-examples"></a>Evite usar avisos do PowerShell em exemplos

O uso da cadeia de caracteres de prompt é desencorajado e deve ser limitado a cenários que se destinam a ilustrar o uso da linha de comando. Para a maioria desses exemplos, a cadeia de caracteres do prompt deve ser `PS>` . Esse aviso é independente dos indicadores específicos do sistema operacional.

Os prompts são necessários em exemplos para ilustrar comandos que alteram o prompt ou quando o caminho exibido é significativo para o cenário. O exemplo a seguir ilustra como o aviso é alterado ao usar o provedor do Registro.

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

### <a name="dont-use-aliases-in-examples"></a>Não use aliases em exemplos

Use o nome completo de todos os cmdlets e parâmetros, a menos que você esteja documentando especificamente o alias.
Os nomes de cmdlet e parâmetro devem usar os nomes de [Pascal-case][] apropriados.

### <a name="using-parameters-in-examples"></a>Como usar parâmetros em exemplos

Evite usar parâmetros posicionais. Em geral, você deve sempre incluir o nome do parâmetro em um exemplo, mesmo que o parâmetro seja posicional. Isso reduz a chance de confusão em seus exemplos.

## <a name="formatting-cmdlet-reference-articles"></a>Artigos de referência de cmdlets de formatação

Os artigos de referência de cmdlet têm uma estrutura específica. Essa estrutura é definida pelo [PlatyPS][].
PlatyPS gera a ajuda do cmdlet para módulos do PowerShell em redução. Depois de editar os arquivos markdown, o PlatyPS é usado para criar os arquivos de ajuda do MAML usados pelo cmdlet `Get-Help`.

O PlatyPS tem um esquema embutido em código para a referência de cmdlet que é gravado no código. O documento [platyPS.schema.md][] tenta descrever essa estrutura. As violações de esquema causam erros de build que precisam ser corrigidos antes que possamos aceitar sua contribuição.

- Não remova nenhuma das estruturas de cabeçalho ATX. O PlatyPS espera um conjunto específico de cabeçalhos.
- Os cabeçalhos **Tipo de entrada** e **Tipo de saída** precisam ter um tipo. Se o cmdlet não usar entrada ou retornar um valor, use o valor `None` .
- As extensões de código embutidas podem ser usadas em qualquer parágrafo.
- Blocos de código isolados são permitidos somente na seção de **exemplos** .

No esquema PlatyPS, **exemplos** é um cabeçalho H2. Cada exemplo é um cabeçalho H3. Em um exemplo, o esquema não permite que os blocos de código sejam separados por parágrafos. O esquema permite a seguinte estrutura:

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

Numerar cada exemplo e adicionar um breve título.

Por exemplo:

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a>Como formatar arquivos About_

`About_*` os arquivos são escritos em redução, mas são enviados como arquivos de texto sem formatação. Usamos [Pandoc][] para converter a redução em texto sem formatação. `About_*` os arquivos são formatados para obter a melhor compatibilidade em todas as versões do PowerShell e com as ferramentas de publicação.

Diretrizes básicas de formatação:

- Limitar as linhas normais a 80 caracteres
- Os blocos de código são limitados a 76 caracteres
- Os Blockquotes (e alertas) têm 78 caracteres limitados
- Ao usar esses metacaracteres especiais `\` , `$` e `<` :
  - Dentro de um cabeçalho, esses caracteres devem ser ignorados usando um caractere à esquerda `\` ou colocados em spans de código usando acentos ( `` ` `` )
  - Dentro de um parágrafo, esses caracteres devem ser colocados em spans de código. Por exemplo:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- As tabelas precisam se ajustar em 76 caracteres
  - Quebre manualmente o conteúdo das células em várias linhas
  - Use caracteres `|` de abertura e fechamento em cada linha
  - O exemplo a seguir ilustra como construir corretamente uma tabela que contém informações que são encapsuladas em várias linhas dentro de uma célula.

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > A limitação de 76 colunas aplica-se somente a `About_*` Tópicos. Você pode usar colunas largas em artigos conceituais ou de referência de cmdlet.

## <a name="next-steps"></a>Próximas etapas

[Lista de verificação editorial](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[Pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
