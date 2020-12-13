---
ms.date: 09/12/2016
ms.topic: reference
title: Arquivo de exemplo XML HelpInfo
description: Arquivo de exemplo XML HelpInfo
ms.openlocfilehash: 321793d61ab5df3cccc7c353b6c93f5a7275b533
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647774"
---
# <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="5053e-103">Arquivo de exemplo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="5053e-103">HelpInfo XML Sample File</span></span>

<span data-ttu-id="5053e-104">Este tópico exibe um exemplo de um arquivo de informações de ajuda atualizável bem formado, normalmente conhecido como "arquivo XML HelpInfo".</span><span class="sxs-lookup"><span data-stu-id="5053e-104">This topic displays a sample of a well-formed Updatable Help Information file, commonly known as "HelpInfo XML file."</span></span> <span data-ttu-id="5053e-105">Neste arquivo de exemplo, os elementos de cultura da interface do usuário são organizados em ordem alfabética pelo nome de cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="5053e-105">In this sample file, the UI culture elements are arranged in alphabetical order by UI culture name.</span></span> <span data-ttu-id="5053e-106">A ordenação alfabética é uma prática recomendada, mas não é necessária.</span><span class="sxs-lookup"><span data-stu-id="5053e-106">Alphabetical ordering is a best practice, but it is not required.</span></span>

## <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="5053e-107">Arquivo de exemplo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="5053e-107">HelpInfo XML Sample File</span></span>

```xml

<?xml version="1.0" encoding="utf-8"?>
<HelpInfo xmlns="http://schemas.microsoft.com/powershell/help/2010/05">
   <HelpContentURI>https://go.microsoft.com/fwlink/?LinkID=141553</HelpContentURI>
   <SupportedUICultures>
    <UICulture>
      <UICultureName>de-DE</UICultureName>
      <UICultureVersion>2.15.0.10</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>en-US</UICultureName>
      <UICultureVersion>3.2.0.7</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>it-IT</UICultureName>
      <UICultureVersion>1.1.0.5</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>ja-JP</UICultureName>
      <UICultureVersion>3.2.0.4</UICultureVersion>
    </UICulture>
   </SupportedUICultures>
</HelpInfo>

```
