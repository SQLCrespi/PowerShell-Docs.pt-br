---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Script de DSC
ms.openlocfilehash: 50d4667396c8c619079288ec51599152ed2d6cd5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557015"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="bb8b6-103">Recurso Script de DSC</span><span class="sxs-lookup"><span data-stu-id="bb8b6-103">DSC Script Resource</span></span>

> <span data-ttu-id="bb8b6-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="bb8b6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="bb8b6-105">O recurso **Script** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para executar blocos de script do Windows PowerShell em nós de destino.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="bb8b6-106">O recurso **Script** usa as propriedades **GetScript**, **SetScript** e **TestScript** que contêm blocos de script definidos para executar as operações de estado de DSC correspondentes.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-106">The **Script** resource uses **GetScript**, **SetScript**, and **TestScript** properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb8b6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bb8b6-107">Syntax</span></span>

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
> <span data-ttu-id="bb8b6-108">Os blocos **GetScript**, **TestScript** e **SetScript** são armazenados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-108">**GetScript**, **TestScript**, and **SetScript** blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="bb8b6-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="bb8b6-109">Properties</span></span>

|<span data-ttu-id="bb8b6-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bb8b6-110">Property</span></span> |<span data-ttu-id="bb8b6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb8b6-111">Description</span></span> |
|---|---|
|<span data-ttu-id="bb8b6-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-112">GetScript</span></span> |<span data-ttu-id="bb8b6-113">Um bloco de script que retorna o estado atual do Node.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-113">A script block that returns the current state of the Node.</span></span> |
|<span data-ttu-id="bb8b6-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-114">SetScript</span></span> |<span data-ttu-id="bb8b6-115">Um bloco de script usado pelo DSC para impor a conformidade quando o Node não estiver no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
|<span data-ttu-id="bb8b6-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-116">TestScript</span></span> |<span data-ttu-id="bb8b6-117">Um bloco de script que determina se o Node está no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-117">A script block that determines if the Node is in the desired state.</span></span> |
|<span data-ttu-id="bb8b6-118">Credencial</span><span class="sxs-lookup"><span data-stu-id="bb8b6-118">Credential</span></span> |<span data-ttu-id="bb8b6-119">Indica as credenciais que devem ser usadas para executar esse script, caso sejam necessárias.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-119">Indicates the credentials to use for running this script, if credentials are required.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="bb8b6-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="bb8b6-120">Common properties</span></span>

|<span data-ttu-id="bb8b6-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bb8b6-121">Property</span></span> |<span data-ttu-id="bb8b6-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb8b6-122">Description</span></span> |
|---|---|
|<span data-ttu-id="bb8b6-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="bb8b6-123">DependsOn</span></span> |<span data-ttu-id="bb8b6-124">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="bb8b6-125">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="bb8b6-126">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="bb8b6-126">PsDscRunAsCredential</span></span> |<span data-ttu-id="bb8b6-127">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-127">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="bb8b6-128">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-128">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="bb8b6-129">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="bb8b6-129">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="bb8b6-130">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="bb8b6-130">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="bb8b6-131">GetScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-131">GetScript</span></span>

<span data-ttu-id="bb8b6-132">O DSC não usa a saída do **GetScript**.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-132">DSC does not use the output from **GetScript**.</span></span> <span data-ttu-id="bb8b6-133">O cmdlet [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) executa o **GetScript** para recuperar o estado atual do nó.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-133">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes **GetScript** to retrieve a node's current state.</span></span> <span data-ttu-id="bb8b6-134">**GetScript** não exige um valor retornado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-134">A return value is not required from **GetScript**.</span></span> <span data-ttu-id="bb8b6-135">Se você especificar um valor retornado, ele deverá ser uma tabela de hash que contenha uma chave **Result** cujo valor seja uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-135">If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="bb8b6-136">TestScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-136">TestScript</span></span>

<span data-ttu-id="bb8b6-137">O **TestScript** é executado pelo DSC para determinar se o **SetScript** deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-137">**TestScript** is executed by DSC to determine if **SetScript** should be run.</span></span> <span data-ttu-id="bb8b6-138">Se o **TestScript** retornar `$false`, o DSC executará o **SetScript** para colocar o nó de volta no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-138">If **TestScript** returns `$false`, DSC executes **SetScript** to bring the node back to the desired state.</span></span> <span data-ttu-id="bb8b6-139">Ele deve retornar um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-139">It must return a boolean value.</span></span> <span data-ttu-id="bb8b6-140">Um resultado de `$true` indica que o nó está em conformidade e **SetScript** não deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-140">A result of `$true` indicates that the node is compliant and **SetScript** should not executed.</span></span>

<span data-ttu-id="bb8b6-141">O cmdlet [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) executa **TestScript** para recuperar a conformidade de nós com os recursos de **Script**.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-141">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes **TestScript** to retrieve the nodes compliance with the **Script** resources.</span></span>
<span data-ttu-id="bb8b6-142">No entanto, nesse caso, **SetScript** não é executado, não importa o que o bloco **TestScript** retorna.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-142">However, in this case, **SetScript** does not run, no matter what **TestScript** block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="bb8b6-143">Toda a saída do **TestScript** faz parte de seu valor retornado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-143">All output from your **TestScript** is part of its return value.</span></span> <span data-ttu-id="bb8b6-144">O PowerShell interpreta a saída não suprimida como diferente de zero, o que significa que o **TestScript** retornará `$true` independentemente do estado do nó.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-144">PowerShell interprets unsuppressed output as non-zero, which means that your **TestScript** will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="bb8b6-145">Isso resulta em resultados imprevisíveis, falsos positivos e causa dificuldades durante a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-145">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="bb8b6-146">SetScript</span><span class="sxs-lookup"><span data-stu-id="bb8b6-146">SetScript</span></span>

<span data-ttu-id="bb8b6-147">**SetScript** modifica o nó para impor o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-147">**SetScript** modifies the node to enforce the desired state.</span></span> <span data-ttu-id="bb8b6-148">Ele será chamado pelo DSC se o bloco de script **TestScript** retornar `$false`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-148">It is called by DSC if the **TestScript** script block returns `$false`.</span></span> <span data-ttu-id="bb8b6-149">O **SetScript** não deve ter nenhum valor retornado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-149">The **SetScript** should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="bb8b6-150">Exemplos</span><span class="sxs-lookup"><span data-stu-id="bb8b6-150">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="bb8b6-151">Exemplo 1: Escrever texto de exemplo usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="bb8b6-151">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="bb8b6-152">Este exemplo testa a existência de `C:\TempFolder\TestFile.txt` em cada nó.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-152">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="bb8b6-153">Se não existir, ele o criará usando o `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-153">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="bb8b6-154">O `GetScript` retorna o conteúdo do arquivo, e seu valor de retorno não é usado.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-154">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="bb8b6-155">Exemplo 2: Comparar informações de versão usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="bb8b6-155">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="bb8b6-156">Este exemplo recupera as informações da versão *compatível* de um arquivo de texto no computador de criação e as armazenam na variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-156">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="bb8b6-157">Ao gerar o arquivo MOF do nó, o DSC substitui as variáveis `$using:version` em cada bloco de script pelo valor da variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-157">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="bb8b6-158">Durante a execução, a versão *compatível* é armazenada em um arquivo de texto em cada Node, comparada e atualizada em execuções subsequentes.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-158">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

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

                if( $state['Result'] -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
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

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="bb8b6-159">Exemplo 3: Utilizar parâmetros em um recurso de script</span><span class="sxs-lookup"><span data-stu-id="bb8b6-159">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="bb8b6-160">Este exemplo acessa parâmetros de dentro do recurso de script usando o escopo `using`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-160">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span> <span data-ttu-id="bb8b6-161">Observe que **ConfigurationData** pode ser acessado de maneira semelhante.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-161">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="bb8b6-162">Como o exemplo 2, espera-se que uma versão seja armazenada dentro de um arquivo local no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-162">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="bb8b6-163">No entanto, o caminho do arquivo local e a versão são configuráveis, desacoplando o código dos dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-163">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

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

<span data-ttu-id="bb8b6-164">O arquivo MOF resultante inclui as variáveis e seus respectivos valores acessados por meio do escopo `using`.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-164">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="bb8b6-165">Eles são injetados em cada bloco de script que usa as variáveis.</span><span class="sxs-lookup"><span data-stu-id="bb8b6-165">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="bb8b6-166">Por razões de brevidade, os scripts Test e Set foram removidos:</span><span class="sxs-lookup"><span data-stu-id="bb8b6-166">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```
