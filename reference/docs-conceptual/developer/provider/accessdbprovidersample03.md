---
title: AccessDBProviderSample03 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: 86daab97236ca4be94669f107d5a03abea6f6c91
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633389"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

Este exemplo mostra como substituir os métodos [System. Management. Automation. Provider. createcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) e [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para dar suporte a chamadas para `Get-Item` os `Set-Item` cmdlets e. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

## <a name="demonstrates"></a>Demonstra

> [!IMPORTANT]
> Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:
>
> - Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
> - Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).
> - Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Consulte [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).

Este exemplo demonstra o seguinte:

- Declarando o `CmdletProvider` atributo.
- Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. mycmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
- Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) para alterar o comportamento do `New-PSDrive` cmdlet, permitindo que o usuário crie novas unidades.
  (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `New-PSDrive` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para dar suporte à remoção de unidades existentes.
- Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) para alterar o comportamento do `Get-Item` cmdlet, permitindo que o usuário recupere itens do armazenamento de dados. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Get-Item` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para alterar o comportamento do `Set-Item` cmdlet, permitindo que o usuário atualize os itens no repositório de dados. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Get-Item` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. mycmdletprovider. myexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) para alterar o comportamento do `Test-Path` cmdlet. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao `Test-Path` cmdlet.)
- Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) para determinar se o caminho fornecido é válido.

## <a name="example"></a>Exemplo

Este exemplo mostra como substituir os métodos necessários para obter e definir itens em um banco de dados do Microsoft Access.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Projetar seu provedor do Windows PowerShell](./provider-types.md)
