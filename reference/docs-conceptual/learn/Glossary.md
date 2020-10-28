---
ms.date: 06/11/2020
keywords: powershell, cmdlet
title: Glossário do PowerShell
description: Um glossário de terminologia relacionada ao PowerShell.
ms.openlocfilehash: 75b1ed69df7547474687361a9ad3a15e1d677cdc
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499885"
---
# <a name="powershell-glossary"></a>Glossário do PowerShell

|            Termo             | Definição |
| --------------------------- | ---------- |
| módulo binário               | Um módulo do PowerShell cujo módulo raiz é um arquivo de módulo binário (.dll). Um módulo binário pode ou não incluir um manifesto de módulo. |
| parâmetro comum            | Um parâmetro que é adicionado a todos os cmdlets, os fluxos de trabalho e as funções avançadas pelo mecanismo do PowerShell. |
| dot source                  | No PowerShell, a ação de iniciar um comando digitando um ponto e um espaço antes do comando. Comandos que são dot sourced são executados no escopo atual em vez de em um novo escopo. Quaisquer variáveis, aliases, funções ou unidades que o comando criar serão criadas no escopo atual e estarão disponíveis para os usuários quando o comando for concluído. |
| módulo dinâmico              | Um módulo que existe apenas na memória. Os cmdlets New-Module e Import-PSSession criam módulos dinâmicos. |
| parâmetro dinâmico           | Um parâmetro que é adicionado a um cmdlet, uma função ou um script do PowerShell em determinadas condições. Cmdlets, funções, provedores e scripts podem adicionar parâmetros dinâmicos. |
| arquivo de formatação             | Um arquivo XML do PowerShell que tem a extensão `.format.ps1xml` e que define como o PowerShell exibe um objeto com base no tipo do .NET Framework dele. |
| estado de sessão global        | O estado de sessão que contém os dados que são acessíveis para o usuário de uma sessão do PowerShell. |
| host                        | A interface que o mecanismo do PowerShell usa para comunicar-se com o usuário. Por exemplo, o host especifica como os prompts são tratados entre o PowerShell e o usuário. |
| aplicativo host            | Um programa que carrega o mecanismo do PowerShell no processo e usa-o para executar operações. |
| método de processamento de entrada     | Um método que um cmdlet pode usar para processar os registros que ele recebe como entrada. Os métodos de processamento de entrada incluem o método BeginProcessing, o método ProcessRecord, o método EndProcessing e o método StopProcessing. |
| módulo de manifesto             | Um módulo do PowerShell que tem um manifesto e cuja chave RootModule está vazia. |
| module                      | Uma unidade reutilizável autossuficiente que permite particionar, organizar e abstrair o código do PowerShell. Um módulo pode conter cmdlets, provedores, funções, variáveis e outros tipos de recursos que podem ser importados como uma única unidade. |
| manifesto de módulo             | Um arquivo de dados do PowerShell (`.psd1`) que descreve o conteúdo de um módulo e que controla como um módulo é processado. |
| estado de sessão do módulo        | O estado de sessão que contém os dados públicos e privados de um módulo do PowerShell. Os dados privados nesse estado de sessão não estão disponíveis para o usuário de uma sessão do PowerShell. |
| erro de não encerramento       | Um erro que não impede que o PowerShell continue a processar o comando. |
| noun                        | A palavra após o hífen em um nome de cmdlet do PowerShell. O substantivo descreve os recursos sobre os quais o cmdlet atua. |
| conjunto de parâmetros               | Um grupo de parâmetros que podem ser usados no mesmo comando para executar uma ação específica. |
| pipe                        | No PowerShell, o envio dos resultados do comando anterior como entrada para o próximo comando no pipeline. |
| pipeline                    | Uma série de comandos conectados por operadores de pipeline (&#124;) (ASCII 124). Cada operador de pipeline envia os resultados do comando anterior como entrada para o próximo comando. |
| Cmdlet do PowerShell           | Um único comando que participa da semântica do pipeline do PowerShell. Isso inclui cmdlets binários (C#), funções de script avançadas, CDXML e fluxos de trabalho. |
| Comando do PowerShell          | Os elementos em um pipeline que fazem uma ação ser realizada. Os comandos do PowerShell são digitados no teclado ou invocados programaticamente. |
| Arquivo de dados do PowerShell        | Um arquivo de texto que tem a extensão de nome de arquivo `.psd1`. O PowerShell usa arquivos de dados para várias finalidades, como armazenar dados de manifesto de módulo e armazenar cadeias de caracteres traduzidas para internacionalização de script. |
| Unidade do PowerShell            | Uma unidade virtual que fornece acesso direto a um armazenamento de dados. Ela pode ser definida por um provedor do PowerShell ou criada na linha de comando. Unidades criadas na linha de comando são unidades de sessão específica e serão perdidas quando a sessão for fechada. |
| provider                    | Um programa baseado no Microsoft .NET Framework que disponibiliza os dados em um armazenamento de dados especializado disponível no PowerShell para que você possa vê-los e gerenciá-los. |
| PSSession                   | Um tipo de sessão do PowerShell que é criado, gerenciado e fechado pelo usuário. |
| módulo raiz                 | O módulo especificado na chave RootModule em um manifesto de módulo. |
| runspace                    | No PowerShell, o ambiente operacional em que cada comando em um pipeline é executado. |
| bloco de script                | Na linguagem de programação do PowerShell, uma coleção de instruções ou expressões que podem ser usadas como uma única unidade. Um bloco de script pode aceitar argumentos e valores de retorno. |
| arquivo de script                 | Um arquivo que tem a extensão `.ps1` e que contém um script que é gravado na linguagem do PowerShell. |
| módulo de script               | Um módulo do PowerShell cujo módulo raiz é um arquivo de módulo de script (`.psm1`). Um módulo de script pode ou não incluir um manifesto de módulo. |
| arquivo de módulo de script          | Um arquivo que contém um script do PowerShell. O script define os membros que exporta o módulo de script. Os arquivos de módulo de script têm a extensão de nome de arquivo `.psm1`. |
| shell                       | O interpretador de comando que é usado para passar comandos para o sistema operacional. |
| parâmetro de opção            | Um parâmetro que não têm um argumento. |
| erro fatal           | Um erro que interrompe o processamento do comando do PowerShell. |
| transaction                 | Uma unidade atômica de trabalho. O trabalho em uma transação deve ser concluído como um todo; se qualquer parte da transação falhar, a transação inteira falhará. |
| arquivo de tipos                  | Um arquivo XML do PowerShell que tem a extensão `.ps1xml` e que estende as propriedades de tipos do Microsoft .NET Framework no PowerShell. |
| verbo                        | A palavra que precede o hífen em um nome de cmdlet do PowerShell. O verbo descreve a ação que o cmdlet executa. |
| Windows PowerShell ISE      | O Ambiente de Script Integrado – um aplicativo host do Windows PowerShell que permite executar comandos e gravar, testar e depurar scripts em um ambiente amigável, com cores na sintaxe e compatível com Unicode. |
| Snap-in do Windows PowerShell  | Um recurso que define um conjunto de cmdlets, provedores e tipos de Microsoft .NET Framework que podem ser adicionados ao ambiente do Windows PowerShell. |
| Fluxo de trabalho do Windows PowerShell | Um fluxo de trabalho é uma sequência de etapas programadas e conectadas que executam tarefas de execução longa ou exigem a coordenação de várias etapas em vários dispositivos ou nós gerenciados. O fluxo de trabalho do Windows PowerShell permite que os desenvolvedores e profissionais de TI criem sequências de atividades de gerenciamento de vários dispositivos ou tarefas únicas dentro de um fluxo de trabalho, como fluxos de trabalho. O fluxo de trabalho do Windows PowerShell permite adaptar e executar os scripts do PowerShell e os arquivos XAML como fluxos de trabalho. |
