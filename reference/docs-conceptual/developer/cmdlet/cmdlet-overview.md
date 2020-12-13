---
ms.date: 06/11/2020
ms.topic: reference
title: Visão geral do cmdlet
description: Visão geral do cmdlet
ms.openlocfilehash: ed3082e1a821bb9643ea2eef13b7348eb48488e4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653222"
---
# <a name="cmdlet-overview"></a>Visão geral do cmdlet

Um cmdlet é um comando leve que é usado no ambiente do PowerShell. O tempo de execução do PowerShell invoca esses cmdlets dentro do contexto de scripts de automação que são fornecidos na linha de comando. O tempo de execução do PowerShell também os chama programaticamente por meio de APIs do PowerShell.

## <a name="cmdlets"></a>Cmdlets

Os cmdlets executam uma ação e normalmente retornam um objeto Microsoft .NET para o próximo comando no pipeline. Um cmdlet é um único comando que participa da semântica do pipeline do PowerShell.
Isso inclui cmdlets binários (C#), funções de script avançadas, CDXML e fluxos de trabalho.

Esta documentação do SDK descreve como criar cmdlets binários escritos em C#. Para obter informações sobre cmdlets baseados em script, consulte:

- [about_Functions_Advanced](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [about_Functions_CmdletBindingAttribute](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [about_Functions_Advanced_Methods](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

Para criar um cmdlet binário, você deve implementar uma classe de cmdlet que derive de uma das duas classes base de cmdlet especializadas. A classe derivada deve:

- Declare um atributo que identifique a classe derivada como um cmdlet.
- Defina propriedades públicas que são decoradas com atributos que identificam as propriedades públicas como parâmetros de cmdlet.
- Substitua um ou mais métodos de processamento de entrada para processar registros.

Você pode carregar o assembly que contém a classe diretamente usando o cmdlet [Import-Module](/powershell/module/microsoft.powershell.core/import-module) ou pode criar um aplicativo host que carrega o assembly usando a API [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) . Os dois métodos fornecem acesso programático e de linha de comando à funcionalidade do cmdlet.

## <a name="cmdlet-terms"></a>Termos do cmdlet

Os termos a seguir são usados com frequência na documentação do cmdlet do PowerShell:

### <a name="cmdlet-attribute"></a>Atributo de cmdlet

Um atributo do .NET que é usado para declarar uma classe de cmdlet como um cmdlet. Embora o PowerShell use vários outros atributos opcionais, o atributo cmdlet é necessário. Para obter mais informações sobre esse atributo, consulte [declaração de atributo de cmdlet](cmdlet-attribute-declaration.md).

### <a name="cmdlet-parameter"></a>Parâmetro de cmdlet

As propriedades públicas que definem os parâmetros que estão disponíveis para o usuário ou para o aplicativo que está executando o cmdlet. Os cmdlets podem ter parâmetros obrigatórios, nomeados, posicionais e de *comutação* . Parâmetros de opção permitem definir parâmetros que serão avaliados somente se os parâmetros forem especificados na chamada. Para obter mais informações sobre os diferentes tipos de parâmetros, consulte [cmdlet Parameters](cmdlet-parameters.md).

### <a name="parameter-set"></a>Conjunto de Parâmetros

Um grupo de parâmetros que podem ser usados no mesmo comando para executar uma ação específica. Um cmdlet pode ter vários conjuntos de parâmetros, mas cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo. Um bom design de cmdlet sugere fortemente que o parâmetro exclusivo também seja um parâmetro necessário.
Para obter mais informações sobre conjuntos de parâmetros, consulte [conjuntos de parâmetros de cmdlet](cmdlet-parameter-sets.md).

### <a name="dynamic-parameter"></a>Parâmetro dinâmico

Um parâmetro que é adicionado ao cmdlet em tempo de execução. Normalmente, os parâmetros dinâmicos são adicionados ao cmdlet quando outro parâmetro é definido como um valor específico. Para obter mais informações sobre parâmetros dinâmicos, consulte [parâmetros dinâmicos de cmdlet](cmdlet-dynamic-parameters.md).

### <a name="input-processing-methods"></a>Métodos de processamento de entrada

A classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) fornece os métodos virtuais a seguir que são usados para processar registros. Todas as classes de cmdlet derivadas devem substituir um ou mais dos três primeiros métodos:

- [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing): usado para fornecer uma funcionalidade de pré-processamento única e opcional para o cmdlet.
- [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord): usado para fornecer a funcionalidade de processamento de registro por registro para o cmdlet. O método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) pode ser chamado qualquer número de vezes, ou não, dependendo da entrada do cmdlet.
- [System. Management. Automation. cmdlet. Noprocessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing): usado para fornecer uma funcionalidade de pós-processamento única opcional para o cmdlet.
- [System. Management. Automation. cmdlet. StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing): usado para interromper o processamento quando o usuário interrompe o cmdlet de forma assíncrona (por exemplo, pressionando <kbd>Ctrl</kbd> + <kbd>C</kbd>).

Para obter mais informações sobre esses métodos, consulte [métodos de processamento de entrada de cmdlet](./cmdlet-input-processing-methods.md).

Ao implementar um cmdlet, você deve substituir pelo menos um desses métodos de processamento de entrada.
Normalmente, o **ProcessRecord ()** é o método que você substitui porque ele é chamado para cada registro que o cmdlet processa. Por outro lado, o método **BeginProcessing ()** e o método **endprocessor ()** são chamados uma vez para executar o pré-processamento ou o pós-processamento dos registros. Para obter mais informações sobre esses métodos, consulte [métodos de processamento de entrada](cmdlet-input-processing-methods.md).

### <a name="shouldprocess-feature"></a>Recurso ShouldProcess

O PowerShell permite que você crie cmdlets que solicitam ao usuário comentários antes que o cmdlet faça uma alteração no sistema. Para usar esse recurso, o cmdlet deve declarar que oferece suporte ao `ShouldProcess` recurso quando você declara o atributo cmdlet, e o cmdlet deve chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) de dentro de um método de processamento de entrada. Para obter mais informações sobre como dar suporte à `ShouldProcess` funcionalidade, consulte [solicitando confirmação](requesting-confirmation-from-cmdlets.md).

### <a name="transaction"></a>Transação

Um grupo lógico de comandos que são tratados como uma única tarefa. A tarefa falhará automaticamente se algum comando no grupo falhar e o usuário tiver a opção de aceitar ou rejeitar as ações executadas na transação. Para participar de uma transação, o cmdlet deve declarar que oferece suporte a transações quando o atributo de cmdlet é declarado. O suporte para transações foi introduzido no Windows PowerShell 2,0. Para obter mais informações sobre transações, consulte [como dar suporte a transações](how-to-support-transactions.md).

## <a name="how-cmdlets-differ-from-commands"></a>Como os cmdlets diferem dos comandos

Os cmdlets diferem dos comandos em outros ambientes de Shell de comando das seguintes maneiras:

- Os cmdlets são instâncias de classes .NET; Eles não são executáveis autônomos.
- Os cmdlets podem ser criados a partir de apenas uma dúzia de linhas de código.
- Os cmdlets geralmente não realizam sua própria análise, apresentação de erro ou formatação de saída. A análise, a apresentação de erros e a formatação de saída são manipuladas pelo tempo de execução do PowerShell.
- Os cmdlets processam objetos de entrada do pipeline em vez de fluxos de texto, e os cmdlets normalmente entregam objetos como saída para o pipeline.
- Os cmdlets são orientados a registros porque processam um único objeto de cada vez.

## <a name="cmdlet-base-classes"></a>Classes base de cmdlet

O Windows PowerShell dá suporte a cmdlets que são derivados das duas classes base a seguir.

- A maioria dos cmdlets baseia-se em classes .NET que derivam da classe base [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .
  A derivação dessa classe permite que um cmdlet Use o conjunto mínimo de dependências no tempo de execução do Windows PowerShell. Isso oferece dois benefícios. O primeiro benefício é que os objetos de cmdlet são menores e é menos provável que você seja afetado por alterações no tempo de execução do PowerShell. O segundo benefício é que, se necessário, você pode criar diretamente uma instância do objeto cmdlet e, em seguida, chamá-lo diretamente em vez de chamá-lo por meio do tempo de execução do PowerShell.

- Os cmdlets mais complexos se baseiam em classes .NET que derivam da classe base [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) . A derivação dessa classe oferece muito mais acesso ao tempo de execução do PowerShell. Esse acesso permite que o cmdlet chame scripts, acesse provedores e acesse o estado de sessão atual.
  (Para acessar o estado de sessão atual, você obtém e define as preferências e variáveis de sessão.) No entanto, derivar dessa classe aumenta o tamanho do objeto cmdlet e significa que seu cmdlet está intimamente acoplado à versão atual do tempo de execução do PowerShell.

Em geral, a menos que você precise do acesso estendido ao tempo de execução do PowerShell, você deve derivar da classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .
No entanto, o tempo de execução do PowerShell tem recursos de log extensivos para a execução de cmdlets. Se o modelo de auditoria depender desse log, você poderá impedir a execução do cmdlet de dentro de outro cmdlet derivando da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .

## <a name="cmdlet-attributes"></a>Atributos de cmdlet

O PowerShell define vários atributos .NET que são usados para gerenciar cmdlets e especificar funcionalidades comuns que são fornecidas pelo PowerShell e que podem ser exigidas pelo cmdlet. Por exemplo, os atributos são usados para designar uma classe como um cmdlet, especificar os parâmetros do cmdlet e solicitar a validação de entrada para que os desenvolvedores de cmdlets não precisem implementar essa funcionalidade em seu código de cmdlet. Para obter mais informações sobre atributos, consulte [atributos do PowerShell](./cmdlet-attributes.md).

## <a name="cmdlet-names"></a>Nomes dos cmdlets

O PowerShell usa um par de nomes verbo-and-substantivo para nomear cmdlets. Por exemplo, o `Get-Command` cmdlet incluído no PowerShell é usado para obter todos os cmdlets registrados no Shell de comando. O verbo identifica a ação que o cmdlet executa e o substantivo identifica o recurso no qual o cmdlet executa sua ação.

Esses nomes são especificados quando a classe .NET é declarada como um cmdlet. Para obter mais informações sobre como declarar uma classe .NET como um cmdlet, consulte [declaração de atributo de cmdlet](./cmdlet-class-declaration.md).

## <a name="writing-cmdlet-code"></a>Escrevendo código de cmdlet

Este documento fornece duas maneiras de descobrir como o código de cmdlet é escrito. Se você preferir ver o código sem muita explicação, consulte [exemplos de código de cmdlet](./examples-of-cmdlet-code.md). Se você preferir mais explicações sobre o código, consulte os tópicos [tutorial do getproc](./getproc-tutorial.md), [tutorial do StopProc](./stopproc-tutorial.md)ou [tutorial do SelectStr](./selectstr-tutorial.md) .

Para obter mais informações sobre as diretrizes para escrever cmdlets, consulte [diretrizes de desenvolvimento de cmdlet](./cmdlet-development-guidelines.md).

## <a name="see-also"></a>Consulte Também

[Conceitos de cmdlet do PowerShell](./windows-powershell-cmdlet-concepts.md)

[Gravar um cmdlet do PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do PowerShell](../windows-powershell-reference.md)
