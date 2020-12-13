---
ms.date: 09/13/2016
ms.topic: reference
title: Exibição de lista (GroupBy)
description: Exibição de lista (GroupBy)
ms.openlocfilehash: e039c38d1e4e93f65a508fe60aaaf35c64ebe2ed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666613"
---
# <a name="list-view-groupby"></a><span data-ttu-id="025f0-103">Exibição de lista (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="025f0-103">List View (GroupBy)</span></span>

<span data-ttu-id="025f0-104">Este exemplo mostra como implementar um modo de exibição de lista que separa as linhas da lista em grupos.</span><span class="sxs-lookup"><span data-stu-id="025f0-104">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="025f0-105">Esta exibição de lista exibe as propriedades do [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) retornados pelo cmdlet [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="025f0-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="025f0-106">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="025f0-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="025f0-107">Para carregar este arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="025f0-107">To load this formatting file</span></span>

1. <span data-ttu-id="025f0-108">Copie o XML da seção de exemplo deste tópico em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="025f0-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="025f0-109">Salve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="025f0-109">Save the text file.</span></span> <span data-ttu-id="025f0-110">Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="025f0-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="025f0-111">Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="025f0-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="025f0-112">Esse arquivo de formatação define a exibição de um objeto que já está definido por um arquivo de formatação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="025f0-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="025f0-113">Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.</span><span class="sxs-lookup"><span data-stu-id="025f0-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="025f0-114">Demonstra</span><span class="sxs-lookup"><span data-stu-id="025f0-114">Demonstrates</span></span>

<span data-ttu-id="025f0-115">Esse arquivo de formatação demonstra os seguintes elementos XML:</span><span class="sxs-lookup"><span data-stu-id="025f0-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="025f0-116">O elemento [Name](./name-element-for-view-format.md) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="025f0-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="025f0-117">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="025f0-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="025f0-118">O elemento [GroupBy](./viewselectedby-element-format.md) que define como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="025f0-118">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="025f0-119">O elemento [ListControl](./listcontrol-element-format.md) que define qual propriedade é exibida pela exibição.</span><span class="sxs-lookup"><span data-stu-id="025f0-119">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="025f0-120">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="025f0-120">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="025f0-121">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) que define qual propriedade é exibida.</span><span class="sxs-lookup"><span data-stu-id="025f0-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="025f0-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="025f0-122">Example</span></span>

<span data-ttu-id="025f0-123">O XML a seguir define um modo de exibição de lista que inicia um novo grupo sempre que o valor da propriedade [System. ServiceProcess. ServiceController. status](/dotnet/api/System.ServiceProcess.ServiceController.Status) é alterado.</span><span class="sxs-lookup"><span data-stu-id="025f0-123">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="025f0-124">Quando cada grupo é iniciado, é exibido um rótulo personalizado que inclui o novo valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="025f0-124">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
      <ListControl>
        <ListEntries>
          <ListEntry>
            <ListItems>
              <ListItem>
                <PropertyName>Name</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>DisplayName</PropertyName>
              </ListItem>
              <ListItem>
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

<span data-ttu-id="025f0-125">O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.</span><span class="sxs-lookup"><span data-stu-id="025f0-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="025f0-126">As linhas em branco adicionadas antes e depois do rótulo do grupo são automaticamente adicionadas pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="025f0-126">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="025f0-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="025f0-127">See Also</span></span>

[<span data-ttu-id="025f0-128">Exemplos de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="025f0-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="025f0-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="025f0-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
