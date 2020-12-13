---
ms.date: 07/09/2020
ms.topic: reference
title: Visão geral do sistema de tipo estendido
description: Visão geral do sistema de tipo estendido
ms.openlocfilehash: f4a789f779fa8a52f0fe524abff7ec3311e93b6c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655724"
---
# <a name="extended-type-system-overview"></a>Visão geral do sistema de tipo estendido

O PowerShell usa seu objeto **PSObject** para estender os tipos de objetos de duas maneiras. Primeiro, o objeto **PSObject** fornece uma maneira de mostrar diferentes modos de exibição de tipos de objetos específicos. Isso é conhecido como mostrar uma exibição adaptada de um objeto. Em segundo lugar, o objeto **PSObject** fornece uma maneira de adicionar membros a um objeto existente. Juntos, ao encapsular um objeto existente, chamado de objeto base, o objeto **PSObject** fornece um sistema de tipo estendido (ETS) que os desenvolvedores de script e cmdlet podem usar para manipular objetos .net no Shell.

## <a name="cmdlet-and-script-development-issues"></a>Problemas de desenvolvimento de cmdlets e scripts

O ETS resolve dois problemas fundamentais:

Primeiro, alguns objetos .NET não têm o comportamento padrão necessário para atuar como os dados entre os cmdlets.

- Alguns objetos .NET são objetos "meta" (por exemplo: objetos WMI, objetos ADO e objetos XML) cujos membros descrevem os dados que eles contêm. No entanto, em um ambiente de script, eles são os dados contidos que são mais interessantes, não a descrição dos dados contidos. O ETS resolve esse problema introduzindo a noção de adaptadores que adaptam o objeto .NET subjacente para ter a semântica padrão esperada.
- Alguns membros de objeto .NET são nomeados inconsistentes, fornecem um conjunto insuficiente de membros públicos ou fornecem funcionalidade insuficiente. O ETS resolve esse problema introduzindo a capacidade de estender o objeto .NET com membros adicionais.

Em segundo lugar, a linguagem de script do PowerShell é sem _tipo_ , pois uma variável não precisa ser declarada de um tipo específico. Ou seja, as variáveis que um desenvolvedor de scripts cria são por natureza não _tipada_. No entanto, o sistema do PowerShell é "controlado por tipo", pois depende de ter um nome de tipo para operar para operações básicas, como resultados de saída ou classificação.

Portanto, um desenvolvedor de scripts deve ter a capacidade de declarar o tipo de uma de suas variáveis e criar seu próprio conjunto de "objetos" digitados dinamicamente que contenham Propriedades e métodos e possam participar do sistema orientado por tipos. O ETS resolve esse problema fornecendo um objeto comum para a linguagem de script que tem a capacidade de declarar seu tipo dinamicamente e adicionar membros dinamicamente.

Fundamentalmente, o ETS resolve o problema mencionado anteriormente fornecendo o objeto **PSObject** , que atua como a base de todo o acesso a objetos da linguagem de script e fornece uma abstração padrão para o desenvolvedor de cmdlets.

### <a name="cmdlet-developers"></a>Desenvolvedores de cmdlets

Para os desenvolvedores de cmdlets, o ETS fornece o seguinte suporte:

- As abstrações para trabalhar com objetos de uma maneira genérica usando o objeto **PSObject** . O ETS também fornece a capacidade de detalhar essas abstrações, se necessário.
- Os mecanismos para criar um comportamento padrão para formatação, classificação, serialização e outras manipulações do sistema de seu tipo de objeto usando um conjunto conhecido de membros estendidos.
- O meio para operar em qualquer objeto usando a mesma semântica que a linguagem de script usando um objeto LanguagePrimitives.
- O meio de "digitar" dinamicamente uma tabela de hash para que o restante do sistema possa operar com eficiência.

### <a name="script-developers"></a>Desenvolvedores de scripts

Para os desenvolvedores de scripts, o ETS fornece o seguinte suporte:

- A capacidade de fazer referência a qualquer tipo de objeto subjacente usando a mesma sintaxe ( `$a.x` ).
- A capacidade de acessar além da abstração fornecida pelo objeto **PSObject** (como acessar somente membros adaptados ou acessar o próprio objeto base).
- A capacidade de definir membros bem conhecidos que controlam a formatação, a classificação, a serialização e outras manipulações de uma instância ou tipo de objeto.
- O meio para nomear um objeto como um tipo específico e, portanto, controlar a herança de seus membros baseados em tipo.
- A capacidade de adicionar, remover e modificar membros estendidos.
- A capacidade de manipular o objeto **PSObject** em si, se necessário.

## <a name="the-psobject-class"></a>A classe PSObject

O objeto **PSObject** é a base de todos os acessos a objetos da linguagem de script e fornece uma abstração padrão para o desenvolvedor de cmdlets. Ele contém um objeto base (um objeto .NET) e qualquer membro de instância (Membros, especificamente Membros estendidos, que estão presentes em uma determinada instância de objeto, enquanto não necessariamente em outros objetos do mesmo tipo). Dependendo do tipo do objeto base, o objeto **PSObject** também pode fornecer acesso implícito e explícito aos membros adaptados, bem como a qualquer membro estendido baseado em tipo.

O objeto **PSObject** fornece os seguintes mecanismos:

- A capacidade de construir um **PSObject** com ou sem um objeto base.
- A capacidade de acessar todos os membros de cada objeto **PSObject** construído por meio de um algoritmo de pesquisa comum e a capacidade de substituir esse algoritmo quando necessário.
- A capacidade de obter e definir os nomes de tipo dos objetos **PSObject** construídos para que os scripts e cmdlets possam referenciar objetos **PSObject** semelhantes pelo mesmo nome-tipo, independentemente do tipo de seu objeto base.

### <a name="how-to-construct-a-psobject"></a>Como construir um PSObject

A lista a seguir descreve maneiras de criar um objeto **PSObject** :

- Chamar o construtor **PSObject** . #ctor cria um novo objeto **PSObject** com um objeto base de PSCustomObject. Um objeto base desse tipo indica que o objeto **PSObject** não tem nenhum objeto base significativo. No entanto, um objeto **PSObject** com esse tipo de objeto base fornece um recipiente de propriedades que os desenvolvedores de cmdlets podem encontrar úteis adicionando Membros estendidos.

Os desenvolvedores também podem especificar o tipo de objeto-nome, que permite que esse objeto Compartilhe seus membros estendidos com outros objetos **PSObject** do mesmo nome de tipo.

- Chamar o construtor **PSObject** . #ctor (System. Object) cria um novo objeto **PSObject** com um objeto base do tipo System. Object.

  Nesse caso, o tipo-nome para o objeto criado é uma coleção da hierarquia de derivação do objeto base. Por exemplo, o nome do tipo para o **PSObject** que contém um objeto base ProcessInfo incluiria os seguintes nomes:

  - System.Diagnostics.Process
  - System. ComponentModel. componente
  - System.MarshalByRefObject
  - System.Object

- Chamando o **PSObject** . O método AsPSObject (System. Object) cria um novo objeto **PSObject** com base em um objeto fornecido.

  Se o objeto fornecido for do tipo System. Object, o objeto fornecido será usado como o objeto base para o novo objeto **PSObject** . Se o objeto fornecido já for um objeto **PSObject** , o objeto fornecido será retornado como está.

### <a name="base-adapted-and-extended-members"></a>Membros base, adaptados e estendidos

Conceitualmente, o ETS usa os seguintes termos para mostrar a relação entre os membros originais do objeto base e os membros adicionados pelo PowerShell. Para obter mais informações sobre os tipos específicos de membros que são usados pelo objeto **PSObject** , consulte [classe PSObject](/dotnet/api/system.management.automation.psobject).

#### <a name="base-object-members"></a>Membros de objeto base

Se o objeto base for especificado durante a construção dos objetos **PSObject** , os membros do objeto base serão disponibilizados por meio da propriedade Members.

#### <a name="adapted-members"></a>Membros adaptados

Quando um objeto base é um metaobjeto, um que contém dados de um modo genérico cujas propriedades "descrevem" seus dados contidos, o ETS adapta esses objetos a uma exibição que permite o acesso direto aos dados por meio de membros adaptados do objeto **PSObject** . Membros adaptados e membros de objeto base são acessados por meio da propriedade Members.

#### <a name="extended-members"></a>Membros estendidos

Além dos membros disponibilizados do objeto base ou dos membros adaptados criados pelo PowerShell, um **PSObject** também pode definir membros estendidos que estendem o objeto base original com informações adicionais que são úteis no ambiente de script.

Por exemplo, todos os cmdlets principais fornecidos pelo PowerShell, como os cmdlets Get-Content e Set-Content, usam um parâmetro Path. Para garantir que esses cmdlets e outros possam trabalhar com objetos de tipos diferentes, um membro de caminho pode ser adicionado a esses objetos para que todos declarem suas informações de forma comum. Esse membro de caminho estendido garante que os cmdlets possam trabalhar com todos esses tipos, mesmo que não haja um membro de caminho para a classe base.

Membros estendidos, membros adaptados e membros de objeto base são todos acessados por meio da propriedade Members.
