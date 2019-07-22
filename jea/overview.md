---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Visão geral de Just Enough Administration
ms.openlocfilehash: 4b74e5be9558810748a8844a325c8213e1b3ebc9
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726657"
---
# <a name="just-enough-administration"></a>Just Enough Administration

O JEA (Administração Suficiente) é uma tecnologia de segurança que permite a administração delegada para itens que possam ser gerenciados com o PowerShell. Com o JEA, você pode:

- **Reduzir o número de administradores em seus computadores** usando contas virtuais ou contas de serviço gerenciado de grupo para executar ações privilegiadas em nome dos usuários regulares.
- **Limitar o que os usuários podem fazer** especificando quais cmdlets, funções e comandos externos eles podem executar.
- **Entender melhor o que seus usuários estão fazendo** com transcrições e logs que mostram exatamente quais comandos um usuário executou durante uma sessão.

**Por que o JEA é importante?**

Contas altamente privilegiadas, usadas para administrar os servidores, representam um sério risco de segurança. Caso um invasor comprometa uma dessas contas, poderia iniciar [ataques laterais](https://aka.ms/pth) por toda a sua organização. Cada conta comprometida fornece a um invasor acesso a um número ainda maior de contas e recursos e o coloca a um passo de roubar os segredos da empresa, iniciar um ataque de negação de serviço, entre outros.

No entanto, nem sempre é fácil remover privilégios administrativos. Considere um cenário comum no qual a função DNS é instalada no mesmo computador que seu Controlador de Domínio do Active Directory. Os administradores do DNS exigem privilégios de administrador local para corrigir problemas com o servidor DNS. Mas para fazer isso, você precisa torná-los membros do altamente privilegiado grupo de segurança **Administradores do Domínio**. Essa abordagem concede de forma efetiva aos Administradores de DNS o controle todo o domínio e o acesso a todos os recursos nesse computador.

O JEA cuida desse problema por meio do princípio de **Privilégios mínimos**. Com o JEA, você pode configurar um ponto de extremidade de gerenciamento para administradores do DNS que fornece a eles acesso somente os comandos do PowerShell de que precisam para realizar seus trabalhos. Isso significa que você pode fornecer o acesso apropriado para reparar um cache DNS inviabilizado ou reiniciar o servidor DNS, sem acidentalmente conceder a eles direitos ao Active Directory, para navegar no sistema de arquivos ou para executar scripts potencialmente perigosos. Melhor ainda, quando a sessão JEA está configurada para usar contas virtuais privilegiadas temporárias, os administradores do DNS podem se conectar ao servidor usando credenciais de **não administrador** e ainda podem executar comandos que, geralmente, exigem privilégios de administrador. O JEA permite que você remova usuários de funções de administrador local/de domínio amplamente privilegiadas e controle cuidadosamente o que eles podem fazer em cada computador.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre os requisitos de uso do JEA, confira o artigo [Pré-requisitos](prerequisites.md).

## <a name="samples-and-dsc-resource"></a>Exemplos e recurso DSC

Exemplos de configurações de JEA e o recurso DSC de JEA podem ser encontrados no [Repositório GitHub de JEA](https://github.com/PowerShell/JEA).
