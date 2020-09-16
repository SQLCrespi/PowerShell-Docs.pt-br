---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Desinstalar o WMF 5.0
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236298"
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
4. Selecione **Windows Management Framework 5.0** na lista de atualizações instaladas. Isso corresponde à *KB3134758*, *KB3134759* ou *KB3134760*. Clique em **Desinstalar.**
