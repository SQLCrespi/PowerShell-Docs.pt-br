---
ms.date: 07/08/2020
keywords: DSC,powershell,configuração,instalação
title: Recursos de composição – Usar uma configuração DSC como um recurso
description: Este artigo descreve como criar e usar um recurso de composição.
ms.openlocfilehash: c1f0e3b45c3a393c04700b5a4bc88be365794820
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667293"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a>Recursos de composição: usando uma configuração DSC como um recurso

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

Em situações reais, as configurações podem se tornar longas e complexas, chamando muitos recursos diferentes e definindo um grande número de propriedades. Para ajudar a resolver essa complexidade, é possível usar uma configuração do tipo Configuração de Estado Desejado (DSC) do Windows PowerShell como um recurso para outras configurações. Isso é chamado de recurso de composição. Um recurso de composição é uma configuração DSC que usa parâmetros. Os parâmetros da configuração atuam como as propriedades do recurso.
A configuração é salva como um arquivo com uma extensão `.schema.psm1`. Ela substitui o esquema MOF e o script em um recurso de DSC típico. Para obter mais informações sobre recursos de DSC, confira [Recursos de Desired State Configuration do Windows PowerShell](resources.md).

## <a name="creating-the-composite-resource"></a>Criando o recurso de composição

Em nosso exemplo, criamos uma configuração que invoca uma série de recursos existentes para configurar máquinas virtuais. Em vez de especificar os valores a serem definidos em blocos de configuração, a configuração pega parâmetros que são usados nos blocos de configuração.

```powershell
Configuration xVirtualMachine
{
    param
    (
        # Name of VMs
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String[]] $VMName,

        # Name of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchName,

        # Type of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchType,

        # Source Path for VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDParentPath,

        # Destination path for diff VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDPath,

        # Startup Memory for VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMStartupMemory,

        # State of the VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMState
    )

    # Import the module that defines custom resources
    Import-DscResource -Module xComputerManagement,xHyper-V

    # Install the Hyper-V role
    WindowsFeature HyperV
    {
        Ensure = "Present"
        Name = "Hyper-V"
    }

    # Create the virtual switch
    xVMSwitch $SwitchName
    {
        Ensure = "Present"
        Name = $SwitchName
        Type = $SwitchType
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check for Parent VHD file
    File ParentVHDFile
    {
        Ensure = "Present"
        DestinationPath = $VHDParentPath
        Type = "File"
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check the destination VHD folder
    File VHDFolder
    {
        Ensure = "Present"
        DestinationPath = $VHDPath
        Type = "Directory"
        DependsOn = "[File]ParentVHDFile"
    }

    # Create VM specific diff VHD
    foreach ($Name in $VMName)
    {
        xVHD "VHD$Name"
        {
            Ensure = "Present"
            Name = $Name
            Path = $VHDPath
            ParentPath = $VHDParentPath
            DependsOn = @("[WindowsFeature]HyperV",
                          "[File]VHDFolder")
        }
    }

    # Create VM using the above VHD
    foreach($Name in $VMName)
    {
        xVMHyperV "VMachine$Name"
        {
            Ensure = "Present"
            Name = $Name
            VhDPath = (Join-Path -Path $VHDPath -ChildPath $Name)
            SwitchName = $SwitchName
            StartupMemory = $VMStartupMemory
            State = $VMState
            MACAddress = $MACAddress
            WaitForIP = $true
            DependsOn = @("[WindowsFeature]HyperV",
                          "[xVHD]VHD$Name")
        }
    }
}
```

> [!NOTE]
> Atualmente, a DSC não dá suporte à colocação de recursos compostos ou configurações aninhadas em um recurso de composição.

### <a name="saving-the-configuration-as-a-composite-resource"></a>Salvando a configuração como um recurso de composição

Para usar a configuração com parâmetros como um recurso de DSC, salve-a em uma estrutura de diretórios semelhante à de qualquer outro recurso baseado em MOF e nomeie-a com uma extensão `.schema.psm1`. No caso deste exemplo, chamaremos o arquivo de `xVirtualMachine.schema.psm1`. Você também precisa criar um manifesto chamado `xVirtualMachine.psd1` que contenha a linha a seguir.

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

> [!NOTE]
> Este se soma ao `MyDscResources.psd1`, o manifesto de módulo para todos os recursos na pasta `MyDscResources`.

Quando terminar, a estrutura de pastas deve ser a seguinte.

```
$env: psmodulepath
    |- MyDscResources
        |- MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

O recurso é detectável usando o cmdlet `Get-DscResource`, e suas propriedades são detectáveis por meio desse cmdlet ou pelo preenchimento automático com <kbd>Ctrl</kbd>+<kbd>Espaço</kbd> no ISE do Windows PowerShell.

## <a name="using-the-composite-resource"></a>Usando o recurso de composição

Em seguida, criamos uma configuração que chama o recurso de composição. Essa configuração chama o recurso de composição xVirtualMachine para criar uma máquina virtual e, em seguida, chama o recurso **xComputer** para renomeá-lo.

```powershell
configuration RenameVM
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VM
        {
            VMName = "Test"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }

    Node "192.168.10.1"
    {
        xComputer Name
        {
            Name = "SQL01"
            DomainName = "fourthcoffee.com"
        }
    }
}
```

Também é possível usar esse recurso para criar várias VMs passando uma matriz de nomes de VM para o recurso xVirtualMachine.

```PowerShell
Configuration MultipleVms
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VMs
        {
            VMName = "IIS01", "SQL01", "SQL02"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }
}
```

## <a name="supporting-psdscrunascredential"></a>Dando suporte a PsDscRunAsCredential

> [!NOTE]
> **PsDscRunAsCredential** tem suporte no PowerShell 5.0 e posterior.

A propriedade **PsDscRunAsCredential** pode ser usada no bloco de recurso [Configurações DSC](../configurations/configurations.md) para especificar que o recurso deve ser executado em um conjunto de credenciais específico. Para obter mais informações, veja [Executando o DSC com as credenciais do usuário](../configurations/runAsUser.md).

Para acessar o contexto do usuário de dentro de um recurso personalizado, você pode usar a variável automática `$PsDscContext`.

Por exemplo, o código a seguir escreveria o contexto do usuário em que o recurso está em execução para o fluxo de saída detalhada:

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a>Consulte Também

### <a name="concepts"></a>Conceitos

- [Escrevendo um recurso personalizado de DSC com MOF](authoringResourceMOF.md)
- [Introdução à Configuração de Estado Desejado do Windows PowerShell](../overview/overview.md)
