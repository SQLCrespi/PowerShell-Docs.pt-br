---
description: Descreve como definir valores padrão personalizados para parâmetros de cmdlet e funções avançadas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: c2bc8c64b6b3c0d3627d9db61132dde58522555e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196114"
---
# <a name="about-parameters-default-values"></a>Sobre valores padrão de parâmetros

## <a name="short-description"></a>Descrição breve

Descreve como definir valores padrão personalizados para parâmetros de cmdlet e funções avançadas.

## <a name="long-description"></a>Descrição longa

A `$PSDefaultParameterValues` variável de preferência permite especificar valores padrão personalizados para qualquer cmdlet ou função avançada. Os cmdlets e as funções avançadas usam o valor padrão personalizado, a menos que você especifique outro valor no comando.

Os autores de cmdlets e funções avançadas definem valores padrão para seus parâmetros. Normalmente, os valores padrão são úteis, mas eles podem não ser apropriados para todos os ambientes.

Esse recurso é especialmente útil quando você deve especificar o mesmo valor de parâmetro alternativo quase sempre que usar o comando ou quando um valor de parâmetro específico for difícil de lembrar, como um nome de servidor de email ou GUID de projeto.

Se o valor padrão desejado variar de forma previsível, você poderá especificar um bloco de script que forneça valores padrão diferentes para um parâmetro sob condições diferentes.

`$PSDefaultParameterValues` foi introduzido no PowerShell 3,0.

## <a name="syntax"></a>Syntax

A `$PSDefaultParameterValues` variável é uma tabela de hash que valida o formato das chaves como um tipo de objeto de **System. Management. Automation. DefaultParameterDictionary** . A tabela de hash contém pares de **chave/valor** . Uma **chave** está no formato `CmdletName:ParameterName` . Um **valor** é o **DefaultValue** ou **scriptblock** atribuído à chave.

A sintaxe da `$PSDefaultParameterValues` variável de preferência é a seguinte:

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

Caracteres curinga são permitidos nos valores **CmdletName** e **ParameterName** .

Para definir, alterar, adicionar ou remover um par de **chave/valor** específico de `$PSDefaultParameterValues` , use os métodos para editar uma tabela de hash padrão. Por exemplo, os métodos **Add** e **Remove** . Esses métodos não substituem outros valores na tabela de hash.

Há outra sintaxe que não substitui uma tabela de `$PSDefaultParameterValues` hash existente. Para adicionar ou alterar um par de **chave/valor** específico, use a seguinte sintaxe:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

O **CmdletName** deve ser o nome de um cmdlet ou o nome de uma função avançada que usa o atributo **CmdletBinding** . Você não pode usar o `$PSDefaultParameterValues` para especificar valores padrão para scripts ou funções simples.

O **DefaultValue** pode ser um objeto ou um bloco de script. Se o valor for um bloco de script, o PowerShell avaliará o bloco de script e usará o resultado como o valor do parâmetro. Quando o parâmetro especificado aceita um valor de bloco de script, coloque o valor de bloco de script em um segundo conjunto de chaves, como:

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

Para obter mais informações, consulte um dos seguintes documentos:

- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Preference_Variables](about_Preference_Variables.md)

## <a name="examples"></a>Exemplos

### <a name="how-to-set-psdefaultparametervalues"></a>Como definir \$ PSDefaultParameterValues

`$PSDefaultParameterValues` é uma variável de preferência, portanto, ela existe somente na sessão na qual ela está definida. Não tem nenhum valor padrão.

Para definir `$PSDefaultParameterValues` , digite o nome da variável e um ou mais pares **chave/valor** . Se você executar outro `$PSDefaultParameterValues` comando, ele substituirá a tabela de hash existente.

Para obter exemplos de como alterar os pares de **chave/valor** sem substituir os valores de tabela de hash existentes, consulte [como adicionar valores a \$ PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) ou [como alterar valores em \$ PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).

Para salvar em `$PSDefaultParameterValues` sessões futuras, adicione um `$PSDefaultParameterValues` comando ao seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](about_Profiles.md).

#### <a name="set-a-custom-default-value"></a>Definir um valor padrão personalizado

O par **chave/valor** define a `Send-MailMessage:SmtpServer` chave para um valor padrão personalizado de **Server123** .

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a>Definir valores padrão para vários parâmetros

Para definir valores padrão para vários parâmetros, separe cada par de **chave/valor** com um ponto e vírgula ( `;` ). As `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` chaves e são definidas como valores padrão personalizados.

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a>Usar curingas e parâmetros de comutador

Os nomes de cmdlet e parâmetro podem conter caracteres curinga. Use `$True` e `$False` para definir valores para parâmetros de comutador, como **detalhado** . O parâmetro **Verbose** do parâmetro comum é definido como `$True` para todos os comandos.

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a>Usar uma matriz para o valor padrão

Se um parâmetro puder aceitar vários valores, uma matriz, você poderá definir vários valores como os valores padrão. O valor padrão da `Invoke-Command:ComputerName` chave é definido como um valor de matriz de **Server01** e **Server02** .

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a>Usar um bloco de script

Você pode usar um bloco de script para especificar valores padrão diferentes para um parâmetro sob condições diferentes. O PowerShell avalia o bloco de script e usa o resultado como o valor do parâmetro padrão.

Os `Format-Table:AutoSize` conjuntos de chaves que alternam o parâmetro para um valor padrão de **true** . A `If` instrução contém uma condição que `$host.Name` deve ser o console do PowerShell, **ConsoleHost** .

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

Se um parâmetro aceitar um valor de bloco de script, coloque o bloco de script em um conjunto extra de chaves. Quando o PowerShell avalia o bloco de script externo, o resultado é o bloco de script interno e é definido como o valor de parâmetro padrão.

A `Invoke-Command:ScriptBlock` chave é definida como um valor padrão do **log de eventos do sistema** porque o bloco de script está incluído em um segundo conjunto de chaves. O resultado do bloco de script é passado para o `Invoke-Command` cmdlet.

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a>Como obter \$ PSDefaultParameterValues

Os valores da tabela de hash são exibidos digitando `$PSDefaultParameterValues` no prompt do PowerShell.

Uma `$PSDefaultParameterValues` tabela de hash é definida com três pares de **chave/valor** .
Essa tabela de hash é usada nos exemplos a seguir que descrevem como adicionar, alterar e remover valores de `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

Para obter o valor de uma `CmdletName:ParameterName` chave específica, use a seguinte sintaxe:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

Por exemplo, para obter o valor da `Send-MailMessage:SmtpServer` chave.

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a>Como adicionar valores a \$ PSDefaultParameterValues

Para adicionar um valor a `$PSDefaultParameterValues` , use o método **Add** . A adição de um valor não afeta os valores existentes da tabela de hash.

Use uma vírgula ( `,` ) para separar a **chave** do **valor** . A sintaxe a seguir mostra como usar o método **Add** para `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

A tabela de hash criada no exemplo anterior é atualizada com um novo par de **chave/valor** . O método **Add** define a `Get-Process:Name` chave para o valor **PowerShell** .

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

A sintaxe a seguir realiza o mesmo resultado.

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada. A `Get-Process:Name` chave foi adicionada.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a>Como remover valores de \$ PSDefaultParameterValues

Para remover um valor de `$PSDefaultParameterValues` , use o método **Remove** de tabelas de hash. A remoção de um valor não afeta os valores existentes da tabela de hash.

A sintaxe a seguir mostra como usar o método **Remove** em `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

Neste exemplo, a tabela de hash criada no exemplo anterior é atualizada para remover um par de **chave/valor** . O método **Remove** remove a `Get-Process:Name` chave.

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada. A `Get-Process:Name` chave foi removida.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a>Como alterar valores em \$ PSDefaultParameterValues

As alterações em um valor específico não afetam os valores de tabela de hash existentes. Para alterar um par de **chave/valor** específico no `$PSDefaultParameterValues` , use a seguinte sintaxe:

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

Neste exemplo, a tabela de hash criada no exemplo anterior é atualizada para alterar um par de **chave/valor** . O comando a seguir altera a `Send-MailMessage:SmtpServer` chave para um novo valor de **ServerXYZ** .

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada. A `Send-MailMessage:SmtpServer` chave foi alterada para um novo valor.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a>Como desabilitar e reabilitar o \$ PSDefaultParameterValues

Você pode desabilitar e, em seguida, reabilitar temporariamente `$PSDefaultParameterValues` .
Desabilitar `$PSDefaultParameterValues` será útil se você estiver executando scripts que precisam de valores de parâmetro padrão diferentes.

Para desabilitar `$PSDefaultParameterValues` , adicione uma chave de `Disabled` com um valor de **true** . Os valores em `$PSDefaultParameterValues` são preservados, mas não são efetivos.

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

A sintaxe a seguir realiza o mesmo resultado.

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada com o valor para a `Disabled` chave.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

Para reabilitar `$PSDefaultParameterValues` , remova a chave **desabilitada** ou altere o valor da chave **desabilitada** para `$False` . O valor anterior de `$PSDefaultParameterValues` é efetivo novamente.

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

A sintaxe a seguir realiza o mesmo resultado.

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada. Quando o método **Remove** é usado, a `Disabled` chave é removida da saída.
Se a sintaxe alternativa foi usada para reabilitar `$PSDefaultParameterValues` , a `Disabled` chave será exibida como **false** .

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a>Confira também

[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Script_Blocks](about_Script_Blocks.md)
