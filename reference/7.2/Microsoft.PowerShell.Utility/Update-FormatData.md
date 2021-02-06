---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 91d0274e485573de96d9960fa49f6d327156a79a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597813"
---
# <span data-ttu-id="e7b30-102">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="e7b30-102">Update-FormatData</span></span>

## <span data-ttu-id="e7b30-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e7b30-103">SYNOPSIS</span></span>
<span data-ttu-id="e7b30-104">Atualiza os dados de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e7b30-104">Updates the formatting data in the current session.</span></span>

## <span data-ttu-id="e7b30-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7b30-105">SYNTAX</span></span>

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e7b30-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7b30-106">DESCRIPTION</span></span>

<span data-ttu-id="e7b30-107">O `Update-FormatData` cmdlet recarrega os dados de formatação de arquivos de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e7b30-107">The `Update-FormatData` cmdlet reloads the formatting data from formatting files into the current session.</span></span> <span data-ttu-id="e7b30-108">Esse cmdlet permite que você atualize os dados de formatação sem reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7b30-108">This cmdlet lets you update the formatting data without restarting PowerShell.</span></span>

<span data-ttu-id="e7b30-109">Sem parâmetros, `Update-FormatData` o recarrega os arquivos de formatação que ele carregou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7b30-109">Without parameters, `Update-FormatData` reloads the formatting files that it loaded previously.</span></span>
<span data-ttu-id="e7b30-110">Você pode usar os parâmetros de `Update-FormatData` para adicionar novos arquivos de formatação à sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-110">You can use the parameters of `Update-FormatData` to add new formatting files to the session.</span></span>

<span data-ttu-id="e7b30-111">Os arquivos de formatação são arquivos de texto em formato XML com a `format.ps1xml` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e7b30-111">Formatting files are text files in XML format with the `format.ps1xml` file name extension.</span></span> <span data-ttu-id="e7b30-112">A formatação de dados nos arquivos define a exibição de objetos do Microsoft .NET Framework presentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-112">The formatting data in the files defines the display of Microsoft .NET Framework objects in the session.</span></span>

<span data-ttu-id="e7b30-113">Quando o PowerShell é iniciado, ele carrega os dados de formato do código-fonte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7b30-113">When PowerShell starts, it loads the format data from the PowerShell source code.</span></span> <span data-ttu-id="e7b30-114">No entanto, você pode criar arquivos XML de format.ps1personalizados para atualizar a formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e7b30-114">However, you can create custom format.ps1xml files to update formatting in the current session.</span></span> <span data-ttu-id="e7b30-115">Você pode usar `Update-FormatData` o para recarregar os dados de formatação na sessão atual sem reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7b30-115">You can use `Update-FormatData` to reload the formatting data into the current session without restarting PowerShell.</span></span> <span data-ttu-id="e7b30-116">Isso é útil para quando você adicionou ou alterou um arquivo de formatação, mas não deseja interromper a sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-116">This is useful when you have added or changed a formatting file, but do not want to interrupt the session.</span></span>

<span data-ttu-id="e7b30-117">Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="e7b30-117">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="e7b30-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e7b30-118">EXAMPLES</span></span>

### <span data-ttu-id="e7b30-119">Exemplo 1: recarregar arquivos de formatação carregados anteriormente</span><span class="sxs-lookup"><span data-stu-id="e7b30-119">Example 1: Reload previously loaded formatting files</span></span>

```powershell
Update-FormatData
```

<span data-ttu-id="e7b30-120">Este comando recarrega os arquivos de formatação que havia carregado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7b30-120">This command reloads the formatting files that it loaded previously.</span></span>

### <span data-ttu-id="e7b30-121">Exemplo 2: recarregar arquivos de formatação e rastreamento e arquivos de formatação de log</span><span class="sxs-lookup"><span data-stu-id="e7b30-121">Example 2: Reload formatting files and trace and log formatting files</span></span>

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

<span data-ttu-id="e7b30-122">Este comando recarrega os arquivos de formatação para a sessão, incluindo dois novos arquivos: Trace.format.ps1xml e Log.format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="e7b30-122">This command reloads the formatting files into the session, including two new files, Trace.format.ps1xml and Log.format.ps1xml.</span></span>

<span data-ttu-id="e7b30-123">Como o comando usa o parâmetro **AppendPath** , os dados de formatação nos novos arquivos são carregados após os dados de formatação dos arquivos internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-123">Because the command uses the **AppendPath** parameter, the formatting data in the new files is loaded after the formatting data from the built-in files.</span></span>

<span data-ttu-id="e7b30-124">O parâmetro **AppendPath** é usado porque os novos arquivos contêm dados de formatação para objetos que não são referenciados nos arquivos internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-124">The **AppendPath** parameter is used because the new files contain formatting data for objects that are not referenced in the built-in files.</span></span>

### <span data-ttu-id="e7b30-125">Exemplo 3: editar um arquivo de formatação e recarregá-lo</span><span class="sxs-lookup"><span data-stu-id="e7b30-125">Example 3: Edit a formatting file and reload it</span></span>

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

<span data-ttu-id="e7b30-126">Este exemplo mostra como recarregar um arquivo formatação após você tê-lo editado.</span><span class="sxs-lookup"><span data-stu-id="e7b30-126">This example shows how to reload a formatting file after you have edited it.</span></span>

<span data-ttu-id="e7b30-127">O primeiro comando adiciona o arquivo NewFiles.format.ps1xml à sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-127">The first command adds the NewFiles.format.ps1xml file to the session.</span></span> <span data-ttu-id="e7b30-128">Ele usa o parâmetro **PrependPath** porque o arquivo contém dados de formatação para objetos que são referenciados nos arquivos internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-128">It uses the **PrependPath** parameter because the file contains formatting data for objects that are referenced in the built-in files.</span></span>

<span data-ttu-id="e7b30-129">Depois de adicionar o arquivo XML de NewFiles.format.ps1e testá-lo nessas sessões, o autor editará o arquivo.</span><span class="sxs-lookup"><span data-stu-id="e7b30-129">After adding the NewFiles.format.ps1xml file and testing it in these sessions, the author edits the file.</span></span>

<span data-ttu-id="e7b30-130">O segundo comando usa o `Update-FormatData` cmdlet para recarregar os arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="e7b30-130">The second command uses the `Update-FormatData` cmdlet to reload the formatting files.</span></span> <span data-ttu-id="e7b30-131">Como o arquivo XML de NewFiles.format.ps1foi carregado anteriormente, o `Update-FormatData` recarrega automaticamente sem usar parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e7b30-131">Because the NewFiles.format.ps1xml file was previously loaded, `Update-FormatData` automatically reloads it without using parameters.</span></span>

## <span data-ttu-id="e7b30-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7b30-132">PARAMETERS</span></span>

### <span data-ttu-id="e7b30-133">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="e7b30-133">-AppendPath</span></span>

<span data-ttu-id="e7b30-134">Especifica os arquivos de formatação que esse cmdlet adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-134">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="e7b30-135">Os arquivos são carregados depois que o PowerShell carrega os arquivos de formatação internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-135">The files are loaded after PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="e7b30-136">Ao Formatar objetos .NET, o PowerShell usa a primeira definição de formatação que encontra para cada tipo de .NET.</span><span class="sxs-lookup"><span data-stu-id="e7b30-136">When formatting .NET objects, PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="e7b30-137">Se você usar o parâmetro **AppendPath** , o PowerShell pesquisará os dados dos arquivos internos antes de encontrar os dados de formatação que você está adicionando.</span><span class="sxs-lookup"><span data-stu-id="e7b30-137">If you use the **AppendPath** parameter, PowerShell searches the data from the built-in files before it encounters the formatting data that you are adding.</span></span>

<span data-ttu-id="e7b30-138">Use este parâmetro para adicionar um arquivo que formata um objeto .NET que não é referenciado nos arquivos de formatação internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-138">Use this parameter to add a file that formats a .NET object that is not referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e7b30-139">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="e7b30-139">-PrependPath</span></span>

<span data-ttu-id="e7b30-140">Especifica os arquivos de formatação que esse cmdlet adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="e7b30-140">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="e7b30-141">Os arquivos são carregados antes que o PowerShell carregue os arquivos de formatação internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-141">The files are loaded before PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="e7b30-142">Ao Formatar objetos .NET, o PowerShell usa a primeira definição de formatação que encontra para cada tipo de .NET.</span><span class="sxs-lookup"><span data-stu-id="e7b30-142">When formatting .NET objects, PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="e7b30-143">Se você usar o parâmetro **PrependPath** , o PowerShell pesquisará os dados dos arquivos que você está adicionando antes de encontrar os dados de formatação dos arquivos internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-143">If you use the **PrependPath** parameter, PowerShell searches the data from the files that you are adding before it encounters the formatting data from the built-in files.</span></span>

<span data-ttu-id="e7b30-144">Use este parâmetro para adicionar um arquivo que formata um objeto .NET que também é referenciado nos arquivos de formatação internos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-144">Use this parameter to add a file that formats a .NET object that is also referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7b30-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e7b30-145">-Confirm</span></span>

<span data-ttu-id="e7b30-146">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7b30-146">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e7b30-147">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e7b30-147">-WhatIf</span></span>

<span data-ttu-id="e7b30-148">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e7b30-148">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e7b30-149">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e7b30-149">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e7b30-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7b30-150">CommonParameters</span></span>

<span data-ttu-id="e7b30-151">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7b30-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7b30-152">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7b30-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7b30-153">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e7b30-153">INPUTS</span></span>

### <span data-ttu-id="e7b30-154">System.String</span><span class="sxs-lookup"><span data-stu-id="e7b30-154">System.String</span></span>

<span data-ttu-id="e7b30-155">É possível canalizar uma cadeia de caracteres que contém o caminho de acréscimo para `Update-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="e7b30-155">You can pipe a string that contains the append path to `Update-FormatData`.</span></span>

## <span data-ttu-id="e7b30-156">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e7b30-156">OUTPUTS</span></span>

### <span data-ttu-id="e7b30-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e7b30-157">None</span></span>

<span data-ttu-id="e7b30-158">O cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e7b30-158">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="e7b30-159">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e7b30-159">NOTES</span></span>

- <span data-ttu-id="e7b30-160">`Update-FormatData` também atualiza os dados de formatação para comandos na sessão que foram importados dos módulos.</span><span class="sxs-lookup"><span data-stu-id="e7b30-160">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="e7b30-161">Se o arquivo de formatação de um módulo for alterado, você poderá executar um `Update-FormatData` comando para atualizar os dados de formatação para comandos importados.</span><span class="sxs-lookup"><span data-stu-id="e7b30-161">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="e7b30-162">Você não precisa importar o módulo novamente.</span><span class="sxs-lookup"><span data-stu-id="e7b30-162">You do not need to import the module again.</span></span>

## <span data-ttu-id="e7b30-163">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e7b30-163">RELATED LINKS</span></span>

[<span data-ttu-id="e7b30-164">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="e7b30-164">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="e7b30-165">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="e7b30-165">Export-FormatData</span></span>](Export-FormatData.md)
