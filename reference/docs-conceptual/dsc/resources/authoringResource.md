---
ms.date: 07/08/2020
keywords: DSC,powershell,configuração,instalação
title: Criar recursos personalizados de configuração de estado desejado do Windows PowerShell
description: Este artigo fornece uma visão geral do desenvolvimento de recursos e links para artigos com exemplos e informações específicas.
ms.openlocfilehash: ff9a0c8ae10583155217fbeccc62e6e1c94f9a11
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656402"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a>Criar recursos personalizados de configuração de estado desejado do Windows PowerShell

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

A Configuração de Estado Desejado (DSC) do Windows PowerShell tem recursos internos que podem ser usados para configurar seu ambiente. Este artigo fornece uma visão geral do desenvolvimento de recursos e links para artigos com exemplos e informações específicas.

## <a name="dsc-resource-components"></a>Componentes de recursos de DSC

Um recurso de DSC é um módulo do Windows PowerShell. O módulo contém o esquema (a definição das propriedades configuráveis) e a implementação (o código que faz o trabalho real especificado por uma configuração) do recurso. Um esquema de recursos de DSC pode ser definido em um arquivo MOF e a implementação é executada por um módulo de script. Começando com o suporte das classes do PowerShell na versão 5, o esquema e a implementação podem ser definidos em uma classe. Os artigos a seguir descrevem detalhadamente como criar recursos de DSC.

- [Escrevendo um recurso personalizado de DSC com MOF](authoringResourceMOF.md)
- [Implementando um recurso de DSC em C#](authoringResourceMofCS.md)
- [Escrevendo um recurso personalizado de DSC com classes do PowerShell](authoringResourceClass.md)
- [Recursos de composição: usando uma configuração DSC como um recurso](authoringResourceComposite.md)
- [Usando a ferramenta Designer de Recursos](authoringResourceMofDesigner.md)
