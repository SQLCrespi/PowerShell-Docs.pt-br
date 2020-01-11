---
title: Criar um provedor de navegação do Windows PowerShell
ms.date: 09/13/2016
ms.topic: article
ms.assetid: 8bd3224d-ca6f-4640-9464-cb4d9f4e13b1
ms.openlocfilehash: 96a9167019c047bb9c6e56362b2c1110ece553dd
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870686"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>Criar um provedor de navegação do Windows PowerShell

Este tópico descreve como criar um provedor de navegação do Windows PowerShell que pode navegar pelo armazenamento de dados. Esse tipo de provedor dá suporte a comandos recursivos, Contêineres aninhados e caminhos relativos.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (AccessDBSampleProvider05.cs) para este provedor usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Os arquivos de origem baixados estão disponíveis no **\<exemplos do PowerShell >** diretório. Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

O provedor descrito aqui permite que o usuário manipule um banco de dados do Access como uma unidade para que o usuário possa navegar até as tabelas de data no banco de dado. Ao criar seu próprio provedor de navegação, você pode implementar métodos que podem tornar os caminhos qualificados da unidade necessários para navegação, normalizar caminhos relativos, mover itens do armazenamento de dados, bem como métodos que obtêm nomes filho, obter o caminho pai de um item e testar para identificar se um item é um contêiner.

> [!CAUTION]
> Lembre-se de que esse design pressupõe um banco de dados que tem um campo com a ID Name e que o tipo do campo é LongInteger.

## <a name="define-the-windows-powershell-provider"></a>Definir o provedor do Windows PowerShell

Um provedor de navegação do Windows PowerShell deve criar uma classe .NET que deriva da classe base [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Aqui está a definição de classe para o provedor de navegação descrito nesta seção.

[!code-csharp[AccessDBProviderSample05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L31-L32
"AccessDBProviderSample05.cs")]

Observe que, nesse provedor, o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) inclui dois parâmetros. O primeiro parâmetro especifica um nome amigável para o provedor usado pelo Windows PowerShell. O segundo parâmetro especifica os recursos específicos do Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando. Para esse provedor, não há recursos específicos do Windows PowerShell adicionados.

## <a name="defining-base-functionality"></a>Definindo a funcionalidade base

Conforme descrito em [criar seu provedor de PS](./designing-your-windows-powershell-provider.md), a classe base [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) deriva de várias outras classes que forneceram funcionalidade de provedor diferente. Um provedor de navegação do Windows PowerShell, portanto, deve definir toda a funcionalidade fornecida por essas classes.

Para implementar a funcionalidade para adicionar informações de inicialização específicas da sessão e para liberar recursos que são usados pelo provedor, consulte [criando um provedor básico do PS](./creating-a-basic-windows-powershell-provider.md). No entanto, a maioria dos provedores (incluindo o provedor descrito aqui) pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.

Para obter acesso ao armazenamento de dados por meio de uma unidade do Windows PowerShell, você deve implementar os métodos da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de unidade do Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Para manipular os itens de um armazenamento de dados, como obter, configurar e limpar itens, o provedor deve implementar os métodos fornecidos pela classe base [System. Management. Automation. Provider. @ cmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de item do Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

Para obter os itens filho, ou seus nomes, do armazenamento de dados, bem como métodos que criam, copiam, renomeam e removem itens, você deve implementar os métodos fornecidos pela classe base [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Para obter mais informações sobre como implementar esses métodos, consulte [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

## <a name="creating-a-windows-powershell-path"></a>Criando um caminho do Windows PowerShell

Provedor de navegação do Windows PowerShell use um caminho interno de provedor do Windows PowerShell para navegar pelos itens do armazenamento de dados. Para criar um caminho interno do provedor, o provedor deve implementar o método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) para dar suporte a chamadas do cmdlet Combine-Path. Esse método combina um caminho pai e filho em um caminho interno de provedor, usando um separador de caminho específico de provedor entre os caminhos pai e filho.

A implementação padrão usa caminhos com "/" ou "\\" como o separador de caminho, normaliza o separador de caminho para "\\", combina as partes do caminho pai e filho com o separador entre elas e, em seguida, retorna uma cadeia de caracteres que contém os caminhos combinados.

Este provedor de navegação não implementa esse método. No entanto, o código a seguir é a implementação padrão do método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) .

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>Coisas a serem lembradas sobre a implementação de MakePath

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):

- Sua implementação do método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) não deve validar o caminho como um caminho válido totalmente qualificado no namespace do provedor. Lembre-se de que cada parâmetro pode representar apenas uma parte de um caminho, e as partes combinadas podem não gerar um caminho totalmente qualificado. Por exemplo, o método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) para o provedor FileSystem pode receber "Windows\System32" no parâmetro `parent` e "ABC. dll" no parâmetro `child`. O método une esses valores com o separador "\\" e retorna "windows\system32\abc.dll", que não é um caminho de sistema de arquivos totalmente qualificado.

  > [!IMPORTANT]
  > As partes de caminho fornecidas na chamada para [System. Management. Automation. Provider. Navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) podem conter caracteres não permitidos no namespace do provedor. Esses caracteres provavelmente são usados para a expansão de curingas e a implementação desse método não deve removê-los.

## <a name="retrieving-the-parent-path"></a>Recuperando o caminho pai

Os provedores de navegação do Windows PowerShell implementam o método [System. Management. Automation. Provider. Navigationcmdletprovider. GetParentPath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) para recuperar a parte pai do caminho específico do provedor, completo ou parcial indicado. O método remove a parte filho do caminho e retorna a parte do caminho pai. O parâmetro `root` especifica o caminho totalmente qualificado para a raiz de uma unidade. Esse parâmetro pode ser nulo ou vazio se uma unidade montada não estiver em uso para a operação de recuperação. Se uma raiz for especificada, o método deverá retornar um caminho para um contêiner na mesma árvore que a raiz.

O provedor de navegação de exemplo não substitui esse método, mas usa a implementação padrão.
Ele aceita caminhos que usam "/" e "\\" como separadores de caminho. Primeiro, ele normaliza o caminho para ter apenas separadores "\\" e, em seguida, divide o caminho pai no último "\\" e retorna o caminho pai.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>Para se lembrar de implementar GetParentPath

Sua implementação do método [System. Management. Automation. Provider. Navigationcmdletprovider. GetParentPath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) deve dividir o caminho lexicalmente no separador de caminho para o namespace do provedor. Por exemplo, o provedor FileSystem usa esse método para procurar o último "\\" e retorna tudo à esquerda do separador.

## <a name="retrieve-the-child-path-name"></a>Recuperar o nome do caminho filho

Seu provedor de navegação implementa o método [System. Management. Automation. Provider. Navigationcmdletprovider. getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) para recuperar o nome (elemento folha) do filho do item localizado no caminho específico do provedor, completo ou parcial indicado.

O provedor de navegação de exemplo não substitui esse método. A implementação padrão é mostrada abaixo. Ele aceita caminhos que usam "/" e "\\" como separadores de caminho. Primeiro, ele normaliza o caminho para ter apenas separadores "\\" e, em seguida, divide o caminho pai no último "\\" e retorna o nome da parte do caminho filho.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>Coisas a serem lembradas sobre a implementação de getchildname

Sua implementação do método [System. Management. Automation. Provider. Navigationcmdletprovider. getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) deve dividir o caminho lexicalmente no separador de caminho. Se o caminho fornecido não contiver separadores de caminho, o método deverá retornar o caminho inalterado.

> [!IMPORTANT]
> O caminho fornecido na chamada para esse método pode conter caracteres ilegais no namespace do provedor. Esses caracteres são mais prováveis para a expansão de curingas ou a correspondência de expressão regular, e a implementação desse método não deve removê-los.

## <a name="determining-if-an-item-is-a-container"></a>Determinando se um item é um contêiner

O provedor de navegação pode implementar o método [System. Management. Automation. Provider. Navigationcmdletprovider. IsItemContainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) para determinar se o caminho especificado indica um contêiner. Retornará true se o caminho representar um contêiner; caso contrário, false. O usuário precisa desse método para poder usar o cmdlet `Test-Path` para o caminho fornecido.

O código a seguir mostra a implementação de [System. Management. Automation. Provider. Navigationcmdletprovider. IsItemContainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) em nosso provedor de navegação de exemplo. O método verifica se o caminho especificado está correto e se a tabela existe e retorna true se o caminho indica um contêiner.

[!code-csharp[AccessDBProviderSample05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L847-L872 "AccessDBProviderSample05.cs")]

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>Coisas a serem lembradas sobre a implementação de IsItemContainer

Sua classe .NET do provedor de navegação pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesse caso, a implementação de [System. Management. Automation. Provider. Navigationcmdletprovider. IsItemContainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) precisa garantir que o caminho passado atenda aos requisitos. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, a propriedade [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .

## <a name="moving-an-item"></a>Movendo um item

Para dar suporte ao cmdlet `Move-Item`, seu provedor de navegação implementa o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) . Esse método move o item especificado pelo parâmetro `path` para o contêiner no caminho fornecido no parâmetro `destination`.

O provedor de navegação de exemplo não substitui o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) . A seguir está a implementação padrão.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>Coisas a serem lembradas sobre a implementação de MoveItem

Sua classe .NET do provedor de navegação pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesse caso, a implementação de [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) deve garantir que o caminho passado atenda aos requisitos. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, a propriedade **cmdletprovider. Exclude** .

Por padrão, as substituições desse método não devem mover objetos sobre objetos existentes, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Por exemplo, o provedor FileSystem não copiará c:\temp\abc.txt sobre um arquivo c:\bar.txt existente, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) esteja definida como `true`. Se o caminho especificado no parâmetro `destination` existir e for um contêiner, a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) não será necessária. Nesse caso, [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) deve mover o item indicado pelo parâmetro `path` para o contêiner indicado pelo parâmetro `destination` como um filho.

Sua implementação do método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Esse método é usado para confirmar a execução de uma operação quando uma alteração é feita no estado do sistema, por exemplo, excluir arquivos.
[System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell levando em conta quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido ao usuário.

Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true`, o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Esse método envia uma mensagem ao usuário para permitir comentários a fim de dizer se a operação deve continuar. Seu provedor deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) como uma verificação adicional para modificações potencialmente perigosas do sistema.

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Move-Item

Às vezes, o cmdlet `Move-Item` requer parâmetros adicionais que são fornecidos dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de navegação deve implementar o método [System. Management. Automation. Provider. Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) para obter os valores de parâmetro necessários do item no caminho indicado e retornar um objeto que tenha propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou a um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Este provedor de navegação não implementa esse método. No entanto, o código a seguir é a implementação padrão de [System. Management. Automation. Provider. Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>Normalizando um caminho relativo

Seu provedor de navegação implementa o método [System. Management. Automation. Provider. Navigationcmdletprovider. Normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) para normalizar o caminho totalmente qualificado indicado no parâmetro `path` como sendo relativo ao caminho especificado pelo parâmetro `basePath`. O método retorna uma representação de cadeia de caracteres do caminho normalizado. Ele gravará um erro se o parâmetro `path` especificar um caminho inexistente.

O provedor de navegação de exemplo não substitui esse método. A seguir está a implementação padrão.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>Coisas a serem lembradas sobre a implementação de NormalizeRelativePath

Sua implementação de [System. Management. Automation. Provider. Navigationcmdletprovider. Normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) deve analisar o parâmetro `path`, mas não precisa usar uma análise puramente sintática. Você é incentivado a criar esse método para usar o caminho para pesquisar as informações de caminho no repositório de dados e criar um caminho que corresponda à sintaxe de caminho padronizado e com maiúsculas e minúsculas.

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

É possível que um provedor adicione membros a objetos existentes ou defina novos objetos. Para obter mais informações, consulte[estendendo tipos de objeto e formatação](/previous-versions/ms714665(v=vs.85)).

## <a name="building-the-windows-powershell-provider"></a>Criando o provedor do Windows PowerShell

Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Testando o provedor do Windows PowerShell

Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando, incluindo os cmdlets disponibilizados pela derivação. Este exemplo testará o provedor de navegação de exemplo.

1. Execute o novo shell e use o cmdlet `Set-Location` para definir o caminho para indicar o banco de dados do Access.

   ```powershell
   Set-Location mydb:
   ```

2. Agora execute o cmdlet `Get-Childitem` para recuperar uma lista de itens de banco de dados, que são as tabelas de banco de dados disponíveis. Para cada tabela, esse cmdlet também recupera o número de linhas da tabela.

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```Output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. Use o cmdlet `Set-Location` novamente para definir o local da tabela de dados Employees.

   ```powershell
   Set-Location Employees
   ```

4. Agora, vamos usar o cmdlet `Get-Location` para recuperar o caminho para a tabela Employees.

   ```powershell
   Get-Location
   ```

   ```Output
   Path
   ----
   mydb:\Employees
   ```

5. Agora, use o cmdlet `Get-Childitem` canalizado para o cmdlet `Format-Table`. Esse conjunto de cmdlets recupera os itens da tabela de dados Employees, que são as linhas da tabela. Eles são formatados conforme especificado pelo cmdlet `Format-Table`.

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```Output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. Agora você pode executar o cmdlet `Get-Item` para recuperar os itens para a linha 0 da tabela de dados Employees.

   ```powershell
   Get-Item 0
   ```

   ```Output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. Use o cmdlet `Get-Item` novamente para recuperar os dados do funcionário para os itens na linha 0.

   ```powershell
   (Get-Item 0).data
   ```

   ```Output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a>Veja também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Estendendo tipos de objeto e formatação](/previous-versions/ms714665(v=vs.85))

[Implementar um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md)

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions/ms714644(v=vs.85))

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
