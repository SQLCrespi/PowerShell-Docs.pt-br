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
ms.openlocfilehash: aa67bb605f90c1ea40323b4583766069ff1226fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359985"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

Este exemplo mostra como substituir os métodos [System. Management. Automation. Provider. createcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) e [System. Management. Automation. Provider. docmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para dar suporte a chamadas para os cmdlets `Get-Item` e `Set-Item`. A classe de provedor neste exemplo deriva da classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

## <a name="demonstrates"></a>Demonstra

> [!IMPORTANT]
> Sua classe de provedor provavelmente derivará de uma das seguintes classes e, possivelmente, implementará outras interfaces de provedor:
>
> -   Classe [System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
> -   Classe [System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Consulte [AccessDBProviderSample04](./accessdbprovidersample04.md).
> -   Classe [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Consulte [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Para obter mais informações sobre como escolher qual classe de provedor deve ser derivada com base nos recursos do provedor, consulte [projetando seu provedor do Windows PowerShell](./provider-types.md).

Este exemplo demonstra o seguinte:

- Declarando o atributo `CmdletProvider`.

- Definindo uma classe de provedor que deriva da classe [System. Management. Automation. Provider. mycmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

- Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. NewDrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) para alterar o comportamento do cmdlet `New-PSDrive`, permitindo que o usuário crie novas unidades. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `New-PSDrive`.)

- Substituindo o método [System. Management. Automation. Provider. Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) para dar suporte à remoção de unidades existentes.

- Substituindo o método [System. Management. Automation. Provider. docmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) para alterar o comportamento do cmdlet `Get-Item`, permitindo que o usuário recupere itens do armazenamento de dados. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Get-Item`.)

- Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) para alterar o comportamento do cmdlet `Set-Item`, permitindo que o usuário atualize os itens no repositório de dados. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Get-Item`.)

- Substituindo o método [System. Management. Automation. Provider. docmdletprovider. myexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) para alterar o comportamento do cmdlet `Test-Path`. (Este exemplo não mostra como adicionar parâmetros dinâmicos ao cmdlet `Test-Path`.)

- Substituindo o método [System. Management. Automation. Provider. createcmdletprovider. Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) para determinar se o caminho fornecido é válido.

## <a name="example"></a>Exemplo

Este exemplo mostra como substituir os métodos necessários para obter e definir itens em um banco de dados do Microsoft Access.

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Provider. createcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Criando seu provedor do Windows PowerShell](./provider-types.md)
