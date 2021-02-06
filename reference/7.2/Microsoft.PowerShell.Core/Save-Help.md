---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 6996decc6b2f8b99ab9c04d96c487c37f2609c9e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598813"
---
# <span data-ttu-id="0eac3-102">Save-Help</span><span class="sxs-lookup"><span data-stu-id="0eac3-102">Save-Help</span></span>

## <span data-ttu-id="0eac3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0eac3-103">SYNOPSIS</span></span>
<span data-ttu-id="0eac3-104">Baixa e salva os arquivos de ajuda mais recentes em um diretório de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-104">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="0eac3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0eac3-105">SYNTAX</span></span>

### <span data-ttu-id="0eac3-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="0eac3-106">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="0eac3-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0eac3-107">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="0eac3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0eac3-108">DESCRIPTION</span></span>

<span data-ttu-id="0eac3-109">O `Save-Help` cmdlet baixa os arquivos de ajuda mais recentes para os módulos do PowerShell e os salva em um diretório que você especificar.</span><span class="sxs-lookup"><span data-stu-id="0eac3-109">The `Save-Help` cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span> <span data-ttu-id="0eac3-110">Esse recurso permite que você atualize os arquivos de ajuda em computadores que não têm acesso à Internet e torna mais fácil atualizar os arquivos de ajuda em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="0eac3-110">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="0eac3-111">No Windows PowerShell 3,0, `Save-Help` funcionava apenas para módulos que estão instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="0eac3-111">In Windows PowerShell 3.0, `Save-Help` worked only for modules that are installed on the local computer.</span></span> <span data-ttu-id="0eac3-112">Embora fosse possível importar um módulo de um computador remoto ou obter uma referência a um objeto **PSModuleInfo** de um computador remoto usando a comunicação remota do PowerShell, a propriedade **HelpInfoUri** não foi preservada e `Save-Help` não funcionaria para a ajuda do módulo remoto.</span><span class="sxs-lookup"><span data-stu-id="0eac3-112">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and `Save-Help` would not work for remote module Help.</span></span>

<span data-ttu-id="0eac3-113">No Windows PowerShell 4,0, a propriedade **HelpInfoUri** é preservada pela comunicação remota do PowerShell, que permite o `Save-Help` trabalho para os módulos instalados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-113">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables `Save-Help` to work for modules that are installed on remote computers.</span></span> <span data-ttu-id="0eac3-114">Também é possível salvar um objeto **PSModuleInfo** em disco ou mídia removível executando `Export-Clixml` em um computador que não tenha acesso à Internet, importar o objeto em um computador que tenha acesso à Internet e, em seguida, executar `Save-Help` no objeto **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-114">It is also possible to save a **PSModuleInfo** object to disk or removable media by running `Export-Clixml` on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="0eac3-115">A ajuda salva pode ser transportada para o computador remoto usando mídia de armazenamento removível, como uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0eac3-115">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span> <span data-ttu-id="0eac3-116">A ajuda pode ser instalada no computador remoto executando `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0eac3-116">The help can be installed on the remote computer by running `Update-Help`.</span></span> <span data-ttu-id="0eac3-117">Esse processo pode ser usado para instalar ajuda em computadores que não têm qualquer tipo de acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="0eac3-117">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="0eac3-118">Para instalar arquivos de ajuda salvos, execute o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-118">To install saved help files, run the `Update-Help` cmdlet.</span></span> <span data-ttu-id="0eac3-119">Adicione seu parâmetro **SourcePath** para especificar a pasta na qual você salvou os arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="0eac3-119">Add its **SourcePath** parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="0eac3-120">Sem parâmetros, um `Save-Help` comando baixa a ajuda mais recente para todos os módulos na sessão e para os módulos que estão instalados no computador em um local listado na variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-120">Without parameters, a `Save-Help` command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="0eac3-121">Esta ação ignora módulos que não dão suporte à ajuda atualizável sem aviso.</span><span class="sxs-lookup"><span data-stu-id="0eac3-121">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="0eac3-122">O `Save-Help` cmdlet verifica a versão dos arquivos de ajuda na pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="0eac3-122">The `Save-Help` cmdlet checks the version of any help files in the destination folder.</span></span> <span data-ttu-id="0eac3-123">Se os arquivos de ajuda mais recentes estiverem disponíveis, esse cmdlet baixará os arquivos de ajuda mais recentes da Internet e os salvará na pasta.</span><span class="sxs-lookup"><span data-stu-id="0eac3-123">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span> <span data-ttu-id="0eac3-124">O `Save-Help` cmdlet funciona exatamente como o `Update-Help` cmdlet, exceto que ele salva os arquivos de gabinete (. cab) baixados, em vez de extrair os arquivos de ajuda dos arquivos de gabinete e instalá-los no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-124">The `Save-Help` cmdlet works just like the `Update-Help` cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="0eac3-125">A ajuda salva para cada módulo consiste em um arquivo de informações de ajuda (HelpInfo XML) e um arquivo de gabinete (. cab) para os arquivos de ajuda de cada cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0eac3-125">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="0eac3-126">Você não precisa extrair os arquivos de ajuda do arquivo de gabinete.</span><span class="sxs-lookup"><span data-stu-id="0eac3-126">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="0eac3-127">O `Update-Help` cmdlet extrai os arquivos da ajuda, valida o XML para segurança e, em seguida, instala os arquivos de ajuda e o arquivo de informações da ajuda em uma subpasta específica do idioma da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-127">The `Update-Help` cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="0eac3-128">Para salvar os arquivos de ajuda dos módulos na pasta de instalação do PowerShell ( `$pshome\Modules` ), inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-128">To save the help files for modules in the PowerShell installation folder (`$pshome\Modules`), start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="0eac3-129">Você precisa ser um membro do grupo Administradores no computador para baixar os arquivos de ajuda para esses módulos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-129">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="0eac3-130">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0eac3-130">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0eac3-131">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0eac3-131">EXAMPLES</span></span>

### <span data-ttu-id="0eac3-132">Exemplo 1: salvar a ajuda para o módulo DhcpServer</span><span class="sxs-lookup"><span data-stu-id="0eac3-132">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module,
# save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="0eac3-133">Este exemplo mostra três maneiras diferentes de usar `Save-Help` para salvar a ajuda do módulo **dhcpserver** de um computador cliente conectado à Internet, sem instalar o módulo **dhcpserver** ou a função de servidor DHCP no computador local.</span><span class="sxs-lookup"><span data-stu-id="0eac3-133">This example shows three different ways to use `Save-Help` to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="0eac3-134">Exemplo 2: instalar a ajuda para o módulo DhcpServer</span><span class="sxs-lookup"><span data-stu-id="0eac3-134">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the
# PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer
# module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and
# then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="0eac3-135">Este exemplo mostra como instalar a ajuda que você salvou no exemplo 1 para o módulo **DhcpServer** em um computador que não tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-135">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="0eac3-136">Exemplo 3: salvar a ajuda para todos os módulos</span><span class="sxs-lookup"><span data-stu-id="0eac3-136">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="0eac3-137">Esse comando baixa os arquivos de ajuda mais recentes para todos os módulos na cultura da interface do usuário definidos para o Windows no computador local.</span><span class="sxs-lookup"><span data-stu-id="0eac3-137">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span> <span data-ttu-id="0eac3-138">Ele salva os arquivos da ajuda na `\\Server01\Fileshare01` pasta.</span><span class="sxs-lookup"><span data-stu-id="0eac3-138">It saves the help files in the `\\Server01\Fileshare01` folder.</span></span>

### <span data-ttu-id="0eac3-139">Exemplo 4: salvar a ajuda para um módulo no computador</span><span class="sxs-lookup"><span data-stu-id="0eac3-139">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="0eac3-140">Esse comando baixa os arquivos de ajuda mais recentes para o módulo **ServerManager** e os salva na `\\Server01\Fileshare01` pasta.</span><span class="sxs-lookup"><span data-stu-id="0eac3-140">This command downloads the newest help files for the **ServerManager** module, and then saves them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="0eac3-141">Quando um módulo é instalado no computador, você pode digitar o nome do módulo como o valor do parâmetro **Module**, ainda que o módulo não seja importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0eac3-141">When a module is installed on the computer, you can type the module name as the value of the **Module** parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="0eac3-142">O comando usa o parâmetro **Credential** para fornecer as credenciais de um usuário que tem permissão para gravar no compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-142">The command uses the **Credential** parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="0eac3-143">Exemplo 5: salvar a ajuda para um módulo em um computador diferente</span><span class="sxs-lookup"><span data-stu-id="0eac3-143">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="0eac3-144">Esses comandos baixam os arquivos de ajuda mais recentes para o módulo **CustomSQL** e os salvam na `\\Server01\Fileshare01` pasta.</span><span class="sxs-lookup"><span data-stu-id="0eac3-144">These commands download the newest help files for the **CustomSQL** module and save them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="0eac3-145">Como o módulo **CustomSQL** não está instalado no computador, a sequência inclui um `Invoke-Command` comando que obtém o objeto de módulo para o módulo CustomSQL do computador Server02 e, em seguida, canaliza o objeto de módulo para o `Save-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-145">Because the **CustomSQL** module is not installed on the computer, the sequence includes an `Invoke-Command` command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the `Save-Help` cmdlet.</span></span>

<span data-ttu-id="0eac3-146">Quando um módulo não está instalado no computador, `Save-Help` o precisa do objeto de módulo, que inclui informações sobre o local dos arquivos de ajuda mais recentes.</span><span class="sxs-lookup"><span data-stu-id="0eac3-146">When a module is not installed on the computer, `Save-Help` needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="0eac3-147">Exemplo 6: salvar a ajuda para um módulo em vários idiomas</span><span class="sxs-lookup"><span data-stu-id="0eac3-147">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="0eac3-148">Esse comando salva a ajuda para os módulos do PowerShell Core em quatro culturas de interface do usuário diferentes.</span><span class="sxs-lookup"><span data-stu-id="0eac3-148">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span> <span data-ttu-id="0eac3-149">Os pacotes de idiomas dessas localidades não precisam ser instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-149">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="0eac3-150">`Save-Help` o pode baixar arquivos de ajuda para módulos em diferentes culturas de interface do usuário somente quando o proprietário do módulo disponibiliza os arquivos traduzidos na Internet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-150">`Save-Help` can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="0eac3-151">Exemplo 7: salvar ajuda mais de uma vez por dia</span><span class="sxs-lookup"><span data-stu-id="0eac3-151">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="0eac3-152">Este comando salva ajuda para todos os módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-152">This command saves help for all modules that are installed on the computer.</span></span> <span data-ttu-id="0eac3-153">O comando especifica o parâmetro **Force** para substituir a regra que impede que o `Save-Help` cmdlet Baixe a ajuda mais de uma vez em cada período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="0eac3-153">The command specifies the **Force** parameter to override the rule that prevents the `Save-Help` cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="0eac3-154">O parâmetro **Force** também substitui a restrição de 1 GB e evita a verificação da versão.</span><span class="sxs-lookup"><span data-stu-id="0eac3-154">The **Force** parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="0eac3-155">Portanto, você pode baixar arquivos mesmo que a versão não seja posterior à versão na pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="0eac3-155">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="0eac3-156">O comando usa o `Save-Help` cmdlet para baixar e salvar os arquivos de ajuda na pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="0eac3-156">The command uses the `Save-Help` cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="0eac3-157">O parâmetro **Force** é necessário quando você precisa executar um `Save-Help` comando mais de uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="0eac3-157">The **Force** parameter is required when you have to run a `Save-Help` command more than one time each day.</span></span>

## <span data-ttu-id="0eac3-158">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0eac3-158">PARAMETERS</span></span>

### <span data-ttu-id="0eac3-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="0eac3-159">-Credential</span></span>

<span data-ttu-id="0eac3-160">Especifica uma credencial de usuário.</span><span class="sxs-lookup"><span data-stu-id="0eac3-160">Specifies a user credential.</span></span> <span data-ttu-id="0eac3-161">Esse cmdlet executa o comando usando as credenciais de um usuário que tem permissão para acessar o local do sistema de arquivos especificado pelo parâmetro **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-161">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="0eac3-162">Esse parâmetro é válido somente quando o parâmetro **DestinationPath** ou **LiteralPath** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="0eac3-162">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="0eac3-163">Esse parâmetro permite que você execute `Save-Help` comandos que usam o parâmetro **DestinationPath** em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-163">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="0eac3-164">Ao fornecer credenciais explícitas, você pode executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador sem encontrar um erro de acesso negado ou usar a autenticação CredSSP para delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="0eac3-164">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="0eac3-165">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-165">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0eac3-166">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="0eac3-166">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0eac3-167">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0eac3-167">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0eac3-168">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0eac3-168">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-169">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="0eac3-169">-DestinationPath</span></span>

<span data-ttu-id="0eac3-170">Especifica o caminho da pasta na qual os arquivos de ajuda são salvos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-170">Specifies the path of the folder in which the help files are saved.</span></span> <span data-ttu-id="0eac3-171">Não especifique um nome de arquivo ou extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-171">Do not specify a file name or file name extension.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-172">-Force</span><span class="sxs-lookup"><span data-stu-id="0eac3-172">-Force</span></span>

<span data-ttu-id="0eac3-173">Indica que esse cmdlet não segue a limitação de uma vez por dia, ignora a verificação de versão e baixa os arquivos que excedem o limite de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="0eac3-173">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="0eac3-174">Sem esse parâmetro, apenas um `Save-Help` comando para cada módulo é permitido em cada período de 24 horas, os downloads são limitados a 1 GB de conteúdo descompactado por módulo, e os arquivos de ajuda para um módulo são instalados somente quando são mais recentes do que os arquivos no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-174">Without this parameter, only one `Save-Help` command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="0eac3-175">O limite de uma vez por dia protege os servidores que hospedam os arquivos de ajuda e torna prático para você adicionar um `Save-Help` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0eac3-175">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a `Save-Help` command to your PowerShell profile.</span></span>

<span data-ttu-id="0eac3-176">Para salvar a ajuda de um módulo em várias culturas de interface do usuário sem o parâmetro **Force** , inclua todas as culturas da interface do usuário no mesmo comando, como: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="0eac3-176">To save help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-177">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="0eac3-177">-FullyQualifiedModule</span></span>

<span data-ttu-id="0eac3-178">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-178">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="0eac3-179">Consulte a seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="0eac3-179">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="0eac3-180">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um destes formatos:</span><span class="sxs-lookup"><span data-stu-id="0eac3-180">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="0eac3-181">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="0eac3-181">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="0eac3-182">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-182">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="0eac3-183">os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-183">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-184">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0eac3-184">-LiteralPath</span></span>

<span data-ttu-id="0eac3-185">Especifica um caminho da pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="0eac3-185">Specifies a path of the destination folder.</span></span> <span data-ttu-id="0eac3-186">Ao contrário do valor do parâmetro **DestinationPath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="0eac3-186">Unlike the value of the **DestinationPath** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="0eac3-187">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0eac3-187">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="0eac3-188">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0eac3-188">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0eac3-189">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0eac3-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-190">-Módulo</span><span class="sxs-lookup"><span data-stu-id="0eac3-190">-Module</span></span>

<span data-ttu-id="0eac3-191">Especifica os módulos para os quais esse cmdlet baixa a ajuda.</span><span class="sxs-lookup"><span data-stu-id="0eac3-191">Specifies modules for which this cmdlet downloads help.</span></span> <span data-ttu-id="0eac3-192">Insira um ou mais nomes de módulo ou nome padrões em uma lista separada por vírgulas ou em um arquivo que tenha um nome de módulo em cada linha.</span><span class="sxs-lookup"><span data-stu-id="0eac3-192">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span> <span data-ttu-id="0eac3-193">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="0eac3-194">Você também pode canalizar objetos de módulo do `Get-Module` cmdlet para `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="0eac3-194">You can also pipe module objects from the `Get-Module` cmdlet to `Save-Help`.</span></span>

<span data-ttu-id="0eac3-195">Por padrão, o `Save-Help` baixa ajuda para todos os módulos que dão suporte à ajuda atualizável e são instalados no computador local em um local listado na variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-195">By default, `Save-Help` downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="0eac3-196">Para salvar a ajuda para módulos que não estão instalados no computador, execute um `Get-Module` comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0eac3-196">To save help for modules that are not installed on the computer, run a `Get-Module` command on a remote computer.</span></span> <span data-ttu-id="0eac3-197">Em seguida, direcione os objetos do módulo resultante para o `Save-Help` cmdlet ou envie os objetos do módulo como o valor do **módulo** ou dos parâmetros **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-197">Then pipe the resulting module objects to the `Save-Help` cmdlet or submit the module objects as the value of the **Module** or **InputObject** parameters.</span></span>

<span data-ttu-id="0eac3-198">Se o módulo especificado estiver instalado no computador, você pode inserir o nome do módulo ou um objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-198">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span> <span data-ttu-id="0eac3-199">Se o módulo não estiver instalado no computador, você deverá inserir um objeto de módulo, como um retornado pelo `Get-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-199">If the module is not installed on the computer, you must enter a module object, such as one returned by the `Get-Module` cmdlet.</span></span>

<span data-ttu-id="0eac3-200">O parâmetro **Module** do `Save-Help` cmdlet não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-200">The **Module** parameter of the `Save-Help` cmdlet does not accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="0eac3-201">Para salvar a ajuda para um módulo que não está em um local **PSModulePath** , importe o módulo para a sessão atual antes de executar o `Save-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="0eac3-201">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the `Save-Help` command.</span></span>

<span data-ttu-id="0eac3-202">Um valor de "\*" (All) tenta atualizar a ajuda para todos os módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-202">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="0eac3-203">Isso inclui módulos que não dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="0eac3-203">This includes modules that do not support Updatable Help.</span></span> <span data-ttu-id="0eac3-204">Esse valor pode gerar erros quando o comando encontra módulos que não dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="0eac3-204">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0eac3-205">-UICulture</span><span class="sxs-lookup"><span data-stu-id="0eac3-205">-UICulture</span></span>

<span data-ttu-id="0eac3-206">Especifica os valores de cultura da interface do usuário para os quais este cmdlet obtém arquivos de ajuda atualizados.</span><span class="sxs-lookup"><span data-stu-id="0eac3-206">Specifies UI culture values for which this cmdlet gets updated help files.</span></span> <span data-ttu-id="0eac3-207">Insira um ou mais códigos de idioma, como `es-ES` uma variável que contém objetos de cultura, ou um comando que obtém objetos de cultura, como um `Get-Culture` `Get-UICulture` comando ou.</span><span class="sxs-lookup"><span data-stu-id="0eac3-207">Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span>

<span data-ttu-id="0eac3-208">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-208">Wildcard characters are not permitted.</span></span> <span data-ttu-id="0eac3-209">Não especifique um código de idioma parcial, como "de".</span><span class="sxs-lookup"><span data-stu-id="0eac3-209">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="0eac3-210">Por padrão, `Save-Help` o Obtém os arquivos de ajuda na cultura da interface do usuário definida para o Windows ou sua cultura de fallback.</span><span class="sxs-lookup"><span data-stu-id="0eac3-210">By default, `Save-Help` gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="0eac3-211">Se você especificar o parâmetro **UICulture** , o `Save-Help` procurará ajuda apenas para a cultura da interface do usuário especificada, não em qualquer cultura de fallback.</span><span class="sxs-lookup"><span data-stu-id="0eac3-211">If you specify the **UICulture** parameter, `Save-Help` looks for help only for the specified UI culture, not in any fallback culture.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-212">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="0eac3-212">-UseDefaultCredentials</span></span>

<span data-ttu-id="0eac3-213">Indica que esse cmdlet executa o comando, incluindo o download da Web, com as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0eac3-213">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span> <span data-ttu-id="0eac3-214">Por padrão, o comando é executado sem credenciais explícitas.</span><span class="sxs-lookup"><span data-stu-id="0eac3-214">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="0eac3-215">Esse parâmetro é válido somente quando o download da Web usa autenticação NTLM, de negociação ou baseada em Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0eac3-215">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-216">-Escopo</span><span class="sxs-lookup"><span data-stu-id="0eac3-216">-Scope</span></span>

<span data-ttu-id="0eac3-217">Esse parâmetro não faz nada nesse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eac3-217">This paramater does nothing in this cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0eac3-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0eac3-218">CommonParameters</span></span>

<span data-ttu-id="0eac3-219">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0eac3-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0eac3-220">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0eac3-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0eac3-221">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0eac3-221">INPUTS</span></span>

### <span data-ttu-id="0eac3-222">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0eac3-222">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="0eac3-223">É possível canalizar um objeto de módulo do `Get-Module` cmdlet para o parâmetro de **módulo** de `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="0eac3-223">You can pipe a module object from the `Get-Module` cmdlet to the **Module** parameter of `Save-Help`.</span></span>

## <span data-ttu-id="0eac3-224">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0eac3-224">OUTPUTS</span></span>

### <span data-ttu-id="0eac3-225">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0eac3-225">None</span></span>

<span data-ttu-id="0eac3-226">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0eac3-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0eac3-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0eac3-227">NOTES</span></span>

- <span data-ttu-id="0eac3-228">Para salvar a ajuda para os módulos na pasta $pshome \Modules, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-228">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="0eac3-229">Somente os membros do grupo Administradores no computador podem baixar a ajuda para os módulos na pasta $pshome \Modules.</span><span class="sxs-lookup"><span data-stu-id="0eac3-229">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
- <span data-ttu-id="0eac3-230">A ajuda salva para cada módulo consiste em um arquivo de informações de ajuda (HelpInfo XML) e um arquivo de gabinete (. cab) para os arquivos de ajuda de cada cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0eac3-230">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="0eac3-231">Você não precisa extrair os arquivos de ajuda do arquivo de gabinete.</span><span class="sxs-lookup"><span data-stu-id="0eac3-231">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="0eac3-232">O `Update-Help` cmdlet extrai os arquivos da ajuda, valida o XML e, em seguida, instala os arquivos de ajuda e o arquivo de informações da ajuda em uma subpasta específica do idioma da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-232">The `Update-Help` cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
- <span data-ttu-id="0eac3-233">O `Save-Help` cmdlet pode salvar a ajuda para módulos que não estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-233">The `Save-Help` cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="0eac3-234">No entanto, como os arquivos de ajuda são instalados na pasta do módulo, o `Update-Help` cmdlet pode instalar o arquivo de ajuda atualizado somente para os módulos que estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="0eac3-234">However, because help files are installed in the module folder, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
- <span data-ttu-id="0eac3-235">Se `Save-Help` o não puder encontrar arquivos de ajuda atualizados para um módulo ou não puder encontrar arquivos de ajuda atualizados no idioma especificado, ele continuará silenciosamente sem exibir uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="0eac3-235">If `Save-Help` cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="0eac3-236">Para ver quais arquivos foram salvos pelo comando, especifique o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="0eac3-236">To see which files were saved by the command, specify the **Verbose** parameter.</span></span>
- <span data-ttu-id="0eac3-237">Os módulos são a menor unidade da ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="0eac3-237">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="0eac3-238">Não é possível salvar a ajuda para um cmdlet específico, somente para todos os cmdlets no módulo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-238">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="0eac3-239">Para localizar o módulo que contém um cmdlet específico, use a propriedade **ModuleName** junto com o `Get-Command` cmdlet, por exemplo, `(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="0eac3-239">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the `Get-Command` cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
- <span data-ttu-id="0eac3-240">`Save-Help` dá suporte a todos os módulos e os snap-ins do PowerShell Core. Ele não dá suporte a nenhum outro snap-ins.</span><span class="sxs-lookup"><span data-stu-id="0eac3-240">`Save-Help` supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
- <span data-ttu-id="0eac3-241">Os `Update-Help` `Save-Help` cmdlets e usam as seguintes portas para baixar arquivos de ajuda: porta 80 para http e porta 443 para https.</span><span class="sxs-lookup"><span data-stu-id="0eac3-241">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
- <span data-ttu-id="0eac3-242">`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="0eac3-242">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="0eac3-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0eac3-243">RELATED LINKS</span></span>

[<span data-ttu-id="0eac3-244">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0eac3-244">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="0eac3-245">Get-Module</span><span class="sxs-lookup"><span data-stu-id="0eac3-245">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="0eac3-246">Update-Help</span><span class="sxs-lookup"><span data-stu-id="0eac3-246">Update-Help</span></span>](Update-Help.md)
