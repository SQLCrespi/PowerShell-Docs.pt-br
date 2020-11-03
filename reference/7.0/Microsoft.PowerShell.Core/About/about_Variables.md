---
description: Descreve como as variáveis armazenam valores que podem ser usados no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 910d09d0606c10679df342092e8fbc3ecb068ecf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195878"
---
# <a name="about-variables"></a>Sobre variáveis

## <a name="short-description"></a>Descrição breve

Descreve como as variáveis armazenam valores que podem ser usados no PowerShell.

## <a name="long-description"></a>Descrição longa

Você pode armazenar todos os tipos de valores em variáveis do PowerShell. Por exemplo, armazene os resultados de comandos e armazene os elementos que são usados em comandos e expressões, como nomes, caminhos, configurações e valores.

Uma variável é uma unidade de memória na qual os valores são armazenados. No PowerShell, as variáveis são representadas por cadeias de caracteres de texto que começam com um cifrão ( `$` ), como `$a` , `$process` ou `$my_var` .

Nomes de variáveis não diferenciam maiúsculas de minúsculas e podem incluir espaços e caracteres especiais. Porém, os nomes de variáveis que incluem caracteres especiais e espaços são difíceis de usar e devem ser evitados. Para obter mais informações, consulte [nomes de variáveis que incluem caracteres especiais](#variable-names-that-include-special-characters).

Há vários tipos diferentes de variáveis no PowerShell.

- Variáveis criadas pelo usuário: as variáveis criadas pelo usuário são criadas e mantidas pelo usuário. Por padrão, as variáveis que você cria na linha de comando do PowerShell existem somente enquanto a janela do PowerShell está aberta. Quando as janelas do PowerShell são fechadas, as variáveis são excluídas. Para salvar uma variável, adicione-a ao seu perfil do PowerShell. Você também pode criar variáveis em scripts com escopo global, de script ou local.

- Variáveis automáticas: as variáveis automáticas armazenam o estado do PowerShell. Essas variáveis são criadas pelo PowerShell e o PowerShell altera seus valores conforme necessário para manter sua precisão. Os usuários não podem alterar o valor dessas variáveis. Por exemplo, a `$PSHOME` variável armazena o caminho para o diretório de instalação do PowerShell.

  Para obter mais informações, uma lista e uma descrição das variáveis automáticas, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

- Variáveis de preferência: variáveis de preferência armazenam preferências do usuário para o PowerShell. Essas variáveis são criadas pelo PowerShell e preenchidas com valores padrão. Os usuários podem alterar os valores dessas variáveis. Por exemplo, a `$MaximumHistoryCount` variável determina o número máximo de entradas no histórico de sessão.

  Para obter mais informações, uma lista e uma descrição das variáveis de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).

## <a name="working-with-variables"></a>Trabalhando com variáveis

Para criar uma nova variável, use uma instrução de atribuição para atribuir um valor à variável. Você não precisa declarar a variável antes de usá-la. O valor padrão de todas as variáveis é `$null` .

Para obter uma lista de todas as variáveis em sua sessão do PowerShell, digite `Get-Variable` . Os nomes de variáveis são exibidos sem o sinal de dólar ( `$` ) precedente que é usado para referenciar variáveis.

Por exemplo:

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

As variáveis são úteis para armazenar os resultados dos comandos.

Por exemplo:

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

Para exibir o valor de uma variável, digite o nome da variável, precedido por um cifrão ( `$` ).

Por exemplo:

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

Para alterar o valor de uma variável, atribua um novo valor à variável.

Os exemplos a seguir exibem o valor da `$MyVariable` variável, altera o valor da variável e, em seguida, exibe o novo valor.

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

Para excluir o valor de uma variável, use o `Clear-Variable` cmdlet ou altere o valor para `$null` .

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

Para excluir a variável, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) ou [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a>Tipos de variáveis

Você pode armazenar qualquer tipo de objeto em uma variável, incluindo inteiros, cadeias de caracteres, matrizes e tabelas de hash. E os objetos que representam processos, serviços, logs de eventos e computadores.

As variáveis do PowerShell são tipificadas de forma flexível, o que significa que elas não são limitadas a um tipo específico de objeto. Uma única variável pode até mesmo conter uma coleção, ou matriz, de diferentes tipos de objetos ao mesmo tempo.

O tipo de dados de uma variável é determinado pelos tipos .NET dos valores da variável. Para exibir o tipo de objeto de uma variável, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).

Por exemplo:

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

Você pode usar um atributo de tipo e uma notação de conversão para garantir que uma variável só possa conter tipos de objeto ou objetos específicos que possam ser convertidos nesse tipo. Se você tentar atribuir um valor de outro tipo, o PowerShell tentará converter o valor em seu tipo. Se o tipo não puder ser convertido, a instrução de atribuição falhará.

Para usar notação de conversão, insira um nome de tipo, entre colchetes, antes do nome da variável (no lado esquerdo da instrução de atribuição). O exemplo a seguir cria uma `$number` variável que pode conter apenas inteiros, uma `$words` variável que pode conter apenas cadeias de caracteres e uma `$dates` variável que pode conter somente objetos **DateTime** .

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a>Usando variáveis em comandos e expressões

Para usar uma variável em um comando ou expressão, digite o nome da variável, precedido pelo sinal de dólar ( `$` ).

Se o nome da variável e o sinal de dólar não estiverem entre aspas, ou se estiverem dentro das marcas de aspas duplas `"` , o valor da variável será usado no comando ou na expressão.

Se o nome da variável e o cifrão estiverem entre aspas simples ( `'` ), o nome da variável será usado na expressão.

Para obter mais informações sobre como usar aspas no PowerShell, consulte [about_Quoting_Rules](about_Quoting_Rules.md).

Este exemplo obtém o valor da `$PROFILE` variável, que é o caminho para o arquivo de perfil de usuário do PowerShell no console do PowerShell.

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

Neste exemplo, são mostrados dois comandos que podem abrir o perfil do PowerShell no **notepad.exe** . O exemplo com marcas de aspas duplas ( `"` ) usa o valor da variável.

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

Os exemplos a seguir usam marcas de aspas simples ( `'` ) que tratam a variável como texto literal.

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a>Nomes de variáveis que incluem caracteres especiais

Os nomes de variáveis começam com um sinal de dólar ( `$` ) e podem incluir caracteres alfanuméricos e caracteres especiais. O comprimento do nome da variável é limitado apenas pela memória disponível.

A prática recomendada é que os nomes de variáveis incluam apenas caracteres alfanuméricos e o caractere sublinhado ( `_` ). Nomes de variáveis que incluem espaços e outros caracteres especiais são difíceis de usar e devem ser evitados.

Os nomes de variáveis alfanuméricas podem conter estes caracteres:

- Caracteres Unicode destas categorias: **Lu** , **ll** , **lt** , **LM** , **lo** ou **ND** .
- Caractere de sublinhado ( `_` ).
- Caractere de ponto de interrogação ( `?` ).

A lista a seguir contém as descrições de categoria Unicode. Para obter mais informações, consulte [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).

- **Lu** -UppercaseLetter
- **Ll** -LowercaseLetter
- **Lt** -TitlecaseLetter
- **LM** -ModifierLetter
- **Lo** OtherLetter
- **ND** -DecimalDigitNumber

Para criar ou exibir um nome de variável que inclua espaços ou caracteres especiais, coloque o nome da variável com os caracteres de chaves ( `{}` ).
As chaves direcionam o PowerShell para interpretar os caracteres do nome da variável como literais.

Os nomes de variável de caracteres especiais podem conter estes caracteres:

- Qualquer caractere Unicode, com as seguintes exceções:
  - O caractere de fechamento de chave ( `}` ) (U + 007D).
  - O caractere de acento grave ( `` ` `` ) (U + 0060). A marca de fim é usada para escapar caracteres Unicode para que sejam tratados como literais.

O PowerShell tem variáveis reservadas, como,, `$$` `$?` `$^` e `$_` que contêm caracteres alfanuméricos e especiais. Para obter mais informações, consulte [about_Automatic_Variables](about_automatic_variables.md).

Por exemplo, o comando a seguir cria a variável chamada `save-items` . As chaves ( `{}` ) são necessárias porque o nome da variável inclui um `-` caractere especial hífen ().

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

O comando a seguir obtém os itens filho no diretório que é representado pela `ProgramFiles(x86)` variável de ambiente.

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

Para fazer referência a um nome de variável que inclui chaves, coloque o nome da variável entre chaves e use o caractere de acento grave para escapar das chaves. Por exemplo, para criar um tipo nomeado de variável `this{value}is` :

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a>Variáveis e escopo

Por padrão, as variáveis só estão disponíveis no escopo em que são criadas.

Por exemplo, uma variável que você cria em uma função está disponível somente dentro da função. Uma variável que você cria em um script está disponível somente dentro do script. Se você criar um ponto-fonte do script, a variável será adicionada ao escopo atual. Para obter mais informações, consulte [about_Scopes](about_Scopes.md).

Você pode usar um modificador de escopo para alterar o escopo padrão da variável. A expressão a seguir cria uma variável chamada `Computers` . A variável tem um escopo global, mesmo quando ela é criada em um script ou uma função.

```powershell
$Global:Computers = "Server01"
```

Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los.

Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).

## <a name="saving-variables"></a>Salvando variáveis

As variáveis que você cria estão disponíveis somente na sessão em que você as cria. Eles são perdidos quando você fecha sua sessão.

Para criar a variável em cada sessão do PowerShell que você iniciar, adicione a variável ao seu perfil do PowerShell.

Por exemplo, para alterar o valor da `$VerbosePreference` variável em cada sessão do PowerShell, adicione o seguinte comando ao seu perfil do PowerShell.

```powershell
$VerbosePreference = "Continue"
```

Você pode adicionar esse comando ao seu perfil do PowerShell abrindo o `$PROFILE` arquivo em um editor de texto, como **notepad.exe** . Para obter mais informações sobre perfis do PowerShell, consulte [about_Profiles](about_Profiles.md).

## <a name="the-variable-drive"></a>A unidade Variable:

O provedor de variáveis do PowerShell cria uma `Variable:` unidade que parece e age como uma unidade do sistema de arquivos, mas contém as variáveis em sua sessão e seus valores.

Para alterar para a `Variable:` unidade, use o seguinte comando:

```powershell
Set-Location Variable:
```

Para listar os itens e variáveis na `Variable:` unidade, use os `Get-Item` `Get-ChildItem` cmdlets ou.

```powershell
Get-ChildItem Variable:
```

Para obter o valor de uma variável específica, use a notação do sistema de arquivos para especificar o nome da unidade e o nome da variável. Por exemplo, para obter a `$PSCulture` variável automática, use o comando a seguir.

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

Para exibir mais informações sobre a `Variable:` unidade e o provedor de variáveis do PowerShell, digite:

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a>Sintaxe de variável com caminhos de provedor

Você pode prefixar um caminho de provedor com o sinal de dólar ( `$` ) e acessar o conteúdo de qualquer provedor que implemente a interface [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) .

Os seguintes provedores internos do PowerShell dão suporte a esta notação:

- [about_Environment_Provider](about_Environment_Provider.md)
- [about_Variable_Provider](about_Variable_Provider.md)
- [about_Function_Provider](about_Function_Provider.md)
- [about_Alias_Provider](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a>Os cmdlets variáveis

O PowerShell inclui um conjunto de cmdlets que são projetados para gerenciar variáveis.

Para listar os cmdlets, digite:

```powershell
Get-Command -Noun Variable
```

Para obter ajuda para um cmdlet específico, digite:

```powershell
Get-Help <cmdlet-name>
```

| Nome do Cmdlet       | Descrição                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | Excluir o valor de uma variável.           |
| `Get-Variable`    | Obtém as variáveis no console atual. |
| `New-Variable`    | Cria uma nova variável.                    |
| `Remove-Variable` | Exclui uma variável e seu valor.          |
| `Set-Variable`    | Altera o valor de uma variável.           |

## <a name="see-also"></a>Confira também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Scopes](about_Scopes.md)

[about_Remote_Variables](about_Remote_Variables.md)
