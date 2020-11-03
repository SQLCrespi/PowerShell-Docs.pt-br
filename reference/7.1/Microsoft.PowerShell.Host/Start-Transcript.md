---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: 395488731d2d30a16db986ccb91af3b1891daa24
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194652"
---
# <span data-ttu-id="487ec-103">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="487ec-103">Start-Transcript</span></span>

## <span data-ttu-id="487ec-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="487ec-104">SYNOPSIS</span></span>
<span data-ttu-id="487ec-105">Cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="487ec-105">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="487ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="487ec-106">SYNTAX</span></span>

### <span data-ttu-id="487ec-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="487ec-107">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="487ec-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="487ec-108">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="487ec-109">ByOutputDirectory</span><span class="sxs-lookup"><span data-stu-id="487ec-109">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="487ec-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="487ec-110">DESCRIPTION</span></span>

<span data-ttu-id="487ec-111">O `Start-Transcript` cmdlet cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="487ec-111">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="487ec-112">A transcrição inclui todo comando que o usuário digita e todos os valores de saída que aparecem no console.</span><span class="sxs-lookup"><span data-stu-id="487ec-112">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="487ec-113">A partir do Windows PowerShell 5,0, `Start-Transcript` inclui o nome do host no arquivo de todas as transcrições geradas.</span><span class="sxs-lookup"><span data-stu-id="487ec-113">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="487ec-114">Isso é especialmente útil quando o registro em log da sua empresa é centralizado.</span><span class="sxs-lookup"><span data-stu-id="487ec-114">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="487ec-115">Os arquivos criados pelo `Start-Transcript` cmdlet incluem caracteres aleatórios em nomes para evitar possíveis substituições ou duplicação quando duas ou mais transcrições são iniciadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="487ec-115">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="487ec-116">Isso também impede a descoberta não autorizada de transcrições armazenadas em um compartilhamento de arquivos centralizado.</span><span class="sxs-lookup"><span data-stu-id="487ec-116">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

## <span data-ttu-id="487ec-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="487ec-117">EXAMPLES</span></span>

### <span data-ttu-id="487ec-118">Exemplo 1: iniciar um arquivo de transcrição com as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="487ec-118">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="487ec-119">Este comando inicia uma transcrição no local de arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="487ec-119">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="487ec-120">Exemplo 2: iniciar um arquivo de transcrição em um local específico</span><span class="sxs-lookup"><span data-stu-id="487ec-120">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="487ec-121">Esse comando inicia uma transcrição no `Transcript0.txt` arquivo em `C:\transcripts` .</span><span class="sxs-lookup"><span data-stu-id="487ec-121">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="487ec-122">Como o parâmetro **NoClobber** é usado, o comando impede que todos os arquivos existentes sejam substituídos.</span><span class="sxs-lookup"><span data-stu-id="487ec-122">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="487ec-123">Se o `Transcript0.txt` arquivo já existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="487ec-123">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="487ec-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="487ec-124">PARAMETERS</span></span>

### <span data-ttu-id="487ec-125">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="487ec-125">-Append</span></span>

<span data-ttu-id="487ec-126">Indica que esse cmdlet adiciona a nova transcrição ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="487ec-126">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="487ec-127">Use o parâmetro **path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="487ec-127">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="487ec-128">-Force</span><span class="sxs-lookup"><span data-stu-id="487ec-128">-Force</span></span>

<span data-ttu-id="487ec-129">Permite que o cmdlet acrescente a transcrição a um arquivo somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="487ec-129">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="487ec-130">Quando usado em um arquivo somente leitura, o cmdlet altera a permissão do arquivo para leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="487ec-130">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="487ec-131">O cmdlet não pode substituir restrições de segurança quando esse parâmetro é usado.</span><span class="sxs-lookup"><span data-stu-id="487ec-131">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="487ec-132">-IncludeInvocationHeader</span><span class="sxs-lookup"><span data-stu-id="487ec-132">-IncludeInvocationHeader</span></span>

<span data-ttu-id="487ec-133">Indica que esse cmdlet registra o carimbo de data/hora quando comandos são executados.</span><span class="sxs-lookup"><span data-stu-id="487ec-133">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="487ec-134">-UseMinimalHeader</span><span class="sxs-lookup"><span data-stu-id="487ec-134">-UseMinimalHeader</span></span>

<span data-ttu-id="487ec-135">Preceda um cabeçalho curto para a transcrição, em vez do cabeçalho detalhado incluído por padrão.</span><span class="sxs-lookup"><span data-stu-id="487ec-135">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="487ec-136">Esse parâmetro foi adicionado no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="487ec-136">This parameter was added in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="487ec-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="487ec-137">-LiteralPath</span></span>

<span data-ttu-id="487ec-138">Especifica um local para o arquivo de transcrição.</span><span class="sxs-lookup"><span data-stu-id="487ec-138">Specifies a location to the transcript file.</span></span> <span data-ttu-id="487ec-139">Ao contrário do parâmetro **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="487ec-139">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="487ec-140">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="487ec-140">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="487ec-141">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="487ec-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="487ec-142">As aspas simples informam o PowerShell para não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="487ec-142">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="487ec-143">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="487ec-143">-NoClobber</span></span>

<span data-ttu-id="487ec-144">Indica que esse cmdlet não substituirá um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="487ec-144">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="487ec-145">Por padrão, se um arquivo de transcrição existir no caminho especificado, `Start-Transcript` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="487ec-145">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="487ec-146">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="487ec-146">-OutputDirectory</span></span>

<span data-ttu-id="487ec-147">Especifica um caminho e uma pasta específicos para salvar uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="487ec-147">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="487ec-148">O PowerShell atribui automaticamente o nome da transcrição.</span><span class="sxs-lookup"><span data-stu-id="487ec-148">PowerShell automatically assigns the transcript name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="487ec-149">-Path</span><span class="sxs-lookup"><span data-stu-id="487ec-149">-Path</span></span>

<span data-ttu-id="487ec-150">Especifica um local para o arquivo de transcrição.</span><span class="sxs-lookup"><span data-stu-id="487ec-150">Specifies a location to the transcript file.</span></span> <span data-ttu-id="487ec-151">Insira um caminho para um `.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="487ec-151">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="487ec-152">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="487ec-152">Wildcards are not permitted.</span></span>

<span data-ttu-id="487ec-153">Se você não especificar um caminho, o `Start-Transcript` usará o caminho no valor da `$Transcript` variável global.</span><span class="sxs-lookup"><span data-stu-id="487ec-153">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="487ec-154">Se você não tiver criado essa variável, `Start-Transcript` o armazenará as transcrições nos `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="487ec-154">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="487ec-155">Se qualquer um dos diretórios no caminho não existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="487ec-155">If any of the directories in the path do not exist, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="487ec-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="487ec-156">-Confirm</span></span>

<span data-ttu-id="487ec-157">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="487ec-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="487ec-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="487ec-158">-WhatIf</span></span>

<span data-ttu-id="487ec-159">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="487ec-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="487ec-160">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="487ec-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="487ec-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="487ec-161">CommonParameters</span></span>

<span data-ttu-id="487ec-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="487ec-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="487ec-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="487ec-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="487ec-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="487ec-164">INPUTS</span></span>

### <span data-ttu-id="487ec-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="487ec-165">None</span></span>

<span data-ttu-id="487ec-166">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="487ec-166">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="487ec-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="487ec-167">OUTPUTS</span></span>

### <span data-ttu-id="487ec-168">System.String</span><span class="sxs-lookup"><span data-stu-id="487ec-168">System.String</span></span>

<span data-ttu-id="487ec-169">Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de confirmação e o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="487ec-169">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="487ec-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="487ec-170">NOTES</span></span>

<span data-ttu-id="487ec-171">Para interromper uma transcrição, use o `Stop-Transcript` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="487ec-171">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="487ec-172">Para registrar uma sessão inteira, adicione o `Start-Transcript` comando ao seu perfil.</span><span class="sxs-lookup"><span data-stu-id="487ec-172">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="487ec-173">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="487ec-173">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="487ec-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="487ec-174">RELATED LINKS</span></span>

[<span data-ttu-id="487ec-175">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="487ec-175">Stop-Transcript</span></span>](Stop-Transcript.md)

