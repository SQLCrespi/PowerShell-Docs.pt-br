---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Atualizar nós de um servidor de pull
description: Este artigo explica como atualizar nós gerenciados da DSC do Servidor de Pull
ms.openlocfilehash: 7256a0e1fdfaa8e56150c4f7299640bc95b82cee
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656767"
---
# <a name="update-nodes-from-a-pull-server"></a>Atualizar nós de um servidor de pull

As seções a seguir pressupõem que você já tenha configurado um servidor de pull. Se ainda não configurou, use os guias a seguir:

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)

Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status. Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente. Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.

## <a name="using-the-update-dscconfiguration-cmdlet"></a>Usando o cmdlet Update-DSCConfiguration

A partir do PowerShell 5.0, o cmdlet [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) força um nó a atualizar sua configuração do servidor de pull configurado no LCM.

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a>Usando Invoke-CIMMethod

No PowerShell 4.0, você ainda pode forçar manualmente um cliente de Pull para atualizar sua configuração usando [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod). O exemplo a seguir cria uma sessão CIM com as credenciais especificadas, invoca o método CIM apropriado e remove a sessão.

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a>Consulte Também

[PerformRequiredConfigurationChecks](../reference/mof-classes/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)
