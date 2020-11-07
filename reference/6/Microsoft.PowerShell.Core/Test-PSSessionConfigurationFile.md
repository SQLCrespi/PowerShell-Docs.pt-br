---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: a5017b7a46e36a8a2c67ad05d3b6606056ded0f1
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343951"
---
# <span data-ttu-id="df2cb-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="df2cb-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="df2cb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="df2cb-104">SYNOPSIS</span></span>
<span data-ttu-id="df2cb-105">Verifica as chaves e os valores em um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="df2cb-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="df2cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df2cb-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="df2cb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df2cb-107">DESCRIPTION</span></span>

<span data-ttu-id="df2cb-108">Esse cmdlet verifica se um arquivo de configuração de sessão contém chaves válidas e se os valores são do tipo correto.</span><span class="sxs-lookup"><span data-stu-id="df2cb-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="df2cb-109">Para valores enumerados, o cmdlet verifica se os valores especificados são válidos.</span><span class="sxs-lookup"><span data-stu-id="df2cb-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="df2cb-110">O cmdlet retornará `$True` se o arquivo passar por todos os testes e se não tiver `$False` .</span><span class="sxs-lookup"><span data-stu-id="df2cb-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="df2cb-111">Para encontrar erros, use o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="df2cb-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="df2cb-112">`Test-PSSessionConfigurationFile` Verifica os arquivos de configuração de sessão, como aqueles criados pelo `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df2cb-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="df2cb-113">Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="df2cb-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="df2cb-114">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="df2cb-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="df2cb-115">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="df2cb-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="df2cb-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="df2cb-116">EXAMPLES</span></span>

### <span data-ttu-id="df2cb-117">Exemplo 1: testar um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="df2cb-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="df2cb-118">Exemplo 2: testar o arquivo de configuração de sessão de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="df2cb-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="df2cb-119">Neste exemplo, testamos o arquivo de configuração usado na configuração de sessão **restrita** .</span><span class="sxs-lookup"><span data-stu-id="df2cb-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="df2cb-120">O valor do parâmetro **path** é o resultado do `Get-PSSessionConfiguration` comando que obtém a configuração de sessão **restrita** .</span><span class="sxs-lookup"><span data-stu-id="df2cb-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="df2cb-121">O caminho do arquivo de configuração de sessão é armazenado no valor da propriedade **ConfigFilePath** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="df2cb-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="df2cb-122">Exemplo 3: testar todos os arquivos de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="df2cb-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="df2cb-123">A função neste exemplo testa todos os arquivos de configuração de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="df2cb-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="df2cb-124">A função usa o `Get-PSSessionConfiguration` cmdlet para obter todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="df2cb-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="df2cb-125">O código dentro do `ForEach-Object` loop exibe o caminho do arquivo e testa cada uma das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="df2cb-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="df2cb-126">A propriedade **ConfigFilePath** de uma configuração de sessão contém o caminho do arquivo de configuração de sessão que é usado na configuração da sessão, se houver.</span><span class="sxs-lookup"><span data-stu-id="df2cb-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="df2cb-127">Se o valor da propriedade **ConfigFilePath** estiver preenchido (é verdadeiro), o comando obtém (imprime) o valor da propriedade **ConfigFilePath**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="df2cb-128">Em seguida, ele usa o `Test-PSSessionConfigurationFile` cmdlet para testar o arquivo no valor **ConfigFilePath** .</span><span class="sxs-lookup"><span data-stu-id="df2cb-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="df2cb-129">O parâmetro **Verbose** retorna o erro de arquivo quando o arquivo falha no teste.</span><span class="sxs-lookup"><span data-stu-id="df2cb-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="df2cb-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df2cb-130">PARAMETERS</span></span>

### <span data-ttu-id="df2cb-131">-Path</span><span class="sxs-lookup"><span data-stu-id="df2cb-131">-Path</span></span>

<span data-ttu-id="df2cb-132">Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="df2cb-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="df2cb-133">Se você omitir o caminho, o padrão será a pasta atual.</span><span class="sxs-lookup"><span data-stu-id="df2cb-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="df2cb-134">Há suporte para caracteres curinga, mas eles devem ser resolvidos para um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="df2cb-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="df2cb-135">Também é possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="df2cb-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="df2cb-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="df2cb-136">CommonParameters</span></span>

<span data-ttu-id="df2cb-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="df2cb-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df2cb-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="df2cb-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df2cb-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="df2cb-139">INPUTS</span></span>

### <span data-ttu-id="df2cb-140">System.String</span><span class="sxs-lookup"><span data-stu-id="df2cb-140">System.String</span></span>

<span data-ttu-id="df2cb-141">É possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="df2cb-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="df2cb-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="df2cb-142">OUTPUTS</span></span>

### <span data-ttu-id="df2cb-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="df2cb-143">System.Boolean</span></span>

## <span data-ttu-id="df2cb-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="df2cb-144">NOTES</span></span>

<span data-ttu-id="df2cb-145">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="df2cb-145">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="df2cb-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="df2cb-146">RELATED LINKS</span></span>

[<span data-ttu-id="df2cb-147">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-147">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-148">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-148">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-149">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-149">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-150">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="df2cb-150">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="df2cb-151">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="df2cb-151">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="df2cb-152">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-152">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-153">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-153">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-154">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="df2cb-154">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="df2cb-155">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="df2cb-155">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="df2cb-156">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="df2cb-156">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="df2cb-157">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="df2cb-157">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="df2cb-158">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="df2cb-158">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
