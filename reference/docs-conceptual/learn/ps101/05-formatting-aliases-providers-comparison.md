---
title: Formatting, aliases, providers, comparison (Formatação, aliases, provedores, comparação)
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: eb23b048a50f10ea83d156c0499772b1be439336
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437997"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a><span data-ttu-id="e63cb-102">Capítulo 5 – Formatação, aliases, provedores, comparação</span><span class="sxs-lookup"><span data-stu-id="e63cb-102">Chapter 5 - Formatting, aliases, providers, comparison</span></span>

## <a name="requirements"></a><span data-ttu-id="e63cb-103">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e63cb-103">Requirements</span></span>

<span data-ttu-id="e63cb-104">O módulo do SQL Server PowerShell é necessário para alguns dos exemplos mostrados neste capítulo.</span><span class="sxs-lookup"><span data-stu-id="e63cb-104">The SQL Server PowerShell module is required by some of the examples shown in this chapter.</span></span> <span data-ttu-id="e63cb-105">O módulo é instalado como parte do [SSMS (SQL Server Management Studio)][SMSS].</span><span class="sxs-lookup"><span data-stu-id="e63cb-105">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="e63cb-106">Ele também é usado nos capítulos seguintes.</span><span class="sxs-lookup"><span data-stu-id="e63cb-106">It's also used in subsequent chapters.</span></span> <span data-ttu-id="e63cb-107">Baixe-o e instale-o no computador do ambiente de laboratório do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e63cb-107">Download and install it on your Windows 10 lab environment computer.</span></span>

## <a name="format-right"></a><span data-ttu-id="e63cb-108">Formatação à direita</span><span class="sxs-lookup"><span data-stu-id="e63cb-108">Format Right</span></span>

<span data-ttu-id="e63cb-109">No Capítulo 4, você aprendeu a realizar a filtragem o máximo possível à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e63cb-109">In Chapter 4, you learned to filter as far to the left as possible.</span></span> <span data-ttu-id="e63cb-110">A regra para formatar manualmente a saída de um comando é semelhante àquela regra, exceto que precisa ocorrer o máximo possível à direita.</span><span class="sxs-lookup"><span data-stu-id="e63cb-110">The rule for manually formatting a command's output is similar to that rule except it needs to occur as far to the right as possible.</span></span>

<span data-ttu-id="e63cb-111">Os comandos de formato mais comuns são `Format-Table` e `Format-List`.</span><span class="sxs-lookup"><span data-stu-id="e63cb-111">The most common format commands are `Format-Table` and `Format-List`.</span></span> <span data-ttu-id="e63cb-112">`Format-Wide` e `Format-Custom` também podem ser usados, mas são menos comuns.</span><span class="sxs-lookup"><span data-stu-id="e63cb-112">`Format-Wide` and `Format-Custom` can also be used, but are less common.</span></span>

<span data-ttu-id="e63cb-113">Conforme mencionado no Capítulo 3, um comando que retorna mais de quatro propriedades usa como padrão uma lista, a menos que a formatação personalizada seja usada.</span><span class="sxs-lookup"><span data-stu-id="e63cb-113">As mentioned in Chapter 3, a command that returns more than four properties defaults to a list unless custom formatting is used.</span></span>

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

<span data-ttu-id="e63cb-114">Use o cmdlet `Format-Table` para substituir manualmente a formatação e mostrar a saída em uma tabela em vez de uma lista.</span><span class="sxs-lookup"><span data-stu-id="e63cb-114">Use the `Format-Table` cmdlet to manually override the formatting and show the output in a table instead of a list.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

<span data-ttu-id="e63cb-115">A saída padrão para `Get-Service` é três propriedades em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="e63cb-115">The default output for `Get-Service` is three properties in a table.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="e63cb-116">Use o cmdlet `Format-List` para substituir a formatação padrão e retornar os resultados em uma lista.</span><span class="sxs-lookup"><span data-stu-id="e63cb-116">Use the `Format-List` cmdlet to override the default formatting and return the results in a list.</span></span>

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

<span data-ttu-id="e63cb-117">Observe que apenas direcionar `Get-Service` para `Format-List` fez com que ele retornasse propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="e63cb-117">Notice that simply piping `Get-Service` to `Format-List` made it return additional properties.</span></span> <span data-ttu-id="e63cb-118">Isso não ocorre com cada comando devido à maneira como a formatação desse comando específico é configurada nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="e63cb-118">This doesn't occur with every command because of the way the formatting for that particular command is set up behind the scenes.</span></span>

<span data-ttu-id="e63cb-119">A primeira coisa da qual você deve estar ciente em relação aos cmdlets de formato é que eles produzem objetos de formato diferentes dos objetos normais no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e63cb-119">The number one thing to be aware of with the format cmdlets is they produce format objects that are different than normal objects in PowerShell.</span></span>

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

<span data-ttu-id="e63cb-120">O que isso significa é que os comandos de formato não podem ser direcionados para a maioria dos outros comandos.</span><span class="sxs-lookup"><span data-stu-id="e63cb-120">What this means is format commands can't be piped to most other commands.</span></span> <span data-ttu-id="e63cb-121">Eles podem ser direcionados para alguns dos comandos `Out-*`, mas é só.</span><span class="sxs-lookup"><span data-stu-id="e63cb-121">They can be piped to some of the `Out-*` commands, but that's about it.</span></span> <span data-ttu-id="e63cb-122">É por isso que o ideal é realizar qualquer formatação bem no final da linha (formatação à direita).</span><span class="sxs-lookup"><span data-stu-id="e63cb-122">This is why you want to perform any formatting at the very end of the line (format right).</span></span>

## <a name="aliases"></a><span data-ttu-id="e63cb-123">Aliases</span><span class="sxs-lookup"><span data-stu-id="e63cb-123">Aliases</span></span>

<span data-ttu-id="e63cb-124">Um alias no PowerShell é um nome mais curto para um comando.</span><span class="sxs-lookup"><span data-stu-id="e63cb-124">An alias in PowerShell is a shorter name for a command.</span></span> <span data-ttu-id="e63cb-125">O PowerShell inclui um conjunto de aliases internos, e você também pode definir aliases próprios.</span><span class="sxs-lookup"><span data-stu-id="e63cb-125">PowerShell includes a set of built-in aliases and you can also define your own aliases.</span></span>

<span data-ttu-id="e63cb-126">O cmdlet `Get-Alias` é usado para localizar aliases.</span><span class="sxs-lookup"><span data-stu-id="e63cb-126">The `Get-Alias` cmdlet is used to find aliases.</span></span> <span data-ttu-id="e63cb-127">Se você já sabe o alias para um comando, o parâmetro **Name** é usado para determinar a qual comando o alias está associado.</span><span class="sxs-lookup"><span data-stu-id="e63cb-127">If you already know the alias for a command, the **Name** parameter is used to determine what command the alias is associated with.</span></span>

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

<span data-ttu-id="e63cb-128">Vários aliases podem ser especificados para o valor do parâmetro **Name**.</span><span class="sxs-lookup"><span data-stu-id="e63cb-128">Multiple aliases can be specified for the value of the **Name** parameter.</span></span>

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="e63cb-129">Com frequência, você verá o parâmetro **Name** omitido, pois ele é um parâmetro posicional.</span><span class="sxs-lookup"><span data-stu-id="e63cb-129">You'll often see the **Name** parameter omitted since it's a positional parameter.</span></span>

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

<span data-ttu-id="e63cb-130">Se você desejar localizar aliases para um comando, precisará usar o parâmetro **Definition**.</span><span class="sxs-lookup"><span data-stu-id="e63cb-130">If you want to find aliases for a command, you'll need to use the **Definition** parameter.</span></span>

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="e63cb-131">O parâmetro **Definition** não pode ser usado de maneira posicional e, portanto, precisa ser especificado.</span><span class="sxs-lookup"><span data-stu-id="e63cb-131">The **Definition** parameter can't be used positionally so it must be specified.</span></span>

<span data-ttu-id="e63cb-132">Os aliases podem economizar alguns pressionamentos de teclas e são bons quando você está digitando comandos no console.</span><span class="sxs-lookup"><span data-stu-id="e63cb-132">Aliases can save you a few keystrokes and they're fine when you're typing commands into the console.</span></span>
<span data-ttu-id="e63cb-133">Eles não devem ser usados em scripts ou em qualquer código que você esteja salvando ou compartilhando com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="e63cb-133">They shouldn't be used in scripts or any code that you're saving or sharing with others.</span></span> <span data-ttu-id="e63cb-134">Conforme mencionado anteriormente neste livro, o uso de cmdlets completos e nomes de parâmetro é autodocumentado e mais fácil de ser entendido.</span><span class="sxs-lookup"><span data-stu-id="e63cb-134">As mentioned earlier in this book, using full cmdlet and parameter names is self-documenting and easier to understand.</span></span>

<span data-ttu-id="e63cb-135">Tenha cuidado ao criar aliases próprios, porque eles só existirão na sessão atual do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="e63cb-135">Use caution when creating your own aliases because they'll only exist in your current PowerShell session on your computer.</span></span>

## <a name="providers"></a><span data-ttu-id="e63cb-136">Provedores</span><span class="sxs-lookup"><span data-stu-id="e63cb-136">Providers</span></span>

<span data-ttu-id="e63cb-137">Um provedor no PowerShell é uma interface que permite um sistema de arquivos, como o acesso a um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="e63cb-137">A provider in PowerShell is an interface that allows file system like access to a datastore.</span></span> <span data-ttu-id="e63cb-138">Há vários provedores internos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e63cb-138">There are a number of built-in providers in PowerShell.</span></span>

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

<span data-ttu-id="e63cb-139">Como você pode ver nos resultados anteriores, há provedores internos para o Registro, aliases, variáveis de ambiente, sistema de arquivos, funções, variáveis, certificados e WSMan.</span><span class="sxs-lookup"><span data-stu-id="e63cb-139">As you can see in the previous results, there are built-in providers for the registry, aliases, environment variables, the file system, functions, variables, certificates, and WSMan.</span></span>

<span data-ttu-id="e63cb-140">As unidades reais que esses provedores usam para expor o armazenamento de dados podem ser determinadas com o cmdlet `Get-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="e63cb-140">The actual drives that these providers use to expose their datastore can be determined with the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="e63cb-141">O cmdlet `Get-PSDrive` exibe as unidades expostas pelos provedores e exibe as unidades lógicas do Windows, incluindo as unidades mapeadas para compartilhamentos de rede.</span><span class="sxs-lookup"><span data-stu-id="e63cb-141">The `Get-PSDrive` cmdlet not only displays drives exposed by providers, but it also displays Windows logical drives including drives mapped to network shares.</span></span>

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

<span data-ttu-id="e63cb-142">Módulos de terceiros, como o módulo do Active Directory PowerShell e o módulo do SQL Server PowerShell, adicionam uma PSDrive e um provedor do PowerShell próprios.</span><span class="sxs-lookup"><span data-stu-id="e63cb-142">Third-party modules such as the Active Directory PowerShell module and the SQLServer PowerShell module both add their own PowerShell provider and PSDrive.</span></span>

<span data-ttu-id="e63cb-143">Importe os módulos do Active Directory e do SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e63cb-143">Import the Active Directory and SQL Server PowerShell modules.</span></span>

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

<span data-ttu-id="e63cb-144">Verifique se outros provedores do PowerShell foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="e63cb-144">Check to see if any additional PowerShell providers were added.</span></span>

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

<span data-ttu-id="e63cb-145">Observe que, no conjunto de resultados anterior, agora existem dois novos provedores do PowerShell, um para o Active Directory e outro para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e63cb-145">Notice that in the previous set of results, two new PowerShell providers now exist, one for Active Directory and another one for SQL Server.</span></span>

<span data-ttu-id="e63cb-146">Uma PSDrive para cada um desses módulos também foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="e63cb-146">A PSDrive for each of those modules was also added.</span></span>

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

<span data-ttu-id="e63cb-147">As PSDrives podem ser acessadas da mesma forma que um sistema de arquivos tradicional.</span><span class="sxs-lookup"><span data-stu-id="e63cb-147">PSDrives can be accessed just like a traditional file system.</span></span>

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

## <a name="comparison-operators"></a><span data-ttu-id="e63cb-148">Operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="e63cb-148">Comparison Operators</span></span>

<span data-ttu-id="e63cb-149">O PowerShell contém vários operadores de comparação que são usados para comparar valores ou localizar valores que correspondem a determinados padrões.</span><span class="sxs-lookup"><span data-stu-id="e63cb-149">PowerShell contains a number of comparison operators that are used to compare values or find values that match certain patterns.</span></span> <span data-ttu-id="e63cb-150">A Tabela 5-1 contém uma lista de operadores de comparação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e63cb-150">Table 5-1 contains a list of comparison operators in PowerShell.</span></span>

|    <span data-ttu-id="e63cb-151">Operador</span><span class="sxs-lookup"><span data-stu-id="e63cb-151">Operator</span></span>    |                          <span data-ttu-id="e63cb-152">Definição</span><span class="sxs-lookup"><span data-stu-id="e63cb-152">Definition</span></span>                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | <span data-ttu-id="e63cb-153">Igual a</span><span class="sxs-lookup"><span data-stu-id="e63cb-153">Equal to</span></span>                                                     |
| `-ne`          | <span data-ttu-id="e63cb-154">É diferente de</span><span class="sxs-lookup"><span data-stu-id="e63cb-154">Not equal to</span></span>                                                 |
| `-gt`          | <span data-ttu-id="e63cb-155">Maior que</span><span class="sxs-lookup"><span data-stu-id="e63cb-155">Greater than</span></span>                                                 |
| `-ge`          | <span data-ttu-id="e63cb-156">Maior que ou igual a</span><span class="sxs-lookup"><span data-stu-id="e63cb-156">Greater than or equal to</span></span>                                     |
| `-lt`          | <span data-ttu-id="e63cb-157">Menor que</span><span class="sxs-lookup"><span data-stu-id="e63cb-157">Less than</span></span>                                                    |
| `-le`          | <span data-ttu-id="e63cb-158">Menor que ou igual a</span><span class="sxs-lookup"><span data-stu-id="e63cb-158">Less than or equal to</span></span>                                        |
| `-Like`        | <span data-ttu-id="e63cb-159">Corresponde à expressão usando o caractere curinga `*`</span><span class="sxs-lookup"><span data-stu-id="e63cb-159">Match using the `*` wildcard character</span></span>                       |
| `-NotLike`     | <span data-ttu-id="e63cb-160">Não corresponde à expressão usando o caractere curinga `*`</span><span class="sxs-lookup"><span data-stu-id="e63cb-160">Does not match using the `*` wildcard character</span></span>              |
| `-Match`       | <span data-ttu-id="e63cb-161">Corresponde à expressão regular especificada</span><span class="sxs-lookup"><span data-stu-id="e63cb-161">Matches the specified regular expression</span></span>                     |
| `-NotMatch`    | <span data-ttu-id="e63cb-162">Não corresponde à expressão regular especificada</span><span class="sxs-lookup"><span data-stu-id="e63cb-162">Does not match the specified regular expression</span></span>              |
| `-Contains`    | <span data-ttu-id="e63cb-163">Determina se uma coleção contém um valor especificado</span><span class="sxs-lookup"><span data-stu-id="e63cb-163">Determines if a collection contains a specified value</span></span>        |
| `-NotContains` | <span data-ttu-id="e63cb-164">Determina se uma coleção não contém um valor específico</span><span class="sxs-lookup"><span data-stu-id="e63cb-164">Determines if a collection does not contain a specific value</span></span> |
| `-In`          | <span data-ttu-id="e63cb-165">Determina se um valor especificado está em uma coleção</span><span class="sxs-lookup"><span data-stu-id="e63cb-165">Determines if a specified value is in a collection</span></span>           |
| `-NotIn`       | <span data-ttu-id="e63cb-166">Determina se um valor especificado não está em uma coleção</span><span class="sxs-lookup"><span data-stu-id="e63cb-166">Determines if a specified value is not in a collection</span></span>       |
| `-Replace`     | <span data-ttu-id="e63cb-167">Substitui o valor especificado</span><span class="sxs-lookup"><span data-stu-id="e63cb-167">Replaces the specified value</span></span>                                 |

<span data-ttu-id="e63cb-168">Todos os operadores listados na Tabela 5-1 não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e63cb-168">All of the operators listed in Table 5-1 are case-insensitive.</span></span> <span data-ttu-id="e63cb-169">Coloque um `c` na frente do operador listado na Tabela 5-1 para fazer com que ele diferencie maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e63cb-169">Place a `c` in front of the operator listed in Table 5-1 to make it case-sensitive.</span></span> <span data-ttu-id="e63cb-170">Por exemplo, `-ceq` é a versão que diferencia maiúsculas de minúsculas do operador de comparação `-eq`.</span><span class="sxs-lookup"><span data-stu-id="e63cb-170">For example, `-ceq` is the case-sensitive version of the `-eq` comparison operator.</span></span>

<span data-ttu-id="e63cb-171">"PowerShell" com o uso correto de maiúsculas é igual a "powershell" em minúsculas com o operador de comparação equals.</span><span class="sxs-lookup"><span data-stu-id="e63cb-171">Proper case "PowerShell" is equal to lower case "powershell" using the equals comparison operator.</span></span>

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

<span data-ttu-id="e63cb-172">Ele não é igual ao uso da versão que diferencia maiúsculas de minúsculas do operador de comparação equals.</span><span class="sxs-lookup"><span data-stu-id="e63cb-172">It's not equal using the case-sensitive version of the equals comparison operator.</span></span>

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

<span data-ttu-id="e63cb-173">O operador de comparação não igual inverte a condição.</span><span class="sxs-lookup"><span data-stu-id="e63cb-173">The not equal comparison operator reverses the condition.</span></span>

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

<span data-ttu-id="e63cb-174">Maior que, maior que ou igual a, menor que e menor que ou igual a funcionam com valores numéricos ou cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e63cb-174">Greater than, greater than or equal to, less than, and less than or equal all work with string or numeric values.</span></span>

```powershell
5 -gt 5
```

```Output
False
```

<span data-ttu-id="e63cb-175">O uso de maior que ou igual a em vez de maior que com o exemplo anterior retorna o **booliano** true, pois cinco é igual a cinco.</span><span class="sxs-lookup"><span data-stu-id="e63cb-175">Using greater than or equal to instead of greater than with the previous example returns the **Boolean** true since five is equal to five.</span></span>

```powershell
5 -ge 5
```

```Output
True
```

<span data-ttu-id="e63cb-176">Com base nos resultados dos dois exemplos anteriores, é provável que você adivinhe como funcionam menor que e menor que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="e63cb-176">Based on the results from the previous two examples, you can probably guess how both less than and less than or equal to work.</span></span>

```powershell
5 -lt 10
```

```Output
True
```

<span data-ttu-id="e63cb-177">Os operadores `-Like` e `-Match` podem ser confusos, mesmo para usuários experientes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e63cb-177">The `-Like` and `-Match` operators can be confusing, even for experienced PowerShell users.</span></span> <span data-ttu-id="e63cb-178">`-Like` é usado com os caracteres curinga `*` e `?` para fazer correspondências "semelhantes".</span><span class="sxs-lookup"><span data-stu-id="e63cb-178">`-Like` is used with wildcard the characters `*` and `?` to perform "like" matches.</span></span>

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

<span data-ttu-id="e63cb-179">`-Match` usa uma expressão regular para fazer a correspondência.</span><span class="sxs-lookup"><span data-stu-id="e63cb-179">`-Match` uses a regular expression to perform the matching.</span></span>

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

<span data-ttu-id="e63cb-180">Use o operador de intervalo para armazenar os números 1 a 10 em uma variável.</span><span class="sxs-lookup"><span data-stu-id="e63cb-180">Use the range operator to store the numbers 1 through 10 in a variable.</span></span>

```powershell
$Numbers = 1..10
```

```Output
```

<span data-ttu-id="e63cb-181">Determine se a variável `$Numbers` inclui o 15.</span><span class="sxs-lookup"><span data-stu-id="e63cb-181">Determine if the `$Numbers` variable includes 15.</span></span>

```powershell
$Numbers -contains 15
```

```Output
False
```

<span data-ttu-id="e63cb-182">Determine se ele inclui o número 10.</span><span class="sxs-lookup"><span data-stu-id="e63cb-182">Determine if it includes the number 10.</span></span>

```powershell
$Numbers -contains 10
```

```Output
True
```

<span data-ttu-id="e63cb-183">`-NotContains` inverte a lógica para ver se a variável `$Numbers` não contém um valor.</span><span class="sxs-lookup"><span data-stu-id="e63cb-183">`-NotContains` reverses the logic to see if the `$Numbers` variable doesn't contain a value.</span></span>

```powershell
$Numbers -notcontains 15
```

```Output
True
```

<span data-ttu-id="e63cb-184">O exemplo anterior retorna o **booliano** true, porque é verdade que a variável `$Numbers` não contém o 15.</span><span class="sxs-lookup"><span data-stu-id="e63cb-184">The previous example returns the **Boolean** true because it's true that the `$Numbers` variable doesn't contain 15.</span></span> <span data-ttu-id="e63cb-185">No entanto, ela contém o número 10 e, portanto, é falsa quando é testada.</span><span class="sxs-lookup"><span data-stu-id="e63cb-185">It does however contain the number 10 so it's false when it's tested.</span></span>

```powershell
$Numbers -notcontains 10
```

```Output
False
```

<span data-ttu-id="e63cb-186">O operador de comparação "in" foi apresentado pela primeira vez no PowerShell versão 3.0.</span><span class="sxs-lookup"><span data-stu-id="e63cb-186">The "in" comparison operator was first introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="e63cb-187">Ele é usado para determinar se um valor está "em" uma matriz.</span><span class="sxs-lookup"><span data-stu-id="e63cb-187">It's used to determine if a value is "in" an array.</span></span> <span data-ttu-id="e63cb-188">A variável `$Numbers` é uma matriz, pois contém vários valores.</span><span class="sxs-lookup"><span data-stu-id="e63cb-188">The `$Numbers` variable is an array since it contains multiple values.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="e63cb-189">Em outras palavras, `-in` executa o mesmo teste que o operador de comparação contains, exceto que isso é feito na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="e63cb-189">In other words, `-in` performs the same test as the contains comparison operator except from the opposite direction.</span></span>

```powershell
10 -in $Numbers
```

```Output
True
```

<span data-ttu-id="e63cb-190">O 15 não está na matriz `$Numbers` e, portanto, false é retornado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e63cb-190">15 isn't in the `$Numbers` array so false is returned in the following example.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="e63cb-191">Assim como o operador `-contains`, `not` reverte a lógica para o operador `-in`.</span><span class="sxs-lookup"><span data-stu-id="e63cb-191">Just like the `-contains` operator, `not` reverses the logic for the `-in` operator.</span></span>

```powershell
10 -notin $Numbers
```

```Output
False
```

<span data-ttu-id="e63cb-192">O exemplo anterior retorna false, porque a matriz `$Numbers` inclui o 10 e a condição estava sendo testada para determinar se ela não continha o 10.</span><span class="sxs-lookup"><span data-stu-id="e63cb-192">The previous example returns false because the `$Numbers` array does include 10 and the condition was testing to determine if it didn't contain 10.</span></span>

<span data-ttu-id="e63cb-193">O 15 "não está na" matriz `$Numbers` e, portanto, retorna o **booliano** true.</span><span class="sxs-lookup"><span data-stu-id="e63cb-193">15 is "not in" the `$Numbers` array so it returns the **Boolean** true.</span></span>

```powershell
15 -notin $Numbers
```

```Output
True
```

<span data-ttu-id="e63cb-194">O operador `-replace` faz exatamente o que você pensa.</span><span class="sxs-lookup"><span data-stu-id="e63cb-194">The `-replace` operator does just want you would think.</span></span> <span data-ttu-id="e63cb-195">Ele é usado para substituir algo.</span><span class="sxs-lookup"><span data-stu-id="e63cb-195">It's used to replace something.</span></span> <span data-ttu-id="e63cb-196">A especificação de um valor substitui esse valor por nada.</span><span class="sxs-lookup"><span data-stu-id="e63cb-196">Specifying one value replaces that value with nothing.</span></span> <span data-ttu-id="e63cb-197">No exemplo a seguir, substituo "Shell" por nada.</span><span class="sxs-lookup"><span data-stu-id="e63cb-197">In the following example, I replace "Shell" with nothing.</span></span>

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

<span data-ttu-id="e63cb-198">Se você quiser substituir um valor por outro valor, especifique o novo valor após o padrão que deseja substituir.</span><span class="sxs-lookup"><span data-stu-id="e63cb-198">If you want to replace a value with a different value, specify the new value after the pattern you want to replace.</span></span> <span data-ttu-id="e63cb-199">O SQL Saturday em Baton Rouge é um evento do qual tento participar todos os anos.</span><span class="sxs-lookup"><span data-stu-id="e63cb-199">SQL Saturday in Baton Rouge is an event that I try to speak at every year.</span></span> <span data-ttu-id="e63cb-200">No exemplo a seguir, substituo a palavra "Saturday" pela abreviação "Sat".</span><span class="sxs-lookup"><span data-stu-id="e63cb-200">In the following example, I replace the word "Saturday" with the abbreviation "Sat".</span></span>

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="e63cb-201">Também há métodos como **Replace()** que podem ser usados para substituir itens semelhantes ao modo como o operador replace funciona.</span><span class="sxs-lookup"><span data-stu-id="e63cb-201">There are also methods like **Replace()** that can be used to replace things similar to the way the replace operator works.</span></span> <span data-ttu-id="e63cb-202">No entanto, o operador `-Replace` não diferencia maiúsculas de minúsculas por padrão, ao contrário do método **Replace()** .</span><span class="sxs-lookup"><span data-stu-id="e63cb-202">However, the `-Replace` operator is case-insensitive by default, and the **Replace()** method is case-sensitive.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

<span data-ttu-id="e63cb-203">Observe que a palavra "Saturday" não foi substituída no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e63cb-203">Notice that the word "Saturday" wasn't replaced in the previous example.</span></span> <span data-ttu-id="e63cb-204">Isso ocorre porque ela foi especificada com maiúsculas e minúsculas diferentes do original.</span><span class="sxs-lookup"><span data-stu-id="e63cb-204">This is because it was specified in a different case than the original.</span></span> <span data-ttu-id="e63cb-205">Quando a palavra "Saturday" é especificada com maiúsculas e minúsculas iguais às do original, o método **Replace()** a substitui como esperado.</span><span class="sxs-lookup"><span data-stu-id="e63cb-205">When the word "Saturday" is specified in the same case as the original, the **Replace()** method does replace it as expected.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="e63cb-206">Tenha cuidado ao usar métodos para transformar dados, porque você pode se deparar com problemas imprevistos, como a reprovação no _Teste da Turquia_.</span><span class="sxs-lookup"><span data-stu-id="e63cb-206">Be careful when using methods to transform data because you can run into unforeseen problems, such as failing the _Turkey Test_.</span></span> <span data-ttu-id="e63cb-207">Para obter um exemplo, confira o artigo de blog intitulado [Como usar o Pester para testar o código do PowerShell com outras culturas][].</span><span class="sxs-lookup"><span data-stu-id="e63cb-207">For an example, see the blog article titled [Using Pester to Test PowerShell Code with Other Cultures][].</span></span> <span data-ttu-id="e63cb-208">Minha recomendação é usar um operador em vez de um método sempre que possível para evitar esses tipos de problemas.</span><span class="sxs-lookup"><span data-stu-id="e63cb-208">My recommendation is to use an operator instead of a method whenever possible to avoid these types of problems.</span></span>

<span data-ttu-id="e63cb-209">Embora os operadores de comparação possam ser usados conforme mostrado nos exemplos anteriores, normalmente, uso esses operadores com o cmdlet `Where-Object` para realizar algum tipo de filtragem.</span><span class="sxs-lookup"><span data-stu-id="e63cb-209">While the comparison operators can be used as shown in the previous examples, I normally find myself using them with the `Where-Object` cmdlet to perform some type of filtering.</span></span>

## <a name="summary"></a><span data-ttu-id="e63cb-210">Resumo</span><span class="sxs-lookup"><span data-stu-id="e63cb-210">Summary</span></span>

<span data-ttu-id="e63cb-211">Neste capítulo, você conheceu vários tópicos diferentes, incluindo formatação à direta, aliases, provedores e operadores de comparação.</span><span class="sxs-lookup"><span data-stu-id="e63cb-211">In this chapter, you've learned a number of different topics to include Formatting Right, Aliases, Providers, and Comparison Operators.</span></span>

## <a name="review"></a><span data-ttu-id="e63cb-212">Revisão</span><span class="sxs-lookup"><span data-stu-id="e63cb-212">Review</span></span>

1. <span data-ttu-id="e63cb-213">Por que é necessário realizar a formatação o máximo possível à direita?</span><span class="sxs-lookup"><span data-stu-id="e63cb-213">Why is it necessary to perform Formatting as far to the right as possible?</span></span>
1. <span data-ttu-id="e63cb-214">Como determinar qual é o cmdlet real para o alias `%`?</span><span class="sxs-lookup"><span data-stu-id="e63cb-214">How do you determine what the actual cmdlet is for the `%` alias?</span></span>
1. <span data-ttu-id="e63cb-215">Por que você não deve usar aliases em scripts salvos ou em códigos que compartilha com outras pessoas?</span><span class="sxs-lookup"><span data-stu-id="e63cb-215">Why shouldn't you use aliases in scripts you save or code you share with others?</span></span>
1. <span data-ttu-id="e63cb-216">Faça uma listagem de diretórios nas unidades que estão associados a um dos provedores de Registro.</span><span class="sxs-lookup"><span data-stu-id="e63cb-216">Perform a directory listing on the drives that are associated with one of the registry providers.</span></span>
1. <span data-ttu-id="e63cb-217">Qual é um dos principais benefícios do uso do operador replace em vez do método replace?</span><span class="sxs-lookup"><span data-stu-id="e63cb-217">What's one of the main benefits of using the replace operator instead of the replace method?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="e63cb-218">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="e63cb-218">Recommended Reading</span></span>

- <span data-ttu-id="e63cb-219">[Format-Table][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-219">[Format-Table][]</span></span>
- <span data-ttu-id="e63cb-220">[Format-List][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-220">[Format-List][]</span></span>
- <span data-ttu-id="e63cb-221">[Format-Wide][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-221">[Format-Wide][]</span></span>
- <span data-ttu-id="e63cb-222">[about_Aliases][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-222">[about_Aliases][]</span></span>
- <span data-ttu-id="e63cb-223">[about_Providers][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-223">[about_Providers][]</span></span>
- <span data-ttu-id="e63cb-224">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-224">[about_Comparison_Operators][]</span></span>
- <span data-ttu-id="e63cb-225">[about_Arrays][]</span><span class="sxs-lookup"><span data-stu-id="e63cb-225">[about_Arrays][]</span></span>

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
[Using Pester to Test PowerShell Code with Other Cultures]: https://mikefrobbins.com/2015/10/22/using-pester-to-test-powershell-code-with-other-cultures/
