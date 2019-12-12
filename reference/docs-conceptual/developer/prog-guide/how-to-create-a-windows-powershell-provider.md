---
title: Como criar um provedor do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide]
- providers [PowerShellProgrammer's Guide], creating
- Windows PowerShell Programmer's Guide, providers
ms.assetid: 863e48e9-7206-4c6a-a59a-2ab2d30396bc
caps.latest.revision: 5
ms.openlocfilehash: ffbf8028ba2b52e77d8e22c061baa9b8b67f6da3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366645"
---
# <a name="how-to-create-a-windows-powershell-provider"></a>Como criar um provedor do Windows PowerShell

Esta seção descreve como criar um provedor do Windows PowerShell. Um provedor do Windows PowerShell pode ser considerado de duas maneiras. Para o usuário, o provedor representa um conjunto de dados armazenados. Por exemplo, os dados armazenados podem ser a metabase Serviços de Informações da Internet (IIS), o registro do Microsoft Windows, o sistema de arquivos do Windows, o Active Directory e os dados de variável e alias armazenados pelo Windows PowerShell.

Para o desenvolvedor, o provedor do Windows PowerShell é a interface entre o usuário e os dados que o usuário precisa acessar. Dessa perspectiva, cada tipo de provedor descrito nesta seção dá suporte a um conjunto de classes base e interfaces específicas que permitem que o tempo de execução do Windows PowerShell exponha determinados cmdlets ao usuário de uma maneira comum.

## <a name="providers-provided-by-windows-powershell"></a>Provedores fornecidos pelo Windows PowerShell

O Windows PowerShell fornece vários provedores (como o provedor FileSystem, o provedor de registro e o provedor de alias) usados para acessar armazenamentos de dados conhecidos. Para obter mais informações sobre os provedores fornecidos pelo Windows PowerShell, use o seguinte comando para acessar a ajuda online:

**PS > Get-Help about_providers**

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a>Acessando os dados armazenados usando caminhos do Windows PowerShell

Provedores do Windows PowerShell são acessíveis para o tempo de execução do Windows PowerShell e para comandos de forma programática por meio do uso de caminhos do Windows PowerShell. Na maioria das vezes, esses caminhos são usados para acessar diretamente os dados por meio do provedor. No entanto, alguns caminhos podem ser resolvidos para caminhos internos do provedor que permitem que um cmdlet Use interfaces de programação de aplicativo (APIs) não Windows PowerShell para acessar os dados. Para obter mais informações sobre como os provedores do Windows PowerShell operam no Windows PowerShell, veja [como funciona o Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a>Expondo cmdlets de provedor usando unidades do Windows PowerShell

Um provedor do Windows PowerShell expõe seus cmdlets com suporte usando unidades virtuais do Windows PowerShell. O Windows PowerShell aplica as seguintes regras para uma unidade do Windows PowerShell:

- O nome de uma unidade pode ser qualquer sequência alfanumérica.

- Uma unidade pode ser especificada em qualquer ponto válido em um caminho, chamado de "raiz".

- Uma unidade pode ser implementada para qualquer dado armazenado, não apenas o sistema de arquivos.

- Cada unidade mantém seu próprio local de trabalho atual, permitindo que o usuário Mantenha o contexto ao alternar entre as unidades.

## <a name="in-this-section"></a>Nesta seção

A tabela a seguir lista os tópicos que incluem exemplos de código que se baseiam um no outro. A partir do segundo tópico, o provedor básico do Windows PowerShell pode ser inicializado e não inicializado pelo tempo de execução do Windows PowerShell, o próximo tópico adiciona a funcionalidade para acessar os dados, o próximo tópico adiciona a funcionalidade para manipular os dados ( os itens nos dados armazenados) e assim por diante.

|Tópico|Definição|
|-----------|----------------|
|[Criando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)|Este tópico discute as coisas que você deve considerar antes de implementar um provedor do Windows PowerShell. Ele resume as classes base do provedor do Windows PowerShell e as interfaces que são usadas.|
|[Criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite que o tempo de execução do Windows PowerShell inicialize e desinicialize o provedor.|
|[Criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite ao usuário acessar um armazenamento de dados por meio de uma unidade do Windows PowerShell.|
|[Criando um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite ao usuário manipular os itens em um armazenamento de dados.|
|[Criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite que o usuário trabalhe em armazenamentos de dados de várias camadas.|
|[Criando um provedor de navegação do Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite ao usuário navegar pelos itens de um armazenamento de dados de maneira hierárquica.|
|[Criando um provedor de conteúdo do Windows PowerShell](./creating-a-windows-powershell-content-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite ao usuário manipular o conteúdo de itens em um armazenamento de dados.|
|[Criando um provedor de propriedades do Windows PowerShell](./creating-a-windows-powershell-property-provider.md)|Este tópico mostra como criar um provedor do Windows PowerShell que permite ao usuário manipular as propriedades de itens em um armazenamento de dados.|

## <a name="see-also"></a>Consulte Também

[Como funciona o Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[SDK do Windows PowerShell](../windows-powershell-reference.md)

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)
