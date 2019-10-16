---
title: Criando seu provedor do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], designing
ms.assetid: 11d20319-cc40-4227-b810-4af33372b182
caps.latest.revision: 10
ms.openlocfilehash: 962d2ba9fd892c297a633276b9ac07a5fa75ea87
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366805"
---
# <a name="designing-your-windows-powershell-provider"></a>Projetar seu provedor do Windows PowerShell

Você deve implementar um provedor do Windows PowerShell se seu produto ou configuração expõe um conjunto de dados armazenados, como um banco de dado que o usuário deseja navegar ou procurar. Além disso, se o seu produto fornecer um contêiner, mesmo que não seja um contêiner de vários níveis, faz sentido implementar um provedor do Windows PowerShell. Por exemplo, talvez você queira implementar um provedor de contêiner do Windows PowerShell se a cópia do verbo do cmdlet, mover, renomear, novo ou remover fizer sentido como uma operação em seu produto ou dados de configuração.

## <a name="windows-powershell-paths-identify-your-provider"></a>Caminhos do Windows PowerShell identificam seu provedor

O tempo de execução do Windows PowerShell usa caminhos do Windows PowerShell para acessar o provedor do Windows PowerShell apropriado. Quando um cmdlet especifica um desses caminhos, o tempo de execução sabe qual provedor usar para acessar o armazenamento de dados associado. Esses caminhos incluem caminhos qualificados da unidade, caminhos qualificados do provedor, caminhos diretos do provedor e caminhos internos do provedor. Cada provedor do Windows PowerShell deve dar suporte a um ou mais desses caminhos.

Para obter mais informações sobre os caminhos do Windows PowerShell, consulte como o Windows PowerShell funciona.

### <a name="defining-a-drive-qualified-path"></a>Definindo um caminho qualificado da unidade

Para permitir que o usuário acesse os dados localizados em uma unidade física, seu provedor do Windows PowerShell deve dar suporte a um caminho qualificado para unidade. Esse caminho começa com o nome da unidade seguido por dois-pontos (:), por exemplo, myDrive: \ abc\bar.

### <a name="defining-a-provider-qualified-path"></a>Definindo um caminho qualificado pelo provedor

Para permitir que o tempo de execução do Windows PowerShell inicialize e desinicialize o provedor, seu provedor do Windows PowerShell deve dar suporte a um caminho qualificado para provedor. Por exemplo, FileSystem:: \\ \ uncshare\abc\bar é o caminho qualificado do provedor para o provedor FileSystem fornecido pelo Windows PowerShell.

### <a name="defining-a-provider-direct-path"></a>Definindo um caminho direto do provedor

Para permitir o acesso remoto ao seu provedor do Windows PowerShell, ele deve dar suporte a um caminho direto do provedor para passar diretamente para o provedor do Windows PowerShell para o local atual. Por exemplo, o provedor do Windows PowerShell do registro pode usar \\ \ server\regkeypath como um caminho direto do provedor.

### <a name="defining-a-provider-internal-path"></a>Definindo um caminho interno do provedor

Para permitir que o cmdlet do provedor acesse dados usando interfaces de programação de aplicativo (APIs) não Windows PowerShell, seu provedor do Windows PowerShell deve dar suporte a um caminho interno do provedor. Esse caminho é indicado após "::" no caminho qualificado do provedor. Por exemplo, o caminho interno do provedor do sistema de arquivos do provedor do Windows PowerShell é \\ \ uncshare\abc\bar.

## <a name="changing-stored-data"></a>Alterando dados armazenados

Ao substituir métodos que modificam o armazenamento de dados subjacente, sempre chame o método [System. Management. Automation. Provider. cmdletprovider. Writeitemobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) com a versão mais atualizada do item alterado por esse método. A infraestrutura do provedor determina se o objeto item precisa ser passado para o pipeline, como quando o usuário especifica o parâmetro-PassThru. Se a recuperação do item mais atualizado for uma operação dispendiosa (em termos de desempenho), você poderá testar a propriedade Context. PassThru para determinar se realmente precisa gravar o item resultante.

## <a name="choose-a-base-class-for-your-provider"></a>Escolha uma classe base para seu provedor

O Windows PowerShell fornece várias classes base que você pode usar para implementar seu próprio provedor do Windows PowerShell. Ao criar um provedor, escolha a classe base, descrita nesta seção, que é mais adequada para seus requisitos.

Cada classe base do provedor do Windows PowerShell disponibiliza um conjunto de cmdlets. Esta seção descreve os cmdlets, mas não descreve seus parâmetros.

Usando o estado de sessão, o tempo de execução do Windows PowerShell disponibiliza vários cmdlets de local para determinados provedores do Windows PowerShell, como os cmdlets `Get-Location`, `Set-Location`, `Pop-Location` e `Push-Location`. Você pode usar o cmdlet `Get-Help` para obter informações sobre esses cmdlets de local.

### <a name="cmdletprovider-base-class"></a>Classe base cmdletprovider

A classe [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) define um provedor básico do Windows PowerShell. Essa classe dá suporte à declaração do provedor e fornece uma série de propriedades e métodos que estão disponíveis para todos os provedores do Windows PowerShell. A classe é invocada pelo cmdlet `Get-PSProvider` para listar todos os provedores disponíveis para uma sessão. A implementação desse cmdlet é fornecida pelo estado da sessão.

> [!NOTE]
> Os provedores do Windows PowerShell estão disponíveis para todos os escopos de idiomas do Windows PowerShell.

### <a name="drivecmdletprovider-base-class"></a>Classe base DriveCmdletProvider

A classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) define um provedor de unidade do Windows PowerShell que dá suporte a operações para adicionar novas unidades, remover unidades existentes e inicializar unidades padrão. Por exemplo, o provedor FileSystem fornecido pelo Windows PowerShell Inicializa unidades para todos os volumes que são montados, como discos rígidos e unidades de dispositivo de CD/DVD.

Essa classe deriva da classe base [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) . A tabela a seguir lista os cmdlets expostos por essa classe. Além daqueles listados, o cmdlet `Get-PSDrive` (exposto por estado de sessão) é um cmdlet relacionado que é usado para recuperar as unidades disponíveis.

|Cmdlet|Definição|
|------------|----------------|
|`New-PSDrive`|Cria uma nova unidade para a sessão e transmite as informações da unidade.|
|`Remove-PSDrive`|Remove uma unidade da sessão.|

### <a name="itemcmdletprovider-base-class"></a>Classe base de defaultcmdletprovider

A classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) define um provedor de item do Windows PowerShell que executa operações em itens individuais do armazenamento de dados e não assume nenhum recurso de navegação ou contêiner. Essa classe deriva da classe base [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . A tabela a seguir lista os cmdlets expostos por essa classe.

|Cmdlet|Definição|
|------------|----------------|
|`Clear-Item`|Limpa o conteúdo atual dos itens no local especificado e o substitui pelo valor "Clear" especificado pelo provedor. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Get-Item`|Recupera itens do local especificado e transmite os objetos resultantes.|
|`Invoke-Item`|Invoca a ação padrão para o item no caminho especificado.|
|`Set-Item`|Define um item no local especificado com o valor indicado. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Resolve-Path`|Resolve os curingas para um caminho do Windows PowerShell e transmite informações de caminho.|
|`Test-Path`|Testa o caminho especificado e retorna `true` se ele existir e `false` caso contrário. Esse cmdlet é implementado para dar suporte ao parâmetro `IsContainer` para o método [System. Management. Automation. Provider. cmdletprovider. Writeitemobject *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .|

### <a name="containercmdletprovider-base-class"></a>Classe base ContainerCmdletProvider

A classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) define um provedor de contêiner do Windows PowerShell que expõe um contêiner, para itens de armazenamento de dados, ao usuário. Lembre-se de que um provedor de contêiner do Windows PowerShell pode ser usado somente quando há um contêiner (sem Contêineres aninhados) com itens. Se houver Contêineres aninhados, você deverá implementar um provedor de navegação do Windows PowerShell.

Essa classe deriva da classe base [System. Management. Automation. Provider. @ cmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . A tabela a seguir define os cmdlets implementados por essa classe.

|Cmdlet|Definição|
|------------|----------------|
|`Copy-Item`|Copia itens de um local para outro. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Get-Childitem`|Recupera os itens filho no local especificado e os transmite como objetos.|
|`New-Item`|Cria novos itens no local especificado e transmite o objeto resultante.|
|`Remove-Item`|Remove itens do local especificado.|
|`Rename-Item`|Renomeia um item no local especificado. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|

### <a name="navigationcmdletprovider-base-class"></a>Classe base NavigationCmdletProvider

A classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) define um provedor de navegação do Windows PowerShell que executa operações para itens que usam mais de um contêiner. Essa classe deriva da classe base [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . A tabela a seguir lista os cmdlets expostos por essa classe.

|Cmdlet|Definição|
|------------|----------------|
|Combinação-caminho|Combina dois caminhos em um único caminho, usando um delimitador específico de provedor entre caminhos. Esse cmdlet transmite cadeias de caracteres.|
|`Move-Item`|Move itens para o local especificado. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|

Um cmdlet relacionado é o cmdlet de análise-caminho básico fornecido pelo Windows PowerShell. Esse cmdlet pode ser usado para analisar um caminho do Windows PowerShell para dar suporte ao parâmetro `Parent`. Ele transmite a cadeia de caracteres do caminho pai.

## <a name="select-provider-interfaces-to-support"></a>Selecionar interfaces de provedor para dar suporte

Além de derivar de uma das classes base do Windows PowerShell, seu provedor do Windows PowerShell pode dar suporte a outras funcionalidades derivando de uma ou mais das seguintes interfaces de provedor. Esta seção define as interfaces e os cmdlets com suporte em cada um. Ele não descreve os parâmetros para os cmdlets com suporte de interface. As informações de parâmetro de cmdlet estão disponíveis online usando os cmdlets `Get-Command` e `Get-Help`.

### <a name="icontentcmdletprovider"></a>IContentCmdletProvider

A interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) define um provedor de conteúdo que executa operações no conteúdo de um item de dados. A tabela a seguir lista os cmdlets expostos por essa interface.

|Cmdlet|Definição|
|------------|----------------|
|`Add-Content`|Acrescenta os comprimentos de valor indicados ao conteúdo do item especificado. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Clear-Content`|Define o conteúdo do item especificado para o valor "Clear". Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Get-Content`|Recupera o conteúdo dos itens especificados e transmite os objetos resultantes.|
|`Set-Content`|Substitui o conteúdo existente para os itens especificados. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|

### <a name="ipropertycmdletprovider"></a>IPropertyCmdletProvider

A interface [System. Management. Automation. Provider. Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) define uma propriedade do provedor do Windows PowerShell que executa operações nas propriedades de itens no armazenamento de dados. A tabela a seguir lista os cmdlets expostos por essa interface.

> [!NOTE]
> O parâmetro `Path` nesses cmdlets indica um caminho para um item em vez de identificar uma propriedade.

|Cmdlet|Definição|
|------------|----------------|
|`Clear-ItemProperty`|Define as propriedades dos itens especificados para o valor "Clear". Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Get-ItemProperty`|Recupera as propriedades dos itens especificados e transmite os objetos resultantes.|
|`Set-ItemProperty`|Define as propriedades dos itens especificados com os valores indicados. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|

### <a name="idynamicpropertycmdletprovider"></a>IDynamicPropertyCmdletProvider

A interface [System. Management. Automation. Provider. Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) , derivada de [System. Management. Automation. Provider. Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider), define um provedor que especifica parâmetros dinâmicos para seu cmdlets com suporte. Esse tipo de provedor trata as operações para as quais as propriedades podem ser definidas em tempo de execução, por exemplo, uma nova operação de propriedade. Essas operações não são possíveis em itens com propriedades definidas estaticamente. A tabela a seguir lista os cmdlets expostos por essa interface.

|Cmdlet|Definição|
|------------|----------------|
|`Copy-ItemProperty`|Copia uma propriedade do item especificado para outro item. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`Move-ItemProperty`|Move uma propriedade do item especificado para outro item. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|
|`New-ItemProperty`|Cria uma propriedade nos itens especificados e transmite os objetos resultantes.|
|`Remove-ItemProperty`|Remove uma propriedade para os itens especificados.|
|`Rename-ItemProperty`|Renomeia uma propriedade dos itens especificados. Esse cmdlet não passa um objeto de saída por meio do pipeline, a menos que seu parâmetro `PassThru` seja especificado.|

### <a name="isecuritydescriptorcmdletprovider"></a>ISecurityDescriptorCmdletProvider

A interface [System. Management. Automation. Provider. Isecuritydescriptorcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ISecurityDescriptorCmdletProvider) adiciona a funcionalidade de descritor de segurança a um provedor. Essa interface permite que o usuário obtenha e defina informações de descritor de segurança para um item no repositório de dados. A tabela a seguir lista os cmdlets expostos por essa interface.

|Cmdlet|Definição|
|------------|----------------|
|`Get-Acl`|Recupera as informações contidas em uma ACL (lista de controle de acesso), que faz parte de um descritor de segurança usado para proteger os recursos do sistema operacional, por exemplo, um arquivo ou um objeto.|
|`Set-Acl`|Define as informações de uma ACL. Ele está na forma de uma instância de [System. Security. AccessControl. ObjectSecurity](/dotnet/api/System.Security.AccessControl.ObjectSecurity) nos itens designados para o caminho especificado. Esse cmdlet pode definir informações sobre arquivos, chaves e subchaves no registro, ou qualquer outro item de provedor, se o provedor do Windows PowerShell oferecer suporte à configuração de informações de segurança.|

## <a name="see-also"></a>Consulte Também

[Criando provedores do Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Como funciona o Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[SDK do Windows PowerShell](../windows-powershell-reference.md)