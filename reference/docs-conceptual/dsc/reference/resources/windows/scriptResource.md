---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso Script de DSC
description: Recurso Script de DSC
ms.openlocfilehash: f404bf3137caa9f57ad56034895cb15c8944ec07
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142966"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="188cd-103">Recurso Script de DSC</span><span class="sxs-lookup"><span data-stu-id="188cd-103">DSC Script Resource</span></span>

> <span data-ttu-id="188cd-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="188cd-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="188cd-105">O recurso `Script` na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para executar blocos de script do Windows PowerShell em nós de destino.</span><span class="sxs-lookup"><span data-stu-id="188cd-105">The `Script` resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="188cd-106">O recurso `Script` usa as propriedades `GetScript`
`SetScript` e `TestScript` que contém blocos de script definidos para executar as operações de estado de DSC correspondentes.</span><span class="sxs-lookup"><span data-stu-id="188cd-106">The `Script` resource uses `GetScript`
`SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="188cd-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="188cd-107">Syntax</span></span>

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="188cd-108">Os blocos `GetScript`, `TestScript` e `SetScript` são armazenados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="188cd-108">`GetScript` `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="188cd-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="188cd-109">Properties</span></span>

|  <span data-ttu-id="188cd-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="188cd-110">Property</span></span>  |                                          <span data-ttu-id="188cd-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="188cd-111">Description</span></span>                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="188cd-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="188cd-112">GetScript</span></span>  | <span data-ttu-id="188cd-113">Um bloco de script que retorna o estado atual do Node.</span><span class="sxs-lookup"><span data-stu-id="188cd-113">A script block that returns the current state of the Node.</span></span>                                    |
| <span data-ttu-id="188cd-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="188cd-114">SetScript</span></span>  | <span data-ttu-id="188cd-115">Um bloco de script usado pelo DSC para impor a conformidade quando o Node não estiver no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="188cd-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
| <span data-ttu-id="188cd-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="188cd-116">TestScript</span></span> | <span data-ttu-id="188cd-117">Um bloco de script que determina se o Node está no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="188cd-117">A script block that determines if the Node is in the desired state.</span></span>                           |
| <span data-ttu-id="188cd-118">Credencial</span><span class="sxs-lookup"><span data-stu-id="188cd-118">Credential</span></span> | <span data-ttu-id="188cd-119">Indica as credenciais que devem ser usadas para executar esse script, caso sejam necessárias.</span><span class="sxs-lookup"><span data-stu-id="188cd-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>        |

## <a name="common-properties"></a><span data-ttu-id="188cd-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="188cd-120">Common properties</span></span>

|       <span data-ttu-id="188cd-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="188cd-121">Property</span></span>       |                                            <span data-ttu-id="188cd-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="188cd-122">Description</span></span>                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="188cd-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="188cd-123">DependsOn</span></span>            | <span data-ttu-id="188cd-124">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="188cd-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> |
| <span data-ttu-id="188cd-125">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="188cd-125">PsDscRunAsCredential</span></span> | <span data-ttu-id="188cd-126">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="188cd-126">Sets the credential for running the entire resource as.</span></span>                                           |

> [!NOTE]
> <span data-ttu-id="188cd-127">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="188cd-127">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="188cd-128">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="188cd-128">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="188cd-129">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="188cd-129">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="188cd-130">GetScript</span><span class="sxs-lookup"><span data-stu-id="188cd-130">GetScript</span></span>

<span data-ttu-id="188cd-131">O DSC não usa a saída de `GetScript`. O cmdlet [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) executa `GetScript` para recuperar o estado atual de um nó.</span><span class="sxs-lookup"><span data-stu-id="188cd-131">DSC does not use the output from `GetScript` The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="188cd-132">`GetScript` não exige um valor retornado. Se você especificar um valor retornado, ele deverá ser uma tabela de hash que contenha uma chave **Result** cujo valor seja uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="188cd-132">A return value is not required from `GetScript` If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="188cd-133">TestScript</span><span class="sxs-lookup"><span data-stu-id="188cd-133">TestScript</span></span>

<span data-ttu-id="188cd-134">O `TestScript` é executado pelo DSC para determinar se o `SetScript` deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="188cd-134">`TestScript` is executed by DSC to determine if `SetScript` should be run.</span></span> <span data-ttu-id="188cd-135">Se o `TestScript` retornar `$false`, o DSC executará o `SetScript` para colocar o nó de volta no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="188cd-135">If `TestScript` returns `$false`, DSC executes `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="188cd-136">Ele deve retornar um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="188cd-136">It must return a boolean value.</span></span> <span data-ttu-id="188cd-137">Um resultado de `$true` indica que o nó está em conformidade, e `SetScript` não deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="188cd-137">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="188cd-138">O cmdlet [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) executa `TestScript` para recuperar a conformidade de nós com os recursos de `Script`.</span><span class="sxs-lookup"><span data-stu-id="188cd-138">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes `TestScript` to retrieve the nodes compliance with the `Script` resources.</span></span> <span data-ttu-id="188cd-139">No entanto, nesse caso, `SetScript` não é executado, não importa o que o bloco `TestScript` retorna.</span><span class="sxs-lookup"><span data-stu-id="188cd-139">However, in this case, `SetScript` does not run, no matter what `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="188cd-140">Toda a saída do seu `TestScript` faz parte de seu valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="188cd-140">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="188cd-141">O PowerShell interpreta a saída não suprimida como diferente de zero, o que significa que seu `TestScript` retornará `$true` independentemente do estado do seu nó.</span><span class="sxs-lookup"><span data-stu-id="188cd-141">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="188cd-142">Isso resulta em resultados imprevisíveis, falsos positivos e causa dificuldades durante a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="188cd-142">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="188cd-143">SetScript</span><span class="sxs-lookup"><span data-stu-id="188cd-143">SetScript</span></span>

<span data-ttu-id="188cd-144">`SetScript` modifica o nó para impor o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="188cd-144">`SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="188cd-145">Ele será chamado pelo DSC se o bloco de script `TestScript` retornar `$false`.</span><span class="sxs-lookup"><span data-stu-id="188cd-145">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="188cd-146">O `SetScript` não deve ter nenhum valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="188cd-146">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="188cd-147">Exemplos</span><span class="sxs-lookup"><span data-stu-id="188cd-147">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="188cd-148">Exemplo 1: Escrever texto de exemplo usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="188cd-148">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="188cd-149">Este exemplo testa a existência de `C:\TempFolder\TestFile.txt` em cada nó.</span><span class="sxs-lookup"><span data-stu-id="188cd-149">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="188cd-150">Se não existir, ele o criará usando o `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="188cd-150">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="188cd-151">O `GetScript` retorna o conteúdo do arquivo, e seu valor de retorno não é usado.</span><span class="sxs-lookup"><span data-stu-id="188cd-151">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="188cd-152">Exemplo 2: Comparar informações de versão usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="188cd-152">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="188cd-153">Este exemplo recupera as informações da versão _compatível_ de um arquivo de texto no computador de criação e as armazenam na variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="188cd-153">This example retrieves the _compliant_ version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="188cd-154">Ao gerar o arquivo MOF do nó, o DSC substitui as variáveis `$using:version` em cada bloco de script pelo valor da variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="188cd-154">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="188cd-155">Durante a execução, a versão _compatível_ é armazenada em um arquivo de texto em cada Node, comparada e atualizada em execuções subsequentes.</span><span class="sxs-lookup"><span data-stu-id="188cd-155">During execution, the _compliant_ version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="188cd-156">Exemplo 3: Utilizar parâmetros em um recurso de script</span><span class="sxs-lookup"><span data-stu-id="188cd-156">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="188cd-157">Este exemplo acessa parâmetros de dentro do recurso de script usando o escopo `using`.</span><span class="sxs-lookup"><span data-stu-id="188cd-157">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span>
<span data-ttu-id="188cd-158">Observe que **ConfigurationData** pode ser acessado de maneira semelhante.</span><span class="sxs-lookup"><span data-stu-id="188cd-158">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="188cd-159">Como o exemplo 2, espera-se que uma versão seja armazenada dentro de um arquivo local no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="188cd-159">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="188cd-160">No entanto, o caminho do arquivo local e a versão são configuráveis, desacoplando o código dos dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="188cd-160">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

<span data-ttu-id="188cd-161">O arquivo MOF resultante inclui as variáveis e seus respectivos valores acessados por meio do escopo `using`.</span><span class="sxs-lookup"><span data-stu-id="188cd-161">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="188cd-162">Eles são injetados em cada bloco de script que usa as variáveis.</span><span class="sxs-lookup"><span data-stu-id="188cd-162">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="188cd-163">Por razões de brevidade, os scripts Test e Set foram removidos:</span><span class="sxs-lookup"><span data-stu-id="188cd-163">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a><span data-ttu-id="188cd-164">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="188cd-164">Known Limitations</span></span>

- <span data-ttu-id="188cd-165">As credenciais que estão sendo passadas dentro de um recurso de script nem sempre são confiáveis ao usar um modelo de servidor de pull ou push.</span><span class="sxs-lookup"><span data-stu-id="188cd-165">Credentials being passed within a script resource are not always reliable when using a pull or push server model.</span></span> <span data-ttu-id="188cd-166">É recomendável usar um recurso completo em vez de um recurso de script nesse caso.</span><span class="sxs-lookup"><span data-stu-id="188cd-166">It is recommended to use a full resource rather than use a script resource in this case.</span></span>
