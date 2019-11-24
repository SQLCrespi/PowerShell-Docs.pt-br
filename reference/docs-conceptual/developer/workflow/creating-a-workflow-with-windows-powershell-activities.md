---
title: Criando um fluxo de trabalho com atividades do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359625"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Criar um fluxo de trabalho com atividades do Windows PowerShell

Você pode criar um fluxo de trabalho do Windows PowerShell selecionando atividades na caixa de ferramentas do Visual Studio e arrastando-as para a janela Designer de Fluxo de Trabalho. Para obter informações sobre como adicionar atividades do Windows PowerShell à caixa de ferramentas do Visual Studio, consulte [adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).

Os procedimentos a seguir descrevem como criar um fluxo de trabalho que verifica o status de domínio de um grupo de computadores especificados pelo usuário, une-os a um domínio se eles ainda não estiverem associados e, em seguida, verifica o status novamente.

### <a name="setting-up-the-project"></a>Configurando o projeto

1. Siga o procedimento em [adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) para criar um projeto de fluxo de trabalho e adicionar as atividades dos assemblies [Microsoft. PowerShell. Activities](/dotnet/api/Microsoft.PowerShell.Activities) e [Microsoft. PowerShell. Management. Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) à caixa de ferramentas.

2. Adicione o System. Management. Automation, o Microsoft. PowerShell. Activities, o System. Management, o Microsoft. PowerShell. Management. Activities e o Microsoft. PowerShell. Commands. Management como no projeto como assemblies de referência.

### <a name="adding-activities-to-the-workflow"></a>Adicionando atividades ao fluxo de trabalho

1. Adicione uma atividade de **sequência** ao fluxo de trabalho.

2. Crie um argumento chamado `ComputerName` com um tipo de argumento de `String[]`. Esse argumento representa os nomes dos computadores a serem verificados e Unidos.

3. Crie um argumento chamado `DomainCred` do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Esse argumento representa as credenciais de domínio de uma conta de domínio que está autorizada a ingressar um computador no domínio.

4. Crie um argumento chamado `MachineCred` do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Esse argumento representa as credenciais de um administrador nos computadores para verificar e ingressar.

5. Adicione uma atividade **ParallelForEach** dentro da atividade **Sequence** . Insira `comp` e `ComputerName` nas caixas de texto para que o loop itere pelos elementos da matriz de `ComputerName`.

6. Adicione uma atividade **Sequence** ao corpo da atividade **ParallelForEach** . Defina a propriedade **DisplayName** da sequência como `JoinDomain`.

7. Adicione uma atividade **getwmiobject** à sequência **JoinDomain** .

8. Edite as propriedades da atividade **Getwmiobject** da seguinte maneira.

   |Propriedade|Valor|
   |--------------|-----------|
   |**Classes**|"Win32_ComputerSystem"|
   |**PSComputerName**|às|
   |**PSCredential**|MachineCred|

9. Adicione uma atividade **addcomputer** à sequência **JoinDomain** após a atividade **getwmiobject** .

10. Edite as propriedades da atividade **Addcomputer** da seguinte maneira.

    |Propriedade|Valor|
    |--------------|-----------|
    |**ComputerName**|às|
    |**DomainCredential**|DomainCred|

11. Adicione uma atividade **RestartComputer** à sequência **JoinDomain** após a atividade **addcomputer** .

12. Edite as propriedades da atividade **RestartComputer** da seguinte maneira.

    |Propriedade|Valor|
    |--------------|-----------|
    |**ComputerName**|às|
    |**Provedores**|MachineCred|
    |**Fins**|Microsoft. PowerShell. Commands. WaitForServiceTypes. PowerShell|
    |**Aplicação**|verdadeiro|
    |Wait|verdadeiro|
    |PSComputerName|{""}|

13. Adicione uma atividade **getwmiobject** à sequência **JoinDomain** após a atividade **RestartComputer** . Edite suas propriedades para que sejam iguais à atividade **getwmiobject** anterior.

    Quando você tiver concluído os procedimentos, a janela de design do fluxo de trabalho deverá ser parecida com esta.

    ![XAML JoinDomain no designer de fluxo de trabalho](../media/joindomainworkflow.png)
    ![XAML JoinDomain no designer de fluxo de trabalho](../media/joindomainworkflow.png "JoinDomainWorkflow")