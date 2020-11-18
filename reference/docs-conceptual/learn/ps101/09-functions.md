---
title: Funções
description: As funções do PowerShell permitem que você crie ferramentas que podem ser reutilizadas em scripts.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 9554c0b4d3932b7371201f7b08c8b9d26a567f5e
ms.sourcegitcommit: e85e56d6614cbd30e01965a5cf03fb3f5ca78103
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "94589118"
---
# <a name="chapter-9---functions"></a><span data-ttu-id="397ab-103">Capítulo 9 – Funções</span><span class="sxs-lookup"><span data-stu-id="397ab-103">Chapter 9 - Functions</span></span>

<span data-ttu-id="397ab-104">Se você estiver escrevendo um ou mais scripts do PowerShell e acreditar que está sempre precisando modificá-los para diferentes cenários, há uma boa chance de que ele seja um bom candidato a ser transformado em uma função que possa ser reutilizada.</span><span class="sxs-lookup"><span data-stu-id="397ab-104">If you're writing PowerShell one-liners or scripts and find yourself often having to modify them for different scenarios, there's a good chance that it's a good candidate to be turned into a function that can be reused.</span></span>

<span data-ttu-id="397ab-105">Sempre que possível, prefiro escrever funções porque elas são mais orientadas por ferramentas.</span><span class="sxs-lookup"><span data-stu-id="397ab-105">Whenever possible, I prefer to write functions because they are more tool oriented.</span></span> <span data-ttu-id="397ab-106">Posso colocar as funções em um módulo de script, colocar esse módulo em `$env:PSModulePath` e chamar as funções sem precisar localizar fisicamente o local em que elas foram salvas.</span><span class="sxs-lookup"><span data-stu-id="397ab-106">I can put the functions in a script module, put that module in the `$env:PSModulePath`, and call the functions without needing to physically locate where they're saved.</span></span> <span data-ttu-id="397ab-107">Usando o módulo PowerShellGet, é fácil compartilhar esses módulos em um repositório do NuGet.</span><span class="sxs-lookup"><span data-stu-id="397ab-107">Using the PowerShellGet module, it's easy to share those modules in a NuGet repository.</span></span> <span data-ttu-id="397ab-108">O PowerShellGet é fornecido no PowerShell versão 5.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="397ab-108">PowerShellGet ships with PowerShell version 5.0 and higher.</span></span> <span data-ttu-id="397ab-109">Ele está disponível como um download separado para o PowerShell versão 3.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="397ab-109">It is available as a separate download for PowerShell version 3.0 and higher.</span></span>

<span data-ttu-id="397ab-110">Não complique demais.</span><span class="sxs-lookup"><span data-stu-id="397ab-110">Don't over complicate things.</span></span> <span data-ttu-id="397ab-111">Mantenha a simplicidade e use a maneira mais direta de realizar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="397ab-111">Keep it simple and use the most straight forward way to accomplish a task.</span></span> <span data-ttu-id="397ab-112">Evite aliases e parâmetros posicionais em qualquer código que você reutilize.</span><span class="sxs-lookup"><span data-stu-id="397ab-112">Avoid aliases and positional parameters in any code that you reuse.</span></span> <span data-ttu-id="397ab-113">Formate seu código para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="397ab-113">Format your code for readability.</span></span> <span data-ttu-id="397ab-114">Não embuta os valores em código. Use parâmetros e variáveis.</span><span class="sxs-lookup"><span data-stu-id="397ab-114">Don't hardcode values; use parameters and variables.</span></span> <span data-ttu-id="397ab-115">Não escreva código desnecessário mesmo que isso não prejudique nada.</span><span class="sxs-lookup"><span data-stu-id="397ab-115">Don't write unnecessary code even if it doesn't hurt anything.</span></span> <span data-ttu-id="397ab-116">Ele adiciona complexidade desnecessária.</span><span class="sxs-lookup"><span data-stu-id="397ab-116">It adds unnecessary complexity.</span></span> <span data-ttu-id="397ab-117">A atenção aos detalhes ajuda muito ao escrever qualquer código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="397ab-117">Attention to detail goes a long way when writing any PowerShell code.</span></span>

## <a name="naming"></a><span data-ttu-id="397ab-118">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="397ab-118">Naming</span></span>

<span data-ttu-id="397ab-119">Ao nomear suas funções no PowerShell, use um nome [Pascal Case][] com um verbo aprovado e um substantivo singular.</span><span class="sxs-lookup"><span data-stu-id="397ab-119">When naming your functions in PowerShell, use a [Pascal case][] name with an approved verb and a singular noun.</span></span> <span data-ttu-id="397ab-120">Também recomendo a prefixação do substantivo.</span><span class="sxs-lookup"><span data-stu-id="397ab-120">I also recommend prefixing the noun.</span></span> <span data-ttu-id="397ab-121">Por exemplo: `<ApprovedVerb>-<Prefix><SingularNoun>`.</span><span class="sxs-lookup"><span data-stu-id="397ab-121">For example: `<ApprovedVerb>-<Prefix><SingularNoun>`.</span></span>

<span data-ttu-id="397ab-122">No PowerShell, há uma lista específica de verbos aprovados que podem ser obtidos executando `Get-Verb`.</span><span class="sxs-lookup"><span data-stu-id="397ab-122">In PowerShell, there's a specific list of approved verbs that can be obtained by running `Get-Verb`.</span></span>

```powershell
Get-Verb | Sort-Object -Property Verb
```

```Output
Verb        Group
----        -----
Add         Common
Approve     Lifecycle
Assert      Lifecycle
Backup      Data
Block       Security
Checkpoint  Data
Clear       Common
Close       Common
Compare     Data
Complete    Lifecycle
Compress    Data
Confirm     Lifecycle
Connect     Communications
Convert     Data
ConvertFrom Data
ConvertTo   Data
Copy        Common
Debug       Diagnostic
Deny        Lifecycle
Disable     Lifecycle
Disconnect  Communications
Dismount    Data
Edit        Data
Enable      Lifecycle
Enter       Common
Exit        Common
Expand      Data
Export      Data
Find        Common
Format      Common
Get         Common
Grant       Security
Group       Data
Hide        Common
Import      Data
Initialize  Data
Install     Lifecycle
Invoke      Lifecycle
Join        Common
Limit       Data
Lock        Common
Measure     Diagnostic
Merge       Data
Mount       Data
Move        Common
New         Common
Open        Common
Optimize    Common
Out         Data
Ping        Diagnostic
Pop         Common
Protect     Security
Publish     Data
Push        Common
Read        Communications
Receive     Communications
Redo        Common
Register    Lifecycle
Remove      Common
Rename      Common
Repair      Diagnostic
Request     Lifecycle
Reset       Common
Resize      Common
Resolve     Diagnostic
Restart     Lifecycle
Restore     Data
Resume      Lifecycle
Revoke      Security
Save        Data
Search      Common
Select      Common
Send        Communications
Set         Common
Show        Common
Skip        Common
Split       Common
Start       Lifecycle
Step        Common
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Switch      Common
Sync        Data
Test        Diagnostic
Trace       Diagnostic
Unblock     Security
Undo        Common
Uninstall   Lifecycle
Unlock      Common
Unprotect   Security
Unpublish   Data
Unregister  Lifecycle
Update      Data
Use         Other
Wait        Lifecycle
Watch       Common
Write       Communications
```

<span data-ttu-id="397ab-123">No exemplo anterior, classifiquei os resultados pela coluna **Verb**.</span><span class="sxs-lookup"><span data-stu-id="397ab-123">In the previous example, I've sorted the results by the **Verb** column.</span></span> <span data-ttu-id="397ab-124">A coluna **Group** dá uma ideia de como esses verbos são usados.</span><span class="sxs-lookup"><span data-stu-id="397ab-124">The **Group** column gives you an idea of how these verbs are used.</span></span> <span data-ttu-id="397ab-125">É importante escolher um verbo aprovado no PowerShell quando as funções são adicionadas a um módulo.</span><span class="sxs-lookup"><span data-stu-id="397ab-125">It's important to choose an approved verb in PowerShell when functions are added to a module.</span></span> <span data-ttu-id="397ab-126">O módulo vai gerar uma mensagem de aviso no tempo de carregamento se você escolher um verbo não aprovado.</span><span class="sxs-lookup"><span data-stu-id="397ab-126">The module generates a warning message at load time if you choose an unapproved verb.</span></span> <span data-ttu-id="397ab-127">Essa mensagem de aviso faz com que suas funções pareçam não profissionais.</span><span class="sxs-lookup"><span data-stu-id="397ab-127">That warning message makes your functions look unprofessional.</span></span> <span data-ttu-id="397ab-128">Os verbos não aprovados também limitam a capacidade de descoberta de suas funções.</span><span class="sxs-lookup"><span data-stu-id="397ab-128">Unapproved verbs also limit the discoverability of your functions.</span></span>

## <a name="a-simple-function"></a><span data-ttu-id="397ab-129">Uma função simples</span><span class="sxs-lookup"><span data-stu-id="397ab-129">A simple function</span></span>

<span data-ttu-id="397ab-130">Uma função no PowerShell é declarada com a palavra-chave function seguida pelo nome da função e, em seguida, uma chave de abertura e fechamento.</span><span class="sxs-lookup"><span data-stu-id="397ab-130">A function in PowerShell is declared with the function keyword followed by the function name and then an open and closing curly brace.</span></span> <span data-ttu-id="397ab-131">O código que a função executará está contido nessas chaves.</span><span class="sxs-lookup"><span data-stu-id="397ab-131">The code that the function will execute is contained within those curly braces.</span></span>

```powershell
function Get-Version {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="397ab-132">A função mostrada é um exemplo simples que retorna a versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="397ab-132">The function shown is a simple example that returns the version of PowerShell.</span></span>

```powershell
Get-Version
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="397ab-133">Há uma boa chance de conflito de nome com funções que têm um nome como `Get-Version` e comandos padrão no PowerShell ou comandos que outras pessoas possam escrever.</span><span class="sxs-lookup"><span data-stu-id="397ab-133">There's a good chance of name conflict with functions named something like `Get-Version` and default commands in PowerShell or commands that others may write.</span></span> <span data-ttu-id="397ab-134">É por isso que recomendo a prefixação da parte do substantivo de suas funções para ajudar a evitar conflitos de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="397ab-134">This is why I recommend prefixing the noun portion of your functions to help prevent naming conflicts.</span></span> <span data-ttu-id="397ab-135">No exemplo a seguir, usarei o prefixo "PS".</span><span class="sxs-lookup"><span data-stu-id="397ab-135">In the following example, I'll use the prefix "PS".</span></span>

```powershell
function Get-PSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="397ab-136">Além do nome, essa função é idêntica à anterior.</span><span class="sxs-lookup"><span data-stu-id="397ab-136">Other than the name, this function is identical to the previous one.</span></span>

```powershell
Get-PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="397ab-137">Mesmo ao prefixar o substantivo com algo como o PS, ainda há uma boa chance de ter um conflito de nome.</span><span class="sxs-lookup"><span data-stu-id="397ab-137">Even when prefixing the noun with something like PS, there's still a good chance of having a name conflict.</span></span> <span data-ttu-id="397ab-138">Normalmente, prefixarei meus substantivos de função com minhas iniciais.</span><span class="sxs-lookup"><span data-stu-id="397ab-138">I typically prefix my function nouns with my initials.</span></span> <span data-ttu-id="397ab-139">Desenvolva um padrão e se atenha a ele.</span><span class="sxs-lookup"><span data-stu-id="397ab-139">Develop a standard and stick to it.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="397ab-140">Essa função não é diferente das duas anteriores, além de usar um nome mais sensato para tentar evitar conflitos de nomenclatura com outros comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="397ab-140">This function is no different than the previous two other than using a more sensible name to try to prevent naming conflicts with other PowerShell commands.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="397ab-141">Uma vez carregadas na memória, você poderá ver funções na PSDrive **Function**.</span><span class="sxs-lookup"><span data-stu-id="397ab-141">Once loaded into memory, you can see functions on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-Version
Function        Get-PSVersion
Function        Get-MrPSVersion
```

<span data-ttu-id="397ab-142">Se desejar remover essas funções da sessão atual, você precisará removê-las da PSDrive **Function** ou fechar e reabrir o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="397ab-142">If you want to remove these functions from your current session, you'll have to remove them from the **Function** PSDrive or close and reopen PowerShell.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version | Remove-Item
```

<span data-ttu-id="397ab-143">Verifique se as funções foram realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="397ab-143">Verify that the functions were indeed removed.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

<span data-ttu-id="397ab-144">Se as funções tiverem sido carregadas como parte de um módulo, o módulo poderá ser descarregado para removê-las.</span><span class="sxs-lookup"><span data-stu-id="397ab-144">If the functions were loaded as part of a module, the module can be unloaded to remove them.</span></span>

```powershell
Remove-Module -Name <ModuleName>
```

<span data-ttu-id="397ab-145">O cmdlet `Remove-Module` remove módulos da memória na sua sessão atual do PowerShell, ele não os remove do seu sistema ou do disco.</span><span class="sxs-lookup"><span data-stu-id="397ab-145">The `Remove-Module` cmdlet removes modules from memory in your current PowerShell session, it doesn't remove them from your system or from disk.</span></span>

## <a name="parameters"></a><span data-ttu-id="397ab-146">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="397ab-146">Parameters</span></span>

<span data-ttu-id="397ab-147">Não atribua valores estaticamente.</span><span class="sxs-lookup"><span data-stu-id="397ab-147">Don't statically assign values!</span></span> <span data-ttu-id="397ab-148">Use parâmetros e variáveis.</span><span class="sxs-lookup"><span data-stu-id="397ab-148">Use parameters and variables.</span></span> <span data-ttu-id="397ab-149">Ao nomear parâmetros, use o mesmo nome que os cmdlets padrão para seus nomes de parâmetro sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="397ab-149">When it comes to naming your parameters, use the same name as the default cmdlets for your parameter names whenever possible.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-150">Por que usei **ComputerName** e não **Computer**, **ServerName** ou **Host** para meu nome de parâmetro?</span><span class="sxs-lookup"><span data-stu-id="397ab-150">Why did I use **ComputerName** and not **Computer**, **ServerName**, or **Host** for my parameter name?</span></span> <span data-ttu-id="397ab-151">Porque eu queria que minha função fosse padronizada como os cmdlets padrão.</span><span class="sxs-lookup"><span data-stu-id="397ab-151">It's because I wanted my function standardized like the default cmdlets.</span></span>

<span data-ttu-id="397ab-152">Criarei uma função para consultar todos os comandos em um sistema e retornar quantos deles têm nomes de parâmetro específicos.</span><span class="sxs-lookup"><span data-stu-id="397ab-152">I'll create a function to query all of the commands on a system and return the number of them that have specific parameter names.</span></span>

```powershell
function Get-MrParameterCount {
    param (
        [string[]]$ParameterName
    )

    foreach ($Parameter in $ParameterName) {
        $Results = Get-Command -ParameterName $Parameter -ErrorAction SilentlyContinue

        [pscustomobject]@{
            ParameterName = $Parameter
            NumberOfCmdlets = $Results.Count
        }
    }
}
```

<span data-ttu-id="397ab-153">Como você pode ver nos resultados mostrados abaixo, 39 comandos têm um parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="397ab-153">As you can see in the results shown below, 39 commands that have a **ComputerName** parameter.</span></span> <span data-ttu-id="397ab-154">Não há cmdlets com parâmetros como **Computer**, **ServerName**, **Host** ou **Machine**.</span><span class="sxs-lookup"><span data-stu-id="397ab-154">There aren't any cmdlets that have parameters such as **Computer**, **ServerName**, **Host**, or **Machine**.</span></span>

```powershell
Get-MrParameterCount -ParameterName ComputerName, Computer, ServerName, Host, Machine
```

```Output
ParameterName NumberOfCmdlets
------------- ---------------
ComputerName               39
Computer                    0
ServerName                  0
Host                        0
Machine                     0
```

<span data-ttu-id="397ab-155">Também recomendo usar as mesmas letras maiúsculas e minúsculas para os nomes de parâmetro que os cmdlets padrão.</span><span class="sxs-lookup"><span data-stu-id="397ab-155">I also recommend using the same case for your parameter names as the default cmdlets.</span></span> <span data-ttu-id="397ab-156">Use `ComputerName`, não `computername`.</span><span class="sxs-lookup"><span data-stu-id="397ab-156">Use `ComputerName`, not `computername`.</span></span> <span data-ttu-id="397ab-157">Isso faz com que suas funções se pareçam com os cmdlets padrão.</span><span class="sxs-lookup"><span data-stu-id="397ab-157">This makes your functions look and feel like the default cmdlets.</span></span> <span data-ttu-id="397ab-158">As pessoas que já estão familiarizadas com o PowerShell se sentirão em casa.</span><span class="sxs-lookup"><span data-stu-id="397ab-158">People who are already familiar with PowerShell will feel right at home.</span></span>

## <a name="advanced-functions"></a><span data-ttu-id="397ab-159">Funções avançadas</span><span class="sxs-lookup"><span data-stu-id="397ab-159">Advanced Functions</span></span>

<span data-ttu-id="397ab-160">Transformar uma função no PowerShell em uma função avançada é realmente simples.</span><span class="sxs-lookup"><span data-stu-id="397ab-160">Turning a function in PowerShell into an advanced function is really simple.</span></span> <span data-ttu-id="397ab-161">Uma das diferenças entre uma função e uma função avançada é que as funções avançadas têm um número de parâmetros comuns que são adicionados à função automaticamente.</span><span class="sxs-lookup"><span data-stu-id="397ab-161">One of the differences between a function and an advanced function is that advanced functions have a number of common parameters that are added to the function automatically.</span></span> <span data-ttu-id="397ab-162">Esses parâmetros comuns incluem parâmetros como **Verbose** e **Debug**.</span><span class="sxs-lookup"><span data-stu-id="397ab-162">These common parameters include parameters such as **Verbose** and **Debug**.</span></span>

<span data-ttu-id="397ab-163">Começarei com a função `Test-MrParameter` que foi usada na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="397ab-163">I'll start out with the `Test-MrParameter` function that was used in the previous section.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-164">Observe que a função `Test-MrParameter` não tem nenhum parâmetro comum.</span><span class="sxs-lookup"><span data-stu-id="397ab-164">What I want you to notice is that the `Test-MrParameter` function doesn't have any common parameters.</span></span> <span data-ttu-id="397ab-165">Há algumas maneiras diferentes de ver os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="397ab-165">There are a couple of different ways to see the common parameters.</span></span> <span data-ttu-id="397ab-166">Uma delas é exibir a sintaxe usando `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="397ab-166">One is by viewing the syntax using `Get-Command`.</span></span>

```powershell
Get-Command -Name Test-MrParameter -Syntax
```

```Output
Test-MrParameter [[-ComputerName] <Object>]
```

<span data-ttu-id="397ab-167">Outra é fazer uma busca detalhada nos parâmetros com `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="397ab-167">Another is to drill down into the parameters with `Get-Command`.</span></span>

```powershell
(Get-Command -Name Test-MrParameter).Parameters.Keys
```

```Output
ComputerName
```

<span data-ttu-id="397ab-168">Adicione `CmdletBinding` para transformar a função em uma função avançada.</span><span class="sxs-lookup"><span data-stu-id="397ab-168">Add `CmdletBinding` to turn the function into an advanced function.</span></span>

```powershell
function Test-MrCmdletBinding {

    [CmdletBinding()] #<<-- This turns a regular function into an advanced function
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-169">Adicionar `CmdletBinding` adiciona os parâmetros comuns automaticamente.</span><span class="sxs-lookup"><span data-stu-id="397ab-169">Adding `CmdletBinding` adds the common parameters automatically.</span></span> <span data-ttu-id="397ab-170">`CmdletBinding` requer um bloco de `param`, mas o bloco de `param` pode estar vazio.</span><span class="sxs-lookup"><span data-stu-id="397ab-170">`CmdletBinding` requires a `param` block, but the `param` block can be empty.</span></span>

```powershell
Get-Command -Name Test-MrCmdletBinding -Syntax
```

```Output
Test-MrCmdletBinding [[-ComputerName] <Object>] [<CommonParameters>]
```

<span data-ttu-id="397ab-171">Analisar detalhadamente os parâmetros com `Get-Command` mostra os nomes de parâmetro reais, incluindo os comuns.</span><span class="sxs-lookup"><span data-stu-id="397ab-171">Drilling down into the parameters with `Get-Command` shows the actual parameter names including the common ones.</span></span>

```powershell
(Get-Command -Name Test-MrCmdletBinding).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="397ab-172">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="397ab-172">SupportsShouldProcess</span></span>

<span data-ttu-id="397ab-173">`SupportsShouldProcess` adiciona os parâmetros **WhatIf** e **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="397ab-173">`SupportsShouldProcess` adds **WhatIf** and **Confirm** parameters.</span></span> <span data-ttu-id="397ab-174">Eles são necessários apenas para comandos que fazem alterações.</span><span class="sxs-lookup"><span data-stu-id="397ab-174">These are only needed for commands that make changes.</span></span>

```powershell
function Test-MrSupportsShouldProcess {

    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-175">Observe que agora há os parâmetros **WhatIf** e **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="397ab-175">Notice that there are now **WhatIf** and **Confirm** parameters.</span></span>

```powershell
Get-Command -Name Test-MrSupportsShouldProcess -Syntax
```

```Output
Test-MrSupportsShouldProcess [[-ComputerName] <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="397ab-176">Mais uma vez, você também pode usar `Get-Command` para retornar uma lista dos nomes de parâmetro reais, incluindo os comuns, juntamente com WhatIf e Confirm.</span><span class="sxs-lookup"><span data-stu-id="397ab-176">Once again, you can also use `Get-Command` to return a list of the actual parameter names including the common ones along with WhatIf and Confirm.</span></span>

```powershell
(Get-Command -Name Test-MrSupportsShouldProcess).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
WhatIf
Confirm
```

## <a name="parameter-validation"></a><span data-ttu-id="397ab-177">Validação de parâmetro</span><span class="sxs-lookup"><span data-stu-id="397ab-177">Parameter Validation</span></span>

<span data-ttu-id="397ab-178">Valide a entrada no início.</span><span class="sxs-lookup"><span data-stu-id="397ab-178">Validate input early on.</span></span> <span data-ttu-id="397ab-179">Por que o código pode continuar em um caminho quando não é possível executá-lo sem uma entrada válida?</span><span class="sxs-lookup"><span data-stu-id="397ab-179">Why allow your code to continue on a path when it's not possible to run without valid input?</span></span>

<span data-ttu-id="397ab-180">Sempre digite as variáveis que estão sendo usadas para seus parâmetros (especifique um tipo de dados).</span><span class="sxs-lookup"><span data-stu-id="397ab-180">Always type the variables that are being used for your parameters (specify a datatype).</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-181">No exemplo anterior, especifiquei **String** como o tipo de dados do parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="397ab-181">In the previous example, I've specified **String** as the datatype for the **ComputerName** parameter.</span></span> <span data-ttu-id="397ab-182">Isso faz com que ele permita que apenas um único nome do computador seja especificado.</span><span class="sxs-lookup"><span data-stu-id="397ab-182">This causes it to allow only a single computer name to be specified.</span></span> <span data-ttu-id="397ab-183">Se mais de um nome do computador for especificado por meio de uma lista separada por vírgulas, um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="397ab-183">If more than one computer name is specified via a comma-separated list, an error is generated.</span></span>

```powershell
Test-MrParameterValidation -ComputerName Server01, Server02
```

```Output
Test-MrParameterValidation : Cannot process argument transformation on parameter
'ComputerName'. Cannot convert value to type System.String.
At line:1 char:42
+ Test-MrParameterValidation -ComputerName Server01, Server02
+
    + CategoryInfo          : InvalidData: (:) [Test-MrParameterValidation], ParameterBindingArg
     umentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Test-MrParameterValidation
```

<span data-ttu-id="397ab-184">O problema com a definição atual é que ela é válida para omitir o valor do parâmetro **ComputerName**, mas um valor é necessário para que a função seja concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="397ab-184">The problem with the current definition is that it's valid to omit the value of the **ComputerName** parameter, but a value is required for the function to complete successfully.</span></span> <span data-ttu-id="397ab-185">É aí que o atributo de parâmetro `Mandatory` é útil.</span><span class="sxs-lookup"><span data-stu-id="397ab-185">This is where the `Mandatory` parameter attribute comes in handy.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-186">A sintaxe usada no exemplo anterior é compatível com o PowerShell versão 3.0 e superiores.</span><span class="sxs-lookup"><span data-stu-id="397ab-186">The syntax used in the previous example is PowerShell version 3.0 and higher compatible.</span></span>
<span data-ttu-id="397ab-187">`[Parameter(Mandatory=$true)]` pode ser especificado em vez de tornar a função compatível com o PowerShell versão 2.0 e superiores.</span><span class="sxs-lookup"><span data-stu-id="397ab-187">`[Parameter(Mandatory=$true)]` could be specified instead to make the function compatible with PowerShell version 2.0 and higher.</span></span> <span data-ttu-id="397ab-188">Agora que o **ComputerName** é necessário, se um não for especificado, a função o solicitará.</span><span class="sxs-lookup"><span data-stu-id="397ab-188">Now that the **ComputerName** is required, if one isn't specified, the function will prompt for one.</span></span>

```powershell
Test-MrParameterValidation
```

```Output
cmdlet Test-MrParameterValidation at command pipeline position 1
Supply values for the following parameters:
ComputerName:
```

<span data-ttu-id="397ab-189">Se você quiser permitir mais de um valor para o parâmetro **ComputerName**, use o tipo de dados **String**, mas adicione colchetes abertos e fechados ao tipo de dados para permitir uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="397ab-189">If you want to allow for more than one value for the **ComputerName** parameter, use the **String** datatype but add open and closed square brackets to the datatype to allow for an array of strings.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string[]]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-190">Talvez você queira especificar um valor padrão para o parâmetro **ComputerName** se um não tiver especificado.</span><span class="sxs-lookup"><span data-stu-id="397ab-190">Maybe you want to specify a default value for the **ComputerName** parameter if one isn't specified.</span></span>
<span data-ttu-id="397ab-191">O problema é que os valores padrão não podem ser usados com parâmetros obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="397ab-191">The problem is that default values can't be used with mandatory parameters.</span></span> <span data-ttu-id="397ab-192">Em vez disso, você precisará usar o atributo de validação de parâmetro `ValidateNotNullOrEmpty` com um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="397ab-192">Instead, you'll need to use the `ValidateNotNullOrEmpty` parameter validation attribute with a default value.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="397ab-193">Mesmo ao definir um valor padrão, tente não usar valores estáticos.</span><span class="sxs-lookup"><span data-stu-id="397ab-193">Even when setting a default value, try not to use static values.</span></span> <span data-ttu-id="397ab-194">No exemplo anterior, `$env:COMPUTERNAME` é usado como o valor padrão, que será automaticamente convertido no nome do computador local se um valor não for fornecido.</span><span class="sxs-lookup"><span data-stu-id="397ab-194">In the previous example, `$env:COMPUTERNAME` is used as the default value, which is automatically translated into the local computer name if a value is not provided.</span></span>

## <a name="verbose-output"></a><span data-ttu-id="397ab-195">Saída detalhada</span><span class="sxs-lookup"><span data-stu-id="397ab-195">Verbose Output</span></span>

<span data-ttu-id="397ab-196">Embora comentários embutidos sejam úteis, especialmente se você estiver escrevendo um código complexo, eles nunca serão vistos pelos usuários, a menos que eles examinem o próprio código.</span><span class="sxs-lookup"><span data-stu-id="397ab-196">While inline comments are useful, especially if you're writing some complex code, they never get seen by users unless they look into the code itself.</span></span>

<span data-ttu-id="397ab-197">A função mostrada no exemplo a seguir tem um comentário embutido no loop de `foreach`.</span><span class="sxs-lookup"><span data-stu-id="397ab-197">The function shown in the following example has an inline comment in the `foreach` loop.</span></span> <span data-ttu-id="397ab-198">Embora esse comentário específico não seja tão difícil de localizar, imagine se a função incluísse centenas de linhas de código.</span><span class="sxs-lookup"><span data-stu-id="397ab-198">While this particular comment may not be that difficult to locate, imagine if the function included hundreds of lines of code.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        #Attempting to perform some action on $Computer <<-- Don't use
        #inline comments like this, use write verbose instead.
        Write-Output $Computer
    }

}
```

<span data-ttu-id="397ab-199">Uma opção melhor é usar `Write-Verbose` em vez de comentários embutidos.</span><span class="sxs-lookup"><span data-stu-id="397ab-199">A better option is to use `Write-Verbose` instead of inline comments.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        Write-Verbose -Message "Attempting to perform some action on $Computer"
        Write-Output $Computer
    }

}
```

<span data-ttu-id="397ab-200">Quando a função é chamada sem o parâmetro **Verbose**, a saída detalhada não é exibida.</span><span class="sxs-lookup"><span data-stu-id="397ab-200">When the function is called without the **Verbose** parameter, the verbose output won't be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02
```

<span data-ttu-id="397ab-201">Quando for chamado com o parâmetro **Verbose**, a saída detalhada será exibida.</span><span class="sxs-lookup"><span data-stu-id="397ab-201">When it's called with the **Verbose** parameter, the verbose output will be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02 -Verbose
```

## <a name="pipeline-input"></a><span data-ttu-id="397ab-202">Entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="397ab-202">Pipeline Input</span></span>

<span data-ttu-id="397ab-203">Quando você quiser que sua função aceite a entrada do pipeline, é necessária alguma codificação adicional.</span><span class="sxs-lookup"><span data-stu-id="397ab-203">When you want your function to accept pipeline input, some additional coding is necessary.</span></span> <span data-ttu-id="397ab-204">Como mencionado anteriormente neste livro, os comandos podem aceitar a entrada do pipeline **por valor** (por tipo) ou **por nome da propriedade**.</span><span class="sxs-lookup"><span data-stu-id="397ab-204">As mentioned earlier in this book, commands can accept pipeline input **by value** (by type) or **by property name**.</span></span> <span data-ttu-id="397ab-205">Você pode escrever suas funções exatamente como os comandos nativos para que aceitem um ou ambos os tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="397ab-205">You can write your functions just like the native commands so that they accept either one or both of these types of input.</span></span>

<span data-ttu-id="397ab-206">Para aceitar a entrada de pipeline **por valor**, especifique o atributo de parâmetro `ValueFromPipeline` para esse parâmetro específico.</span><span class="sxs-lookup"><span data-stu-id="397ab-206">To accept pipeline input **by value**, specified the `ValueFromPipeline` parameter attribute for that particular parameter.</span></span> <span data-ttu-id="397ab-207">Lembre-se de que você só pode aceitar a entrada de pipeline **por valor** de um de cada tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="397ab-207">Keep in mind that you can only accept pipeline input **by value** from one of each datatype.</span></span> <span data-ttu-id="397ab-208">Por exemplo, se você tiver dois parâmetros que aceitam a entrada de cadeia de caracteres, somente um deles poderá aceitar a entrada de pipeline **por valor** porque, se você o tiver especificado para ambos os parâmetros de cadeia de caracteres, a entrada do pipeline não saberá a qual deles se associar.</span><span class="sxs-lookup"><span data-stu-id="397ab-208">For example, if you have two parameters that accept string input, only one of those can accept pipeline input **by value** because if you specified it for both of the string parameters, the pipeline input wouldn't know which one to bind to.</span></span> <span data-ttu-id="397ab-209">Essa é outra razão pela qual eu chamo esse tipo de entrada de pipeline _por tipo_, em vez de **por valor**.</span><span class="sxs-lookup"><span data-stu-id="397ab-209">This is another reason I call this type of pipeline input _by type_ instead of **by value**.</span></span>

<span data-ttu-id="397ab-210">A entrada do pipeline vem em um item de cada vez, de maneira semelhante a como os itens são manipulados em um loop de `foreach`.</span><span class="sxs-lookup"><span data-stu-id="397ab-210">Pipeline input comes in one item at a time similar to the way items are handled in a `foreach` loop.</span></span>
<span data-ttu-id="397ab-211">No mínimo, um bloco `process` será necessário para processar cada um desses itens se você estiver aceitando uma matriz como entrada.</span><span class="sxs-lookup"><span data-stu-id="397ab-211">At a minimum, a `process` block is required to process each of these items if you're accepting an array as input.</span></span> <span data-ttu-id="397ab-212">Se você estiver aceitando apenas um único valor como entrada, um bloco de `process` não será necessário, mas eu ainda recomendo especificá-lo para fins de consistência.</span><span class="sxs-lookup"><span data-stu-id="397ab-212">If you're only accepting a single value as input, a `process` block isn't necessary, but I still recommend specifying it for consistency.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline)]
        [string[]]$ComputerName
    )

    PROCESS {
        Write-Output $ComputerName
    }

}
```

<span data-ttu-id="397ab-213">Aceitar a entrada do pipeline **pelo nome da propriedade** é semelhante, exceto pelo fato de ser especificado com o atributo de parâmetro `ValueFromPipelineByPropertyName` e pode ser especificado para qualquer número de parâmetros, independentemente do tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="397ab-213">Accepting pipeline input **by property name** is similar except it's specified with the `ValueFromPipelineByPropertyName` parameter attribute and it can be specified for any number of parameters regardless of datatype.</span></span> <span data-ttu-id="397ab-214">A chave é que a saída do comando que está sendo canalizado deve ter um nome de propriedade que corresponda ao nome do parâmetro ou a um alias de parâmetro de sua função.</span><span class="sxs-lookup"><span data-stu-id="397ab-214">The key is that the output of the command that's being piped in has to have a property name that matches the name of the parameter or a parameter alias of your function.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
            Write-Output $ComputerName
    }

}
```

<span data-ttu-id="397ab-215">Os blocos de `BEGIN` e `END` são opcionais.</span><span class="sxs-lookup"><span data-stu-id="397ab-215">`BEGIN` and `END` blocks are optional.</span></span> <span data-ttu-id="397ab-216">`BEGIN` seria especificado antes do bloco de `PROCESS` e é usado para executar qualquer trabalho inicial antes dos itens que estão sendo recebidos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="397ab-216">`BEGIN` would be specified before the `PROCESS` block and is used to perform any initial work prior to the items being received from the pipeline.</span></span> <span data-ttu-id="397ab-217">É importante entender isso.</span><span class="sxs-lookup"><span data-stu-id="397ab-217">This is important to understand.</span></span> <span data-ttu-id="397ab-218">Os valores que são canalizados para dentro não estão acessíveis no bloco de `BEGIN`.</span><span class="sxs-lookup"><span data-stu-id="397ab-218">Values that are piped in are not accessible in the `BEGIN` block.</span></span> <span data-ttu-id="397ab-219">O bloco de `END` seria especificado após o bloco de `PROCESS` e é usado para limpeza depois que todos os itens que foram canalizados para dentro foram processados.</span><span class="sxs-lookup"><span data-stu-id="397ab-219">The `END` block would be specified after the `PROCESS` block and is used for cleanup once all of the items that are piped in have been processed.</span></span>

## <a name="error-handling"></a><span data-ttu-id="397ab-220">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="397ab-220">Error Handling</span></span>

<span data-ttu-id="397ab-221">A função mostrada no exemplo a seguir gera uma exceção sem tratamento quando um computador não pode ser contatado.</span><span class="sxs-lookup"><span data-stu-id="397ab-221">The function shown in the following example generates an unhandled exception when a computer can't be contacted.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            Test-WSMan -ComputerName $Computer
        }
    }

}
```

<span data-ttu-id="397ab-222">Há algumas maneiras diferentes de lidar com erros no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="397ab-222">There are a couple of different ways to handle errors in PowerShell.</span></span> <span data-ttu-id="397ab-223">`Try/Catch` é a maneira mais moderna de lidar com erros.</span><span class="sxs-lookup"><span data-stu-id="397ab-223">`Try/Catch` is the more modern way to handle errors.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="397ab-224">Embora a função mostrada no exemplo anterior use o tratamento de erro, ela também gera uma exceção sem tratamento, pois o comando não gera um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="397ab-224">Although the function shown in the previous example uses error handling, it also generates an unhandled exception because the command doesn't generate a terminating error.</span></span> <span data-ttu-id="397ab-225">Também é importante entender isso.</span><span class="sxs-lookup"><span data-stu-id="397ab-225">This is also important to understand.</span></span> <span data-ttu-id="397ab-226">Somente erros de encerramento são capturados.</span><span class="sxs-lookup"><span data-stu-id="397ab-226">Only terminating errors are caught.</span></span> <span data-ttu-id="397ab-227">Especifique o parâmetro **ErrorAction** com **Stop** como o valor para transformar um erro de não finalização em um encerramento.</span><span class="sxs-lookup"><span data-stu-id="397ab-227">Specify the **ErrorAction** parameter with **Stop** as the value to turn a non-terminating error into a terminating one.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer -ErrorAction Stop
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="397ab-228">Não modifique a variável `$ErrorActionPreference` global, a menos que seja absolutamente necessário.</span><span class="sxs-lookup"><span data-stu-id="397ab-228">Don't modify the global `$ErrorActionPreference` variable unless absolutely necessary.</span></span> <span data-ttu-id="397ab-229">Se você estiver usando algo como o .NET diretamente de dentro de sua função do PowerShell, não poderá especificar a **ErrorAction** no próprio comando.</span><span class="sxs-lookup"><span data-stu-id="397ab-229">If you're using something like .NET directly from within your PowerShell function, you can't specify the **ErrorAction** on the command itself.</span></span> <span data-ttu-id="397ab-230">Nesse cenário, talvez seja preciso alterar a variável de `$ErrorActionPreference` global, mas se você alterá-la, faça isso imediatamente depois de tentar o comando.</span><span class="sxs-lookup"><span data-stu-id="397ab-230">In that scenario, you might need to change the global `$ErrorActionPreference` variable, but if you do change it, change it back immediately after trying the command.</span></span>

## <a name="comment-based-help"></a><span data-ttu-id="397ab-231">Ajuda baseada em comentários</span><span class="sxs-lookup"><span data-stu-id="397ab-231">Comment-Based Help</span></span>

<span data-ttu-id="397ab-232">É considerada uma melhor prática adicionar ajuda com base em comentários às suas funções para que as pessoas com as quais você está compartilhando saibam saber como usá-las.</span><span class="sxs-lookup"><span data-stu-id="397ab-232">It's considered to be a best practice to add comment based help to your functions so the people you're sharing them with will know how to use them.</span></span>

```powershell
function Get-MrAutoStoppedService {

<#
.SYNOPSIS
    Returns a list of services that are set to start automatically, are not
    currently running, excluding the services that are set to delayed start.

.DESCRIPTION
    Get-MrAutoStoppedService is a function that returns a list of services from
    the specified remote computer(s) that are set to start automatically, are not
    currently running, and it excludes the services that are set to start automatically
    with a delayed startup.

.PARAMETER ComputerName
    The remote computer(s) to check the status of the services on.

.PARAMETER Credential
    Specifies a user account that has permission to perform this action. The default
    is the current user.

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1', 'Server2'

.EXAMPLE
     'Server1', 'Server2' | Get-MrAutoStoppedService

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1' -Credential (Get-Credential)

.INPUTS
    String

.OUTPUTS
    PSCustomObject

.NOTES
    Author:  Mike F Robbins
    Website: http://mikefrobbins.com
    Twitter: @mikefrobbins
#>

    [CmdletBinding()]
    param (

    )

    #Function Body

}
```

<span data-ttu-id="397ab-233">Quando você adiciona ajuda com base em comentários às suas funções, é possível recuperar a ajuda para elas, assim como os comandos internos padrão.</span><span class="sxs-lookup"><span data-stu-id="397ab-233">When you add comment based help to your functions, help can be retrieved for them just like the default built-in commands.</span></span>

<span data-ttu-id="397ab-234">Toda a sintaxe para escrever uma função no PowerShell pode parecer difícil principalmente para alguém que está recém começando.</span><span class="sxs-lookup"><span data-stu-id="397ab-234">All of the syntax for writing a function in PowerShell can seem overwhelming especially for someone who is just getting started.</span></span> <span data-ttu-id="397ab-235">Com frequência, se eu não me lembrar da sintaxe de algo, abrirei uma segunda cópia do ISE em um monitor separado e exibirei o snippet "cmdlet (advanced function) - Complete" ao digitar o código para a minha função.</span><span class="sxs-lookup"><span data-stu-id="397ab-235">Often times if I can't remember the syntax for something, I'll open a second copy of the ISE on a separate monitor and view the "Cmdlet (advanced function) - Complete" snippet while typing in the code for my function.</span></span> <span data-ttu-id="397ab-236">Os snippets de código podem ser acessados no ISE do PowerShell usando a combinação de teclas <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="397ab-236">Snippets can be accessed in the PowerShell ISE using the <kbd>Ctrl</kbd>+<kbd>J</kbd> key combination.</span></span>

## <a name="summary"></a><span data-ttu-id="397ab-237">Resumo</span><span class="sxs-lookup"><span data-stu-id="397ab-237">Summary</span></span>

<span data-ttu-id="397ab-238">Neste capítulo, você aprendeu as noções básicas de como escrever funções no PowerShell para incluir como transformar uma função em uma função avançada e alguns dos elementos mais importantes que você deve considerar ao escrever funções do PowerShell, como validação de parâmetro, saída detalhada, entrada de pipeline, tratamento de erro e ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="397ab-238">In this chapter you've learned the basics of writing functions in PowerShell to include how to turn a function into an advanced function and some of the more important elements that you should consider when writing PowerShell functions such as parameter validation, verbose output, pipeline input, error handling, and comment based help.</span></span>

## <a name="review"></a><span data-ttu-id="397ab-239">Revisão</span><span class="sxs-lookup"><span data-stu-id="397ab-239">Review</span></span>

1. <span data-ttu-id="397ab-240">Como obter uma lista de verbos aprovados no PowerShell?</span><span class="sxs-lookup"><span data-stu-id="397ab-240">How do you obtain a list of approved verbs in PowerShell?</span></span>
1. <span data-ttu-id="397ab-241">Como transformar uma função do PowerShell em uma função avançada?</span><span class="sxs-lookup"><span data-stu-id="397ab-241">How do you turn a PowerShell function into an advanced function?</span></span>
1. <span data-ttu-id="397ab-242">Quando os parâmetros **WhatIf** e **Confirm** devem ser adicionados às funções do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="397ab-242">When should **WhatIf** and **Confirm** parameters be added to your PowerShell functions?</span></span>
1. <span data-ttu-id="397ab-243">Como você transforma um erro não de encerramento em um de encerramento?</span><span class="sxs-lookup"><span data-stu-id="397ab-243">How do you turn a non-terminating error into a terminating one?</span></span>
1. <span data-ttu-id="397ab-244">Por que você deve adicionar ajuda baseada em comentários às suas funções?</span><span class="sxs-lookup"><span data-stu-id="397ab-244">Why should you add comment based help to your functions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="397ab-245">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="397ab-245">Recommended Reading</span></span>

- <span data-ttu-id="397ab-246">[about_Functions][]</span><span class="sxs-lookup"><span data-stu-id="397ab-246">[about_Functions][]</span></span>
- <span data-ttu-id="397ab-247">[about_Functions_Advanced_Parameters][]</span><span class="sxs-lookup"><span data-stu-id="397ab-247">[about_Functions_Advanced_Parameters][]</span></span>
- <span data-ttu-id="397ab-248">[about_CommonParameters][]</span><span class="sxs-lookup"><span data-stu-id="397ab-248">[about_CommonParameters][]</span></span>
- <span data-ttu-id="397ab-249">[about_Functions_CmdletBindingAttribute][]</span><span class="sxs-lookup"><span data-stu-id="397ab-249">[about_Functions_CmdletBindingAttribute][]</span></span>
- <span data-ttu-id="397ab-250">[about_Functions_Advanced][]</span><span class="sxs-lookup"><span data-stu-id="397ab-250">[about_Functions_Advanced][]</span></span>
- <span data-ttu-id="397ab-251">[about_Try_Catch_Finally][]</span><span class="sxs-lookup"><span data-stu-id="397ab-251">[about_Try_Catch_Finally][]</span></span>
- <span data-ttu-id="397ab-252">[about_Comment_Based_Help][]</span><span class="sxs-lookup"><span data-stu-id="397ab-252">[about_Comment_Based_Help][]</span></span>
- <span data-ttu-id="397ab-253">[Vídeo: Toolmaking do PowerShell com funções avançadas e módulos de script][]</span><span class="sxs-lookup"><span data-stu-id="397ab-253">[Video: PowerShell Toolmaking with Advanced Functions and Script Modules][]</span></span>

<!-- link references -->
[about_Functions]: /powershell/module/microsoft.powershell.core/about/about_functions
[about_Functions_Advanced_Parameters]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters
[about_CommonParameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[about_Functions_CmdletBindingAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute
[about_Functions_Advanced]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[about_Try_Catch_Finally]: /powershell/module/microsoft.powershell.core/about/about_try_catch_finally
[about_Comment_Based_Help]: /powershell/module/microsoft.powershell.core/about/about_comment_based_help
[Vídeo: Toolmaking do PowerShell com funções avançadas e módulos de script]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/
[Video: PowerShell Toolmaking with Advanced Functions and Script Modules]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/
[Pascal Case]: /dotnet/standard/design-guidelines/capitalization-conventions
[Pascal case]: /dotnet/standard/design-guidelines/capitalization-conventions
