---
title: Exemplo de código AccessDbProviderSample02 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b89a4903-3efc-4b08-9b20-2baadf1d1b66
caps.latest.revision: 6
ms.openlocfilehash: 33cdebd7f2f5ae21ec7aff559382362025d12e47
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416255"
---
# <a name="accessdbprovidersample02-code-sample"></a>Exemplo de código AccessDbProviderSample02

O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md). Essa implementação cria um caminho, estabelece uma conexão com um banco de dados do Access e, em seguida, remove a unidade.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (AccessDBSampleProvider02.cs) para este provedor usando o Microsoft Windows Software Development Kit para Windows Vista e os componentes de tempo de execução do Microsoft .NET Framework 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
>
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório.
>
> Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L11-L154 "AccessDBProviderSample02.cs")]


## <a name="see-also"></a>Consulte também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
