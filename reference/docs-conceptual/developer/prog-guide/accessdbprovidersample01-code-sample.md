---
title: Exemplo de código AccessDbProviderSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35540d2a-c18f-4179-b869-1a3dc5a8c1bd
caps.latest.revision: 6
ms.openlocfilehash: 22cfbc63bd369ebcb2fd8a0d0e8d1995941bbb0f
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417993"
---
# <a name="accessdbprovidersample01-code-sample"></a>Exemplo de código AccessDbProviderSample01

O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Essa implementação fornece métodos para iniciar e interromper o provedor e, embora não forneça um meio para acessar um armazenamento de dados ou para obter ou definir os dados no repositório de dados, ele fornece a funcionalidade básica exigida por todos os provedores.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (AccessDBSampleProvider01.cs) para esse provedor usando o kit de desenvolvimento de software do Windows para componentes de tempo de execução do Windows Vista e Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
>
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.
>
> Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[AccessDBProviderSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a>Consulte também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
