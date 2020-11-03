---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: fa3ea8f965ea8089defa5fde7b88b18f00cd83bc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194715"
---
# <span data-ttu-id="99f89-103">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="99f89-103">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="99f89-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="99f89-104">SYNOPSIS</span></span>
<span data-ttu-id="99f89-105">Obtém informações sobre a assinatura Authenticode de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-105">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="99f89-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99f89-106">SYNTAX</span></span>

### <span data-ttu-id="99f89-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="99f89-107">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="99f89-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="99f89-108">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="99f89-109">ByContent</span><span class="sxs-lookup"><span data-stu-id="99f89-109">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="99f89-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99f89-110">DESCRIPTION</span></span>

<span data-ttu-id="99f89-111">O `Get-AuthenticodeSignature` cmdlet obtém informações sobre a assinatura Authenticode para um conteúdo de arquivo ou arquivo como uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="99f89-111">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="99f89-112">Se o arquivo não estiver assinado as informações serão recuperadas, mas os campos ficarão vazios.</span><span class="sxs-lookup"><span data-stu-id="99f89-112">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="99f89-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="99f89-113">EXAMPLES</span></span>

### <span data-ttu-id="99f89-114">Exemplo 1: obter a assinatura Authenticode para um arquivo</span><span class="sxs-lookup"><span data-stu-id="99f89-114">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="99f89-115">Este comando obtém informações sobre a assinatura Authenticode no arquivo NewScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="99f89-115">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="99f89-116">Ele usa o parâmetro **FilePath** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-116">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="99f89-117">Exemplo 2: obter a assinatura Authenticode para vários arquivos</span><span class="sxs-lookup"><span data-stu-id="99f89-117">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="99f89-118">Este comando obtém informações sobre a assinatura Authenticode para os quatro arquivos listados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="99f89-118">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="99f89-119">Neste exemplo, o nome do parâmetro **FilePath** , que é opcional, é omitido.</span><span class="sxs-lookup"><span data-stu-id="99f89-119">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="99f89-120">Exemplo 3: obter apenas assinaturas de Authenticode válidas para vários arquivos</span><span class="sxs-lookup"><span data-stu-id="99f89-120">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="99f89-121">Esse comando lista todos os arquivos no `$PSHOME` diretório que têm uma assinatura Authenticode válida.</span><span class="sxs-lookup"><span data-stu-id="99f89-121">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="99f89-122">A `$PSHOME` variável automática contém o caminho para o diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f89-122">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="99f89-123">O comando usa o `Get-ChildItem` cmdlet para obter os arquivos no `$PSHOME` diretório.</span><span class="sxs-lookup"><span data-stu-id="99f89-123">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="99f89-124">Ele usa um padrão de *.*</span><span class="sxs-lookup"><span data-stu-id="99f89-124">It uses a pattern of *.*</span></span> <span data-ttu-id="99f89-125">para excluir diretórios (embora também exclua arquivos sem um ponto no nome do arquivo).</span><span class="sxs-lookup"><span data-stu-id="99f89-125">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="99f89-126">O comando usa um operador de pipeline ( `|` ) para enviar os arquivos `$PSHOME` para o `ForEach-Object` cmdlet, onde `Get-AuthenticodeSignature` é chamado para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-126">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="99f89-127">Os resultados do `Get-AuthenticodeSignature` comando são enviados para um `Where-Object` comando que seleciona apenas os objetos de assinatura com um status válido.</span><span class="sxs-lookup"><span data-stu-id="99f89-127">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="99f89-128">Exemplo 4: obter a assinatura Authenticode para um conteúdo de arquivo especificado como matriz de bytes</span><span class="sxs-lookup"><span data-stu-id="99f89-128">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="99f89-129">Esse comando obtém informações sobre a assinatura Authenticode para o conteúdo de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-129">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="99f89-130">Neste exemplo, a extensão de arquivo é especificada junto com o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-130">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="99f89-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99f89-131">PARAMETERS</span></span>

### <span data-ttu-id="99f89-132">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="99f89-132">-Content</span></span>

<span data-ttu-id="99f89-133">Conteúdo de um arquivo como uma matriz de bytes para a qual a assinatura Authenticode é recuperada.</span><span class="sxs-lookup"><span data-stu-id="99f89-133">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="99f89-134">Esse parâmetro deve ser usado com o parâmetro **SourcePathOrExtension** .</span><span class="sxs-lookup"><span data-stu-id="99f89-134">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="99f89-135">O conteúdo do arquivo deve estar no formato Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="99f89-135">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99f89-136">-FilePath</span><span class="sxs-lookup"><span data-stu-id="99f89-136">-FilePath</span></span>

<span data-ttu-id="99f89-137">Especifica o caminho para o arquivo a ser examinado.</span><span class="sxs-lookup"><span data-stu-id="99f89-137">Specifies the path to the file to examine.</span></span> <span data-ttu-id="99f89-138">Caracteres curinga são permitidos, mas eles devem levar a um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f89-138">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="99f89-139">Não é necessário digitar **FilePath** na linha de comando quando você especifica um valor para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="99f89-139">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="99f89-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="99f89-140">-LiteralPath</span></span>

<span data-ttu-id="99f89-141">Especifica o caminho para o arquivo que está sendo examinado.</span><span class="sxs-lookup"><span data-stu-id="99f89-141">Specifies the path to the file being examined.</span></span> <span data-ttu-id="99f89-142">Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="99f89-142">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="99f89-143">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="99f89-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="99f89-144">Se o caminho incluir um caractere de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="99f89-144">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="99f89-145">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="99f89-145">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99f89-146">-SourcePathOrExtension</span><span class="sxs-lookup"><span data-stu-id="99f89-146">-SourcePathOrExtension</span></span>

<span data-ttu-id="99f89-147">Caminho para o arquivo ou tipo de arquivo do conteúdo para o qual a assinatura Authenticode é recuperada.</span><span class="sxs-lookup"><span data-stu-id="99f89-147">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="99f89-148">Esse parâmetro é usado com o **conteúdo** em que o conteúdo do arquivo é passado como uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="99f89-148">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="99f89-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="99f89-149">CommonParameters</span></span>

<span data-ttu-id="99f89-150">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99f89-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99f89-151">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="99f89-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="99f89-152">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="99f89-152">INPUTS</span></span>

### <span data-ttu-id="99f89-153">System.String</span><span class="sxs-lookup"><span data-stu-id="99f89-153">System.String</span></span>

<span data-ttu-id="99f89-154">É possível canalizar uma cadeia de caracteres que contém um caminho de arquivo para `Get-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="99f89-154">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="99f89-155">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="99f89-155">OUTPUTS</span></span>

### <span data-ttu-id="99f89-156">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="99f89-156">System.Management.Automation.Signature</span></span>

<span data-ttu-id="99f89-157">`Get-AuthenticodeSignature` Retorna um objeto de assinatura para cada assinatura obtida.</span><span class="sxs-lookup"><span data-stu-id="99f89-157">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="99f89-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="99f89-158">NOTES</span></span>

<span data-ttu-id="99f89-159">Para obter informações sobre assinaturas Authenticode no PowerShell, consulte [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="99f89-159">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="99f89-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="99f89-160">RELATED LINKS</span></span>

[<span data-ttu-id="99f89-161">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="99f89-161">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="99f89-162">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="99f89-162">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="99f89-163">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="99f89-163">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="99f89-164">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="99f89-164">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="99f89-165">about_Signing</span><span class="sxs-lookup"><span data-stu-id="99f89-165">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)

