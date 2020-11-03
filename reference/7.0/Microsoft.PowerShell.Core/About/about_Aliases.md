---
description: Descreve como usar nomes alternativos para cmdlets e comandos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 409e6b01f32c5a6f60ac4b450ff08998caf1084a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196118"
---
# <a name="about-aliases"></a>Sobre aliases

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como usar nomes alternativos para cmdlets e comandos no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Um alias é um nome alternativo ou apelido para um cmdlet ou para um elemento de comando, como uma função, script, arquivo ou arquivo executável. Você pode usar o alias em vez do nome do comando em qualquer comando do PowerShell.

Para criar um alias, use o cmdlet New-Alias. Por exemplo, o comando a seguir cria o alias de "gás" para o `Get-AuthenticodeSignature` cmdlet:

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

Depois de criar o alias para o nome do cmdlet, você pode usar o alias em vez do nome do cmdlet. Por exemplo, para obter a assinatura Authenticode para o arquivo de SqlScript.ps1, digite:

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

Ou, digite:

```powershell
gas SqlScript.ps1
```

Se você criar "Word" como o alias para Microsoft Office Word, poderá digitar "Word" em vez do seguinte:

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a>ALIASES INTERNOS

O PowerShell inclui um conjunto de aliases internos, incluindo "CD" e "chdir" para o cmdlet Set-Location, e "ls" e "dir" para o cmdlet Get-ChildItem.

Para obter todos os aliases no computador, incluindo os aliases internos, digite:

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a>CMDLETS DE ALIAS

O PowerShell inclui os seguintes cmdlets, que são projetados para trabalhar com aliases:

- `Get-Alias` -Obtém todos os aliases na sessão atual.
- `New-Alias` -Cria um novo alias.
- `Set-Alias` -Cria ou altera um alias.
- `Export-Alias` -Exporta um ou mais aliases para um arquivo.
- `Import-Alias` -Importa um arquivo de alias para o PowerShell.

Para obter informações detalhadas sobre os cmdlets, digite:

```powershell
Get-Help <cmdlet-Name> -Detailed
```

Por exemplo, digite:

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a>CRIANDO UM ALIAS

Para criar um novo alias, use o cmdlet New-Alias. Por exemplo, para criar o alias "GH" para Get-Help, digite:

```powershell
New-Alias -Name gh -Value Get-Help
```

Você pode usar o alias em comandos, assim como você usaria o nome completo do cmdlet, e você pode usar o alias com parâmetros.

Por exemplo, para obter ajuda detalhada para o cmdlet Get-WmiObject, digite:

```powershell
Get-Help Get-WmiObject -Detailed
```

Ou, digite:

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a>SALVANDO ALIASES

Os aliases que você cria são salvos somente na sessão atual. Para usar os aliases em uma sessão diferente, adicione o alias ao seu perfil do PowerShell. Ou use o cmdlet Export-Alias para salvar os aliases em um arquivo.

Para obter mais informações, digite: 

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a>OBTENDO ALIASES

Para obter todos os aliases na sessão atual, incluindo os aliases internos, os aliases em seus perfis do PowerShell e os aliases que você criou na sessão atual, digite o texto:

```powershell
Get-Alias
```

Para obter aliases específicos, use o parâmetro Name do cmdlet Get-Alias. Por exemplo, para obter aliases que começam com "p", digite:

```powershell
Get-Alias -Name p*
```

Para obter os aliases de um item específico, use o parâmetro de definição. Por exemplo, para obter os aliases para o tipo de cmdlet Get-ChildItem:

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a>SAÍDA DE GET-ALIAS

Get-Alias retorna apenas um tipo de objeto, um objeto AliasInfo (System. Management. Automation. AliasInfo). O nome dos aliases que não incluem um hífen, como "CD", são exibidos no seguinte formato:

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

Isso torna muito rápido e fácil obter as informações de que você precisa.

O formato de nome de alias com base em seta não é usado para aliases que incluem um hífen. Esses são provavelmente nomes substitutos preferidos para cmdlets e funções, em vez de abreviações típicas ou apelidos, e o autor talvez não queira que eles estejam tão evidentes.

## <a name="alternate-names-for-commands-with-parameters"></a>NOMES ALTERNATIVOS PARA COMANDOS COM PARÂMETROS

Você pode atribuir um alias a um cmdlet, script, função ou arquivo executável. Você não pode atribuir um alias a um comando e seus parâmetros. Por exemplo, você pode atribuir um alias ao `Get-Eventlog` cmdlet, mas não pode atribuir um alias ao `Get-Eventlog -LogName System` comando.

Você pode criar uma função que inclui o comando. Para criar uma função, digite a palavra "função" seguida por um nome para a função. Digite o comando e coloque-o entre chaves ( {} ).

Por exemplo, o comando a seguir cria a função syslog. Essa função representa o `Get-Eventlog -LogName System` comando:

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

Agora você pode digitar "syslog" em vez do comando. E, você pode criar aliases para a nova função.

Para obter mais informações sobre o functions, digite:

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a>OBJETOS DE ALIAS

Os aliases do PowerShell são representados por objetos que são instâncias da classe System. Management. Automation. AliasInfo. Para obter mais informações sobre esse tipo de objeto, consulte [classe AliasInfo][aliasinfo] na biblioteca do Microsoft Developer Network (MSDN).

Para exibir as propriedades e os métodos dos objetos de alias, obtenha os aliases.
Em seguida, direcione-os para o cmdlet Get-Member. Por exemplo:

```powershell
Get-Alias | Get-Member
```

Para exibir os valores das propriedades de um alias específico, como o `dir` alias, obtenha o alias. Em seguida, redirecione-o para o cmdlet Format-List. Por exemplo, o comando a seguir obtém o alias "dir". Em seguida, o comando canaliza o alias para o cmdlet Format-List. Em seguida, o comando usa o parâmetro Property de Format-List com um caractere curinga ( \* ) para exibir todas as propriedades do `dir` alias. O comando a seguir executa estas tarefas:

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a>PROVEDOR de ALIAS do PowerShell

O PowerShell inclui o provedor de alias. O provedor de alias permite exibir os aliases no PowerShell como se estivessem em uma unidade do sistema de arquivos.

O provedor de alias expõe a unidade Alias:. Para entrar na unidade Alias:, digite:

```powershell
Set-Location Alias:
```

Para exibir o conteúdo da unidade, digite:

```powershell
Get-ChildItem
```

Para exibir o conteúdo da unidade de outra unidade do PowerShell, inicie o caminho com o nome da unidade. Inclua os dois-pontos (:). Por exemplo:

```powershell
Get-ChildItem -Path Alias:
```

Para obter informações sobre um alias específico, digite o nome da unidade e o nome do alias. Ou digite um padrão de nome. Por exemplo, para obter todos os aliases que começam com "p", digite:

```powershell
Get-ChildItem -Path Alias:p*
```

Para obter mais informações sobre o provedor de alias do PowerShell, digite:

```powershell
Get-Help Alias
```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [about_functions](about_functions.md)
- [about_profiles](about_profiles.md)
- [about_providers](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
