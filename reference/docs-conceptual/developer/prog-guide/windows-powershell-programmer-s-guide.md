---
title: Guia do programador do Windows PowerShell&#39;s | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- Windows PowerShell Programmer's Guide
ms.openlocfilehash: 64feb66b8e42ab12b279025ebe6c86d7f91ecae5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771559"
---
# <a name="windows-powershell-programmer39s-guide"></a>Guia do programador do Windows PowerShell&#39;s

Este guia do programador destina-se a desenvolvedores interessados em fornecer um ambiente de gerenciamento de linha de comando para administradores do sistema. O Windows PowerShell fornece uma maneira simples de criar comandos de gerenciamento que expõem objetos .NET, permitindo ao mesmo tempo que o Windows PowerShell faça a maior parte do trabalho para você.

No desenvolvimento tradicional de comandos, você precisa escrever um analisador de parâmetro, um associador de parâmetro, filtros e todas as outras funcionalidades expostas por cada comando. O Windows PowerShell fornece o seguinte para facilitar a gravação de comandos:

- Um tempo de execução do Windows PowerShell poderoso (mecanismo de execução) com seu próprio analisador e um mecanismo para vinculação automática de parâmetros de comando.

- Utilitários para formatar e exibir os resultados de comando usando um interpretador de linha de comando (CLI).

- Suporte para altos níveis de funcionalidade (por meio de provedores do Windows PowerShell) que facilitam o acesso a dados armazenados.

  A um custo pequeno, você pode representar um objeto .NET por um comando avançado ou conjunto de comandos que oferecerá uma experiência completa de linha de comando ao administrador.

  A próxima seção aborda os principais conceitos e termos do Windows PowerShell. Familiarize-se com esses conceitos e termos antes de iniciar o desenvolvimento.

## <a name="about-windows-powershell"></a>Sobre o Windows PowerShell

O Windows PowerShell define vários tipos de comandos que você pode usar no desenvolvimento. Esses comandos incluem: funções, filtros, scripts, aliases e executáveis (aplicativos). O tipo de comando principal discutido neste guia é um comando simples e pequeno chamado de "cmdlet". O Windows PowerShell fornece um conjunto de cmdlets e dá suporte total à personalização de cmdlets para se adequar ao seu ambiente. O tempo de execução do Windows PowerShell processa todos os tipos de comando da mesma forma que os cmdlets, usando pipelines.

Além dos comandos, o Windows PowerShell dá suporte a vários provedores personalizáveis do Windows PowerShell que disponibilizam conjuntos específicos de cmdlets disponíveis. O Shell opera dentro do aplicativo host fornecido pelo Windows PowerShell (Windows PowerShell.exe), mas ele é igualmente acessível a partir de um aplicativo host personalizado que você pode desenvolver para atender a requisitos específicos. Para obter mais informações, consulte [como funciona o Windows PowerShell](/previous-versions//ms714658(v=vs.85)).

### <a name="windows-powershell-cmdlets"></a>Cmdlets do Windows PowerShell

Um cmdlet é um comando leve que é usado no ambiente do Windows PowerShell. O tempo de execução do Windows PowerShell invoca esses cmdlets dentro do contexto de scripts de automação que são fornecidos na linha de comando, e o tempo de execução do Windows PowerShell também os chama de forma programática por meio de APIs do Windows PowerShell.

Para obter mais informações sobre cmdlets, consulte [escrevendo um cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).

### <a name="windows-powershell-providers"></a>Provedores do Windows PowerShell

Ao executar tarefas administrativas, o usuário pode precisar examinar os dados armazenados em um armazenamento de dados (por exemplo, o sistema de arquivos, o registro do Windows ou um repositório de certificados). Para facilitar essas operações, o Windows PowerShell define um módulo chamado provedor do Windows PowerShell que pode ser usado para acessar um armazenamento de dados específico, como o registro do Windows. Cada provedor dá suporte a um conjunto de cmdlets relacionados para dar ao usuário uma exibição simétrica dos dados na loja.

O Windows PowerShell fornece vários provedores padrão do Windows PowerShell. Por exemplo, o provedor de registro dá suporte à navegação e manipulação do registro do Windows. As chaves do registro são representadas como itens e os valores do registro são tratados como propriedades.

Se você expor um armazenamento de dados que o usuário precisará acessar, talvez seja necessário escrever seu próprio provedor do Windows PowerShell, conforme descrito em [criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md). Para obter mais informações sobre provedores do PowerShell aboutWindows, consulte [como funciona o Windows PowerShell](/previous-versions//ms714658(v=vs.85)).

### <a name="host-application"></a>Aplicativo Host

O Windows PowerShell inclui o aplicativo host padrão powershell.exe, que é um aplicativo de console que interage com o usuário e hospeda o tempo de execução do Windows PowerShell usando uma janela de console.

Apenas raramente você precisará escrever seu próprio aplicativo host para o Windows PowerShell, embora haja suporte para a personalização. Um caso em que você pode precisar de seu próprio aplicativo é quando você tem um requisito para uma interface de GUI que é mais rica do que a interface fornecida pelo aplicativo host padrão. Você também pode querer um aplicativo personalizado quando estiver baseando sua GUI na linha de comando. Para obter mais informações, consulte [como criar um aplicativo host do Windows PowerShell](/powershell/scripting/developer/hosting/writing-a-windows-powershell-host-application).

### <a name="windows-powershell-runtime"></a>Tempo de execução do Windows PowerShell

O tempo de execução do Windows PowerShell é o mecanismo de execução que implementa o processamento de comandos. Ele inclui as classes que fornecem a interface entre o aplicativo host e os comandos e provedores do Windows PowerShell. O tempo de execução do Windows PowerShell é implementado como um objeto de runspace para a sessão atual do Windows PowerShell, que é o ambiente operacional no qual o Shell e os comandos são executados. Para obter detalhes operacionais, consulte [como funciona o Windows PowerShell](/previous-versions//ms714658(v=vs.85)).

### <a name="windows-powershell-language"></a>Idioma do Windows PowerShell

A linguagem do Windows PowerShell fornece funções e mecanismos de script para invocar comandos. Para obter informações completas sobre scripts, consulte a referência de linguagem do Windows PowerShell fornecida com o Windows PowerShell.

### <a name="extended-type-system-ets"></a>Sistema de tipo estendido (ETS)

O Windows PowerShell fornece acesso a uma variedade de objetos diferentes, como objetos .NET e XML. Como consequência, para apresentar uma abstração comum para todos os tipos de objeto, o Shell usa o sistema de tipo estendido (ETS). A maioria das funcionalidades do ETS é transparente para o usuário, mas o script ou o desenvolvedor do .NET o utiliza para as seguintes finalidades:

- Exibindo um subconjunto dos membros de objetos específicos. O Windows PowerShell fornece uma exibição "adaptada" de vários tipos de objetos específicos.

- Adicionando membros a objetos existentes.

- Acesso a objetos serializados.

- Gravando objetos personalizados.

  Usando o ETS, você pode criar novos "tipos" flexíveis que são compatíveis com a linguagem do Windows PowerShell. Se você for um desenvolvedor do .NET, poderá trabalhar com objetos usando a mesma semântica que a linguagem do Windows PowerShell se aplica ao script, por exemplo, para determinar se um objeto é avaliado como `true` .

  Para obter mais informações sobre o ETS e como o Windows PowerShell usa objetos, consulte [conceitos de objeto do Windows PowerShell](/powershell/scripting/learn/understanding-important-powershell-concepts?view=powershell-6).

## <a name="programming-for-windows-powershell"></a>Programação para o Windows PowerShell

O Windows PowerShell define seu código para comandos, provedores e outros módulos de programa usando o .NET Framework. Você não está confinado ao uso de Microsoft Visual Studio na criação de módulos personalizados para o Windows PowerShell, embora os exemplos fornecidos neste guia sejam conhecidos para execução nessa ferramenta. Você pode usar qualquer linguagem .NET que dê suporte à herança de classe e ao uso de atributos. Em alguns casos, as APIs do Windows PowerShell exigem que a linguagem de programação seja capaz de acessar tipos genéricos.

## <a name="programmers-reference"></a>Referência do programador

Para referência ao desenvolver para o Windows PowerShell, consulte o [SDK do Windows PowerShell](../windows-powershell-reference.md).

## <a name="getting-started-using-windows-powershell"></a>Introdução usando o Windows PowerShell

Para obter mais informações sobre como começar a usar o Shell do Windows PowerShell, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell) fornecido com o Windows PowerShell. Um documento de referência rápida com três dobras também é fornecido como um primer para uso de cmdlet.

## <a name="contents-of-this-guide"></a>Conteúdo deste guia

|Tópico|Definição|
|-----------|----------------|
|[Como criar um provedor do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)|Esta seção descreve como criar um provedor do Windows PowerShell para o Windows PowerShell.|
|[Como criar um aplicativo host do Windows PowerShell](/powershell/scripting/developer/hosting/writing-a-windows-powershell-host-application)|Esta seção descreve como gravar um aplicativo host que manipula um runspace e como gravar um aplicativo host que implementa seu próprio host personalizado.|
|[Como criar um snap-in do Windows PowerShell](../cmdlet/how-to-create-a-windows-powershell-snap-in.md)|Esta seção descreve como criar um snap-in que é usado para registrar todos os cmdlets e provedores em um assembly e como criar um snap-in personalizado.|
|[Como criar um shell do console](./how-to-create-a-console-shell.md)|Esta seção descreve como criar um shell de console que não é extensível.|
|[Conceitos do Windows PowerShell](./windows-powershell-concepts.md)|Esta seção contém informações conceituais que ajudarão você a entender o Windows PowerShell do ponto de vista de um desenvolvedor.|

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
