---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193832"
---
# <span data-ttu-id="3b3db-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="3b3db-103">Export-Clixml</span></span>

## <span data-ttu-id="3b3db-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3b3db-104">SYNOPSIS</span></span>
<span data-ttu-id="3b3db-105">Cria uma representação baseada em XML de um objeto ou objetos e armazena-a em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="3b3db-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b3db-106">SYNTAX</span></span>

### <span data-ttu-id="3b3db-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="3b3db-107">ByPath (Default)</span></span>

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3b3db-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b3db-108">ByLiteralPath</span></span>

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3b3db-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b3db-109">DESCRIPTION</span></span>

<span data-ttu-id="3b3db-110">O `Export-Clixml` cmdlet cria uma representação baseada em XML Common Language Infrastructure (CLI) de um objeto ou objetos e a armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="3b3db-111">Você pode usar o `Import-Clixml` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="3b3db-112">Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="3b3db-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="3b3db-113">Esse cmdlet é semelhante a `ConvertTo-Xml` , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="3b3db-114">`ConvertTo-XML` Retorna o XML, para que você possa continuar a processá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b3db-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="3b3db-115">Um uso valioso do `Export-Clixml` em computadores com Windows é exportar credenciais e proteger cadeias de caracteres com segurança como XML.</span><span class="sxs-lookup"><span data-stu-id="3b3db-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="3b3db-116">Para obter um exemplo, consulte o exemplo 3.</span><span class="sxs-lookup"><span data-stu-id="3b3db-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="3b3db-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3b3db-117">EXAMPLES</span></span>

### <span data-ttu-id="3b3db-118">Exemplo 1: exportar uma cadeia de caracteres para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="3b3db-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="3b3db-119">Este exemplo cria um arquivo XML que armazena no diretório atual, uma representação da cadeia de caracteres que **é um teste** .</span><span class="sxs-lookup"><span data-stu-id="3b3db-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="3b3db-120">A cadeia de caracteres **é um teste** que é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="3b3db-120">The string **This is a test** is sent down the pipeline.</span></span> <span data-ttu-id="3b3db-121">`Export-Clixml` usa o parâmetro **path** para criar um arquivo XML chamado `sample.xml` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="3b3db-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="3b3db-122">Exemplo 2: exportar um objeto para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="3b3db-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="3b3db-123">Este exemplo mostra como exportar um objeto para um arquivo XML e, em seguida, criar um objeto importando o XML do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="3b3db-124">O `Get-Acl` cmdlet obtém o descritor de segurança do `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="3b3db-125">Ele envia o objeto para baixo no pipeline para o qual passar o descritor de segurança `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="3b3db-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="3b3db-126">A representação baseada em XML do objeto é armazenada em um arquivo chamado `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="3b3db-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="3b3db-127">O `Import-Clixml` cmdlet cria um objeto do XML no `FileACL.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b3db-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="3b3db-128">Em seguida, ele salva o objeto na `$fileacl` variável.</span><span class="sxs-lookup"><span data-stu-id="3b3db-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="3b3db-129">Exemplo 3: criptografar um objeto de credencial exportado</span><span class="sxs-lookup"><span data-stu-id="3b3db-129">Example 3: Encrypt an exported credential object</span></span>

<span data-ttu-id="3b3db-130">Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="3b3db-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b3db-131">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="3b3db-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="3b3db-132">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="3b3db-132">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="3b3db-133">O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows.</span><span class="sxs-lookup"><span data-stu-id="3b3db-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="3b3db-134">A criptografia garante que apenas sua conta de usuário somente no computador possa descriptografar o conteúdo do objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="3b3db-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span> <span data-ttu-id="3b3db-135">O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="3b3db-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="3b3db-136">No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="3b3db-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="3b3db-137">Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.</span><span class="sxs-lookup"><span data-stu-id="3b3db-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="3b3db-138">Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="3b3db-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="3b3db-139">Para importar a credencial automaticamente para o script, execute os dois comandos finais.</span><span class="sxs-lookup"><span data-stu-id="3b3db-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="3b3db-140">Execute `Import-Clixml` para importar o objeto de credencial protegido para o script.</span><span class="sxs-lookup"><span data-stu-id="3b3db-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="3b3db-141">Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.</span><span class="sxs-lookup"><span data-stu-id="3b3db-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="3b3db-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b3db-142">PARAMETERS</span></span>

### <span data-ttu-id="3b3db-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3b3db-143">-Confirm</span></span>

<span data-ttu-id="3b3db-144">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b3db-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3b3db-145">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="3b3db-145">-Depth</span></span>

<span data-ttu-id="3b3db-146">Especifica quantos níveis de objetos contidos estão incluídos na representação XML.</span><span class="sxs-lookup"><span data-stu-id="3b3db-146">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="3b3db-147">O valor padrão é `2`.</span><span class="sxs-lookup"><span data-stu-id="3b3db-147">The default value is `2`.</span></span>

<span data-ttu-id="3b3db-148">O valor padrão pode ser substituído para o tipo de objeto nos `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="3b3db-148">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="3b3db-149">Para obter mais informações, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="3b3db-149">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-150">-Codificação</span><span class="sxs-lookup"><span data-stu-id="3b3db-150">-Encoding</span></span>

<span data-ttu-id="3b3db-151">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="3b3db-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="3b3db-152">O valor padrão é **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="3b3db-152">The default value is **Unicode** .</span></span>

<span data-ttu-id="3b3db-153">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="3b3db-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3b3db-154">`ASCII` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="3b3db-154">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3b3db-155">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="3b3db-155">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="3b3db-156">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="3b3db-156">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="3b3db-157">`OEM` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="3b3db-157">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="3b3db-158">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="3b3db-158">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="3b3db-159">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="3b3db-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="3b3db-160">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="3b3db-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="3b3db-161">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="3b3db-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-162">-Force</span><span class="sxs-lookup"><span data-stu-id="3b3db-162">-Force</span></span>

<span data-ttu-id="3b3db-163">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="3b3db-163">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="3b3db-164">Faz com que o cmdlet limpe o atributo somente leitura do arquivo de saída, se necessário.</span><span class="sxs-lookup"><span data-stu-id="3b3db-164">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="3b3db-165">O cmdlet tentará redefinir o atributo somente leitura quando o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="3b3db-165">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="3b3db-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3b3db-166">-InputObject</span></span>

<span data-ttu-id="3b3db-167">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="3b3db-167">Specifies the object to be converted.</span></span> <span data-ttu-id="3b3db-168">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="3b3db-168">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="3b3db-169">Você também pode canalizar objetos para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="3b3db-169">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-170">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b3db-170">-LiteralPath</span></span>

<span data-ttu-id="3b3db-171">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="3b3db-171">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="3b3db-172">Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="3b3db-172">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="3b3db-173">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="3b3db-173">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3b3db-174">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3b3db-174">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3b3db-175">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="3b3db-175">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-176">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="3b3db-176">-NoClobber</span></span>

<span data-ttu-id="3b3db-177">Indica que o cmdlet não substitui o conteúdo de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="3b3db-177">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="3b3db-178">Por padrão, se um arquivo existir no caminho especificado, `Export-Clixml` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="3b3db-178">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-179">-Path</span><span class="sxs-lookup"><span data-stu-id="3b3db-179">-Path</span></span>

<span data-ttu-id="3b3db-180">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="3b3db-180">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b3db-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3b3db-181">-WhatIf</span></span>

<span data-ttu-id="3b3db-182">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="3b3db-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3b3db-183">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="3b3db-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3b3db-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3b3db-184">CommonParameters</span></span>

<span data-ttu-id="3b3db-185">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b3db-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b3db-186">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b3db-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b3db-187">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3b3db-187">INPUTS</span></span>

### <span data-ttu-id="3b3db-188">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3b3db-188">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3b3db-189">Você pode canalizar qualquer objeto para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="3b3db-189">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="3b3db-190">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3b3db-190">OUTPUTS</span></span>

### <span data-ttu-id="3b3db-191">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="3b3db-191">System.IO.FileInfo</span></span>

<span data-ttu-id="3b3db-192">`Export-Clixml` Cria um arquivo que contém o XML.</span><span class="sxs-lookup"><span data-stu-id="3b3db-192">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="3b3db-193">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3b3db-193">NOTES</span></span>

## <span data-ttu-id="3b3db-194">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3b3db-194">RELATED LINKS</span></span>

[<span data-ttu-id="3b3db-195">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="3b3db-195">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="3b3db-196">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="3b3db-196">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="3b3db-197">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="3b3db-197">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="3b3db-198">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="3b3db-198">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="3b3db-199">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3b3db-199">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="3b3db-200">Armazenar credenciais com segurança no disco</span><span class="sxs-lookup"><span data-stu-id="3b3db-200">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="3b3db-201">Usar o PowerShell para passar credenciais para sistemas herdados</span><span class="sxs-lookup"><span data-stu-id="3b3db-201">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="3b3db-202">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="3b3db-202">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
