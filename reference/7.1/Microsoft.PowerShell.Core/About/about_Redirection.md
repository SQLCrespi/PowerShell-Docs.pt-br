---
description: Explica como redirecionar a saída do PowerShell para arquivos de texto.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 85b719b7af11cce2396e7d62fcc638007b55c834
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040891"
---
# <a name="about-redirection"></a>Sobre o redirecionamento

## <a name="short-description"></a>Descrição breve
Explica como redirecionar a saída do PowerShell para arquivos de texto.

## <a name="long-description"></a>Descrição longa

Por padrão, o PowerShell envia a saída para o host do PowerShell. Geralmente, esse é o aplicativo de console. No entanto, você pode direcionar a saída para um arquivo de texto e pode redirecionar a saída de erro para o fluxo de saída regular.

Você pode usar os seguintes métodos para redirecionar a saída:

- Use o `Out-File` cmdlet, que envia a saída de comando para um arquivo de texto.
  Normalmente, você usa o `Out-File` cmdlet quando precisa usar seus parâmetros, como os `Encoding` `Force` parâmetros,, `Width` ou `NoClobber` .

- Use o `Tee-Object` cmdlet, que envia a saída do comando para um arquivo de texto e, em seguida, o envia para o pipeline.

- Use os operadores de redirecionamento do PowerShell. Usar o operador de redirecionamento com um destino de arquivo é funcionalmente equivalente a direcionar para o sem `Out-File` Parâmetros extras.

Para obter mais informações sobre fluxos, consulte [about_Output_Streams](about_Output_Streams.md).

### <a name="redirectable-output-streams"></a>Fluxos de saída redirecionáveis

O PowerShell dá suporte ao redirecionamento dos fluxos de saída a seguir.

| Fluxo # |      Descrição       | Introduzido em  |    Cmdlet de gravação     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | **Êxito** Fluxo     | PowerShell 2.0 | `Write-Output`      |
| 2        | **Erro** do Fluxo       | PowerShell 2.0 | `Write-Error`       |
| 3        | **Aviso** Fluxo     | PowerShell 3.0 | `Write-Warning`     |
| 4        | **Modo detalhado** Fluxo     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | **Depurar** Fluxo       | PowerShell 3.0 | `Write-Debug`       |
| 6        | **Informações** do Fluxo | PowerShell 5.0 | `Write-Information` |
| *        | Todos os fluxos            | PowerShell 3.0 |                     |

> [!NOTE]
> Também há um fluxo de **progresso** no PowerShell, mas ele não dá suporte ao redirecionamento.

### <a name="powershell-redirection-operators"></a>Operadores de redirecionamento do PowerShell

Os operadores de redirecionamento do PowerShell são os seguintes, onde `n` representa o número do fluxo. O fluxo de **êxito** ( `1` ) será o padrão se nenhum fluxo for especificado.

| Operador |                         Descrição                         | Syntax |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | Enviar o fluxo especificado para um arquivo.                            | `n>`   |
| `>>`     | **Acrescentar** o fluxo especificado a um arquivo.                      | `n>>`  |
| `>&1`    | _Redireciona_ o fluxo especificado para o fluxo de **êxito** . | `n>&1` |

> [!NOTE]
> Ao contrário de alguns shells do UNIX, você só pode redirecionar outros fluxos para o fluxo de **êxito** .

## <a name="examples"></a>Exemplos

### <a name="example-1-redirect-errors-and-output-to-a-file"></a>Exemplo 1: redirecionar erros e saída para um arquivo

Este exemplo é executado `dir` em um item que terá sucesso e um que será um erro.

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

Ele usa `2>&1` para redirecionar o fluxo de **erros** para o fluxo de **êxito** e `>` para enviar o fluxo de **êxito** resultante para um arquivo chamado `dir.log`

### <a name="example-2-send-all-success-stream-data-to-a-file"></a>Exemplo 2: enviar todos os dados de fluxo de êxito para um arquivo

Este exemplo envia todos os dados de fluxo de **êxito** para um arquivo chamado `script.log` .

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a>Exemplo 3: enviar fluxos de êxito, de aviso e de erro para um arquivo

Este exemplo mostra como você pode combinar operadores de redirecionamento para obter um resultado desejado.

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- `3>&1` redireciona o fluxo de **aviso** para o fluxo de **êxito** .
- `2>&1` redireciona o fluxo de **erro** para o fluxo de **êxito** (que também inclui todos os dados de fluxo de **aviso** )
- `>` redireciona o fluxo de **êxito** (que agora contém os fluxos de **aviso** e de **erro** ) para um arquivo chamado `C:\temp\redirection.log` )

### <a name="example-4-redirect-all-streams-to-a-file"></a>Exemplo 4: redirecionar todos os fluxos para um arquivo

Este exemplo envia a saída de todos os fluxos de um script chamado `script.ps1` para um arquivo chamado `script.log`

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a>Exemplo 5: suprimir todos os Write-Host e dados de fluxo de informações

Este exemplo suprime todos os dados de fluxo de informações. Para ler mais sobre os cmdlets de fluxo de **informações** , consulte [write-host](xref:Microsoft.PowerShell.Utility.Write-Host) e [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a>Exemplo 6: mostrar o efeito das preferências de ação

Variáveis de preferência de ação e parâmetros podem alterar o que é gravado em um fluxo específico. O script neste exemplo mostra como o valor de `$ErrorActionPreference` afeta o que é gravado no fluxo de **erro** .

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

Quando executamos esse script, recebemos uma solicitação quando `$ErrorActionPreference` é definido como `Inquire` .

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

Quando examinamos o arquivo de log, vemos o seguinte:

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a>Observações

Os operadores de redirecionamento que não acrescentam dados ( `>` e `n>` ) substituem o conteúdo atual do arquivo especificado sem aviso.

No entanto, se o arquivo for somente leitura, oculto ou arquivo do sistema, o redirecionamento **falhará**. Os operadores de redirecionamento de acréscimo ( `>>` e `n>>` ) não gravam em um arquivo somente leitura, mas acrescentam conteúdo a um sistema ou arquivo oculto.

Para forçar o redirecionamento de conteúdo para um arquivo somente leitura, oculto ou de sistema, use o `Out-File` cmdlet com seu `Force` parâmetro.

Quando você está gravando em arquivos, os operadores de redirecionamento usam `UTF8NoBOM` codificação. Se o arquivo tiver uma codificação diferente, a saída poderá não ser formatada corretamente. Para gravar em arquivos com uma codificação diferente, use o `Out-File` cmdlet com seu `Encoding` parâmetro.

### <a name="potential-confusion-with-comparison-operators"></a>Possível confusão com operadores de comparação

O `>` operador não deve ser confundido com o operador de comparação [maior que](about_Comparison_Operators.md#-gt--ge--lt-and--le) (geralmente indicado como `>` em outras linguagens de programação).

Dependendo dos objetos que estão sendo comparados, a saída usando `>` pode parecer correta (porque 36 não é maior que 42).

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

No entanto, uma verificação do sistema de arquivos local pode ver que um arquivo chamado `42` foi gravado, com o conteúdo `36` .

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

A tentativa de usar a comparação inversa `<` (menor que) produz um erro do sistema:

```powershell
PS> if (36 < 42) { "true" } else { "false" }
ParserError:
Line |
   1 |  if (36 < 42) { "true" } else { "false" }
     |         ~
     | The '<' operator is reserved for future use.
```

Se a comparação numérica for a operação necessária `-lt` e `-gt` deve ser usada. Para obter mais informações, consulte o `-gt` operador em [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).

## <a name="see-also"></a>Confira também

- [Out-File](xref:Microsoft.PowerShell.Utility.Out-File)
- [Tee-Object](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [about_Output_Streams](about_Output_Streams.md)
- [about_Operators](about_Operators.md)
- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Path_Syntax](about_Path_Syntax.md)
