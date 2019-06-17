---
ms.date: 06/03/2019
keywords: powershell, cmdlet
title: Trabalhando com instalações de software
ms.openlocfilehash: 6d2111a332f0e8c1b545186d3d950e936aed1834
ms.sourcegitcommit: 4ec9e10647b752cc62b1eabb897ada3dc03c93eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66830298"
---
# <a name="working-with-software-installations"></a><span data-ttu-id="57bf9-103">Trabalhando com instalações de software</span><span class="sxs-lookup"><span data-stu-id="57bf9-103">Working with Software Installations</span></span>

<span data-ttu-id="57bf9-104">Aplicativos que são projetados para usar o Windows Installer podem ser acessados por meio da classe do WMI **Win32_Product**, mas nem todos os aplicativos usados atualmente usam o Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="57bf9-104">Applications that are designed to use Windows Installer can be accessed through WMI's **Win32_Product** class, but not all applications in use today use the Windows Installer.</span></span>
<span data-ttu-id="57bf9-105">Aplicativos que usam rotinas de instalação alternativas geralmente não são gerenciados pelo Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="57bf9-105">Applications that use alternate setup routines are not usually managed by the Windows Installer.</span></span>
<span data-ttu-id="57bf9-106">As técnicas específicas para trabalhar com esses aplicativos dependem do instalador do software e das decisões tomadas pelo desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57bf9-106">Specific techniques for working with those applications depends on the installer software and decisions made by the application developer.</span></span> <span data-ttu-id="57bf9-107">Por exemplo, aplicativos instalados ao copiar os arquivos para uma pasta do computador, geralmente não podem ser gerenciados por meio das técnicas discutidas aqui.</span><span class="sxs-lookup"><span data-stu-id="57bf9-107">For example, applications installed by copying the files to a folder on the computer usually cannot be managed by using techniques discussed here.</span></span> <span data-ttu-id="57bf9-108">É possível gerenciar esses aplicativos como arquivos e pastas, usando as técnicas discutidas em [Como trabalhar com arquivos e pastas](Working-with-Files-and-Folders.md).</span><span class="sxs-lookup"><span data-stu-id="57bf9-108">You can manage these applications as files and folders by using the techniques discussed in [Working With Files and Folders](Working-with-Files-and-Folders.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="57bf9-109">A classe **Win32_Product** não é otimizada para consulta.</span><span class="sxs-lookup"><span data-stu-id="57bf9-109">The **Win32_Product** class is not query optimized.</span></span> <span data-ttu-id="57bf9-110">Consultas que usam filtros curinga fazem com que o WMI use o provedor MSI para enumerar todos os produtos instalados e, em seguida, analisar a lista completa em sequência para lidar com o filtro.</span><span class="sxs-lookup"><span data-stu-id="57bf9-110">Queries that use wildcard filters cause WMI to use the MSI provider to enumerate all installed products then parse the full list sequentially to handle the filter.</span></span> <span data-ttu-id="57bf9-111">Isso também inicia uma verificação de consistência dos pacotes instalados, verificando e reparando a instalação.</span><span class="sxs-lookup"><span data-stu-id="57bf9-111">This also initiates a consistency check of packages installed, verifying and repairing the install.</span></span> <span data-ttu-id="57bf9-112">A validação é um processo lento e pode resultar em erros nos logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="57bf9-112">The validation is a slow process and may result in errors in the event logs.</span></span> <span data-ttu-id="57bf9-113">Para obter mais informações, confira o [artigo da base de dados de conhecimento 974524](https://support.microsoft.com/help/974524).</span><span class="sxs-lookup"><span data-stu-id="57bf9-113">For more information seek [KB article 974524](https://support.microsoft.com/help/974524).</span></span>

## <a name="listing-windows-installer-applications"></a><span data-ttu-id="57bf9-114">Listando aplicativos do Windows Installer</span><span class="sxs-lookup"><span data-stu-id="57bf9-114">Listing Windows Installer Applications</span></span>

<span data-ttu-id="57bf9-115">Para listar os aplicativos instalados com o Windows Installer em um sistema local ou remoto, use a seguinte consulta simples do WMI:</span><span class="sxs-lookup"><span data-stu-id="57bf9-115">To list the applications installed with the Windows Installer on a local or remote system, use the following simple WMI query:</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)"
```

```Output
Name               Caption                     Vendor                 Version      IdentifyingNumber
----               -------                     ------                 -------      -----------------
Microsoft .NET ... Microsoft .NET Core Runt... Microsoft Corporation  16.72.26629  {ACC73072-9AD5-416C-94B...
```

<span data-ttu-id="57bf9-116">Para exibir todas as propriedades do objeto **Win32_Product** na tela, use o parâmetro **Properties** dos cmdlets de formatação, como o cmdlet `Format-List`, com um valor de `*` (all).</span><span class="sxs-lookup"><span data-stu-id="57bf9-116">To display all the properties of the **Win32_Product** object to the display, use the **Properties** parameter of the formatting cmdlets, such as the `Format-List` cmdlet, with a value of `*` (all).</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)" |
    Format-List -Property *
```

```Output
Name                  : Microsoft .NET Core Runtime - 2.1.2 (x64)
Version               : 16.72.26629
InstallState          : 5
Caption               : Microsoft .NET Core Runtime - 2.1.2 (x64)
Description           : Microsoft .NET Core Runtime - 2.1.2 (x64)
IdentifyingNumber     : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
SKUNumber             :
Vendor                : Microsoft Corporation
AssignmentType        : 1
HelpLink              :
HelpTelephone         :
InstallDate           : 20180816
InstallDate2          :
InstallLocation       :
InstallSource         : C:\ProgramData\Package Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
Language              : 1033
LocalPackage          : C:\WINDOWS\Installer\414c96e.msi
PackageCache          : C:\WINDOWS\Installer\414c96e.msi
PackageCode           : {D20AC783-1EC5-4A58-9277-F452F5EB9AD9}
PackageName           : dotnet-runtime-2.1.2-win-x64.msi
ProductID             :
RegCompany            :
RegOwner              :
Transforms            :
URLInfoAbout          :
URLUpdateInfo         :
WordCount             : 0
PSComputerName        :
CimClass              : root/cimv2:Win32_Product
CimInstanceProperties : {Caption, Description, IdentifyingNumber, Name...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

<span data-ttu-id="57bf9-117">Se preferir, você poderá usar o parâmetro `Get-CimInstance` **Filter** para selecionar apenas o Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="57bf9-117">Or, you could use the `Get-CimInstance` **Filter** parameter to select only Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="57bf9-118">O valor do parâmetro **Filter** usa a sintaxe da linguagem WQL, não a sintaxe do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57bf9-118">The value of the **Filter** parameter uses WMI Query Language (WQL) syntax, not Windows PowerShell syntax.</span></span> <span data-ttu-id="57bf9-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="57bf9-119">For example:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property *
```

<span data-ttu-id="57bf9-120">Para listar somente as propriedades de seu interesse, use o parâmetro **Property** dos cmdlets de formatação para listar as propriedades desejadas.</span><span class="sxs-lookup"><span data-stu-id="57bf9-120">To list only the properties that interest you, use the **Property** parameter of the formatting cmdlets to list the desired properties.</span></span>

```powershell
Get-CimInstance -Class Win32_Product  -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
```

```Output
Name              : Microsoft .NET Core Runtime - 2.1.2 (x64)
InstallDate       : 20180816
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\414c96e.msi
Vendor            : Microsoft Corporation
Version           : 16.72.26629
IdentifyingNumber : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
```

## <a name="listing-all-uninstallable-applications"></a><span data-ttu-id="57bf9-121">Listando todos os aplicativos desinstaláveis</span><span class="sxs-lookup"><span data-stu-id="57bf9-121">Listing All Uninstallable Applications</span></span>

<span data-ttu-id="57bf9-122">Como a maioria dos aplicativos padrão registra um desinstalador com o Windows, podemos trabalhar com eles localmente, localizando-os no Registro do Windows.</span><span class="sxs-lookup"><span data-stu-id="57bf9-122">Because most standard applications register an uninstaller with Windows, we can work with those locally by finding them in the Windows registry.</span></span> <span data-ttu-id="57bf9-123">Não há uma forma garantida de localizar todos os aplicativos em um sistema.</span><span class="sxs-lookup"><span data-stu-id="57bf9-123">There is no guaranteed way to find every application on a system.</span></span> <span data-ttu-id="57bf9-124">No entanto, é possível encontrar todos os programas com listagens exibidas em **Adicionar ou Remover Programas**.</span><span class="sxs-lookup"><span data-stu-id="57bf9-124">However, it is possible to find all programs with listings displayed in **Add or Remove Programs**.</span></span> <span data-ttu-id="57bf9-125">**Adicionar ou Remover Programas** encontra esses aplicativos na seguinte chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="57bf9-125">**Add or Remove Programs** finds these applications in the following registry key:</span></span>

<span data-ttu-id="57bf9-126">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span><span class="sxs-lookup"><span data-stu-id="57bf9-126">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span></span>

<span data-ttu-id="57bf9-127">Podemos examinar essa chave para encontrar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="57bf9-127">We can examine this key to find applications.</span></span> <span data-ttu-id="57bf9-128">Para facilitar ainda mais a exibição da Chave de desinstalação, podemos mapear uma unidade do PowerShell neste local do registro:</span><span class="sxs-lookup"><span data-stu-id="57bf9-128">To make it easier to view the Uninstall key, we can map a PowerShell drive to this registry location:</span></span>

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```
<span data-ttu-id="57bf9-129">Agora temos uma unidade chamada "Desinstalação:" que pode ser usada como uma maneira rápida e conveniente de procurar as instalações de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="57bf9-129">We now have a drive named "Uninstall:" that can be used to quickly and conveniently look for application installations.</span></span> <span data-ttu-id="57bf9-130">Podemos encontrar o número de aplicativos instalados contando o número de chaves de registro na Desinstalação: Unidade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="57bf9-130">We can find the number of installed applications by counting the number of registry keys in the Uninstall: PowerShell drive:</span></span>

```
(Get-ChildItem -Path Uninstall:).Count
459
```

<span data-ttu-id="57bf9-131">Podemos pesquisar esta lista de aplicativos ainda mais detalhadamente usando uma variedade de técnicas, começando com **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="57bf9-131">We can search this list of applications further by using a variety of techniques, beginning with **Get-ChildItem**.</span></span> <span data-ttu-id="57bf9-132">Para obter uma lista de aplicativos e salvá-los na variável **$UninstallableApplications**, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="57bf9-132">To get a list of applications and save them in the **$UninstallableApplications** variable, use the following command:</span></span>

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

<span data-ttu-id="57bf9-133">Para exibir os valores das entradas do registro nas chaves do registro em Desinstalação, use o método GetValue das chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="57bf9-133">To display the values of the registry entries in the registry keys under Uninstall, use the GetValue method of the registry keys.</span></span> <span data-ttu-id="57bf9-134">O valor do método é o nome da entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="57bf9-134">The value of the method is the name of the registry entry.</span></span>

<span data-ttu-id="57bf9-135">Por exemplo, para localizar os nomes para exibição dos aplicativos na Chave de desinstalação, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="57bf9-135">For example, to find the display names of applications in the Uninstall key, use the following command:</span></span>

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

<span data-ttu-id="57bf9-136">Não há nenhuma garantia de que esses valores sejam exclusivos.</span><span class="sxs-lookup"><span data-stu-id="57bf9-136">There is no guarantee that these values are unique.</span></span> <span data-ttu-id="57bf9-137">No exemplo a seguir, dois itens instalados aparecem como "Windows Media Encoder 9 Series":</span><span class="sxs-lookup"><span data-stu-id="57bf9-137">In the following example, two installed items appear as "Windows Media Encoder 9 Series":</span></span>

```powershell
$UninstallableApplications | Where-Object -FilterScript { $_.GetValue("DisplayName") -eq "Windows Media Encoder 9 Series"}
```

```Output
Name                           Property
----                           --------
{ACC73072-9AD5-416C-94BF-D82DD AuthorizedCDFPrefix :
CEA0F1B}                       Comments            :
                               Contact             :
                               DisplayVersion      : 16.72.26629
                               HelpLink            :
                               HelpTelephone       :
                               InstallDate         : 20180816
                               InstallLocation     :
                               InstallSource       : C:\ProgramData\Package
                               Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
                               ModifyPath          : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               NoModify            : 1
                               Publisher           : Microsoft Corporation
                               Readme              :
                               Size                :
                               EstimatedSize       : 67156
                               SystemComponent     : 1
                               UninstallString     : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               URLInfoAbout        :
                               URLUpdateInfo       :
                               VersionMajor        : 16
                               VersionMinor        : 72
                               WindowsInstaller    : 1
                               Version             : 273180677
                               Language            : 1033
                               DisplayName         : Microsoft .NET Core Runtime - 2.1.2 (x64)
```

## <a name="installing-applications"></a><span data-ttu-id="57bf9-138">Instalando aplicativos</span><span class="sxs-lookup"><span data-stu-id="57bf9-138">Installing Applications</span></span>

<span data-ttu-id="57bf9-139">Você pode usar a classe **Win32_Product** para instalar os pacotes do Windows Installer, local ou remotamente.</span><span class="sxs-lookup"><span data-stu-id="57bf9-139">You can use the **Win32_Product** class to install Windows Installer packages, remotely or locally.</span></span>

> [!NOTE]
> <span data-ttu-id="57bf9-140">Para instalar um aplicativo, inicie o PowerShell com a opção "Executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="57bf9-140">To install an application, you must start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="57bf9-141">Ao instalar remotamente, use um caminho de rede da Convenção de Nomenclatura Universal (UNC) para especificar o caminho para o pacote .msi, porque o subsistema WMI não entende caminhos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57bf9-141">When installing remotely, use a Universal Naming Convention (UNC) network path to specify the path to the .msi package, because the WMI subsystem does not understand PowerShell paths.</span></span> <span data-ttu-id="57bf9-142">Por exemplo, para instalar o pacote NewPackage.msi localizado no compartilhamento de rede `\\AppServ\dsp` no computador remoto PC01, digite o seguinte comando no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="57bf9-142">For example, to install the NewPackage.msi package located in the network share `\\AppServ\dsp` on the remote computer PC01, type the following command at the PowerShell prompt:</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

<span data-ttu-id="57bf9-143">Aplicativos que não usam a tecnologia Windows Installer podem ter métodos específicos de aplicativos para a implantação automática.</span><span class="sxs-lookup"><span data-stu-id="57bf9-143">Applications that do not use Windows Installer technology may have application-specific methods for automated deployment.</span></span> <span data-ttu-id="57bf9-144">Confira a documentação do aplicativo ou consulte o sistema de suporte do fornecedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57bf9-144">Check the documentation for the application or consult the application vendor's support system.</span></span>

## <a name="removing-applications"></a><span data-ttu-id="57bf9-145">Removendo aplicativos</span><span class="sxs-lookup"><span data-stu-id="57bf9-145">Removing Applications</span></span>

<span data-ttu-id="57bf9-146">Remover um pacote do Windows Installer, usando o PowerShell funciona quase da mesma forma que a instalação de um pacote.</span><span class="sxs-lookup"><span data-stu-id="57bf9-146">Removing a Windows Installer package using PowerShell works in approximately the same way as installing a package.</span></span> <span data-ttu-id="57bf9-147">Aqui está um exemplo que seleciona o pacote para desinstalar com base em seu nome; em alguns casos pode ser mais fácil de filtrar com o **IdentifyingNumber**:</span><span class="sxs-lookup"><span data-stu-id="57bf9-147">Here is an example that selects the package to uninstall based on its name; in some cases it may be easier to filter with the **IdentifyingNumber**:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

<span data-ttu-id="57bf9-148">Remover outros aplicativos não é tão simples, mesmo quando feito localmente.</span><span class="sxs-lookup"><span data-stu-id="57bf9-148">Removing other applications is not quite so simple, even when done locally.</span></span> <span data-ttu-id="57bf9-149">Podemos encontrar as cadeias de caracteres de desinstalação de linha de comando para esses aplicativos por meio da extração da propriedade **UninstallString**.</span><span class="sxs-lookup"><span data-stu-id="57bf9-149">We can find the command line uninstallation strings for these applications by extracting the **UninstallString** property.</span></span>
<span data-ttu-id="57bf9-150">Esse método funciona para aplicativos do Windows Installer em programas mais antigos que aparecem sob a Chave de desinstalação:</span><span class="sxs-lookup"><span data-stu-id="57bf9-150">This method works for Windows Installer applications and for older programs appearing under the Uninstall key:</span></span>

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="57bf9-151">Você pode filtrar a saída pelo nome da exibição, se desejar:</span><span class="sxs-lookup"><span data-stu-id="57bf9-151">You can filter the output by the display name, if you like:</span></span>

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="57bf9-152">No entanto, essas cadeias de caracteres podem não ser diretamente utilizáveis no prompt do PowerShell sem modificação.</span><span class="sxs-lookup"><span data-stu-id="57bf9-152">However, these strings may not be directly usable from the PowerShell prompt without some modification.</span></span>

## <a name="upgrading-windows-installer-applications"></a><span data-ttu-id="57bf9-153">Atualizando aplicativos do Windows Installer</span><span class="sxs-lookup"><span data-stu-id="57bf9-153">Upgrading Windows Installer Applications</span></span>

<span data-ttu-id="57bf9-154">Para atualizar um aplicativo, você precisa saber o nome do aplicativo e o caminho para o pacote de atualização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57bf9-154">To upgrade an application, you need to know the name of the application and the path to the application upgrade package.</span></span> <span data-ttu-id="57bf9-155">Com essas informações, você pode atualizar um aplicativo com um único comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="57bf9-155">With that information, you can upgrade an application with a single PowerShell command:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
