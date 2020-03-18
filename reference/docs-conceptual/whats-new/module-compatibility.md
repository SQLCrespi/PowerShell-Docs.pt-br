---
title: Compatibilidade de módulo do PowerShell 7
ms.date: 02/03/2020
ms.openlocfilehash: 02095b8233b6fc7b6d2a30bcb841bfd831a50031
ms.sourcegitcommit: 1fa89ab20d14a61f139f1394c45aaedd5a7c5438
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2020
ms.locfileid: "78935183"
---
# <a name="powershell-7-module-compatibility"></a>Compatibilidade de módulo do PowerShell 7

Este artigo contém uma lista de módulos do PowerShell publicados pela Microsoft. Esses módulos fornecem gerenciamento e suporte para vários produtos e serviços da Microsoft. Os módulos foram atualizados para funcionar nativamente com o PowerShell 7 ou foram testados quanto à compatibilidade com o PowerShell 7. Esta lista será atualizada com novas informações à medida que mais módulos forem identificados e testados.

Se você tiver informações para compartilhar ou problemas com módulos específicos, registre o problema no [repositório WindowsCompatibility](https://github.com/PowerShell/WindowsCompatibility).

## <a name="windows-management-modules"></a>Módulos de gerenciamento do Windows

O módulo de gerenciamento do Windows é instalado de maneiras diferentes, dependendo da edição do Windows e de como o módulo foi empacotado nessa edição.

No Windows Server, use o nome do recurso com o cmdlet [Install-WindowsFeature](/powershell/module/servermanager/install-windowsfeature) como administrador. Por exemplo:

```powershell
Install-WindowsFeature -Name ActiveDirectory
```

No Windows 10, os módulos de gerenciamento do Windows são disponibilizados como **Recursos Opcionais do Windows** ou **Recursos do Windows**. Os comandos a seguir devem ser executados a partir de uma sessão com privilégios elevados usando **Executar como administrador**.


- Para os Recursos Opcionais do Windows

  Para obter uma lista de Recursos Opcionais, execute o seguinte comando:

  ```powershell
  Get-WindowsOptionalFeature -Online
  ```

  Para instalar o recurso:

  ```powershell
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Management-PowerShell
  ```

  Para obter mais informações, consulte:

  - [Get-WindowsOptionalFeature](/powershell/module/dism/get-windowsoptionalfeature)
  - [Enable-WindowsOptionalFeature](/powershell/module/dism/enable-windowsoptionalfeature)

- Para Recursos do Windows

  Para obter uma lista de Recursos do Windows, execute o seguinte comando:

  ```powershell
  Get-WindowsCapability -online
  ```

  Observe que o nome do pacote de recursos termina com `~~~~0.0.1.0`. Você deve usar o nome completo para instalar o recurso:

  ```powershell
  Add-WindowsCapability -Online -Name Rsat.ServerManager.Tools~~~~0.0.1.0
  ```

  Para obter mais informações, consulte:

  - [Get-WindowsCapability](/powershell/module/dism/get-windowscapability)
  - [Add-WindowsCapability](/powershell/module/dism/add-windowscapability)

### <a name="module-list"></a>Lista de módulos

| Nome do módulo                        | Status                               | SO com suporte                       |
| ---------------------------------- | ------------------------------------ | ---------------------------------- |
| Active Directory                    | Nativamente compatível                  | Windows Server 1809 e posteriores com RSAT-AD-PowerShell<br>Windows 10 1809 e posteriores com Rsat.ActiveDirectory.DS-LDS.Tools |
| ADFS                               | Não testado com a camada de compatibilidade    |                                    |
| AppBackgroundTask                  | Nativamente compatível                  | Windows 10 1903 e posteriores                   |
| AppLocker                          | Não testado com a camada de compatibilidade    |                                    |
| AppvClient                         | Não testado com a camada de compatibilidade    |                                    |
| Appx                               | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores |
| AssignedAccess                     | Nativamente compatível                  | Windows 10 1809 e posteriores                   |
| BestPractices                      | Não testado com a camada de compatibilidade    |                                    |
| BitLocker                          | Nativamente compatível                  | Windows Server 1809 e posteriores com BitLocker<br>Windows 10 1809 e posteriores |
| BitsTransfer                       | Nativamente compatível                  | Windows Server 20H1<br>Windows 10 20H1 |
| BootEventCollector                 | Não testado com a camada de compatibilidade    |                                        |
| BranchCache                        | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores |
| CimCmdlets                         | Nativamente compatível                  | Integrado ao PowerShell 7 |
| ClusterAwareUpdating               | Não testado com a camada de compatibilidade    |                         |
| ConfigCI                           | Não testado com a camada de compatibilidade    |                         |
| Defender                           | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores  |
| DeliveryOptimization               | Nativamente compatível                  | Windows Server 1903 e posteriores<br>Windows 10 1903 e posteriores  |
| DFSN                               | Nativamente compatível                  | Windows Server 1809 e posteriores com FS-DFS-Namespace<br>Windows 10 1809 e posteriores com Rsat.FailoverCluster.Management.Tools |
| DFSR                               | Não testado com a camada de compatibilidade    |                                   |
| DhcpServer                         | Não testado com a camada de compatibilidade    |                                   |
| DirectAccessClientComponents       | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores  |
| Dism                               | Nativamente compatível                  | Windows Server 1903 e posteriores<br>Windows 10 1903 e posteriores  |
| DnsClient                          | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores  |
| DnsServer                          | Nativamente compatível                  | Windows Server 1809 e posteriores com DNS ou RSAT-DNS-Server<br>Windows 10 1809 e posteriores com Rsat.Dns.Tools |
| EventTracingManagement             | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores  |
| FailoverClusters                   | Não testado com a camada de compatibilidade    |                                  |
| FailoverClusterSet                 | Não testado com a camada de compatibilidade    |                                  |
| FileServerResourceManager          | Nativamente compatível                  | Windows Server 1809 e posteriores com FS-Resource-Manager |
| GroupPolicy                        | Não testado com a camada de compatibilidade    |                                               |
| HgsClient                          | Nativamente compatível                  | Windows Server 1903 e posteriores com Hyper-V ou RSAT-Shielded-VM-Tools<br>Windows 10 1903 e posteriores com Rsat.Shielded.VM.Tools |
| HgsDiagnostics                     | Nativamente compatível                  | Windows Server 1809 e posteriores com Hyper-V ou RSAT-Shielded-VM-Tools<br>Windows 10 1809 e posteriores com Rsat.Shielded.VM.Tools |
| Hyper-v                            | Nativamente compatível                  | Windows Server 1809 e posteriores com Hyper-V-PowerShell<br>Windows 10 1809 e posteriores com Microsoft-Hyper-V-Management-PowerShell |
| IISAdministration                  | Não testado com a camada de compatibilidade    |                                               |
| Internacional                      | Nativamente compatível                  | Windows Server 1903 e posteriores<br>Windows 10 1903 e posteriores      |
| IpamServer                         | Não testado com a camada de compatibilidade    |                                               |
| iSCSI                              | Não testado com a camada de compatibilidade    |                                               |
| IscsiTarget                        | Não testado com a camada de compatibilidade    |                                               |
| ISE                                | Não testado com a camada de compatibilidade    |                                               |
| Kds                                | Nativamente compatível                  | Windows Server 20H1<br>Windows 10 20H1        |
| Microsoft.PowerShell.Archive       | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.PowerShell.Diagnostics   | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.PowerShell.Host          | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.PowerShell.LocalAccounts | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| Microsoft.PowerShell.Management    | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.PowerShell.ODataUtils    | Não testado com a camada de compatibilidade    |                                               |
| Microsoft.PowerShell.Security      | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.PowerShell.Utility       | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| Microsoft.WSMan.Management         | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| MMAgent                            | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| MPIO                               | Nativamente compatível                  | Windows Server 1809 e posteriores com Multipath-IO        |
| MsDtc                              | Não testado com a camada de compatibilidade    |                                               |
| NetAdapter                         | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetConnection                      | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetEventPacketCapture              | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetLbfo                            | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetLldpAgent                       | Não testado com a camada de compatibilidade    |                                               |
| NetNat                             | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetQos                             | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetSecurity                        | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetSwitchTeam                      | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetTCPIP                           | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetWNV                             | Não testado com a camada de compatibilidade    |                                               |
| NetworkConnectivityStatus          | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetworkController                  | Não testado com a camada de compatibilidade    |                                               |
| NetworkControllerDiagnostics       | Não testado com a camada de compatibilidade    |                                               |
| NetworkLoadBalancingClusters       | Não testado com a camada de compatibilidade    |                                               |
| NetworkSwitchManager               | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NetworkTransition                  | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| NFS                                | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores com Rsat.ServerManager.Tools |
| PackageManagement                  | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| PcsvDevice                         | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| PersistentMemory                   | Não testado com a camada de compatibilidade    |                                               |
| PKI                                | Não testado com a camada de compatibilidade    |                                               |
| PnpDevice                          | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| PowerShellGet                      | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| PrintManagement                    | Nativamente compatível                  | Windows Server 1903 e posteriores com Print-Services<br>Windows 10 1903 e posteriores  |
| ProcessMitigations                 | Nativamente compatível                  | Windows Server 1903 e posteriores<br>Windows 10 1903 e posteriores      |
| Provisionamento                       | Não testado com a camada de compatibilidade    |                                               |
| PSDesiredStateConfiguration        | Parcialmente                            | Integrado ao PowerShell 7                       |
| PSDiagnostics                      | Nativamente compatível                  | Integrado ao PowerShell 7                       |
| PSScheduledJob                     | Não testado com a camada de compatibilidade | Integrado ao PowerShell 5.1                     |
| PSWorkflow                         | Não testado com a camada de compatibilidade    |                                               |
| PSWorkflowUtility                  | Não testado com a camada de compatibilidade    |                                               |
| RemoteAccess                       | Não testado com a camada de compatibilidade    |                                               |
| RemoteDesktop                      | Não testado com a camada de compatibilidade    |                                               |
| ScheduledTasks                     | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| SecureBoot                         | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| ServerCore                         | Não testado com a camada de compatibilidade    |                                               |
| ServerManager                      | Não testado com a camada de compatibilidade    |                                               |
| ServerManagerTasks                 | Não testado com a camada de compatibilidade    |                                               |
| ShieldedVMDataFile                 | Nativamente compatível                  | Windows Server 1903 e posteriores com RSAT-Shielded-VM-Tools<br>Windows 10 1903 e posteriores com Rsat.Shielded.VM.Tools |
| ShieldedVMProvisioning             | Nativamente compatível                  | Windows Server 1809 e posteriores com HostGuardian<br>Windows 10 1809 e posteriores com HostGuardian  |
| ShieldedVMTemplate                 | Nativamente compatível                  | Windows Server 1809 e posteriores com RSAT-Shielded-VM-Tools<br>Windows 10 1809 e posteriores com Rsat.Shielded.VM.Tools |
| SmbShare                           | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| SmbWitness                         | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| SMISConfig                         | Nativamente compatível                  | Windows Server 1903 e posteriores com WindowsStorageManagementService |
| sms                                | Não testado com a camada de compatibilidade    |                                               |
| SoftwareInventoryLogging           | Nativamente compatível                  | Windows Server 1809 e posteriores                          |
| StartLayout                        | Nativamente compatível                  | Windows Server 1809 e posteriores com Experiência Desktop<br>Windows 10 1809 e posteriores |
| Armazenamento                            | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| StorageBusCache                    | Não testado com a camada de compatibilidade    |                                               |
| StorageMigrationService            | Não testado com a camada de compatibilidade    |                                               |
| StorageQOS                         | Nativamente compatível                  | Windows Server 1809 e posteriores com RSAT-Clustering-PowerShell<br>Windows 10 1809 e posteriores com Rsat.FailoverCluster.Management.Tools |
| StorageReplica                     | Não testado com a camada de compatibilidade    |                                               |
| SyncShare                          | Nativamente compatível                  | Windows Server 1809 e posteriores com FS-SyncShareService |
| SystemInsights                     | Não testado com a camada de compatibilidade    |                                               |
| TLS                                | Não testado com a camada de compatibilidade    |                                               |
| TroubleshootingPack                | Nativamente compatível                  | Windows 10 1903 e posteriores                              |
| TrustedPlatformModule              | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| UEV                                | Nativamente compatível                  | Windows Server ??versão futura do Server com Experiência Desktop??<br>Windows 10 1903 e posteriores |
| UpdateServices                     | Não testado com a camada de compatibilidade |                                               |
| VpnClient                          | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| Wdac                               | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| WebAdministration                  | Não testado com a camada de compatibilidade    |                                               |
| WHEA                               | Nativamente compatível                  | Windows Server 1903 e posteriores<br>Windows 10 1903 e posteriores      |
| WindowsDeveloperLicense            | Nativamente compatível                  | Windows Server 1809 e posteriores com Experiência Desktop<br>Windows 10 1809 e posteriores |
| WindowsErrorReporting              | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores      |
| WindowsSearch                      | Nativamente compatível                  | Windows 10 1903 e posteriores                              |
| WindowsServerBackup                | Nativamente compatível                  | Windows Server 19H2 com Windows-Server-Backup |
| WindowsUpdate                      | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores       |
| WindowsUpdateProvider              | Nativamente compatível                  | Windows Server 1809 e posteriores<br>Windows 10 1809 e posteriores       |
