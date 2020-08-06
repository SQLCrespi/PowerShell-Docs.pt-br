---
title: Criando um provedor básico do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- base provider [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], base provider
ms.openlocfilehash: 16cadb6099bb4f315bacda4aea617b89f9af5626
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787216"
---
# <a name="creating-a-basic-windows-powershell-provider"></a>Criar um provedor básico do Windows PowerShell

Este tópico é o ponto de partida para aprender a criar um provedor do Windows PowerShell. O provedor básico descrito aqui fornece métodos para iniciar e interromper o provedor e, embora esse provedor não forneça um meio para acessar um armazenamento de dados ou obter ou definir os dados no repositório de dados, ele fornece a funcionalidade básica exigida por todos os provedores.

Conforme mencionado anteriormente, o provedor básico descrito aqui implementa métodos para iniciar e parar o provedor. O tempo de execução do Windows PowerShell chama esses métodos para inicializar e cancelar a inicialização do provedor.

> [!NOTE]
> Você pode encontrar um exemplo desse provedor no arquivo AccessDBSampleProvider01.cs fornecido pelo Windows PowerShell.

## <a name="defining-the-windows-powershell-provider-class"></a>Definindo a classe do provedor do Windows PowerShell

A primeira etapa na criação de um provedor do Windows PowerShell é definir sua classe .NET. Esse provedor básico define uma classe chamada `AccessDBProvider` derivada da classe base [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .

É recomendável que você coloque suas classes de provedor em um `Providers` namespace do seu namespace de API, por exemplo, XXX. PowerShell. Providers. Esse provedor usa o `Microsoft.Samples.PowerShell.Provider` namespace, no qual todos os exemplos de provedor do Windows PowerShell são executados.

> [!NOTE]
> A classe para um provedor do Windows PowerShell deve ser explicitamente marcada como pública. As classes não marcadas como públicas usarão como padrão o interno e não serão encontradas pelo tempo de execução do Windows PowerShell.

Aqui está a definição de classe para este provedor básico:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="23-24":::

Logo antes da definição de classe, você deve declarar o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) com a sintaxe [cmdletprovider ()].

Você pode definir palavras-chave de atributo para declarar ainda mais a classe, se necessário. Observe que o atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) declarado aqui inclui dois parâmetros. O primeiro parâmetro de atributo especifica o nome amigável padrão para o provedor, que o usuário pode modificar mais tarde. O segundo parâmetro especifica os recursos definidos pelo Windows PowerShell que o provedor expõe para o tempo de execução do Windows PowerShell durante o processamento do comando. Os valores possíveis para os recursos do provedor são definidos pela enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Como esse é um provedor base, ele não oferece suporte a recursos.

> [!NOTE]
> O nome totalmente qualificado do provedor do Windows PowerShell inclui o nome do assembly e outros atributos determinados pelo Windows PowerShell após o registro do provedor.

## <a name="defining-provider-specific-state-information"></a>Definindo informações de estado específicas do provedor

A classe base [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) e todas as classes derivadas são consideradas sem estado porque o tempo de execução do Windows PowerShell cria instâncias de provedor somente conforme necessário. Portanto, se seu provedor exigir controle total e manutenção de estado para dados específicos do provedor, ele deverá derivar uma classe da classe [System. Management. Automation. providerInfo](/dotnet/api/System.Management.Automation.ProviderInfo) . Sua classe derivada deve definir os membros necessários para manter o estado de forma que os dados específicos do provedor possam ser acessados quando o tempo de execução do Windows PowerShell chama o método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) para inicializar o provedor.

Um provedor do Windows PowerShell também pode manter o estado baseado em conexão. Para obter mais informações sobre como manter o estado de conexão, consulte [criando um provedor de unidade do PowerShell](./creating-a-windows-powershell-drive-provider.md).

## <a name="initializing-the-provider"></a>Inicializando o provedor

Para inicializar o provedor, o tempo de execução do Windows PowerShell chama o método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) quando o Windows PowerShell é iniciado. Para a maior parte, seu provedor pode usar a implementação padrão desse método, que simplesmente retorna o objeto [System. Management. Automation. providerInfo](/dotnet/api/System.Management.Automation.ProviderInfo) que descreve seu provedor. No entanto, no caso em que você deseja adicionar informações de inicialização adicionais, você deve implementar seu próprio método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) que retorna uma versão modificada do objeto [System. Management. Automation. providerInfo](/dotnet/api/System.Management.Automation.ProviderInfo) que é passado para seu provedor. Em geral, esse método deve retornar o objeto [System. Management. Automation. providerInfo](/dotnet/api/System.Management.Automation.ProviderInfo) fornecido passado a ele ou um objeto [System. Management. Automation. providerInfo](/dotnet/api/System.Management.Automation.ProviderInfo) modificado que contém outras informações de inicialização.

Este provedor básico não substitui esse método. No entanto, o código a seguir mostra a implementação padrão desse método:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

O provedor pode manter o estado das informações específicas do provedor, conforme descrito em [definindo o estado de dados específicos do provedor](#defining-provider-specific-state-information). Nesse caso, sua implementação deve substituir o método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) para retornar uma instância da classe derivada.

## <a name="start-dynamic-parameters"></a>Iniciar parâmetros dinâmicos

A implementação do provedor do método [System. Management. Automation. Provider. cmdletprovider. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) pode exigir parâmetros adicionais. Nesse caso, o provedor deve substituir o método [System. Management. Automation. Provider. cmdletprovider. Startdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) e retornar um objeto que tenha propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou a um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Este provedor básico não substitui esse método. No entanto, o código a seguir mostra a implementação padrão desse método:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a>Cancelando a inicialização do provedor

Para liberar recursos que o provedor do Windows PowerShell usa, seu provedor deve implementar seu próprio método [System. Management. Automation. Provider. cmdletprovider. Stop *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) . Esse método é chamado pelo tempo de execução do Windows PowerShell para cancelar a inicialização do provedor no fechamento de uma sessão.

Este provedor básico não substitui esse método. No entanto, o código a seguir mostra a implementação padrão desse método:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a>Exemplo de código

Para obter o código de exemplo completo, consulte [exemplo de código AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md).

## <a name="testing-the-windows-powershell-provider"></a>Testando o provedor do Windows PowerShell

Depois que o provedor do Windows PowerShell tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando os cmdlets com suporte na linha de comando. Para este provedor básico, execute o novo shell e use o `Get-PSProvider` cmdlet para recuperar a lista de provedores e verifique se o provedor AccessDb está presente.

```powershell
Get-PSProvider
```

O seguinte resultado é exibido:

```Output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a>Consulte Também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Projetar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)
