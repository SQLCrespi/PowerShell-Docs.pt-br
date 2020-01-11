---
title: Criando um provedor de contêiner do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], container provider
- container providers [PowerShell Programmer's Guide]
ms.assetid: a7926647-0d18-45b2-967e-b31f92004bc4
caps.latest.revision: 5
ms.openlocfilehash: 69e45de4220a234783d35a877116ad5a5e47d182
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870771"
---
# <a name="creating-a-windows-powershell-container-provider"></a>Criar um provedor de contêineres do Windows PowerShell

Este tópico descreve como criar um provedor do Windows PowerShell que pode funcionar em armazenamentos de dados de várias camadas. Para esse tipo de armazenamento de dados, o nível superior do repositório contém os itens raiz e cada nível subsequente é referido como um nó de itens filho. Ao permitir que o usuário trabalhe nesses nós filho, um usuário pode interagir hierarquicamente por meio do armazenamento de dados.

Provedores que podem trabalhar em repositórios de dados de vários níveis são chamados de provedores de contêiner do Windows PowerShell. No entanto, lembre-se de que um provedor de contêiner do Windows PowerShell pode ser usado somente quando há um contêiner (sem Contêineres aninhados) com itens. Se houver Contêineres aninhados, você deverá implementar um provedor de navegação do Windows PowerShell. Para obter mais informações sobre como implementar o provedor de navegação do Windows PowerShell, consulte [criando um provedor de navegação do Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

> [!NOTE]
> Você pode baixar o C# arquivo de origem (AccessDBSampleProvider04.cs) para este provedor usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório. Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

O provedor de contêiner do Windows PowerShell descrito aqui define o banco de dados como seu único contêiner, com as tabelas e linhas do banco de dados definidas como itens do contêiner.

> [!CAUTION]
> Lembre-se de que esse design pressupõe um banco de dados que tem um campo com a ID Name e que o tipo do campo é LongInteger.

## <a name="defining-a-windows-powershell-container-provider-class"></a>Definindo uma classe de provedor de contêiner do Windows PowerShell

Um provedor de contêiner do Windows PowerShell deve definir uma classe .NET que deriva da classe base [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Aqui está a definição de classe para o provedor de contêiner do Windows PowerShell descrito nesta seção.

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
public class AccessDBProvider : ContainerCmdletProvider
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L34-L35 "AccessDBProviderSample04.cs")]

Observe que nessa definição de classe, o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) inclui dois parâmetros. O primeiro parâmetro especifica um nome amigável para o provedor usado pelo Windows PowerShell. O segundo parâmetro especifica os recursos específicos do Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando. Para esse provedor, não há recursos específicos do Windows PowerShell adicionados.

## <a name="defining-base-functionality"></a>Definindo a funcionalidade base

Conforme descrito em [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md), a classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) deriva de várias outras classes que forneceram funcionalidade de provedor diferente. O provedor de contêiner do Windows PowerShell, portanto, precisa definir toda a funcionalidade fornecida por essas classes.

Para implementar a funcionalidade para adicionar informações de inicialização específicas da sessão e para liberar recursos que são usados pelo provedor, consulte [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
No entanto, a maioria dos provedores (incluindo o provedor descrito aqui) pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.

Para obter acesso ao armazenamento de dados, o provedor deve implementar os métodos da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Para manipular os itens de um armazenamento de dados, como obter, configurar e limpar itens, o provedor deve implementar os métodos fornecidos pela classe base [System. Management. Automation. Provider. @ cmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

## <a name="retrieving-child-items"></a>Recuperando itens filho

Para recuperar um item filho, o provedor de contêiner do Windows PowerShell deve substituir o método [System. Management. Automation. provedor. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) para dar suporte a chamadas do cmdlet `Get-ChildItem`. Esse método recupera itens filho do armazenamento de dados e os grava no pipeline como objetos. Se o parâmetro `recurse` do cmdlet for especificado, o método recuperará todos os filhos, independentemente do nível em que estão. Se o parâmetro `recurse` não for especificado, o método recuperará apenas um único nível de filhos.

Aqui está a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) para esse provedor. Observe que esse método recupera os itens filho em todas as tabelas de banco de dados quando o caminho indica o banco de dados do Access e recupera os itens filho das linhas dessa tabela, caso o caminho indique uma tabela.

```csharp
protected override void GetChildItems(string path, bool recurse)
{
    // If path represented is a drive then the children in the path are
    // tables. Hence all tables in the drive represented will have to be
    // returned
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table, path, true);

            // if the specified item exists and recurse has been set then
            // all child items within it have to be obtained as well
            if (ItemExists(path) && recurse)
            {
                GetChildItems(path + pathSeparator + table.Name, recurse);
            }
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get the table name, row number and type of path from the
        // path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Obtain all the rows within the table
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);
            WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
        }
        else
        {
            // In this case, the path specified is not valid
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L311-L362 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchilditems"></a>Coisas a serem lembradas sobre a implementação de GetChildItems

As condições a seguir podem se aplicar à implementação de [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- Ao definir a classe do provedor, um provedor de contêiner do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- A implementação desse método deve levar em conta qualquer forma de acesso ao item que pode tornar o item visível para o usuário. Por exemplo, se um usuário tiver acesso de gravação a um arquivo por meio do provedor FileSystem (fornecido pelo Windows PowerShell), mas não tiver acesso de leitura, o arquivo ainda existirá e [System. Management. Automation. Provider. @ cmdletprovider. itens existentes *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) retornará `true`. Sua implementação pode exigir a verificação de um item pai para ver se o filho pode ser enumerado.

- Ao gravar vários itens, o método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) pode levar algum tempo. Você pode criar seu provedor para gravar os itens usando o método [System. Management. Automation. Provider. cmdletprovider. Writeitemobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) um de cada vez. Usar essa técnica apresentará os itens para o usuário em um fluxo.

- Sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) é responsável por impedir a recursão infinita quando há links circulares e assim por diante. Uma exceção de encerramento apropriada deve ser lançada para refletir essa condição.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Get-ChildItem

Às vezes, o cmdlet `Get-ChildItem` que chama [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) . Esse método recupera parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `Get-ChildItem`.

Este provedor de contêiner do Windows PowerShell não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a>Recuperando nomes de item filho

Para recuperar os nomes dos itens filho, o provedor de contêiner do Windows PowerShell deve substituir o método [System. Management. Automation. provedor. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) para dar suporte a chamadas do cmdlet `Get-ChildItem` quando seu parâmetro `Name` for especificado. Esse método recupera os nomes dos itens filho para o caminho especificado ou os nomes de item filho para todos os contêineres se o parâmetro `returnAllContainers` do cmdlet for especificado. Um nome filho é a parte folha de um caminho. Por exemplo, o nome filho para o caminho c:\windows\system32\abc.dll é "ABC. dll". O nome filho do diretório c:\Windows\System32 é "System32".

Aqui está a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) para esse provedor. Observe que o método recupera nomes de tabela se o caminho especificado indicar o banco de dados do Access (unidade) e os números de linha se o caminho indicar uma tabela.

```csharp
protected override void GetChildNames(string path,
                            ReturnContainers returnContainers)
{
    // If the path represented is a drive, then the child items are
    // tables. get the names of all the tables in the drive.
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table.Name, path, true);
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get type, table name and row number from path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Get all the rows in the table and then write out the
            // row numbers.
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row.RowNumber, path, false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);

            WriteItemObject(row.RowNumber, path, false);
        }
        else
        {
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildNames
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L369-L411 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchildnames"></a>Coisas a serem lembradas sobre a implementação de getchildnames

As condições a seguir podem se aplicar à implementação de [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- Ao definir a classe do provedor, um provedor de contêiner do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

  > [!NOTE]
  > Uma exceção a essa regra ocorre quando o parâmetro `returnAllContainers` do cmdlet é especificado. Nesse caso, o método deve recuperar qualquer nome filho para um contêiner, mesmo que ele não corresponda aos valores de [System. Management. Automation. Provider. cmdletprovider. Filter *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter), [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)ou [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) Properties.

- Por padrão, as substituições desse método não devem recuperar nomes de objetos que geralmente são ocultados do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) seja especificada. Se o caminho especificado indicar um contêiner, a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) não será necessária.

- Sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) é responsável por impedir a recursão infinita quando há links circulares e assim por diante. Uma exceção de encerramento apropriada deve ser lançada para refletir essa condição.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a>Anexando parâmetros dinâmicos ao cmdlet Get-ChildItem (Name)

Às vezes, o cmdlet `Get-ChildItem` (com o parâmetro `Name`) requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) . Esse método recupera os parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `Get-ChildItem`.

Este provedor não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a>Renomeando itens

Para renomear um item, um provedor de contêiner do Windows PowerShell deve substituir o método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) para dar suporte a chamadas do cmdlet `Rename-Item`. Esse método altera o nome do item no caminho especificado para o novo nome fornecido. O novo nome deve sempre ser relativo ao item pai (contêiner).

Esse provedor não substitui o método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) . No entanto, a implementação padrão é a seguinte.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a>Coisas a serem lembradas sobre a implementação de RenameItem

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):

- Ao definir a classe do provedor, um provedor de contêiner do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- O método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) destina-se apenas à modificação do nome de um item e não para operações de movimentação.
  Sua implementação do método deve gravar um erro se o parâmetro `newName` contiver separadores de caminho ou pode fazer com que o item altere seu local pai.

- Por padrão, as substituições desse método não devem renomear objetos, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) seja especificada. Se o caminho especificado indicar um contêiner, a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) não será necessária.

- Sua implementação do método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Esse método é usado para confirmar a execução de uma operação quando uma alteração é feita no estado do sistema, por exemplo, renomeando arquivos.
  [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell levando em conta quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido.

  Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true`, o método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Esse método envia uma mensagem de confirmação ao usuário para permitir comentários adicionais a fim de dizer se a operação deve continuar. Um provedor deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema.

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Rename-Item

Às vezes, o cmdlet `Rename-Item` requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Renameitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) . Esse método recupera os parâmetros para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `Rename-Item`.

Este provedor de contêiner não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a>Criando novos itens

Para criar novos itens, um provedor de contêiner deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) para dar suporte a chamadas do cmdlet `New-Item`. Esse método cria um item de dados localizado no caminho especificado. O parâmetro `type` do cmdlet contém o tipo definido pelo provedor para o novo item. Por exemplo, o provedor FileSystem usa um parâmetro `type` com um valor de "File" ou "Directory". O parâmetro `newItemValue` do cmdlet especifica um valor específico do provedor para o novo item.

Aqui está a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) para esse provedor.

```csharp
protected override void NewItem( string path, string type, object newItemValue )
{
    // Create the new item here after
    // performing necessary validations
    //
    // WriteItemObject(newItemValue, path, false);

    // Example
    //
    // if (ShouldProcess(path, "new item"))
    // {
    //      // Create a new item and then call WriteObject
    //      WriteObject(newItemValue, path, false);
    // }

} // NewItem
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L939-L955 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-newitem"></a>Coisas a serem lembradas sobre a implementação de NewItem

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- O método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) deve executar uma comparação que não diferencia maiúsculas de minúsculas da cadeia de caracteres passada no parâmetro `type`.
  Ele também deve permitir correspondências menos ambíguas. Por exemplo, para os tipos "File" e "Directory", somente a primeira letra é necessária para ambiguidade. Se o parâmetro `type` indicar um tipo que seu provedor não pode criar, o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) deve escrever uma ArgumentException com uma mensagem indicando os tipos que o provedor pode criar.

- Para o parâmetro `newItemValue`, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) é recomendada para aceitar cadeias de caracteres no mínimo. Ele também deve aceitar o tipo de objeto recuperado pelo método [System. Management. Automation. Provider. docmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) para o mesmo caminho. O método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) pode usar o método [System. Management. Automation. LanguagePrimitives. ConvertTo *](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo) para converter tipos para o tipo desejado.

- Sua implementação do método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar true, o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema.

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet New-Item

Às vezes, o cmdlet `New-Item` requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Newitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) . Esse método recupera os parâmetros para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `New-Item`.

Este provedor não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a>Removendo itens

Para remover itens, o provedor do Windows PowerShell deve substituir o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) para dar suporte a chamadas do cmdlet `Remove-Item`. Esse método exclui um item do repositório de dados no caminho especificado. Se o parâmetro `recurse` do cmdlet `Remove-Item` for definido como `true`, o método removerá todos os itens filho, independentemente de seu nível. Se o parâmetro for definido como `false`, o método removerá apenas um único item no caminho especificado.

Este provedor não dá suporte à remoção de item. No entanto, o código a seguir é a implementação padrão de [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a>Coisas a serem lembradas sobre a implementação de RemoveItem

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- Ao definir a classe do provedor, um provedor de contêiner do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem remover objetos, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como true. Se o caminho especificado indicar um contêiner, a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) não será necessária.

- A implementação de [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) é responsável por impedir a recursão infinita quando há links circulares e assim por diante. Uma exceção de encerramento apropriada deve ser lançada para refletir essa condição.

- Sua implementação do método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true`, o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema.

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Remove-Item

Às vezes, o cmdlet `Remove-Item` requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Removeitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) para lidar com esses parâmetros. Esse método recupera os parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `Remove-Item`.

Este provedor de contêiner não implementa esse método. No entanto, o código a seguir é a implementação padrão de [System. Management. Automation. Provider. Containercmdletprovider. Removeitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a>Consultando itens filho

Para verificar se há itens filho no caminho especificado, o provedor de contêiner do Windows PowerShell deve substituir o método [System. Management. Automation. Provider. Containercmdletprovider. Haschilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) . Esse método retornará `true` se o item tiver filhos e `false` caso contrário. Para um caminho nulo ou vazio, o método considera que todos os itens no repositório de dados sejam filhos e retorna `true`.

Aqui está a substituição para o método [System. Management. Automation. Provider. Containercmdletprovider. Haschilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) . Se houver mais de duas partes de caminho criadas pelo método auxiliar ChunkPath, o método retornará `false`, já que apenas um contêiner de banco de dados e um contêiner de tabela são definidos. Para obter mais informações sobre esse método auxiliar, consulte o método ChunkPath é discutido na [criação de um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L1094-L1097 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-haschilditems"></a>Coisas a serem lembradas sobre a implementação de HasChildItems

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Containercmdletprovider. Haschilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):

- Se o provedor de contêiner expõe uma raiz que contém pontos de montagem interessantes, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. Haschilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) deve retornar `true` quando uma cadeia de caracteres nula ou vazia for passada para o caminho.

## <a name="copying-items"></a>Copiando itens

Para copiar itens, o provedor de contêiner deve implementar o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) para dar suporte a chamadas do cmdlet `Copy-Item`. Esse método copia um item de dados do local indicado pelo parâmetro `path` do cmdlet para o local indicado pelo parâmetro `copyPath`. Se o parâmetro `recurse` for especificado, o método copiará todos os subcontêineres. Se o parâmetro não for especificado, o método copiará apenas um único nível de itens.

Este provedor não implementa esse método. No entanto, o código a seguir é a implementação padrão de [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a>Coisas a serem lembradas sobre a implementação de CopyItem

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):

- Ao definir a classe do provedor, um provedor de contêiner do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem copiar objetos sobre objetos existentes, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Por exemplo, o provedor FileSystem não copiará c:\temp\abc.txt sobre um arquivo c:\abc.txt existente, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Se o caminho especificado no parâmetro `copyPath` existir e indicar um contêiner, a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) não será necessária. Nesse caso, [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) deve copiar o item indicado pelo parâmetro `path` para o contêiner indicado pelo parâmetro `copyPath` como um filho.

- Sua implementação de [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) é responsável por impedir a recursão infinita quando há links circulares e assim por diante. Uma exceção de encerramento apropriada deve ser lançada para refletir essa condição.

- Sua implementação do método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar true, o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema. Para obter mais informações sobre como chamar esses métodos, consulte [renomear itens](#renaming-items).

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Copy-Item

Às vezes, o cmdlet `Copy-Item` requer parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de contêiner do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Containercmdletprovider. Copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) para lidar com esses parâmetros. Esse método recupera os parâmetros para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet `Copy-Item`.

Este provedor não implementa esse método. No entanto, o código a seguir é a implementação padrão de [System. Management. Automation. Provider. Containercmdletprovider. Copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md).

## <a name="building-the-windows-powershell-provider"></a>Criando o provedor do Windows PowerShell

Consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Testando o provedor do Windows PowerShell

Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando. Lembre-se de que a saída de exemplo a seguir usa um banco de dados de acesso fictício.

1. Execute o cmdlet `Get-ChildItem` para recuperar a lista de itens filho de uma tabela Customers no banco de dados Access.

   ```powershell
   Get-ChildItem mydb:customers
   ```

   A saída a seguir aparece.

   ```output
   PSPath        : AccessDB::customers
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : True
   Data          : System.Data.DataRow
   Name          : Customers
   RowCount      : 91
   Columns       :
   ```

2. Execute o cmdlet `Get-ChildItem` novamente para recuperar os dados de uma tabela.

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   A saída a seguir aparece.

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. Agora, use o cmdlet `Get-Item` para recuperar os itens na linha 0 na tabela de dados.

   ```powershell
   Get-Item mydb:\customers\0
   ```

   A saída a seguir aparece.

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. Reutilize `Get-Item` para recuperar os dados para os itens na linha 0.

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   A saída a seguir aparece.

   ```output
   CustomerID   : 1234
   CompanyName  : Fabrikam
   ContactName  : Eric Gruber
   ContactTitle : President
   Address      : 4567 Main Street
   City         : Buffalo
   Region       : NY
   PostalCode   : 98052
   Country      : USA
   Phone        : (425) 555-0100
   Fax          : (425) 555-0101
   ```

5. Agora, use o cmdlet `New-Item` para adicionar uma linha a uma tabela existente. O parâmetro `Path` especifica o caminho completo para a linha e deve indicar um número de linha maior que o número existente de linhas na tabela. O parâmetro `Type` indica "Row" para especificar esse tipo de item a ser adicionado.
   Por fim, o parâmetro `Value` especifica uma lista delimitada por vírgulas de valores de coluna para a linha.

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. Verifique a exatidão da nova operação de item da seguinte maneira.

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   A saída a seguir aparece.

   ```output
   ID        : 3
   FirstName : Eric
   LastName  : Gruber
   Email     : ericgruber@fabrikam.com
   Title     : President
   Company   : Fabrikam
   WorkPhone : (425) 555-0100
   Address   : 4567 Main Street
   City      : Buffalo
   State     : NY
   Zip       : 98052
   Country   : USA
   ```

## <a name="see-also"></a>Veja também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Criando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Implementando um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md)

[Implementando um provedor de navegação do Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[SDK do Windows PowerShell](../windows-powershell-reference.md)

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)
