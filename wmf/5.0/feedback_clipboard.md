---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: d5ec95abb1d3160afc4179cff991cb5ef72d85fe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057291"
---
# <a name="clipboard-cmdlets"></a>Área de transferência de Cmdlets
**Get-Clipboard** e **Set-Clipboard** facilitam a transferência do conteúdo de e para uma sessão do Windows PowerShell. Por exemplo, se você usar o Windows Explorer para copiar três arquivos na área de transferência (selecionando-os e pressionando `ctrl-c`, por exemplo), poderá facilmente acessar o conteúdo da área de transferência como uma lista de arquivos:

```powershell
PS C:\\&gt; Get-Clipboard -Format FileDropList

Directory: C:\\Users\\slee\\Downloads\\Example

Mode LastWriteTime Length Name

---- ------------- ------ ----

-a---- 4/14/2015 1:19 PM 0 File2.txt

-a---- 4/14/2015 1:19 PM 0 File3.txt

-a---- 4/14/2015 1:19 PM 0 File1.txt
```


Os cmdlets Clipboard dão suporte a imagens, arquivos de áudio, listas de arquivo e texto.
