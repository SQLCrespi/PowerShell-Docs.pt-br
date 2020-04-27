---
title: Noções básicas sobre a codificação de arquivos no VS Code e PowerShell
description: Configurar a codificação de arquivos no VS Code e no PowerShell
ms.date: 02/28/2019
ms.openlocfilehash: b09c13374c28e88c66d1d84fbe56ca5c66b34c8c
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80978671"
---
# <a name="understanding-file-encoding-in-vs-code-and-powershell"></a><span data-ttu-id="185d1-103">Noções básicas sobre a codificação de arquivos no VS Code e PowerShell</span><span class="sxs-lookup"><span data-stu-id="185d1-103">Understanding file encoding in VS Code and PowerShell</span></span>

<span data-ttu-id="185d1-104">Ao usar o VS Code para criar e editar scripts do PowerShell, é importante que os arquivos sejam salvos usando o formato de codificação de caracteres correto.</span><span class="sxs-lookup"><span data-stu-id="185d1-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="185d1-105">O que é codificação de arquivos e por que ela é importante?</span><span class="sxs-lookup"><span data-stu-id="185d1-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="185d1-106">O VS Code gerencia a interface entre um humano inserindo cadeias de caracteres em um buffer e lendo/gravando blocos de bytes no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="185d1-106">VS Code manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="185d1-107">Quando o VS Code salva um arquivo, ele usa uma codificação de texto para decidir quais bytes cada caractere se torna.</span><span class="sxs-lookup"><span data-stu-id="185d1-107">When VS Code saves a file, it uses a text encoding to decide what bytes each character becomes.</span></span>

<span data-ttu-id="185d1-108">De forma semelhante, quando o PowerShell executa um script, ele precisa converter os bytes em um arquivo em caracteres para reconstruir o arquivo em um programa do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-108">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="185d1-109">Como o VS Code grava o arquivo e o PowerShell lê o arquivo, eles precisam usar o mesmo sistema de codificação.</span><span class="sxs-lookup"><span data-stu-id="185d1-109">Since VS Code writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="185d1-110">O processo de análise de um script do PowerShell é: *bytes* -> *caracteres* -> *tokens* -> *árvore de sintaxe abstrata* -> *execução*.</span><span class="sxs-lookup"><span data-stu-id="185d1-110">This process of parsing a PowerShell script goes: *bytes* -> *characters* -> *tokens* -> *abstract syntax tree* -> *execution*.</span></span>

<span data-ttu-id="185d1-111">O VS Code e o PowerShell são instalados com uma configuração de codificação padrão adequada.</span><span class="sxs-lookup"><span data-stu-id="185d1-111">Both VS Code and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="185d1-112">No entanto, a codificação padrão usada pelo PowerShell foi alterada com o lançamento do PowerShell Core (v6. x).</span><span class="sxs-lookup"><span data-stu-id="185d1-112">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="185d1-113">Para garantir que não tenha problemas para usar o PowerShell ou a extensão do PowerShell no VS Code, você precisa definir corretamente suas configurações do VS Code e do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-113">To ensure you have no problems using PowerShell or the PowerShell extension in VS Code, you need to configure your VS Code and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="185d1-114">Causas comuns de problemas de codificação</span><span class="sxs-lookup"><span data-stu-id="185d1-114">Common causes of encoding issues</span></span>

<span data-ttu-id="185d1-115">Problemas de codificação ocorrem quando a codificação do VS Code ou seu arquivo de script não coincidem com a codificação esperada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-115">Encoding problems occur when the encoding of VS Code or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="185d1-116">Não há nenhuma maneira de o PowerShell determinar automaticamente a codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="185d1-116">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="185d1-117">Você tem mais probabilidade de ter problemas de codificação quando usa caracteres que não estão no [conjunto de caracteres ASCII de 7 bits](https://ascii.cl/).</span><span class="sxs-lookup"><span data-stu-id="185d1-117">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="185d1-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="185d1-118">For example:</span></span>

- <span data-ttu-id="185d1-119">Caracteres não alfabéticos estendidos, como travessão (`—`), espaço contínuo (` `) ou aspas duplas à esquerda (`"`)</span><span class="sxs-lookup"><span data-stu-id="185d1-119">Extended non-letter characters like em-dash (`—`), non-breaking space (` `) or left double quotation mark (`"`)</span></span>
- <span data-ttu-id="185d1-120">Caracteres latinos acentuados (`É`, `ü`)</span><span class="sxs-lookup"><span data-stu-id="185d1-120">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="185d1-121">Caracteres não latinos, como cirílico (`Д`, `Ц`)</span><span class="sxs-lookup"><span data-stu-id="185d1-121">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="185d1-122">Caracteres CJK (`本`, `화`, `が`)</span><span class="sxs-lookup"><span data-stu-id="185d1-122">CJK characters (`本`, `화`, `が`)</span></span>

<span data-ttu-id="185d1-123">Motivos comuns para problemas de codificação são:</span><span class="sxs-lookup"><span data-stu-id="185d1-123">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="185d1-124">As codificações do VS Code e do PowerShell não foram alteradas em relação aos padrões.</span><span class="sxs-lookup"><span data-stu-id="185d1-124">The encodings of VS Code and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="185d1-125">Para o PowerShell 5.1 e versões anteriores, a codificação padrão é diferente da codificação do VS Code.</span><span class="sxs-lookup"><span data-stu-id="185d1-125">For PowerShell 5.1 and below, the default encoding is different from VS Code's.</span></span>
- <span data-ttu-id="185d1-126">Outro editor abriu e substituiu o arquivo em uma nova codificação.</span><span class="sxs-lookup"><span data-stu-id="185d1-126">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="185d1-127">Isso costuma acontecer com o ISE.</span><span class="sxs-lookup"><span data-stu-id="185d1-127">This often happens with the ISE.</span></span>
- <span data-ttu-id="185d1-128">É feito o check-in do arquivo no controle do código-fonte com uma codificação diferente da esperada pelo VS Code ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-128">The file is checked into source control in an encoding that is different from what VS Code or PowerShell expects.</span></span> <span data-ttu-id="185d1-129">Isso pode acontecer quando colaboradores usam editores com configurações de codificação diferentes.</span><span class="sxs-lookup"><span data-stu-id="185d1-129">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="185d1-130">Como saber que você tem problemas de codificação</span><span class="sxs-lookup"><span data-stu-id="185d1-130">How to tell when you have encoding issues</span></span>

<span data-ttu-id="185d1-131">Com frequência, erros de codificação são apresentados como erros de análise nos scripts.</span><span class="sxs-lookup"><span data-stu-id="185d1-131">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="185d1-132">Se você encontrar sequências de caracteres estranhos em seu script, esse poderá ser o problema.</span><span class="sxs-lookup"><span data-stu-id="185d1-132">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="185d1-133">No exemplo a seguir, um traço (`–`) é exibido como os caracteres `â&euro;"`:</span><span class="sxs-lookup"><span data-stu-id="185d1-133">In the example below, an en-dash (`–`) appears as the characters `â&euro;"`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â&euro;"From $from â&euro;"To $recipient1 â&euro;"Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="185d1-134">Esse problema ocorre porque o VS Code codifica o caractere `–` em UTF-8 como os bytes `0xE2 0x80 0x93`.</span><span class="sxs-lookup"><span data-stu-id="185d1-134">This problem occurs because VS Code encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span> <span data-ttu-id="185d1-135">Quando são decodificados como Windows-1252, esses bytes são interpretados como caracteres `â&euro;"`.</span><span class="sxs-lookup"><span data-stu-id="185d1-135">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â&euro;"`.</span></span>

<span data-ttu-id="185d1-136">Algumas sequências de caracteres estranhos que você pode ver incluem:</span><span class="sxs-lookup"><span data-stu-id="185d1-136">Some strange character sequences that you might see include:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="185d1-137">`â&euro;"` em vez de `–`</span><span class="sxs-lookup"><span data-stu-id="185d1-137">`â&euro;"` instead of `–`</span></span>
- <span data-ttu-id="185d1-138">`â&euro;"` em vez de `—`</span><span class="sxs-lookup"><span data-stu-id="185d1-138">`â&euro;"` instead of `—`</span></span>
- <span data-ttu-id="185d1-139">`Ã„2` em vez de `Ä`</span><span class="sxs-lookup"><span data-stu-id="185d1-139">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="185d1-140">`Â` em vez de ` ` (um espaço contínuo)</span><span class="sxs-lookup"><span data-stu-id="185d1-140">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="185d1-141">`Ã&copy;` em vez de `é`</span><span class="sxs-lookup"><span data-stu-id="185d1-141">`Ã&copy;` instead of `é`</span></span>
<!-- markdownlint-enable MD038 -->

<span data-ttu-id="185d1-142">Esta [referência](https://www.i18nqa.com/debug/utf8-debug.html) útil lista os padrões comuns que indicam que há um problema de codificação UTF-8/Windows-1252.</span><span class="sxs-lookup"><span data-stu-id="185d1-142">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vs-code-interacts-with-encodings"></a><span data-ttu-id="185d1-143">Como a extensão do PowerShell no VS Code interage com codificações</span><span class="sxs-lookup"><span data-stu-id="185d1-143">How the PowerShell extension in VS Code interacts with encodings</span></span>

<span data-ttu-id="185d1-144">A extensão do PowerShell interage com scripts de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="185d1-144">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="185d1-145">Quando scripts são editados no VS Code, o conteúdo é enviado pelo VS Code para a extensão.</span><span class="sxs-lookup"><span data-stu-id="185d1-145">When scripts are edited in VS Code, the contents are sent by VS Code to the extension.</span></span> <span data-ttu-id="185d1-146">O [Protocolo de servidor de linguagem][] exige que esse conteúdo seja transferido em UTF-8.</span><span class="sxs-lookup"><span data-stu-id="185d1-146">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="185d1-147">Portanto, não é possível que a extensão obtenha a codificação errada.</span><span class="sxs-lookup"><span data-stu-id="185d1-147">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
2. <span data-ttu-id="185d1-148">Quando são executados diretamente no Console integrado, os scripts são lidos do arquivo diretamente pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-148">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="185d1-149">Se a codificação do PowerShell for diferente da codificação do VS Code, algo poderá dar errado aqui.</span><span class="sxs-lookup"><span data-stu-id="185d1-149">If PowerShell's encoding differs from VS Code's, something can go wrong here.</span></span>
3. <span data-ttu-id="185d1-150">Quando um script aberto no VS Code faz referência a outro script que não está aberto no VS Code, a extensão volta a carregar o conteúdo do script do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="185d1-150">When a script that is open in VS Code references another script that is not open in VS Code, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="185d1-151">A extensão do PowerShell usa por padrão a codificação UTF-8, mas usa a detecção de [marca de ordem de byte][], ou BOM, para selecionar a codificação correta.</span><span class="sxs-lookup"><span data-stu-id="185d1-151">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="185d1-152">O problema ocorre ao assumir a codificação de formatos sem BOM (como [UTF-8][] sem BOM e [Windows-1252][]).</span><span class="sxs-lookup"><span data-stu-id="185d1-152">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span> <span data-ttu-id="185d1-153">A extensão do PowerShell usa UTF-8 por padrão.</span><span class="sxs-lookup"><span data-stu-id="185d1-153">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="185d1-154">A extensão não pode alterar as configurações de codificação do VS Code.</span><span class="sxs-lookup"><span data-stu-id="185d1-154">The extension cannot change VS Code's encoding settings.</span></span> <span data-ttu-id="185d1-155">Para saber mais, confira [problema 824] (https://github.com/Microsoft/VS Code/issues/824).</span><span class="sxs-lookup"><span data-stu-id="185d1-155">For more information, see [issue #824](https://github.com/Microsoft/VS Code/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="185d1-156">Escolher a codificação correta</span><span class="sxs-lookup"><span data-stu-id="185d1-156">Choosing the right encoding</span></span>

<span data-ttu-id="185d1-157">Aplicativos e sistemas diferentes podem usar codificações diferentes:</span><span class="sxs-lookup"><span data-stu-id="185d1-157">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="185d1-158">No .NET Standard, na Web e no universo Linux, UTF-8 é a codificação dominante.</span><span class="sxs-lookup"><span data-stu-id="185d1-158">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="185d1-159">Muitos aplicativos .NET Framework usam [UTF-16][].</span><span class="sxs-lookup"><span data-stu-id="185d1-159">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="185d1-160">Por razões históricas, às vezes ele é chamado de "Unicode", um termo que hoje se refere a um [padrão](https://en.wikipedia.org/wiki/Unicode) amplo que inclui UTF-8 e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="185d1-160">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="185d1-161">No Windows, muitos aplicativos nativos anteriores ao Unicode continuam usando o Windows-1252 por padrão.</span><span class="sxs-lookup"><span data-stu-id="185d1-161">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="185d1-162">Codificações Unicode também têm o conceito de uma BOM (marca de ordem de byte).</span><span class="sxs-lookup"><span data-stu-id="185d1-162">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="185d1-163">BOMs ocorrem no início do texto para informar ao decodificador qual codificação o texto está usando.</span><span class="sxs-lookup"><span data-stu-id="185d1-163">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="185d1-164">Para codificações de múltiplos bytes, a BOM também indica a [ordenação](https://en.wikipedia.org/wiki/Endianness) da codificação.</span><span class="sxs-lookup"><span data-stu-id="185d1-164">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="185d1-165">BOMs são designadas como bytes que raramente ocorrem em texto não Unicode, permitindo presumir de forma razoável que o texto é Unicode quando uma BOM está presente.</span><span class="sxs-lookup"><span data-stu-id="185d1-165">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="185d1-166">BOMs são opcionais e sua adoção não é tão popular no universo Linux, pois uma convenção confiável de UTF-8 é usada em todo lugar.</span><span class="sxs-lookup"><span data-stu-id="185d1-166">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="185d1-167">A maioria dos aplicativos Linux presume que a entrada de texto está codificada em UTF-8.</span><span class="sxs-lookup"><span data-stu-id="185d1-167">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="185d1-168">Embora muitos aplicativos Linux reconheçam e lidem corretamente com uma BOM, vários deles não fazem isso, levando a artefatos nos textos manipulados com esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="185d1-168">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="185d1-169">**Portanto**:</span><span class="sxs-lookup"><span data-stu-id="185d1-169">**Therefore**:</span></span>

- <span data-ttu-id="185d1-170">se trabalha principalmente com aplicativos do Windows e Windows PowerShell, você deve preferir uma codificação como UTF-8 com BOM ou UTF-16.</span><span class="sxs-lookup"><span data-stu-id="185d1-170">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="185d1-171">Se trabalha com plataformas cruzadas, você deve preferir UTF-8 com BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-171">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="185d1-172">Se trabalha principalmente em contextos associados ao Linux, você deve preferir UTF-8 sem BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-172">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="185d1-173">Windows-1252 e latin-1 são essencialmente codificações herdadas que você deve evitar se possível.</span><span class="sxs-lookup"><span data-stu-id="185d1-173">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="185d1-174">No entanto, alguns aplicativos do Windows mais antigos podem depender delas.</span><span class="sxs-lookup"><span data-stu-id="185d1-174">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="185d1-175">Também vale observar que a assinatura de script é [dependente da codificação](https://github.com/PowerShell/PowerShell/issues/3466), o que significa que uma alteração na codificação de um script assinado exigirá uma nova assinatura.</span><span class="sxs-lookup"><span data-stu-id="185d1-175">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vs-code"></a><span data-ttu-id="185d1-176">Configurar o VS Code</span><span class="sxs-lookup"><span data-stu-id="185d1-176">Configuring VS Code</span></span>

<span data-ttu-id="185d1-177">A codificação padrão do VS Code é UTF-8 sem BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-177">VS Code's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="185d1-178">Para definir a [Codificação de VS Code][], vá para a seção correspondente (<kbd>Ctrl</kbd>+<kbd>,</kbd>) e defina a configuração `"files.encoding"`:</span><span class="sxs-lookup"><span data-stu-id="185d1-178">To set [VS Code's encoding][], go to the VS Code settings (<kbd>Ctrl</kbd>+<kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="185d1-179">Alguns valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="185d1-179">Some possible values are:</span></span>

- <span data-ttu-id="185d1-180">`utf8`: [UTF-8] sem BOM</span><span class="sxs-lookup"><span data-stu-id="185d1-180">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="185d1-181">`utf8bom`: [UTF-8] com BOM</span><span class="sxs-lookup"><span data-stu-id="185d1-181">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="185d1-182">`utf16le`: [UTF-16] little endian</span><span class="sxs-lookup"><span data-stu-id="185d1-182">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="185d1-183">`utf16be`: [UTF-16] big endian</span><span class="sxs-lookup"><span data-stu-id="185d1-183">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="185d1-184">`windows1252`: [Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="185d1-184">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="185d1-185">Você deve obter uma lista suspensa deles no modo de exibição de GUI ou preenchimentos no modo de exibição JSON.</span><span class="sxs-lookup"><span data-stu-id="185d1-185">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="185d1-186">Você também pode adicionar o seguinte para obter detecção automática da codificação quando possível:</span><span class="sxs-lookup"><span data-stu-id="185d1-186">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="185d1-187">Caso não queira que essas configurações afetem todos os tipos de arquivos, o VS Code também permite configurações por idioma.</span><span class="sxs-lookup"><span data-stu-id="185d1-187">If you don't want these settings to affect all files types, VS Code also allows per-language configurations.</span></span> <span data-ttu-id="185d1-188">Crie uma configuração específica a um idioma colocando as configurações em um campo `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="185d1-188">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="185d1-189">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="185d1-189">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a><span data-ttu-id="185d1-190">Configurar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="185d1-190">Configuring PowerShell</span></span>

<span data-ttu-id="185d1-191">A codificação padrão do PowerShell varia dependendo da versão:</span><span class="sxs-lookup"><span data-stu-id="185d1-191">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="185d1-192">No PowerShell 6 +, a codificação padrão é UTF-8 sem BOM em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="185d1-192">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="185d1-193">No Windows PowerShell, a codificação padrão geralmente é Windows-1252, uma extensão de [latin-1][], também conhecida como ISO 8859-1.</span><span class="sxs-lookup"><span data-stu-id="185d1-193">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="185d1-194">No PowerShell 5 +, você pode encontrar sua codificação padrão usando:</span><span class="sxs-lookup"><span data-stu-id="185d1-194">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="185d1-195">O seguinte [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) pode ser usado para determinar qual codificação sua sessão do PowerShell infere para um script sem BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-195">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

```powershell
$badBytes = [byte[]]@(0xC3, 0x80)
$utf8Str = [System.Text.Encoding]::UTF8.GetString($badBytes)
$bytes = [System.Text.Encoding]::ASCII.GetBytes('Write-Output "') + [byte[]]@(0xC3, 0x80) + [byte[]]@(0x22)
$path = Join-Path ([System.IO.Path]::GetTempPath()) 'encodingtest.ps1'

try
{
    [System.IO.File]::WriteAllBytes($path, $bytes)

    switch (& $path)
    {
        $utf8Str
        {
            return 'UTF-8'
            break
        }

        default
        {
            return 'Windows-1252'
            break
        }
    }
}
finally
{
    Remove-Item $path
}
```

<span data-ttu-id="185d1-196">É possível configurar o PowerShell para usar uma determinada codificação de modo mais geral usando configurações de perfil.</span><span class="sxs-lookup"><span data-stu-id="185d1-196">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span>
<span data-ttu-id="185d1-197">Veja os artigos a seguir:</span><span class="sxs-lookup"><span data-stu-id="185d1-197">See the following articles:</span></span>

- <span data-ttu-id="185d1-198">[Resposta de [@mklement0] sobre a codificação do PowerShell no StackOverflow](https://stackoverflow.com/a/40098904).</span><span class="sxs-lookup"><span data-stu-id="185d1-198">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="185d1-199">[Postagem no blob de [@rkeithhill] sobre como lidar com entradas UTF-8 sem BOM no PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span><span class="sxs-lookup"><span data-stu-id="185d1-199">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="185d1-200">Não é possível forçar o PowerShell a usar uma codificação de entrada específica.</span><span class="sxs-lookup"><span data-stu-id="185d1-200">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="185d1-201">O PowerShell 5.1 e anteriores usam por padrão a codificação Windows-1252 quando não há uma BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-201">PowerShell 5.1 and below default to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="185d1-202">Por motivos de interoperabilidade, é melhor salvar os scripts em um formato Unicode com uma BOM.</span><span class="sxs-lookup"><span data-stu-id="185d1-202">For interoperability reasons, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="185d1-203">Qualquer outra ferramenta que você tiver que tocar os scripts do PowerShell poderão ser afetadas por suas escolhas de codificação ou recodificar seus scripts com outra codificação.</span><span class="sxs-lookup"><span data-stu-id="185d1-203">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="185d1-204">Scripts existentes</span><span class="sxs-lookup"><span data-stu-id="185d1-204">Existing scripts</span></span>

<span data-ttu-id="185d1-205">Scripts que já estão no sistema de arquivos poderão precisar ser codificados novamente para sua codificação escolhida.</span><span class="sxs-lookup"><span data-stu-id="185d1-205">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="185d1-206">Na barra inferior do VS Code, você verá o rótulo UTF-8.</span><span class="sxs-lookup"><span data-stu-id="185d1-206">In the bottom bar of VS Code, you'll see the label UTF-8.</span></span> <span data-ttu-id="185d1-207">Clique nele para abrir a barra de ação e selecione **Salvar com codificação**.</span><span class="sxs-lookup"><span data-stu-id="185d1-207">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="185d1-208">Agora, você pode escolher uma nova codificação para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="185d1-208">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="185d1-209">Confira [Codificação de VS Code][] para obter instruções completas.</span><span class="sxs-lookup"><span data-stu-id="185d1-209">See [VS Code's encoding][] for full instructions.</span></span>

<span data-ttu-id="185d1-210">Se precisar codificar vários arquivos novamente, você poderá usar o script a seguir:</span><span class="sxs-lookup"><span data-stu-id="185d1-210">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="185d1-211">O (ISE) Ambiente de Script Integrado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="185d1-211">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="185d1-212">Caso também edite scripts usando o ISE do PowerShell, você precisará sincronizar suas configurações de codificação nele.</span><span class="sxs-lookup"><span data-stu-id="185d1-212">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="185d1-213">O ISE deve honrar uma BOM, mas também é possível usar reflexão para [definir a codificação](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span><span class="sxs-lookup"><span data-stu-id="185d1-213">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="185d1-214">Observe que isso não persistiria entre inicializações.</span><span class="sxs-lookup"><span data-stu-id="185d1-214">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="185d1-215">Software de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="185d1-215">Source control software</span></span>

<span data-ttu-id="185d1-216">Algumas ferramentas de controle do código-fonte, como git, ignoram as codificações; o git apenas controla os bytes.</span><span class="sxs-lookup"><span data-stu-id="185d1-216">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span> <span data-ttu-id="185d1-217">Outros, como Azure DevOps ou Mercurial, podem não fazer isso.</span><span class="sxs-lookup"><span data-stu-id="185d1-217">Others, like Azure DevOps or Mercurial, may not.</span></span> <span data-ttu-id="185d1-218">Até mesmo algumas ferramentas baseadas em git dependem da decodificação de texto.</span><span class="sxs-lookup"><span data-stu-id="185d1-218">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="185d1-219">Quando for esse o caso, não deixe de:</span><span class="sxs-lookup"><span data-stu-id="185d1-219">When this is the case, make sure you:</span></span>

- <span data-ttu-id="185d1-220">Configure a codificação de texto no controle do código-fonte para corresponder à configuração do VS Code.</span><span class="sxs-lookup"><span data-stu-id="185d1-220">Configure the text encoding in your source control to match your VS Code configuration.</span></span>
- <span data-ttu-id="185d1-221">Garantir que todos os arquivos sejam verificados no controle do código-fonte na codificação relevante.</span><span class="sxs-lookup"><span data-stu-id="185d1-221">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="185d1-222">Estar atento a alterações na codificação recebidas por meio do controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="185d1-222">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="185d1-223">Um sinal importante disto é uma comparação indicando alterações, mas em que nada parece ter sido alterado (porque os bytes foram, mas os caracteres não).</span><span class="sxs-lookup"><span data-stu-id="185d1-223">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="185d1-224">Ambientes de colaboradores</span><span class="sxs-lookup"><span data-stu-id="185d1-224">Collaborators' environments</span></span>

<span data-ttu-id="185d1-225">Além de configurar o controle do código-fonte, certifique-se de que seus colaboradores em todos os arquivos que você compartilha não tenham configurações que substituem sua codificação codificando novamente os arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185d1-225">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="185d1-226">Outros programas</span><span class="sxs-lookup"><span data-stu-id="185d1-226">Other programs</span></span>

<span data-ttu-id="185d1-227">Qualquer outro programa que lê ou grava um script do PowerShell pode codificá-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="185d1-227">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="185d1-228">Alguns exemplos são:</span><span class="sxs-lookup"><span data-stu-id="185d1-228">Some examples are:</span></span>

- <span data-ttu-id="185d1-229">Usar a área de transferência para copiar e colar um script.</span><span class="sxs-lookup"><span data-stu-id="185d1-229">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="185d1-230">Isso é comum em cenários como:</span><span class="sxs-lookup"><span data-stu-id="185d1-230">This is common in scenarios like:</span></span>
  - <span data-ttu-id="185d1-231">Copiar um script para uma VM</span><span class="sxs-lookup"><span data-stu-id="185d1-231">Copying a script into a VM</span></span>
  - <span data-ttu-id="185d1-232">Copiar um script para fora de um email ou página da Web</span><span class="sxs-lookup"><span data-stu-id="185d1-232">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="185d1-233">Copiar um script de ou para um documento do Microsoft Word ou PowerPoint</span><span class="sxs-lookup"><span data-stu-id="185d1-233">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="185d1-234">Outros editores de texto, como:</span><span class="sxs-lookup"><span data-stu-id="185d1-234">Other text editors, such as:</span></span>
  - <span data-ttu-id="185d1-235">Bloco de notas</span><span class="sxs-lookup"><span data-stu-id="185d1-235">Notepad</span></span>
  - <span data-ttu-id="185d1-236">vim</span><span class="sxs-lookup"><span data-stu-id="185d1-236">vim</span></span>
  - <span data-ttu-id="185d1-237">Qualquer outro editor de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="185d1-237">Any other PowerShell script editor</span></span>
- <span data-ttu-id="185d1-238">Utilitários de edição de texto, como:</span><span class="sxs-lookup"><span data-stu-id="185d1-238">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="185d1-239">Operadores de redirecionamento do PowerShell, como `>` e `>>`</span><span class="sxs-lookup"><span data-stu-id="185d1-239">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="185d1-240">Programas de transferência de arquivos, como:</span><span class="sxs-lookup"><span data-stu-id="185d1-240">File transfer programs, like:</span></span>
  - <span data-ttu-id="185d1-241">Um navegador da Web, ao baixar scripts</span><span class="sxs-lookup"><span data-stu-id="185d1-241">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="185d1-242">Um compartilhamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="185d1-242">A file share</span></span>

<span data-ttu-id="185d1-243">Algumas dessas ferramentas lidam com bytes em vez de texto, mas outras oferecem configurações de codificação.</span><span class="sxs-lookup"><span data-stu-id="185d1-243">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="185d1-244">Nos casos em que precisa configurar uma codificação, você precisa fazer com que ela seja igual à codificação de seu editor para evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="185d1-244">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="185d1-245">Outros recursos sobre codificação no PowerShell</span><span class="sxs-lookup"><span data-stu-id="185d1-245">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="185d1-246">Há algumas outras postagens interessantes sobre codificação e configuração da codificação do PowerShell que merecem uma leitura:</span><span class="sxs-lookup"><span data-stu-id="185d1-246">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- <span data-ttu-id="185d1-247">[Resumo de [@mklement0] sobre a codificação do PowerShell no StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="185d1-247">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="185d1-248">Problemas anteriores abertos no VS Code-PowerShell referentes a problemas de codificação:</span><span class="sxs-lookup"><span data-stu-id="185d1-248">Previous issues opened on VS Code-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="185d1-249">#1308</span><span class="sxs-lookup"><span data-stu-id="185d1-249">#1308</span></span>](https://github.com/PowerShell/VS Code-powershell/issues/1308)
  - [<span data-ttu-id="185d1-250">#1628</span><span class="sxs-lookup"><span data-stu-id="185d1-250">#1628</span></span>](https://github.com/PowerShell/VS Code-powershell/issues/1628)
  - [<span data-ttu-id="185d1-251">#1680</span><span class="sxs-lookup"><span data-stu-id="185d1-251">#1680</span></span>](https://github.com/PowerShell/VS Code-powershell/issues/1680)
  - [<span data-ttu-id="185d1-252">#1744</span><span class="sxs-lookup"><span data-stu-id="185d1-252">#1744</span></span>](https://github.com/PowerShell/VS Code-powershell/issues/1744)
  - [<span data-ttu-id="185d1-253">#1751</span><span class="sxs-lookup"><span data-stu-id="185d1-253">#1751</span></span>](https://github.com/PowerShell/VS Code-powershell/issues/1751)
- [<span data-ttu-id="185d1-254">O artigo clássico de *Joel on Software* sobre Unicode</span><span class="sxs-lookup"><span data-stu-id="185d1-254">The classic *Joel on Software* write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="185d1-255">Codificação no .NET Standard</span><span class="sxs-lookup"><span data-stu-id="185d1-255">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)


[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[marca de ordem de byte]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[Protocolo de servidor de linguagem]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[Codificação de VS Code]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VS Code's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
