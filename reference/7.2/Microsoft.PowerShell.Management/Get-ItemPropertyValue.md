---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: b8980febb80a4e7dfaefba46649ac49b5b41b427
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597795"
---
# <span data-ttu-id="311b7-102">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="311b7-102">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="311b7-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="311b7-103">SYNOPSIS</span></span>
<span data-ttu-id="311b7-104">Obtém o valor de uma ou mais propriedades de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="311b7-104">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="311b7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="311b7-105">SYNTAX</span></span>

### <span data-ttu-id="311b7-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="311b7-106">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="311b7-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="311b7-107">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="311b7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="311b7-108">DESCRIPTION</span></span>

<span data-ttu-id="311b7-109">O `Get-ItemPropertyValue` Obtém o valor atual para uma propriedade que você especifica quando usa o parâmetro *Name* , localizado em um caminho que você especifica com os parâmetros *Path* ou *LiteralPath* .</span><span class="sxs-lookup"><span data-stu-id="311b7-109">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="311b7-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="311b7-110">EXAMPLES</span></span>

### <span data-ttu-id="311b7-111">Exemplo 1: obter o valor da propriedade ProductID</span><span class="sxs-lookup"><span data-stu-id="311b7-111">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="311b7-112">Esse comando obtém o valor da propriedade **ProductID** do objeto "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" no provedor de registro do Windows.</span><span class="sxs-lookup"><span data-stu-id="311b7-112">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="311b7-113">Exemplo 2: obter a hora da última gravação de um arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="311b7-113">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="311b7-114">Esse comando obtém o valor da propriedade **LastWriteTime** , ou a última vez que um arquivo ou pasta foi alterado, da pasta "C:\Users\Test\Documents\ModuleToAssembly", trabalhando no provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="311b7-114">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="311b7-115">Exemplo 3: obter vários valores de propriedade de um arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="311b7-115">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="311b7-116">Esse comando obtém os valores das propriedades **LastWriteTime**, **CreationTime** e **root** de uma pasta.</span><span class="sxs-lookup"><span data-stu-id="311b7-116">This command gets the values of the **LastWriteTime**, **CreationTime**, and **Root** properties of a folder.</span></span> <span data-ttu-id="311b7-117">Os valores de propriedade são retornados na ordem em que você especificou os nomes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="311b7-117">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="311b7-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="311b7-118">PARAMETERS</span></span>

### <span data-ttu-id="311b7-119">-Credential</span><span class="sxs-lookup"><span data-stu-id="311b7-119">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="311b7-120">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="311b7-120">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="311b7-121">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-121">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="311b7-122">-Excluir</span><span class="sxs-lookup"><span data-stu-id="311b7-122">-Exclude</span></span>

<span data-ttu-id="311b7-123">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="311b7-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="311b7-124">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="311b7-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="311b7-125">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="311b7-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="311b7-126">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="311b7-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="311b7-127">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="311b7-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="311b7-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="311b7-128">-Filter</span></span>

<span data-ttu-id="311b7-129">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="311b7-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="311b7-130">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="311b7-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="311b7-131">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="311b7-132">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="311b7-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="311b7-133">-Incluir</span><span class="sxs-lookup"><span data-stu-id="311b7-133">-Include</span></span>

<span data-ttu-id="311b7-134">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="311b7-134">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="311b7-135">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="311b7-135">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="311b7-136">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="311b7-136">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="311b7-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="311b7-137">Wildcard characters are permitted.</span></span> <span data-ttu-id="311b7-138">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="311b7-138">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="311b7-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="311b7-139">-LiteralPath</span></span>

<span data-ttu-id="311b7-140">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="311b7-140">Specifies a path to one or more locations.</span></span> <span data-ttu-id="311b7-141">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="311b7-141">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="311b7-142">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="311b7-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="311b7-143">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="311b7-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="311b7-144">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="311b7-144">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="311b7-145">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-145">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="311b7-146">-Name</span><span class="sxs-lookup"><span data-stu-id="311b7-146">-Name</span></span>

<span data-ttu-id="311b7-147">Especifica o nome da propriedade ou propriedades para recuperar.</span><span class="sxs-lookup"><span data-stu-id="311b7-147">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="311b7-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="311b7-148">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="311b7-149">-Path</span><span class="sxs-lookup"><span data-stu-id="311b7-149">-Path</span></span>

<span data-ttu-id="311b7-150">Especifica o caminho para o(s) item(ns).</span><span class="sxs-lookup"><span data-stu-id="311b7-150">Specifies the path to the item or items.</span></span>
<span data-ttu-id="311b7-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="311b7-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="311b7-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="311b7-152">CommonParameters</span></span>

<span data-ttu-id="311b7-153">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="311b7-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="311b7-154">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="311b7-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="311b7-155">INPUTS</span></span>

### <span data-ttu-id="311b7-156">System.String</span><span class="sxs-lookup"><span data-stu-id="311b7-156">System.String</span></span>

<span data-ttu-id="311b7-157">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="311b7-157">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="311b7-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="311b7-158">OUTPUTS</span></span>

### <span data-ttu-id="311b7-159">System. booliano, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="311b7-159">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="311b7-160">Esse cmdlet retorna um objeto para cada valor de propriedade de item que obtém.</span><span class="sxs-lookup"><span data-stu-id="311b7-160">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="311b7-161">O tipo de objeto depende do valor da propriedade que é recuperado.</span><span class="sxs-lookup"><span data-stu-id="311b7-161">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="311b7-162">Por exemplo, em uma unidade do sistema de arquivos, o cmdlet pode retornar um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="311b7-162">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="311b7-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="311b7-163">NOTES</span></span>

<span data-ttu-id="311b7-164">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="311b7-164">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="311b7-165">Para listar os provedores disponíveis em sua sessão, execute o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="311b7-165">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="311b7-166">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="311b7-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="311b7-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="311b7-167">RELATED LINKS</span></span>

[<span data-ttu-id="311b7-168">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-168">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="311b7-169">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-169">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="311b7-170">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-170">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="311b7-171">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="311b7-171">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="311b7-172">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-172">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="311b7-173">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-173">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="311b7-174">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-174">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="311b7-175">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-175">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="311b7-176">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="311b7-176">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="311b7-177">about_Providers</span><span class="sxs-lookup"><span data-stu-id="311b7-177">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

