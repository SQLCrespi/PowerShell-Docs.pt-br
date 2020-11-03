---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: fcfb974a360c450f474ba97d65190b019860d8c4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192961"
---
# <span data-ttu-id="441a6-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-103">Test-Path</span></span>

## <span data-ttu-id="441a6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="441a6-104">SYNOPSIS</span></span>
<span data-ttu-id="441a6-105">Determina se todos os elementos de um caminho existem ou não.</span><span class="sxs-lookup"><span data-stu-id="441a6-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="441a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="441a6-106">SYNTAX</span></span>

### <span data-ttu-id="441a6-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="441a6-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="441a6-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="441a6-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="441a6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="441a6-109">DESCRIPTION</span></span>

<span data-ttu-id="441a6-110">O `Test-Path` cmdlet determina se todos os elementos do caminho existem.</span><span class="sxs-lookup"><span data-stu-id="441a6-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="441a6-111">Ele retornará `$True` se todos os elementos existirem e `$False` se algum estiver ausente.</span><span class="sxs-lookup"><span data-stu-id="441a6-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="441a6-112">Ele também pode informar se a sintaxe do caminho é válida e se o caminho leva a um contêiner ou a um elemento de terminal ou folha.</span><span class="sxs-lookup"><span data-stu-id="441a6-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="441a6-113">Se o `Path` for um espaço em branco uma cadeia de caracteres vazia, `$False` será retornado.</span><span class="sxs-lookup"><span data-stu-id="441a6-113">If the `Path` is whitespace an empty string, then `$False` is returned.</span></span> <span data-ttu-id="441a6-114">Se `Path` for `$null` , matriz ou matriz `$null` vazia, um erro de não finalização será retornado.</span><span class="sxs-lookup"><span data-stu-id="441a6-114">If the `Path` is `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="441a6-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="441a6-115">EXAMPLES</span></span>

### <span data-ttu-id="441a6-116">Exemplo 1: testar um caminho</span><span class="sxs-lookup"><span data-stu-id="441a6-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="441a6-117">Esse comando verifica se todos os elementos no caminho existem, ou seja, o diretório C:, o diretório Documents and Settings e o diretório DavidC</span><span class="sxs-lookup"><span data-stu-id="441a6-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="441a6-118">Se algum estiver faltando, o cmdlet retornará `$False` .</span><span class="sxs-lookup"><span data-stu-id="441a6-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="441a6-119">Caso contrário, retornará `$True`.</span><span class="sxs-lookup"><span data-stu-id="441a6-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="441a6-120">Exemplo 2: testar o caminho de um perfil</span><span class="sxs-lookup"><span data-stu-id="441a6-120">Example 2: Test the path of a profile</span></span>

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

<span data-ttu-id="441a6-121">Esses comandos testam o caminho do perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="441a6-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="441a6-122">O primeiro comando determina se todos os elementos no caminho existem.</span><span class="sxs-lookup"><span data-stu-id="441a6-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="441a6-123">O segundo comando determina se a sintaxe do caminho está correta.</span><span class="sxs-lookup"><span data-stu-id="441a6-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="441a6-124">Nesse caso, o caminho é `$False` , mas a sintaxe está correta `$True` .</span><span class="sxs-lookup"><span data-stu-id="441a6-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="441a6-125">Esses comandos usam `$profile` , a variável automática que aponta para o local do perfil, mesmo que o perfil não exista.</span><span class="sxs-lookup"><span data-stu-id="441a6-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="441a6-126">Para obter mais informações sobre variáveis automáticas, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="441a6-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="441a6-127">Exemplo 3: verificar se há arquivos além de um tipo especificado</span><span class="sxs-lookup"><span data-stu-id="441a6-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="441a6-128">Esse comando verifica se há arquivos no diretório prédios comerciais que não sejam arquivos. dwg.</span><span class="sxs-lookup"><span data-stu-id="441a6-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="441a6-129">O comando usa o parâmetro **path** para especificar o caminho.</span><span class="sxs-lookup"><span data-stu-id="441a6-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="441a6-130">Como o caminho inclui um espaço, o caminho é colocado entre aspas.</span><span class="sxs-lookup"><span data-stu-id="441a6-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="441a6-131">O asterisco no final do caminho indica o conteúdo do diretório Prédios comerciais.</span><span class="sxs-lookup"><span data-stu-id="441a6-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="441a6-132">Com caminhos longos, como este, digite as primeiras letras do caminho e, em seguida, use a tecla TAB para concluir o caminho.</span><span class="sxs-lookup"><span data-stu-id="441a6-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="441a6-133">O comando especifica o parâmetro **Exclude** para especificar os arquivos que serão omitidos da avaliação.</span><span class="sxs-lookup"><span data-stu-id="441a6-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="441a6-134">Nesse caso, como o diretório contém apenas arquivos. dwg, o resultado é `$False` .</span><span class="sxs-lookup"><span data-stu-id="441a6-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="441a6-135">Exemplo 4: verificar se há um arquivo</span><span class="sxs-lookup"><span data-stu-id="441a6-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="441a6-136">Esse comando verifica se o caminho armazenado na `$profile` variável leva a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="441a6-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="441a6-137">Nesse caso, como o perfil do PowerShell é um `.ps1` arquivo, o cmdlet retorna `$True` .</span><span class="sxs-lookup"><span data-stu-id="441a6-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="441a6-138">Exemplo 5: verificar caminhos no registro</span><span class="sxs-lookup"><span data-stu-id="441a6-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="441a6-139">Esses comandos usam `Test-Path` com o provedor de registro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="441a6-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="441a6-140">O primeiro comando testa se o caminho do registro da chave do registro **Microsoft. PowerShell** está correto no sistema.</span><span class="sxs-lookup"><span data-stu-id="441a6-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="441a6-141">Se o PowerShell for instalado corretamente, o cmdlet retornará `$True` .</span><span class="sxs-lookup"><span data-stu-id="441a6-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="441a6-142">`Test-Path` Não funciona corretamente com todos os provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="441a6-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="441a6-143">Por exemplo, você pode usar `Test-Path` o para testar o caminho de uma chave do registro, mas se você usá-la para testar o caminho de uma entrada do registro, ela sempre retornará `$False` , mesmo que a entrada do registro esteja presente.</span><span class="sxs-lookup"><span data-stu-id="441a6-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### <span data-ttu-id="441a6-144">Exemplo 6: testar se um arquivo é mais novo do que uma data especificada</span><span class="sxs-lookup"><span data-stu-id="441a6-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="441a6-145">Esse comando usa o parâmetro dinâmico **NewerThan** para determinar se o arquivo "PowerShell.exe" no computador é mais recente do que "13 de julho de 2009".</span><span class="sxs-lookup"><span data-stu-id="441a6-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="441a6-146">O parâmetro NewerThan funciona apenas em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="441a6-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="441a6-147">Exemplo 7: testar um caminho com NULL como o valor</span><span class="sxs-lookup"><span data-stu-id="441a6-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="441a6-148">O erro retornado para `null` , matriz `null` ou matriz vazia é um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="441a6-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="441a6-149">Ele pode ser suprimido usando `-ErrorAction SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="441a6-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="441a6-150">O exemplo a seguir mostra todos os casos que retornam o `NullPathNotPermitted` erro.</span><span class="sxs-lookup"><span data-stu-id="441a6-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### <span data-ttu-id="441a6-151">Exemplo 8: testar um caminho com espaço em branco como o valor</span><span class="sxs-lookup"><span data-stu-id="441a6-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="441a6-152">Quando um espaço em branco ou uma cadeia de caracteres vazia é fornecido para o `-Path` parâmetro, ele retorna **false** .</span><span class="sxs-lookup"><span data-stu-id="441a6-152">When a whitespace or empty string is provided for the the `-Path` parameter, it returns **False** .</span></span>
<span data-ttu-id="441a6-153">O exemplo a seguir mostra o espaço em branco e a cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="441a6-153">The following example show whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## <span data-ttu-id="441a6-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="441a6-154">PARAMETERS</span></span>

### <span data-ttu-id="441a6-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="441a6-155">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="441a6-156">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="441a6-156">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="441a6-157">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="441a6-157">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-158">-Excluir</span><span class="sxs-lookup"><span data-stu-id="441a6-158">-Exclude</span></span>

<span data-ttu-id="441a6-159">Especifica os itens que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="441a6-159">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="441a6-160">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="441a6-160">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="441a6-161">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="441a6-161">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="441a6-162">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="441a6-162">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="441a6-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="441a6-163">-Filter</span></span>

<span data-ttu-id="441a6-164">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="441a6-164">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="441a6-165">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="441a6-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="441a6-166">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="441a6-166">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="441a6-167">Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica quando recupera os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="441a6-167">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="441a6-168">-Incluir</span><span class="sxs-lookup"><span data-stu-id="441a6-168">-Include</span></span>

<span data-ttu-id="441a6-169">Especifica os caminhos que este cmdlet testa.</span><span class="sxs-lookup"><span data-stu-id="441a6-169">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="441a6-170">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="441a6-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="441a6-171">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="441a6-171">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="441a6-172">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="441a6-172">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="441a6-173">-IsValid</span><span class="sxs-lookup"><span data-stu-id="441a6-173">-IsValid</span></span>

<span data-ttu-id="441a6-174">Indica que esse cmdlet testa a sintaxe do caminho, independentemente se os elementos do caminho existem.</span><span class="sxs-lookup"><span data-stu-id="441a6-174">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="441a6-175">Esse cmdlet retornará `$True` se a sintaxe do caminho for válida e `$False` se não for.</span><span class="sxs-lookup"><span data-stu-id="441a6-175">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="441a6-176">-LiteralPath</span></span>

<span data-ttu-id="441a6-177">Especifica um caminho a ser testado.</span><span class="sxs-lookup"><span data-stu-id="441a6-177">Specifies a path to be tested.</span></span> <span data-ttu-id="441a6-178">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="441a6-178">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="441a6-179">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="441a6-179">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="441a6-180">Se o caminho incluir caracteres que poderiam ser interpretados pelo PowerShell como sequências de escape, você deverá colocar o caminho entre aspas simples para que eles não sejam interpretados.</span><span class="sxs-lookup"><span data-stu-id="441a6-180">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-181">-NewerThan</span><span class="sxs-lookup"><span data-stu-id="441a6-181">-NewerThan</span></span>

<span data-ttu-id="441a6-182">Especifique uma hora como um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="441a6-182">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-183">-OlderThan</span><span class="sxs-lookup"><span data-stu-id="441a6-183">-OlderThan</span></span>

<span data-ttu-id="441a6-184">Especifique uma hora como um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="441a6-184">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-185">-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-185">-Path</span></span>

<span data-ttu-id="441a6-186">Especifica um caminho a ser testado.</span><span class="sxs-lookup"><span data-stu-id="441a6-186">Specifies a path to be tested.</span></span> <span data-ttu-id="441a6-187">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="441a6-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="441a6-188">Se o caminho incluir espaços, coloque-os entre aspas.</span><span class="sxs-lookup"><span data-stu-id="441a6-188">If the path includes spaces, enclose it in quotation marks.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="441a6-189">-PathType</span><span class="sxs-lookup"><span data-stu-id="441a6-189">-PathType</span></span>

<span data-ttu-id="441a6-190">Especifica o tipo do elemento final no caminho.</span><span class="sxs-lookup"><span data-stu-id="441a6-190">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="441a6-191">Esse cmdlet retorna `$True` se o elemento for do tipo especificado e `$False` se não for.</span><span class="sxs-lookup"><span data-stu-id="441a6-191">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="441a6-192">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="441a6-192">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="441a6-193">Contêiner.</span><span class="sxs-lookup"><span data-stu-id="441a6-193">Container.</span></span>
  <span data-ttu-id="441a6-194">Um elemento que contém outros elementos, como um diretório ou chave do registro.</span><span class="sxs-lookup"><span data-stu-id="441a6-194">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="441a6-195">Chapa.</span><span class="sxs-lookup"><span data-stu-id="441a6-195">Leaf.</span></span>
  <span data-ttu-id="441a6-196">Um elemento que não contém outros elementos, como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="441a6-196">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="441a6-197">Outro.</span><span class="sxs-lookup"><span data-stu-id="441a6-197">Any.</span></span>
  <span data-ttu-id="441a6-198">Pode ser tanto um contêiner quanto uma folha.</span><span class="sxs-lookup"><span data-stu-id="441a6-198">Either a container or a leaf.</span></span>

<span data-ttu-id="441a6-199">Indica se o elemento final no caminho é ou não de um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="441a6-199">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="441a6-200">Até o PowerShell versão 6.1.2, quando as opções **IsValid** e **PathType** são especificadas juntas, o `Test-Path` cmdlet ignora a opção **PathType** e valida o caminho sintático sem validar o tipo de caminho.</span><span class="sxs-lookup"><span data-stu-id="441a6-200">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="441a6-201">De acordo com o [problema #8607](https://github.com/PowerShell/PowerShell/issues/8607), corrigir esse comportamento pode ser uma alteração significativa em uma versão futura, em que as opções **IsValid** e **PathType** pertencem a conjuntos de parâmetros separados e, portanto, não podem ser usadas em conjunto, evitando essa confusão.</span><span class="sxs-lookup"><span data-stu-id="441a6-201">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="441a6-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="441a6-202">CommonParameters</span></span>

<span data-ttu-id="441a6-203">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="441a6-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="441a6-204">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="441a6-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="441a6-205">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="441a6-205">INPUTS</span></span>

### <span data-ttu-id="441a6-206">System.String</span><span class="sxs-lookup"><span data-stu-id="441a6-206">System.String</span></span>

<span data-ttu-id="441a6-207">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="441a6-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="441a6-208">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="441a6-208">OUTPUTS</span></span>

### <span data-ttu-id="441a6-209">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="441a6-209">System.Boolean</span></span>

<span data-ttu-id="441a6-210">O cmdlet retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="441a6-210">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="441a6-211">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="441a6-211">NOTES</span></span>

<span data-ttu-id="441a6-212">Os cmdlets que contêm o substantivo de **caminho** (os cmdlets de **caminho** ) funcionam com nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar.</span><span class="sxs-lookup"><span data-stu-id="441a6-212">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="441a6-213">Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="441a6-213">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="441a6-214">Use-os como usaria **dirname** , **Normpath** , **realpath** , **Join** ou outros manipuladores de caminho.</span><span class="sxs-lookup"><span data-stu-id="441a6-214">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="441a6-215">O `Test-Path` é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="441a6-215">The `Test-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="441a6-216">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="441a6-216">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="441a6-217">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="441a6-217">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="441a6-218">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="441a6-218">RELATED LINKS</span></span>

[<span data-ttu-id="441a6-219">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-219">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="441a6-220">Join-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-220">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="441a6-221">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-221">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="441a6-222">Split-Path</span><span class="sxs-lookup"><span data-stu-id="441a6-222">Split-Path</span></span>](Split-Path.md)
