---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: c6d6d305b283522215d43b7339683b1617a85804
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596809"
---
# <span data-ttu-id="8ba3e-102">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8ba3e-102">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="8ba3e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8ba3e-103">SYNOPSIS</span></span>
<span data-ttu-id="8ba3e-104">Verifica as chaves e os valores em um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-104">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="8ba3e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ba3e-105">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="8ba3e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ba3e-106">DESCRIPTION</span></span>

<span data-ttu-id="8ba3e-107">Esse cmdlet verifica se um arquivo de configuração de sessão contém chaves válidas e se os valores são do tipo correto.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-107">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="8ba3e-108">Para valores enumerados, o cmdlet verifica se os valores especificados são válidos.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-108">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="8ba3e-109">O cmdlet retornará `$True` se o arquivo passar por todos os testes e se não tiver `$False` .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-109">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="8ba3e-110">Para encontrar erros, use o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-110">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="8ba3e-111">`Test-PSSessionConfigurationFile` Verifica os arquivos de configuração de sessão, como aqueles criados pelo `New-PSSessionConfigurationFile` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-111">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="8ba3e-112">Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8ba3e-112">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="8ba3e-113">Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="8ba3e-113">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="8ba3e-114">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="8ba3e-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8ba3e-115">EXAMPLES</span></span>

### <span data-ttu-id="8ba3e-116">Exemplo 1: testar um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="8ba3e-116">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="8ba3e-117">Exemplo 2: testar o arquivo de configuração de sessão de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="8ba3e-117">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="8ba3e-118">Neste exemplo, testamos o arquivo de configuração usado na configuração de sessão **restrita** .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-118">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="8ba3e-119">O valor do parâmetro **path** é o resultado do `Get-PSSessionConfiguration` comando que obtém a configuração de sessão **restrita** .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-119">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="8ba3e-120">O caminho do arquivo de configuração de sessão é armazenado no valor da propriedade **ConfigFilePath** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-120">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="8ba3e-121">Exemplo 3: testar todos os arquivos de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="8ba3e-121">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="8ba3e-122">A função neste exemplo testa todos os arquivos de configuração de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-122">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="8ba3e-123">A função usa o `Get-PSSessionConfiguration` cmdlet para obter todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-123">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="8ba3e-124">O código dentro do `ForEach-Object` loop exibe o caminho do arquivo e testa cada uma das configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-124">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

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

<span data-ttu-id="8ba3e-125">A propriedade **ConfigFilePath** de uma configuração de sessão contém o caminho do arquivo de configuração de sessão que é usado na configuração da sessão, se houver.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-125">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="8ba3e-126">Se o valor da propriedade **ConfigFilePath** estiver preenchido (é verdadeiro), o comando obtém (imprime) o valor da propriedade **ConfigFilePath**.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-126">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="8ba3e-127">Em seguida, ele usa o `Test-PSSessionConfigurationFile` cmdlet para testar o arquivo no valor **ConfigFilePath** .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-127">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="8ba3e-128">O parâmetro **Verbose** retorna o erro de arquivo quando o arquivo falha no teste.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-128">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="8ba3e-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ba3e-129">PARAMETERS</span></span>

### <span data-ttu-id="8ba3e-130">-Path</span><span class="sxs-lookup"><span data-stu-id="8ba3e-130">-Path</span></span>

<span data-ttu-id="8ba3e-131">Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="8ba3e-131">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="8ba3e-132">Se você omitir o caminho, o padrão será a pasta atual.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-132">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="8ba3e-133">Há suporte para caracteres curinga, mas eles devem ser resolvidos para um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-133">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="8ba3e-134">Também é possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-134">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

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

### <span data-ttu-id="8ba3e-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8ba3e-135">CommonParameters</span></span>

<span data-ttu-id="8ba3e-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ba3e-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ba3e-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ba3e-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8ba3e-138">INPUTS</span></span>

### <span data-ttu-id="8ba3e-139">System.String</span><span class="sxs-lookup"><span data-stu-id="8ba3e-139">System.String</span></span>

<span data-ttu-id="8ba3e-140">É possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="8ba3e-140">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="8ba3e-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8ba3e-141">OUTPUTS</span></span>

### <span data-ttu-id="8ba3e-142">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="8ba3e-142">System.Boolean</span></span>

## <span data-ttu-id="8ba3e-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8ba3e-143">NOTES</span></span>

<span data-ttu-id="8ba3e-144">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="8ba3e-144">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="8ba3e-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8ba3e-145">RELATED LINKS</span></span>

[<span data-ttu-id="8ba3e-146">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-146">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-147">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-147">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-148">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-148">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-149">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8ba3e-149">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="8ba3e-150">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="8ba3e-150">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="8ba3e-151">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-151">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-152">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-152">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-153">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8ba3e-153">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="8ba3e-154">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ba3e-154">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="8ba3e-155">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="8ba3e-155">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="8ba3e-156">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8ba3e-156">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="8ba3e-157">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="8ba3e-157">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
