---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Desinstalar o WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147856"
---
# <a name="uninstallation-instructions"></a>Instruções de desinstalação

## <a name="using-command-prompt"></a>Usando o Prompt de Comando

1. Abra o **Prompt de Comando.**
2. Execute o [Inicializador Autônomo do Windows Update](https://support.microsoft.com/en-us/kb/934307), conforme mostrado abaixo:

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
