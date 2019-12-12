---
title: Como adicionar sintaxe a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c6d03f-1c1a-43d8-928e-e3290e90e0bc
caps.latest.revision: 5
ms.openlocfilehash: 0210b5ed3104777541692a0e78e7d3b16f9c8256
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361205"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a>Como adicionar sintaxe a um tópico de ajuda do cmdlet

Antes de começar a codificar o XML para o diagrama de sintaxe no arquivo de ajuda do cmdlet, leia esta seção para obter uma visão clara do tipo de dados que você precisa fornecer, como os atributos de parâmetro e como esses dados são exibidos no diagrama de sintaxe.

### <a name="parameter-attributes"></a>Atributos de parâmetro

- Necessária

  - Se for true, o parâmetro deverá aparecer em todos os comandos que usam o conjunto de parâmetros.

  - Se for false, o parâmetro será opcional em todos os comandos que usam o conjunto de parâmetros.

- Posição

  - Se nomeado, o nome do parâmetro será obrigatório.

  - Se posicional, o nome do parâmetro será opcional. Quando é omitido, o valor do parâmetro deve estar na posição especificada no comando. Por exemplo, se o valor for position = "1", o valor do parâmetro deverá ser o primeiro ou apenas o valor do parâmetro não nomeado no comando.

- Entrada de pipeline

  - Se verdadeiro (ByValue), você pode canalizar a entrada para o parâmetro. A entrada é associada ao parâmetro ("Bound to"), mesmo se o nome da propriedade e o tipo de objeto não corresponderem ao tipo esperado. O Windows PowerShell? os componentes de associação de parâmetro tentam converter a entrada para o tipo correto e apresentar falha no comando somente quando o tipo não puder ser convertido. Somente um parâmetro em um conjunto de parâmetros pode ser associado por valor.

  - Se verdadeiro (ByPropertyName), você pode canalizar a entrada para o parâmetro. No entanto, a entrada é associada ao parâmetro somente quando o nome do parâmetro corresponde ao nome de uma propriedade do objeto de entrada. Por exemplo, se o nome do parâmetro for `Path`, os objetos canalizados para o cmdlet serão associados a esse parâmetro somente quando o objeto tiver uma propriedade chamada Path.

  - Se true (ByValue, ByPropertyName), você poderá canalizar a entrada para o parâmetro pelo nome da propriedade ou por valor. Somente um parâmetro em um conjunto de parâmetros pode ser associado por valor.

  - Se for false, não será possível canalizar a entrada para esse parâmetro.

- Global

  - Se for true, o texto que o usuário digitar para o valor do parâmetro poderá incluir caracteres curinga.

  - Se for false, o texto que o usuário digitar para o valor do parâmetro não poderá incluir caracteres curinga.

### <a name="parameter-value-attributes"></a>Atributos de valor do parâmetro

- Necessária

  - Se for true, o valor especificado deverá ser usado sempre que usar o parâmetro em um comando.

  - Se for false, o valor do parâmetro será opcional. Normalmente, um valor é opcional somente quando é um dos vários valores válidos para um parâmetro, como em um tipo enumerado.

O atributo necessário de um valor de parâmetro é diferente do atributo necessário de um parâmetro.

O atributo Required de um parâmetro indica se o parâmetro (e seu valor) deve ser incluído ao invocar o cmdlet. Por outro lado, o atributo Required de um valor de parâmetro é usado somente quando o parâmetro é incluído no comando. Indica se esse valor específico deve ser usado com o parâmetro.

Normalmente, os valores de parâmetro que são espaços reservados são necessários e os valores de parâmetros que são literais não são necessários, pois eles são um dos vários valores que podem ser usados com o parâmetro.

### <a name="gathering-syntax-information"></a>Coletando informações de sintaxe

1. Comece com o nome do cmdlet.

   ```
   SYNTAX
       Get-Tech
   ```

2. Liste todos os parâmetros do cmdlet. Digite um traço (também conhecido como "Dash" ou "sinal de subtração" (ASCII 45) antes de cada nome de parâmetro. Separe os parâmetros em conjuntos de parâmetros (alguns cmdlets podem ter apenas um conjunto de parâmetros). Neste exemplo, o cmdlet Get-Tech tem dois conjuntos de parâmetros.

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   Inicie cada conjunto de parâmetros com o nome do cmdlet.

   Liste o conjunto de parâmetros padrão primeiro. O parâmetro padrão é especificado pela classe cmdlet.

   Para cada conjunto de parâmetros, liste seu parâmetro exclusivo primeiro, a menos que haja parâmetros posicionais que devem aparecer primeiro. No exemplo anterior, os parâmetros Name e ID são parâmetros exclusivos para os dois conjuntos de parâmetros (cada conjunto de parâmetros deve ter um parâmetro que seja exclusivo para esse conjunto de parâmetros). Isso torna mais fácil para os usuários identificar qual parâmetro eles precisam fornecer para o conjunto de parâmetros.

   Liste os parâmetros na ordem em que eles devem aparecer no comando. Se o pedido não for importante, liste os parâmetros relacionados juntos ou liste os parâmetros usados com mais frequência primeiro.

   Certifique-se de listar os parâmetros WhatIf e Confirm se o cmdlet der suporte para ShouldProcess.

   Não liste os parâmetros comuns (como Verbose, Debug e ErrorAction) em seu diagrama de sintaxe. O cmdlet `Get-Help` adiciona essas informações para você quando ele exibe o tópico da ajuda.

3. Adicione os valores de parâmetro. No Windows PowerShell?, os valores de parâmetro são representados por seu tipo .NET. No entanto, o nome do tipo pode ser abreviado, como "String" para System. String.

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   Abreviar tipos contanto que seu significado esteja claro, como "String" para System. String e "int" para System. Int32.

   Liste todos os valores de enumerações, como o parâmetro-Type no exemplo anterior, que pode ser definido como "básico" ou "avançado".

   Parâmetros de switch, como-List no exemplo anterior, não têm valores.

4. Adicione colchetes angulares aos valores de parâmetros que são espaços reservados, em comparação com os valores de parâmetro que são literais.

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. Coloque os parâmetros opcionais e seus valores entre colchetes.

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. Coloque os nomes de parâmetros opcionais (para parâmetros posicionais) entre colchetes. O nome dos parâmetros que são posicionais, como o parâmetro Name no exemplo a seguir, não precisa ser incluído no comando.

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. Se um valor de parâmetro puder conter vários valores, como uma lista de nomes no parâmetro Name, adicione um par de colchetes diretamente após o valor do parâmetro.

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. Se o usuário puder escolher parâmetros ou valores de parâmetro, como o parâmetro de tipo, coloque as opções entre chaves e separe-as com o símbolo exclusivo ou (;).

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. Se o valor do parâmetro precisar usar formatação específica, como aspas ou parênteses, mostre o formato na sintaxe.

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a>Codificando o XML do diagrama de sintaxe

O nó de sintaxe do XML começa imediatamente após o nó de descrição, que termina com a marca \</maml: Description >. Para obter informações sobre como coletar os dados usados no diagrama de sintaxe, consulte [coletando informações de sintaxe](#gathering-syntax-information).

### <a name="adding-a-syntax-node"></a>Adicionando um nó de sintaxe

O diagrama de sintaxe exibido no tópico de ajuda do cmdlet é gerado a partir dos dados no nó sintaxe do XML. O nó de sintaxe será colocado em um par se \<comando: Syntax > Tags. Com cada conjunto de parâmetros do cmdlet incluído em um par de \<comando: syntaxitem > marcas. Não há nenhum limite para o número de \<comando: syntaxitem > marcas que você pode adicionar.

O exemplo a seguir mostra um nó de sintaxe que tem nós de item de sintaxe para dois conjuntos de parâmetros.

```xml
<command:syntax>
  <command:syntaxItem>
    ...
    <!--Parameter Set 1 (default parameter set) parameters go here-->
    ...
  </command:syntaxItem>
  <command:syntaxItem>
    ...
    <!--Parameter Set 2 parameters go here-->
    ...
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a>Adicionando o nome do cmdlet aos dados do conjunto de parâmetros

Cada conjunto de parâmetros do cmdlet é especificado em um nó de item de sintaxe. Cada nó de sintaxe do item começa com um par de \<maml: nome > marcas que incluem o nome do cmdlet.

O exemplo a seguir inclui um nó de sintaxe que tem nós de item de sintaxe para dois conjuntos de parâmetros.

```xml
<command:syntax>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-parameters"></a>Adicionando parâmetros

Cada parâmetro adicionado ao nó de item de sintaxe é especificado dentro de um par de \<comando: > marcas de parâmetro. Você precisa de um par de \<comando: parâmetros > marcas para cada parâmetro incluído no conjunto de parâmetros, com exceção dos parâmetros comuns fornecidos pelo Windows PowerShell?.

Os atributos do comando de abertura \<: > marca de parâmetro determinam como o parâmetro aparece no diagrama de sintaxe. Para obter informações sobre atributos de parâmetro, consulte [atributos de parâmetro](#parameter-attributes).

> [!NOTE]
> O comando \<: o parâmetro > marca dá suporte a um elemento filho \<maml: Description > cujo conteúdo nunca é exibido. As descrições de parâmetro são especificadas no nó de parâmetro do XML. Para evitar inconsistências entre as informações no item de sintaxe bodes e o nó de parâmetro, omita a descrição (\<maml: Description > ou deixe-a vazia.

O exemplo a seguir inclui um nó de item de sintaxe para um conjunto de parâmetros com dois parâmetros.

```xml
<command:syntaxItem>
  <maml:name>Cmdlet-Name</maml:name>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByValue)" position="1">
    <maml:name>ParameterName1</maml:name>
    <command:parameterValue required="true">
      string[]
    </command:parameterValue>
  </command:parameter>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByPropertyName)">
    <maml:name>ParameterName2</maml:name>
    <command:parameterValue required="true">
      int32[]
    </command:parameterValue>
  </command:parameter>
</command:syntaxItem>
```
