---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 4189201cd373d29e8ea8e88441376e0df902742e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193218"
---
# <span data-ttu-id="eca4e-103">Join-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-103">Join-Path</span></span>

## <span data-ttu-id="eca4e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="eca4e-104">SYNOPSIS</span></span>
<span data-ttu-id="eca4e-105">Combina um caminho e um caminho filho em um único caminho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-105">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="eca4e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eca4e-106">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="eca4e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eca4e-107">DESCRIPTION</span></span>

<span data-ttu-id="eca4e-108">O `Join-Path` cmdlet combina um caminho e um caminho filho em um único caminho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-108">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="eca4e-109">O provedor fornece os delimitadores de caminho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-109">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="eca4e-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="eca4e-110">EXAMPLES</span></span>

### <span data-ttu-id="eca4e-111">Exemplo 1: combinar um caminho com um caminho filho</span><span class="sxs-lookup"><span data-stu-id="eca4e-111">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="eca4e-112">Esse comando usa `Join-Path` para combinar um caminho com um ChildPath.</span><span class="sxs-lookup"><span data-stu-id="eca4e-112">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="eca4e-113">Como o comando é executado do `FileSystem` provedor, ele fornece o `\` delimitador para unir os caminhos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-113">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="eca4e-114">Exemplo 2: combinar caminhos que já contêm separadores de diretório</span><span class="sxs-lookup"><span data-stu-id="eca4e-114">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="eca4e-115">Separadores de diretório existentes `\` e manipulados para que haja apenas um separador entre `Path` e `ChildPath`</span><span class="sxs-lookup"><span data-stu-id="eca4e-115">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="eca4e-116">Exemplo 3: exibir arquivos e pastas unindo um caminho com um caminho filho</span><span class="sxs-lookup"><span data-stu-id="eca4e-116">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="eca4e-117">Esse comando exibe os arquivos e pastas que são referenciados unindo o \* caminho C:\win e o \* caminho filho do sistema.</span><span class="sxs-lookup"><span data-stu-id="eca4e-117">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="eca4e-118">Ele exibe os mesmos arquivos e pastas que `Get-ChildItem` , mas exibe o caminho totalmente qualificado para cada item.</span><span class="sxs-lookup"><span data-stu-id="eca4e-118">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="eca4e-119">Nesse comando, os `Path` nomes de `ChildPath` parâmetro e opcionais são omitidos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-119">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="eca4e-120">Exemplo 4: usar Join-Path com o provedor de registro do PowerShell</span><span class="sxs-lookup"><span data-stu-id="eca4e-120">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="eca4e-121">Esse comando exibe as chaves do registro na `HKLM\System` subchave do registro que incluem `ControlSet` .</span><span class="sxs-lookup"><span data-stu-id="eca4e-121">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="eca4e-122">O `Resolve` parâmetro, tenta resolver o caminho Unido, incluindo curingas do caminho do provedor atual `HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="eca4e-122">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="eca4e-123">Exemplo 5: combinar várias raízes de caminho com um caminho filho</span><span class="sxs-lookup"><span data-stu-id="eca4e-123">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="eca4e-124">Esse comando usa `Join-Path` para combinar várias raízes de caminho com um caminho filho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-124">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="eca4e-125">As unidades especificadas por `Path` devem existir ou haverá falha na junção dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="eca4e-125">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="eca4e-126">Exemplo 6: combinar as raízes de uma unidade do sistema de arquivos com um caminho filho</span><span class="sxs-lookup"><span data-stu-id="eca4e-126">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="eca4e-127">Esse comando combina as raízes de cada unidade do sistema de arquivos do PowerShell no console do com o caminho filho subdir.</span><span class="sxs-lookup"><span data-stu-id="eca4e-127">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="eca4e-128">O comando usa o `Get-PSDrive` cmdlet para obter as unidades do PowerShell com suporte pelo provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="eca4e-128">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="eca4e-129">A `ForEach-Object` instrução seleciona apenas a propriedade raiz dos `PSDriveInfo` objetos e a combina com o caminho filho especificado.</span><span class="sxs-lookup"><span data-stu-id="eca4e-129">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="eca4e-130">A saída mostra que as unidades do PowerShell no computador incluíram uma unidade mapeada para o diretório C:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="eca4e-130">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

### <span data-ttu-id="eca4e-131">Exemplo 7: combinar um número indefinido de caminhos</span><span class="sxs-lookup"><span data-stu-id="eca4e-131">Example 7: Combine an indefinite number of paths</span></span>

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

<span data-ttu-id="eca4e-132">O `AdditionalChildPath` parâmetro permite a junção de um número ilimitado de caminhos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-132">The `AdditionalChildPath` parameter allows the joining of an unlimited number of paths.</span></span>

<span data-ttu-id="eca4e-133">Neste exemplo, nenhum nome de parâmetro é usado, portanto "a" é associado a `Path` "b" a `ChildPath` e "c-g" para `AdditionalChildPath`</span><span class="sxs-lookup"><span data-stu-id="eca4e-133">In this example, no parameter names are used, thus "a" binds to `Path`, "b" to `ChildPath` and "c-g" to `AdditionalChildPath`</span></span>

## <span data-ttu-id="eca4e-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eca4e-134">PARAMETERS</span></span>

### <span data-ttu-id="eca4e-135">-AdditionalChildPath</span><span class="sxs-lookup"><span data-stu-id="eca4e-135">-AdditionalChildPath</span></span>

<span data-ttu-id="eca4e-136">Especifica elementos adicionais a serem acrescentados ao valor do parâmetro *path* .</span><span class="sxs-lookup"><span data-stu-id="eca4e-136">Specifies additional elements to append to the value of the *Path* parameter.</span></span> <span data-ttu-id="eca4e-137">O `ChildPath` parâmetro ainda é obrigatório e também deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="eca4e-137">The `ChildPath` parameter is still mandatory and must be specified as well.</span></span>

<span data-ttu-id="eca4e-138">Esse parâmetro é especificado com a `ValueFromRemainingArguments` propriedade que permite ingressar em um número indefinido de caminhos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-138">This parameter is specified with the `ValueFromRemainingArguments` property which enables joining an indefinite number of paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eca4e-139">-ChildPath</span><span class="sxs-lookup"><span data-stu-id="eca4e-139">-ChildPath</span></span>

<span data-ttu-id="eca4e-140">Especifica os elementos a serem acrescentados ao valor do `Path` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eca4e-140">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="eca4e-141">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-141">Wildcards are permitted.</span></span>
<span data-ttu-id="eca4e-142">O `ChildPath` parâmetro é necessário, embora o nome do parâmetro ("ChildPath") seja opcional.</span><span class="sxs-lookup"><span data-stu-id="eca4e-142">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="eca4e-143">-Credential</span><span class="sxs-lookup"><span data-stu-id="eca4e-143">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="eca4e-144">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eca4e-144">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="eca4e-145">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="eca4e-145">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="eca4e-146">-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-146">-Path</span></span>

<span data-ttu-id="eca4e-147">Especifica o caminho principal (ou caminhos) ao qual o caminho filho é anexado.</span><span class="sxs-lookup"><span data-stu-id="eca4e-147">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="eca4e-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="eca4e-148">Wildcards are permitted.</span></span>

<span data-ttu-id="eca4e-149">O valor de `Path` determina qual provedor une os caminhos e adiciona os delimitadores de caminho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-149">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="eca4e-150">O `Path` parâmetro é necessário, embora o nome do parâmetro ("Path") seja opcional.</span><span class="sxs-lookup"><span data-stu-id="eca4e-150">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="eca4e-151">-Resolver</span><span class="sxs-lookup"><span data-stu-id="eca4e-151">-Resolve</span></span>

<span data-ttu-id="eca4e-152">Indica que este cmdlet deve tentar resolver o caminho Unido do provedor atual.</span><span class="sxs-lookup"><span data-stu-id="eca4e-152">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="eca4e-153">Se forem usados curingas, o cmdlet retornará todos os caminhos que correspondam ao caminho Unido.</span><span class="sxs-lookup"><span data-stu-id="eca4e-153">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="eca4e-154">Se **nenhum** caractere curinga for usado, o cmdlet será um erro se o caminho não existir.</span><span class="sxs-lookup"><span data-stu-id="eca4e-154">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

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

### <span data-ttu-id="eca4e-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eca4e-155">CommonParameters</span></span>

<span data-ttu-id="eca4e-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eca4e-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eca4e-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eca4e-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eca4e-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="eca4e-158">INPUTS</span></span>

### <span data-ttu-id="eca4e-159">System.String</span><span class="sxs-lookup"><span data-stu-id="eca4e-159">System.String</span></span>

<span data-ttu-id="eca4e-160">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eca4e-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="eca4e-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="eca4e-161">OUTPUTS</span></span>

### <span data-ttu-id="eca4e-162">System.String</span><span class="sxs-lookup"><span data-stu-id="eca4e-162">System.String</span></span>

<span data-ttu-id="eca4e-163">Esse cmdlet retorna uma cadeia de caracteres que contém o caminho resultante.</span><span class="sxs-lookup"><span data-stu-id="eca4e-163">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="eca4e-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="eca4e-164">NOTES</span></span>

<span data-ttu-id="eca4e-165">Os cmdlets que contêm o substantivo de caminho (os cmdlets de caminho) manipulam nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar.</span><span class="sxs-lookup"><span data-stu-id="eca4e-165">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="eca4e-166">Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="eca4e-166">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="eca4e-167">Use-os como usaria Dirname, Normpath, Realpath, Join ou outros manipuladores de caminho.</span><span class="sxs-lookup"><span data-stu-id="eca4e-167">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="eca4e-168">Você pode usar os cmdlets de caminho com vários provedores, incluindo `FileSystem` os `Registry` provedores, e `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="eca4e-168">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="eca4e-169">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="eca4e-169">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="eca4e-170">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="eca4e-170">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="eca4e-171">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="eca4e-171">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="eca4e-172">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eca4e-172">RELATED LINKS</span></span>

[<span data-ttu-id="eca4e-173">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-173">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="eca4e-174">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-174">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="eca4e-175">Split-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-175">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="eca4e-176">Test-Path</span><span class="sxs-lookup"><span data-stu-id="eca4e-176">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="eca4e-177">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="eca4e-177">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="eca4e-178">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="eca4e-178">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="eca4e-179">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="eca4e-179">Get-PSDrive</span></span>](Get-PSDrive.md)

