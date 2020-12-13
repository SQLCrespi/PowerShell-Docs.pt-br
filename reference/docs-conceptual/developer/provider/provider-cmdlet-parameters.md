---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de cmdlet do provedor
description: Parâmetros de cmdlet do provedor
ms.openlocfilehash: 6fd340f22202d984b7111c34806e3461a356c670
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662771"
---
# <a name="provider-cmdlet-parameters"></a>Parâmetros de cmdlet do provedor

Os cmdlets do provedor vêm com um conjunto de parâmetros estáticos que estão disponíveis para todos os provedores que oferecem suporte ao cmdlet, bem como parâmetros dinâmicos que são adicionados quando o usuário especifica um determinado valor para determinados parâmetros estáticos do cmdlet do provedor.

## <a name="provider-cmdlet-static-parameters"></a>Parâmetros estáticos do cmdlet do provedor

Os parâmetros estáticos são definidos pelo Windows PowerShell. Um grande conjunto desses parâmetros é implementado pelo Windows PowerShell para fornecer consistência em todos os provedores e para fornecer uma experiência de desenvolvimento mais simples. Exemplos desses parâmetros incluem os `literalPath` parâmetros, `exclude` e `include` do `Get-Item` cmdlet. Um conjunto menor desses parâmetros pode ser substituído para fornecer ações específicas ao seu provedor. Exemplos desses parâmetros incluem o `Path` parâmetro e `Value` do `Set-Item` cmdlet. Aqui está uma lista dos parâmetros que podem ser substituídos para os cmdlets do provedor.

`Clear-Content` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Clear-Content` cmdlet implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

`Clear-Item` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Clear-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. ClearItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

`Clear-ItemProperty` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Name` parâmetros e do `Clear-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

`Copy-Item` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Destination` parâmetros, e `Recurse` do `Copy-Item` cmdlet implementando o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) .

Get-ChildItems cmdlet, você pode definir como seu provedor usará os valores passados para `Path` os `Recurse` parâmetros e do `Get-ChildItem` cmdlet implementando os métodos [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) e [System. Management. Automation. Provider. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

`Get-Content` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Get-Content` cmdlet implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Get-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

`Get-ItemProperty` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Name` parâmetros e do `Get-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

`Invoke-Item` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Invoke-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

`Move-Item` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Destination` parâmetros e do `Move-Item` cmdlet implementando o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

`New-Item` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `ItemType` parâmetros, e `Value` do `New-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) .

`New-ItemProperty` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Name` parâmetros,, `PropertyType` e `Value` do `New-ItemProperty` cmdlet implementando o método [Microsoft. PowerShell. Commands. registryprovider. NewProperty *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) .

`Remove-Item` Você pode definir como seu provedor usará os valores passados para os `Path` `Recurse` parâmetros e do `Remove-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty` Você pode definir como seu provedor usará os valores passados para os `Path` `Name` parâmetros e do `Remove-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. RemoveProperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) .

`Rename-Item` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `NewName` parâmetros e do `Rename-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty` Você pode definir como seu provedor usará os valores passados para os `Path` `NewName` parâmetros, e `Name` do `Rename-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. renomeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) .

`Set-Content` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Set-Content` cmdlet implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

`Set-Item` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Value` parâmetros e do `Set-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

`Set-ItemProperty` cmdlet você pode definir como seu provedor usará os valores passados para os `Path` `Value` parâmetros e do `Set-Item` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

`Test-Path` cmdlet você pode definir como seu provedor usará os valores passados para o `Path` parâmetro do `Test-Path` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Além disso, você não pode especificar as características desses parâmetros, como se eles são opcionais ou obrigatórios, nem você pode dar a esses parâmetros um alias ou especificar qualquer um dos atributos de validação. Por outro lado, você pode especificar características de parâmetro em cmdlets autônomos usando atributos como o `Parameters` atributo.

## <a name="provider-cmdlet-dynamic-parameters"></a>Parâmetros dinâmicos do cmdlet do provedor

Os parâmetros dinâmicos para provedores de cmdlet são semelhantes aos provedores dinâmicos para cmdlets autônomos. Em ambos os casos, os parâmetros são adicionados ao cmdlet quando o usuário especifica um determinado valor para um dos parâmetros padrão, como o `path` parâmetro. No entanto, nem todos os parâmetros estáticos podem ser usados para disparar a adição de parâmetros dinâmicos. Para obter mais informações sobre parâmetros dinâmicos, consulte [parâmetros dinâmicos do cmdlet do provedor](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>Consulte Também

[Parâmetros dinâmicos do cmdlet do provedor](./provider-cmdlet-dynamic-parameters.md)

[Escrever um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)
