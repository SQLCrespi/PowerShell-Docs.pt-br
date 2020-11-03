---
description: Explica como usar a ferramenta de linha de comando PowerShell_Ise.exe.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196169"
---
# <a name="about-powershell-iseexe"></a>Sobre Ise.exe do PowerShell

## <a name="short-description"></a>DESCRIÇÃO BREVE

Explica como usar a ferramenta de linha de comando PowerShell_Ise.exe.

## <a name="long-description"></a>DESCRIÇÃO LONGA

PowerShell_Ise.exe inicia uma sessão de Ambiente de Script Integrado do Windows PowerShell (ISE). Você pode executá-lo em Cmd.exe e no Windows PowerShell.

Para executar PowerShell_ISE.exe, digite PowerShell_ISE.exe, PowerShell_ISE ou ISE.

## <a name="syntax"></a>SYNTAX

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a>PARAMETERS

### <a name="-file"></a>-File

Abre os arquivos especificados no ISE do Windows PowerShell. O nome do parâmetro ("-File") é opcional. Para listar mais de um arquivo, insira uma cadeia de caracteres de texto entre aspas. Use vírgulas para separar os nomes de arquivo dentro da cadeia de caracteres.

Por exemplo:

PowerShell_ISE-File "File1.ps1, File2.ps1 File3.xml".

Os espaços entre os nomes de arquivo são permitidos no Windows PowerShell, mas podem não ser interpretados corretamente por outros programas, como Cmd.exe.

Você pode usar esse parâmetro para abrir qualquer arquivo de texto, incluindo arquivos de script do Windows PowerShell e arquivos XML.

### <a name="-mta"></a>-Mta

Inicia ISE do Windows PowerShell usando um apartamento multi-threaded. Este parâmetro é introduzido no Windows PowerShell 3.0. STA (single-threaded apartment) é o padrão.

### <a name="-noprofile"></a>-NoProfile

Não executa perfis do Windows PowerShell. Por padrão, os perfis do Windows PowerShell são executados em cada sessão.

Esse parâmetro é recomendado quando você está gravando conteúdo compartilhado, como funções e scripts que serão executados em sistemas com perfis diferentes.
Para obter mais informações, consulte [about_Profiles](about_Profiles.md).

### <a name="-help---"></a>-Ajuda-?,/?

Exibe a ajuda para PowerShell_ISE.exe.

## <a name="examples"></a>EXEMPLOS

Esses comandos iniciam ISE do Windows PowerShell. Os comandos são equivalentes e podem ser usados intercambiavelmente.

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

Esses comandos abrem o script Get-Profile.ps1 no ISE do Windows PowerShell.
Os comandos são equivalentes e podem ser usados intercambiavelmente.

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

Esse comando abre o Get-Backups.ps1 e Get-BackupInstance.ps1 scripts no ISE do Windows PowerShell. Para abrir mais de um arquivo, use uma vírgula para separar os nomes de arquivo e coloque o valor do nome de arquivo inteiro entre aspas.

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

Este comando inicia ISE do Windows PowerShell sem perfis.

```
PS C:> ISE -NoProfile
```

Este comando obtém ajuda para PowerShell_ISE.exe.

```
PS C:> ISE -help
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_PowerShell.exe](about_PowerShell_exe.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)

[Ambiente de Script Integrado do Windows PowerShell (ISE)](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
