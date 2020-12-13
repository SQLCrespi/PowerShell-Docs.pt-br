---
ms.date: 09/13/2016
ms.topic: reference
title: Referência do Windows PowerShell
description: Referência do Windows PowerShell
ms.openlocfilehash: 9c1547ac5ec5134c99aa9213e6aaca1af8d5b3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390228"
---
# <a name="windows-powershell-reference"></a>Referência do Windows PowerShell

O Windows PowerShell é um ambiente conectado à estrutura Microsoft .NET projetado para automação administrativa. O Windows PowerShell fornece uma nova abordagem para a criação de comandos, a composição de soluções e a criação de ferramentas de gerenciamento baseadas em interface gráfica do usuário.

O Windows PowerShell permite que um administrador de sistema Automatize a administração de recursos do sistema pela execução de comandos diretamente ou por meio de scripts.

## <a name="developer-audience"></a>Público do desenvolvedor

O SDK (Software Development Kit) do Windows PowerShell foi escrito para desenvolvedores de comando que exigem informações de referência sobre as APIs fornecidas pelo Windows PowerShell. Os desenvolvedores de comando usam o Windows PowerShell para criar comandos e provedores que estendem as tarefas que podem ser executadas pelo Windows PowerShell.

## <a name="windows-powershell-resources"></a>Recursos do Windows PowerShell

Além do SDK do Windows PowerShell, os recursos a seguir fornecem mais informações.

[Introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell) Fornece uma introdução ao Windows PowerShell: a linguagem, os cmdlets, os provedores e o uso de objetos.

[Escrevendo um módulo do Windows PowerShell](./module/writing-a-windows-powershell-module.md) Fornece informações e exemplos para administradores, desenvolvedores de scripts e desenvolvedores de cmdlets que precisam empacotar e distribuir suas soluções do Windows PowerShell usando módulos do Windows PowerShell.

[Escrevendo um cmdlet do Windows PowerShell](./cmdlet/writing-a-windows-powershell-cmdlet.md) Fornece informações e exemplos de código para gerentes de programa que estão criando cmdlets e para desenvolvedores que estão implementando código de cmdlet.

[Blog da equipe do Windows PowerShell](https://devblogs.microsoft.com/powershell/) O melhor recurso para aprender e colaborar com outros usuários do Windows PowerShell. Leia o blog da equipe do Windows PowerShell e ingresse no fórum de usuário do Windows PowerShell (Microsoft. Public. Windows. PowerShell).
Use o Windows Live Search para encontrar outros Blogs e recursos do Windows PowerShell. Em seguida, ao desenvolver sua experiência, colabore livremente suas ideias.

[Navegador de módulo do PowerShell](/powershell/module/) Fornece as versões mais recentes dos tópicos de ajuda da linha de comando.

## <a name="class-libraries"></a>Bibliotecas de classes

[System. Management. Automation](/dotnet/api/System.Management.Automation) esse namespace é o namespace raiz do Windows PowerShell. Ele contém as classes, as enumerações e as interfaces necessárias para implementar cmdlets personalizados. Em particular, a classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) é a classe base da qual todas as classes de cmdlet devem ser derivadas. Para obter mais informações sobre cmdlets, consulte.

[System. Management. Automation. Provider](/dotnet/api/System.Management.Automation.Provider) este namespace contém as classes, as enumerações e as interfaces necessárias para implementar um provedor do Windows PowerShell. Em particular, a classe [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) é a classe base da qual todas as classes de provedor do Windows PowerShell devem ser derivadas.

[Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) este namespace contém as classes para os cmdlets e provedores implementados pelo Windows PowerShell. Da mesma forma, é recomendável que você crie um *seu*. Namespace de comandos para os cmdlets que você implementa.

[System. Management. Automation. host](/dotnet/api/System.Management.Automation.Host) esse namespace contém as classes, enumerações e interfaces que o cmdlet usa para definir a interação entre o usuário e o Windows PowerShell.

[System. Management. Automation. Internal](/dotnet/api/System.Management.Automation.Internal) este namespace contém as classes base usadas por outras classes de namespace. Por exemplo, a classe [System. Management. Automation. Internal. Cmdletmetadataattribute](/dotnet/api/System.Management.Automation.Internal.CmdletMetadataAttribute) é a classe base para a classe [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .

[System. Management. Automation. Runspaces](/dotnet/api/System.Management.Automation.Runspaces) este namespace contém as classes, enumerações e interfaces usadas para criar um runspace do Windows PowerShell. Nesse contexto, o runspace do Windows PowerShell é o contexto no qual um ou mais pipelines do Windows PowerShell invocam cmdlets. Ou seja, os cmdlets funcionam dentro do contexto de um runspace do Windows PowerShell. Para obter mais informações aboutWindows de espaços de Tróia do PowerShell, consulte espaços de informações do [Windows PowerShell](hosting/creating-runspaces.md).
