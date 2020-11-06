---
ms.date: 06/12/2017
title: Desinstalar o WMF 5.0
description: Este artigo explica como desinstalar o WMF de versões mais antigas do Windows.
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660810"
---
# <a name="uninstallation-instructions"></a>Instruções de desinstalação

## <a name="using-command-prompt"></a>Usando o Prompt de Comando

1. Abra o **Prompt de Comando.**
2. Execute o [Inicializador Autônomo do Windows Update](https://support.microsoft.com/kb/934307), conforme mostrado abaixo:

No Windows Server 2012 R2 e Windows 8.1:

```powershell
wusa /uninstall /kb:3134758
```

No Windows Server 2012:

```powershell
wusa /uninstall /kb:3134759
```

No Windows Server 2008 R2 SP1 e Windows 7 SP1:

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a>Usando o Painel de Controle

1. Abra o **Painel de Controle.**
2. Abra **Programas** e, em seguida, **Desinstalar um programa.**
3. Clique em **Exibir atualizações instaladas.**
4. Selecione **Windows Management Framework 5.0** na lista de atualizações instaladas. Isso corresponde à *KB3134758* , *KB3134759* ou *KB3134760*. Clique em **Desinstalar.**
