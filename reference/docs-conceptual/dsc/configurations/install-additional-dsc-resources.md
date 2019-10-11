---
ms.date: 12/12/2018
keywords: dsc,powershell,recurso,galeria,instalação
title: Instalar recursos adicionais do DSC
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954483"
---
# <a name="install-additional-dsc-resources"></a>Instalar recursos adicionais do DSC

O PowerShell inclui vários recursos prontos para uso no DSC (Desired State Configuration). O módulo **PSDesiredStateConfiguration** contém todos os recursos DSC OOB disponíveis na instância específica do PowerShell.

Esta é uma lista dos recursos OOB incluídos no PowerShell 4.0 e uma descrição das capacidades dos recursos.

> [!NOTE]
> Essa lista está incompleta, pois o número de recursos OOB cresce a cada versão do PowerShell.

|Recurso  |Descrição  |
|---------|---------|
|**File**|Controla o estado dos arquivos e diretórios. Copia os arquivos de uma **Fonte** para um **Destino** e os atualiza quando a **Fonte** muda comparando datas, somas de verificação e hashes.|
|**Archive**|Desempacota os arquivos e um local especificado. Valida os arquivos com a **soma de verificação** especificada.|
|**Environment**|Gerencia as variáveis de ambiente.|
|**Grupo**|Gerencia os grupos locais e controla a associação de grupo.|
|**Log**|Grava as mensagens no log de eventos `Microsoft-Windows-Desired State Configuration/Analytic`.|
|**Pacote**|Instala ou desinstala pacotes usando **Arguments**, **LogPath**, **ReturnCode** e outras configurações.|
|**Registry**|Gerencia os valores e as chaves do registro.|
|**Script**|Permite que você crie seus próprios blocos de script [get-test-set](../resources/get-test-set.md).|
|**Service**|Configura os serviços do Windows.|
|**User** |Gerencia os atributos e usuários locais.|
|**WindowsFeature**|Gerencia as funções e os recursos.|
|**WindowsProcess**|Configura os processos do Windows.|

Os recursos OOB proporcionam um bom ponto de partida para operações comuns. Se os recursos OOB não atenderem às suas necessidades, você poderá escrever seu próprio [Recurso personalizado](../resources/authoringResource.md). Antes de escrever um recurso personalizado para resolver seu problema, procure na vasta gama de recursos DSC que já foram criados pela Microsoft e pela comunidade do PowerShell.

Você pode encontrar recursos DSC na [Galeria do PowerShell](https://www.powershellgallery.com/) e no [GitHub](https://github.com/). Também é possível instalar recursos DSC diretamente do console do PowerShell usando o [PowerShellGet](/powershell/module/powershellget/).

## <a name="installing-powershellget"></a>Instalando o PowerShellGet

Para determinar se você já tem o **PowerShell** ou para obter ajuda para instalá-lo, confira o guia a seguir: [Instalando o PowerShellGet](/powershell/gallery/installing-psget).

## <a name="finding-dsc-resources-using-powershellget"></a>Localizar os recursos DSC usando o PowerShellGet

Assim que o **PowerShellGet** é instalado no sistema, você pode localizar e instalar os recursos DSC hospedados na [Galeria do PowerShell](https://www.powershellgallery.com/).

Primeiro, use o cmdlet [Find-DSCResource](/powershell/module/powershellget/find-dscresource) para localizar os recursos DSC. Ao executar `Find-DSCResource` pela primeira vez, você verá o seguinte prompt para instalar o "provedor do NuGet".

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

Depois de pressionar "y", o provedor "NuGet" é instalado e você verá uma lista de recursos DSC que podem ser instalados da Galeria do PowerShell.

> [!NOTE]
> A lista não é exibida por ser grande demais.

Você também pode especificar o parâmetro `-Name` usando caracteres curinga ou o parâmetro `-Filter` sem caracteres curinga para restringir sua pesquisa. Este exemplo tenta localizar um recurso DSC de "Fuso horário" usando os caracteres curinga.

> [!IMPORTANT]
> Atualmente, há um bug no cmdlet `Find-DSCResource` que impede o uso de caracteres curinga nos parâmetros `-Name` e `-Filter`. O segundo exemplo abaixo mostra uma solução alternativa usando `Where-Object`.

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

Você também pode usar `Where-Object` para encontrar os recursos DSC com filtragem mais granular. Essa abordagem será mais lenta do que usar os parâmetros de filtragem integrados.

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

Para saber mais sobre filtragem, confira [Where-Object](/powershell/module/microsoft.powershell.core/where-object).

## <a name="installing-dsc-resources-using-powershellget"></a>Instalar os recursos DSC usando o PowerShellGet

Para instalar um recurso DSC, use o cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module), especificando o nome do módulo exibido em nome do **Módulo** nos resultados da pesquisa.

O recurso de "Fuso horário" existe no módulo "ComputerManagementDSC", portanto este é o módulo que o exemplo instala.

> [!NOTE]
> Se você não confiar na Galeria do PowerShell, verá o aviso abaixo solicitando a confirmação e mostrando como evitar avisos subsequentes nas instalações.

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Pressione "y" para continuar a instalação do módulo. Após a instalação, verifique se o novo recurso foi instalado usando [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

Também é possível exibir outros recursos no módulo recém-instalado, especificando o parâmetro `-ModuleName`.

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a>Consulte também

- [O que são recursos?](../resources/resources.md)
