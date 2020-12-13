---
ms.date: 09/13/2016
ms.topic: reference
title: Exibição de lista (rótulos)
description: Exibição de lista (rótulos)
ms.openlocfilehash: 2d341ae95d025e0f95b5d88b96afb846b62b092f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666681"
---
# <a name="list-view-labels"></a><span data-ttu-id="12839-103">Exibição de lista (rótulos)</span><span class="sxs-lookup"><span data-stu-id="12839-103">List View (Labels)</span></span>

<span data-ttu-id="12839-104">Este exemplo mostra como implementar um modo de exibição de lista que exibe um rótulo personalizado para cada linha da lista.</span><span class="sxs-lookup"><span data-stu-id="12839-104">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="12839-105">Esta exibição de lista exibe as propriedades do [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) que é retornado pelo cmdlet [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="12839-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="12839-106">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="12839-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="12839-107">Para carregar este arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="12839-107">To load this formatting file</span></span>

1. <span data-ttu-id="12839-108">Copie o XML da seção de exemplo deste tópico em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="12839-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="12839-109">Salve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="12839-109">Save the text file.</span></span> <span data-ttu-id="12839-110">Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="12839-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="12839-111">Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="12839-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="12839-112">Esse arquivo de formatação define a exibição de um objeto que já está definido por um arquivo de formatação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12839-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="12839-113">Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.</span><span class="sxs-lookup"><span data-stu-id="12839-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="12839-114">Demonstra</span><span class="sxs-lookup"><span data-stu-id="12839-114">Demonstrates</span></span>

<span data-ttu-id="12839-115">Esse arquivo de formatação demonstra os seguintes elementos XML:</span><span class="sxs-lookup"><span data-stu-id="12839-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="12839-116">O elemento [Name](./name-element-for-view-format.md) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="12839-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="12839-117">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="12839-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="12839-118">O elemento [ListControl](./listcontrol-element-format.md) que define qual propriedade é exibida pela exibição.</span><span class="sxs-lookup"><span data-stu-id="12839-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="12839-119">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="12839-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="12839-120">O elemento [Label](./label-element-for-listitem-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="12839-120">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="12839-121">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) que define qual propriedade é exibida.</span><span class="sxs-lookup"><span data-stu-id="12839-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="12839-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="12839-122">Example</span></span>

<span data-ttu-id="12839-123">O XML a seguir define um modo de exibição de lista que exibe um rótulo personalizado em cada linha.</span><span class="sxs-lookup"><span data-stu-id="12839-123">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="12839-124">Nesse caso, o rótulo inclui o nome da propriedade com cada letra em maiúscula e a palavra "Property".</span><span class="sxs-lookup"><span data-stu-id="12839-124">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="12839-125">Em cada linha, o nome da propriedade é exibido seguido pelo valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="12839-125">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>

  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="12839-126">O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.</span><span class="sxs-lookup"><span data-stu-id="12839-126">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="12839-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12839-127">See Also</span></span>

[<span data-ttu-id="12839-128">Exemplos de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="12839-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="12839-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="12839-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
