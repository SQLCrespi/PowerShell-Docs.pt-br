---
title: Parâmetros do cmdlet do provedor | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: ad7f9737c646dd5cea5abb14b828236e40feac5a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366305"
---
# <a name="provider-cmdlet-parameters"></a>Parâmetros de cmdlet do provedor

Os cmdlets do provedor vêm com um conjunto de parâmetros estáticos que estão disponíveis para todos os provedores que oferecem suporte ao cmdlet, bem como parâmetros dinâmicos que são adicionados quando o usuário especifica um determinado valor para determinados parâmetros estáticos do cmdlet do provedor.

## <a name="provider-cmdlet-static-parameters"></a>Parâmetros estáticos do cmdlet do provedor

Os parâmetros estáticos são definidos pelo Windows PowerShell. Um grande conjunto desses parâmetros é implementado pelo Windows PowerShell para fornecer consistência em todos os provedores e para fornecer uma experiência de desenvolvimento mais simples. Exemplos desses parâmetros incluem os parâmetros `literalPath`, `exclude`e `include` do cmdlet `Get-Item`. Um conjunto menor desses parâmetros pode ser substituído para fornecer ações específicas ao seu provedor. Exemplos desses parâmetros incluem o parâmetro `Path` e `Value` do cmdlet `Set-Item`. Aqui está uma lista dos parâmetros que podem ser substituídos para os cmdlets do provedor.

`Clear-Content` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Clear-Content` implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

`Clear-Item` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Clear-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. ClearItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

`Clear-ItemProperty` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Name` do cmdlet `Clear-ItemProperty` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. clearproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

`Copy-Item` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path`, `Destination`e `Recurse` do cmdlet `Copy-Item` implementando o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) .

Cmdlet Get-ChildItems você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Recurse` do cmdlet `Get-ChildItem` implementando os métodos [System. Management. Automation. provedor. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) e [System. Management. Automation. provedor. Containercmdletprovider. getfilhonames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

`Get-Content` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Get-Content` implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Get-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

`Get-ItemProperty` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Name` do cmdlet `Get-ItemProperty` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. GetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

`Invoke-Item` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Invoke-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

`Move-Item` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Destination` do cmdlet `Move-Item` implementando o método [System. Management. Automation. Provider. Navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

`New-Item` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path`, `ItemType`e `Value` do cmdlet `New-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) .

`New-ItemProperty` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path`, `Name`, `PropertyType`e `Value` do cmdlet `New-ItemProperty` implementando o método [Microsoft. PowerShell. Commands. registryprovider. NewProperty *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) .

`Remove-Item` você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Recurse` do cmdlet `Remove-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty` você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Name` do cmdlet `Remove-ItemProperty` implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. RemoveProperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) .

`Rename-Item` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `NewName` do cmdlet `Rename-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. RenameItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty` você pode definir como seu provedor usará os valores passados para os parâmetros `Path`, `NewName`e `Name` do cmdlet `Rename-ItemProperty` implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. renomeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) .

`Set-Content` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Set-Content` implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

`Set-Item` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Value` do cmdlet `Set-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

`Set-ItemProperty` cmdlet, você pode definir como seu provedor usará os valores passados para os parâmetros `Path` e `Value` do cmdlet `Set-Item` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

`Test-Path` cmdlet, você pode definir como seu provedor usará os valores passados para o parâmetro `Path` do cmdlet `Test-Path` implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Além disso, você não pode especificar as características desses parâmetros, como se eles são opcionais ou obrigatórios, nem você pode dar a esses parâmetros um alias ou especificar qualquer um dos atributos de validação. Por outro lado, você pode especificar características de parâmetro em cmdlets autônomos usando atributos como o atributo `Parameters`.

## <a name="provider-cmdlet-dynamic-parameters"></a>Parâmetros dinâmicos do cmdlet do provedor

Os parâmetros dinâmicos para provedores de cmdlet são semelhantes aos provedores dinâmicos para cmdlets autônomos. Em ambos os casos, os parâmetros são adicionados ao cmdlet quando o usuário especifica um determinado valor para um dos parâmetros padrão, como o parâmetro `path`. No entanto, nem todos os parâmetros estáticos podem ser usados para disparar a adição de parâmetros dinâmicos. Para obter mais informações sobre parâmetros dinâmicos, consulte [parâmetros dinâmicos do cmdlet do provedor](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>Consulte Também

[Parâmetros dinâmicos do cmdlet do provedor](./provider-cmdlet-dynamic-parameters.md)

[Escrevendo um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)