---
description: Descreve como o PowerShell usa a codificação de caracteres para entrada e saída de dados de cadeia de caracteres.
Locale: en-US
ms.date: 10/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Character_Encoding
ms.openlocfilehash: 48a33903bd44db68a3c581183f83ec23ea97161a
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "96349798"
---
# <a name="about_character_encoding"></a><span data-ttu-id="a2e8b-103">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="a2e8b-103">about_Character_Encoding</span></span>

## <a name="short-description"></a><span data-ttu-id="a2e8b-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a2e8b-104">Short description</span></span>
<span data-ttu-id="a2e8b-105">Descreve como o PowerShell usa a codificação de caracteres para entrada e saída de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-105">Describes how PowerShell uses character encoding for input and output of string data.</span></span>

## <a name="long-description"></a><span data-ttu-id="a2e8b-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a2e8b-106">Long description</span></span>

<span data-ttu-id="a2e8b-107">O Unicode é um padrão mundial de codificação de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-107">Unicode is a worldwide character-encoding standard.</span></span> <span data-ttu-id="a2e8b-108">O sistema usa Unicode exclusivamente para manipulação de caracteres e cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-108">The system uses Unicode exclusively for character and string manipulation.</span></span> <span data-ttu-id="a2e8b-109">Para obter uma descrição detalhada de todos os aspectos do Unicode, consulte [o padrão Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-109">For a detailed description of all aspects of Unicode, refer to [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>

<span data-ttu-id="a2e8b-110">O Windows dá suporte a conjuntos de caracteres Unicode e tradicionais.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-110">Windows supports Unicode and traditional character sets.</span></span> <span data-ttu-id="a2e8b-111">Conjuntos de caracteres tradicionais, como páginas de código do Windows, usam valores de 8 bits ou combinações de valores de 8 bits para representar os caracteres usados em uma linguagem específica ou configurações de região geográfica.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-111">Traditional character sets, such as Windows code pages, use 8-bit values or combinations of 8-bit values to represent the characters used in a specific language or geographical region settings.</span></span>

<span data-ttu-id="a2e8b-112">O PowerShell usa um conjunto de caracteres Unicode por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-112">PowerShell uses a Unicode character set by default.</span></span> <span data-ttu-id="a2e8b-113">No entanto, vários cmdlets têm um parâmetro de **codificação** que pode especificar a codificação para um conjunto de caracteres diferente.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-113">However, several cmdlets have an **Encoding** parameter that can specify encoding for a different character set.</span></span> <span data-ttu-id="a2e8b-114">Esse parâmetro permite que você escolha a codificação de caracteres específica necessária para interoperabilidade com outros sistemas e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-114">This parameter allows you to choose the specific the character encoding you need for interoperability with other systems and applications.</span></span>

<span data-ttu-id="a2e8b-115">Os cmdlets a seguir têm o parâmetro **Encoding** :</span><span class="sxs-lookup"><span data-stu-id="a2e8b-115">The following cmdlets have the **Encoding** parameter:</span></span>

- <span data-ttu-id="a2e8b-116">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="a2e8b-116">Microsoft.PowerShell.Management</span></span>
  - <span data-ttu-id="a2e8b-117">Add-Content</span><span class="sxs-lookup"><span data-stu-id="a2e8b-117">Add-Content</span></span>
  - <span data-ttu-id="a2e8b-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="a2e8b-118">Get-Content</span></span>
  - <span data-ttu-id="a2e8b-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="a2e8b-119">Set-Content</span></span>
- <span data-ttu-id="a2e8b-120">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="a2e8b-120">Microsoft.PowerShell.Utility</span></span>
  - <span data-ttu-id="a2e8b-121">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="a2e8b-121">Export-Clixml</span></span>
  - <span data-ttu-id="a2e8b-122">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="a2e8b-122">Export-Csv</span></span>
  - <span data-ttu-id="a2e8b-123">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2e8b-123">Export-PSSession</span></span>
  - <span data-ttu-id="a2e8b-124">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="a2e8b-124">Format-Hex</span></span>
  - <span data-ttu-id="a2e8b-125">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="a2e8b-125">Import-Csv</span></span>
  - <span data-ttu-id="a2e8b-126">Out-File</span><span class="sxs-lookup"><span data-stu-id="a2e8b-126">Out-File</span></span>
  - <span data-ttu-id="a2e8b-127">Select-String</span><span class="sxs-lookup"><span data-stu-id="a2e8b-127">Select-String</span></span>
  - <span data-ttu-id="a2e8b-128">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="a2e8b-128">Send-MailMessage</span></span>

## <a name="the-byte-order-mark"></a><span data-ttu-id="a2e8b-129">A marca de ordem de byte</span><span class="sxs-lookup"><span data-stu-id="a2e8b-129">The byte-order-mark</span></span>

<span data-ttu-id="a2e8b-130">A BOM (marca de ordem de byte) é uma _assinatura Unicode_ nos primeiros bytes de um fluxo de arquivo ou de texto que indica a codificação Unicode usada para os dados.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-130">The byte-order-mark (BOM) is a _Unicode signature_ in the first few bytes of a file or text stream that indicate which Unicode encoding used for the data.</span></span> <span data-ttu-id="a2e8b-131">Para obter mais informações, consulte a documentação de [marca de ordem de byte](/globalization/encoding/byte-order-mark) .</span><span class="sxs-lookup"><span data-stu-id="a2e8b-131">For more information, see the [Byte order mark](/globalization/encoding/byte-order-mark) documentation.</span></span>

<span data-ttu-id="a2e8b-132">No Windows PowerShell, qualquer codificação Unicode, exceto `UTF7` , sempre cria uma bom.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-132">In Windows PowerShell, any Unicode encoding, except `UTF7`, always creates a BOM.</span></span> <span data-ttu-id="a2e8b-133">O PowerShell Core usa como padrão `utf8NoBOM` para toda a saída de texto.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-133">PowerShell Core defaults to `utf8NoBOM` for all text output.</span></span>

<span data-ttu-id="a2e8b-134">Para obter a melhor compatibilidade geral, evite usar BOMs em arquivos UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-134">For best overall compatibility, avoid using BOMs in UTF-8 files.</span></span> <span data-ttu-id="a2e8b-135">As plataformas UNIX e os utilitários Unix-Heritage também usados em plataformas Windows não dão suporte a BOMs.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-135">Unix platforms and Unix-heritage utilities also used on Windows Platforms don't support BOMs.</span></span>

<span data-ttu-id="a2e8b-136">Da mesma forma, a `UTF7` codificação deve ser evitada.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-136">Similarly, `UTF7` encoding should be avoided.</span></span> <span data-ttu-id="a2e8b-137">O UTF-7 não é uma codificação Unicode padrão e é escrito sem uma BOM em todas as versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-137">UTF-7 is not a standard Unicode encoding and is written without a BOM in all versions of PowerShell.</span></span>

<span data-ttu-id="a2e8b-138">Criar scripts do PowerShell em uma plataforma semelhante a UNIX ou usar um editor de plataforma cruzada no Windows, como Visual Studio Code, resulta em um arquivo codificado usando `UTF8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="a2e8b-138">Creating PowerShell scripts on a Unix-like platform or using a cross-platform editor on Windows, such as Visual Studio Code, results in a file encoded using `UTF8NoBOM`.</span></span> <span data-ttu-id="a2e8b-139">Esses arquivos funcionam bem no PowerShell Core, mas podem interromper o Windows PowerShell se o arquivo contiver caracteres não ASCII.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-139">These files work fine on PowerShell Core, but may break in Windows PowerShell if the file contains non-Ascii characters.</span></span>

<span data-ttu-id="a2e8b-140">Se você precisar usar caracteres não ASCII em seus scripts, salve-os como UTF-8 com a BOM.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-140">If you need to use non-Ascii characters in your scripts, save them as UTF-8 with BOM.</span></span> <span data-ttu-id="a2e8b-141">Sem a BOM, o Windows PowerShell interpreta incorretamente seu script como codificado na página de código "ANSI" herdada.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-141">Without the BOM, Windows PowerShell misinterprets your script as being encoded in the legacy "ANSI" codepage.</span></span> <span data-ttu-id="a2e8b-142">Por outro lado, os arquivos que têm a BOM UTF-8 podem ser problemáticos em plataformas semelhantes ao Unix.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-142">Conversely, files that do have the UTF-8 BOM can be problematic on Unix-like platforms.</span></span> <span data-ttu-id="a2e8b-143">Muitas ferramentas Unix, como,, `cat` `sed` `awk` e alguns editores, como `gedit` não sabem como tratar a bom.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-143">Many Unix tools such as `cat`, `sed`, `awk`, and some editors such as `gedit` don't know how to treat the BOM.</span></span>

## <a name="character-encoding-in-windows-powershell"></a><span data-ttu-id="a2e8b-144">Codificação de caracteres no Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2e8b-144">Character encoding in Windows PowerShell</span></span>

<span data-ttu-id="a2e8b-145">No PowerShell 5,1, o parâmetro de **codificação** dá suporte aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-145">In PowerShell 5.1, the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="a2e8b-146">`Ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-146">`Ascii` Uses Ascii (7-bit) character set.</span></span>
- <span data-ttu-id="a2e8b-147">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-147">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-148">`BigEndianUTF32` Usa UTF-32 com a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-148">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-149">`Byte` Codifica um conjunto de caracteres em uma sequência de bytes.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-149">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="a2e8b-150">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-150">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="a2e8b-151">`Oem` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-151">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="a2e8b-152">`String` Igual a `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-152">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="a2e8b-153">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-153">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-154">`Unknown` Igual a `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-154">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="a2e8b-155">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-155">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-156">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-156">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="a2e8b-157">`UTF8` Usa UTF-8 (com BOM).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-157">`UTF8` Uses UTF-8 (with BOM).</span></span>

<span data-ttu-id="a2e8b-158">Em geral, o Windows PowerShell usa a codificação [UTF-16Le](https://wikipedia.org/wiki/UTF-16) Unicode por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-158">In general, Windows PowerShell uses the Unicode [UTF-16LE](https://wikipedia.org/wiki/UTF-16) encoding by default.</span></span> <span data-ttu-id="a2e8b-159">No entanto, a codificação padrão usada por cmdlets no Windows PowerShell não é consistente.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-159">However, the default encoding used by cmdlets in Windows PowerShell is not consistent.</span></span>

> [!NOTE]
> <span data-ttu-id="a2e8b-160">Usar qualquer codificação Unicode, exceto `UTF7` , sempre cria uma bom.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-160">Using any Unicode encoding, except `UTF7`, always creates a BOM.</span></span>

<span data-ttu-id="a2e8b-161">Para cmdlets que gravam a saída em arquivos:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-161">For cmdlets that write output to files:</span></span>

- <span data-ttu-id="a2e8b-162">`Out-File` e os operadores de redirecionamento `>` e `>>` criar UTF-16LE, que notavelmente difere de `Set-Content` e `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="a2e8b-162">`Out-File` and the redirection operators `>` and `>>` create UTF-16LE, which notably differs from `Set-Content` and `Add-Content`.</span></span>

- <span data-ttu-id="a2e8b-163">`New-ModuleManifest` e `Export-CliXml` também criar arquivos UTF-16LE.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-163">`New-ModuleManifest` and `Export-CliXml` also create UTF-16LE files.</span></span>

- <span data-ttu-id="a2e8b-164">Quando o arquivo de destino estiver vazio ou não existir, `Set-Content` e `Add-Content` usar a `Default` codificação.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-164">When the target file is empty or doesn't exist, `Set-Content` and `Add-Content` use `Default` encoding.</span></span> <span data-ttu-id="a2e8b-165">`Default` é a codificação especificada pela página de código herdado do ANSI da localidade do sistema ativa.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-165">`Default` is the encoding specified by the active system locale's ANSI legacy code page.</span></span>

- <span data-ttu-id="a2e8b-166">`Export-Csv` cria `Ascii` arquivos, mas usa codificação diferente ao usar o parâmetro **Append** (veja abaixo).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-166">`Export-Csv` creates `Ascii` files but uses different encoding when using **Append** parameter (see below).</span></span>

- <span data-ttu-id="a2e8b-167">`Export-PSSession` cria arquivos UTF-8 com a BOM por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-167">`Export-PSSession` creates UTF-8 files with BOM by default.</span></span>

- <span data-ttu-id="a2e8b-168">`New-Item -Type File -Value` Cria um arquivo UTF-8 sem BOM.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-168">`New-Item -Type File -Value` creates a BOM-less UTF-8 file.</span></span>

- <span data-ttu-id="a2e8b-169">`Send-MailMessage` usa `Default` a codificação por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-169">`Send-MailMessage` uses `Default` encoding by default.</span></span>

- <span data-ttu-id="a2e8b-170">`Start-Transcript` cria `Utf8` arquivos com uma bom.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-170">`Start-Transcript` creates `Utf8` files with a BOM.</span></span> <span data-ttu-id="a2e8b-171">Quando o parâmetro **Append** é usado, a codificação pode ser diferente (veja abaixo).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-171">When the **Append** parameter is used, the encoding can be different (see below).</span></span>

<span data-ttu-id="a2e8b-172">Para comandos que acrescentam a um arquivo existente:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-172">For commands that append to an existing file:</span></span>

- <span data-ttu-id="a2e8b-173">`Out-File -Append` e o `>>` operador de redirecionamento não faz nenhuma tentativa de corresponder à codificação do conteúdo do arquivo de destino existente.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-173">`Out-File -Append` and the `>>` redirection operator make no attempt to match the encoding of the existing target file's content.</span></span> <span data-ttu-id="a2e8b-174">Em vez disso, eles usam a codificação padrão, a menos que o parâmetro de **codificação** seja usado.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-174">Instead, they use the default encoding unless the **Encoding** parameter is used.</span></span> <span data-ttu-id="a2e8b-175">Você deve usar a codificação original de arquivos ao acrescentar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-175">You must use the files original encoding when appending content.</span></span>

- <span data-ttu-id="a2e8b-176">Na ausência de um parâmetro de **codificação** explícito, `Add-Content` o detecta a codificação existente e a aplica automaticamente ao novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-176">In the absence of an explicit **Encoding** parameter, `Add-Content` detects the existing encoding and automatically applies it to the new content.</span></span> <span data-ttu-id="a2e8b-177">Se o conteúdo existente não tiver uma BOM, a `Default` codificação ANSI será usada.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-177">If the existing content has no BOM, `Default` ANSI encoding is used.</span></span> <span data-ttu-id="a2e8b-178">O comportamento do `Add-Content` é o mesmo no PowerShell Core (V6 e superior), exceto pela codificação padrão `Utf8` .</span><span class="sxs-lookup"><span data-stu-id="a2e8b-178">The behavior of `Add-Content` is the same in PowerShell Core (v6 and higher) except the default encoding is `Utf8`.</span></span>

- <span data-ttu-id="a2e8b-179">`Export-Csv -Append` faz a correspondência da codificação existente quando o arquivo de destino contém uma BOM.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-179">`Export-Csv -Append` matches the existing encoding when the target file contains a BOM.</span></span> <span data-ttu-id="a2e8b-180">Na ausência de uma BOM, ela usa `Utf8` codificação.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-180">In the absence of a BOM, it uses `Utf8` encoding.</span></span>

- <span data-ttu-id="a2e8b-181">`Start-Transcript -Append` corresponde à codificação existente de arquivos que incluem uma BOM.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-181">`Start-Transcript -Append` matches the existing encoding of files that include a BOM.</span></span> <span data-ttu-id="a2e8b-182">Na ausência de uma BOM, o padrão é a `Ascii` codificação.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-182">In the absence of a BOM, it defaults to `Ascii` encoding.</span></span> <span data-ttu-id="a2e8b-183">Essa codificação pode resultar em perda de dados ou corrupção de caracteres quando os dados na transcrição contiverem caracteres multibyte.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-183">This encoding can result in data loss or character corruption when the data in the transcript contains multibyte characters.</span></span>

<span data-ttu-id="a2e8b-184">Para cmdlets que lêem dados de cadeia de caracteres na ausência de uma BOM:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-184">For cmdlets that read string data in the absence of a BOM:</span></span>

- <span data-ttu-id="a2e8b-185">`Get-Content` e `Import-PowerShellDataFile` usa a `Default` codificação ANSI.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-185">`Get-Content` and `Import-PowerShellDataFile` uses the `Default` ANSI encoding.</span></span> <span data-ttu-id="a2e8b-186">O ANSI também é o que o mecanismo do PowerShell usa quando lê o código-fonte dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-186">ANSI is also what the PowerShell engine uses when it reads source code from files.</span></span>

- <span data-ttu-id="a2e8b-187">`Import-Csv`, `Import-CliXml` e `Select-String` assumem `Utf8` a ausência de uma bom.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-187">`Import-Csv`, `Import-CliXml`, and `Select-String` assume `Utf8` in the absence of a BOM.</span></span>

## <a name="character-encoding-in-powershell-core"></a><span data-ttu-id="a2e8b-188">Codificação de caracteres no PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="a2e8b-188">Character encoding in PowerShell Core</span></span>

<span data-ttu-id="a2e8b-189">No PowerShell Core (V6 e superior), o parâmetro **Encoding** oferece suporte aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-189">In PowerShell Core (v6 and higher), the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="a2e8b-190">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-190">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="a2e8b-191">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-191">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-192">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-192">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="a2e8b-193">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-193">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="a2e8b-194">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-194">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="a2e8b-195">`utf8`: Codifica em formato UTF-8 (sem BOM).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-195">`utf8`: Encodes in UTF-8 format (no BOM).</span></span>
- <span data-ttu-id="a2e8b-196">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="a2e8b-196">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a2e8b-197">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="a2e8b-197">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a2e8b-198">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-198">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="a2e8b-199">O PowerShell Core usa como padrão `utf8NoBOM` para todas as saídas.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-199">PowerShell Core defaults to `utf8NoBOM` for all output.</span></span>

<span data-ttu-id="a2e8b-200">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-200">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="a2e8b-201">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-201">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage).</span></span>

## <a name="changing-the-default-encoding"></a><span data-ttu-id="a2e8b-202">Alterando a codificação padrão</span><span class="sxs-lookup"><span data-stu-id="a2e8b-202">Changing the default encoding</span></span>

<span data-ttu-id="a2e8b-203">O PowerShell tem duas variáveis padrão que podem ser usadas para alterar o comportamento de codificação padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-203">PowerShell has two default variables that can be used to change the default encoding behavior.</span></span>

- `$PSDefaultParameterValues`
- `$OutputEncoding`

<span data-ttu-id="a2e8b-204">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a2e8b-204">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="a2e8b-205">A partir do PowerShell 5,1, os operadores de redirecionamento ( `>` e `>>` ) chamam o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-205">Beginning in PowerShell 5.1, the redirection operators (`>` and `>>`) call the `Out-File` cmdlet.</span></span> <span data-ttu-id="a2e8b-206">Portanto, você pode definir a codificação padrão deles usando a `$PSDefaultParameterValues` variável de preferência, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2e8b-206">Therefore, you can set the default encoding of them using the `$PSDefaultParameterValues` preference variable as shown in this example:</span></span>

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

<span data-ttu-id="a2e8b-207">Use a instrução a seguir para alterar a codificação padrão para todos os cmdlets que têm o parâmetro de **codificação** .</span><span class="sxs-lookup"><span data-stu-id="a2e8b-207">Use the following statement to change the default encoding for all cmdlets that have the **Encoding** parameter.</span></span>

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> <span data-ttu-id="a2e8b-208">Colocar esse comando em seu perfil do PowerShell torna a preferência uma configuração global da sessão que afeta todos os comandos e scripts que não especificam explicitamente uma codificação.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-208">Putting this command in your PowerShell profile makes the preference a session-global setting that affects all commands and scripts that do not explicitly specify an encoding.</span></span>
>
> <span data-ttu-id="a2e8b-209">Da mesma forma, você deve incluir esses comandos em seus scripts ou módulos que você deseja que se comportem da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-209">Similarly, you should include such commands in your scripts or modules that you want to behave the same way.</span></span> <span data-ttu-id="a2e8b-210">O uso desses comandos garante que os cmdlets se comportem da mesma maneira mesmo quando executados por outro usuário, em um computador diferente ou em uma versão diferente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-210">Using these commands ensure that cmdlets behave the same way even when run by another user, on a different computer, or in a different version of PowerShell.</span></span>

<span data-ttu-id="a2e8b-211">A variável automática `$OutputEncoding` afeta a codificação que o PowerShell usa para se comunicar com programas externos.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-211">The automatic variable `$OutputEncoding` affects the encoding PowerShell uses to communicate with external programs.</span></span> <span data-ttu-id="a2e8b-212">Ele não tem nenhum efeito sobre a codificação que os operadores de redirecionamento de saída e os cmdlets do PowerShell usam para salvar em arquivos.</span><span class="sxs-lookup"><span data-stu-id="a2e8b-212">It has no effect on the encoding that the output redirection operators and PowerShell cmdlets use to save to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2e8b-213">Veja também</span><span class="sxs-lookup"><span data-stu-id="a2e8b-213">See also</span></span>

- [<span data-ttu-id="a2e8b-214">Introdução à codificação de caracteres no .NET</span><span class="sxs-lookup"><span data-stu-id="a2e8b-214">Introduction to character encoding in .NET</span></span>](/dotnet/standard/base-types/character-encoding-introduction)
- [<span data-ttu-id="a2e8b-215">Páginas de código-aplicativos Win32</span><span class="sxs-lookup"><span data-stu-id="a2e8b-215">Code Pages - Win32 apps</span></span>](/windows/win32/intl/code-pages)
- [<span data-ttu-id="a2e8b-216">O padrão Unicode</span><span class="sxs-lookup"><span data-stu-id="a2e8b-216">The Unicode Standard</span></span>](https://www.unicode.org/standard/standard.html)
- [<span data-ttu-id="a2e8b-217">Encoding. CodePage</span><span class="sxs-lookup"><span data-stu-id="a2e8b-217">Encoding.CodePage</span></span>](/dotnet/api/system.text.encoding.codepage)
- [<span data-ttu-id="a2e8b-218">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="a2e8b-218">UTF-16LE</span></span>](https://wikipedia.org/wiki/UTF-16)
- [<span data-ttu-id="a2e8b-219">Marca de ordem de byte</span><span class="sxs-lookup"><span data-stu-id="a2e8b-219">Byte order mark</span></span>](https://wikipedia.org/wiki/Byte_order_mark)
- [<span data-ttu-id="a2e8b-220">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a2e8b-220">about_Preference_Variables</span></span>](about_Preference_Variables.md)
