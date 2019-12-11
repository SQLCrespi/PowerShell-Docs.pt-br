---
ms.date: 06/03/2019
keywords: powershell, cmdlet
title: Trabalhando com instalações de software
ms.openlocfilehash: 6d2111a332f0e8c1b545186d3d950e936aed1834
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "66830298"
---
# <a name="working-with-software-installations"></a>Trabalhando com instalações de software

Aplicativos que são projetados para usar o Windows Installer podem ser acessados por meio da classe do WMI **Win32_Product**, mas nem todos os aplicativos usados atualmente usam o Windows Installer.
Aplicativos que usam rotinas de instalação alternativas geralmente não são gerenciados pelo Windows Installer.
As técnicas específicas para trabalhar com esses aplicativos dependem do instalador do software e das decisões tomadas pelo desenvolvedor do aplicativo. Por exemplo, aplicativos instalados ao copiar os arquivos para uma pasta do computador, geralmente não podem ser gerenciados por meio das técnicas discutidas aqui. É possível gerenciar esses aplicativos como arquivos e pastas, usando as técnicas discutidas em [Como trabalhar com arquivos e pastas](Working-with-Files-and-Folders.md).

> [!CAUTION]
> A classe **Win32_Product** não é otimizada para consulta. Consultas que usam filtros curinga fazem com que o WMI use o provedor MSI para enumerar todos os produtos instalados e, em seguida, analisar a lista completa em sequência para lidar com o filtro. Isso também inicia uma verificação de consistência dos pacotes instalados, verificando e reparando a instalação. A validação é um processo lento e pode resultar em erros nos logs de eventos. Para obter mais informações, confira o [artigo da base de dados de conhecimento 974524](https://support.microsoft.com/help/974524).

## <a name="listing-windows-installer-applications"></a>Listando aplicativos do Windows Installer

Para listar os aplicativos instalados com o Windows Installer em um sistema local ou remoto, use a seguinte consulta simples do WMI:

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)"
```

```Output
Name               Caption                     Vendor                 Version      IdentifyingNumber
----               -------                     ------                 -------      -----------------
Microsoft .NET ... Microsoft .NET Core Runt... Microsoft Corporation  16.72.26629  {ACC73072-9AD5-416C-94B...
```

Para exibir todas as propriedades do objeto **Win32_Product** na tela, use o parâmetro **Properties** dos cmdlets de formatação, como o cmdlet `Format-List`, com um valor de `*` (all).

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

Se preferir, você poderá usar o parâmetro `Get-CimInstance` **Filter** para selecionar apenas o Microsoft .NET Framework 2.0. O valor do parâmetro **Filter** usa a sintaxe da linguagem WQL, não a sintaxe do Windows PowerShell. Por exemplo:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property *
```

Para listar somente as propriedades de seu interesse, use o parâmetro **Property** dos cmdlets de formatação para listar as propriedades desejadas.

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

## <a name="listing-all-uninstallable-applications"></a>Listando todos os aplicativos desinstaláveis

Como a maioria dos aplicativos padrão registra um desinstalador com o Windows, podemos trabalhar com eles localmente, localizando-os no Registro do Windows. Não há uma forma garantida de localizar todos os aplicativos em um sistema. No entanto, é possível encontrar todos os programas com listagens exibidas em **Adicionar ou Remover Programas**. **Adicionar ou Remover Programas** encontra esses aplicativos na seguinte chave do Registro:

`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.

Podemos examinar essa chave para encontrar aplicativos. Para facilitar ainda mais a exibição da Chave de desinstalação, podemos mapear uma unidade do PowerShell neste local do registro:

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```
Agora temos uma unidade chamada "Desinstalação:" que pode ser usada como uma maneira rápida e conveniente de procurar as instalações de aplicativos. Podemos encontrar o número de aplicativos instalados contando o número de chaves de registro na Desinstalação: Unidade do PowerShell:

```
(Get-ChildItem -Path Uninstall:).Count
459
```

Podemos pesquisar esta lista de aplicativos ainda mais detalhadamente usando uma variedade de técnicas, começando com **Get-ChildItem**. Para obter uma lista de aplicativos e salvá-los na variável **$UninstallableApplications**, use o seguinte comando:

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

Para exibir os valores das entradas do registro nas chaves do registro em Desinstalação, use o método GetValue das chaves do registro. O valor do método é o nome da entrada do registro.

Por exemplo, para localizar os nomes para exibição dos aplicativos na Chave de desinstalação, use o seguinte comando:

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

Não há nenhuma garantia de que esses valores sejam exclusivos. No exemplo a seguir, dois itens instalados aparecem como "Windows Media Encoder 9 Series":

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

## <a name="installing-applications"></a>Instalando aplicativos

Você pode usar a classe **Win32_Product** para instalar os pacotes do Windows Installer, local ou remotamente.

> [!NOTE]
> Para instalar um aplicativo, inicie o PowerShell com a opção "Executar como administrador".

Ao instalar remotamente, use um caminho de rede da Convenção de Nomenclatura Universal (UNC) para especificar o caminho para o pacote .msi, porque o subsistema WMI não entende caminhos do PowerShell. Por exemplo, para instalar o pacote NewPackage.msi localizado no compartilhamento de rede `\\AppServ\dsp` no computador remoto PC01, digite o seguinte comando no prompt do PowerShell:

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

Aplicativos que não usam a tecnologia Windows Installer podem ter métodos específicos de aplicativos para a implantação automática. Confira a documentação do aplicativo ou consulte o sistema de suporte do fornecedor do aplicativo.

## <a name="removing-applications"></a>Removendo aplicativos

Remover um pacote do Windows Installer, usando o PowerShell funciona quase da mesma forma que a instalação de um pacote. Aqui está um exemplo que seleciona o pacote para desinstalar com base em seu nome; em alguns casos pode ser mais fácil de filtrar com o **IdentifyingNumber**:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

Remover outros aplicativos não é tão simples, mesmo quando feito localmente. Podemos encontrar as cadeias de caracteres de desinstalação de linha de comando para esses aplicativos por meio da extração da propriedade **UninstallString**.
Esse método funciona para aplicativos do Windows Installer em programas mais antigos que aparecem sob a Chave de desinstalação:

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

Você pode filtrar a saída pelo nome da exibição, se desejar:

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

No entanto, essas cadeias de caracteres podem não ser diretamente utilizáveis no prompt do PowerShell sem modificação.

## <a name="upgrading-windows-installer-applications"></a>Atualizando aplicativos do Windows Installer

Para atualizar um aplicativo, você precisa saber o nome do aplicativo e o caminho para o pacote de atualização do aplicativo. Com essas informações, você pode atualizar um aplicativo com um único comando do PowerShell:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
