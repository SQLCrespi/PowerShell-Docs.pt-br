---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195253"
---
# <span data-ttu-id="2b264-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="2b264-103">Export-Clixml</span></span>

## <span data-ttu-id="2b264-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2b264-104">SYNOPSIS</span></span>
<span data-ttu-id="2b264-105">Cria uma representação baseada em XML de um objeto ou objetos e armazena-a em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="2b264-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2b264-106">SYNTAX</span></span>

### <span data-ttu-id="2b264-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="2b264-107">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2b264-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="2b264-108">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2b264-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2b264-109">DESCRIPTION</span></span>

<span data-ttu-id="2b264-110">O `Export-Clixml` cmdlet cria uma representação baseada em XML Common Language Infrastructure (CLI) de um objeto ou objetos e a armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="2b264-111">Você pode usar o `Import-Clixml` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="2b264-112">Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="2b264-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="2b264-113">Esse cmdlet é semelhante a `ConvertTo-Xml` , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="2b264-114">`ConvertTo-XML` Retorna o XML, para que você possa continuar a processá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b264-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="2b264-115">Um uso valioso do `Export-Clixml` em computadores com Windows é exportar credenciais e proteger cadeias de caracteres com segurança como XML.</span><span class="sxs-lookup"><span data-stu-id="2b264-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="2b264-116">Para obter um exemplo, consulte o exemplo 3.</span><span class="sxs-lookup"><span data-stu-id="2b264-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="2b264-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2b264-117">EXAMPLES</span></span>

### <span data-ttu-id="2b264-118">Exemplo 1: exportar uma cadeia de caracteres para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="2b264-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="2b264-119">Este exemplo cria um arquivo XML que armazena no diretório atual, uma representação da cadeia de caracteres que **é um teste** .</span><span class="sxs-lookup"><span data-stu-id="2b264-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="2b264-120">A cadeia de caracteres `This is a test` é enviada pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="2b264-120">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="2b264-121">`Export-Clixml` usa o parâmetro **path** para criar um arquivo XML chamado `sample.xml` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2b264-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="2b264-122">Exemplo 2: exportar um objeto para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="2b264-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="2b264-123">Este exemplo mostra como exportar um objeto para um arquivo XML e, em seguida, criar um objeto importando o XML do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="2b264-124">O `Get-Acl` cmdlet obtém o descritor de segurança do `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="2b264-125">Ele envia o objeto para baixo no pipeline para o qual passar o descritor de segurança `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="2b264-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="2b264-126">A representação baseada em XML do objeto é armazenada em um arquivo chamado `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="2b264-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="2b264-127">O `Import-Clixml` cmdlet cria um objeto do XML no `FileACL.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b264-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="2b264-128">Em seguida, ele salva o objeto na `$fileacl` variável.</span><span class="sxs-lookup"><span data-stu-id="2b264-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="2b264-129">Exemplo 3: criptografar um objeto de credencial exportado no Windows</span><span class="sxs-lookup"><span data-stu-id="2b264-129">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="2b264-130">Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="2b264-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b264-131">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="2b264-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="2b264-132">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2b264-132">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="2b264-133">Isso fornece alguma ofuscação, mas não fornece criptografia.</span><span class="sxs-lookup"><span data-stu-id="2b264-133">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="2b264-134">O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows.</span><span class="sxs-lookup"><span data-stu-id="2b264-134">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="2b264-135">A criptografia garante que apenas sua conta de usuário somente no computador possa descriptografar o conteúdo do objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="2b264-135">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="2b264-136">O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="2b264-136">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="2b264-137">No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="2b264-137">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="2b264-138">Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.</span><span class="sxs-lookup"><span data-stu-id="2b264-138">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="2b264-139">Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="2b264-139">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="2b264-140">Para importar a credencial automaticamente para o script, execute os dois comandos finais.</span><span class="sxs-lookup"><span data-stu-id="2b264-140">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="2b264-141">Execute `Import-Clixml` para importar o objeto de credencial protegido para o script.</span><span class="sxs-lookup"><span data-stu-id="2b264-141">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="2b264-142">Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.</span><span class="sxs-lookup"><span data-stu-id="2b264-142">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="2b264-143">Exemplo 4: exportando um objeto de credencial no Linux ou no macOS</span><span class="sxs-lookup"><span data-stu-id="2b264-143">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="2b264-144">Neste exemplo, criamos um **PSCredential** na `$Credential` variável usando o `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2b264-144">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2b264-145">Em seguida, usamos `Export-Clixml` para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="2b264-145">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b264-146">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="2b264-146">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="2b264-147">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2b264-147">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="2b264-148">Isso fornece alguma ofuscação, mas não fornece criptografia.</span><span class="sxs-lookup"><span data-stu-id="2b264-148">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

<span data-ttu-id="2b264-149">A saída de `Get-Content` neste exemplo foi truncada para se concentrar nas informações de credenciais no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="2b264-149">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="2b264-150">Observe que o valor de texto sem formatação da senha é armazenado no arquivo XML como uma matriz de caracteres Unicode como comprovado pelo `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="2b264-150">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="2b264-151">Portanto, o valor é codificado, mas não criptografado.</span><span class="sxs-lookup"><span data-stu-id="2b264-151">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="2b264-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2b264-152">PARAMETERS</span></span>

### <span data-ttu-id="2b264-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2b264-153">-Confirm</span></span>

<span data-ttu-id="2b264-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2b264-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2b264-155">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="2b264-155">-Depth</span></span>

<span data-ttu-id="2b264-156">Especifica quantos níveis de objetos contidos estão incluídos na representação XML.</span><span class="sxs-lookup"><span data-stu-id="2b264-156">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="2b264-157">O valor padrão é `2`.</span><span class="sxs-lookup"><span data-stu-id="2b264-157">The default value is `2`.</span></span>

<span data-ttu-id="2b264-158">O valor padrão pode ser substituído para o tipo de objeto nos `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="2b264-158">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="2b264-159">Para obter mais informações, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="2b264-159">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="2b264-160">-Codificação</span><span class="sxs-lookup"><span data-stu-id="2b264-160">-Encoding</span></span>

<span data-ttu-id="2b264-161">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2b264-161">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="2b264-162">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="2b264-162">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="2b264-163">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2b264-163">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2b264-164">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="2b264-164">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="2b264-165">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="2b264-165">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="2b264-166">`bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="2b264-166">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="2b264-167">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="2b264-167">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="2b264-168">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="2b264-168">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="2b264-169">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="2b264-169">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="2b264-170">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2b264-170">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="2b264-171">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="2b264-171">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="2b264-172">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="2b264-172">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="2b264-173">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="2b264-173">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="2b264-174">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="2b264-174">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="2b264-175">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="2b264-175">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="2b264-176">O **UTF-7** \* não é mais recomendado para uso.</span><span class="sxs-lookup"><span data-stu-id="2b264-176">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="2b264-177">No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro de **codificação** .</span><span class="sxs-lookup"><span data-stu-id="2b264-177">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2b264-178">-Force</span><span class="sxs-lookup"><span data-stu-id="2b264-178">-Force</span></span>

<span data-ttu-id="2b264-179">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2b264-179">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="2b264-180">Faz com que o cmdlet limpe o atributo somente leitura do arquivo de saída, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2b264-180">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="2b264-181">O cmdlet tentará redefinir o atributo somente leitura quando o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="2b264-181">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="2b264-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2b264-182">-InputObject</span></span>

<span data-ttu-id="2b264-183">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="2b264-183">Specifies the object to be converted.</span></span> <span data-ttu-id="2b264-184">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="2b264-184">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="2b264-185">Você também pode canalizar objetos para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="2b264-185">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="2b264-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2b264-186">-LiteralPath</span></span>

<span data-ttu-id="2b264-187">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="2b264-187">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="2b264-188">Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="2b264-188">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="2b264-189">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="2b264-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2b264-190">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="2b264-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2b264-191">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="2b264-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2b264-192">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="2b264-192">-NoClobber</span></span>

<span data-ttu-id="2b264-193">Indica que o cmdlet não substitui o conteúdo de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="2b264-193">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="2b264-194">Por padrão, se um arquivo existir no caminho especificado, `Export-Clixml` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="2b264-194">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="2b264-195">-Path</span><span class="sxs-lookup"><span data-stu-id="2b264-195">-Path</span></span>

<span data-ttu-id="2b264-196">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="2b264-196">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="2b264-197">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2b264-197">-WhatIf</span></span>

<span data-ttu-id="2b264-198">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2b264-198">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2b264-199">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2b264-199">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2b264-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2b264-200">CommonParameters</span></span>

<span data-ttu-id="2b264-201">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2b264-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2b264-202">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2b264-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2b264-203">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2b264-203">INPUTS</span></span>

### <span data-ttu-id="2b264-204">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="2b264-204">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2b264-205">Você pode canalizar qualquer objeto para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="2b264-205">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="2b264-206">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2b264-206">OUTPUTS</span></span>

### <span data-ttu-id="2b264-207">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="2b264-207">System.IO.FileInfo</span></span>

<span data-ttu-id="2b264-208">`Export-Clixml` Cria um arquivo que contém o XML.</span><span class="sxs-lookup"><span data-stu-id="2b264-208">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="2b264-209">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2b264-209">NOTES</span></span>

## <span data-ttu-id="2b264-210">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2b264-210">RELATED LINKS</span></span>

[<span data-ttu-id="2b264-211">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="2b264-211">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="2b264-212">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="2b264-212">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="2b264-213">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="2b264-213">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="2b264-214">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="2b264-214">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="2b264-215">Join-Path</span><span class="sxs-lookup"><span data-stu-id="2b264-215">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="2b264-216">Armazenar credenciais com segurança no disco</span><span class="sxs-lookup"><span data-stu-id="2b264-216">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="2b264-217">Usar o PowerShell para passar credenciais para sistemas herdados</span><span class="sxs-lookup"><span data-stu-id="2b264-217">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="2b264-218">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="2b264-218">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
