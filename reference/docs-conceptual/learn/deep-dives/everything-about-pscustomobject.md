---
title: Tudo o que você queria saber sobre o PSCustomObject
description: O PSCustomObject é um jeito simples de criar dados estruturados.
ms.date: 07/29/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 52620fd628d03f62db574210a2a5758c3bf29135
ms.sourcegitcommit: a1886ba2cf35aebd650aafb3e5d7437c4e381781
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90804773"
---
# <a name="everything-you-wanted-to-know-about-pscustomobject"></a>Tudo o que você queria saber sobre o PSCustomObject

`PSCustomObject`s são uma excelente ferramenta para adicionar ao conjunto de ferramentas do PowerShell. Vamos começar com os conceitos básicos e progredir para os recursos mais avançados. A ideia por trás de usar um `PSCustomObject` é ter um jeito simples de criar dados estruturados. Dê uma olhada no primeiro exemplo e você entenderá melhor o que isso significa.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="creating-a-pscustomobject"></a>Como criar um PSCustomObject

Eu adoro usar `[PSCustomObject]` no PowerShell. Nunca foi tão fácil criar um objeto utilizável.
Por isso, vou ignorar todas as outras maneiras de criar um objeto, mas é preciso notar que a maioria desses exemplos são do PowerShell v3.0 ou mais recentes.

```powershell
$myObject = [PSCustomObject]@{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
```

Esse método funciona bem para mim porque uso tabelas de hash para praticamente tudo. Mas, às vezes, eu gostaria que o PowerShell tratasse as tabelas de hash mais como objetos. O primeiro lugar em que é possível perceber a diferença é quando queremos usar `Format-Table` ou `Export-CSV` e percebemos que uma tabela de hash é apenas uma coleção de pares chave/valor.

Então, é possível acessar e usar os valores como faria com um objeto normal.

```powershell
$myObject.Name
```

### <a name="converting-a-hashtable"></a>Como converter uma tabela de hash

Já que toquei no assunto, você sabia que é possível fazer isso:

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

Eu prefiro criar o objeto desde o início, mas às vezes é preciso trabalhar com uma tabela de hash primeiro. Esse exemplo funciona porque o construtor usa uma tabela de hash para as propriedades do objeto. É importante notar que, embora esse método funcione, ele não é um equivalente exato. A principal diferença é que a ordem das propriedades não é preservada.

### <a name="legacy-approach"></a>Abordagem herdada

Talvez você tenha visto pessoas usarem `New-Object` para criar objetos personalizados.

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}

$myObject = New-Object -TypeName PSObject -Property $myHashtable
```

É um jeito um pouco mais lento, mas talvez seja a melhor opção em versões anteriores do PowerShell.

### <a name="saving-to-a-file"></a>Como salvar em uma pasta

Na minha opinião, a melhor maneira de salvar uma tabela de hash em um arquivo é salvá-la como JSON. Assim, será possível importá-la de volta para um `[PSCustomObject]`

```powershell
$myObject | ConvertTo-Json -depth 1- | Set-Content -Path $Path
$myObject = Get-Content -Path $Path | ConvertFrom-Json
```

Eu abordei mais maneiras de salvar objetos em um arquivo em meu artigo sobre [As várias maneiras de ler e gravar em arquivos][].

## <a name="working-with-properties"></a>Como trabalhar com propriedades

### <a name="adding-properties"></a>Adicionando propriedades

Você ainda pode adicionar novas propriedades ao `PSCustomObject` com `Add-Member`.

```powershell
$myObject | Add-Member -MemberType NoteProperty -Name `ID` -Value 'KevinMarquette'

$myObject.ID
```

### <a name="remove-properties"></a>Como remover propriedades

Você também pode remover as propriedades de um objeto.

```powershell
$myObject.psobject.properties.remove('ID')
```

O `psobject` é uma propriedade oculta que fornece acesso aos metadados do objeto base.

### <a name="enumerating-property-names"></a>Como enumerar nomes de propriedade

Às vezes, precisamos de uma lista de todos os nomes de propriedade em um objeto.

```powershell
$myObject | Get-Member -MemberType NoteProperty | Select -ExpandProperty Name
```

Também podemos obter essa mesma lista por meio da propriedade `psobject`.

```powershell
$myobject.psobject.properties.name
```

### <a name="dynamically-accessing-properties"></a>Como acessar propriedades dinamicamente

Já comentei que podemos acessar diretamente os valores de propriedade.

```powershell
$myObject.Name
```

Podemos usar uma cadeia de caracteres para o nome da propriedade e ela funcionará mesmo assim.

```powershell
$myObject.'Name'
```

Podemos ir um pouco mais longe e usar uma variável para o nome da propriedade.

```powershell
$property = 'Name'
$myObject.$property
```

Eu sei que parece estranho, mas funciona.

### <a name="convert-pscustomobject-into-a-hashtable"></a>Converter PSCustomObject em uma tabela de hash

Para continuar de onde paramos na última seção, podemos percorrer dinamicamente as propriedades e criar uma tabela de hash delas.

```powershell
$hashtable = @{}
foreach( $property in $myobject.psobject.properties.name )
{
    $hashtable[$property] = $myObject.$property
}
```

### <a name="testing-for-properties"></a>Como testar as propriedades

Caso você precise saber se uma propriedade existe, basta verificar se essa propriedade tem um valor.

```powershell
if( $null -ne $myObject.ID )
```

Mas caso o valor possivelmente seja `$null` e você ainda precise verificá-lo, ainda é possível fazê-lo verificando nas `psobject.properties`.

```powershell
if( $myobject.psobject.properties.match('ID') )
```

## <a name="adding-object-methods"></a>Como adicionar métodos de objeto

Caso você precise adicionar um método de script a um objeto, é possível fazê-lo com um `Add-Member` e um `ScriptBlock`. Precisamos usar a referência automática de variável `this` no objeto atual. Aqui está um `scriptblock` para transformar um objeto em uma tabela de hash. (mesma forma de código do último exemplo)

```powershell
$ScriptBlock = {
    $hashtable = @{}
    foreach( $property in $this.psobject.properties.name )
    {
        $hashtable[$property] = $this.$property
    }
    return $hashtable
}
```

Em seguida, o adicionamos ao objeto como uma propriedade de script.

```powershell
$memberParam = @{
    MemberType = "ScriptMethod"
    InputObject = $myobject
    Name = "ToHashtable"
    Value = $scriptBlock
}
Add-Member @memberParam
```

Então, poderemos chamar nossa função assim:

```powershell
$myObject.ToHashtable()
```

### <a name="objects-vs-value-types"></a>Objetos vs. Tipos de valor

Objetos e tipos de valor não tratam das atribuições de variáveis do mesmo jeito. Se você atribuir tipos de valor uns aos outros, somente o valor será copiado para a nova variável.

```powershell
$first = 1
$second = $first
$second = 2
```

Nesse caso, `$first` é 1 e `$second` é 2.

As variáveis de objeto contêm referências ao objeto real. Quando atribuímos um objeto a uma nova variável, elas ainda fazem referência ao mesmo objeto.

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third
$fourth.Key = 4
```

Como `$third` e `$fourth` referenciam a mesma instância de um objeto, tanto `$third.key`, como `$fourth.Key` são 4.

### <a name="psobjectcopy"></a>psobject.copy()

Caso você precise de uma cópia verdadeira de um objeto, poderá cloná-lo.

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third.psobject.copy()
$fourth.Key = 4
```

Clonar cria uma cópia superficial do objeto. Eles têm instâncias diferentes agora e `$third.key` é 3 e `$fourth.Key` é 4, neste exemplo.

Eu chamo isso de cópia superficial porque, se você tiver objetos aninhados (em que as propriedades contêm outros objetos), somente os valores de nível superior serão copiados. Os objetos filho se referenciarão entre si.

### <a name="pstypename-for-custom-object-types"></a>PSTypeName para tipos de objeto personalizados

Agora que temos um objeto, podemos fazer coisas bem menos óbvias com ele. Antes de tudo, precisamos dar um `PSTypeName` a ele. Eu geralmente vejo isso ser feito dessa maneira:

```powershell
$myObject.PSObject.TypeNames.Insert(0,"My.Object")
```

Recentemente, descobri que outra maneira de fazer isso, ao ler essa [postagem de /u/markekraus][]. Continuei pesquisando e encontrei mais postagens sobre o assunto de [Adam Bertram][] e [Mike Shepard][], em que eles falam sobre essa abordagem que permite defini-lo como embutido.

```powershell
$myObject = [PSCustomObject]@{
    PSTypeName = 'My.Object'
    Name       = 'Kevin'
    Language   = 'PowerShell'
    State      = 'Texas'
}
```

Eu gosto muito dessa abordagem pela compatibilidade que ela tem com a linguagem. Agora que temos um objeto com um nome de tipo adequado, podemos fazer mais algumas coisas.

> [!NOTE]
> Você também pode criar tipos personalizados do PowerShell usando classes do PowerShell. Para obter mais informações, confira [Visão geral da classe do PowerShell](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes).

## <a name="using-defaultpropertyset-the-long-way"></a>Como usar DefaultPropertySet (a maneira mais longa)

O PowerShell decide para nós quais propriedades exibir por padrão. Muitos dos comandos nativos têm um [arquivo de formatação][] `.ps1xml` que faz todo o trabalho pesado. Nesta [postagem de Boe Prox][], há outra maneira de fazer isso em nosso objeto personalizado usando apenas o PowerShell. Podemos dá-lo um `MemberSet` para que use.

```powershell
$defaultDisplaySet = 'Name','Language'
$defaultDisplayPropertySet = New-Object System.Management.Automation.PSPropertySet(‘DefaultDisplayPropertySet’,[string[]]$defaultDisplaySet)
$PSStandardMembers = [System.Management.Automation.PSMemberInfo[]]@($defaultDisplayPropertySet)
$MyObject | Add-Member MemberSet PSStandardMembers $PSStandardMembers
```

Agora, quando o meu objeto simplesmente cair para o Shell, ele mostrará apenas essas propriedades por padrão.

### <a name="update-typedata-with-defaultpropertyset"></a>Update-TypeData com DefaultPropertySet

É uma abordagem legal, mas encontrei recentemente um jeito melhor ao assistir a [PowerShell Unplugged 2016 com Jeffrey Snover e Don Jones][psunplugged]. Jeffrey estava usando o [Update-TypeData][] para especificar as propriedades padrão.

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    DefaultDisplayPropertySet = 'Name','Language'
}
Update-TypeData @TypeData
```

Essa maneira é tão simples que eu teria me lembrado dela se eu não tivesse essa postagem como referência rápida. Agora, eu posso criar facilmente objetos com muitas propriedades e ainda dar a eles uma ótima exibição ao olhá-lo no Shell. Caso precise, posso acessar ou ver as outras propriedades, elas ainda estão lá.

```powershell
$myObject | Format-List *
```

### <a name="update-typedata-with-scriptproperty"></a>Update-TypeData com ScriptProperty

Outra coisa aprendi nesse vídeo foi criar propriedades de script para os objetos. Aproveito para destacar que isso funciona para objetos existentes também.

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    MemberType = 'ScriptProperty'
    MemberName = 'UpperCaseName'
    Value = {$this.Name.toUpper()}
}
Update-TypeData @TypeData
```

Podemos fazer isso antes ou depois que o objeto for criado e ainda funcionará. É nesse ponto que essa abordagem difere de usar `Add-Member` com uma propriedade de script. Quando usamos `Add-Member` do jeito que mencionei antes, ele só existe nessa instância específica do objeto. Já essa outra abordagem se aplica a todos os objetos com esse `TypeName`.

## <a name="function-parameters"></a>Parâmetros de função

Agora, podemos usar todos esses tipos personalizados para parâmetros em nossas funções e scripts. Podemos usar uma função para criar esses objetos personalizados e, então, passá-los para outras funções.

```powershell
param( [PSTypeName('My.Object')]$Data )
```

O PowerShell requer que o objeto seja do tipo especificado. Caso o tipo não corresponda automaticamente, ele gerará um erro de validação para evitar que você o teste em seu código. Um ótimo exemplo de como deixar que o PowerShell faça o que faz melhor.

### <a name="function-outputtype"></a>OutputType da Função

Também podemos definir um `OutputType` para as funções avançadas.

```powershell
function Get-MyObject
{
    [OutputType('My.Object')]
    [CmdletBinding()]
        param
        (
            ...
```

O valor do atributo **OutputType** é apenas uma observação de documentação. Ele não é derivado do código de função ou comparado à saída real da função.

O principal motivo para usar um tipo de saída é para que as informações meta da função reflitam suas intenções. Coisas como `Get-Command` e `Get-Help` que o seu ambiente de desenvolvimento pode aproveitar. Se deseja mais informações, dê uma olhada na ajuda sobre o assunto: [about_Functions_OutputTypeAttribute][].

Dito isso, caso esteja usando Pester para executar o teste de unidade nas funções, é melhor validar os objetos de saída que correspondam ao **OutputType**. Isso pode capturar variáveis que se enquadram no pipe quando não deveriam.

## <a name="closing-thoughts"></a>Considerações finais

Tratamos do contexto do `[PSCustomObject]`, mas muitas dessas informações se aplicam a objetos em geral.

Já vi a maioria desses recursos de maneira avulsa antes, mas nunca os vi apresentados em uma coleção de informações sobre `PSCustomObject`. Foi só nesta última semana que me deparei com outra e fiquei surpreso por não ter visto antes. Eu queria reunir todas essas ideias para que você pudesse ter acesso ao panorama geral e estivesse ciente delas quando a oportunidade de usá-las surgir. Espero que você tenha aprendido algo útil e possa encontrar um jeito de usar esse conhecimento em seus scripts.

<!-- link references -->
[versão original]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[postagem de Boe Prox]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[arquivo de formatação]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[about_Functions_OutputTypeAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute
[As várias maneiras de ler e gravar em arquivos]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[postagem de /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[Adam Bertram]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Mike Shepard]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[psunplugged]: https://www.youtube.com/watch?v=Ab46gHXNm8Q
[Update-TypeData]: /powershell/module/microsoft.powershell.utility/update-typedata
