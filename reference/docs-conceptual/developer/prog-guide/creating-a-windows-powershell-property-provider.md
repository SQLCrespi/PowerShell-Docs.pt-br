---
ms.date: 09/13/2016
ms.topic: reference
title: Criar um provedor de propriedade do Windows PowerShell
description: Criar um provedor de propriedade do Windows PowerShell
ms.openlocfilehash: 5370624afa784598ca784b201f7e7345eb958ff9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390908"
---
# <a name="creating-a-windows-powershell-property-provider"></a>Criar um provedor de propriedade do Windows PowerShell

Este tópico descreve como criar um provedor que permite ao usuário manipular as propriedades de itens em um armazenamento de dados. Como consequência, esse tipo de provedor é conhecido como um provedor de propriedades do Windows PowerShell. Por exemplo, o provedor de registro fornecido pelo Windows PowerShell manipula valores de chave do registro como propriedades do item de chave do registro. Esse tipo de provedor deve adicionar a interface [System. Management. Automation. Provider. Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) à implementação da classe .net.

> [!NOTE]
> O Windows PowerShell fornece um arquivo de modelo que você pode usar para desenvolver um provedor do Windows PowerShell. O arquivo TemplateProvider.cs está disponível no Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução 3,0. Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> O modelo baixado está disponível no **\<PowerShell Samples>** diretório. Você deve fazer uma cópia desse arquivo e usar a cópia para criar um novo provedor do Windows PowerShell, removendo qualquer funcionalidade que não seja necessária. Para obter mais informações sobre outras implementações de provedor do Windows PowerShell, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

> [!CAUTION]
> Os métodos do seu provedor de propriedades devem gravar quaisquer objetos usando o método [System. Management. Automation. Provider. cmdletprovider. Writepropertyobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WritePropertyObject) .

## <a name="defining-the-windows-powershell-provider"></a>Definindo o provedor do Windows PowerShell

Um provedor de propriedades deve criar uma classe .NET que ofereça suporte à interface [System. Management. Automation. Provider. Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) . Aqui está a declaração de classe padrão do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration](Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration)]  -->

## <a name="defining-base-functionality"></a>Definindo a funcionalidade base

A interface [System. Management. Automation. Provider. Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) pode ser anexada a qualquer uma das classes base do provedor, com exceção da classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Adicione a funcionalidade base exigida pela classe base que você está usando. Para obter mais informações sobre classes base, consulte [projetando seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="retrieving-properties"></a>Recuperando propriedades

Para recuperar propriedades, o provedor deve implementar o método [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) para dar suporte a chamadas do `Get-ItemProperty` cmdlet. Esse método recupera as propriedades do item localizado no caminho interno do provedor especificado (totalmente qualificado).

O `providerSpecificPickList` parâmetro indica quais propriedades recuperar. Se esse parâmetro for `null` ou vazio, o método deverá recuperar todas as propriedades. Além disso, [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) grava uma instância de um objeto [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) que representa um recipiente de propriedades das propriedades recuperadas. O método não deve retornar nada.

É recomendável que a implementação de [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) ofereça suporte à expansão curinga de nomes de propriedade para cada elemento na lista de seleção. Para fazer isso, use a classe [System. Management. Automation. Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) para executar a correspondência de padrão curinga.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty)]  -->

#### <a name="things-to-remember-about-implementing-getproperty"></a>Coisas a serem lembradas sobre a implementação de GetProperty

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty):

- Ao definir a classe do provedor, um provedor de propriedades do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem recuperar um leitor para objetos ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) seja definida como `true` . Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false` .

## <a name="attaching-dynamic-parameters-to-the-get-itemproperty-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Get-ItemProperty

O `Get-ItemProperty` cmdlet pode exigir parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de propriedades do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) . O `path` parâmetro indica um caminho interno de provedor totalmente qualificado, enquanto o `providerSpecificPickList` parâmetro especifica as propriedades específicas do provedor inseridas na linha de comando. Esse parâmetro pode ser `null` ou vazio se as propriedades forem canalizadas para o cmdlet. Nesse caso, esse método retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O tempo de execução do Windows PowerShell usa o objeto retornado para adicionar os parâmetros ao cmdlet.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters)]  -->

## <a name="setting-properties"></a>Definindo propriedades

Para definir propriedades, o provedor de propriedades do Windows PowerShell deve implementar o método [System. Management. Automation. provedor. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) para dar suporte a chamadas do `Set-ItemProperty` cmdlet. Esse método define uma ou mais propriedades do item no caminho especificado e substitui as propriedades fornecidas conforme necessário.
[System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) também grava uma instância de um objeto [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) que representa um recipiente de propriedades das propriedades atualizadas.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty)]  -->

#### <a name="things-to-remember-about-implementing-set-itemproperty"></a>Coisas a serem lembradas sobre a implementação de Set-ItemProperty

As condições a seguir podem se aplicar a uma implementação de [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty):

- Ao definir a classe do provedor, um provedor de propriedades do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) deve garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem recuperar um leitor para objetos ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) seja definida como `true` . Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false` .

- Sua implementação do método [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Esse método é usado para confirmar a execução de uma operação quando uma alteração é feita no estado do sistema, por exemplo, renomeando arquivos.
  [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell e manipulando quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido.

  Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true` , se for possível fazer modificações do sistema potencialmente perigosas, o método [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Esse método envia uma mensagem de confirmação ao usuário para permitir comentários adicionais para indicar que a operação deve continuar.

## <a name="attaching-dynamic-parameters-for-the-set-itemproperty-cmdlet"></a>Anexando parâmetros dinâmicos para o cmdlet Set-ItemProperty

O `Set-ItemProperty` cmdlet pode exigir parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de propriedades do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Setpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) . Esse método retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O `null` valor pode ser retornado se nenhum parâmetro dinâmico for adicionado.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters)]  -->

## <a name="clearing-properties"></a>Limpando Propriedades

Para limpar Propriedades, o provedor de propriedades do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) para dar suporte a chamadas do `Clear-ItemProperty` cmdlet. Esse método define uma ou mais propriedades para o item localizado no caminho especificado.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty](Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty)]  -->

#### <a name="thing-to-remember-about-implementing-clearproperty"></a>Algo a ser lembrado sobre a implementação de Clearproperty

As condições a seguir podem se aplicar à sua implementação de [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty):

- Ao definir a classe do provedor, um provedor de propriedades do Windows PowerShell pode declarar os recursos do provedor de ExpandWildcards, filtrar, incluir ou excluir da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Nesses casos, a implementação do método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) precisa garantir que o caminho passado para o método atenda aos requisitos dos recursos especificados. Para fazer isso, o método deve acessar a propriedade apropriada, por exemplo, as propriedades [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) e [System. Management. Automation. Provider. cmdletprovider. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Por padrão, as substituições desse método não devem recuperar um leitor para objetos ocultos do usuário, a menos que a propriedade [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) seja definida como `true` . Um erro deve ser gravado se o caminho representa um item que está oculto do usuário e [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) é definido como `false` .

- Sua implementação do método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) deve chamar [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) e verificar seu valor de retorno antes de fazer qualquer alteração no armazenamento de dados. Esse método é usado para confirmar a execução de uma operação antes que uma alteração seja feita no estado do sistema, como limpar o conteúdo.
  [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) envia o nome do recurso a ser alterado para o usuário, com o tempo de execução do Windows PowerShell levando em conta quaisquer configurações de linha de comando ou variáveis de preferência para determinar o que deve ser exibido.

  Após a chamada para [System. Management. Automation. Provider. cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) retornar `true` , se for possível fazer modificações do sistema potencialmente perigosas, o método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) deverá chamar o método [System. Management. Automation. Provider. cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Esse método envia uma mensagem de confirmação ao usuário para permitir comentários adicionais para indicar que a operação potencialmente perigosa deve continuar.

## <a name="attaching-dynamic-parameters-to-the-clear-itemproperty-cmdlet"></a>Anexando parâmetros dinâmicos ao cmdlet Clear-ItemProperty

O `Clear-ItemProperty` cmdlet pode exigir parâmetros adicionais que são especificados dinamicamente no tempo de execução. Para fornecer esses parâmetros dinâmicos, o provedor de propriedades do Windows PowerShell deve implementar o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) . Esse método retorna um objeto que tem propriedades e campos com atributos de análise semelhantes a uma classe de cmdlet ou um objeto [System. Management. Automation. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . O `null` valor pode ser retornado se nenhum parâmetro dinâmico for adicionado.

Aqui está a implementação padrão de [System. Management. Automation. Provider. Ipropertycmdletprovider. Clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) do arquivo TemplateProvider.cs fornecido pelo Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters)]  -->

## <a name="building-the-windows-powershell-provider"></a>Criando o provedor do Windows PowerShell

Consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="see-also"></a>Consulte Também

[Provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Criar seu provedor do Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))
