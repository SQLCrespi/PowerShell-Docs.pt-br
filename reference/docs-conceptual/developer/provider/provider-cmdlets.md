---
ms.date: 09/12/2016
ms.topic: reference
title: Cmdlets do provedor
description: Cmdlets do provedor
ms.openlocfilehash: 522dacfe4d7190c12ea0de148fe83bf6b5fed10f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662900"
---
# <a name="provider-cmdlets"></a>Cmdlets do provedor

Os cmdlets que o usuário pode executar para gerenciar um armazenamento de dados são chamados de cmdlets de provedor. Para dar suporte a esses cmdlets, você precisa substituir alguns dos métodos definidos pelas classes e interfaces do provedor base.

## <a name="provider-cmdlets"></a>Cmdlets do provedor

Estes são os cmdlets do provedor que podem ser executados pelo usuário:

### <a name="psdrive-cmdlets"></a>Cmdlets PSDrive

- `Get-PSDrive`: Esse cmdlet retorna as unidades do Windows PowerShell na sessão atual. Você não precisa substituir nenhum método para dar suporte a esse cmdlet.

- `New-PSDrive`: Esse cmdlet permite que o usuário crie unidades do Windows PowerShell para acessar o armazenamento de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) e [System. Management. Automation. Provider. Drivecmdletprovider. Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

- `Remove-PSDrive`: Esse cmdlet permite que o usuário remova as unidades do Windows PowerShell que acessam o armazenamento de dados. Para dar suporte a esse cmdlet, substitua o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) .

### <a name="item-cmdlets"></a>Cmdlets de item

- `Clear-Item`: Esse cmdlet permite que o usuário remova o valor de um item no repositório de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. createcmdletprovider. ClearItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) e [System. Management. Automation. Provider. @ cmdletprovider. Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

- `Copy-Item`: Esse cmdlet permite que o usuário Copie um item de um local para outro. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) e [System. Management. Automation. Provider. Containercmdletprovider. Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

- `Get-Item`: Esse cmdlet permite que o usuário recupere dados do armazenamento de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. createcmdletprovider. GetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) e [System. Management. Automation. Provider. @ cmdletprovider. Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

- `Get-ChildItem`: Esse cmdlet permite que o usuário recupere os itens filho do item pai. Para dar suporte a esse cmdlet, substitua os seguintes métodos:

  - [System. Management. Automation. provedor. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [System. Management. Automation. Provider. Containercmdletprovider. Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [System. Management. Automation. provedor. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [System. Management. Automation. Provider. Containercmdletprovider. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`: Esse cmdlet permite que o usuário execute a ação padrão especificada pelo item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. createcmdletprovider. Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) e [System. Management. Automation. Provider. @ cmdletprovider. Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

- `Move-Item`: Esse cmdlet permite que o usuário mova um item de um local para outro local. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) e [System. Management. Automation. Provider. Navigationcmdletprovider. Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s.

- `New-ItemProperty`: Esse cmdlet permite que o usuário crie um novo item no repositório de dados.

- `Remove-Item`: Esse cmdlet permite que o usuário remova itens do armazenamento de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) e [System. Management. Automation. Provider. Containercmdletprovider. Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

- `Rename-Item`: Esse cmdlet permite que o usuário renomeie itens no armazenamento de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Containercmdletprovider. RenameItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) e [System. Management. Automation. Provider. Containercmdletprovider. Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

- `Set-Item`: Esse cmdlet permite que o usuário atualize os valores de itens no armazenamento de dados. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. createcmdletprovider. SetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) e [System. Management. Automation. Provider. @ cmdletprovider. Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

### <a name="item-content-cmdlets"></a>Cmdlets de conteúdo do item

- `Add-Content`: Esse cmdlet permite que o usuário adicione conteúdo a um item.

- `Clear-Content`: Esse cmdlet permite que o usuário exclua o conteúdo de um item sem excluir o item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) e [System. Management. Automation. Provider. Icontentcmdletprovider. Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

- `Get-Content`: Esse cmdlet permite que o usuário recupere o conteúdo de um item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) e [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) . O método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) retorna uma interface [System. Management. Automation. Provider. Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) que define os métodos usados para ler o conteúdo.

- `Set-Content`: Esse cmdlet permite que o usuário atualize o conteúdo de um item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) e [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) . O método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) retorna uma interface [System. Management. Automation. Provider. Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) que define os métodos usados para gravar o conteúdo.

### <a name="item-property-cmdlets"></a>Cmdlets de propriedade de item

- `Clear-ItemProperty`: Esse cmdlet permite que o usuário exclua o valor de uma propriedade. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) e [System. Management. Automation. Provider. Ipropertycmdletprovider. Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

- `Copy-ItemProperty`: Esse cmdlet permite que o usuário Copie uma propriedade e seu valor de um local para outro. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. copieproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) e [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) .

- `Get-ItemProperty`: Esse cmdlet recupera as propriedades de um item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. provedor. Ipropertycmdletprovider. GetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) e [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

- `Move-ItemProperty`: Esse cmdlet permite que o usuário mova uma propriedade e seu valor de um local para outro. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) e [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) .

- `New-ItemProperty`: Esse cmdlet permite que o usuário crie uma nova propriedade e defina seu valor. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. NewProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) e [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

- `Remove-ItemProperty`: Esse cmdlet permite que o usuário exclua uma propriedade e seu valor. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. RemoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) e [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

- `Rename-ItemProperty`: Esse cmdlet permite que o usuário altere o nome de uma propriedade. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) e [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

- `Set-ItemProperty`: Esse cmdlet permite que o usuário atualize as propriedades de um item. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. provedor. Ipropertycmdletprovider. SetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) e [System. Management. Automation. Provider. Ipropertycmdletprovider. Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

### <a name="location-cmdlets"></a>Cmdlets de local

- `Get-Location`: Recupera informações sobre o local de trabalho atual. Você não precisa substituir nenhum método para dar suporte a esse cmdlet.

- `Pop-Location`: Esse cmdlet altera o local atual para o local mais recentemente enviado para a pilha. Você não precisa substituir nenhum método para dar suporte a esse cmdlet.

- `Push-Location`: Esse cmdlet adiciona o local atual à parte superior de uma lista de locais (uma "pilha"). Você não precisa substituir nenhum método para dar suporte a esse cmdlet.

- `Set-Location`: Esse cmdlet define o local de trabalho atual para um local especificado. Você não precisa substituir nenhum método para dar suporte a esse cmdlet.

### <a name="path-cmdlets"></a>Cmdlets de caminho

- `Join-Path`: Esse cmdlet permite que o usuário combine um segmento de caminho pai e filho para criar um caminho interno de provedor. Para dar suporte a esse cmdlet, substitua o método [System. Management. Automation. Provider. Navigationcmdletprovider. makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) .

- `Convert-Path`: Esse cmdlet converte um caminho de um caminho do Windows PowerShell para um caminho de provedor do Windows PowerShell.

- `Split-Path`: Retorna a parte especificada de um caminho.

- `Resolve-Path`: Resolve os caracteres curinga em um caminho e exibe o conteúdo do caminho.

- `Test-Path`: Esse cmdlet determina se todos os elementos de um caminho existem. Para dar suporte a esse cmdlet, substitua os métodos [System. Management. Automation. Provider. createcmdletprovider. myexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) e [System. Management. Automation. Provider. Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) .

### <a name="psprovider-cmdlets"></a>Cmdlets PSProvider

- `Get-PSProvider`: Esse cmdlet retorna informações sobre os provedores disponíveis na sessão. Você não precisa substituir nenhum método para dar suporte a esse cmdlet.
