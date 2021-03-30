---
ms.date: 03/22/2021
keywords: powershell, cmdlet
title: O que é o PowerShell?
description: Este artigo é uma introdução ao ambiente de script do PowerShell e seus recursos.
ms.openlocfilehash: 3e1c2cae4b8d6507057ee8136265710a8dfe74f3
ms.sourcegitcommit: 719debaed3cc32ba463b1d4cc56a491d8ecbce26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "105029682"
---
# <a name="what-is-powershell"></a>O que é o PowerShell?

O PowerShell é uma solução de automação de tarefas multiplataforma que consiste em um shell de linha de comando, em uma linguagem de script e uma estrutura de gerenciamento de configuração. O PowerShell pode ser executado no Windows, Linux e macOS.

## <a name="shell"></a>Shell

O PowerShell é um shell de comando moderno que inclui os melhores recursos de outros shells populares. Ao contrário da maioria dos shells que só aceita e retorna texto, o PowerShell aceita e retorna objetos .NET. O shell inclui os seguintes recursos:

- [Histórico][] de linha de comando robusto
- Previsão de comando e conclusão da guia (confira [about_PSReadLine][])
- Suporte a [aliases][] de parâmetro e de comando
- [Pipeline][] para comandos de encadeamento
- Sistema de [ajuda][] no console, semelhante a páginas `man` UNIX

## <a name="scripting-language"></a>Idioma do script

Como uma linguagem de script, o PowerShell é normalmente usado para automatizar o gerenciamento de sistemas. Ele também é usado para compilar, testar e implantar soluções, geralmente em ambientes de CI/CD. O PowerShell é criado no CLR (Common Language Runtime) do .NET. Todas as entradas e saídas são objetos .NET. Não é necessário analisar a saída de texto para extrair informações da saída. A linguagem de script do PowerShell inclui os seguintes recursos:

- Extensível por meio de [funções][], [classes][], [scripts][] e [módulos][]
- [Sistema de formatação][formatting] extensível para saída fácil
- [Sistema de tipos][types] extensível para a criação de tipos dinâmicos
- Suporte integrado para formatos de dados comuns como [CSV][], [JSON][] e [XML][]

## <a name="configuration-management"></a>Gerenciamento de configuração

O [DSC][] (Desired State Configuration) do PowerShell é uma estrutura de gerenciamento no PowerShell que permite gerenciar a infraestrutura empresarial com a configuração como código. Com o DSC, você pode:

- Criar [configurações][] declarativas e scripts personalizados para implantações repetíveis
- Impor definições de configuração e relatar sobre descompasso de configuração
- Implantar a configuração usando modelos [push ou pull][push-pull]

## <a name="next-steps"></a>Próximas etapas

### <a name="getting-started"></a>Introdução

Você é novo no PowerShell e não sabe por onde começar? Confira estes recursos.

- [Instalando o PowerShell][install]
- [Introdução ao PowerShell][PS101]
- [Tutoriais de Bits do PowerShell][tutorials]
- [Módulos do Learn do PowerShell][learn]

### <a name="powershell-in-action"></a>PowerShell em ação

Confira como o PowerShell está sendo usado em diferentes cenários e diferentes plataformas.

- [Comunicação remota do PowerShell por SSH][remoting]
- [Introdução ao Azure PowerShell][azure]
- [Criar um pipeline de CI/CD com o DSC][devops]
- [Gerenciar o Microsoft Exchange][exchange]

<!-- link references -->

[história]: /powershell/module/microsoft.powershell.core/about/about_history
[about_PSReadLine]: /powershell/module/psreadline/about/about_psreadline
[aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[Pipeline]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[help]: /powershell/module/microsoft.powershell.core/get-help
[modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[funções]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[classes]: /powershell/module/microsoft.powershell.core/about/about_classes
[scripts]: /powershell/module/microsoft.powershell.core/about/about_scripts
[formatting]: /powershell/module/microsoft.powershell.core/about/about_format.ps1xml
[types]: /powershell/module/microsoft.powershell.core/about/about_types.ps1xml
[CSV]: /powershell/module/microsoft.powershell.utility/convertfrom-csv
[JSON]: /powershell/module/microsoft.powershell.utility/convertfrom-json
[XML]: /powershell/module/microsoft.powershell.utility/convertto-xml
[configurações]: /powershell/scripting/dsc/configurations/configurations
[DSC]: /powershell/scripting/dsc/overview/dscforengineers
[push-pull]: /powershell/scripting/dsc/pull-server/enactingconfigurations
[install]: /powershell/scripting/install/installing-powershell
[PS101]: /powershell/scripting/learn/ps101/00-introduction
[tutorials]: /powershell/scripting/learn/tutorials/00-introduction
[learn]: /learn/browse/?terms=PowerShell
[azure]: /powershell/azure/get-started-azureps
[devops]: /azure/devops/pipelines/release/dsc-cicd
[exchange]: /powershell/exchange/exchange-management-shell
[remoting]: /powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core
