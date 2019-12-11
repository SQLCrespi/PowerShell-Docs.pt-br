---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Script de DSC
ms.openlocfilehash: e09e86011fa7dbb2a4d7f28b5032b4328b6f6ec2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953063"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="eebe7-103">Recurso Script de DSC</span><span class="sxs-lookup"><span data-stu-id="eebe7-103">DSC Script Resource</span></span>

> <span data-ttu-id="eebe7-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="eebe7-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="eebe7-105">O recurso **Script** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para executar blocos de script do Windows PowerShell em nós de destino.</span><span class="sxs-lookup"><span data-stu-id="eebe7-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="eebe7-106">O recurso **Script** usa as propriedades **GetScript**, **SetScript** e **TestScript** que contêm blocos de script definidos para executar as operações de estado de DSC correspondentes.</span><span class="sxs-lookup"><span data-stu-id="eebe7-106">The **Script** resource uses **GetScript**, **SetScript**, and **TestScript** properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="eebe7-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eebe7-107">Syntax</span></span>

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
> <span data-ttu-id="eebe7-108">Os blocos **GetScript**, **TestScript** e **SetScript** são armazenados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eebe7-108">**GetScript**, **TestScript**, and **SetScript** blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="eebe7-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="eebe7-109">Properties</span></span>

|<span data-ttu-id="eebe7-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="eebe7-110">Property</span></span> |<span data-ttu-id="eebe7-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="eebe7-111">Description</span></span> |
|---|---|
|<span data-ttu-id="eebe7-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-112">GetScript</span></span> |<span data-ttu-id="eebe7-113">Um bloco de script que retorna o estado atual do Node.</span><span class="sxs-lookup"><span data-stu-id="eebe7-113">A script block that returns the current state of the Node.</span></span> |
|<span data-ttu-id="eebe7-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-114">SetScript</span></span> |<span data-ttu-id="eebe7-115">Um bloco de script usado pelo DSC para impor a conformidade quando o Node não estiver no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
|<span data-ttu-id="eebe7-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-116">TestScript</span></span> |<span data-ttu-id="eebe7-117">Um bloco de script que determina se o Node está no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-117">A script block that determines if the Node is in the desired state.</span></span> |
|<span data-ttu-id="eebe7-118">Credential</span><span class="sxs-lookup"><span data-stu-id="eebe7-118">Credential</span></span> |<span data-ttu-id="eebe7-119">Indica as credenciais que devem ser usadas para executar esse script, caso sejam necessárias.</span><span class="sxs-lookup"><span data-stu-id="eebe7-119">Indicates the credentials to use for running this script, if credentials are required.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="eebe7-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="eebe7-120">Common properties</span></span>

|<span data-ttu-id="eebe7-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="eebe7-121">Property</span></span> |<span data-ttu-id="eebe7-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="eebe7-122">Description</span></span> |
|---|---|
|<span data-ttu-id="eebe7-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="eebe7-123">DependsOn</span></span> |<span data-ttu-id="eebe7-124">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="eebe7-125">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="eebe7-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="eebe7-126">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="eebe7-126">PsDscRunAsCredential</span></span> |<span data-ttu-id="eebe7-127">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="eebe7-127">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="eebe7-128">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="eebe7-128">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="eebe7-129">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="eebe7-129">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="eebe7-130">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="eebe7-130">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="eebe7-131">GetScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-131">GetScript</span></span>

<span data-ttu-id="eebe7-132">O DSC não usa a saída do **GetScript**.</span><span class="sxs-lookup"><span data-stu-id="eebe7-132">DSC does not use the output from **GetScript**.</span></span> <span data-ttu-id="eebe7-133">O cmdlet [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) executa o **GetScript** para recuperar o estado atual do nó.</span><span class="sxs-lookup"><span data-stu-id="eebe7-133">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes **GetScript** to retrieve a node's current state.</span></span> <span data-ttu-id="eebe7-134">**GetScript** não exige um valor retornado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-134">A return value is not required from **GetScript**.</span></span> <span data-ttu-id="eebe7-135">Se você especificar um valor retornado, ele deverá ser uma tabela de hash que contenha uma chave **Result** cujo valor seja uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eebe7-135">If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="eebe7-136">TestScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-136">TestScript</span></span>

<span data-ttu-id="eebe7-137">O **TestScript** é executado pelo DSC para determinar se o **SetScript** deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-137">**TestScript** is executed by DSC to determine if **SetScript** should be run.</span></span> <span data-ttu-id="eebe7-138">Se o **TestScript** retornar `$false`, o DSC executará o **SetScript** para colocar o nó de volta no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-138">If **TestScript** returns `$false`, DSC executes **SetScript** to bring the node back to the desired state.</span></span> <span data-ttu-id="eebe7-139">Ele deve retornar um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eebe7-139">It must return a boolean value.</span></span> <span data-ttu-id="eebe7-140">Um resultado de `$true` indica que o nó está em conformidade e **SetScript** não deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-140">A result of `$true` indicates that the node is compliant and **SetScript** should not executed.</span></span>

<span data-ttu-id="eebe7-141">O cmdlet [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) executa **TestScript** para recuperar a conformidade de nós com os recursos de **Script**.</span><span class="sxs-lookup"><span data-stu-id="eebe7-141">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes **TestScript** to retrieve the nodes compliance with the **Script** resources.</span></span>
<span data-ttu-id="eebe7-142">No entanto, nesse caso, **SetScript** não é executado, não importa o que o bloco **TestScript** retorna.</span><span class="sxs-lookup"><span data-stu-id="eebe7-142">However, in this case, **SetScript** does not run, no matter what **TestScript** block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="eebe7-143">Toda a saída do **TestScript** faz parte de seu valor retornado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-143">All output from your **TestScript** is part of its return value.</span></span> <span data-ttu-id="eebe7-144">O PowerShell interpreta a saída não suprimida como diferente de zero, o que significa que o **TestScript** retornará `$true` independentemente do estado do nó.</span><span class="sxs-lookup"><span data-stu-id="eebe7-144">PowerShell interprets unsuppressed output as non-zero, which means that your **TestScript** will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="eebe7-145">Isso resulta em resultados imprevisíveis, falsos positivos e causa dificuldades durante a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="eebe7-145">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="eebe7-146">SetScript</span><span class="sxs-lookup"><span data-stu-id="eebe7-146">SetScript</span></span>

<span data-ttu-id="eebe7-147">**SetScript** modifica o nó para impor o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-147">**SetScript** modifies the node to enforce the desired state.</span></span> <span data-ttu-id="eebe7-148">Ele será chamado pelo DSC se o bloco de script **TestScript** retornar `$false`.</span><span class="sxs-lookup"><span data-stu-id="eebe7-148">It is called by DSC if the **TestScript** script block returns `$false`.</span></span> <span data-ttu-id="eebe7-149">O **SetScript** não deve ter nenhum valor retornado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-149">The **SetScript** should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="eebe7-150">Exemplos</span><span class="sxs-lookup"><span data-stu-id="eebe7-150">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="eebe7-151">Exemplo 1: Escrever texto de exemplo usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="eebe7-151">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="eebe7-152">Este exemplo testa a existência de `C:\TempFolder\TestFile.txt` em cada nó.</span><span class="sxs-lookup"><span data-stu-id="eebe7-152">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="eebe7-153">Se não existir, ele o criará usando o `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="eebe7-153">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="eebe7-154">O `GetScript` retorna o conteúdo do arquivo, e seu valor de retorno não é usado.</span><span class="sxs-lookup"><span data-stu-id="eebe7-154">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="eebe7-155">Exemplo 2: Comparar informações de versão usando um recurso de Script</span><span class="sxs-lookup"><span data-stu-id="eebe7-155">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="eebe7-156">Este exemplo recupera as informações da versão *compatível* de um arquivo de texto no computador de criação e as armazenam na variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="eebe7-156">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="eebe7-157">Ao gerar o arquivo MOF do nó, o DSC substitui as variáveis `$using:version` em cada bloco de script pelo valor da variável `$version`.</span><span class="sxs-lookup"><span data-stu-id="eebe7-157">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="eebe7-158">Durante a execução, a versão *compatível* é armazenada em um arquivo de texto em cada Node, comparada e atualizada em execuções subsequentes.</span><span class="sxs-lookup"><span data-stu-id="eebe7-158">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

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