---
title: Gravando um provedor de itens | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 606c880c-6cf1-4ea6-8730-dbf137bfabff
caps.latest.revision: 5
ms.openlocfilehash: 12d2cb8c40c9fd6278bb964a6259d03167536195
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359875"
---
# <a name="writing-an-item-provider"></a>Escrever um provedor de itens

Este tópico descreve como implementar os métodos de um provedor do Windows PowerShell que acessam e manipulam itens no armazenamento de dados. Para poder acessar itens, um provedor deve derivar da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

O provedor nos exemplos neste tópico usa um banco de dados do Access como seu armazenamento de dados. Há vários métodos auxiliares e classes que são usadas para interagir com o banco de dados. Para obter o exemplo completo que inclui os métodos auxiliares, consulte [AccessDBProviderSample03](./accessdbprovidersample03.md)

Para obter mais informações sobre provedores do Windows PowerShell, consulte [visão geral do provedor do Windows PowerShell](./windows-powershell-provider-overview.md).

## <a name="implementing-item-methods"></a>Implementando métodos de item

A classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) expõe vários métodos que podem ser usados para acessar e manipular os itens em um armazenamento de dados. Para obter uma lista completa desses métodos, consulte [métodos do cmdletprovider](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods). Neste exemplo, implementaremos quatro desses métodos. [System. Management. Automation. Provider. createcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) Obtém um item em um caminho especificado. [System. Management. Automation. Provider. createcmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) define o valor do item especificado. [System. Management. Automation. Provider. @ cmdletprovider. itens existentes *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) verifica se um item existe no caminho especificado. [System. Management. Automation. Provider. createcmdletprovider. Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) verifica um caminho para ver se ele é mapeado para um local no armazenamento de dados.

> [!NOTE]
> Este tópico se baseia nas informações no guia de [início rápido do provedor do Windows PowerShell](./windows-powershell-provider-quickstart.md). Este tópico não aborda as noções básicas de como configurar um projeto de provedor ou como implementar os métodos herdados da classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) que criam e removem unidades.

### <a name="declaring-the-provider-class"></a>Declarando a classe do provedor

Declare o provedor para derivar da classe [System. Management. Automation. Provider. mycmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) e decorar-o com o [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a>Implementando GetItem

O [System. Management. Automation. Provider. @ cmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) é chamado pelo mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. getitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) em seu provedor. O método retorna o item no caminho especificado. No exemplo de banco de dados do Access, o método verifica se o item é a própria unidade, uma tabela no banco de dados ou uma linha no banco de dados. O método envia o item para o mecanismo do PowerShell chamando o método [System. Management. Automation. Provider. cmdletprovider. Writeitemobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .

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

### <a name="implementing-setitem"></a>Implementando SetItem

O método [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) é chamado pelas chamadas do mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. setitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) . Ele define o valor do item no caminho especificado.

No exemplo de banco de dados do Access, faz sentido definir o valor de um item somente se esse item for uma linha, portanto, o método gera [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) quando o item não é uma linha.

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

### <a name="implementing-itemexists"></a>Implementando os presentes

O método [System. Management. Automation. Provider. docmdletprovider. myexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) é chamado pelo mecanismo do PowerShell quando um usuário chama o cmdlet [Microsoft. PowerShell. Commands. TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) . O método determina se há um item no caminho especificado. Se o item existir, o método o passará de volta para o mecanismo do PowerShell chamando [System. Management. Automation. Provider. cmdletprovider. Writeitemobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).

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

### <a name="implementing-isvalidpath"></a>Implementando IsValidPath

O método [System. Management. Automation. Provider. docmdletprovider. Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) verifica se o caminho especificado é sintaticamente válido para o provedor atual. Ele não verifica se existe um item no caminho.

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

## <a name="next-steps"></a>Próximas etapas

Um provedor típico do mundo real é capaz de dar suporte a itens que contêm outros itens e de mover itens de um caminho para outro dentro da unidade. Para obter um exemplo de um provedor que dá suporte a contêineres, consulte [escrevendo um provedor de contêiner](./writing-a-container-provider.md). Para obter um exemplo de um provedor que dá suporte à movimentação de itens, consulte [escrevendo um provedor de navegação](./writing-a-navigation-provider.md).

## <a name="see-also"></a>Consulte Também

[Gravando um provedor de contêiner](./writing-a-container-provider.md)

[Escrevendo um provedor de navegação](./writing-a-navigation-provider.md)

[Visão geral do provedor do Windows PowerShell](./windows-powershell-provider-overview.md)
