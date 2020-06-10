---
title: AccessDBProviderSample04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: c0efd10680d3323b6c8d932604176c4425e7266a
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633355"
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
