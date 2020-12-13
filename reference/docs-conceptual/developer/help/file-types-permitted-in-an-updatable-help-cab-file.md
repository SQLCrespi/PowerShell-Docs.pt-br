---
ms.date: 03/22/2012
ms.topic: reference
title: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável
description: Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável
ms.openlocfilehash: bb69b8b89a9a3a5c8c00059ec404a4d41a5db9a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654744"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="d6c3f-103">Tipos de arquivo permitidos em um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="d6c3f-103">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="d6c3f-104">O conteúdo do arquivo CAB não compactado é limitado a 1 GB por padrão.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-104">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="d6c3f-105">Para ignorar esse limite, os usuários precisam usar o parâmetro **Force** dos cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="d6c3f-105">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="d6c3f-106">Para garantir a segurança dos arquivos de ajuda que são baixados da Internet, um arquivo CAB de ajuda atualizável pode incluir apenas os tipos de arquivo listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-106">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="d6c3f-107">O cmdlet [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) valida todos os arquivos em relação aos esquemas de tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="d6c3f-108">Se o `Update-Help` cmdlet encontrar um arquivo inválido ou não for um tipo permitido, ele não instalará o arquivo inválido e interromperá a instalação de arquivos do cab no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-108">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="d6c3f-109">Tópicos de ajuda baseados em XML para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-109">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="d6c3f-110">Tópicos de ajuda baseados em XML para scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-110">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="d6c3f-111">Tópicos de ajuda baseados em XML para provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-111">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="d6c3f-112">Tópicos de ajuda baseados em texto, como sobre tópicos.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-112">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="d6c3f-113">O [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifica o conteúdo do CAB ao descompactar o CAB.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="d6c3f-114">Se o `Update-Help` encontrar tipos de arquivo sem conformidade em um arquivo CAB de ajuda atualizável, ele gerará um erro de encerramento e interromperá a operação.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-114">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="d6c3f-115">Ele não instala arquivos de ajuda do CAB, mesmo os de tipos de arquivo em conformidade.</span><span class="sxs-lookup"><span data-stu-id="d6c3f-115">It does not install any help files from the CAB, even those of compliant file types.</span></span>
