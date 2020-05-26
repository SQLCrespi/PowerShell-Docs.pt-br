---
title: Como importar cmdlets usando módulos | Microsoft Docs
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 840c5bc92d718ec4e54d864dc5e012cd33f83905
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811315"
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

[Importar-módulo](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Instalando módulos](../module/installing-a-powershell-module.md)

[Modificar o caminho de instalação PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Escrevendo um Cmdlet do Windows PowerShell](../cmdlet/cmdlet-overview.md)
