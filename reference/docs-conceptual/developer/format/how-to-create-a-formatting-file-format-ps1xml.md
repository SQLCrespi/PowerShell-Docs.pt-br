---
ms.date: 09/13/2016
ms.topic: reference
title: Como criar um arquivo de formatação (.format.ps1xml)
description: Como criar um arquivo de formatação (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651999"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="747dd-103">Como criar um arquivo de formatação (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="747dd-103">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="747dd-104">Este tópico descreve como criar um arquivo de formatação (.format.ps1XML).</span><span class="sxs-lookup"><span data-stu-id="747dd-104">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="747dd-105">Você também pode criar um arquivo de formatação fazendo uma cópia de um dos arquivos fornecidos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="747dd-105">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="747dd-106">Se você fizer uma cópia de um arquivo existente, exclua a assinatura digital existente e adicione sua própria assinatura ao novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="747dd-106">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="747dd-107">Para criar um arquivo XML .format.ps1.</span><span class="sxs-lookup"><span data-stu-id="747dd-107">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="747dd-108">Crie um arquivo de texto (. txt) usando um editor de texto como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="747dd-108">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="747dd-109">Copie as linhas a seguir no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="747dd-109">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="747dd-110">As `<Configuration></Configuration>` marcas definem o `Configuration` nó raiz.</span><span class="sxs-lookup"><span data-stu-id="747dd-110">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="747dd-111">Todas as marcas XML adicionais serão incluídas nesse nó.</span><span class="sxs-lookup"><span data-stu-id="747dd-111">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="747dd-112">As `<ViewDefinitions></ViewDefinitions>` marcas definem o `ViewDefinitions` nó.</span><span class="sxs-lookup"><span data-stu-id="747dd-112">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="747dd-113">Todas as exibições são definidas neste nó.</span><span class="sxs-lookup"><span data-stu-id="747dd-113">All views are defined within this node.</span></span>

3. <span data-ttu-id="747dd-114">Salve o arquivo na pasta de instalação do Windows PowerShell, na pasta do módulo ou em uma subpasta da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="747dd-114">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="747dd-115">Use o seguinte formato de nome ao salvar o arquivo:  `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="747dd-115">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="747dd-116">Os arquivos de formatação devem usar a `.format.ps1xml` extensão.</span><span class="sxs-lookup"><span data-stu-id="747dd-116">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="747dd-117">Agora você está pronto para adicionar exibições ao arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="747dd-117">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="747dd-118">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="747dd-118">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="747dd-119">Você pode adicionar uma única exibição para cada objeto, várias exibições para o mesmo objeto ou uma única exibição usada por vários objetos.</span><span class="sxs-lookup"><span data-stu-id="747dd-119">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="747dd-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="747dd-120">See Also</span></span>

[<span data-ttu-id="747dd-121">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="747dd-121">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
