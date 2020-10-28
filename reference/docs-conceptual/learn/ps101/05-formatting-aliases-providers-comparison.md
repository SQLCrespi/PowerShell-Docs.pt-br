---
title: Formatting, aliases, providers, comparison (Formatação, aliases, provedores, comparação)
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
description: Este capítulo apresenta os conceitos de formatação de saída, aliases de comando, provedores e operações de comparação.
ms.openlocfilehash: efe70d2d220f8451e781603b6000c3553dda910c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501602"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a>Capítulo 5 – Formatação, aliases, provedores, comparação

## <a name="requirements"></a>Requisitos

O módulo do SQL Server PowerShell é necessário para alguns dos exemplos mostrados neste capítulo. O módulo é instalado como parte do [SSMS (SQL Server Management Studio)][SMSS]. Ele também é usado nos capítulos seguintes. Baixe-o e instale-o no computador do ambiente de laboratório do Windows 10.

## <a name="format-right"></a>Formatação à direita

No Capítulo 4, você aprendeu a realizar a filtragem o máximo possível à esquerda. A regra para formatar manualmente a saída de um comando é semelhante àquela regra, exceto que precisa ocorrer o máximo possível à direita.

Os comandos de formato mais comuns são `Format-Table` e `Format-List`. `Format-Wide` e `Format-Custom` também podem ser usados, mas são menos comuns.

Conforme mencionado no Capítulo 3, um comando que retorna mais de quatro propriedades usa como padrão uma lista, a menos que a formatação personalizada seja usada.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```Output
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

Use o cmdlet `Format-Table` para substituir manualmente a formatação e mostrar a saída em uma tabela em vez de uma lista.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

A saída padrão para `Get-Service` é três propriedades em uma tabela.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Use o cmdlet `Format-List` para substituir a formatação padrão e retornar os resultados em uma lista.

```powershell
Get-Service -Name w32time | Format-List
```

```Output
Name                : w32time
DisplayName         : Windows Time
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
ServiceType         : Win32ShareProcess
```

Observe que apenas direcionar `Get-Service` para `Format-List` fez com que ele retornasse propriedades adicionais. Isso não ocorre com cada comando devido à maneira como a formatação desse comando específico é configurada nos bastidores.

A primeira coisa da qual você deve estar ciente em relação aos cmdlets de formato é que eles produzem objetos de formato diferentes dos objetos normais no PowerShell.

```powershell
Get-Service -Name w32time | Format-List | Get-Member
```

```Output
   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
autosizeInfo                            Property   Microsoft.PowerShell.Commands.Inter...
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
pageFooterEntry                         Property   Microsoft.PowerShell.Commands.Inter...
pageHeaderEntry                         Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEntryData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
formatEntryInfo                         Property   Microsoft.PowerShell.Commands.Inter...
outOfBand                               Property   bool outOfBand {get;set;}
writeStream                             Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
```

O que isso significa é que os comandos de formato não podem ser direcionados para a maioria dos outros comandos. Eles podem ser direcionados para alguns dos comandos `Out-*`, mas é só. É por isso que o ideal é realizar qualquer formatação bem no final da linha (formatação à direita).

## <a name="aliases"></a>Aliases

Um alias no PowerShell é um nome mais curto para um comando. O PowerShell inclui um conjunto de aliases internos, e você também pode definir aliases próprios.

O cmdlet `Get-Alias` é usado para localizar aliases. Se você já sabe o alias para um comando, o parâmetro **Name** é usado para determinar a qual comando o alias está associado.

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

Vários aliases podem ser especificados para o valor do parâmetro **Name** .

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

Com frequência, você verá o parâmetro **Name** omitido, pois ele é um parâmetro posicional.

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

Se você desejar localizar aliases para um comando, precisará usar o parâmetro **Definition** .

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

O parâmetro **Definition** não pode ser usado de maneira posicional e, portanto, precisa ser especificado.

Os aliases podem economizar alguns pressionamentos de teclas e são bons quando você está digitando comandos no console.
Eles não devem ser usados em scripts ou em qualquer código que você esteja salvando ou compartilhando com outras pessoas. Conforme mencionado anteriormente neste livro, o uso de cmdlets completos e nomes de parâmetro é autodocumentado e mais fácil de ser entendido.

Tenha cuidado ao criar aliases próprios, porque eles só existirão na sessão atual do PowerShell no computador.

## <a name="providers"></a>Provedores

Um provedor no PowerShell é uma interface que permite um sistema de arquivos, como o acesso a um armazenamento de dados. Há vários provedores internos no PowerShell.

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
Certificate          ShouldProcess                      {Cert}
WSMan                Credentials                        {WSMan}
```

Como você pode ver nos resultados anteriores, há provedores internos para o Registro, aliases, variáveis de ambiente, sistema de arquivos, funções, variáveis, certificados e WSMan.

As unidades reais que esses provedores usam para expor o armazenamento de dados podem ser determinadas com o cmdlet `Get-PSDrive`. O cmdlet `Get-PSDrive` exibe as unidades expostas pelos provedores e exibe as unidades lógicas do Windows, incluindo as unidades mapeadas para compartilhamentos de rede.

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
Alias                                  Alias
C                  14.41        112.10 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
WSMan                                  WSMan
```

Módulos de terceiros, como o módulo do Active Directory PowerShell e o módulo do SQL Server PowerShell, adicionam uma PSDrive e um provedor do PowerShell próprios.

Importe os módulos do Active Directory e do SQL Server PowerShell.

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

Verifique se outros provedores do PowerShell foram adicionados.

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
ActiveDirectory      Include, Exclude, Filter, Shoul... {AD}
SqlServer            Credentials                        {SQLSERVER}
```

Observe que, no conjunto de resultados anterior, agora existem dois novos provedores do PowerShell, um para o Active Directory e outro para o SQL Server.

Uma PSDrive para cada um desses módulos também foi adicionada.

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
AD                                     ActiveDire... //RootDSE/
Alias                                  Alias
C                  19.38        107.13 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
SQLSERVER                              SqlServer     SQLSERVER:\
Variable                               Variable
WSMan                                  WSMan
```

As PSDrives podem ser acessadas da mesma forma que um sistema de arquivos tradicional.

```powershell
Get-ChildItem -Path Cert:\LocalMachine\CA
```

```Output
   PSParentPath: Microsoft.PowerShell.Security\Certificate::LocalMachine\CA

Thumbprint                                Subject
----------                                -------
FEE449EE0E3965A5246F000E87FDE2A065FD89D4  CN=Root Agency
D559A586669B08F46A30A133F8A9ED3D038E2EA8  OU=www.verisign.com/CPS Incorporated LIABI...
109F1CAED645BB78B3EA2B94C0697C740733031C  CN=Microsoft Windows Hardware Compatibility,...
```

## <a name="comparison-operators"></a>Operadores de comparação

O PowerShell contém vários operadores de comparação que são usados para comparar valores ou localizar valores que correspondem a determinados padrões. A Tabela 5-1 contém uma lista de operadores de comparação do PowerShell.

|    Operador    |                          Definição                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | Igual a                                                     |
| `-ne`          | É diferente de                                                 |
| `-gt`          | Maior que                                                 |
| `-ge`          | Maior que ou igual a                                     |
| `-lt`          | Menor que                                                    |
| `-le`          | Menor que ou igual a                                        |
| `-Like`        | Corresponde à expressão usando o caractere curinga `*`                       |
| `-NotLike`     | Não corresponde à expressão usando o caractere curinga `*`              |
| `-Match`       | Corresponde à expressão regular especificada                     |
| `-NotMatch`    | Não corresponde à expressão regular especificada              |
| `-Contains`    | Determina se uma coleção contém um valor especificado        |
| `-NotContains` | Determina se uma coleção não contém um valor específico |
| `-In`          | Determina se um valor especificado está em uma coleção           |
| `-NotIn`       | Determina se um valor especificado não está em uma coleção       |
| `-Replace`     | Substitui o valor especificado                                 |

Todos os operadores listados na Tabela 5-1 não diferenciam maiúsculas de minúsculas. Coloque um `c` na frente do operador listado na Tabela 5-1 para fazer com que ele diferencie maiúsculas de minúsculas. Por exemplo, `-ceq` é a versão que diferencia maiúsculas de minúsculas do operador de comparação `-eq`.

"PowerShell" com o uso correto de maiúsculas é igual a "powershell" em minúsculas com o operador de comparação equals.

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

Ele não é igual ao uso da versão que diferencia maiúsculas de minúsculas do operador de comparação equals.

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

O operador de comparação não igual inverte a condição.

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

Maior que, maior que ou igual a, menor que e menor que ou igual a funcionam com valores numéricos ou cadeia de caracteres.

```powershell
5 -gt 5
```

```Output
False
```

O uso de maior que ou igual a em vez de maior que com o exemplo anterior retorna o **booliano** true, pois cinco é igual a cinco.

```powershell
5 -ge 5
```

```Output
True
```

Com base nos resultados dos dois exemplos anteriores, é provável que você adivinhe como funcionam menor que e menor que ou igual a.

```powershell
5 -lt 10
```

```Output
True
```

Os operadores `-Like` e `-Match` podem ser confusos, mesmo para usuários experientes do PowerShell. `-Like` é usado com os caracteres curinga `*` e `?` para fazer correspondências "semelhantes".

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

`-Match` usa uma expressão regular para fazer a correspondência.

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

Use o operador de intervalo para armazenar os números 1 a 10 em uma variável.

```powershell
$Numbers = 1..10
```

```Output
```

Determine se a variável `$Numbers` inclui o 15.

```powershell
$Numbers -contains 15
```

```Output
False
```

Determine se ele inclui o número 10.

```powershell
$Numbers -contains 10
```

```Output
True
```

`-NotContains` inverte a lógica para ver se a variável `$Numbers` não contém um valor.

```powershell
$Numbers -notcontains 15
```

```Output
True
```

O exemplo anterior retorna o **booliano** true, porque é verdade que a variável `$Numbers` não contém o 15. No entanto, ela contém o número 10 e, portanto, é falsa quando é testada.

```powershell
$Numbers -notcontains 10
```

```Output
False
```

O operador de comparação "in" foi apresentado pela primeira vez no PowerShell versão 3.0. Ele é usado para determinar se um valor está "em" uma matriz. A variável `$Numbers` é uma matriz, pois contém vários valores.

```powershell
15 -in $Numbers
```

```Output
False
```

Em outras palavras, `-in` executa o mesmo teste que o operador de comparação contains, exceto que isso é feito na direção oposta.

```powershell
10 -in $Numbers
```

```Output
True
```

O 15 não está na matriz `$Numbers` e, portanto, false é retornado no exemplo a seguir.

```powershell
15 -in $Numbers
```

```Output
False
```

Assim como o operador `-contains`, `not` reverte a lógica para o operador `-in`.

```powershell
10 -notin $Numbers
```

```Output
False
```

O exemplo anterior retorna false, porque a matriz `$Numbers` inclui o 10 e a condição estava sendo testada para determinar se ela não continha o 10.

O 15 "não está na" matriz `$Numbers` e, portanto, retorna o **booliano** true.

```powershell
15 -notin $Numbers
```

```Output
True
```

O operador `-replace` faz exatamente o que você pensa. Ele é usado para substituir algo. A especificação de um valor substitui esse valor por nada. No exemplo a seguir, substituo "Shell" por nada.

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

Se você quiser substituir um valor por outro valor, especifique o novo valor após o padrão que deseja substituir. O SQL Saturday em Baton Rouge é um evento do qual tento participar todos os anos. No exemplo a seguir, substituo a palavra "Saturday" pela abreviação "Sat".

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

Também há métodos como **Replace()** que podem ser usados para substituir itens semelhantes ao modo como o operador replace funciona. No entanto, o operador `-Replace` não diferencia maiúsculas de minúsculas por padrão, ao contrário do método **Replace()** .

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

Observe que a palavra "Saturday" não foi substituída no exemplo anterior. Isso ocorre porque ela foi especificada com maiúsculas e minúsculas diferentes do original. Quando a palavra "Saturday" é especificada com maiúsculas e minúsculas iguais às do original, o método **Replace()** a substitui como esperado.

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

Tenha cuidado ao usar métodos para transformar dados, porque você pode se deparar com problemas imprevistos, como a reprovação no _Teste da Turquia_ . Para obter um exemplo, confira o artigo de blog intitulado [Como usar o Pester para testar o código do PowerShell com outras culturas][]. Minha recomendação é usar um operador em vez de um método sempre que possível para evitar esses tipos de problemas.

Embora os operadores de comparação possam ser usados conforme mostrado nos exemplos anteriores, normalmente, uso esses operadores com o cmdlet `Where-Object` para realizar algum tipo de filtragem.

## <a name="summary"></a>Resumo

Neste capítulo, você conheceu vários tópicos diferentes, incluindo formatação à direta, aliases, provedores e operadores de comparação.

## <a name="review"></a>Revisão

1. Por que é necessário realizar a formatação o máximo possível à direita?
1. Como determinar qual é o cmdlet real para o alias `%`?
1. Por que você não deve usar aliases em scripts salvos ou em códigos que compartilha com outras pessoas?
1. Faça uma listagem de diretórios nas unidades que estão associados a um dos provedores de Registro.
1. Qual é um dos principais benefícios do uso do operador replace em vez do método replace?

## <a name="recommended-reading"></a>Leitura recomendada

- [Format-Table][]
- [Format-List][]
- [Format-Wide][]
- [about_Aliases][]
- [about_Providers][]
- [about_Comparison_Operators][]
- [about_Arrays][]

<!-- link references -->
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
[Format-Table]: /powershell/module/microsoft.powershell.utility/format-table
[Format-List]: /powershell/module/microsoft.powershell.utility/format-list
[Format-Wide]: /powershell/module/microsoft.powershell.utility/format-wide
[about_Aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[about_Providers]: /powershell/module/microsoft.powershell.core/about/about_providers
[about_Comparison_Operators]: /powershell/module/microsoft.powershell.core/about/about_comparison_operators
[about_Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Como usar o Pester para testar o código do PowerShell com outras culturas]: https://mikefrobbins.com/2015/10/22/using-pester-to-test-powershell-code-with-other-cultures/
