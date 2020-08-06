---
title: Elemento DisplayError (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774279"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="2c384-102">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="2c384-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="2c384-103">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="2c384-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="2c384-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="2c384-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2c384-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c384-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2c384-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2c384-106">Attributes and Elements</span></span>

<span data-ttu-id="2c384-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DisplayError` elemento.</span><span class="sxs-lookup"><span data-stu-id="2c384-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2c384-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c384-108">Attributes</span></span>

<span data-ttu-id="2c384-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2c384-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2c384-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2c384-110">Child Elements</span></span>

<span data-ttu-id="2c384-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2c384-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2c384-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2c384-112">Parent Elements</span></span>

|<span data-ttu-id="2c384-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c384-113">Element</span></span>|<span data-ttu-id="2c384-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2c384-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2c384-115">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="2c384-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="2c384-116">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="2c384-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2c384-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c384-117">Remarks</span></span>

<span data-ttu-id="2c384-118">Por padrão, quando ocorre um erro durante a tentativa de exibir um dado, o local dos dados é deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="2c384-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="2c384-119">Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibida.</span><span class="sxs-lookup"><span data-stu-id="2c384-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c384-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c384-120">See Also</span></span>

[<span data-ttu-id="2c384-121">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="2c384-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="2c384-122">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c384-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
