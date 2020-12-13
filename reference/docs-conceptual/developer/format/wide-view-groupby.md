---
ms.date: 09/13/2016
ms.topic: reference
title: Exibição ampla (GroupBy)
description: Exibição ampla (GroupBy)
ms.openlocfilehash: 807bea2a5d44c38e2c9977f792bea2fb9bca0fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667667"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="98507-103">Exibição ampla (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="98507-103">Wide View (GroupBy)</span></span>

<span data-ttu-id="98507-104">Este exemplo mostra como implementar uma exibição ampla que exibe grupos de [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) retornados pelo `Get-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98507-104">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="98507-105">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="98507-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="98507-106">Para carregar este arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="98507-106">To load this formatting file</span></span>

1. <span data-ttu-id="98507-107">Copie o XML da seção de exemplo deste tópico em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="98507-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="98507-108">Salve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="98507-108">Save the text file.</span></span> <span data-ttu-id="98507-109">Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="98507-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="98507-110">Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="98507-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="98507-111">Esse arquivo de formatação define a exibição de um objeto que já está definido por arquivos de formatação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98507-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="98507-112">Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.</span><span class="sxs-lookup"><span data-stu-id="98507-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="98507-113">Demonstra</span><span class="sxs-lookup"><span data-stu-id="98507-113">Demonstrates</span></span>

<span data-ttu-id="98507-114">Esse arquivo de formatação demonstra os seguintes elementos XML:</span><span class="sxs-lookup"><span data-stu-id="98507-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="98507-115">O elemento [Name](./name-element-for-view-format.md) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="98507-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="98507-116">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="98507-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="98507-117">O elemento [GroupBy](./groupby-element-for-view-format.md) que define quando um novo grupo é exibido.</span><span class="sxs-lookup"><span data-stu-id="98507-117">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="98507-118">O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) que define qual propriedade é exibida pela exibição.</span><span class="sxs-lookup"><span data-stu-id="98507-118">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="98507-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="98507-119">Example</span></span>

<span data-ttu-id="98507-120">O XML a seguir define uma exibição ampla que exibe grupos de objetos.</span><span class="sxs-lookup"><span data-stu-id="98507-120">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="98507-121">Cada novo grupo é iniciado quando o valor da propriedade [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) é alterado.</span><span class="sxs-lookup"><span data-stu-id="98507-121">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="98507-122">O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.</span><span class="sxs-lookup"><span data-stu-id="98507-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="98507-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98507-123">See Also</span></span>

[<span data-ttu-id="98507-124">Exemplos de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="98507-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="98507-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="98507-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
