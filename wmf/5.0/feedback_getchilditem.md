---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: cc5d2d799c1292f68de5fb2360fcba220c2c010b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085245"
---
# <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="d2334-102">Get-ChildItem contém o parâmetro -Depth</span><span class="sxs-lookup"><span data-stu-id="d2334-102">Get-ChildItem has -Depth parameter</span></span>
<span data-ttu-id="d2334-103">**Get-ChildItem** agora tem um parâmetro **–Depth** que é usado com **–Recurse** para limitar a recursão:</span><span class="sxs-lookup"><span data-stu-id="d2334-103">**Get-ChildItem** now has a **–Depth** parameter you use with **–Recurse** to limit the recursion:</span></span>

<span data-ttu-id="d2334-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span><span class="sxs-lookup"><span data-stu-id="d2334-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span></span>

<span data-ttu-id="d2334-105">Diretório: C:\\Usuários\\slee\\Downloads\\Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2334-105">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="d2334-106">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="d2334-106">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="d2334-107">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="d2334-107">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="d2334-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="d2334-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="d2334-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="d2334-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span><span class="sxs-lookup"><span data-stu-id="d2334-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span></span>

<span data-ttu-id="d2334-112">Diretório: C:\\Usuários\\slee\\Downloads\\Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2334-112">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="d2334-113">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="d2334-113">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="d2334-114">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="d2334-114">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="d2334-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="d2334-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="d2334-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="d2334-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="d2334-118">Diretório: C:\\Usuários\\slee\\Downloads\\Exemplo\\Depth0</span><span class="sxs-lookup"><span data-stu-id="d2334-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span></span>

<span data-ttu-id="d2334-119">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="d2334-119">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="d2334-120">d----- 4/14/2015 5:33 PM Depth1</span><span class="sxs-lookup"><span data-stu-id="d2334-120">d----- 4/14/2015 5:33 PM Depth1</span></span>
