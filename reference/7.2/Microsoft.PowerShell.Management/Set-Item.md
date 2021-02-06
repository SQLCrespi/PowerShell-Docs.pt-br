---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: c617f4554c8e61ed6cf54b0faf0cd7d79be84595
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595368"
---
# <span data-ttu-id="0e8f8-102">Set-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-102">Set-Item</span></span>

## <span data-ttu-id="0e8f8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0e8f8-103">SYNOPSIS</span></span>
<span data-ttu-id="0e8f8-104">Altera o valor de um item para o valor especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-104">Changes the value of an item to the value specified in the command.</span></span>

## <span data-ttu-id="0e8f8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e8f8-105">SYNTAX</span></span>

### <span data-ttu-id="0e8f8-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="0e8f8-106">Path (Default)</span></span>

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e8f8-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e8f8-107">LiteralPath</span></span>

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e8f8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e8f8-108">DESCRIPTION</span></span>

<span data-ttu-id="0e8f8-109">O `Set-Item` cmdlet altera o valor de um item, como uma variável ou chave do registro, para o valor especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-109">The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.</span></span>

## <span data-ttu-id="0e8f8-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0e8f8-110">EXAMPLES</span></span>

### <span data-ttu-id="0e8f8-111">Exemplo 1: criar um alias</span><span class="sxs-lookup"><span data-stu-id="0e8f8-111">Example 1: Create an alias</span></span>

<span data-ttu-id="0e8f8-112">Este comando cria um alias de NP para o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-112">This command creates an alias of np for Notepad.</span></span>

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### <span data-ttu-id="0e8f8-113">Exemplo 2: alterar o valor de uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="0e8f8-113">Example 2: Change the value of an environment variable</span></span>

<span data-ttu-id="0e8f8-114">Esse comando altera o valor da variável de ambiente USERROLE para administrador.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-114">This command changes the value of the UserRole environment variable to Administrator.</span></span>

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### <span data-ttu-id="0e8f8-115">Exemplo 3: modificar sua função de prompt</span><span class="sxs-lookup"><span data-stu-id="0e8f8-115">Example 3: Modify your prompt function</span></span>

<span data-ttu-id="0e8f8-116">Esse comando altera a função de prompt para que ela exiba a hora antes do caminho.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-116">This command changes the prompt function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### <span data-ttu-id="0e8f8-117">Exemplo 4: definir opções para a função de prompt</span><span class="sxs-lookup"><span data-stu-id="0e8f8-117">Example 4: Set options for your prompt function</span></span>

<span data-ttu-id="0e8f8-118">Este comando define as opções de **escopo** e **somente leitura** para a função de prompt.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-118">This command sets the **AllScope** and **ReadOnly** options for the prompt function.</span></span>
<span data-ttu-id="0e8f8-119">Esse comando usa o parâmetro dinâmico **Options** de `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-119">This command uses the **Options** dynamic parameter of `Set-Item`.</span></span>
<span data-ttu-id="0e8f8-120">O parâmetro **Options** está disponível `Set-Item` somente quando você o usa com o **alias** ou o provedor de **funções** .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-120">The **Options** parameter is available in `Set-Item` only when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## <span data-ttu-id="0e8f8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e8f8-121">PARAMETERS</span></span>

### <span data-ttu-id="0e8f8-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="0e8f8-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0e8f8-123">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0e8f8-124">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-125">-Excluir</span><span class="sxs-lookup"><span data-stu-id="0e8f8-125">-Exclude</span></span>

<span data-ttu-id="0e8f8-126">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="0e8f8-127">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0e8f8-128">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0e8f8-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="0e8f8-130">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0e8f8-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="0e8f8-131">-Filter</span></span>

<span data-ttu-id="0e8f8-132">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="0e8f8-133">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="0e8f8-134">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="0e8f8-135">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0e8f8-136">-Force</span><span class="sxs-lookup"><span data-stu-id="0e8f8-136">-Force</span></span>

<span data-ttu-id="0e8f8-137">Força o cmdlet a definir itens que, de outra forma, não podem ser alterados, como alias ou variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-137">Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables.</span></span> <span data-ttu-id="0e8f8-138">O cmdlet não pode alterar variáveis nem aliases constantes.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-138">The cmdlet cannot change constant aliases or variables.</span></span>
<span data-ttu-id="0e8f8-139">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-139">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="0e8f8-140">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-140">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="0e8f8-141">Mesmo usando o parâmetro *Force* , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-141">Even using the *Force* parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-142">-Incluir</span><span class="sxs-lookup"><span data-stu-id="0e8f8-142">-Include</span></span>

<span data-ttu-id="0e8f8-143">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-143">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="0e8f8-144">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-144">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0e8f8-145">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-145">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="0e8f8-146">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-146">Wildcard characters are permitted.</span></span> <span data-ttu-id="0e8f8-147">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-147">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0e8f8-148">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e8f8-148">-LiteralPath</span></span>

<span data-ttu-id="0e8f8-149">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-149">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0e8f8-150">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-150">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0e8f8-151">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-151">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0e8f8-152">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-152">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0e8f8-153">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-153">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0e8f8-154">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-154">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="0e8f8-155">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0e8f8-155">-PassThru</span></span>

<span data-ttu-id="0e8f8-156">Passa um objeto que representa o item para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-156">Passes an object that represents the item to the pipeline.</span></span>
<span data-ttu-id="0e8f8-157">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-157">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-158">-Path</span><span class="sxs-lookup"><span data-stu-id="0e8f8-158">-Path</span></span>

<span data-ttu-id="0e8f8-159">Especifica um caminho do local dos itens.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-159">Specifies a path of the location of the items.</span></span>
<span data-ttu-id="0e8f8-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0e8f8-161">-Value</span><span class="sxs-lookup"><span data-stu-id="0e8f8-161">-Value</span></span>

<span data-ttu-id="0e8f8-162">Especifica um novo valor para o item.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-162">Specifies a new value for the item.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e8f8-163">-Confirm</span></span>

<span data-ttu-id="0e8f8-164">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-164">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e8f8-165">-WhatIf</span></span>

<span data-ttu-id="0e8f8-166">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0e8f8-167">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-167">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e8f8-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e8f8-168">CommonParameters</span></span>

<span data-ttu-id="0e8f8-169">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-169">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0e8f8-170">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0e8f8-171">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0e8f8-171">INPUTS</span></span>

### <span data-ttu-id="0e8f8-172">System.Object</span><span class="sxs-lookup"><span data-stu-id="0e8f8-172">System.Object</span></span>

<span data-ttu-id="0e8f8-173">É possível canalizar um objeto que representa o novo valor do item para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-173">You can pipe an object that represents the new value of the item to this cmdlet.</span></span>

## <span data-ttu-id="0e8f8-174">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0e8f8-174">OUTPUTS</span></span>

### <span data-ttu-id="0e8f8-175">Nenhum ou um objeto que representa o item novo ou alterado.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-175">None or an object representing the new or changed item.</span></span>

<span data-ttu-id="0e8f8-176">Esse cmdlet gera um objeto que representa o item, se você especificar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-176">This cmdlet generates an object that represent the item, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="0e8f8-177">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e8f8-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0e8f8-178">NOTES</span></span>

- <span data-ttu-id="0e8f8-179">`Set-Item` Não é suportado pelo provedor de sistema de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-179">`Set-Item` is not supported by the PowerShell FileSystem provider.</span></span> <span data-ttu-id="0e8f8-180">Para alterar os valores de itens no sistema de arquivos, use o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-180">To change the values of items in the file system, use the `Set-Content` cmdlet.</span></span>
- <span data-ttu-id="0e8f8-181">Nas unidades de registro, `HKLM:` e `HKCU:` `Set-Item` altera os dados no valor (padrão) de uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-181">In the Registry drives, `HKLM:` and `HKCU:`, `Set-Item` changes the data in the (Default) value of a registry key.</span></span>
  - <span data-ttu-id="0e8f8-182">Para criar e alterar os nomes das chaves do registro, use `New-Item` o `Rename-Item` cmdlet e.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-182">To create and change the names of registry keys, use the `New-Item` and `Rename-Item` cmdlet.</span></span>
  - <span data-ttu-id="0e8f8-183">Para alterar os nomes e os dados em valores de registro, use os `New-ItemProperty` `Set-ItemProperty` `Rename-ItemProperty` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-183">To change the names and data in registry values, use the `New-ItemProperty`, `Set-ItemProperty`, and `Rename-ItemProperty` cmdlets.</span></span>
- <span data-ttu-id="0e8f8-184">`Set-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="0e8f8-184">`Set-Item` is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="0e8f8-185">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="0e8f8-185">To list the providers available in your session, type `Get-PsProvider`.</span></span>
  <span data-ttu-id="0e8f8-186">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0e8f8-186">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0e8f8-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0e8f8-187">RELATED LINKS</span></span>

[<span data-ttu-id="0e8f8-188">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-188">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="0e8f8-189">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-189">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="0e8f8-190">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-190">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="0e8f8-191">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-191">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="0e8f8-192">Move-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-192">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="0e8f8-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-193">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="0e8f8-194">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-194">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="0e8f8-195">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="0e8f8-195">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="0e8f8-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0e8f8-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

