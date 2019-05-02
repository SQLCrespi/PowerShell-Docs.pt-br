---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: ec4ae8e4b2ef0ec226cb75607f7aaf34b48f6b76
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085636"
---
# <a name="authoring-improvements-using-powershell-ise"></a>Criando melhorias usando o ISE do PowerShell

Criar configurações DSC no ISE do Windows PowerShell ficou muito mais fácil, graças às seguintes melhorias:

- Liste todos os recursos DSC dentro de um bloco de **configuração** ou de **nó** inserindo **Ctrl+Espaço** em uma linha em branco nele.
- O preenchimento automático das propriedades de recurso é do tipo **enumeração**.
- O preenchimento automático da propriedade **DependsOn** dos recursos DSC baseia-se em outras instâncias de recurso na configuração.
- Um melhor preenchimento de tabulação dos valores de propriedade de recurso.

**Observação:** é necessário ter uma cadeia de caracteres vazia para valores de propriedade de recurso antes de usar Ctrl+Espaço para listar as opções. Pressionar **Tab** percorrerá as opções.
