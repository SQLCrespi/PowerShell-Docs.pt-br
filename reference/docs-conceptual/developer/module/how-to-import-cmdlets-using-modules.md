---
title: Como importar cmdlets usando módulos | Microsoft Docs
ms.date: 08/28/2019
ms.openlocfilehash: fa8d629c14b06e3f9e9d6151cf09aa6b4acce358
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779362"
---
# <a name="how-to-import-cmdlets-using-modules"></a>Como importar cmdlets por meio de módulos

Este artigo descreve como importar cmdlets para uma sessão do PowerShell usando um módulo binário.

> [!NOTE]
> Os membros de módulos podem incluir cmdlets, provedores, funções, variáveis, aliases e muito mais. Os snap-ins podem conter apenas cmdlets e provedores.

## <a name="how-to-load-cmdlets-using-a-module"></a>Como carregar cmdlets usando um módulo

1. Crie uma pasta de módulo que tenha o mesmo nome que o arquivo de assembly no qual os cmdlets são implementados. Neste procedimento, a pasta do módulo é criada na pasta do Windows `system32` .

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. Verifique se a `PSModulePath` variável de ambiente inclui o caminho para a nova pasta do módulo. Por padrão, a pasta do sistema já foi adicionada à `PSModulePath` variável de ambiente. Para exibir o `PSModulePath` , digite: `$env:PSModulePath` .

1. Copie o assembly do cmdlet para a pasta do módulo.

1. Adicione um arquivo de manifesto de módulo ( `.psd1` ) na pasta raiz do módulo. O PowerShell usa o manifesto do módulo para importar o módulo. Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](../module/how-to-write-a-powershell-module-manifest.md).

1. Execute o seguinte comando para adicionar os cmdlets à sessão:

   `Import-Module [Module_Name]`

   Esse procedimento pode ser usado para testar seus cmdlets. Ele adiciona todos os cmdlets no assembly à sessão. Para obter mais informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>Confira também

[Como escrever um manifesto de módulo do Windows PowerShell](../module/how-to-write-a-powershell-module-manifest.md)

[Importar um módulo do PowerShell](../module/importing-a-powershell-module.md)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Instalando módulos](../module/installing-a-powershell-module.md)

[Modificar o caminho de instalação PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/cmdlet-overview.md)
