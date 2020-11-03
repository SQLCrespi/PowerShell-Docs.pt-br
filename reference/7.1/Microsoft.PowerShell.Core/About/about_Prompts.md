---
description: Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: c21c51a58beeb454e785e57989d3b4a75d575d0e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196345"
---
# <a name="about-prompts"></a>Sobre os prompts

## <a name="short-description"></a>Descrição breve
Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .

## <a name="long-description"></a>Descrição longa

O prompt de comando do PowerShell indica que o PowerShell está pronto para executar um comando:

```
PS C:\>
```

O prompt do PowerShell é determinado pela `Prompt` função interna. Você pode personalizar o prompt criando sua própria `Prompt` função e salvando-a em seu perfil do PowerShell.

## <a name="about-the-prompt-function"></a>Sobre a função de prompt

A `Prompt` função determina a aparência do prompt do PowerShell.
O PowerShell vem com uma função interna `Prompt` , mas você pode substituí-la definindo sua própria `Prompt` função.

A `Prompt` função tem a seguinte sintaxe:

```powershell
function Prompt { <function-body> }
```

A `Prompt` função deve retornar um objeto. Como prática recomendada, retorne uma cadeia de caracteres ou um objeto formatado como uma cadeia de caracteres. O comprimento máximo recomendado é de 80 caracteres.

Por exemplo, a função a seguir `Prompt` retorna uma cadeia de caracteres "Olá, mundo" seguida por um colchete angular direito ( `>` ).

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a>Obtendo a função prompt

Para obter a `Prompt` função, use o `Get-Command` cmdlet ou use o `Get-Item` cmdlet na unidade de função.

Por exemplo:

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

Para obter o script que define o valor do prompt, use o método dot para obter a propriedade **scriptblock** da `Prompt` função.

Por exemplo:

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

Como todas as funções, a `Prompt` função é armazenada na `Function:` unidade.
Para exibir o script que cria a `Prompt` função atual, digite:

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a>O prompt padrão

O prompt padrão aparece somente quando a `Prompt` função gera um erro ou não retorna um objeto.

O prompt padrão do PowerShell é:

```
PS>
```

Por exemplo, o comando a seguir define a `Prompt` função como `$null` , que é inválida. Como resultado, o prompt padrão é exibido.

```powershell
PS C:\> function prompt {$null}
PS>
```

Como o PowerShell é fornecido com um prompt interno, normalmente, você não vê o prompt padrão.

### <a name="built-in-prompt"></a>Prompt interno

O PowerShell inclui uma função interna `Prompt` .

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

A função usa o `Test-Path` cmdlet para determinar se a `$PSDebugContext` variável automática é populada. Se `$PSDebugContext` estiver populado, você estará no modo de depuração e `[DBG]:` será adicionado ao prompt da seguinte maneira:

```Output
[DBG]: PS C:\ps-test>
```

Se `$PSDebugContext` não for populado, a função será adicionada `PS` ao prompt.
E, a função usa o `Get-Location` cmdlet para obter o local do diretório do sistema de arquivos atual. Em seguida, ele adiciona um colchete angular direito ( `>` ).

Por exemplo:

```Output
PS C:\ps-test>
```

Se você estiver em um prompt aninhado, a função adicionará dois colchetes angulares ( `>>` ) ao prompt. (Você estará em um prompt aninhado se o valor da `$NestedPromptLevel` variável automática for maior que 1.)

Por exemplo, quando você estiver Depurando em um prompt aninhado, o prompt será semelhante ao seguinte prompt:

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a>Alterações no prompt

O `Enter-PSSession` cmdlet precede o nome do computador remoto para a `Prompt` função atual. Quando você usa o `Enter-PSSession` cmdlet para iniciar uma sessão com um computador remoto, o prompt de comando é alterado para incluir o nome do computador remoto. Por exemplo:

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

Outros aplicativos host do PowerShell e shells alternativos podem ter seus próprios prompts de comando personalizados.

Para obter mais informações sobre `$PSDebugContext` as `$NestedPromptLevel` variáveis automáticas e, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

### <a name="how-to-customize-the-prompt"></a>Como personalizar o prompt

Para personalizar o prompt, escreva uma nova `Prompt` função. A função não está protegida, portanto, você pode substituí-la.

Para gravar uma `Prompt` função, digite o seguinte:

```powershell
function prompt { }
```

Em seguida, entre as chaves, insira os comandos ou a cadeia de caracteres que cria o prompt.

Por exemplo, o seguinte prompt inclui o nome do computador:

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

No computador Server01, o prompt é semelhante ao seguinte prompt:

```Output
PS [Server01] >
```

A função a seguir `Prompt` inclui a data e a hora atuais:

```powershell
function prompt {"$(Get-Date)> "}
```

O prompt é semelhante ao seguinte prompt:

```Output
03/15/2012 17:49:47>
```

Você também pode alterar a `Prompt` função padrão:

Por exemplo, a função modificada a seguir `Prompt` adiciona `[ADMIN]:` ao prompt interno do PowerShell quando o PowerShell é aberto usando a opção **Executar como administrador** :

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

Quando você inicia o PowerShell usando a opção **Executar como administrador** , um prompt semelhante ao seguinte prompt é exibido:

```Output
[ADMIN]: PS C:\ps-test>
```

A função a seguir `Prompt` exibe a ID do histórico do próximo comando. Para exibir o histórico de comandos, use o `Get-History` cmdlet.

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

O prompt a seguir usa `Write-Host` os `Get-Random` cmdlets e para criar um prompt que altera a cor aleatoriamente. Como `Write-Host` o grava no aplicativo host atual, mas não retorna um objeto, essa função inclui uma `Return` instrução. Sem ele, o PowerShell usa o prompt padrão, `PS>` .

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a>Salvando a função prompt

Como qualquer função, a `Prompt` função existe somente na sessão atual. Para salvar a `Prompt` função para sessões futuras, adicione-a aos seus perfis do PowerShell. Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).

## <a name="see-also"></a>Confira também

[Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Get-History](xref:Microsoft.PowerShell.Core.Get-History)

[Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random)

[Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)

[about_Profiles](about_Profiles.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Debuggers](about_Debuggers.md)

[about_Automatic_Variables](about_Automatic_Variables.md)

