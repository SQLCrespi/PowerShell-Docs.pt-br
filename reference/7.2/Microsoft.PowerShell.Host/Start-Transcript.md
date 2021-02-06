---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: d0987c77e3c2bb8cee08e67610cd6fe4fedc36e4
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "99603757"
---
# <span data-ttu-id="8eb76-102">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="8eb76-102">Start-Transcript</span></span>

## <span data-ttu-id="8eb76-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="8eb76-103">Synopsis</span></span>
<span data-ttu-id="8eb76-104">Cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="8eb76-104">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="8eb76-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eb76-105">Syntax</span></span>

### <span data-ttu-id="8eb76-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="8eb76-106">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="8eb76-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="8eb76-107">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="8eb76-108">ByOutputDirectory</span><span class="sxs-lookup"><span data-stu-id="8eb76-108">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="8eb76-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="8eb76-109">Description</span></span>

<span data-ttu-id="8eb76-110">O `Start-Transcript` cmdlet cria um registro de toda ou parte de uma sessão do PowerShell para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="8eb76-110">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="8eb76-111">A transcrição inclui todo comando que o usuário digita e todos os valores de saída que aparecem no console.</span><span class="sxs-lookup"><span data-stu-id="8eb76-111">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="8eb76-112">A partir do Windows PowerShell 5,0, `Start-Transcript` inclui o nome do host no arquivo de todas as transcrições geradas.</span><span class="sxs-lookup"><span data-stu-id="8eb76-112">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="8eb76-113">Isso é especialmente útil quando o registro em log da sua empresa é centralizado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-113">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="8eb76-114">Os arquivos criados pelo `Start-Transcript` cmdlet incluem caracteres aleatórios em nomes para evitar possíveis substituições ou duplicação quando duas ou mais transcrições são iniciadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="8eb76-114">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="8eb76-115">Isso também impede a descoberta não autorizada de transcrições armazenadas em um compartilhamento de arquivos centralizado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-115">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

<span data-ttu-id="8eb76-116">Se o arquivo de destino não tiver uma marca de ordem de byte (BOM), o `Start-Transcript` padrão será `Utf8NoBom` codificar no arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="8eb76-116">If the target file doesn't have a Byte Order Mark (BOM), `Start-Transcript` defaults to `Utf8NoBom` encoding in the target file.</span></span>

## <span data-ttu-id="8eb76-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8eb76-117">Examples</span></span>

### <span data-ttu-id="8eb76-118">Exemplo 1: iniciar um arquivo de transcrição com as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="8eb76-118">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="8eb76-119">Este comando inicia uma transcrição no local de arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="8eb76-119">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="8eb76-120">Exemplo 2: iniciar um arquivo de transcrição em um local específico</span><span class="sxs-lookup"><span data-stu-id="8eb76-120">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="8eb76-121">Esse comando inicia uma transcrição no `Transcript0.txt` arquivo em `C:\transcripts` .</span><span class="sxs-lookup"><span data-stu-id="8eb76-121">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="8eb76-122">Como o parâmetro **NoClobber** é usado, o comando impede que todos os arquivos existentes sejam substituídos.</span><span class="sxs-lookup"><span data-stu-id="8eb76-122">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="8eb76-123">Se o `Transcript0.txt` arquivo já existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="8eb76-123">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="8eb76-124">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8eb76-124">Parameters</span></span>

### <span data-ttu-id="8eb76-125">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="8eb76-125">-Append</span></span>

<span data-ttu-id="8eb76-126">Indica que esse cmdlet adiciona a nova transcrição ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="8eb76-126">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="8eb76-127">Use o parâmetro **path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8eb76-127">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="8eb76-128">-Force</span><span class="sxs-lookup"><span data-stu-id="8eb76-128">-Force</span></span>

<span data-ttu-id="8eb76-129">Permite que o cmdlet acrescente a transcrição a um arquivo somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="8eb76-129">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="8eb76-130">Quando usado em um arquivo somente leitura, o cmdlet altera a permissão do arquivo para leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="8eb76-130">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="8eb76-131">O cmdlet não pode substituir restrições de segurança quando esse parâmetro é usado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-131">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="8eb76-132">-IncludeInvocationHeader</span><span class="sxs-lookup"><span data-stu-id="8eb76-132">-IncludeInvocationHeader</span></span>

<span data-ttu-id="8eb76-133">Indica que esse cmdlet registra o carimbo de data/hora quando comandos são executados.</span><span class="sxs-lookup"><span data-stu-id="8eb76-133">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="8eb76-134">-UseMinimalHeader</span><span class="sxs-lookup"><span data-stu-id="8eb76-134">-UseMinimalHeader</span></span>

<span data-ttu-id="8eb76-135">Preceda um cabeçalho curto para a transcrição, em vez do cabeçalho detalhado incluído por padrão.</span><span class="sxs-lookup"><span data-stu-id="8eb76-135">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="8eb76-136">Esse parâmetro foi adicionado no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="8eb76-136">This parameter was added in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="8eb76-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8eb76-137">-LiteralPath</span></span>

<span data-ttu-id="8eb76-138">Especifica um local para o arquivo de transcrição.</span><span class="sxs-lookup"><span data-stu-id="8eb76-138">Specifies a location to the transcript file.</span></span> <span data-ttu-id="8eb76-139">Ao contrário do parâmetro **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-139">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="8eb76-140">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="8eb76-140">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8eb76-141">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8eb76-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8eb76-142">As aspas simples informam o PowerShell para não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="8eb76-142">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8eb76-143">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="8eb76-143">-NoClobber</span></span>

<span data-ttu-id="8eb76-144">Indica que esse cmdlet não substituirá um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="8eb76-144">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="8eb76-145">Por padrão, se um arquivo de transcrição existir no caminho especificado, `Start-Transcript` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="8eb76-145">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="8eb76-146">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="8eb76-146">-OutputDirectory</span></span>

<span data-ttu-id="8eb76-147">Especifica um caminho e uma pasta específicos para salvar uma transcrição.</span><span class="sxs-lookup"><span data-stu-id="8eb76-147">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="8eb76-148">O PowerShell atribui automaticamente o nome da transcrição.</span><span class="sxs-lookup"><span data-stu-id="8eb76-148">PowerShell automatically assigns the transcript name.</span></span>

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

### <span data-ttu-id="8eb76-149">-Path</span><span class="sxs-lookup"><span data-stu-id="8eb76-149">-Path</span></span>

<span data-ttu-id="8eb76-150">Especifica um local para o arquivo de transcrição.</span><span class="sxs-lookup"><span data-stu-id="8eb76-150">Specifies a location to the transcript file.</span></span> <span data-ttu-id="8eb76-151">Insira um caminho para um `.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="8eb76-151">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="8eb76-152">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8eb76-152">Wildcards are not permitted.</span></span>

<span data-ttu-id="8eb76-153">Se você não especificar um caminho, o `Start-Transcript` usará o caminho no valor da `$Transcript` variável global.</span><span class="sxs-lookup"><span data-stu-id="8eb76-153">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="8eb76-154">Se você não tiver criado essa variável, `Start-Transcript` o armazenará as transcrições nos `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="8eb76-154">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="8eb76-155">Se qualquer um dos diretórios no caminho não existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="8eb76-155">If any of the directories in the path do not exist, the command fails.</span></span>

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

### <span data-ttu-id="8eb76-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8eb76-156">-Confirm</span></span>

<span data-ttu-id="8eb76-157">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8eb76-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8eb76-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8eb76-158">-WhatIf</span></span>

<span data-ttu-id="8eb76-159">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8eb76-160">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8eb76-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8eb76-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8eb76-161">CommonParameters</span></span>

<span data-ttu-id="8eb76-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8eb76-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8eb76-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8eb76-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8eb76-164">Entradas</span><span class="sxs-lookup"><span data-stu-id="8eb76-164">Inputs</span></span>

### <span data-ttu-id="8eb76-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8eb76-165">None</span></span>

<span data-ttu-id="8eb76-166">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8eb76-166">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8eb76-167">Saídas</span><span class="sxs-lookup"><span data-stu-id="8eb76-167">Outputs</span></span>

### <span data-ttu-id="8eb76-168">System.String</span><span class="sxs-lookup"><span data-stu-id="8eb76-168">System.String</span></span>

<span data-ttu-id="8eb76-169">Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de confirmação e o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="8eb76-169">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="8eb76-170">Observações</span><span class="sxs-lookup"><span data-stu-id="8eb76-170">Notes</span></span>

<span data-ttu-id="8eb76-171">Para interromper uma transcrição, use o `Stop-Transcript` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8eb76-171">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="8eb76-172">Para registrar uma sessão inteira, adicione o `Start-Transcript` comando ao seu perfil.</span><span class="sxs-lookup"><span data-stu-id="8eb76-172">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="8eb76-173">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8eb76-173">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="8eb76-174">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="8eb76-174">Related Links</span></span>

[<span data-ttu-id="8eb76-175">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="8eb76-175">Stop-Transcript</span></span>](Stop-Transcript.md)
