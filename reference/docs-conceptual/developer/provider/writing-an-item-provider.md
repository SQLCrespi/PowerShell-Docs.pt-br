---
ms.date: 09/13/2016
ms.topic: reference
title: Escrever um provedor de itens
description: Escrever um provedor de itens
ms.openlocfilehash: f70c6ee50277988c4e3b7c255dc4548bc30319dd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355197"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="ed507-103">Escrever um provedor de itens</span><span class="sxs-lookup"><span data-stu-id="ed507-103">Writing an item provider</span></span>

<span data-ttu-id="ed507-104">Este tópico descreve como implementar os métodos de um provedor do Windows PowerShell que acessam e manipulam itens no armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-104">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="ed507-105">Para poder acessar itens, um provedor deve derivar da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ed507-105">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="ed507-106">O provedor nos exemplos neste tópico usa um banco de dados do Access como seu armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="ed507-107">Há vários métodos auxiliares e classes que são usadas para interagir com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="ed507-108">Para obter o exemplo completo que inclui os métodos auxiliares, consulte [AccessDBProviderSample03](./accessdbprovidersample03.md)</span><span class="sxs-lookup"><span data-stu-id="ed507-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="ed507-109">Para obter mais informações sobre provedores do Windows PowerShell, consulte [visão geral do provedor do Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed507-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="ed507-110">Implementando métodos de item</span><span class="sxs-lookup"><span data-stu-id="ed507-110">Implementing item methods</span></span>

<span data-ttu-id="ed507-111">A classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) expõe vários métodos que podem ser usados para acessar e manipular os itens em um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-111">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span>
<span data-ttu-id="ed507-112">Para obter uma lista completa desses métodos, consulte [métodos do cmdletprovider](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods).</span><span class="sxs-lookup"><span data-stu-id="ed507-112">For a complete list of these methods, see [ItemCmdletProvider Methods](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods).</span></span>
<span data-ttu-id="ed507-113">Neste exemplo, implementaremos quatro desses métodos.</span><span class="sxs-lookup"><span data-stu-id="ed507-113">In this example, we will implement four of these methods.</span></span>
<span data-ttu-id="ed507-114">[System. Management. Automation. Provider. createcmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) Obtém um item em um caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-114">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span>
<span data-ttu-id="ed507-115">[System. Management. Automation. Provider. createcmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) define o valor do item especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-115">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span>
<span data-ttu-id="ed507-116">[System. Management. Automation. Provider. @ cmdletprovider. itens existentes \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) verifica se um item existe no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-116">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span>
<span data-ttu-id="ed507-117">[System. Management. Automation. Provider. createcmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) verifica um caminho para ver se ele é mapeado para um local no armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-117">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="ed507-118">Este tópico se baseia nas informações no guia de [início rápido do provedor do Windows PowerShell](./windows-powershell-provider-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="ed507-118">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="ed507-119">Este tópico não aborda as noções básicas de como configurar um projeto de provedor ou como implementar os métodos herdados da classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) que criam e removem unidades.</span><span class="sxs-lookup"><span data-stu-id="ed507-119">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="ed507-120">Declarando a classe do provedor</span><span class="sxs-lookup"><span data-stu-id="ed507-120">Declaring the provider class</span></span>

<span data-ttu-id="ed507-121">Declare o provedor para derivar da classe [System. Management. Automation. Provider. mycmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) e decorar-o com o [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="ed507-121">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="ed507-122">Implementando GetItem</span><span class="sxs-lookup"><span data-stu-id="ed507-122">Implementing GetItem</span></span>

<span data-ttu-id="ed507-123">O [System. Management. Automation. Provider. @ cmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) é chamado pelo mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. getitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) em seu provedor.</span><span class="sxs-lookup"><span data-stu-id="ed507-123">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet on your provider.</span></span> <span data-ttu-id="ed507-124">O método retorna o item no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-124">The method returns the item at the specified path.</span></span> <span data-ttu-id="ed507-125">No exemplo de banco de dados do Access, o método verifica se o item é a própria unidade, uma tabela no banco de dados ou uma linha no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ed507-125">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="ed507-126">O método envia o item para o mecanismo do PowerShell chamando o método [System. Management. Automation. Provider. cmdletprovider. Writeitemobject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .</span><span class="sxs-lookup"><span data-stu-id="ed507-126">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

```csharp
protected override void GetItem(string path)
      {
          // check if the path represented is a drive
          if (PathIsDrive(path))
          {
              WriteItemObject(this.PSDriveInfo, path, true);
              return;
          }// if (PathIsDrive...

           // Get table name and row information from the path and do
           // necessary actions
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               DatabaseTableInfo table = GetTable(tableName);
               WriteItemObject(table, path, true);
           }
           else if (type == PathType.Row)
           {
               DatabaseRowInfo row = GetRow(tableName, rowNumber);
               WriteItemObject(row, path, false);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

### <a name="implementing-setitem"></a><span data-ttu-id="ed507-127">Implementando SetItem</span><span class="sxs-lookup"><span data-stu-id="ed507-127">Implementing SetItem</span></span>

<span data-ttu-id="ed507-128">O método [System. Management. Automation. Provider. docmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) é chamado pelas chamadas do mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. setitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) .</span><span class="sxs-lookup"><span data-stu-id="ed507-128">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.PowerShell.Commands.SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet.</span></span> <span data-ttu-id="ed507-129">Ele define o valor do item no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-129">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="ed507-130">No exemplo de banco de dados do Access, faz sentido definir o valor de um item somente se esse item for uma linha, portanto, o método gera [NotSupportedException](/dotnet/api/system.notsupportedexception) quando o item não é uma linha.</span><span class="sxs-lookup"><span data-stu-id="ed507-130">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](/dotnet/api/system.notsupportedexception) when the item is not a row.</span></span>

```csharp
protected override void SetItem(string path, object values)
       {
           // Get type, table name and row number from the path specified
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type != PathType.Row)
           {
               WriteError(new ErrorRecord(new NotSupportedException(
                     "SetNotSupported"), "",
                  ErrorCategory.InvalidOperation, path));

               return;
           }

           // Get in-memory representation of table
           OdbcDataAdapter da = GetAdapterForTable(tableName);

           if (da == null)
           {
               return;
           }
           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           if (rowNumber >= table.Rows.Count)
           {
               // The specified row number has to be available. If not
               // NewItem has to be used to add a new row
               throw new ArgumentException("Row specified is not available");
           } // if (rowNum...

           string[] colValues = (values as string).Split(',');

           // set the specified row
           DataRow row = table.Rows[rowNumber];

           for (int i = 0; i < colValues.Length; i++)
           {
               row[i] = colValues[i];
           }

           // Update the table
           if (ShouldProcess(path, "SetItem"))
           {
               da.Update(ds, tableName);
           }

       }
```

### <a name="implementing-itemexists"></a><span data-ttu-id="ed507-131">Implementando os presentes</span><span class="sxs-lookup"><span data-stu-id="ed507-131">Implementing ItemExists</span></span>

<span data-ttu-id="ed507-132">O método [System. Management. Automation. Provider. docmdletprovider. myexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) é chamado pelo mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) .</span><span class="sxs-lookup"><span data-stu-id="ed507-132">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet.</span></span> <span data-ttu-id="ed507-133">O método determina se há um item no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ed507-133">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="ed507-134">Se o item existir, o método o passará de volta para o mecanismo do PowerShell chamando [System. Management. Automation. Provider. cmdletprovider. Writeitemobject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span><span class="sxs-lookup"><span data-stu-id="ed507-134">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

```csharp
protected override bool ItemExists(string path)
       {
           // check if the path represented is a drive
           if (PathIsDrive(path))
           {
               return true;
           }

           // Obtain type, table name and row number from path
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           DatabaseTableInfo table = GetTable(tableName);

           if (type == PathType.Table)
           {
               // if specified path represents a table then DatabaseTableInfo
               // object for the same should exist
               if (table != null)
               {
                   return true;
               }
           }
           else if (type == PathType.Row)
           {
               // if specified path represents a row then DatabaseTableInfo should
               // exist for the table and then specified row number must be within
               // the maximum row count in the table
               if (table != null && rowNumber < table.RowCount)
               {
                   return true;
               }
           }

           return false;

       }
```

### <a name="implementing-isvalidpath"></a><span data-ttu-id="ed507-135">Implementando IsValidPath</span><span class="sxs-lookup"><span data-stu-id="ed507-135">Implementing IsValidPath</span></span>

<span data-ttu-id="ed507-136">O método [System. Management. Automation. Provider. docmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) verifica se o caminho especificado é sintaticamente válido para o provedor atual.</span><span class="sxs-lookup"><span data-stu-id="ed507-136">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="ed507-137">Ele não verifica se existe um item no caminho.</span><span class="sxs-lookup"><span data-stu-id="ed507-137">It does not check whether an item exists at the path.</span></span>

```csharp
protected override bool IsValidPath(string path)
       {
           bool result = true;

           // check if the path is null or empty
           if (String.IsNullOrEmpty(path))
           {
               result = false;
           }

           // convert all separators in the path to a uniform one
           path = NormalizePath(path);

           // split the path into individual chunks
           string[] pathChunks = path.Split(pathSeparator.ToCharArray());

           foreach (string pathChunk in pathChunks)
           {
               if (pathChunk.Length == 0)
               {
                   result = false;
               }
           }
           return result;
       }
```

## <a name="next-steps"></a><span data-ttu-id="ed507-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ed507-138">Next steps</span></span>

<span data-ttu-id="ed507-139">Um provedor típico do mundo real é capaz de dar suporte a itens que contêm outros itens e de mover itens de um caminho para outro dentro da unidade.</span><span class="sxs-lookup"><span data-stu-id="ed507-139">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="ed507-140">Para obter um exemplo de um provedor que dá suporte a contêineres, consulte [escrevendo um provedor de contêiner](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ed507-140">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="ed507-141">Para obter um exemplo de um provedor que dá suporte à movimentação de itens, consulte [escrevendo um provedor de navegação](./writing-a-navigation-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ed507-141">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed507-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed507-142">See Also</span></span>

[<span data-ttu-id="ed507-143">Escrever um provedor de contêineres</span><span class="sxs-lookup"><span data-stu-id="ed507-143">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="ed507-144">Escrever um provedor de navegação</span><span class="sxs-lookup"><span data-stu-id="ed507-144">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="ed507-145">Visão geral do provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed507-145">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
