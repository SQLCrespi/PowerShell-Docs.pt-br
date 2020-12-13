---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample04
description: AccessDBProviderSample04
ms.openlocfilehash: 962d0ab673ff797a60b56ccae7a16a810cc43c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649049"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

Este exemplo mostra como substituir métodos de contêiner para dar suporte a chamadas para os `Copy-Item` `Get-ChildItem` `New-Item` cmdlets,, e `Remove-Item` . Esses métodos devem ser implementados quando o armazenamento de dados contiver itens que são contêineres. Um contêiner é um grupo de itens filho em um item pai comum. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

## <a name="demonstrates"></a>Demonstra

> [!IMPORTANT]
> Sua classe de provedor provavelmente será derivada do [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

Este exemplo demonstra o seguinte:

- Declarando o `CmdletProvider` atributo.
- Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .
- Substituindo o método [System. Management. Automation. Provider. ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) para alterar o comportamento do `Copy-Item` cmdlet que permite ao usuário copiar itens de um local para outro. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Copy-Item` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. GetChildItems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) para alterar o comportamento do cmdlet Get-ChildItems, que permite ao usuário recuperar os itens filho do item pai. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet Get-ChildItems.)
- Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) para alterar o comportamento do cmdlet Get-ChildItems quando o `Name` parâmetro do cmdlet é especificado.
- Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. NewItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) para alterar o comportamento do `New-Item` cmdlet, que permite ao usuário adicionar itens ao armazenamento de dados. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `New-Item` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. Containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) para alterar o comportamento do `Remove-Item` cmdlet. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Remove-Item` cmdlet.)

## <a name="example"></a>Exemplo

Este exemplo mostra como substituir os métodos necessários para copiar, criar e remover itens, bem como métodos para obter os itens filho de um item pai.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Projetar seu provedor do Windows PowerShell](./provider-types.md)
