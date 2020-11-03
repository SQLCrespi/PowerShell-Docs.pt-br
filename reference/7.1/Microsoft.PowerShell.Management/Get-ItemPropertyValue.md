---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 96fc9ce21b320710181fe97b6a47edbab8cc65a1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194294"
---
# <span data-ttu-id="547ce-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="547ce-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="547ce-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="547ce-104">SYNOPSIS</span></span>
<span data-ttu-id="547ce-105">Obtém o valor de uma ou mais propriedades de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="547ce-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="547ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="547ce-106">SYNTAX</span></span>

### <span data-ttu-id="547ce-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="547ce-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="547ce-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="547ce-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="547ce-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="547ce-109">DESCRIPTION</span></span>

<span data-ttu-id="547ce-110">O `Get-ItemPropertyValue` Obtém o valor atual para uma propriedade que você especifica quando usa o parâmetro *Name* , localizado em um caminho que você especifica com os parâmetros *Path* ou *LiteralPath* .</span><span class="sxs-lookup"><span data-stu-id="547ce-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="547ce-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="547ce-111">EXAMPLES</span></span>

### <span data-ttu-id="547ce-112">Exemplo 1: obter o valor da propriedade ProductID</span><span class="sxs-lookup"><span data-stu-id="547ce-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="547ce-113">Esse comando obtém o valor da propriedade **ProductID** do objeto "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" no provedor de registro do Windows.</span><span class="sxs-lookup"><span data-stu-id="547ce-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="547ce-114">Exemplo 2: obter a hora da última gravação de um arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="547ce-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="547ce-115">Esse comando obtém o valor da propriedade **LastWriteTime** , ou a última vez que um arquivo ou pasta foi alterado, da pasta "C:\Users\Test\Documents\ModuleToAssembly", trabalhando no provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="547ce-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="547ce-116">Exemplo 3: obter vários valores de propriedade de um arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="547ce-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="547ce-117">Esse comando obtém os valores das propriedades **LastWriteTime** , **CreationTime** e **root** de uma pasta.</span><span class="sxs-lookup"><span data-stu-id="547ce-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span> <span data-ttu-id="547ce-118">Os valores de propriedade são retornados na ordem em que você especificou os nomes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="547ce-118">The property values are returned in the order in which you specified the property names.</span></span>

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

## <span data-ttu-id="547ce-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="547ce-119">PARAMETERS</span></span>

### <span data-ttu-id="547ce-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="547ce-120">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="547ce-121">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="547ce-121">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="547ce-122">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="547ce-122">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="547ce-123">-Excluir</span><span class="sxs-lookup"><span data-stu-id="547ce-123">-Exclude</span></span>

<span data-ttu-id="547ce-124">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="547ce-124">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="547ce-125">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="547ce-125">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="547ce-126">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="547ce-126">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="547ce-127">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="547ce-127">Wildcard characters are permitted.</span></span> <span data-ttu-id="547ce-128">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="547ce-128">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="547ce-129">-Filter</span><span class="sxs-lookup"><span data-stu-id="547ce-129">-Filter</span></span>

<span data-ttu-id="547ce-130">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="547ce-130">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="547ce-131">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="547ce-131">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="547ce-132">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="547ce-132">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="547ce-133">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="547ce-133">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="547ce-134">-Incluir</span><span class="sxs-lookup"><span data-stu-id="547ce-134">-Include</span></span>

<span data-ttu-id="547ce-135">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="547ce-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="547ce-136">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="547ce-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="547ce-137">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="547ce-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="547ce-138">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="547ce-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="547ce-139">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="547ce-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="547ce-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="547ce-140">-LiteralPath</span></span>

<span data-ttu-id="547ce-141">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="547ce-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="547ce-142">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="547ce-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="547ce-143">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="547ce-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="547ce-144">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="547ce-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="547ce-145">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="547ce-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="547ce-146">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="547ce-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="547ce-147">-Name</span><span class="sxs-lookup"><span data-stu-id="547ce-147">-Name</span></span>

<span data-ttu-id="547ce-148">Especifica o nome da propriedade ou propriedades para recuperar.</span><span class="sxs-lookup"><span data-stu-id="547ce-148">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="547ce-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="547ce-149">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="547ce-150">-Path</span><span class="sxs-lookup"><span data-stu-id="547ce-150">-Path</span></span>

<span data-ttu-id="547ce-151">Especifica o caminho para o(s) item(ns).</span><span class="sxs-lookup"><span data-stu-id="547ce-151">Specifies the path to the item or items.</span></span>
<span data-ttu-id="547ce-152">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="547ce-152">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="547ce-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="547ce-153">CommonParameters</span></span>

<span data-ttu-id="547ce-154">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="547ce-154">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="547ce-155">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="547ce-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="547ce-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="547ce-156">INPUTS</span></span>

### <span data-ttu-id="547ce-157">System.String</span><span class="sxs-lookup"><span data-stu-id="547ce-157">System.String</span></span>

<span data-ttu-id="547ce-158">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="547ce-158">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="547ce-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="547ce-159">OUTPUTS</span></span>

### <span data-ttu-id="547ce-160">System. booliano, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="547ce-160">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="547ce-161">Esse cmdlet retorna um objeto para cada valor de propriedade de item que obtém.</span><span class="sxs-lookup"><span data-stu-id="547ce-161">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="547ce-162">O tipo de objeto depende do valor da propriedade que é recuperado.</span><span class="sxs-lookup"><span data-stu-id="547ce-162">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="547ce-163">Por exemplo, em uma unidade do sistema de arquivos, o cmdlet pode retornar um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="547ce-163">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="547ce-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="547ce-164">NOTES</span></span>

<span data-ttu-id="547ce-165">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="547ce-165">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="547ce-166">Para listar os provedores disponíveis em sua sessão, execute o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="547ce-166">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="547ce-167">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="547ce-167">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="547ce-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="547ce-168">RELATED LINKS</span></span>

[<span data-ttu-id="547ce-169">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-169">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="547ce-170">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-170">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="547ce-171">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-171">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="547ce-172">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="547ce-172">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="547ce-173">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-173">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="547ce-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-174">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="547ce-175">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-175">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="547ce-176">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-176">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="547ce-177">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="547ce-177">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="547ce-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="547ce-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

