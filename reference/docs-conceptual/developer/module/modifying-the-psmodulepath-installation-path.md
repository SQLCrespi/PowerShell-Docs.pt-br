---
title: Modificando o caminho de instalação do PSModulePath | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 5957ea4c15cd3778bd09b67c4b97de0ef0cfdd2a
ms.sourcegitcommit: 0e4c69d8b5cf71431592fe41da816dec9b70f1f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "74953833"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Modificar o caminho de instalação PSModulePath

A variável de ambiente `PSModulePath` armazena os caminhos para os locais dos módulos que estão instalados no disco. O PowerShell usa essa variável para localizar módulos quando o usuário não especifica o caminho completo para um módulo. Os caminhos nessa variável são pesquisados na ordem em que aparecem.

Quando o PowerShell é iniciado, `PSModulePath` é criado como uma variável de ambiente do sistema com o seguinte valor padrão: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` ou `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` para Windows PowerShell.

## <a name="to-view-the-psmodulepath-variable"></a>Para exibir a variável PSModulePath

Para exibir os caminhos especificados na variável `PSModulePath`, digite o seguinte comando:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Para adicionar locais à variável PSModulePath

Para adicionar caminhos a essa variável, use um dos seguintes métodos:

- Para adicionar um valor temporário que está disponível somente para a sessão atual, execute o seguinte comando na linha de comando:

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- Para adicionar um valor persistente que esteja disponível sempre que uma sessão for aberta, adicione o comando acima a um arquivo de perfil do PowerShell (`$PROFILE`) >

  Para obter mais informações sobre perfis, consulte [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

- Para adicionar uma variável persistente ao registro, crie uma nova variável de ambiente de usuário chamada `PSModulePath` usando o editor de variáveis de ambiente na caixa de diálogo **Propriedades do sistema** .

- Para adicionar uma variável persistente usando um script, use o método .NET [SetEnvironmentVariable não](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable) na classe [System. Environment](https://docs.microsoft.com/dotnet/api/system.environment) . Por exemplo, o script a seguir adiciona o caminho `C:\Program Files\Fabrikam\Module` ao valor da variável de ambiente `PSModulePath` para o computador. Para adicionar o caminho para o usuário `PSModulePath` variável de ambiente, defina o destino como "usuário".

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Para remover locais do PSModulePath

Você pode remover caminhos da variável usando métodos semelhantes: por exemplo, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` removerá o caminho **c:\ModulePath** da sessão atual.

## <a name="see-also"></a>Consulte Também

[Escrevendo um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
