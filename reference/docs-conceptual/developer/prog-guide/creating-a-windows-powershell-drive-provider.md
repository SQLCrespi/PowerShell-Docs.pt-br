---
title: Criando um provedor de unidade do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.openlocfilehash: 2a2178714ed548986fe1a1a4de8828e8e0a938cb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787182"
---
# <a name="creating-a-windows-powershell-drive-provider"></a>Criar um provedor de unidade do Windows PowerShell

Este tópico descreve como criar um provedor de unidade do Windows PowerShell que fornece uma maneira de acessar um armazenamento de dados por meio de uma unidade do Windows PowerShell. Esse tipo de provedor também é conhecido como provedores de unidade do Windows PowerShell. As unidades do Windows PowerShell usadas pelo provedor fornecem os meios para se conectar ao armazenamento de dados.

O provedor da unidade do Windows PowerShell descrito aqui fornece acesso a um banco de dados do Microsoft Access.
Para esse provedor, a unidade do Windows PowerShell representa o banco de dados (é possível adicionar qualquer número de unidades a um provedor de unidade), os contêineres de nível superior da unidade representam as tabelas no banco de dados e os itens dos contêineres representam as linhas nas tabelas.

## <a name="defining-the-windows-powershell-provider-class"></a>Definindo a classe do provedor do Windows PowerShell

O provedor de unidade deve definir uma classe .NET que deriva da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Aqui está a definição de classe para este provedor de unidade:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="29-30":::

Observe que, neste exemplo, o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) especifica um nome amigável para o provedor e os recursos específicos do Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando.
Os valores possíveis para os recursos do provedor são definidos pela enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Este provedor de unidade não oferece suporte a nenhum desses recursos.

## <a name="defining-base-functionality"></a>Definindo a funcionalidade base

Conforme descrito em [criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md), a classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) deriva da classe base [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) que define os métodos necessários para inicializar e cancelar a inicialização do provedor. Para implementar a funcionalidade para adicionar informações de inicialização específicas da sessão e para liberar recursos que são usados pelo provedor, consulte [criando um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
No entanto, a maioria dos provedores (incluindo o provedor descrito aqui) pode usar a implementação padrão dessa funcionalidade fornecida pelo Windows PowerShell.

## <a name="creating-drive-state-information"></a>Criando informações de estado da unidade

Todos os provedores do Windows PowerShell são considerados sem monitoração de estado, o que significa que o seu provedor de unidade precisa criar qualquer informação de estado necessária para o tempo de execução do Windows PowerShell quando ele chama seu provedor.

Para este provedor de unidade, as informações de estado incluem a conexão com o banco de dados que é mantido como parte das informações da unidade. Aqui está o código que mostra como essas informações são armazenadas no objeto [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) que descreve a unidade:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="130-151":::

## <a name="creating-a-drive"></a>Criando uma unidade

Para permitir que o tempo de execução do Windows PowerShell crie uma unidade, o provedor de unidade deve implementar o método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) . O código a seguir mostra a implementação do método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) para este provedor de unidade:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="42-84":::

A substituição desse método deve fazer o seguinte:

- Verifique se o [System.Management.Automation.PSDriveinfo. O membro raiz *](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) existe e pode ser feita uma conexão com o armazenamento de dados.
- Crie uma unidade e preencha o membro de conexão, em suporte ao `New-PSDrive` cmdlet.
- Valide o [System.Management.Automation.PSDobjeto riveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) para a unidade proposta.
- Modifique o objeto [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) que descreve a unidade com qualquer informação de desempenho ou confiabilidade necessária ou forneça dados adicionais para os chamadores usando a unidade.
- Lide com falhas usando o método [System. Management. Automation. Provider. cmdletprovider. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) e, em seguida, Return `null` .

  Esse método retorna as informações da unidade que foram passadas para o método ou uma versão específica do provedor.

## <a name="attaching-dynamic-parameters-to-newdrive"></a>Anexando parâmetros dinâmicos a NewDrive

O `New-PSDrive` cmdlet com suporte pelo seu provedor de unidade pode exigir parâmetros adicionais. Para anexar esses parâmetros dinâmicos ao cmdlet, o provedor implementa o método [System. Management. Automation. Provider. Drivecmdletprovider. Newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) . Esse método retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Este provedor de unidade não substitui esse método. No entanto, o código a seguir mostra a implementação padrão desse método:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a>Removendo uma unidade

Para fechar a conexão de banco de dados, o provedor da unidade deve implementar o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) . Esse método fecha a conexão com a unidade depois de limpar qualquer informação específica do provedor.

O código a seguir mostra a implementação do método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para este provedor de unidade:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="91-116":::

Se a unidade puder ser removida, o método deverá retornar as informações passadas para o método por meio do `drive` parâmetro. Se a unidade não puder ser removida, o método deverá gravar uma exceção e, em seguida, retornar `null` . Se o seu provedor não substituir esse método, a implementação padrão desse método retornará apenas as informações da unidade passadas como entrada.

## <a name="initializing-default-drives"></a>Inicializando unidades padrão

O provedor de unidade implementa o método [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) para montar unidades. Por exemplo, o provedor de Active Directory pode montar uma unidade para o contexto de nomenclatura padrão se o computador for ingressado em um domínio.

Esse método retorna uma coleção de informações de unidade sobre as unidades inicializadas ou uma coleção vazia. A chamada para esse método é feita depois que o tempo de execução do Windows PowerShell chama o método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) para inicializar o provedor.

Este provedor de unidade não substitui o método [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) . No entanto, o código a seguir mostra a implementação padrão, que retorna uma coleção de unidades vazia:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a>Coisas a serem lembradas sobre a implementação de InitializeDefaultDrives

Todos os provedores de unidade devem montar uma unidade raiz para ajudar o usuário com a capacidade de descoberta. A unidade raiz pode listar locais que servem como raízes para outras unidades montadas. Por exemplo, o provedor de Active Directory pode criar uma unidade que lista os contextos de nomenclatura encontrados nos `namingContext` atributos no DSE (ambiente de sistema distribuído) raiz. Isso ajuda os usuários a descobrir pontos de montagem para outras unidades.

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).

## <a name="testing-the-windows-powershell-drive-provider"></a>Testando o provedor de unidade do Windows PowerShell

Quando o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando, incluindo todos os cmdlets disponibilizados pela derivação. Vamos testar o provedor de unidade de exemplo.

1. Execute o `Get-PSProvider` cmdlet para recuperar a lista de provedores para garantir que o provedor da unidade AccessDB esteja presente:

   **> PS`Get-PSProvider`**

   O seguinte resultado é exibido:

   ```Output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. Certifique-se de que existe um nome de servidor de banco de dados (DSN) para o banco de dado, acessando a parte de **fontes de dados** das **Ferramentas administrativas** do sistema operacional. Na tabela **DSN de usuário** , clique duas vezes em **banco de dados do MS Access** e adicione o caminho da unidade `C:\ps\northwind.mdb` .

3. Crie uma nova unidade usando o provedor de unidade de exemplo:

   ```powershell
   new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb`
   ```

   O seguinte resultado é exibido:

   ```Output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. Valide a conexão. Como a conexão é definida como um membro da unidade, você pode verificá-la usando o cmdlet Get-PDDrive.

   > [!NOTE]
   > O usuário ainda não pode interagir com o provedor como uma unidade, pois o provedor precisa de funcionalidade de contêiner para essa interação. Para obter mais informações, consulte [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

   **PS> (Get-PSDrive MyDB). Connection**

   O seguinte resultado é exibido:

   ```Output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. Remova a unidade e saia do Shell:

   ```powershell
   PS> remove-psdrive mydb
   PS> exit
   ```

## <a name="see-also"></a>Consulte Também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Criar um provedor básico do Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)
