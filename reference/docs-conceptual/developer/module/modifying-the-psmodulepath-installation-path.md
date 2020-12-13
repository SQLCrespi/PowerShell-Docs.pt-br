---
ms.date: 09/13/2016
ms.topic: reference
title: Modificar o caminho de instalação PSModulePath
description: Modificar o caminho de instalação PSModulePath
ms.openlocfilehash: b802492bf9b49e8165e296817e3f80b9ae8265a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661952"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Modificar o caminho de instalação PSModulePath

A `PSModulePath` variável de ambiente armazena os caminhos para os locais dos módulos que estão instalados no disco. O PowerShell usa essa variável para localizar módulos quando o usuário não especifica o caminho completo para um módulo. Os caminhos nessa variável são pesquisados na ordem em que aparecem.

Quando o PowerShell é iniciado, `PSModulePath` é criado como uma variável de ambiente do sistema com o seguinte valor padrão: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` no Windows e `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` no Linux ou Mac, e `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` para o Windows PowerShell.

> [!NOTE]
> O local **CurrentUser** específico do usuário é a `WindowsPowerShell\Modules` pasta localizada no local **documentos** em seu perfil de usuário. O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta. Por padrão, no Windows 10, esse local é `$HOME\Documents\WindowsPowerShell\Modules` .

## <a name="to-view-the-psmodulepath-variable"></a>Para exibir a variável PSModulePath

Para exibir os caminhos especificados na `PSModulePath` variável, digite o seguinte comando:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Para adicionar locais à variável PSModulePath

Para adicionar caminhos a essa variável, use um dos seguintes métodos:

- Para adicionar um valor temporário que está disponível somente para a sessão atual, execute o seguinte comando na linha de comando:

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- Para adicionar um valor persistente que esteja disponível sempre que uma sessão for aberta, adicione o comando acima a um arquivo de perfil do PowerShell ( `$PROFILE` ) >

  Para obter mais informações sobre perfis, consulte [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

- Para adicionar uma variável persistente ao registro, crie uma nova variável de ambiente de usuário chamada `PSModulePath` usando o editor de variáveis de ambiente na caixa de diálogo **Propriedades do sistema** .

- Para adicionar uma variável persistente usando um script, use o método .NET [SetEnvironmentVariable não](/dotnet/api/system.environment.setenvironmentvariable) na classe [System. Environment](/dotnet/api/system.environment) . Por exemplo, o script a seguir adiciona o `C:\Program Files\Fabrikam\Module` caminho para o valor da `PSModulePath` variável de ambiente para o computador. Para adicionar o caminho à variável de `PSModulePath` ambiente do usuário, defina o destino como "usuário".

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Para remover locais do PSModulePath

Você pode remover caminhos da variável usando métodos semelhantes: por exemplo, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` removerá o caminho **c:\ModulePath** da sessão atual.

## <a name="see-also"></a>Consulte Também

[Escrever um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)

[about_Modules](/powershell/module/microsoft.powershell.core/about/about_modules)
