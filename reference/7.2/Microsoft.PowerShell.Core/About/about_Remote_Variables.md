---
description: Explica como usar variáveis locais e remotas em comandos remotos.
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: 1cd6d0c4562fcd63fc56f103ec41aa6f0bb4c01c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598022"
---
# <a name="about-remote-variables"></a>Sobre variáveis remotas

## <a name="short-description"></a>Descrição breve

Explica como usar variáveis locais e remotas em comandos remotos.

## <a name="long-description"></a>Descrição longa

Você pode usar variáveis em comandos que você executa em computadores remotos. Atribua um valor à variável e, em seguida, use a variável no lugar do valor.

Por padrão, as variáveis em comandos remotos são consideradas como definidas na sessão que executa o comando. As variáveis definidas em uma sessão local devem ser identificadas como variáveis locais no comando.

## <a name="using-remote-variables"></a>Usando variáveis remotas

O PowerShell assume que as variáveis usadas em comandos remotos são definidas na sessão em que o comando é executado.

Neste exemplo, a `$ps` variável é definida na sessão temporária na qual o `Get-WinEvent` comando é executado.

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

Quando o comando é executado em uma sessão persistente, **PSSession**, a variável remota deve ser definida nessa sessão.

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a>Usando variáveis locais

Você pode usar variáveis locais em comandos remotos, mas a variável deve ser definida na sessão local.

A partir do PowerShell 3,0, você pode usar o `Using` modificador de escopo para identificar uma variável local em um comando remoto.

A sintaxe do `Using` é a seguinte:

```
$Using:<VariableName>
```

No exemplo a seguir, a `$ps` variável é criada na sessão local, mas é usada na sessão na qual o comando é executado. O `Using` modificador de escopo identifica `$ps` como uma variável local.

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

O `Using` modificador de escopo pode ser usado em uma **PSSession**.

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

Uma referência de variável, como `$using:var` expande para o valor da variável `$var` do contexto do chamador. Você não tem acesso ao objeto de variável do chamador.
O `Using` modificador de escopo não pode ser usado para modificar uma variável local dentro de **PSSession**. Por exemplo, o código a seguir não funciona:

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

Para obter mais informações sobre o `Using` , consulte [about_Scopes](./about_Scopes.md)

### <a name="using-splatting"></a>Usando nivelamento

O PowerShell nivelamento passa uma coleção de valores e nomes de parâmetro para um comando. Para obter mais informações, consulte [about_Splatting](about_Splatting.md).

Neste exemplo, a variável nivelamento `$Splat` é uma tabela de hash configurada no computador local. O `Invoke-Command` conecta-se a uma sessão de computador remoto. O **scriptblock** usa o `Using` modificador de escopo com o `@` símbolo arroba () para representar a variável splatted.

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a>Outras situações em que o modificador de escopo ' Using ' é necessário

Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los. O `Using` modificador de escopo tem suporte nos seguintes contextos:

- Comandos executados remotamente, iniciados com `Invoke-Command` o uso dos parâmetros **ComputerName**, **hostname**, **SSHConnection** ou **Session** (sessão remota)
- Trabalhos em segundo plano, iniciados com `Start-Job` (sessão fora do processo)
- Trabalhos de thread, iniciados via `Start-ThreadJob` ou `ForEach-Object -Parallel` (sessão de thread separada)

Dependendo do contexto, os valores de variáveis inseridos são cópias independentes dos dados no escopo do chamador ou referências a ele. Em sessões remotas e fora do processo, elas são sempre cópias independentes. Em sessões de thread, elas são passadas por referência.

## <a name="serialization-of-variable-values"></a>Serialização de valores de variáveis

Comandos executados remotamente e trabalhos em segundo plano são executados fora do processo.
Sessões fora do processo usam serialização e desserialização baseadas em XML para tornar os valores das variáveis disponíveis nos limites do processo. O processo de serialização converte objetos em um **PSObject** que contém as propriedades dos objetos originais, mas não seus métodos.

Para um conjunto limitado de tipos, a desserialização rehydrates objetos de volta para o tipo original. O objeto de resalimentação é uma cópia da instância do objeto original.
Ele tem as propriedades e os métodos do tipo. Para tipos simples, como **System. Version**, a cópia é exata. Para tipos complexos, a cópia é imperfeita. Por exemplo, os objetos de certificado resalimentados não incluem a chave privada.

Instâncias de todos os outros tipos são instâncias de **PSObject** . A propriedade **PSTypeNames** contém o nome do tipo original prefixado com **desserializado**, por exemplo, **Deserialized.System. Data. DataTable**

## <a name="using-local-variables-with-argumentlist-parameter"></a>Usando variáveis locais com parâmetro **ArgumentList**

Você pode usar variáveis locais em um comando remoto definindo parâmetros para o comando remoto e usando o parâmetro **ArgumentList** do `Invoke-Command` cmdlet para especificar a variável local como o valor do parâmetro.

- Use a `param` palavra-chave para definir parâmetros para o comando remoto. Os nomes de parâmetro são espaços reservados que não precisam corresponder ao nome da variável local.

- Use os parâmetros definidos pela `param` palavra-chave no comando.

- Use o parâmetro **ArgumentList** do `Invoke-Command` cmdlet para especificar a variável local como o valor do parâmetro.

Por exemplo, os comandos a seguir definem a `$ps` variável na sessão local e, em seguida, o usam em um comando remoto. O comando usa `$log` como o nome do parâmetro e a variável local, `$ps` , como seu valor.

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a>Consulte também

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Splatting](about_Splatting.md)

[about_Variables](about_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Start-ThreadJob](xref:ThreadJob.Start-ThreadJob)

@Microsoft.PowerShell.Core.ForEach-Object

