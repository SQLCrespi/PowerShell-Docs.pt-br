---
title: Como criar um arquivo de formatação (. Format. ps1xml) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: 7a578dd63a53562f992b2970573258b8676e2a52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692278"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="361a1-102">Como criar um arquivo de formatação (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="361a1-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="361a1-103">Este tópico descreve como criar um arquivo de formatação (. Format. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="361a1-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="361a1-104">Você também pode criar um arquivo de formatação fazendo uma cópia de um dos arquivos fornecidos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="361a1-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="361a1-105">Se você fizer uma cópia de um arquivo existente, exclua a assinatura digital existente e adicione sua própria assinatura ao novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="361a1-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="361a1-106">Para criar um arquivo. Format. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="361a1-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="361a1-107">Crie um arquivo de texto (. txt) usando um editor de texto como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="361a1-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="361a1-108">Copie as linhas a seguir no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="361a1-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="361a1-109">As `<Configuration></Configuration>` marcas definem o `Configuration` nó raiz.</span><span class="sxs-lookup"><span data-stu-id="361a1-109">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="361a1-110">Todas as marcas XML adicionais serão incluídas nesse nó.</span><span class="sxs-lookup"><span data-stu-id="361a1-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="361a1-111">As `<ViewDefinitions></ViewDefinitions>` marcas definem o `ViewDefinitions` nó.</span><span class="sxs-lookup"><span data-stu-id="361a1-111">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="361a1-112">Todas as exibições são definidas neste nó.</span><span class="sxs-lookup"><span data-stu-id="361a1-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="361a1-113">Salve o arquivo na pasta de instalação do Windows PowerShell, na pasta do módulo ou em uma subpasta da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="361a1-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="361a1-114">Use o seguinte formato de nome ao salvar o arquivo: `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="361a1-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="361a1-115">Os arquivos de formatação devem usar a `.format.ps1xml` extensão.</span><span class="sxs-lookup"><span data-stu-id="361a1-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="361a1-116">Agora você está pronto para adicionar exibições ao arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="361a1-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="361a1-117">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="361a1-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="361a1-118">Você pode adicionar uma única exibição para cada objeto, várias exibições para o mesmo objeto ou uma única exibição usada por vários objetos.</span><span class="sxs-lookup"><span data-stu-id="361a1-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="361a1-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="361a1-119">See Also</span></span>

[<span data-ttu-id="361a1-120">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="361a1-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
