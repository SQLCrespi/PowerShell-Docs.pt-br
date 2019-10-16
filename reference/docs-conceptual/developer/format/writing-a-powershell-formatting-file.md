---
title: Gravando um arquivo de formatação do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39acce45-5144-43ba-894d-a4ce782fa67d
caps.latest.revision: 13
ms.openlocfilehash: f89f0009972d5237d71cb8f0d1c53cd0ae614b67
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361405"
---
# <a name="writing-a-powershell-formatting-file"></a><span data-ttu-id="55dcc-102">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="55dcc-102">Writing a PowerShell Formatting File</span></span>

<span data-ttu-id="55dcc-103">"Gravar um arquivo de formatação do PowerShell" é para desenvolvedores de comando que estão escrevendo cmdlets ou funções que geram objetos na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="55dcc-103">"Writing a PowerShell Formatting File" is for command developers who are writing cmdlets or functions that output objects to the command line.</span></span> <span data-ttu-id="55dcc-104">Arquivos de formatação definem como o PowerShell exibe esses objetos na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="55dcc-104">Formatting files define how PowerShell displays those objects at the command line.</span></span> <span data-ttu-id="55dcc-105">Esta documentação fornece uma visão geral da formatação de arquivos, uma explicação dos conceitos que você deve entender ao escrever esses arquivos, exemplos de XML usados nesses arquivos e uma seção de referência para os elementos XML.</span><span class="sxs-lookup"><span data-stu-id="55dcc-105">This documentation provides an overview of formatting files, an explanation of the concepts that you should understand when writing these files, examples of XML used in these files, and a reference section for the XML elements.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="55dcc-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="55dcc-106">In This Section</span></span>

<span data-ttu-id="55dcc-107">[Visão geral do arquivo de formatação](./formatting-file-overview.md) Descreve o que é um arquivo de formato e os componentes gerais de um arquivo de formatação, incluindo recursos comuns que podem ser definidos no arquivo, os diferentes tipos de exibições de formato que podem ser definidos para objetos .NET e um exemplo simplificado do XML usado para definir uma tabela v ibir.</span><span class="sxs-lookup"><span data-stu-id="55dcc-107">[Formatting File Overview](./formatting-file-overview.md) Describes what a format file is and the general components of a formatting file, including common features that can be defined in the file, the different types of format views that can be defined for .NET objects, and a simplified example of the XML used to define a table view.</span></span>

<span data-ttu-id="55dcc-108">[Conceitos de formatação de arquivo](./formatting-file-concepts.md) Inclui informações que talvez você precise saber ao criar seus próprios arquivos de formatação, como os diferentes tipos de exibições que você pode definir e componentes especiais dessas exibições.</span><span class="sxs-lookup"><span data-stu-id="55dcc-108">[Formatting File Concepts](./formatting-file-concepts.md) Includes information that you might need to know when creating your own formatting files, such as the different types of views that you can define and special components of those views.</span></span>

<span data-ttu-id="55dcc-109">[Exemplos de arquivos de formatação](./examples-of-formatting-files.md) Fornece exemplos de XML de vários arquivos de formatação, incluindo exemplos de uma exibição de tabela, uma exibição de lista e uma exibição ampla, bem como exemplos que mostram como definir recursos como conjuntos de seleção, condições de seleção e controles comuns.</span><span class="sxs-lookup"><span data-stu-id="55dcc-109">[Examples of Formatting Files](./examples-of-formatting-files.md) Provides XML examples of several formatting files, including examples of a table view, a list view, and a wide view, as well as examples that show how to define features such as selection sets, selection conditions, and common controls.</span></span>

<span data-ttu-id="55dcc-110">[Referência de formato XML](./format-schema-xml-reference.md) Inclui tópicos de referência para os elementos XML usados em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="55dcc-110">[Format XML Reference](./format-schema-xml-reference.md) Includes reference topics for the XML elements used in a formatting file.</span></span>
