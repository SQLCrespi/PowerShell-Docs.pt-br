---
title: Exibição de lista (básica) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74ff8f6eee0a9358c123455aa00736a11e7f085d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783544"
---
# <a name="list-view-basic"></a><span data-ttu-id="7cf91-102">Exibição de lista (Básica)</span><span class="sxs-lookup"><span data-stu-id="7cf91-102">List View (Basic)</span></span>

<span data-ttu-id="7cf91-103">Este exemplo mostra como implementar um modo de exibição de lista básico que exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) retornados pelo cmdlet [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="7cf91-103">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="7cf91-104">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="7cf91-104">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="7cf91-105">Para carregar este arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="7cf91-105">To load this formatting file</span></span>

1. <span data-ttu-id="7cf91-106">Copie o XML da seção de exemplo deste tópico em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7cf91-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="7cf91-107">Salve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7cf91-107">Save the text file.</span></span> <span data-ttu-id="7cf91-108">Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="7cf91-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="7cf91-109">Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="7cf91-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="7cf91-110">Esse arquivo de formatação define a exibição de um objeto que já está definido por um arquivo de formatação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cf91-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="7cf91-111">Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.</span><span class="sxs-lookup"><span data-stu-id="7cf91-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7cf91-112">Demonstra</span><span class="sxs-lookup"><span data-stu-id="7cf91-112">Demonstrates</span></span>

<span data-ttu-id="7cf91-113">Esse arquivo de formatação demonstra os seguintes elementos XML:</span><span class="sxs-lookup"><span data-stu-id="7cf91-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="7cf91-114">O elemento [Name](./name-element-for-view-format.md) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="7cf91-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="7cf91-115">O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="7cf91-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="7cf91-116">O elemento [ListControl](./listcontrol-element-format.md) que define qual propriedade é exibida pela exibição.</span><span class="sxs-lookup"><span data-stu-id="7cf91-116">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="7cf91-117">O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="7cf91-117">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="7cf91-118">O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) que define qual propriedade é exibida.</span><span class="sxs-lookup"><span data-stu-id="7cf91-118">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="7cf91-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7cf91-119">Example</span></span>

<span data-ttu-id="7cf91-120">O XML a seguir define um modo de exibição de lista que exibe quatro propriedades de [System. ServiceProcess. ServiceController? Displayproperty = objeto FullName](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="7cf91-120">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="7cf91-121">Em cada linha, o nome da propriedade é exibido seguido pelo valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="7cf91-121">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
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
              <PropertyName>Name</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>DisplayName</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>Status</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>ServiceType</PropertyName>
            </ListItem>
          </ListItems>
        </ListEntry>
      </ListEntries>
    </ListControl>
  </View>
</Configuration>
```

<span data-ttu-id="7cf91-122">O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.</span><span class="sxs-lookup"><span data-stu-id="7cf91-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="7cf91-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7cf91-123">See Also</span></span>

[<span data-ttu-id="7cf91-124">Exemplos de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="7cf91-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="7cf91-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cf91-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
