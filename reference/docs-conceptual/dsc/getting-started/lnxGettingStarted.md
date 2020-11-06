---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Introdução à Configuração de Estado Desejado (DSC) para Linux
description: Este tópico explica como começar a usar a Configuração de Estado Desejado (DSC) do PowerShell para Linux.
ms.openlocfilehash: 826707654a297306c39d4dfcfd3941f56b7cf91d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651119"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="e1304-104">Introdução à Configuração de Estado Desejado (DSC) para Linux</span><span class="sxs-lookup"><span data-stu-id="e1304-104">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="e1304-105">Este tópico explica como começar a usar a Configuração de Estado Desejado (DSC) do PowerShell para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span>
<span data-ttu-id="e1304-106">Para obter informações gerais sobre o DSC, consulte [Introdução à Configuração de Estado Desejado do Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="e1304-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="e1304-107">Versões do sistema operacional Linux com suporte</span><span class="sxs-lookup"><span data-stu-id="e1304-107">Supported Linux operation system versions</span></span>

<span data-ttu-id="e1304-108">Há suporte para as seguintes versões de sistema operacional do Linux no DSC para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-108">The following Linux operating system versions are supported by DSC for Linux.</span></span>

- <span data-ttu-id="e1304-109">CentOS 5, 6 e 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-109">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="e1304-110">Debian GNU/Linux 6, 7 e 8 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-110">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="e1304-111">Oracle Linux 5, 6 e 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-111">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="e1304-112">Red Hat Enterprise Linux Server 5, 6 e 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-112">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="e1304-113">SUSE Linux Enterprise Server 10, 11 e 12 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-113">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="e1304-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="e1304-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span></span>

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="e1304-115">Instalando a DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="e1304-115">Installing DSC for Linux</span></span>

<span data-ttu-id="e1304-116">É necessário instalar a [OMI (Infraestrutura de Gerenciamento Aberta)](https://github.com/Microsoft/omi) antes de instalar a DSC para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-116">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="e1304-117">Instalando a OMI</span><span class="sxs-lookup"><span data-stu-id="e1304-117">Installing OMI</span></span>

<span data-ttu-id="e1304-118">A Desired State Configuration para Linux requer o servidor CIM da OMI (Infraestrutura de Gerenciamento Aberta), versão 1.0.8.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="e1304-118">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="e1304-119">A OMI pode ser baixada do The Open Group: [OMI (Infraestrutura de Gerenciamento Aberta)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="e1304-119">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="e1304-120">Para instalar a OMI, instale o pacote adequado para seu sistema Linux (.rpm ou .deb), a versão do OpenSSL (ssl_098 ou ssl_100) e a arquitetura (x64/x86).</span><span class="sxs-lookup"><span data-stu-id="e1304-120">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="e1304-121">Pacotes de RPM são adequados para CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server e Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-121">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="e1304-122">Pacotes de DEB são adequados para Debian GNU/Linux e Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="e1304-122">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="e1304-123">Os pacotes ssl_098 são adequados para computadores com OpenSSL 0.9.8 instalado, enquanto os pacotes ssl_100 são adequados para computadores com OpenSSL 1.0 instalado.</span><span class="sxs-lookup"><span data-stu-id="e1304-123">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="e1304-124">Para determinar a versão instalada do OpenSSL, execute o comando `openssl version`.</span><span class="sxs-lookup"><span data-stu-id="e1304-124">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="e1304-125">Execute o seguinte comando para instalar a OMI em um sistema CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="e1304-125">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="e1304-126">Instalando a DSC</span><span class="sxs-lookup"><span data-stu-id="e1304-126">Installing DSC</span></span>

<span data-ttu-id="e1304-127">A DSC para Linux está disponível para download no repositório [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294) do repositório.</span><span class="sxs-lookup"><span data-stu-id="e1304-127">DSC for Linux is available for download from the [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294) repository in the repository.</span></span>

<span data-ttu-id="e1304-128">Para instalar a DSC, instale o pacote adequado para seu sistema Linux (.rpm ou .deb), a versão do OpenSSL (ssl_098 ou ssl_100) e a arquitetura (x64/x86).</span><span class="sxs-lookup"><span data-stu-id="e1304-128">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="e1304-129">Pacotes de RPM são adequados para CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server e Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-129">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="e1304-130">Pacotes de DEB são adequados para Debian GNU/Linux e Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="e1304-130">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="e1304-131">Os pacotes ssl_098 são adequados para computadores com OpenSSL 0.9.8 instalado, enquanto os pacotes ssl_100 são adequados para computadores com OpenSSL 1.0 instalado.</span><span class="sxs-lookup"><span data-stu-id="e1304-131">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="e1304-132">Para determinar a versão instalada do OpenSSL, execute a versão do comando openssl.</span><span class="sxs-lookup"><span data-stu-id="e1304-132">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="e1304-133">Execute o seguinte comando para instalar a DSC em um sistema CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="e1304-133">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="e1304-134">Usando a DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="e1304-134">Using DSC for Linux</span></span>

<span data-ttu-id="e1304-135">As seções a seguir explicam como criar e executar configurações DSC em computadores Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-135">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="e1304-136">Criando um documento MOF de configuração</span><span class="sxs-lookup"><span data-stu-id="e1304-136">Creating a configuration MOF document</span></span>

<span data-ttu-id="e1304-137">A palavra-chave Configuration do Windows PowerShell é usada para criar uma configuração para computadores Linux, assim como para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="e1304-137">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="e1304-138">As etapas a seguir descrevem a criação de um documento de configuração para um computador Linux usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1304-138">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="e1304-139">Importe o módulo nx.</span><span class="sxs-lookup"><span data-stu-id="e1304-139">Import the nx module.</span></span> <span data-ttu-id="e1304-140">O módulo nx do Windows PowerShell contém o esquema para recursos internos para DSC para Linux e deve ser instalado no seu computador local e importado na configuração.</span><span class="sxs-lookup"><span data-stu-id="e1304-140">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="e1304-141">Para instalar o módulo nx, copie o diretório do módulo nx para `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` ou `$PSHOME\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e1304-141">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="e1304-142">O módulo nx está incluído no pacote de instalação da DSC para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-142">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="e1304-143">Para importar o módulo nx na sua configuração, use o comando `Import-DSCResource`:</span><span class="sxs-lookup"><span data-stu-id="e1304-143">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="e1304-144">Definir uma configuração e gerar o documento de configuração:</span><span class="sxs-lookup"><span data-stu-id="e1304-144">Define a configuration and generate the configuration document:</span></span>

   ```powershell
   Configuration ExampleConfiguration
   {
        Import-DscResource -Module nx

        Node  "linuxhost.contoso.com"
        {
            nxFile ExampleFile
            {
                DestinationPath = "/tmp/example"
                Contents = "hello world `n"
                Ensure = "Present"
                Type = "File"
            }
        }
   }

   ExampleConfiguration -OutputPath:"C:\temp"
   ```

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="e1304-145">Envie a configuração por push para o computador Linux</span><span class="sxs-lookup"><span data-stu-id="e1304-145">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="e1304-146">Documentos de configuração (arquivos MOF) podem ser enviados por push para o computador Linux usando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="e1304-146">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="e1304-147">Para usar esse cmdlet, juntamente com os cmdlets [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) ou [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), remotamente em um computador Linux, você deve utilizar uma CIMSession.</span><span class="sxs-lookup"><span data-stu-id="e1304-147">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="e1304-148">O cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) é usado para criar uma **CIMSession** para o computador Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-148">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a **CIMSession** to the Linux computer.</span></span>

<span data-ttu-id="e1304-149">O código a seguir mostra como criar uma CIMSession para DSC para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-149">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName "root" -Message "Enter Password:"

#Ignore SSL certificate validation
#$opt = New-CimSessionOption -UseSsl $true -SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl $true
$Sess=New-CimSession -Credential $credential -ComputerName $Node -Port 5986 -Authentication basic -SessionOption $opt -OperationTimeoutSec 90
```

> [!NOTE]
> <span data-ttu-id="e1304-150">No modo de "Push", a credencial do usuário precisa ser o usuário raiz no computador Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-150">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span> <span data-ttu-id="e1304-151">Há suporte apenas para conexões SSL/TLS para DSC para Linux; a `New-CimSession` precisa ser usada com o parâmetro –UseSSL definido como $true.</span><span class="sxs-lookup"><span data-stu-id="e1304-151">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span> <span data-ttu-id="e1304-152">O certificado SSL usado pela OMI (para DSC) é especificado no arquivo: `/etc/opt/omi/conf/omiserver.conf` com as propriedades: pemfile e keyfile.</span><span class="sxs-lookup"><span data-stu-id="e1304-152">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span> <span data-ttu-id="e1304-153">Se o computador Windows em que você está executando o cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) não confiar nesse certificado, será possível optar por ignorar a validação do certificado com as Opções de CIMSession: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span><span class="sxs-lookup"><span data-stu-id="e1304-153">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span></span>

<span data-ttu-id="e1304-154">Execute o seguinte comando para enviar a configuração DSC por push para o nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-154">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="e1304-155">Distribuir a configuração com um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="e1304-155">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="e1304-156">As configurações podem ser distribuídas para um computador Linux com um servidor de pull, assim como para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="e1304-156">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="e1304-157">Para obter diretrizes sobre como usar um servidor de pull, consulte [Servidores de Pull de Configuração de Estado Desejado do Windows PowerShell](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="e1304-157">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="e1304-158">Para obter informações adicionais e se informar sobre as limitações relacionadas ao uso de computadores Linux com um servidor pull, consulte as Notas de versão para a configuração de estado desejado para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-158">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="e1304-159">Trabalhando com configurações localmente</span><span class="sxs-lookup"><span data-stu-id="e1304-159">Working with configurations locally</span></span>

<span data-ttu-id="e1304-160">A DSC para Linux inclui scripts para trabalhar com a configuração no computador Linux local.</span><span class="sxs-lookup"><span data-stu-id="e1304-160">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="e1304-161">Esses scripts estão localizados em `/opt/microsoft/dsc/Scripts` e incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e1304-161">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="e1304-162">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="e1304-162">GetDscConfiguration.py</span></span>

  <span data-ttu-id="e1304-163">Gera a configuração atual aplicada ao computador.</span><span class="sxs-lookup"><span data-stu-id="e1304-163">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="e1304-164">Semelhante ao cmdlet `Get-DscConfiguration` do cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1304-164">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

  `# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="e1304-165">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="e1304-165">GetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="e1304-166">Gera a metaconfiguração atual aplicada ao computador.</span><span class="sxs-lookup"><span data-stu-id="e1304-166">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="e1304-167">Semelhante ao cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="e1304-167">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

  `# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="e1304-168">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="e1304-168">InstallModule.py</span></span>

  <span data-ttu-id="e1304-169">Instala um módulo personalizado de recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="e1304-169">Installs a custom DSC resource module.</span></span> <span data-ttu-id="e1304-170">Requer o caminho para um arquivo. zip que contém a biblioteca de objeto compartilhado do módulo e os arquivos MOF do esquema.</span><span class="sxs-lookup"><span data-stu-id="e1304-170">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

 `# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="e1304-171">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="e1304-171">RemoveModule.py</span></span>

  <span data-ttu-id="e1304-172">Remove um módulo personalizado de recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="e1304-172">Removes a custom DSC resource module.</span></span> <span data-ttu-id="e1304-173">Requer o nome do módulo que será removido.</span><span class="sxs-lookup"><span data-stu-id="e1304-173">Requires the name of the module to remove.</span></span>

  `# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="e1304-174">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="e1304-174">StartDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="e1304-175">Aplica um arquivo MOF de configuração ao computador.</span><span class="sxs-lookup"><span data-stu-id="e1304-175">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="e1304-176">Semelhante ao cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="e1304-176">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="e1304-177">Exige o caminho até o MOF de configuração para aplicar.</span><span class="sxs-lookup"><span data-stu-id="e1304-177">Requires the path to the configuration MOF to apply.</span></span>

  `# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="e1304-178">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="e1304-178">SetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="e1304-179">Aplica um arquivo MOF de metaconfiguração ao computador.</span><span class="sxs-lookup"><span data-stu-id="e1304-179">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="e1304-180">Semelhante ao cmdlet [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="e1304-180">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="e1304-181">Exige o caminho até o MOF de metaconfiguração para aplicar.</span><span class="sxs-lookup"><span data-stu-id="e1304-181">Requires the path to the Meta Configuration MOF to apply.</span></span>

  `# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="e1304-182">Arquivos de Log da Configuração de Estado Desejado do PowerShell para Linux</span><span class="sxs-lookup"><span data-stu-id="e1304-182">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="e1304-183">Os seguintes arquivos de log são gerados para mensagens da DSC para Linux.</span><span class="sxs-lookup"><span data-stu-id="e1304-183">The following log files are generated for DSC for Linux messages.</span></span>

|     <span data-ttu-id="e1304-184">Arquivo de log</span><span class="sxs-lookup"><span data-stu-id="e1304-184">Log file</span></span>      |     <span data-ttu-id="e1304-185">Diretório</span><span class="sxs-lookup"><span data-stu-id="e1304-185">Directory</span></span>      |                                               <span data-ttu-id="e1304-186">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1304-186">Description</span></span>                                                |
| ----------------- | ------------------ | -------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="e1304-187">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="e1304-187">**omiserver.log**</span></span> | `/var/opt/omi/log` | <span data-ttu-id="e1304-188">Mensagens relacionadas à operação do servidor CIM da OMI.</span><span class="sxs-lookup"><span data-stu-id="e1304-188">Messages relating to the operation of the OMI CIM server.</span></span>                                                |
| <span data-ttu-id="e1304-189">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="e1304-189">**dsc.log**</span></span>       | `/var/opt/omi/log` | <span data-ttu-id="e1304-190">Mensagens relacionadas à operação das operações de recurso do Gerenciador de Configurações Local (LCM) e da DSC.</span><span class="sxs-lookup"><span data-stu-id="e1304-190">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span> |
