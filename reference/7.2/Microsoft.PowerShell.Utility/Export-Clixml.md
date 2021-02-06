---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 7a0c25197ba00fb05089f855592e7744ef10e9b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595761"
---
# <span data-ttu-id="e3e8d-102">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="e3e8d-102">Export-Clixml</span></span>

## <span data-ttu-id="e3e8d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e3e8d-103">SYNOPSIS</span></span>
<span data-ttu-id="e3e8d-104">Cria uma representação baseada em XML de um objeto ou objetos e armazena-a em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-104">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="e3e8d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3e8d-105">SYNTAX</span></span>

### <span data-ttu-id="e3e8d-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="e3e8d-106">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e3e8d-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3e8d-107">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e3e8d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3e8d-108">DESCRIPTION</span></span>

<span data-ttu-id="e3e8d-109">O `Export-Clixml` cmdlet cria uma representação baseada em XML Common Language Infrastructure (CLI) de um objeto ou objetos e a armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-109">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="e3e8d-110">Você pode usar o `Import-Clixml` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-110">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="e3e8d-111">Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-111">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="e3e8d-112">Esse cmdlet é semelhante a `ConvertTo-Xml` , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-112">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="e3e8d-113">`ConvertTo-XML` Retorna o XML, para que você possa continuar a processá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-113">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="e3e8d-114">Um uso valioso do `Export-Clixml` em computadores com Windows é exportar credenciais e proteger cadeias de caracteres com segurança como XML.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-114">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="e3e8d-115">Para obter um exemplo, consulte o exemplo 3.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-115">For an example, see Example 3.</span></span>

## <span data-ttu-id="e3e8d-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-116">EXAMPLES</span></span>

### <span data-ttu-id="e3e8d-117">Exemplo 1: exportar uma cadeia de caracteres para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="e3e8d-117">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="e3e8d-118">Este exemplo cria um arquivo XML que armazena no diretório atual, uma representação da cadeia de caracteres que **é um teste**.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-118">This example creates an XML file that stores in the current directory, a representation of the string **This is a test**.</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="e3e8d-119">A cadeia de caracteres `This is a test` é enviada pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-119">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="e3e8d-120">`Export-Clixml` usa o parâmetro **path** para criar um arquivo XML chamado `sample.xml` no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-120">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="e3e8d-121">Exemplo 2: exportar um objeto para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="e3e8d-121">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="e3e8d-122">Este exemplo mostra como exportar um objeto para um arquivo XML e, em seguida, criar um objeto importando o XML do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-122">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="e3e8d-123">O `Get-Acl` cmdlet obtém o descritor de segurança do `Test.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-123">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="e3e8d-124">Ele envia o objeto para baixo no pipeline para o qual passar o descritor de segurança `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-124">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="e3e8d-125">A representação baseada em XML do objeto é armazenada em um arquivo chamado `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-125">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="e3e8d-126">O `Import-Clixml` cmdlet cria um objeto do XML no `FileACL.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-126">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="e3e8d-127">Em seguida, ele salva o objeto na `$fileacl` variável.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-127">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="e3e8d-128">Exemplo 3: criptografar um objeto de credencial exportado no Windows</span><span class="sxs-lookup"><span data-stu-id="e3e8d-128">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="e3e8d-129">Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-129">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3e8d-130">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-130">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="e3e8d-131">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-131">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="e3e8d-132">Isso fornece alguma ofuscação, mas não fornece criptografia.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-132">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="e3e8d-133">O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="e3e8d-134">A criptografia garante que apenas sua conta de usuário somente no computador possa descriptografar o conteúdo do objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="e3e8d-135">O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="e3e8d-136">No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="e3e8d-137">Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="e3e8d-138">Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="e3e8d-139">Para importar a credencial automaticamente para o script, execute os dois comandos finais.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="e3e8d-140">Execute `Import-Clixml` para importar o objeto de credencial protegido para o script.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="e3e8d-141">Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="e3e8d-142">Exemplo 4: exportando um objeto de credencial no Linux ou no macOS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-142">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="e3e8d-143">Neste exemplo, criamos um **PSCredential** na `$Credential` variável usando o `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-143">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e3e8d-144">Em seguida, usamos `Export-Clixml` para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-144">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3e8d-145">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-145">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="e3e8d-146">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas como um texto simples armazenado como uma matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-146">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="e3e8d-147">Isso fornece alguma ofuscação, mas não fornece criptografia.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-147">This provides some obfuscation but does not provide encryption.</span></span>

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

<span data-ttu-id="e3e8d-148">A saída de `Get-Content` neste exemplo foi truncada para se concentrar nas informações de credenciais no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-148">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="e3e8d-149">Observe que o valor de texto sem formatação da senha é armazenado no arquivo XML como uma matriz de caracteres Unicode como comprovado pelo `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-149">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="e3e8d-150">Portanto, o valor é codificado, mas não criptografado.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-150">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="e3e8d-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-151">PARAMETERS</span></span>

### <span data-ttu-id="e3e8d-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e3e8d-152">-Confirm</span></span>

<span data-ttu-id="e3e8d-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e3e8d-154">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="e3e8d-154">-Depth</span></span>

<span data-ttu-id="e3e8d-155">Especifica quantos níveis de objetos contidos estão incluídos na representação XML.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-155">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="e3e8d-156">O valor padrão é `2`.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-156">The default value is `2`.</span></span>

<span data-ttu-id="e3e8d-157">O valor padrão pode ser substituído para o tipo de objeto nos `Types.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-157">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="e3e8d-158">Para obter mais informações, consulte [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-158">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="e3e8d-159">-Codificação</span><span class="sxs-lookup"><span data-stu-id="e3e8d-159">-Encoding</span></span>

<span data-ttu-id="e3e8d-160">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-160">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="e3e8d-161">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-161">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="e3e8d-162">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="e3e8d-162">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e3e8d-163">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-163">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="e3e8d-164">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-164">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="e3e8d-165">`bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-165">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="e3e8d-166">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-166">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="e3e8d-167">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-167">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="e3e8d-168">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-168">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="e3e8d-169">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-169">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="e3e8d-170">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="e3e8d-170">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e3e8d-171">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="e3e8d-171">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e3e8d-172">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-172">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="e3e8d-173">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-173">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="e3e8d-174">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-174">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="e3e8d-175">O **UTF-7** _ não é mais recomendado para uso.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-175">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="e3e8d-176">No PowerShell 7,1, um aviso será gravado se você especificar `utf7` para o parâmetro _ \*Encoding\*\*.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-176">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="e3e8d-177">-Force</span><span class="sxs-lookup"><span data-stu-id="e3e8d-177">-Force</span></span>

<span data-ttu-id="e3e8d-178">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-178">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="e3e8d-179">Faz com que o cmdlet limpe o atributo somente leitura do arquivo de saída, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-179">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="e3e8d-180">O cmdlet tentará redefinir o atributo somente leitura quando o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-180">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="e3e8d-181">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e3e8d-181">-InputObject</span></span>

<span data-ttu-id="e3e8d-182">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-182">Specifies the object to be converted.</span></span> <span data-ttu-id="e3e8d-183">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-183">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="e3e8d-184">Você também pode canalizar objetos para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-184">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="e3e8d-185">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3e8d-185">-LiteralPath</span></span>

<span data-ttu-id="e3e8d-186">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-186">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="e3e8d-187">Ao contrário do **caminho**, o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-187">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="e3e8d-188">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-188">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e3e8d-189">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-189">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e3e8d-190">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-190">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="e3e8d-191">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="e3e8d-191">-NoClobber</span></span>

<span data-ttu-id="e3e8d-192">Indica que o cmdlet não substitui o conteúdo de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-192">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="e3e8d-193">Por padrão, se um arquivo existir no caminho especificado, `Export-Clixml` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-193">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="e3e8d-194">-Path</span><span class="sxs-lookup"><span data-stu-id="e3e8d-194">-Path</span></span>

<span data-ttu-id="e3e8d-195">Especifica o caminho para o arquivo onde a representação XML do objeto será armazenada.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-195">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="e3e8d-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e3e8d-196">-WhatIf</span></span>

<span data-ttu-id="e3e8d-197">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-197">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e3e8d-198">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-198">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e3e8d-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e3e8d-199">CommonParameters</span></span>

<span data-ttu-id="e3e8d-200">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3e8d-201">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3e8d-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3e8d-202">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-202">INPUTS</span></span>

### <span data-ttu-id="e3e8d-203">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="e3e8d-203">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e3e8d-204">Você pode canalizar qualquer objeto para `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="e3e8d-204">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="e3e8d-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-205">OUTPUTS</span></span>

### <span data-ttu-id="e3e8d-206">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="e3e8d-206">System.IO.FileInfo</span></span>

<span data-ttu-id="e3e8d-207">`Export-Clixml` Cria um arquivo que contém o XML.</span><span class="sxs-lookup"><span data-stu-id="e3e8d-207">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="e3e8d-208">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e3e8d-208">NOTES</span></span>

## <span data-ttu-id="e3e8d-209">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e3e8d-209">RELATED LINKS</span></span>

[<span data-ttu-id="e3e8d-210">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="e3e8d-210">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="e3e8d-211">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="e3e8d-211">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="e3e8d-212">Export-CSV</span><span class="sxs-lookup"><span data-stu-id="e3e8d-212">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="e3e8d-213">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="e3e8d-213">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="e3e8d-214">Join-Path</span><span class="sxs-lookup"><span data-stu-id="e3e8d-214">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="e3e8d-215">Armazenar credenciais com segurança no disco</span><span class="sxs-lookup"><span data-stu-id="e3e8d-215">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="e3e8d-216">Usar o PowerShell para passar credenciais para sistemas herdados</span><span class="sxs-lookup"><span data-stu-id="e3e8d-216">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="e3e8d-217">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="e3e8d-217">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
