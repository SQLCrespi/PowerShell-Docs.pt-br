---
ms.date: 09/12/2016
ms.topic: reference
title: Esquema XML HelpInfo
description: Esquema XML HelpInfo
ms.openlocfilehash: 157fd9c0f47c57efbaa9b7888fa174a34ad9567d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662011"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="9ac11-103">Esquema XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="9ac11-103">HelpInfo XML Schema</span></span>

<span data-ttu-id="9ac11-104">Este tópico contém o esquema XML para arquivos de informações de ajuda atualizáveis, normalmente conhecidos como "arquivos XML HelpInfo".</span><span class="sxs-lookup"><span data-stu-id="9ac11-104">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="9ac11-105">Esquema XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="9ac11-105">HelpInfo XML Schema</span></span>

<span data-ttu-id="9ac11-106">Os arquivos XML HelpInfo são baseados no esquema XML a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ac11-106">HelpInfo XML files are based on the following XML schema.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="http://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
  <element name="HelpInfo">
    <complexType>
      <sequence>
        <element name="HelpContentURI" type="anyURI" minOccurs="1" maxOccurs="1" />
        <element name="SupportedUICultures" minOccurs="1" maxOccurs="1">
          <complexType>
            <sequence>
              <element name="UICulture" minOccurs="1" maxOccurs="unbounded">
                <complexType>
                  <sequence>
                    <element name="UICultureName" type="language" minOccurs="1" maxOccurs="1" />
                    <element name="UICultureVersion" type="string" minOccurs="1" maxOccurs="1" />
                  </sequence>
                </complexType>
              </element>
            </sequence>
          </complexType>
        </element>
      </sequence>
    </complexType>
  </element>
</schema>
```

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="9ac11-107">Elementos XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="9ac11-107">HelpInfo XML Elements</span></span>

<span data-ttu-id="9ac11-108">O arquivo XML HelpInfo inclui os elementos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ac11-108">The HelpInfo XML file includes the following elements.</span></span>

- <span data-ttu-id="9ac11-109">**HelpContentURI** -contém o URI do local dos arquivos CAB de ajuda para o módulo.</span><span class="sxs-lookup"><span data-stu-id="9ac11-109">**HelpContentURI** - Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="9ac11-110">O URI deve começar com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="9ac11-110">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="9ac11-111">O URI deve especificar um local de Internet, mas não deve incluir o nome de arquivo CAB.</span><span class="sxs-lookup"><span data-stu-id="9ac11-111">The URI should specify an internet location, but must not include the CAB filename.</span></span> <span data-ttu-id="9ac11-112">O valor de **HelpContentURI** pode ser o mesmo ou diferente do valor de **HelpInfoURI** .</span><span class="sxs-lookup"><span data-stu-id="9ac11-112">The **HelpContentURI** value can be the same or different from the **HelpInfoURI** value.</span></span>

- <span data-ttu-id="9ac11-113">**SupportedUICultures** -representa os arquivos de ajuda do módulo em todas as culturas da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9ac11-113">**SupportedUICultures** - Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="9ac11-114">Contém elementos **UICulture** , cada um dos quais representa um conjunto de arquivos de ajuda para o módulo em uma cultura de interface do usuário especificada.</span><span class="sxs-lookup"><span data-stu-id="9ac11-114">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

- <span data-ttu-id="9ac11-115">**UICulture** -representa um conjunto de arquivos de ajuda para o módulo em uma cultura de interface do usuário especificada.</span><span class="sxs-lookup"><span data-stu-id="9ac11-115">**UICulture** - Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="9ac11-116">Adicione um elemento **UICulture** para cada cultura de interface do usuário na qual os arquivos de ajuda são gravados.</span><span class="sxs-lookup"><span data-stu-id="9ac11-116">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

- <span data-ttu-id="9ac11-117">**Uiculturename** -contém o código de idioma para a cultura da interface do usuário na qual os arquivos de ajuda são gravados.</span><span class="sxs-lookup"><span data-stu-id="9ac11-117">**UICultureName** - Contains the language code for the UI culture in which the help files are written.</span></span>

- <span data-ttu-id="9ac11-118">**UICultureVersion** -contém um número de versão de 4 partes em "N1. N2. N3. N4 "formato que representa a versão do arquivo CAB de ajuda na cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9ac11-118">**UICultureVersion** - Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="9ac11-119">Aumente esse número de versão sempre que carregar novos arquivos CAB de ajuda na cultura da interface do usuário especificada por **uiculturename**.</span><span class="sxs-lookup"><span data-stu-id="9ac11-119">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="9ac11-120">Para obter mais informações sobre esse valor, consulte [classe de versão](/dotnet/api/system.version).</span><span class="sxs-lookup"><span data-stu-id="9ac11-120">For more information about this value, see [Version Class](/dotnet/api/system.version).</span></span>
