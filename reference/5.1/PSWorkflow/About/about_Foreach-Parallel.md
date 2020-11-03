---
description: Descreve a `ForEach -Parallel` construção de linguagem no fluxo de trabalho do Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach paralelo
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195811"
---
# <a name="about-foreach-parallel"></a>Sobre Foreach-Parallel

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve a `ForEach -Parallel` construção de linguagem no fluxo de trabalho do Windows PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O parâmetro **Parallel** da `ForEach` palavra-chave executa os comandos em um bloco de `ForEach` script uma vez para cada item em uma coleção especificada.

Os itens na coleção, como um disco em uma coleção de discos, são processados em paralelo. Os comandos no bloco de script são executados em sequência em cada item da coleção.

`ForEach -Parallel` é válido somente em um fluxo de trabalho do Windows PowerShell.

### <a name="syntax"></a>SYNTAX

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a>DESCRIÇÃO DETALHADA

Assim como a instrução ForEach no Windows PowerShell, a variável que contém a coleção `$<collection>` deve ser definida antes da `ForEach -Parallel` instrução, mas a variável que representa o item atual `$<item>` é definida na `ForEach -Parallel` instrução.

A `ForEach -Parallel` construção é diferente da `ForEach` palavra-chave e do parâmetro **paralelo** . A `ForEach` palavra-chave processa os itens na coleção em sequência. O parâmetro **Parallel** executa comandos em um bloco de script em paralelo. Você pode colocar um bloco de script paralelo em um `ForEach -Parallel` bloco de script.

Os computadores de destino em um fluxo de trabalho, como aqueles especificados pelo parâmetro comum do fluxo de trabalho **PSComputerName** , são sempre processados em paralelo.
Você não precisa especificar a `ForEach -Parallel` palavra-chave para essa finalidade.

### <a name="examples"></a>EXEMPLOS

O fluxo de trabalho a seguir contém uma `ForEach -Parallel` instrução que processa os discos que a `Get-Disk` atividade obtém. Os comandos no `ForEach -Parallel` bloco de script são executados em sequência, mas eles são executados nos discos em paralelo. Os discos podem ser processados simultaneamente e em qualquer ordem.

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[Writing a Script Workflow](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)
