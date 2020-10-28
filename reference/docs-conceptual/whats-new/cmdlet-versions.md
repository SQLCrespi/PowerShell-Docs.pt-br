---
ms.date: 02/03/2020
keywords: powershell,core
title: Histórico de versões de módulos e cmdlets
description: Este artigo lista os módulos e os cmdlets incluídos em várias versões do PowerShell.
ms.openlocfilehash: cefd84c5d3785d19670ee649f5af951d5975912c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501653"
---
# <a name="release-history-of-modules-and-cmdlets"></a>Histórico de versões de módulos e cmdlets

Este artigo lista os módulos e os cmdlets incluídos em várias versões do PowerShell. Este é um resumo das informações encontradas nessas notas sobre a versão. É possível encontrar informações mais detalhadas nas notas sobre a versão:

- [Novidades do PowerShell Core 6.2](what-s-new-in-powershell-core-62.md)
- [Novidades do PowerShell Core 6.1](what-s-new-in-powershell-core-61.md)
- [Novidades do PowerShell Core 6.0](what-s-new-in-powershell-core-60.md)
- [Alterações da falha no PowerShell Core 6.0](breaking-changes-ps6.md)
- [Problemas conhecidos do PowerShell Core 6.0](known-issues-ps6.md)

Este é um trabalho em andamento. Precisamos da sua ajuda para manter estas informações atualizadas.

## <a name="module-release-history"></a>Histórico de versões do módulo

|         Nome do módulo/Versão do PS          |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| ----------------------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| CimCmdlets                                | &check; | &check; | &check; | &check; | Somente Windows |
| ISE (introduzido em 2.0)                   | &check; |         |         |         | Somente Windows |
| Microsoft.PowerShell.Archive              | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Core                 | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Diagnostics          | &check; | &check; | &check; | &check; | Somente Windows |
| Microsoft.PowerShell.Host                 | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.LocalAccounts        | &check; |         |         |         | Somente Windows |
| Microsoft.PowerShell.Management           | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.ODataUtils           | &check; |         |         |         | Somente Windows |
| Microsoft.PowerShell.Operation.Validation | &check; |         |         |         | Somente Windows |
| Microsoft.PowerShell.Security             | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Utility              | &check; | &check; | &check; | &check; |              |
| Microsoft.WsMan.Management                | &check; | &check; | &check; | &check; | Somente Windows |
| PackageManagement                         | &check; | &check; | &check; | &check; |              |
| PowershellGet                             | &check; | &check; | &check; | &check; |              |
| PSDesiredStateConfiguration               | &check; | &check; | &check; | &check; |              |
| PSDiagnostics                             | &check; | &check; | &check; | &check; | Somente Windows |
| PSReadline 1.x                            | &check; |         |         |         | Somente Windows |
| PSReadline 2.x                            |         | &check; | &check; | &check; |              |
| PSScheduledJob                            | &check; |         |         |         | Somente Windows |
| PSWorkflow                                | &check; |         |         |         | Somente Windows |
| PSWorkflowUtility                         | &check; |         |         |         | Somente Windows |
| ThreadJob                                 |         | &check; | &check; | &check; | Pode ser instalado no PowerShell 5.1 |

## <a name="cmdlet-release-history"></a>Histórico de versões de cmdlets

### <a name="cimcmdlets"></a>CimCmdlets

|         Nome do cmdlet         |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| --------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Export-BinaryMiLog          | &check; | &check; | &check; | &check; | Somente Windows |
| Get-CimAssociatedInstance   | &check; | &check; | &check; | &check; | Somente Windows |
| Get-CimClass                | &check; | &check; | &check; | &check; | Somente Windows |
| Get-CimInstance             | &check; | &check; | &check; | &check; | Somente Windows |
| Get-CimSession              | &check; | &check; | &check; | &check; | Somente Windows |
| Import-BinaryMiLog          | &check; | &check; | &check; | &check; | Somente Windows |
| Invoke-CimMethod            | &check; | &check; | &check; | &check; | Somente Windows |
| New-CimInstance             | &check; | &check; | &check; | &check; | Somente Windows |
| New-CimSession              | &check; | &check; | &check; | &check; | Somente Windows |
| New-CimSessionOption        | &check; | &check; | &check; | &check; | Somente Windows |
| Register-CimIndicationEvent | &check; | &check; | &check; | &check; | Somente Windows |
| Remove-CimInstance          | &check; | &check; | &check; | &check; | Somente Windows |
| Remove-CimSession           | &check; | &check; | &check; | &check; | Somente Windows |
| Set-CimInstance             | &check; | &check; | &check; | &check; | Somente Windows |

### <a name="ise-introduced-in-20"></a>ISE (introduzido em 2.0)

|    Nome do cmdlet    |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| ----------------- | :-----: | :--- | :---: | :---: | ------------ |
| Get-IseSnippet    | &check; |      |       |       | Somente Windows |
| Import-IseSnippet | &check; |      |       |       | Somente Windows |
| New-IseSnippet    | &check; |      |       |       | Somente Windows |

### <a name="microsoftpowershellarchive"></a>Microsoft.PowerShell.Archive

|   Nome do cmdlet    |   5.1   |   6.x   |   7.0   |   7.1   | Observação |
| ---------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Compress-Archive | &check; | &check; | &check; | &check; |      |
| Expand-Archive   | &check; | &check; | &check; | &check; |      |

### <a name="microsoftpowershellcore"></a>Microsoft.PowerShell.Core

|            Nome do cmdlet            |   5.1   |   6.x   |   7.0   |   7.1   |            Observação            |
| --------------------------------- | :-----: | :-----: | :-----: | :-----: | -------------------------- |
| Add-History                       | &check; | &check; | &check; | &check; |                            |
| Add-PSSnapin                      | &check; |         |         |         | Somente Windows               |
| Clear-History                     | &check; | &check; | &check; | &check; |                            |
| Clear-Host                        | &check; | &check; | &check; | &check; |                            |
| Connect-PSSession                 | &check; | &check; | &check; | &check; | Somente Windows               |
| Debug-Job                         | &check; | &check; | &check; | &check; |                            |
| Disable-ExperimentalFeature       |         |   6.2   | &check; | &check; |                            |
| Disable-PSRemoting                | &check; | &check; | &check; | &check; | Somente Windows               |
| Disable-PSSessionConfiguration    | &check; | &check; | &check; | &check; | Somente Windows               |
| Disconnect-PSSession              | &check; | &check; | &check; | &check; | Somente Windows               |
| Enable-ExperimentalFeature        |         |   6.2   | &check; | &check; |                            |
| Enable-PSRemoting                 | &check; | &check; | &check; | &check; | Somente Windows               |
| Disable-PSSessionConfiguration     | &check; | &check; | &check; | &check; | Somente Windows               |
| Enter-PSHostProcess               | &check; | &check; | &check; | &check; | Suporte adicionado para Linux em 6.2 |
| Enter-PSSession                   | &check; | &check; | &check; | &check; |                            |
| Exit-PSHostProcess                | &check; | &check; | &check; | &check; | Suporte adicionado para Linux em 6.2 |
| Exit-PSSession                    | &check; | &check; | &check; | &check; |                            |
| Export-Console                    | &check; |         |         |         | Somente Windows               |
| Export-ModuleMember               | &check; | &check; | &check; | &check; |                            |
| ForEach-Object                    | &check; | &check; | &check; | &check; |                            |
| Get-Command                       | &check; | &check; | &check; | &check; |                            |
| Get-ExperimentalFeature           |         |   6.2   | &check; | &check; |                            |
| Get-Help                          | &check; | &check; | &check; | &check; |                            |
| Get-History                       | &check; | &check; | &check; | &check; |                            |
| Get-Job                           | &check; | &check; | &check; | &check; |                            |
| Get-Module                        | &check; | &check; | &check; | &check; |                            |
| Get-PSHostProcessInfo             | &check; | &check; | &check; | &check; | Suporte adicionado para Linux em 6.2 |
| Get-PSSession                     | &check; | &check; | &check; | &check; |                            |
| Get-PSSessionCapability           | &check; | &check; | &check; | &check; |                            |
| Get-PSSessionConfiguration        | &check; | &check; | &check; | &check; |                            |
| Get-PSSnapin                      | &check; |         |         |         | Somente Windows               |
| Get-Verb                          | &check; |         |         |         | Movido para Microsoft.PowerShell.Utility 6.0+ |
| Import-Module                     | &check; | &check; | &check; | &check; |                            |
| Invoke-Command                    | &check; | &check; | &check; | &check; |                            |
| Invoke-History                    | &check; | &check; | &check; | &check; |                            |
| New-Module                        | &check; | &check; | &check; | &check; |                            |
| New-ModuleManifest                | &check; | &check; | &check; | &check; |                            |
| New-PSRoleCapabilityFile          | &check; | &check; | &check; | &check; |                            |
| New-PSSession                     | &check; | &check; | &check; | &check; |                            |
| New-PSSessionConfigurationFile    | &check; | &check; | &check; | &check; | Somente Windows               |
| New-PSSessionOption               | &check; | &check; | &check; | &check; |                            |
| New-PSTransportOption             | &check; | &check; | &check; | &check; |                            |
| Out-Default                       | &check; | &check; | &check; | &check; |                            |
| Out-Host                          | &check; | &check; | &check; | &check; |                            |
| Out-Null                          | &check; | &check; | &check; | &check; |                            |
| Receive-Job                       | &check; | &check; | &check; | &check; |                            |
| Receive-PSSession                 | &check; | &check; | &check; | &check; | Somente Windows               |
| Register-ArgumentCompleter        | &check; | &check; | &check; | &check; |                            |
| Register-PSSessionConfiguration   | &check; | &check; | &check; | &check; | Somente Windows               |
| Remove-Job                        | &check; | &check; | &check; | &check; |                            |
| Remove-Module                     | &check; | &check; | &check; | &check; |                            |
| Remove-PSSession                  | &check; | &check; | &check; | &check; |                            |
| Remove-PSSnapin                   | &check; |         |         |         | Somente Windows               |
| Resume-Job                        | &check; |         |         |         |                            |
| Save-Help                         | &check; | &check; | &check; | &check; |                            |
| Set-PSDebug                       | &check; | &check; | &check; | &check; |                            |
| Set-PSSessionConfiguration        | &check; | &check; | &check; | &check; | Somente Windows               |
| Set-StrictMode                    | &check; | &check; | &check; | &check; |                            |
| Start-Job                         | &check; | &check; | &check; | &check; |                            |
| Stop-Job                          | &check; | &check; | &check; | &check; |                            |
| Suspend-Job                       | &check; |         |         |         | Somente Windows               |
| Test-ModuleManifest               | &check; | &check; | &check; | &check; |                            |
| Test-PSSessionConfigurationFile   | &check; | &check; | &check; | &check; | Somente Windows               |
| Unregister-PSSessionConfiguration | &check; | &check; | &check; | &check; | Somente Windows               |
| Update-Help                       | &check; | &check; | &check; | &check; |                            |
| Wait-Job                          | &check; | &check; | &check; | &check; |                            |
| Where-Object                      | &check; | &check; | &check; | &check; |                            |

### <a name="microsoftpowershelldiagnostics"></a>Microsoft.PowerShell.Diagnostics

|  Nome do cmdlet   |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| -------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Export-Counter | &check; |         |         |         | Somente Windows |
| Get-Counter    | &check; |         | &check; | &check; | Somente Windows |
| Get-WinEvent   | &check; | &check; | &check; | &check; | Somente Windows |
| Import-Counter | &check; |         |         |         | Somente Windows |
| New-WinEvent   | &check; | &check; | &check; | &check; | Somente Windows |

### <a name="microsoftpowershellhost"></a>Microsoft.PowerShell.Host

|   Nome do cmdlet    |   5.1   |   6.x   |   7.0   |   7.1   | Observação |
| ---------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Start-Transcript | &check; | &check; | &check; | &check; |      |
| Stop-Transcript  | &check; | &check; | &check; | &check; |      |

### <a name="microsoftpowershelllocalaccounts"></a>Microsoft.PowerShell.LocalAccounts

|       Nome do cmdlet       |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| ----------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Add-LocalGroupMember    | &check; |      |       |       | Somente Windows |
| Disable-LocalUser       | &check; |      |       |       | Somente Windows |
| Enable-LocalUser        | &check; |      |       |       | Somente Windows |
| Get-LocalGroup          | &check; |      |       |       | Somente Windows |
| Get-LocalGroupMember    | &check; |      |       |       | Somente Windows |
| Get-LocalUser           | &check; |      |       |       | Somente Windows |
| New-LocalGroup          | &check; |      |       |       | Somente Windows |
| New-LocalUser           | &check; |      |       |       | Somente Windows |
| Remove-LocalGroup       | &check; |      |       |       | Somente Windows |
| Remove-LocalGroupMember | &check; |      |       |       | Somente Windows |
| Remove-LocalUser        | &check; |      |       |       | Somente Windows |
| Rename-LocalGroup       | &check; |      |       |       | Somente Windows |
| Rename-LocalUser        | &check; |      |       |       | Somente Windows |
| Set-LocalGroup          | &check; |      |       |       | Somente Windows |
| Set-LocalUser           | &check; |      |       |       | Somente Windows |

### <a name="microsoftpowershellmanagement"></a>Microsoft.PowerShell.Management

|          Nome do cmdlet          |   5.1   |   6.x   |   7.0   |   7.1   |               Observação               |
| ----------------------------- | :-----: | :-----: | :-----: | :-----: | -------------------------------- |
| Add-Computer                  | &check; |         |         |         | Somente Windows                     |
| Add-Content                   | &check; | &check; | &check; | &check; |                                  |
| Checkpoint-Computer           | &check; |         |         |         | Somente Windows                     |
| Clear-Content                 | &check; | &check; | &check; | &check; |                                  |
| Clear-EventLog                | &check; |         |         |         | Somente Windows                     |
| Clear-Item                    | &check; | &check; | &check; | &check; |                                  |
| Clear-ItemProperty            | &check; | &check; | &check; | &check; |                                  |
| Clear-RecycleBin              | &check; |         | &check; | &check; | Somente Windows                     |
| Complete-Transaction          | &check; |         |         |         | Somente Windows                     |
| Convert-Path                  | &check; | &check; | &check; | &check; |                                  |
| Copy-Item                     | &check; | &check; | &check; | &check; |                                  |
| Copy-ItemProperty             | &check; | &check; | &check; | &check; |                                  |
| Debug-Process                 | &check; | &check; | &check; | &check; |                                  |
| Disable-ComputerRestore       | &check; |         |         |         | Somente Windows                     |
| Enable-ComputerRestore        | &check; |         |         |         | Somente Windows                     |
| Get-ChildItem                 | &check; | &check; | &check; | &check; |                                  |
| Get-Clipboard                 | &check; |         | &check; | &check; | Não há suporte no macOS           |
| Get-ComputerInfo              | &check; | &check; | &check; | &check; |                                  |
| Get-ComputerRestorePoint      | &check; |         |         |         | Somente Windows                     |
| Get-Content                   | &check; | &check; | &check; | &check; |                                  |
| Get-ControlPanelItem          | &check; |         |         |         | Somente Windows                     |
| Get-EventLog                  | &check; |         |         |         | Somente Windows                     |
| Get-HotFix                    | &check; |         | &check; | &check; | Somente Windows                     |
| Get-Item                      | &check; | &check; | &check; | &check; |                                  |
| Get-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| Get-ItemPropertyValue         | &check; | &check; | &check; | &check; |                                  |
| Get-Location                  | &check; | &check; | &check; | &check; |                                  |
| Get-Process                   | &check; | &check; | &check; | &check; |                                  |
| Get-PSDrive                   | &check; | &check; | &check; | &check; |                                  |
| Get-PSProvider                | &check; | &check; | &check; | &check; |                                  |
| Get-Service                   | &check; | &check; | &check; | &check; | Somente Windows                     |
| Get-TimeZone                  | &check; | &check; | &check; | &check; |                                  |
| Get-Transaction               | &check; |         |         |         | Somente Windows                     |
| Get-WmiObject                 | &check; |         |         |         | Somente Windows                     |
| Invoke-Item                   | &check; | &check; | &check; | &check; |                                  |
| Invoke-WmiMethod              | &check; |         |         |         | Somente Windows                     |
| Join-Path                     | &check; | &check; | &check; | &check; |                                  |
| Limit-EventLog                | &check; |         |         |         | Somente Windows                     |
| Move-Item                     | &check; | &check; | &check; | &check; |                                  |
| Move-ItemProperty             | &check; | &check; | &check; | &check; |                                  |
| New-EventLog                  | &check; |         |         |         | Somente Windows                     |
| New-Item                      | &check; | &check; | &check; | &check; |                                  |
| New-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| New-PSDrive                   | &check; | &check; | &check; | &check; |                                  |
| New-Service                   | &check; | &check; | &check; | &check; | Somente Windows                     |
| New-WebServiceProxy           | &check; |         |         |         | Somente Windows                     |
| Pop-Location                  | &check; | &check; | &check; | &check; |                                  |
| Push-Location                 | &check; | &check; | &check; | &check; |                                  |
| Register-WmiEvent             | &check; |         |         |         | Somente Windows                     |
| Remove-Computer               | &check; |         |         |         | Somente Windows                     |
| Remove-EventLog               | &check; |         |         |         | Somente Windows                     |
| Remove-Item                   | &check; | &check; | &check; | &check; |                                  |
| Remove-ItemProperty           | &check; | &check; | &check; | &check; |                                  |
| Remove-PSDrive                | &check; | &check; | &check; | &check; |                                  |
| Remove-Service                |         | &check; | &check; | &check; | Somente Windows                     |
| Remove-WmiObject              | &check; |         |         |         | Somente Windows                     |
| Rename-Computer               | &check; | &check; | &check; | &check; |                                  |
| Rename-Item                   | &check; | &check; | &check; | &check; |                                  |
| Rename-ItemProperty           | &check; | &check; | &check; | &check; |                                  |
| Reset-ComputerMachinePassword | &check; |         |         |         | Somente Windows                     |
| Resolve-Path                  | &check; | &check; | &check; | &check; |                                  |
| Restart-Computer              | &check; | &check; | &check; | &check; | Suporte para o Linux/macOS adicionado na versão 7.1 |
| Restart-Service               | &check; | &check; | &check; | &check; | Somente Windows                     |
| Restore-Computer              | &check; |         |         |         | Somente Windows                     |
| Resume-Service                | &check; | &check; | &check; | &check; | Somente Windows                     |
| Set-Clipboard                 | &check; |         | &check; | &check; |                                  |
| Set-Content                   | &check; | &check; | &check; | &check; |                                  |
| Set-Item                      | &check; | &check; | &check; | &check; |                                  |
| Set-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| Set-Location                  | &check; | &check; | &check; | &check; |                                  |
| Set-Service                   | &check; | &check; | &check; | &check; | Somente Windows                     |
| Set-TimeZone                  | &check; | &check; | &check; | &check; |                                  |
| Set-WmiInstance               | &check; |         |         |         | Somente Windows                     |
| Show-ControlPanelItem         | &check; |         |         |         | Somente Windows                     |
| Show-EventLog                 | &check; |         |         |         | Somente Windows                     |
| Split-Path                    | &check; | &check; | &check; | &check; |                                  |
| Start-Process                 | &check; | &check; | &check; | &check; |                                  |
| Start-Service                 | &check; | &check; | &check; | &check; | Somente Windows                     |
| Start-Transaction             | &check; |         |         |         | Somente Windows                     |
| Stop-Computer                 | &check; | &check; | &check; | &check; | Suporte para o Linux/macOS adicionado na versão 7.1 |
| Stop-Process                  | &check; | &check; | &check; | &check; |                                  |
| Stop-Service                  | &check; | &check; | &check; | &check; | Somente Windows                     |
| Suspend-Service               | &check; | &check; | &check; | &check; | Somente Windows                     |
| Test-ComputerSecureChannel    | &check; |         |         |         | Somente Windows                     |
| Test-Connection               | &check; | &check; | &check; | &check; |                                  |
| Test-Path                     | &check; | &check; | &check; | &check; |                                  |
| Undo-Transaction              | &check; |         |         |         | Somente Windows                     |
| Use-Transaction               | &check; |         |         |         | Somente Windows                     |
| Wait-Process                  | &check; | &check; | &check; | &check; | Não funciona no Linux/macOS     |
| Write-EventLog                | &check; |         |         |         | Somente Windows                     |

### <a name="microsoftpowershellodatautils"></a>Microsoft.PowerShell.ODataUtils

|        Nome do cmdlet        |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| ------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Export-ODataEndpointProxy | &check; |      |       |       | Somente Windows |

### <a name="microsoftpowershelloperationvalidation"></a>Microsoft.PowerShell.Operation.Validation

|        Nome do cmdlet         |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| -------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Get-OperationValidation    | &check; |      |       |       | Somente Windows |
| Invoke-OperationValidation | &check; |      |       |       | Somente Windows |

### <a name="microsoftpowershellsecurity"></a>Microsoft.PowerShell.Security

|        Nome do cmdlet        |   5.1   |   6.x   |   7.0   |   7.1   |                  Observação                   |
| ------------------------- | :-----: | :-----: | :-----: | :-----: | --------------------------------------- |
| ConvertFrom-SecureString  | &check; | &check; | &check; | &check; |                                         |
| ConvertTo-SecureString    | &check; | &check; | &check; | &check; |                                         |
| Get-Acl                   | &check; | &check; | &check; | &check; | Somente Windows                            |
| Get-AuthenticodeSignature | &check; | &check; | &check; | &check; | Somente Windows                            |
| Get-CmsMessage            | &check; | &check; | &check; | &check; | Suporte para Linux/macOS adicionado no 7.1    |
| Get-Credential            | &check; | &check; | &check; | &check; |                                         |
| Get-ExecutionPolicy       | &check; | &check; | &check; | &check; | Retorna **Irrestrito** no Linux/macOS |
| Get-PfxCertificate        | &check; | &check; | &check; | &check; |                                         |
| New-FileCatalog           | &check; | &check; | &check; | &check; | Somente Windows                            |
| Protect-CmsMessage        | &check; | &check; | &check; | &check; | Suporte para Linux/macOS adicionado no 7.1    |
| Set-Acl                   | &check; | &check; | &check; | &check; | Somente Windows                            |
| Set-AuthenticodeSignature | &check; | &check; | &check; | &check; | Somente Windows                            |
| Set-ExecutionPolicy       | &check; | &check; | &check; | &check; | Não tem efeito no Linux/macOS             |
| Test-FileCatalog          | &check; | &check; | &check; | &check; | Somente Windows                            |
| Unprotect-CmsMessage      | &check; | &check; | &check; | &check; | Suporte para Linux/macOS adicionado no 7.1    |

### <a name="microsoftpowershellutility"></a>Microsoft.PowerShell.Utility

|        Nome do cmdlet        |   5.1   |   6.x   |   7.0   |   7.1   |                   Observação                    |
| ------------------------- | :-----: | :-----: | :-----: | :-----: | ----------------------------------------- |
| Add-Member                | &check; | &check; | &check; | &check; |                                           |
| Add-Type                  | &check; | &check; | &check; | &check; |                                           |
| Clear-Variable            | &check; | &check; | &check; | &check; |                                           |
| Compare-Object            | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Csv           | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Json          | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Markdown      |         |   6.1   | &check; | &check; |                                           |
| ConvertFrom-SddlString    | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-String        | &check; |         |         |         |                                           |
| ConvertFrom-StringData    | &check; | &check; | &check; | &check; |                                           |
| Convert-String            | &check; |         |         |         |                                           |
| ConvertTo-Csv             | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Html            | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Json            | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Xml             | &check; | &check; | &check; | &check; |                                           |
| Debug-Runspace            | &check; | &check; | &check; | &check; |                                           |
| Disable-PSBreakpoint      | &check; | &check; | &check; | &check; |                                           |
| Disable-RunspaceDebug     | &check; | &check; | &check; | &check; |                                           |
| Enable-PSBreakpoint       | &check; | &check; | &check; | &check; |                                           |
| Enable-RunspaceDebug      | &check; | &check; | &check; | &check; |                                           |
| Export-Alias              | &check; | &check; | &check; | &check; |                                           |
| Export-Clixml             | &check; | &check; | &check; | &check; |                                           |
| Export-Csv                | &check; | &check; | &check; | &check; |                                           |
| Export-FormatData         | &check; | &check; | &check; | &check; |                                           |
| Export-PSSession          | &check; | &check; | &check; | &check; |                                           |
| Format-Custom             | &check; | &check; | &check; | &check; |                                           |
| Format-Hex                | &check; | &check; | &check; | &check; |                                           |
| Format-List               | &check; | &check; | &check; | &check; |                                           |
| Format-Table              | &check; | &check; | &check; | &check; |                                           |
| Format-Wide               | &check; | &check; | &check; | &check; |                                           |
| Get-Alias                 | &check; | &check; | &check; | &check; |                                           |
| Get-Culture               | &check; | &check; | &check; | &check; |                                           |
| Get-Date                  | &check; | &check; | &check; | &check; |                                           |
| Get-Error                 |         |         | &check; | &check; |                                           |
| Get-Event                 | &check; | &check; | &check; | &check; | Não há fontes de evento disponíveis no Linux/macOS |
| Get-EventSubscriber       | &check; | &check; | &check; | &check; |                                           |
| Get-FileHash              | &check; | &check; | &check; | &check; |                                           |
| Get-FormatData            | &check; | &check; | &check; | &check; |                                           |
| Get-Host                  | &check; | &check; | &check; | &check; |                                           |
| Get-MarkdownOption        |         |   6.1   | &check; | &check; |                                           |
| Get-Member                | &check; | &check; | &check; | &check; |                                           |
| Get-PSBreakpoint          | &check; | &check; | &check; | &check; |                                           |
| Get-PSCallStack           | &check; | &check; | &check; | &check; |                                           |
| Get-Random                | &check; | &check; | &check; | &check; |                                           |
| Get-Runspace              | &check; | &check; | &check; | &check; |                                           |
| Get-RunspaceDebug         | &check; | &check; | &check; | &check; |                                           |
| Get-TraceSource           | &check; | &check; | &check; | &check; |                                           |
| Get-TypeData              | &check; | &check; | &check; | &check; |                                           |
| Get-UICulture             | &check; | &check; | &check; | &check; |                                           |
| Get-Unique                | &check; | &check; | &check; | &check; |                                           |
| Get-Uptime                |         | &check; | &check; | &check; |                                           |
| Get-Variable              | &check; | &check; | &check; | &check; |                                           |
| Get-Verb                  |         | &check; | &check; | &check; |                                           |
| Group-Object              | &check; | &check; | &check; | &check; |                                           |
| Import-Alias              | &check; | &check; | &check; | &check; |                                           |
| Import-Clixml             | &check; | &check; | &check; | &check; |                                           |
| Import-Csv                | &check; | &check; | &check; | &check; |                                           |
| Import-LocalizedData      | &check; | &check; | &check; | &check; |                                           |
| Import-PowerShellDataFile | &check; | &check; | &check; | &check; |                                           |
| Import-PSSession          | &check; | &check; | &check; | &check; |                                           |
| Invoke-Expression         | &check; | &check; | &check; | &check; |                                           |
| Invoke-RestMethod         | &check; | &check; | &check; | &check; |                                           |
| Invoke-WebRequest         | &check; | &check; | &check; | &check; |                                           |
| Join-String               |         | &check; | &check; | &check; |                                           |
| Measure-Command           | &check; | &check; | &check; | &check; |                                           |
| Measure-Object            | &check; | &check; | &check; | &check; |                                           |
| New-Alias                 | &check; | &check; | &check; | &check; |                                           |
| New-Event                 | &check; | &check; | &check; | &check; | Não há fontes de evento disponíveis no Linux/macOS |
| New-Guid                  | &check; | &check; | &check; | &check; |                                           |
| New-Object                | &check; | &check; | &check; | &check; |                                           |
| New-TemporaryFile         | &check; | &check; | &check; | &check; |                                           |
| New-TimeSpan              | &check; | &check; | &check; | &check; |                                           |
| New-Variable              | &check; | &check; | &check; | &check; |                                           |
| Out-File                  | &check; | &check; | &check; | &check; |                                           |
| Out-GridView              | &check; |         | &check; | &check; | Somente Windows                              |
| Out-Printer               | &check; |         | &check; | &check; |                                           |
| Out-String                | &check; | &check; | &check; | &check; |                                           |
| Read-Host                 | &check; | &check; | &check; | &check; |                                           |
| Register-EngineEvent      | &check; | &check; | &check; | &check; | Não há fontes de evento disponíveis no Linux/macOS |
| Register-ObjectEvent      | &check; | &check; | &check; | &check; |                                           |
| Remove-Alias              |         | &check; | &check; | &check; |                                           |
| Remove-Event              | &check; | &check; | &check; | &check; | Não há fontes de evento disponíveis no Linux/macOS |
| Remove-PSBreakpoint       | &check; | &check; | &check; | &check; |                                           |
| Remove-TypeData           | &check; | &check; | &check; | &check; |                                           |
| Remove-Variable           | &check; | &check; | &check; | &check; |                                           |
| Select-Object             | &check; | &check; | &check; | &check; |                                           |
| Select-String             | &check; | &check; | &check; | &check; |                                           |
| Select-Xml                | &check; | &check; | &check; | &check; |                                           |
| Send-MailMessage          | &check; | &check; | &check; | &check; |                                           |
| Set-Alias                 | &check; | &check; | &check; | &check; |                                           |
| Set-Date                  | &check; | &check; | &check; | &check; |                                           |
| Set-MarkdownOption        |         |   6.1   | &check; | &check; |                                           |
| Set-PSBreakpoint          | &check; | &check; | &check; | &check; |                                           |
| Set-TraceSource           | &check; | &check; | &check; | &check; |                                           |
| Set-Variable              | &check; | &check; | &check; | &check; |                                           |
| Show-Command              | &check; |         | &check; | &check; |                                           |
| Show-Markdown             |         |   6.1   | &check; | &check; |                                           |
| Sort-Object               | &check; | &check; | &check; | &check; |                                           |
| Start-Sleep               | &check; | &check; | &check; | &check; |                                           |
| Tee-Object                | &check; | &check; | &check; | &check; |                                           |
| Test-Json                 |         | &check; | &check; | &check; |                                           |
| Trace-Command             | &check; | &check; | &check; | &check; |                                           |
| Unblock-File              | &check; | &check; | &check; | &check; | Suporte adicionado para macOS na versão 7.0            |
| Unregister-Event          | &check; | &check; | &check; | &check; | Não há fontes de evento disponíveis no Linux/macOS |
| Update-FormatData         | &check; | &check; | &check; | &check; |                                           |
| Update-List               | &check; |         | &check; | &check; |                                           |
| Update-TypeData           | &check; | &check; | &check; | &check; |                                           |
| Wait-Debugger             | &check; | &check; | &check; | &check; |                                           |
| Wait-Event                | &check; | &check; | &check; | &check; |                                           |
| Write-Debug               | &check; | &check; | &check; | &check; |                                           |
| Write-Error               | &check; | &check; | &check; | &check; |                                           |
| Write-Host                | &check; | &check; | &check; | &check; |                                           |
| Write-Information         | &check; | &check; | &check; | &check; |                                           |
| Write-Output              | &check; | &check; | &check; | &check; |                                           |
| Write-Progress            | &check; | &check; | &check; | &check; |                                           |
| Write-Verbose             | &check; | &check; | &check; | &check; |                                           |
| Write-Warning             | &check; | &check; | &check; | &check; |                                           |

### <a name="microsoftwsmanmanagement"></a>Microsoft.WsMan.Management

|      Nome do cmdlet       |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| ---------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Connect-WSMan          | &check; | &check; | &check; | &check; | Somente Windows |
| Disable-WSManCredSSP   | &check; | &check; | &check; | &check; | Somente Windows |
| Disconnect-WSMan       | &check; | &check; | &check; | &check; | Somente Windows |
| Enable-WSManCredSSP    | &check; | &check; | &check; | &check; | Somente Windows |
| Get-WSManCredSSP       | &check; | &check; | &check; | &check; | Somente Windows |
| Get-WSManInstance      | &check; | &check; | &check; | &check; | Somente Windows |
| Invoke-WSManAction     | &check; | &check; | &check; | &check; | Somente Windows |
| New-WSManInstance      | &check; | &check; | &check; | &check; | Somente Windows |
| New-WSManSessionOption | &check; | &check; | &check; | &check; | Somente Windows |
| Remove-WSManInstance   | &check; | &check; | &check; | &check; | Somente Windows |
| Set-WSManInstance      | &check; | &check; | &check; | &check; | Somente Windows |
| Set-WSManQuickConfig   | &check; | &check; | &check; | &check; | Somente Windows |
| Test-WSMan             | &check; | &check; | &check; | &check; | Somente Windows |

### <a name="packagemanagement"></a>PackageManagement

|       Nome do cmdlet        |   5.1   |   6.x   |   7.0   |   7.1   | Observação |
| ------------------------ | :-----: | :-----: | :-----: | :-----: | ---- |
| Find-Package             | &check; | &check; | &check; | &check; |      |
| Find-PackageProvider     | &check; | &check; | &check; | &check; |      |
| Get-Package              | &check; | &check; | &check; | &check; |      |
| Get-PackageProvider      | &check; | &check; | &check; | &check; |      |
| Get-PackageSource        | &check; | &check; | &check; | &check; |      |
| Import-PackageProvider   | &check; | &check; | &check; | &check; |      |
| Install-Package          | &check; | &check; | &check; | &check; |      |
| Install-PackageProvider  | &check; | &check; | &check; | &check; |      |
| Register-PackageSource   | &check; | &check; | &check; | &check; |      |
| Save-Package             | &check; | &check; | &check; | &check; |      |
| Set-PackageSource        | &check; | &check; | &check; | &check; |      |
| Uninstall-Package        | &check; | &check; | &check; | &check; |      |
| Unregister-PackageSource | &check; | &check; | &check; | &check; |      |

### <a name="powershellget"></a>PowershellGet

|           Nome do cmdlet           |   5.1   |   6.x   |   7.0   |   7.1   | Observação |
| ------------------------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Find-Command                    | &check; | &check; | &check; | &check; |      |
| Find-DscResource                | &check; | &check; | &check; | &check; |      |
| Find-Module                     | &check; | &check; | &check; | &check; |      |
| Find-RoleCapability             | &check; | &check; | &check; | &check; |      |
| Find-Script                     | &check; | &check; | &check; | &check; |      |
| Get-CredsFromCredentialProvider |         | &check; | &check; | &check; |      |
| Get-InstalledModule             | &check; | &check; | &check; | &check; |      |
| Get-InstalledScript             | &check; | &check; | &check; | &check; |      |
| Get-PSRepository                | &check; | &check; | &check; | &check; |      |
| Install-Module                  | &check; | &check; | &check; | &check; |      |
| Install-Script                  | &check; | &check; | &check; | &check; |      |
| New-ScriptFileInfo              | &check; | &check; | &check; | &check; |      |
| Publish-Module                  | &check; | &check; | &check; | &check; |      |
| Publish-Script                  | &check; | &check; | &check; | &check; |      |
| Register-PSRepository           | &check; | &check; | &check; | &check; |      |
| Save-Module                     | &check; | &check; | &check; | &check; |      |
| Save-Script                     | &check; | &check; | &check; | &check; |      |
| Set-PSRepository                | &check; | &check; | &check; | &check; |      |
| Test-ScriptFileInfo             | &check; | &check; | &check; | &check; |      |
| Uninstall-Module                | &check; | &check; | &check; | &check; |      |
| Uninstall-Script                | &check; | &check; | &check; | &check; |      |
| Unregister-PSRepository         | &check; | &check; | &check; | &check; |      |
| Update-Module                   | &check; | &check; | &check; | &check; |      |
| Update-ModuleManifest           | &check; | &check; | &check; | &check; |      |
| Update-Script                   | &check; | &check; | &check; | &check; |      |
| Update-ScriptFileInfo           | &check; | &check; | &check; | &check; |      |

### <a name="psdesiredstateconfiguration"></a>PSDesiredStateConfiguration

|                Nome do cmdlet                 |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| ------------------------------------------ | :-----: | :-----: | :-----: | :-----: | ------------ |
| Disable-DscDebug                           | &check; |         |         |         | Somente Windows |
| Enable-DscDebug                            | &check; |         |         |         | Somente Windows |
| Get-DscConfiguration                       | &check; |         |         |         | Somente Windows |
| Get-DscConfigurationStatus                 | &check; |         |         |         | Somente Windows |
| Get-DscLocalConfigurationManager           | &check; |         |         |         | Somente Windows |
| Get-DscResource                            | &check; | &check; | &check; | &check; |              |
| Invoke-DscResource                         | &check; |         | &check; | &check; |              |
| New-DSCCheckSum                            | &check; | &check; | &check; | &check; |              |
| Publish-DscConfiguration                   | &check; |         |         |         | Somente Windows |
| Remove-DscConfigurationDocument            | &check; |         |         |         | Somente Windows |
| Restore-DscConfiguration                   | &check; |         |         |         | Somente Windows |
| Set-DscLocalConfigurationManager           | &check; |         |         |         | Somente Windows |
| Start-DscConfiguration                     | &check; |         |         |         | Somente Windows |
| Stop-DscConfiguration                      | &check; |         |         |         | Somente Windows |
| Test-DscConfiguration                      | &check; |         |         |         | Somente Windows |
| Update-DscConfiguration                    | &check; |         |         |         | Somente Windows |

### <a name="psdiagnostics"></a>PSDiagnostics

|         Nome do cmdlet          |   5.1   |   6.x   |   7.0   |   7.1   |     Observação     |
| ---------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Disable-PSTrace              | &check; |   6.2   | &check; | &check; | Somente Windows |
| Disable-PSWSManCombinedTrace | &check; |   6.2   | &check; | &check; | Somente Windows |
| Disable-WSManTrace           | &check; | &check; | &check; | &check; | Somente Windows |
| Enable-PSTrace               | &check; | &check; | &check; | &check; | Somente Windows |
| Enable-PSWSManCombinedTrace  | &check; | &check; | &check; | &check; | Somente Windows |
| Enable-WSManTrace            | &check; |   6.2   | &check; | &check; | Somente Windows |
| Get-LogProperties            | &check; |   6.2   | &check; | &check; | Somente Windows |
| Set-LogProperties            | &check; |   6.2   | &check; | &check; | Somente Windows |
| Start-Trace                  | &check; |   6.2   | &check; | &check; | Somente Windows |
| Stop-Trace                   | &check; |   6.2   | &check; | &check; | Somente Windows |

### <a name="psreadline"></a>PSReadline

|         Nome do cmdlet         |   5.1   |   6.x   |   7.0   |   7.1   | Observação |
| --------------------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Get-PSReadlineKeyHandler    | &check; | &check; | &check; | &check; |      |
| Get-PSReadlineOption        | &check; | &check; | &check; | &check; |      |
| PSConsoleHostReadline       | &check; | &check; | &check; | &check; |      |
| Remove-PSReadlineKeyHandler | &check; | &check; | &check; | &check; |      |
| Set-PSReadlineKeyHandler    | &check; | &check; | &check; | &check; |      |
| Set-PSReadlineOption        | &check; | &check; | &check; | &check; |      |

### <a name="psscheduledjob"></a>PSScheduledJob

|       Nome do cmdlet       |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| ----------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Add-JobTrigger          | &check; |      |       |       | Somente Windows |
| Disable-JobTrigger      | &check; |      |       |       | Somente Windows |
| Disable-ScheduledJob    | &check; |      |       |       | Somente Windows |
| Enable-JobTrigger       | &check; |      |       |       | Somente Windows |
| Enable-ScheduledJob     | &check; |      |       |       | Somente Windows |
| Get-JobTrigger          | &check; |      |       |       | Somente Windows |
| Get-ScheduledJob        | &check; |      |       |       | Somente Windows |
| Get-ScheduledJobOption  | &check; |      |       |       | Somente Windows |
| New-JobTrigger          | &check; |      |       |       | Somente Windows |
| New-ScheduledJobOption  | &check; |      |       |       | Somente Windows |
| Register-ScheduledJob   | &check; |      |       |       | Somente Windows |
| Remove-JobTrigger       | &check; |      |       |       | Somente Windows |
| Set-JobTrigger          | &check; |      |       |       | Somente Windows |
| Set-ScheduledJob        | &check; |      |       |       | Somente Windows |
| Set-ScheduledJobOption  | &check; |      |       |       | Somente Windows |
| Unregister-ScheduledJob | &check; |      |       |       | Somente Windows |

### <a name="psworkflow--psworkflowutility"></a>PSWorkflow & PSWorkflowUtility

|          Nome do cmdlet          |   5.1   | 6.x  |  7.0  |  7.1  |     Observação     |
| ----------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| New-PSWorkflowExecutionOption | &check; |      |       |       | Somente Windows |
| New-PSWorkflowSession         | &check; |      |       |       | Somente Windows |
| Invoke-AsWorkflow             | &check; |      |       |       | Somente Windows |

### <a name="threadjob"></a>ThreadJob

|   Nome do cmdlet   |  5.1  |   6.x   |   7.0   |   7.1   | Observação |
| --------------- | :---: | :-----: | :-----: | :-----: | ---- |
| Start-ThreadJob |       | &check; | &check; | &check; | Pode ser instalado no PowerShell 5.1 |
