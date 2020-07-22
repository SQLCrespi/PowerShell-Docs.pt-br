---
title: Colocar a ajuda baseada em comentários em scripts
ms.date: 09/12/2016
ms.openlocfilehash: a3ade6c3138826b924939056b9d1ffb233006d44
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893179"
---
# <a name="placing-comment-based-help-in-scripts"></a>Colocar a ajuda baseada em comentários em scripts

Este tópico explica onde posicionar a ajuda baseada em comentários para um script para que o `Get-Help` cmdlet associe o tópico de ajuda baseado em comentário a scripts e não a nenhuma função que possa estar no script.

## <a name="where-to-place-comment-based-help-for-a-script"></a>Onde posicionar a ajuda baseada em comentários para um script

- No início do arquivo de script.

  A ajuda do script pode ser precedida no script somente por comentários e linhas em branco.

- No final do arquivo de script.

  Se o primeiro item no corpo do script (após a ajuda) for uma declaração de função, deve haver pelo menos duas linhas em branco entre o final da ajuda do script e a declaração da função. Caso contrário, a ajuda será interpretada como sendo ajuda para a função, não ajuda para o script.

## <a name="examples-of-help-placement-in-a-script"></a>Exemplos de posicionamento de ajuda em um script

Os exemplos a seguir mostram cada uma das opções de posicionamento da ajuda baseada em comentários para um script.

### <a name="help-at-the-beginning-of-a-script"></a>Ajuda no início de um script

O exemplo a seguir mostra o comentário baseado no início de um script.

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>Ajuda no final de um script

 O exemplo a seguir mostra o comentário baseado no final de um script.

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
