---
ms.date: 10/11/2019
keywords: DSC,powershell,configuração,instalação
title: Visão Geral da Desired State Configuration para Tomadores de Decisão
ms.openlocfilehash: 271ec04035feb17e932acd0ac80f32213a4e018b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72352131"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a>Visão geral da Desired State Configuration para tomadores de decisão

Este documento descreve os benefícios comerciais do uso da DSC (Desired State Configuration) do PowerShell e não é um guia técnico.

## <a name="what-is-dsc"></a>O que é a DSC?

A DSC do PowerShell é uma plataforma de gerenciamento de configuração integrada ao Windows que se baseia em padrões abertos. A DSC é flexível o suficiente para funcionar de maneira confiável e consistente em cada estágio do ciclo de vida de implantação (desenvolvimento, teste, pré-produção, produção) e durante a expansão.

A DSC concentra-se em [configurações](../configurations/configurations.md). Uma configuração é um script do PowerShell que descreve um ambiente composto por computadores ou nós com características específicas. Essas características podem ser tão simples quanto assegurar que um recurso específico do Windows esteja habilitado ou tão complexas quanto a implantação do SharePoint.

A DSC tem monitoramento e emissão de relatórios internos. Se um sistema não for mais compatível, a DSC poderá gerar um alerta e agir para corrigir o sistema.

## <a name="benefits-of-using-dsc"></a>Benefícios do uso da DSC

O design da configuração simplifica a leitura, o armazenamento e a atualização. As configurações declaram o estado dos dispositivos de destino, em vez de escrever instruções sobre como colocar os dispositivos nesse estado. Esses fatores reduzem os custos de aprendizado, adoção, implementação e manutenção da configuração por meio da DSC.

A criação de configurações significa que etapas complexas de implantação são capturadas como uma **única fonte da verdade** em um único local. As configurações fazem com que as implantações repetidas de um conjunto específico de máquinas sejam menos propensas a erros. Além disso, elas agilizam e tornam as implantações mais confiáveis, o que permite um retorno rápido em implantações complexas.

As configurações são compartilhadas por meio da [Galeria do PowerShell](https://powershellgallery.com). É possível que já existam cenários e melhores práticas comuns para o trabalho que você precisa executar.

## <a name="dsc-and-devops"></a>DSC e DevOps

A DSC foi concebida pensando em [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx). Uma combinação de pessoas, processos e ferramentas que permitem uma implantação e iteração rápidas concentradas em proporcionar vantagens para os usuários finais internos ou externos. Uma única configuração que define um ambiente significa que os desenvolvedores podem codificar seus requisitos em uma configuração e verificá-la no controle do código-fonte. As equipes de operações podem implantar o código sem passar por processos manuais propensos a erros.

As configurações são [controladas por dados](../configurations/configData.md). A definição de dados facilita as operações de identificação e alteração de ambientes sem a intervenção do desenvolvedor.

## <a name="dsc-on-premises-and-off-premises"></a>DSC local e externa

A DSC pode gerenciar implantações locais e externas. Para soluções locais, a DSC tem um [Servidor de pull](../pull-server/pullServer.md) que pode ser usado para centralizar o gerenciamento de máquinas e relatar seus status. Para soluções de nuvem externas, a DSC pode ser usada em praticamente qualquer lugar em que o Windows possa ser utilizado.
Há ofertas específicas do Azure criadas na DSC, como a [Automação do Azure](https://azure.microsoft.com/en-us/documentation/services/automation/), que centralizam os relatórios de DSC.

## <a name="dsc-and-compatibility"></a>DSC e compatibilidade

A DSC foi introduzida no Windows Server 2012 R2, mas está disponível para sistemas operacionais de nível inferior por meio do WMF (Windows Management Framework). Para obter mais informações sobre o WMF, confira [Windows Management Framework](/powershell/scripting/wmf/overview).

A DSC pode ser usada para gerenciar o Linux. Para saber mais, veja [Introdução à DSC para Linux](../getting-started/lnxGettingStarted.md).
