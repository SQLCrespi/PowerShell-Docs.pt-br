---
title: Criando um fluxo de trabalho usando um script do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: 5eb2186cbceee21f8b4a8c88b812e9c71f15e0af
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366025"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a>Criar um fluxo de trabalho pelo uso de um script do Windows PowerShell

Você pode criar um fluxo de trabalho escrevendo um script do Windows PowerShell. Para criar um fluxo de trabalho, use a palavra-chave Workflow seguida por um nome para o fluxo de trabalho antes do corpo do script. Por exemplo:

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

Você encontra o fluxo de trabalho da mesma maneira que faria com qualquer outro comando do Windows PowerShell.

## <a name="implementing-parallel-and-sequence"></a>Implementando paralelo e sequência

O [Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) dá suporte à execução de atividades em paralelo. Para implementar esse recurso em um script do Windows PowerShell, use a palavra-chave `parallel` na frente de um bloco de script. Você também pode usar a construção `foreach -parallel` para iterar por meio de uma coleção de objetos em paralelo. Para executar um grupo de atividades em ordem sequencial dentro de um bloco paralelo, coloque esse grupo de atividades em um bloco de script e preceda o bloco com a palavra-chave Sequence.

## <a name="joining-computers-to-a-domain"></a>Unindo computadores a um domínio

O script a seguir cria um fluxo de trabalho que verifica o status de domínio de um grupo de computadores especificados pelo usuário, une-os a um domínio se eles ainda não estiverem associados e, em seguida, verifica o status novamente. Esta é uma versão de script do fluxo de trabalho XAML explicada na [criação de um fluxo de trabalho com atividades do Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md).

```powershell
workflow Join-Domain
{
    param([string[]] $ComputerName, [PSCredential] $DomainCred, [PsCredential] $MachineCred)

    foreach -parallel($Computer in $ComputerName)
    {
        sequence {
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        Add-Computer -PSComputerName $Computer -PSCredential $DomainCred
        Restart-Computer -ComputerName $Computer -Credential $MachineCred -For PowerShell -Force -Wait -PSComputerName ""
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        }
    }
 }

```