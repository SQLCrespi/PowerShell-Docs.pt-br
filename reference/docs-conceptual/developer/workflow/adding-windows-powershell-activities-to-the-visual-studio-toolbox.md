---
title: Adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: ecd23d3eb722137bdda0498fc71e0e966c57a589
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561182"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a>Adicionar atividades do Windows PowerShell à caixa de ferramentas do Visual Studio

Antes de criar um fluxo de trabalho do PowerShell usando Designer de Fluxo de Trabalho, você deve primeiro adicionar as atividades do PowerShell à caixa de ferramentas em um projeto de aplicativo do console de fluxo de trabalho do Visual Studio. O procedimento a seguir mostra como adicionar as atividades do assembly Microsoft. PowerShell. Core. Activities à caixa de ferramentas do Visual Studio.

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a>Adicionando atividades do Windows PowerShell à caixa de ferramentas

1. Crie um novo projeto de aplicativo de console de fluxo de trabalho no Visual Studio.

2. No menu **Exibir** , clique em **Caixa de Ferramentas**.

3. Adicione uma nova guia na caixa de ferramentas clicando com o botão direito do mouse na caixa de ferramentas e clicando em **Adicionar guia**e dê à nova guia um nome como "atividades do PowerShell".

   A adição de uma guia permite que você agrupe as atividades do PowerShell separadas de outras ferramentas na caixa de ferramentas.

4. Na nova guia caixa de ferramentas, clique em **escolher itens...**. A caixa de diálogo **escolher itens da caixa de ferramentas** é exibida.

5. Na caixa de diálogo **escolher itens da caixa de ferramentas** , clique na guia **sistema. atividades** .

6. Clique em **Procurar**.

7. Navegue até a pasta%WINDIR%\Microsoft.NET\assembly\ GAC_MSIL \Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e e clique duas vezes em Microsoft. PowerShell. Core. Activities. dll.

8. Clique em **OK**. As atividades definidas pelo assembly Microsoft. PowerShell. Core. Activities agora estão disponíveis na caixa de ferramentas.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Fluxo de Trabalho do Windows PowerShell](./writing-a-windows-powershell-workflow.md)

[Criar um fluxo de trabalho com atividades do Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)
