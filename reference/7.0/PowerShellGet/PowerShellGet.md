---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113539
Help Version: 7.0.1.0
keywords: powershell, cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: b4988bdfa027c439436073d683e1cc1013294fc8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890450"
---
# Módulo PowerShellGet

## Descrição

O PowerShellGet é um módulo com comandos para descobrir, instalar, atualizar e publicar artefatos do PowerShell, como módulos, recursos de DSC, recursos de função e scripts.

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## Cmdlets do PowerShellGet

### [Find-Command](Find-Command.md)
Localiza comandos do PowerShell em módulos.

### [Find-DscResource](Find-DscResource.md)
Localiza recursos de DSC (configuração de estado desejado).

### [Find-Module](Find-Module.md)
Localiza módulos em um repositório que corresponde aos critérios especificados.

### [Find-RoleCapability](Find-RoleCapability.md)
Localiza capacidades de função em módulos.

### [Find-Script](Find-Script.md)
Localiza um script.

### [Get-InstalledModule](Get-InstalledModule.md)
Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.

### [Get-InstalledScript](Get-InstalledScript.md)
Obtém um script instalado.

### [Get-PSRepository](Get-PSRepository.md)
Obtém repositórios do PowerShell.

### [Install-Module](Install-Module.md)
Baixa um ou mais módulos de um repositório e os instala no computador local.

### [Install-Script](Install-Script.md)
Instala um script.

### [New-ScriptFileInfo](New-ScriptFileInfo.md)
Cria um arquivo de script com metadados.

### [Publish-Module](Publish-Module.md)
Publica um módulo especificado do computador local em uma galeria online.

### [Publish-Script](Publish-Script.md)
Publica um script.

### [Register-PSRepository](Register-PSRepository.md)
Registra um repositório do PowerShell.

### [Save-Module](Save-Module.md)
Salva um módulo e suas dependências no computador local, mas não instala o módulo.

### [Save-Script](Save-Script.md)
Salva um script.

### [Set-PSRepository](Set-PSRepository.md)
Define valores para um repositório registrado.

### [Test-ScriptFileInfo](Test-ScriptFileInfo.md)
Valida um bloco de comentário para um script.

### [Uninstall-Module](Uninstall-Module.md)
Desinstala um módulo.

### [Uninstall-Script](Uninstall-Script.md)
Desinstala um script.

### [Unregister-PSRepository](Unregister-PSRepository.md)
Cancela o registro de um repositório.

### [Update-Module](Update-Module.md)
Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.

### [Update-ModuleManifest](Update-ModuleManifest.md)
Atualiza um arquivo de manifesto do módulo.

### [Update-Script](Update-Script.md)
Atualiza um script.

### [Update-ScriptFileInfo](Update-ScriptFileInfo.md)
Atualiza informações de um script.

