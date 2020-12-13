---
ms.date: 09/13/2016
ms.topic: reference
title: Escrever um provedor de navegação
description: Escrever um provedor de navegação
ms.openlocfilehash: 3123672d3365c97714557bd0e72a6e444ac228a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355214"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="df117-103">Escrever um provedor de navegação</span><span class="sxs-lookup"><span data-stu-id="df117-103">Writing a navigation provider</span></span>

<span data-ttu-id="df117-104">Este tópico descreve como implementar os métodos de um provedor do Windows PowerShell que oferece suporte a Contêineres aninhados (armazenamentos de dados de vários níveis), movimentação de itens e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="df117-104">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="df117-105">Um provedor de navegação deve derivar da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="df117-105">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="df117-106">O provedor nos exemplos neste tópico usa um banco de dados do Access como seu armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="df117-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="df117-107">Há vários métodos auxiliares e classes que são usadas para interagir com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df117-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="df117-108">Para obter o exemplo completo que inclui os métodos auxiliares, consulte [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="df117-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="df117-109">Para obter mais informações sobre provedores do Windows PowerShell, consulte [visão geral do provedor do Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="df117-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="df117-110">Implementando métodos de navegação</span><span class="sxs-lookup"><span data-stu-id="df117-110">Implementing navigation methods</span></span>

<span data-ttu-id="df117-111">A classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) implementa métodos que dão suporte a Contêineres aninhados, caminhos relativos e movimentação de itens.</span><span class="sxs-lookup"><span data-stu-id="df117-111">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="df117-112">Para obter uma lista completa desses métodos, consulte [métodos NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span><span class="sxs-lookup"><span data-stu-id="df117-112">For a complete list of these methods, see [NavigationCmdletProvider Methods](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="df117-113">Este tópico se baseia nas informações no guia de [início rápido do provedor do Windows PowerShell](./windows-powershell-provider-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="df117-113">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="df117-114">Este tópico não aborda as noções básicas de como configurar um projeto de provedor ou como implementar os métodos herdados da classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) que criam e removem unidades.</span><span class="sxs-lookup"><span data-stu-id="df117-114">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="df117-115">Este tópico também não aborda como implementar métodos expostos pelas classes [System. Management. Automation. Provider. docmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) ou [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="df117-115">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="df117-116">Para obter um exemplo que mostra como implementar cmdlets de item, consulte [escrevendo um provedor de item](./writing-an-item-provider.md).</span><span class="sxs-lookup"><span data-stu-id="df117-116">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="df117-117">Para obter um exemplo que mostra como implementar cmdlets de contêiner, consulte [escrevendo um provedor de contêiner](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="df117-117">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="df117-118">Declarando a classe do provedor</span><span class="sxs-lookup"><span data-stu-id="df117-118">Declaring the provider class</span></span>

<span data-ttu-id="df117-119">Declare o provedor para derivar da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) e decorar com o [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="df117-119">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="df117-120">Implementando IsItemContainer</span><span class="sxs-lookup"><span data-stu-id="df117-120">Implementing IsItemContainer</span></span>

<span data-ttu-id="df117-121">O método [System. Management. Automation. Provider. Navigationcmdletprovider. IsItemContainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) verifica se o item no caminho especificado é um contêiner.</span><span class="sxs-lookup"><span data-stu-id="df117-121">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

```csharp
protected override bool IsItemContainer(string path)
      {
         if (PathIsDrive(path))
         {
             return true;
         }

         string[] pathChunks = ChunkPath(path);
         string tableName;
         int rowNumber;

         PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

         if (type == PathType.Table)
         {
            foreach (DatabaseTableInfo ti in GetTables())
            {
                if (string.Equals(ti.Name, tableName, StringComparison.OrdinalIgnoreCase))
                {
                    return true;
                }
            } // foreach (DatabaseTableInfo...
         } // if (pathChunks...

         return false;
      }
```

### <a name="implementing-getchildname"></a><span data-ttu-id="df117-122">Implementando getchildname</span><span class="sxs-lookup"><span data-stu-id="df117-122">Implementing GetChildName</span></span>

<span data-ttu-id="df117-123">O método [System. Management. Automation. Provider. Navigationcmdletprovider. getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) Obtém a propriedade Name do item filho no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="df117-123">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="df117-124">Se o item no caminho especificado não for um filho de um contêiner, esse método deverá retornar o caminho.</span><span class="sxs-lookup"><span data-stu-id="df117-124">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

```csharp
protected override string GetChildName(string path)
       {
           if (PathIsDrive(path))
           {
               return path;
           }

           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               return tableName;
           }
           else if (type == PathType.Row)
           {
               return rowNumber.ToString(CultureInfo.CurrentCulture);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

           return null;
       }
```

### <a name="implementing-getparentpath"></a><span data-ttu-id="df117-125">Implementando GetParentPath</span><span class="sxs-lookup"><span data-stu-id="df117-125">Implementing GetParentPath</span></span>

<span data-ttu-id="df117-126">O método [System. Management. Automation. Provider. Navigationcmdletprovider. GetParentPath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) Obtém o caminho do pai do item no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="df117-126">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="df117-127">Se o item no caminho especificado for a raiz do armazenamento de dados (portanto, ele não tem nenhum pai), esse método deverá retornar o caminho raiz.</span><span class="sxs-lookup"><span data-stu-id="df117-127">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

```csharp
protected override string GetParentPath(string path, string root)
       {
           // If root is specified then the path has to contain
           // the root. If not nothing should be returned
           if (!String.IsNullOrEmpty(root))
           {
               if (!path.Contains(root))
               {
                   return null;
               }
           }

           return path.Substring(0, path.LastIndexOf(pathSeparator, StringComparison.OrdinalIgnoreCase));
       }
```

### <a name="implementing-makepath"></a><span data-ttu-id="df117-128">Implementando MakePath</span><span class="sxs-lookup"><span data-stu-id="df117-128">Implementing MakePath</span></span>

<span data-ttu-id="df117-129">O método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) une um caminho pai especificado e um caminho filho especificado para criar um caminho interno de provedor (para obter informações sobre os tipos de caminho aos quais os provedores podem dar suporte, consulte [visão geral do provedor do Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="df117-129">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="df117-130">O mecanismo do PowerShell chama esse método quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) .</span><span class="sxs-lookup"><span data-stu-id="df117-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet.</span></span>

```csharp
protected override string MakePath(string parent, string child)
       {
           string result;

           string normalParent = NormalizePath(parent);
           normalParent = RemoveDriveFromPath(normalParent);
           string normalChild = NormalizePath(child);
           normalChild = RemoveDriveFromPath(normalChild);

           if (String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               result = String.Empty;
           }
           else if (String.IsNullOrEmpty(normalParent) && !String.IsNullOrEmpty(normalChild))
           {
               result = normalChild;
           }
           else if (!String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               if (normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent;
               }
               else
               {
                   result = normalParent + pathSeparator;
               }
           } // else if (!String...
           else
           {
               if (!normalParent.Equals(String.Empty) &&
                   !normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent + pathSeparator;
               }
               else
               {
                   result = normalParent;
               }

               if (normalChild.StartsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result += normalChild.Substring(1);
               }
               else
               {
                   result += normalChild;
               }
           } // else

           return result;
       }
```

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="df117-131">Implementando NormalizeRelativePath</span><span class="sxs-lookup"><span data-stu-id="df117-131">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="df117-132">O método [System. Management. Automation. Provider. Navigationcmdletprovider. Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) usa `path` `basepath` parâmetros e retorna um caminho normalizado que é equivalente ao `path` parâmetro e relativo ao `basepath` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="df117-132">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

```csharp
protected override string NormalizeRelativePath(string path,
                                                            string basepath)
       {
           // Normalize the paths first
           string normalPath = NormalizePath(path);
           normalPath = RemoveDriveFromPath(normalPath);
           string normalBasePath = NormalizePath(basepath);
           normalBasePath = RemoveDriveFromPath(normalBasePath);

           if (String.IsNullOrEmpty(normalBasePath))
           {
               return normalPath;
           }
           else
           {
               if (!normalPath.Contains(normalBasePath))
               {
                   return null;
               }

               return normalPath.Substring(normalBasePath.Length + pathSeparator.Length);
           }
       }
```

### <a name="implementing-moveitem"></a><span data-ttu-id="df117-133">Implementando MoveItem</span><span class="sxs-lookup"><span data-stu-id="df117-133">Implementing MoveItem</span></span>

<span data-ttu-id="df117-134">O método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) move um item do caminho especificado para o caminho de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="df117-134">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="df117-135">O mecanismo do PowerShell chama esse método quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) .</span><span class="sxs-lookup"><span data-stu-id="df117-135">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet.</span></span>

```csharp
protected override void MoveItem(string path, string destination)
       {
           // Get type, table name and rowNumber from the path
           string tableName, destTableName;
           int rowNumber, destRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           PathType destType = GetNamesFromPath(destination, out destTableName,
                                    out destRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (destType == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(destination);
           }

           if (type == PathType.Table)
           {
               ArgumentException e = new ArgumentException("Move not supported for tables");

               WriteError(new ErrorRecord(e, "MoveNotSupported",
                   ErrorCategory.InvalidArgument, path));

               throw e;
           }
           else
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               OdbcDataAdapter dda = GetAdapterForTable(destTableName);
               if (dda == null)
               {
                   return;
               }

               DataSet dds = GetDataSetForTable(dda, destTableName);
               DataTable destTable = GetDataTable(dds, destTableName);
               DataRow row = table.Rows[rowNumber];

               if (destType == PathType.Table)
               {
                   DataRow destRow = destTable.NewRow();

                   destRow.ItemArray = row.ItemArray;
               }
               else
               {
                   DataRow destRow = destTable.Rows[destRowNumber];

                   destRow.ItemArray = row.ItemArray;
               }

               // Update the changes
               if (ShouldProcess(path, "MoveItem"))
               {
                   WriteItemObject(row, path, false);
                   dda.Update(dds, destTableName);
               }
           }
       }
```

## <a name="see-also"></a><span data-ttu-id="df117-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df117-136">See Also</span></span>

[<span data-ttu-id="df117-137">Escrever um provedor de contêineres</span><span class="sxs-lookup"><span data-stu-id="df117-137">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="df117-138">Visão geral do provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df117-138">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
