---
title: Visão geral do provedor do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82244fbd-07b9-47f3-805c-3fb90ebbf58a
caps.latest.revision: 13
ms.openlocfilehash: 9f1b94e722e59e707a26547949c661b5098d29e0
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560943"
---
# <a name="windows-powershell-provider-overview"></a>Visão geral do provedor do Windows PowerShell

Um provedor do Windows PowerShell permite que qualquer armazenamento de dados seja exposto como um sistema de arquivos como se fosse uma unidade montada. Por exemplo, o provedor de registro interno permite que você navegue no registro como você navegaria na `c` unidade do seu computador. Um provedor também pode substituir os `Item` cmdlets (por exemplo,,, `Get-Item` `Set-Item` etc.), de modo que os dados em seu armazenamento de dados possam ser tratados como arquivos e diretórios são tratados ao navegar em um sistema de arquivos. Para obter mais informações sobre provedores e unidades e os provedores internos do Windows PowerShell, consulte [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).

## <a name="providers-and-drives"></a>Provedores e unidades

Um provedor define a lógica que é usada para acessar, navegar e editar um armazenamento de dados, enquanto uma unidade especifica um ponto de entrada específico para um armazenamento de dados (ou uma parte de um armazenamento de dados) que é do tipo definido pelo provedor. Por exemplo, o provedor de registro permite que você acesse Hives e chaves em um registro, e as unidades HKLM e HKCU especificam os hives correspondentes no registro. As unidades HKLM e HKCU usam o provedor de registro.

Ao escrever um provedor, você pode especificar unidades-unidades padrão que são criadas automaticamente quando o provedor está disponível. Você também define um método para criar novas unidades que usam esse provedor.

## <a name="type-of-providers"></a>Tipo de provedores

Há vários tipos de provedores, cada um dos quais fornece um nível diferente de funcionalidade. Um provedor é implementado como uma classe que deriva de um dos descendentes da classe [System. Management. Automation. SessionStateCategory](/dotnet/api/system.management.automation.sessionstatecategory?view=pscore-6.2.0) do **cmdletprovider** . Para obter informações sobre os diferentes tipos de provedores, consulte [tipos de provedor](./provider-types.md).

## <a name="provider-cmdlets"></a>Cmdlets do provedor

Os provedores podem implementar métodos que correspondam aos cmdlets, criando comportamentos personalizados para esses cmdlets quando usados em uma unidade para esse provedor. Dependendo do tipo de provedor, diferentes conjuntos de cmdlets estão disponíveis. Para obter uma lista completa dos cmdlets disponíveis para personalização em provedores, consulte [cmdlets do provedor](./provider-cmdlets.md).

## <a name="provider-paths"></a>Caminhos de provedor

Os usuários navegam por unidades de provedor como sistemas de arquivos. Por isso, eles esperam que a sintaxe dos caminhos corresponda aos caminhos usados na navegação do sistema de arquivos. Quando um usuário executa um cmdlet de provedor, ele especifica um caminho para o item a ser acessado. O caminho especificado pode ser interpretado de várias maneiras. Um provedor deve dar suporte a um ou mais dos seguintes tipos de caminho.

### <a name="drive-qualified-paths"></a>Caminhos qualificados para a unidade

Um caminho qualificado para unidade é uma combinação do nome do item, o contêiner e os sub-recipientes nos quais o item está localizado e a unidade do Windows PowerShell por meio da qual o item é acessado. (As unidades são definidas pelo provedor que é usado para acessar o armazenamento de dados. Esse caminho começa com o nome da unidade seguido por dois-pontos (:). Por exemplo: `get-childitem C:`

### <a name="provider-qualified-paths"></a>Caminhos qualificados para o provedor

Para permitir que o mecanismo do Windows PowerShell inicialize e desinicialize seu provedor, o provedor deve dar suporte a um caminho qualificado para provedor. Por exemplo, o usuário pode inicializar e cancelar a inicialização do provedor FileSystem porque ele define o seguinte caminho qualificado para provedor: `FileSystem::\\uncshare\abc\bar` .

### <a name="provider-direct-paths"></a>Provedores-caminhos diretos

Para permitir o acesso remoto ao seu provedor do Windows PowerShell, ele deve dar suporte a um caminho direto do provedor para passar diretamente para o provedor do Windows PowerShell para o local atual. Por exemplo, o provedor do Windows PowerShell do registro pode usar `\\server\regkeypath` como um caminho direto do provedor.

### <a name="provider-internal-paths"></a>Provedor-caminhos internos

Para permitir que o cmdlet do provedor acesse dados usando interfaces de programação de aplicativo (APIs) não Windows PowerShell, seu provedor do Windows PowerShell deve dar suporte a um caminho interno do provedor. Esse caminho é indicado após "::" no caminho qualificado do provedor. Por exemplo, o caminho interno do provedor para o sistema de arquivos do provedor do Windows PowerShell é `\\uncshare\abc\bar` .

## <a name="overriding-cmdlet-parameters"></a>Substituindo parâmetros de cmdlet

O comportamento de alguns cmdlets específicos do provedor pode ser substituído por um provedor. Para obter uma lista de parâmetros que podem ser substituídos e como substituí-los em sua classe de provedor, consulte [parâmetros de cmdlet do provedor](./provider-cmdlet-parameters.md)

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Os provedores podem definir parâmetros dinâmicos que são adicionados a um cmdlet de provedor quando o usuário especifica um determinado valor para um dos parâmetros estáticos do cmdlet. Um provedor faz isso implementando um ou mais métodos de parâmetro dinâmicos. Para obter uma lista de parâmetros de cmdlet que podem ser usados para adicionar um parâmetro dinâmico e os métodos usados para implementá-los, consulte [parâmetros dinâmicos do cmdlet do provedor](./provider-cmdlet-dynamic-parameters.md).

## <a name="provider-capabilities"></a>Recursos do provedor

A enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) define uma série de recursos aos quais os provedores podem dar suporte. Isso inclui a capacidade de usar curingas, filtrar itens e transações de suporte. Para especificar recursos para um provedor, adicione uma lista de valores da enumeração [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) , combinada com uma operação lógica `OR` , como a propriedade [System. Management. Automation. Provider. Cmdletproviderattribute. Providercapabilities *](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities) (o segundo parâmetro do atributo) do atributo [System. Management. Automation. Provider. Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) para sua classe de provedor. Por exemplo, o atributo a seguir especifica que o provedor dá suporte aos recursos de **Transações** [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities?view=pscore-6.2.0) **ShouldProcess** e [System. Management. Automation. Provider. Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities?view=pscore-6.2.0) .

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a>Ajuda do cmdlet do provedor

Ao escrever um provedor, você pode implementar sua própria ajuda para os cmdlets do provedor aos quais você dá suporte. Isso inclui um único tópico de ajuda para cada cmdlet de provedor ou várias versões de um tópico da ajuda para casos em que o cmdlet do provedor atua de forma diferente com base no uso de parâmetros dinâmicos. Para dar suporte à ajuda específica do cmdlet do provedor, seu provedor deve implementar a interface [System. Management. Automation. Provider. Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp) .

O mecanismo do Windows PowerShell chama o método [System. Management. Automation. Provider. Icmdletprovidersupportshelp. Gethelpmaml *](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml) para exibir o tópico da ajuda para seus cmdlets do provedor. O mecanismo fornece o nome do cmdlet que o usuário especificou ao executar o `Get-Help` cmdlet e o caminho atual do usuário. O caminho atual será necessário se o provedor implementar versões diferentes do mesmo cmdlet do provedor para unidades diferentes. O método deve retornar uma cadeia de caracteres que contém o XML para a ajuda do cmdlet.

O conteúdo do arquivo de ajuda é escrito usando PSMAML XML. Esse é o mesmo esquema XML usado para gravar o conteúdo da ajuda para cmdlets autônomos. Adicione o conteúdo para a ajuda do cmdlet personalizado ao arquivo de ajuda para o seu provedor no `CmdletHelpPaths` elemento. O exemplo a seguir mostra o `command` elemento para um cmdlet de provedor único e mostra como você especifica o nome do cmdlet do provedor que seu provedor. dá suporte

```xml
<CmdletHelpPaths>
  <command:command>
    <command:details>
      <command:name>ProviderCmdletName</command:name>
      <command:verb>Verb</command:verb>
      <command:noun>Noun</command:noun>
    <command:details>
  </command:command>
<CmdletHelpPath>
```

## <a name="see-also"></a>Consulte Também

[Funcionalidade do provedor do Windows PowerShell](./provider-types.md)

[Cmdlets do provedor](./provider-cmdlets.md)

[Escrever um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)
