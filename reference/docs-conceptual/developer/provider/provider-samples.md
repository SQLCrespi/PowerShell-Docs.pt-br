---
ms.date: 09/13/2016
ms.topic: reference
title: Amostras de provedor
description: Amostras de provedor
ms.openlocfilehash: e6b1e8ce603092a3fd9dd44d7be428587544466b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651128"
---
# <a name="provider-samples"></a>Amostras de provedor

Esta seção inclui exemplos de provedores que acessam um banco de dados do Microsoft Access. Esses exemplos incluem classes de provedor que derivam de todas as classes de provedor base.

## <a name="in-this-section"></a>Nesta seção

Esta seção inclui os tópicos a seguir:

[Exemplo de AccessDBProviderSample01](./accessdbprovidersample01.md) Este exemplo mostra como declarar a classe de provedor que deriva diretamente da classe [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) . Ele é incluído aqui apenas para fins de integridade.

[AccessDBProviderSample02](./accessdbprovidersample02.md) Este exemplo mostra como substituir os métodos [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) e [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para dar suporte a chamadas para `New-PSDrive` os `Remove-PSDrive` cmdlets e. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .

[AccessDBProviderSample03](./accessdbprovidersample03.md) Este exemplo mostra como substituir os métodos [System. Management. Automation. Provider. createcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) e [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para dar suporte a chamadas para `Get-Item` os `Set-Item` cmdlets e. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

[AccessDBProviderSample04](./accessdbprovidersample04.md) Este exemplo mostra como substituir métodos de contêiner para dar suporte a chamadas para os `Copy-Item` `Get-ChildItem` `New-Item` cmdlets,, e `Remove-Item` . Esses métodos devem ser implementados quando o armazenamento de dados contiver itens que são contêineres. Um contêiner é um grupo de itens filho em um item pai comum. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

[AccessDBProviderSample05](./accessdbprovidersample05.md) Este exemplo mostra como substituir métodos de contêiner para dar suporte a chamadas para os `Move-Item` `Join-Path` cmdlets e. Esses métodos deverão ser implementados quando o usuário precisar mover itens dentro de um contêiner e se o armazenamento de dados contiver contêineres aninhados. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

[AccessDBProviderSample06](./accessdbprovidersample06.md) Este exemplo mostra como substituir os métodos de conteúdo para dar suporte a chamadas para os `Clear-Content` `Get-Content` `Set-Content` cmdlets, e. Esses métodos devem ser implementados quando o usuário precisa gerenciar o conteúdo dos itens no armazenamento de dados. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) e implementa a interface [System. Management. Automation. Provider. Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

## <a name="see-also"></a>Consulte Também

[Escrever um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)
