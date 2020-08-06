---
title: Criando controles personalizados | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c36fa9b778e01501a3c88f735cdefdfbb04411a0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786111"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="15477-102">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="15477-102">Creating Custom Controls</span></span>

<span data-ttu-id="15477-103">Os controles personalizados são os componentes mais flexíveis de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="15477-103">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="15477-104">Ao contrário das exibições de tabela, lista e amplas que definem uma estrutura formal de dados, como uma tabela de dados, os controles personalizados permitem que você defina como uma parte de dados individual é exibida.</span><span class="sxs-lookup"><span data-stu-id="15477-104">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="15477-105">Você pode definir um conjunto comum de controles personalizados que estão disponíveis para todas as exibições do arquivo de formatação, pode definir controles personalizados que estão disponíveis para uma exibição específica ou pode definir um conjunto de controles que estão disponíveis para um grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="15477-105">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="15477-106">Exemplo de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="15477-106">Custom Control Example</span></span>

<span data-ttu-id="15477-107">O exemplo a seguir mostra um controle personalizado que é definido no arquivo XML de Certificates.Format.ps1.</span><span class="sxs-lookup"><span data-stu-id="15477-107">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="15477-108">Esse controle personalizado é usado para separar os objetos [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) exibidos em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="15477-108">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="15477-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15477-109">See Also</span></span>

[<span data-ttu-id="15477-110">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="15477-110">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
