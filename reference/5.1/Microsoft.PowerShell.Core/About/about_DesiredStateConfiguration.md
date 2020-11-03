---
description: Fornece uma breve introdução ao recurso de configuração de estado desejado (DSC) do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 2f043104c67078b98355b3e54171a8993e534837
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196556"
---
# <a name="about_desiredstateconfiguration"></a>about_DesiredStateConfiguration

## <a name="short-description"></a>DESCRIÇÃO BREVE

Fornece uma breve introdução ao recurso de configuração de estado desejado (DSC) do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O DSC é uma plataforma de gerenciamento no PowerShell que permite a implantação e o gerenciamento de dados de configuração para serviços de software e o gerenciamento do ambiente no qual esses serviços são executados.

A DSC fornece um conjunto de extensões de linguagem do PowerShell, novos cmdlets e recursos que você pode usar para especificar declarativamente como deseja que o estado do seu ambiente de software seja configurado. Também fornece um meio para manter e gerenciar as configurações existentes.

A DSC é introduzida no PowerShell 4,0.

Para obter informações detalhadas sobre a DSC, consulte [visão geral da configuração de estado desejado do PowerShell](/powershell/scripting/dsc/overview/overview) na biblioteca do TechNet.

## <a name="developing-dsc-resources-with-classes"></a>DESENVOLVENDO RECURSOS DE DSC COM CLASSES

A partir do PowerShell 5,0, você pode desenvolver recursos de DSC usando classes.
Para obter mais informações, consulte [about_Classes](about_Classes.md)e [escrevendo um recurso personalizado de DSC com classes do PowerShell](/previous-versions//dn948461(v=technet.10)) no Microsoft TechNet.

## <a name="using-dsc"></a>USANDO O DSC

Para usar a DSC para configurar seu ambiente, primeiro defina um bloco de script do PowerShell usando a palavra-chave Configuration, seguido por um identificador, que, por sua vez, é seguido pelo par de chaves que delimitam o bloco. Dentro do bloco de configuração, você pode definir blocos de nós que especificam o estado de configuração desejado para cada nó (computador) no ambiente. Um bloco de nó começa com a palavra-chave node, seguida pelo nome do computador de destino, que pode ser uma variável. Depois do nome do computador, vêm as chaves que delimitam o bloco de nós. Dentro do bloco de nó, você pode definir blocos de recursos para configurar recursos específicos. Um bloco de recursos começa com o nome do tipo do recurso, seguido pelo identificador que você deseja especificar para esse bloco, seguido pelas chaves que delimitam o bloco, conforme mostrado no exemplo a seguir.

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

Para criar uma configuração, invoque o bloco de configuração da mesma forma que você invocaria uma função do PowerShell, passando quaisquer parâmetros esperados que você tenha definido (dois no exemplo acima). Por exemplo, neste caso:

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

Isso gera um arquivo MOF por nó no caminho que você especificar. Esses arquivos MOF especificam a configuração desejada para cada nó. Em seguida, use o cmdlet a seguir para analisar os arquivos MOF de configuração, enviar a cada nó sua configuração correspondente e aplicar essas configurações. Observe que você não precisa criar um arquivo MOF separado para recursos de DSC baseados em classe.

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a>USANDO A DSC PARA MANTER O ESTADO DE CONFIGURAÇÃO

Com a DSC, a configuração é idempotente. Isso significa que, se você usar a DSC para aplicar a mesma configuração mais de uma vez, o estado de configuração resultante sempre será o mesmo. Por isso, se você suspeitar que qualquer nó em seu ambiente pode ter sido desfeito do estado desejado da configuração, você pode aplicar a mesma configuração de DSC novamente para trazê-las de volta para o estado desejado. Você não precisa modificar o script de configuração para endereçar apenas os recursos cujo estado foi desfeito do estado desejado.

O exemplo a seguir mostra como você pode verificar se o estado real da configuração em um determinado nó foi descompasso da última configuração DSC aplicada no nó. Neste exemplo, verificamos a configuração do computador local.

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a>RECURSOS INTERNOS DE DSC

Você pode usar os seguintes recursos internos em seus scripts de configuração:

|Name                  |Propriedades                                         |
|----------------------|---------------------------------------------------|
|Arquivo                  |{DestinationPath, Attributes, checksum, Content...}|
|Archive               |{Destino, caminho, soma de verificação, credencial...}       |
|Ambiente           |{Name, depende, verifique, caminho...}                 |
|Grupo                 |{GroupName, Credential, depend, Description...} |
|Registro                   |{Mensagem, depende, PsDscRunAsCredential}         |
|Pacote               |{Name, Path, ProductId, Arguments...}              |
|Registro              |{Key, valueName, depende, verifique...}             |
|script                |{GetScript, setscript, TestScript, credencial...}  |
|Serviço               |{Nome, BuiltInAccount, credencial, dependências...}|
|Usuário                  |{Nome de usuário, depende, descrição, desabilitado...}    |
|WaitForAll            |{NodeName, resourceName, dependo, PsDscRunAsC...}|
|WaitForAny            |{NodeName, resourceName, dependo, PsDscRunAsC...}|
|WaitForSome           |{NodeCount, NodeName, resourceName, depende...}  |
|WindowsFeature        |{Nome, credencial, depende, garantir...}           |
|WindowsOptionalFeature|{Name, depende, verifique, LogLevel...}             |
|WindowsProcess        |{Argumentos, caminho, credencial, depende...}        |

Para obter uma lista de recursos de DSC disponíveis no seu sistema, execute o `Get-DscResource` cmdlet.

> [!NOTE]
> Nas versões do PowerShell antes de 7.0, `Get-DscResource` não encontra recursos de DSC baseados em classe.

O exemplo neste tópico demonstra como usar os recursos File e WindowsFeature. Para ver todas as propriedades que você pode usar com um recurso, insira o cursor na palavra-chave Resource (por exemplo, File) em seu script de configuração no ISE do <kbd>CTRL</kbd>PowerShell, mantenha a + <kbd>barra de espaços</kbd> CTRL

## <a name="find-more-resources"></a>ENCONTRAR MAIS RECURSOS

Você pode baixar, instalar e aprender sobre muitos outros recursos de DSC disponíveis que foram criados pela comunidade de usuários do PowerShell e do DSC e pela Microsoft. Visite a [Galeria do PowerShell](https://www.powershellgallery.com/) para procurar e saber mais sobre os recursos de DSC disponíveis.

## <a name="see-also"></a>CONSULTE TAMBÉM

[Visão geral da configuração de estado desejado do PowerShell](/powershell/scripting/dsc/overview/overview)

[Recursos internos de configuração de estado desejado do PowerShell](/powershell/scripting/dsc/resources/resources)

[Criar recursos personalizados de configuração de estado desejado do PowerShell](/powershell/scripting/dsc/resources/authoringResource)
