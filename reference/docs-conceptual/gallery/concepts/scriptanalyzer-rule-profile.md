---
ms.date: 06/12/2017
title: Perfil de regra do ScriptAnalyzer para a Galeria
description: Explica como o ScriptAnalyzer do PowerShell é integrado à Galeria do PowerShell.
ms.openlocfilehash: 3af710e8811f0fabfb02f5317d5b4ff9c320f29a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646771"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>Perfil de regra do ScriptAnalyzer para a Galeria

Para garantir a qualidade dos pacotes publicados na Galeria do PowerShell, executamos as regras do [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) para determinar se há violações nos scripts enviados.

Você pode encontrar a lista de regras que estão em execução na [página GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1) do ScriptAnalyzer.
Se tiver preocupações com relação às regras que estamos executando, entre em contato com os Administradores da Galeria do PowerShell ou abra um problema do ScriptAnalyzer.

Os resultados do ScriptAnalyzer serão exibidos em cada página de pacote individual na Galeria no próximo lançamento. Recomendamos que os proprietários de pacote verifiquem seus pacotes para se certificar de que não haja nenhum erro grave nos pacotes publicados.
