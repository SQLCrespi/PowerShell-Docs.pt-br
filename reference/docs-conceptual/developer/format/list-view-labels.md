---
title: Exibição de lista (rótulos) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: da45bd8dce7ac2149de6a34c11d5419d6cb4ddb0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773378"
---
# <a name="list-view-labels"></a><span data-ttu-id="980ec-102">Exibição de lista (rótulos)</span><span class="sxs-lookup"><span data-stu-id="980ec-102">List View (Labels)</span></span>

<span data-ttu-id="980ec-103">Este exemplo mostra como implementar um modo de exibição de lista que exibe um rótulo personalizado para cada linha da lista.</span><span class="sxs-lookup"><span data-stu-id="980ec-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="980ec-104">Esta exibição de lista exibe as propriedades do [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) que é retornado pelo cmdlet [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="980ec-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="980ec-105">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="980ec-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="980ec-106">Para carregar este arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="980ec-106">To load this formatting file</span></span>

1. <span data-ttu-id="980ec-107">Copie o XML da seção de exemplo deste tópico em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="980ec-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="980ec-108">Salve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="980ec-108">Save the text file.</span></span> <span data-ttu-id="980ec-109">Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="980ec-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="980ec-110">Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="980ec-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="980ec-111">Esse arquivo de formatação define a exibição de um objeto que já está definido por um arquivo de formatação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="980ec-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="980ec-112">Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.</span><span class="sxs-lookup"><span data-stu-id="980ec-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="980ec-113">Demonstra</span><span class="sxs-lookup"><span data-stu-id="980ec-113">Demonstrates</span></span>

<span data-ttu-id="980ec-114">Esse arquivo de formatação demonstra os seguintes elementos XML:</span><span class="sxs-lookup"><span data-stu-id="980ec-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="980ec-115">O elemento [Name](./name-element-for-view-format.md) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="980ec-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="980ec-116">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="980ec-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="980ec-117">O elemento [ListControl](./listcontrol-element-format.md) que define qual propriedade é exibida pela exibição.</span><span class="sxs-lookup"><span data-stu-id="980ec-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="980ec-118">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="980ec-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="980ec-119">O elemento [Label](./label-element-for-listitem-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="980ec-119">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="980ec-120">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) que define qual propriedade é exibida.</span><span class="sxs-lookup"><span data-stu-id="980ec-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="980ec-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="980ec-121">Example</span></span>

<span data-ttu-id="980ec-122">O XML a seguir define um modo de exibição de lista que exibe um rótulo personalizado em cada linha.</span><span class="sxs-lookup"><span data-stu-id="980ec-122">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="980ec-123">Nesse caso, o rótulo inclui o nome da propriedade com cada letra em maiúscula e a palavra "Property".</span><span class="sxs-lookup"><span data-stu-id="980ec-123">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="980ec-124">Em cada linha, o nome da propriedade é exibido seguido pelo valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="980ec-124">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="980ec-125">O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.</span><span class="sxs-lookup"><span data-stu-id="980ec-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="980ec-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="980ec-126">See Also</span></span>

[<span data-ttu-id="980ec-127">Exemplos de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="980ec-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="980ec-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="980ec-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
