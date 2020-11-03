---
description: Descreve a linguagem WQL, que pode ser usada para obter objetos WMI no Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196131"
---
# <a name="about-wql"></a>Sobre o WQL

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve a linguagem WQL, que pode ser usada para obter objetos WMI no Windows PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

WQL é a linguagem de consulta Instrumentação de Gerenciamento do Windows (WMI), que é a linguagem usada para obter informações do WMI.

Não é necessário usar o WQL para executar uma consulta WMI no Windows PowerShell.
Em vez disso, você pode usar os parâmetros dos cmdlets Get-WmiObject ou Get-CimInstance. As consultas WQL são um pouco mais rápidas do que os comandos de Get-WmiObject padrão e o desempenho aprimorado é evidente quando os comandos são executados em centenas de sistemas. No entanto, certifique-se de que o tempo gasto para escrever uma consulta WQL bem-sucedida não supere a melhoria do desempenho.

As instruções WQL básicas que você precisa usar WQL são selecionar, onde e de.

## <a name="when-to-use-wql"></a>QUANDO USAR WQL

Ao trabalhar com o WMI e, especialmente com a WQL, não se esqueça de que você também está usando o Windows PowerShell. Geralmente, se uma consulta WQL não funcionar conforme o esperado, será mais fácil usar um comando padrão do Windows PowerShell do que Depurar a consulta WQL.

A menos que você esteja retornando grandes quantidades de dados de sistemas remotos com largura de banda restrita, raramente é produtivo gastar horas tentando aperfeiçoar uma consulta WQL complicada e complicadas quando há um cmdlet do Windows perfeitamente aceitável que faz a mesma coisa, se for um pouco mais lento.

## <a name="using-the-select-statement"></a>USANDO A INSTRUÇÃO SELECT

Uma consulta WMI típica começa com uma instrução SELECT que obtém todas as propriedades ou propriedades específicas de uma classe WMI. Para selecionar todas as propriedades de uma classe WMI, use um asterisco ( \* ). A palavra-chave from especifica a classe WMI.

Uma instrução SELECT tem o seguinte formato:

```
Select <property> from <WMI-class>
```

Por exemplo, a instrução SELECT a seguir seleciona todas as propriedades (*) das instâncias da classe WMI Win32_Bios.

```
Select * from Win32_Bios
```

Para selecionar uma propriedade específica de uma classe WMI, coloque o nome da propriedade entre as palavras-chave SELECT e from.

A consulta a seguir seleciona apenas o nome do BIOS da classe Win32_Bios WMI. O comando salva a consulta na variável $queryName.

```
Select Name from Win32_Bios
```

Para selecionar mais de uma propriedade, use vírgulas para separar os nomes de propriedade.
A consulta WMI a seguir seleciona o nome e a versão da classe Win32_Bios WMI. O comando salva a consulta na variável $queryNameVersion.

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a>USANDO A CONSULTA WQL

Há três maneiras de usar a consulta WQL no comando do Windows PowerShell.

- Usar o cmdlet Get-WmiObject
- Usar o cmdlet Get-CimInstance
- Use o acelerador de tipo [WMISEARCHER].

## <a name="using-the-get-wmiobject-cmdlet"></a>USANDO O CMDLET GET-WMIOBJECT

A maneira mais básica de usar a consulta WQL é colocá-la entre aspas (como uma cadeia de caracteres) e, em seguida, usar a cadeia de caracteres de consulta como o valor do parâmetro de consulta do cmdlet Get-WmiObject, conforme mostrado no exemplo a seguir.

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Você também pode salvar a instrução WQL em uma variável e, em seguida, usar a variável como o valor do parâmetro de consulta, conforme mostrado no comando a seguir.

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

Você pode usar qualquer um dos formatos com qualquer instrução WQL. O comando a seguir usa a consulta na variável $queryName para obter apenas as propriedades Name e Version do BIOS do sistema.

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

Lembre-se de que você pode usar os parâmetros do cmdlet Get-WmiObject para obter o mesmo resultado. Por exemplo, o comando a seguir também obtém os valores das propriedades Name e Version de instâncias da classe WMI Win32_Bios.

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a>USANDO O CMDLET GET-CIMINSTANCE

A partir do Windows PowerShell 3,0, você pode usar o cmdlet Get-CimInstance para executar consultas WQL.

Get-CimInstance Obtém instâncias de classes compatíveis com CIM, incluindo classes WMI. Os cmdlets do CIM, introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI. Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM), que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores Windows e computadores que executam outros sistemas operacionais.

O comando a seguir usa o cmdlet Get-CimInstance para executar uma consulta WQL.

Qualquer consulta WQL que possa ser usada com Get-WmiObject também pode ser usada com Get-CimInstance.

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Get-CimInstance retorna um objeto CimInstance, em vez de ManagementObject que Get-WmiObject retorna, mas os objetos são bastante semelhantes.

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a>USANDO o ACELERAdor de tipo [WMISEARCHER]

O acelerador de tipo [WMISEARCHER] cria um objeto ManagementObjectSearcher a partir de uma cadeia de caracteres de instrução WQL. O objeto ManagementObjectSearcher tem muitas propriedades e métodos, mas o método mais básico é o método Get, que invoca a consulta WMI especificada e retorna os objetos resultantes.

Usando o [WMISEARCHER], você obterá acesso fácil à classe de .NET Framework do ManagementObjectSearcher. Isso permite consultar o WMI e configurar a maneira como a consulta é realizada.

Para usar o acelerador de tipo [WMISEARCHER]:

1. Converta a cadeia de caracteres WQL em um objeto ManagementObjectSearcher.
2. Chame o método Get do objeto ManagementObjectSearcher.

Por exemplo, o comando a seguir converte a consulta "selecionar tudo", salva o resultado na variável $bios e, em seguida, chama o método Get do objeto ManagementObjectSearcher na variável $bios.

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Observação: somente as propriedades de objeto selecionadas são exibidas por padrão. Essas propriedades são definidas no arquivo XML Types.ps1.

Você pode usar o acelerador de tipo [WMISEARCHER] para converter a consulta ou a variável. No exemplo a seguir, o acelerador de tipo [WMISEARCHER] é usado para converter a variável. O resultado é o mesmo.

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Quando você usa o acelerador de tipo [WMISEARCHER], ele altera a cadeia de caracteres de consulta em um objeto ManagementObjectSearcher, conforme mostrado nos comandos a seguir.

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

Esse formato de comando funciona em qualquer consulta. O comando a seguir obtém o valor da propriedade Name da classe WMI Win32_Bios.

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

Você pode executar essa operação em um único comando, embora o comando seja um pouco mais difícil de interpretar.

Nesse formato, você usa o acelerador de tipo [WMISEARCHER] para converter a cadeia de caracteres de consulta WQL em um ManagementObjectSearcher e, em seguida, chamar o método Get no objeto, tudo em um único comando. Os parênteses () que envolvem a cadeia de caracteres convertida direcionam o Windows PowerShell para converter a cadeia de caracteres antes de chamar o método.

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a>USANDO A INSTRUÇÃO WHERE BÁSICA DO WQL

Uma instrução WHERE estabelece condições para os dados retornados por uma instrução SELECT.

A instrução WHERE tem o seguinte formato:

```
where <property> <operator> <value>
```

Por exemplo:

```
where Name = 'Notepad.exe'
```

A instrução WHERE é usada com a instrução SELECT, conforme mostrado no exemplo a seguir.

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

Ao usar a instrução WHERE, o nome da propriedade e o valor devem ser precisos.

Por exemplo, o comando a seguir obtém os processos do bloco de notas no computador local.

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

No entanto, o comando a seguir falhará, porque o nome do processo inclui a extensão de nome de arquivo ". exe".

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a>OPERADORES DE COMPARAÇÃO DE INSTRUÇÕES WHERE

Os operadores a seguir são válidos em uma instrução WHERE do WQL.

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

Há outros operadores, mas são aqueles usados para fazer comparações.

Por exemplo, a consulta a seguir seleciona o nome e as propriedades de prioridade dos processos na classe Win32_Process em que a prioridade do processo é maior ou igual a 11. O cmdlet Get-WmiObject executa a consulta.

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a>USANDO OS OPERADORES WQL NO PARÂMETRO FILTER

Os operadores WQL também podem ser usados no valor do parâmetro de filtro dos cmdlets Get-WmiObject ou Get-CimInstance, bem como no valor dos parâmetros de consulta desses cmdlets.

Por exemplo, o comando a seguir obtém as propriedades Name e ProcessID dos últimos cinco processos que têm valores de ProcessID maiores que 1004. O comando usa o parâmetro Filter para especificar a condição ProcessID.

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a>USANDO O OPERADOR LIKE

O operador Like permite que você use caracteres curinga para filtrar os resultados de uma consulta WQL.

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

Quando o operador Like é usado sem nenhum caractere curinga ou operador de intervalo, ele se comporta como o operador de igualdade (=) e retorna objetos somente quando eles são uma correspondência exata para o padrão.

Você pode combinar a operação de intervalo com o caractere curinga percentual para criar filtros simples, mas poderosos.

### <a name="like-operator-examples"></a>EXEMPLOS DE OPERADOR LIKE

#### <a name="example-1-range"></a>EXEMPLO 1: [ \<range> ]

Os comandos a seguir iniciam o bloco de notas e, em seguida, pesquisam uma instância da classe Win32_Process que tem um nome que começa com uma letra entre "H" e "N" (não diferencia maiúsculas de minúsculas).

A consulta deve retornar qualquer processo de Hotpad.exe por meio de Notepad.exe.

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a>EXEMPLO 2: [ \<range> ] e%

Os comandos a seguir selecionam todos os processos que têm um nome que começa com uma letra entre A e P (não diferencia maiúsculas de minúsculas) seguidos por zero ou mais letras em qualquer combinação.

O cmdlet Get-WmiObject executa a consulta, o cmdlet Select-Object Obtém as propriedades Name e ProcessID, e o cmdlet Sort-Object classifica os resultados em ordem alfabética por nome.

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a>EXEMPLO 3: não está no intervalo (^)

O comando a seguir obtém os processos cujos nomes não começam com nenhuma das seguintes letras: A, S, W, P, R, C, U, N

e seguido zero ou mais letras.

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a>EXEMPLO 4: quaisquer caracteres-ou nenhum (%)

Os comandos a seguir obtêm processos que têm nomes que começam com "Calc".
O símbolo% em WQL é equivalente ao símbolo de asterisco ( \* ) em expressões regulares.

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a>EXEMPLO 5: um caractere (_)

Os comandos a seguir obtêm processos com nomes que têm o seguinte padrão, "c_lc.exe", em que o caractere de sublinhado representa um caractere. Esse padrão corresponde a qualquer nome de calc.exe por meio de czlc.exe, ou c9lc.exe, mas não corresponde a nomes nos quais "c" e "l" são separados por mais de um caractere.

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a>EXEMPLO 6: correspondência exata

Os comandos a seguir obtêm processos chamados WLIDSVC.exe. Embora a consulta use a palavra-chave like, ela requer uma correspondência exata, pois o valor não inclui nenhum caractere curinga.

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a>USANDO O OPERADOR OR

Para especificar várias condições independentes, use a palavra-chave ou. A palavra-chave ou é exibida na cláusula WHERE. Ele executa uma operação inclusiva ou em duas (ou mais) condições e retorna itens que atendem a qualquer uma das condições.

O operador or tem o seguinte formato:

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

Por exemplo, os comandos a seguir obtêm todas as instâncias da classe Win32_Process WMI, mas as retornarão somente se o nome do processo for winword.exe ou excel.exe.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

A instrução or pode ser usada com mais de duas condições. Na consulta a seguir, a instrução or Obtém Winword.exe, Excel.exe ou Powershell.exe.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a>USANDO O OPERADOR AND

Para especificar várias condições relacionadas, use a palavra-chave and. A palavra-chave and é exibida na cláusula WHERE. Ele retorna os itens que atendem a todas as condições.

O operador and tem o seguinte formato:

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

Por exemplo, os comandos a seguir obtêm processos que têm um nome de "Winword.exe" e a ID de processo de 6512.

Observe que os comandos usam o cmdlet Get-CimInstance.

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

Todos os operadores, incluindo os operadores like, são válidos com os operadores or e e. Além disso, você pode combinar os operadores or e and em uma única consulta com parênteses que informam ao Windows PowerShell quais cláusulas processar primeiro.

Esse comando usa o caractere de continuação do Windows PowerShell (') dividir o comando em duas linhas.

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a>PESQUISANDO VALORES NULOS

Pesquisar valores nulos no WMI é desafiador, pois pode levar a resultados imprevisíveis. NULL não é zero e não é equivalente ou a uma cadeia de caracteres vazia. Algumas propriedades de classe WMI são inicializadas e outras não, portanto, uma pesquisa por NULL pode não funcionar para todas as propriedades.

Para pesquisar valores nulos, use o operador is com um valor de "NULL".

Por exemplo, os comandos a seguir obtêm processos que têm um valor nulo para a propriedade IntallDate. Os comandos retornam muitos processos.

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

Por outro lado, o comando a seguir obtém as contas de usuário que têm um valor nulo para a propriedade Description. Esse comando não retorna nenhuma conta de usuário, embora a maioria das contas de usuário não tenha nenhum valor para a propriedade Description.

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

Para localizar as contas de usuário que não têm valor para a propriedade Description, use o operador de igualdade para obter uma cadeia de caracteres vazia. Para representar a cadeia de caracteres vazia, use duas aspas simples consecutivas.

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a>USANDO TRUE OU FALSE

Para obter valores Boolianos nas propriedades de objetos WMI, use true e false.
Eles não diferenciam maiúsculas de minúsculas.

A consulta WQL a seguir retorna apenas contas de usuário local de um computador ingressado no domínio.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

Para localizar contas de domínio, use um valor de false, conforme mostrado no exemplo a seguir.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a>USANDO O CARACTERE DE ESCAPE

O WQL usa a barra invertida ( \) como seu caractere de escape. Isso é diferente do Windows PowerShell, que usa o caractere de acento grave (').

As aspas e os caracteres usados para aspas, geralmente precisam ser precedidos para que não sejam interpretados erroneamente.

Para localizar um usuário cujo nome inclui uma aspa simples, use uma barra invertida para escapar a aspa simples, conforme mostrado no comando a seguir.

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

Em alguns casos, a barra invertida também precisa ter escape. Por exemplo, os comandos a seguir geram um erro de consulta inválido devido à barra invertida no valor da legenda.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

Para escapar a barra invertida, use um segundo caractere de barra invertida, conforme mostrado no comando a seguir.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Special_Characters](about_Special_Characters.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_WMI](about_WMI.md)

[about_WMI_Cmdlets](about_WMI_Cmdlets.md)
