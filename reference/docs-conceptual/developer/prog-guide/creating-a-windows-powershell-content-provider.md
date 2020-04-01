---
title: Criar um provedor de conteúdo do Windows PowerShell
ms.date: 09/13/2016
ms.topic: article
ms.assetid: 3da88ff9-c4c7-4ace-aa24-0a29c8cfa060
ms.openlocfilehash: 149ddb5becf2e0237973e535323ddf8b03b86f24
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500833"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Criar um provedor de conteúdo do Windows PowerShell

Este tópico descreve como criar um provedor do Windows PowerShell que permite ao usuário manipular o conteúdo dos itens em um armazenamento de dados. Como consequência, um provedor que pode manipular o conteúdo dos itens é conhecido como um provedor de conteúdo do Windows PowerShell.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (AccessDBSampleProvider06.cs) para este provedor usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório. Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="define-the-windows-powershell-content-provider-class"></a>Definir a classe do provedor de conteúdo do Windows PowerShell

Um provedor de conteúdo do Windows PowerShell deve criar uma classe .NET que ofereça suporte à interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) . Aqui está a definição de classe para o provedor de item descrito nesta seção.

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

Observe que nessa definição de classe, o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) inclui dois parâmetros. O primeiro parâmetro especifica um nome amigável para o provedor usado pelo Windows PowerShell. O segundo parâmetro especifica os recursos específicos do Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando. Para esse provedor, não há nenhum recurso específico do Windows PowerShell adicionado.

## <a name="define-functionality-of-base-class"></a>Definir a funcionalidade da classe base

Conforme descrito em [criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md), a classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) deriva de várias outras classes que forneceram funcionalidade de provedor diferente. Portanto, um provedor de conteúdo do Windows PowerShell, em geral, define toda a funcionalidade fornecida por essas classes.

Para obter mais informações sobre como implementar a funcionalidade para adicionar informações de inicialização específicas da sessão e para liberar recursos que são usados pelo provedor, consulte [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
No entanto, a maioria dos provedores, incluindo o provedor descrito aqui, pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.

Para acessar o armazenamento de dados, o provedor deve implementar os métodos da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Para manipular os itens de um armazenamento de dados, como obter, configurar e limpar itens, o provedor deve implementar os métodos fornecidos pela classe base [System. Management. Automation. Provider. @ cmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

Para trabalhar em repositórios de dados de várias camadas, o provedor deve implementar os métodos fornecidos pela classe base [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

Para dar suporte a comandos recursivos, Contêineres aninhados e caminhos relativos, o provedor deve implementar a classe base [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Além disso, esse provedor de conteúdo do Windows PowerShell pode anexar a interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) à classe base [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) e, portanto, deve implementar os métodos fornecidos por essa classe. Para obter mais informações, consulte Implementando esses métodos, consulte [implementar um provedor de navegação do Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

## <a name="implementing-a-content-reader"></a>Implementando um leitor de conteúdo

Para ler o conteúdo de um item, um provedor deve implementar uma classe de leitor de conteúdo derivada de [System. Management. Automation. Provider. Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader).
O leitor de conteúdo para esse provedor permite o acesso ao conteúdo de uma linha em uma tabela de dados. A classe Content Reader define um método **Read** que recupera os dados da linha indicada e retorna uma lista que representa esses dados, um método de **busca** que move o leitor de conteúdo, um método **Close** que fecha o leitor de conteúdo e um método **Dispose** .

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241
"AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a>Implementando um gravador de conteúdo

Para gravar o conteúdo em um item, um provedor deve implementar uma classe de gravador de conteúdo derivada de [System. Management. Automation. Provider. Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter).
A classe de gravador de conteúdo define um método de **gravação** que grava o conteúdo de linha especificado, um método de **busca** que move o gravador de conteúdo, um método **Close** que fecha o gravador de conteúdo e um método **Dispose** .

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a>Recuperando o leitor de conteúdo

Para obter o conteúdo de um item, o provedor deve implementar o [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) para dar suporte ao cmdlet `Get-Content`. Esse método retorna o leitor de conteúdo para o item localizado no caminho especificado. O objeto leitor pode ser aberto para ler o conteúdo.

Aqui está a implementação de [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) para esse método para esse provedor.

```csharp
public IContentReader GetContentReader(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be obtained only for tables");
    }

    return new AccessDBContentReader(path, this);
} // GetContentReader
```

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1829-L1846 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>Coisas a serem lembradas sobre a implementação de GetContentReader

As condições a seguir podem se aplicar a uma implementação de [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):

- Ao definir a classe do provedor, um provedor de conteúdo do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) deve garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem recuperar um leitor para objetos ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false`.

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Get-Content

O cmdlet `Get-Content` pode exigir parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de conteúdo do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreaderdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) . Esse método recupera parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet.

Este provedor de contêiner do Windows PowerShell não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a>Recuperando o gravador de conteúdo

Para gravar o conteúdo em um item, o provedor deve implementar o [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) para dar suporte aos cmdlets `Set-Content` e `Add-Content`. Esse método retorna o gravador de conteúdo para o item localizado no caminho especificado.

Aqui está a implementação de [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) para esse método.

```csharp
public IContentWriter GetContentWriter(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be added only to tables");
    }

    return new AccessDBContentWriter(path, this);
}
```

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1863-L1880 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>Coisas a serem lembradas sobre a implementação de GetContentWriter

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):

- Ao definir a classe do provedor, um provedor de conteúdo do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) deve garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem recuperar um gravador para objetos ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false`.

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>Anexando parâmetros dinâmicos aos cmdlets Add-Content e Set-Content

Os cmdlets `Add-Content` e `Set-Content` podem exigir parâmetros dinâmicos adicionais que são adicionados a um tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de conteúdo do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) para lidar com esses parâmetros. Esse método recupera parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros aos cmdlets.

Este provedor de contêiner do Windows PowerShell não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a>Limpando conteúdo

Seu provedor de conteúdo implementa o método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) no suporte do cmdlet `Clear-Content`. Esse método remove o conteúdo do item no caminho especificado, mas deixa o item intacto.

Aqui está a implementação do método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) para esse provedor.

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a>Coisas a serem lembradas sobre a implementação de ClearContent

As condições a seguir podem se aplicar a uma implementação de [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):

- Ao definir a classe do provedor, um provedor de conteúdo do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) deve garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem limpar o conteúdo dos objetos que estão ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false`.

- Sua implementação do método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Esse método é usado para confirmar a execução de uma operação quando uma alteração é feita no armazenamento de dados, como limpar o conteúdo. O método [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell manipulando as configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido.

  Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true`, o método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Esse método envia uma mensagem ao usuário para permitir que os comentários verifiquem se a operação deve continuar. A chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) permite uma verificação adicional de modificações potencialmente perigosas do sistema.

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Clear-Content

O cmdlet `Clear-Content` pode exigir parâmetros dinâmicos adicionais que são adicionados no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de conteúdo do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Icontentcmdletprovider. Clearcontentdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) para lidar com esses parâmetros. Esse método recupera os parâmetros para o item no caminho indicado. Esse método recupera parâmetros dinâmicos para o item no caminho indicado e retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet.

Este provedor de contêiner do Windows PowerShell não implementa esse método. No entanto, o código a seguir é a implementação padrão desse método.

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](~/powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1819-L1822 "AccessDBProviderSample06.cs")]

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

Ao escrever um provedor, pode ser necessário adicionar membros a objetos existentes ou definir novos objetos. Quando isso é feito, você deve criar um arquivo de tipos que o Windows PowerShell pode usar para identificar os membros do objeto e um arquivo de formato que define como o objeto é exibido. Para obter mais informações, consulte [estendendo tipos de objeto e formatação](/previous-versions/ms714665(v=vs.85)).

## <a name="building-the-windows-powershell-provider"></a>Criando o provedor do Windows PowerShell

Consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Testando o provedor do Windows PowerShell

Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando. Por exemplo, teste o provedor de conteúdo de exemplo.

Use o cmdlet `Get-Content` para recuperar o conteúdo do item especificado na tabela de banco de dados no caminho especificado pelo parâmetro `Path`. O parâmetro `ReadCount` especifica o número de itens para o leitor de conteúdo definido a ser lido (padrão 1). Com a entrada de comando a seguir, o cmdlet recupera duas linhas (itens) da tabela e exibe seu conteúdo. Observe que a saída de exemplo a seguir usa um banco de dados de acesso fictício.

```powershell
Get-Content -Path mydb:\Customers -ReadCount 2
```

```Output
ID        : 1
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
ID        : 2
FirstName : Eva
LastName  : Corets
Email     : evacorets@cohowinery.com
Title     : Sales Representative
Company   : Coho Winery
WorkPhone : (360) 555-0100
Address   : 8910 Main Street
City      : Cabmerlot
State     : WA
Zip       : 98089
Country   : USA
```

## <a name="see-also"></a>Consulte Também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Implementar um provedor de navegação do Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[SDK do Windows PowerShell](../windows-powershell-reference.md)

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)
