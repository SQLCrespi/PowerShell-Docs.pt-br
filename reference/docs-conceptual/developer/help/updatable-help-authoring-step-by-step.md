---
title: 'Criação de ajuda atualizável: passo a passo | Microsoft Docs'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: a5290265f3d729504983b95195c793b88c4a2613
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811375"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="38735-102">Criação de ajuda atualizável: passo a passo</span><span class="sxs-lookup"><span data-stu-id="38735-102">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="38735-103">Este documento lista as etapas no processo de criação de ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="38735-103">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="38735-104">Criando ajuda atualizável: passo a passo</span><span class="sxs-lookup"><span data-stu-id="38735-104">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="38735-105">A ajuda atualizável foi projetada para usuários finais, mas também fornece benefícios significativos para autores de módulo e autores de ajuda, incluindo a capacidade de adicionar conteúdo, corrigir erros, fornecer em várias culturas de interface do usuário e responder a comentários e solicitações de usuários, muito depois que o módulo for enviado.</span><span class="sxs-lookup"><span data-stu-id="38735-105">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="38735-106">Este tópico explica como empacotar e carregar arquivos de ajuda para que os usuários possam baixá-los e instalá-los usando os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="38735-106">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="38735-107">As etapas a seguir fornecem uma visão geral do processo de suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="38735-107">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="38735-108">Etapa 1: localizar um site da Internet para seus arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="38735-108">Step 1: Find an Internet site for your help files</span></span>

<span data-ttu-id="38735-109">A primeira etapa na criação da ajuda atualizável é encontrar um local da Internet para os arquivos de ajuda do seu módulo.</span><span class="sxs-lookup"><span data-stu-id="38735-109">The first step in creating updatable help is to find an Internet location for your module's help files.</span></span> <span data-ttu-id="38735-110">Na verdade, você pode usar dois locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="38735-110">Actually, you can use two different locations.</span></span> <span data-ttu-id="38735-111">Você pode manter o arquivo de informações de ajuda do módulo (HelpInfo XML – descrito abaixo) em um local da Internet e o conteúdo da ajuda arquivos CAB em outro local da Internet.</span><span class="sxs-lookup"><span data-stu-id="38735-111">You can keep your module's help information file (HelpInfo XML - described below) at one Internet location and the help content CAB files at another Internet location.</span></span> <span data-ttu-id="38735-112">Todos os arquivos CAB de conteúdo da ajuda para um módulo devem estar no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="38735-112">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="38735-113">Você pode inserir arquivos CAB de conteúdo da ajuda para diferentes módulos no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="38735-113">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="38735-114">Etapa 2: adicionar uma chave HelpInfoURI ao manifesto do módulo</span><span class="sxs-lookup"><span data-stu-id="38735-114">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="38735-115">Adicione uma chave **HelpInfoURI** ao manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="38735-115">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="38735-116">O valor da chave é o Uniform Resource Identifier (URI) do local do arquivo de informações XML HelpInfo para seu módulo.</span><span class="sxs-lookup"><span data-stu-id="38735-116">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="38735-117">Por segurança, o endereço deve começar com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="38735-117">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="38735-118">O URI deve especificar um local de Internet, mas não deve incluir o nome de arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="38735-118">The URI should specify an Internet location, but must not include the HelpInfo XML file name.</span></span>

<span data-ttu-id="38735-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="38735-119">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'https://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="38735-120">Etapa 3: criar um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="38735-120">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="38735-121">O arquivo de informações XML HelpInfo contém o URI do local da Internet dos seus arquivos de ajuda e os números de versão dos arquivos de ajuda mais recentes para seu módulo em cada cultura de interface do usuário com suporte.</span><span class="sxs-lookup"><span data-stu-id="38735-121">The HelpInfo XML information file contains the URI of the Internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="38735-122">Cada módulo do Windows PowerShell tem um arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="38735-122">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="38735-123">Ao atualizar os arquivos de ajuda, você edita ou substitui o arquivo XML HelpInfo; Você não adiciona outro.</span><span class="sxs-lookup"><span data-stu-id="38735-123">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="38735-124">Para obter mais informações, consulte [como criar um arquivo XML HelpInfo](./how-to-create-a-helpinfo-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="38735-124">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-sign-your-help-files"></a><span data-ttu-id="38735-125">Etapa 4: assinar seus arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="38735-125">Step 4: Sign your help files</span></span>

<span data-ttu-id="38735-126">As assinaturas digitais não são necessárias, mas elas são uma recomendação de práticas recomendadas sempre que você estiver compartilhando arquivos.</span><span class="sxs-lookup"><span data-stu-id="38735-126">Digital signatures are not required, but they are a best-practice recommendation whenever you are sharing files.</span></span>

### <a name="step-5-create-cab-files"></a><span data-ttu-id="38735-127">Etapa 5: criar arquivos CAB</span><span class="sxs-lookup"><span data-stu-id="38735-127">Step 5: Create CAB files</span></span>

<span data-ttu-id="38735-128">Use uma ferramenta que cria arquivos de gabinete (. cab), como MakeCab. exe, para criar um. Arquivo CAB que contém os arquivos de ajuda para seu módulo.</span><span class="sxs-lookup"><span data-stu-id="38735-128">Use a tool that creates cabinet (.cab) files, such as MakeCab.exe, to create a .CAB file that contains the help files for your module.</span></span> <span data-ttu-id="38735-129">Crie um arquivo CAB separado para os arquivos de ajuda em cada cultura de interface do usuário com suporte.</span><span class="sxs-lookup"><span data-stu-id="38735-129">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="38735-130">Para obter mais informações, consulte [como preparar arquivos CAB de ajuda atualizáveis](./how-to-prepare-updatable-help-cab-files.md).</span><span class="sxs-lookup"><span data-stu-id="38735-130">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-6-upload-your-files"></a><span data-ttu-id="38735-131">Etapa 6: carregar seus arquivos</span><span class="sxs-lookup"><span data-stu-id="38735-131">Step 6: Upload your files</span></span>

<span data-ttu-id="38735-132">Para publicar arquivos de ajuda novos ou atualizados, carregue os arquivos CAB no local da Internet que é especificado pelo elemento **HelpContentUri** no arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="38735-132">To publish new or updated help files, upload the CAB files to the Internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="38735-133">Em seguida, carregue o arquivo XML HelpInfo no local da Internet que é especificado pelo valor da chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="38735-133">Then, upload the HelpInfo XML file to the Internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
