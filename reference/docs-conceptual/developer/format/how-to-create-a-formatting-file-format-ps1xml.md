---
title: Como criar um arquivo de formatação (.format.ps1XML) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: abdbd4e15b0c4cb1dafcde087d24ed5792c86c3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781249"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="51d4f-102">Como criar um arquivo de formatação (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="51d4f-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="51d4f-103">Este tópico descreve como criar um arquivo de formatação (.format.ps1XML).</span><span class="sxs-lookup"><span data-stu-id="51d4f-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="51d4f-104">Você também pode criar um arquivo de formatação fazendo uma cópia de um dos arquivos fornecidos pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d4f-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="51d4f-105">Se você fizer uma cópia de um arquivo existente, exclua a assinatura digital existente e adicione sua própria assinatura ao novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="51d4f-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="51d4f-106">Para criar um arquivo XML .format.ps1.</span><span class="sxs-lookup"><span data-stu-id="51d4f-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="51d4f-107">Crie um arquivo de texto (. txt) usando um editor de texto como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="51d4f-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="51d4f-108">Copie as linhas a seguir no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="51d4f-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="51d4f-109">As `<Configuration></Configuration>` marcas definem o `Configuration` nó raiz.</span><span class="sxs-lookup"><span data-stu-id="51d4f-109">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="51d4f-110">Todas as marcas XML adicionais serão incluídas nesse nó.</span><span class="sxs-lookup"><span data-stu-id="51d4f-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="51d4f-111">As `<ViewDefinitions></ViewDefinitions>` marcas definem o `ViewDefinitions` nó.</span><span class="sxs-lookup"><span data-stu-id="51d4f-111">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="51d4f-112">Todas as exibições são definidas neste nó.</span><span class="sxs-lookup"><span data-stu-id="51d4f-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="51d4f-113">Salve o arquivo na pasta de instalação do Windows PowerShell, na pasta do módulo ou em uma subpasta da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="51d4f-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="51d4f-114">Use o seguinte formato de nome ao salvar o arquivo: `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="51d4f-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="51d4f-115">Os arquivos de formatação devem usar a `.format.ps1xml` extensão.</span><span class="sxs-lookup"><span data-stu-id="51d4f-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="51d4f-116">Agora você está pronto para adicionar exibições ao arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="51d4f-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="51d4f-117">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="51d4f-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="51d4f-118">Você pode adicionar uma única exibição para cada objeto, várias exibições para o mesmo objeto ou uma única exibição usada por vários objetos.</span><span class="sxs-lookup"><span data-stu-id="51d4f-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="51d4f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51d4f-119">See Also</span></span>

[<span data-ttu-id="51d4f-120">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51d4f-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
