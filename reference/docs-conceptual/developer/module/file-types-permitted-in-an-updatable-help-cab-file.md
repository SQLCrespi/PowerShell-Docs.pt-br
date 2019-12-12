---
title: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 3562804157ebdfca561445a8671d726b55cc4efd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367255"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="52530-102">Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="52530-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="52530-103">Este tópico lista e descreve os requisitos de conteúdo para arquivos CAB de ajuda atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="52530-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="52530-104">Requisitos de arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="52530-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="52530-105">O conteúdo do arquivo CAB não compactado é limitado a 1 GB por padrão.</span><span class="sxs-lookup"><span data-stu-id="52530-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="52530-106">Para ignorar esse limite, os usuários precisam usar o parâmetro **Force** dos cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="52530-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="52530-107">Para garantir a segurança dos arquivos de ajuda que são baixados da Internet, um arquivo CAB de ajuda atualizável pode incluir apenas os tipos de arquivo listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="52530-107">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="52530-108">O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) valida todos os arquivos em relação aos esquemas de tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="52530-108">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="52530-109">Se o cmdlet `Update-Help` encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do CAB no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="52530-109">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="52530-110">Tópicos de ajuda baseados em XML para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="52530-110">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="52530-111">Tópicos de ajuda baseados em XML para scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="52530-111">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="52530-112">Tópicos de ajuda baseados em XML para provedores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52530-112">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="52530-113">Tópicos de ajuda baseados em texto, como sobre tópicos.</span><span class="sxs-lookup"><span data-stu-id="52530-113">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="52530-114">O [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifica o conteúdo do CAB ao descompactar o CAB.</span><span class="sxs-lookup"><span data-stu-id="52530-114">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="52530-115">Se `Update-Help` localizar tipos de arquivo sem conformidade em um arquivo CAB de ajuda atualizável, ele gerará um erro de encerramento e interromperá a operação.</span><span class="sxs-lookup"><span data-stu-id="52530-115">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="52530-116">Ele não instala arquivos de ajuda do CAB, mesmo os de tipos de arquivo em conformidade.</span><span class="sxs-lookup"><span data-stu-id="52530-116">It does not install any help files from the CAB, even those of compliant file types.</span></span>