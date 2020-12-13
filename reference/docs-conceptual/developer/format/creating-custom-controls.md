---
ms.date: 09/13/2016
ms.topic: reference
title: Criar controles personalizados
description: Criar controles personalizados
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668041"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="57137-103">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="57137-103">Creating Custom Controls</span></span>

<span data-ttu-id="57137-104">Os controles personalizados são os componentes mais flexíveis de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="57137-104">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="57137-105">Ao contrário das exibições de tabela, lista e amplas que definem uma estrutura formal de dados, como uma tabela de dados, os controles personalizados permitem que você defina como uma parte de dados individual é exibida.</span><span class="sxs-lookup"><span data-stu-id="57137-105">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="57137-106">Você pode definir um conjunto comum de controles personalizados que estão disponíveis para todas as exibições do arquivo de formatação, pode definir controles personalizados que estão disponíveis para uma exibição específica ou pode definir um conjunto de controles que estão disponíveis para um grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="57137-106">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="57137-107">Exemplo de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="57137-107">Custom Control Example</span></span>

<span data-ttu-id="57137-108">O exemplo a seguir mostra um controle personalizado que é definido no arquivo XML de Certificates.Format.ps1.</span><span class="sxs-lookup"><span data-stu-id="57137-108">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="57137-109">Esse controle personalizado é usado para separar os objetos [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) exibidos em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="57137-109">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a><span data-ttu-id="57137-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57137-110">See Also</span></span>

[<span data-ttu-id="57137-111">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="57137-111">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
