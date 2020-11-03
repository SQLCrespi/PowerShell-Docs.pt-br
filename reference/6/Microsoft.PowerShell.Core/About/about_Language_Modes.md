---
description: Explica os modos de linguagem e seu efeito nas sessões do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 8254760e49d5d9b2d1b035038b14414b0074435c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195716"
---
# <a name="about-language-modes"></a><span data-ttu-id="09877-104">Sobre os modos de linguagem</span><span class="sxs-lookup"><span data-stu-id="09877-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="09877-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="09877-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="09877-106">Explica os modos de linguagem e seu efeito nas sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09877-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="09877-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="09877-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="09877-108">O modo de linguagem de uma sessão do PowerShell determina, em parte, quais elementos da linguagem do PowerShell podem ser usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="09877-109">O PowerShell dá suporte aos seguintes modos de linguagem:</span><span class="sxs-lookup"><span data-stu-id="09877-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="09877-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-110">FullLanguage</span></span>
- <span data-ttu-id="09877-111">ConstrainedLanguage (introduzido no PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="09877-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="09877-112">RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-112">RestrictedLanguage</span></span>
- <span data-ttu-id="09877-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="09877-114">O QUE É UM MODO DE LINGUAGEM?</span><span class="sxs-lookup"><span data-stu-id="09877-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="09877-115">O modo de linguagem determina os elementos de linguagem que são permitidos na sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="09877-116">O modo de linguagem é, na verdade, uma propriedade da configuração de sessão (ou "ponto de extremidade") usada para criar a sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="09877-117">Todas as sessões que usam uma configuração de sessão específica têm o modo de linguagem da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="09877-118">Todas as sessões do PowerShell têm um modo de linguagem, incluindo PSSessions que você cria usando o `New-PSSession` cmdlet, sessões temporárias que usam o parâmetro ComputerName e as sessões padrão que aparecem quando você inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09877-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="09877-119">As sessões remotas são criadas usando as configurações de sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="09877-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="09877-120">O modo de linguagem definido na configuração de sessão determina o modo de linguagem da sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="09877-121">Para especificar a configuração de sessão de uma PSSession, use o parâmetro ConfigurationName de cmdlets que criam uma sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="09877-122">MODOS DE LINGUAGEM</span><span class="sxs-lookup"><span data-stu-id="09877-122">LANGUAGE MODES</span></span>

<span data-ttu-id="09877-123">Esta seção descreve os modos de linguagem em sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09877-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="09877-124">LINGUAGEM completa (FullLanguage)</span><span class="sxs-lookup"><span data-stu-id="09877-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="09877-125">O modo FullLanguage permite todos os elementos de linguagem na sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="09877-126">FullLanguage é o modo de idioma padrão para sessões padrão em todas as versões do Windows, exceto para o Windows RT.</span><span class="sxs-lookup"><span data-stu-id="09877-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="09877-127">LINGUAGEM restrita (RestrictedLanguage)</span><span class="sxs-lookup"><span data-stu-id="09877-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="09877-128">No modo RestrictedLanguage, os usuários podem executar comandos (cmdlets, funções, comandos CIM e fluxos de trabalho), mas não têm permissão para usar blocos de script.</span><span class="sxs-lookup"><span data-stu-id="09877-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="09877-129">Por padrão, somente as seguintes variáveis são permitidas no modo RestrictedLanguage:</span><span class="sxs-lookup"><span data-stu-id="09877-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="09877-130">Os manifestos de módulo, que usam o modo RestrictedLanguage, também permitem as seguintes variáveis adicionais:</span><span class="sxs-lookup"><span data-stu-id="09877-130">Module manifests, which use RestrictedLanguage mode, permit the following additional variables as well:</span></span>

- `$PSScriptRoot`
- <span data-ttu-id="09877-131">`$PSEdition` (no PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="09877-131">`$PSEdition` (in PowerShell Core)</span></span>
- <span data-ttu-id="09877-132">`$EnabledExperimentalFeatures` (no PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="09877-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span></span>

<span data-ttu-id="09877-133">Somente os seguintes operadores de comparação são permitidos:</span><span class="sxs-lookup"><span data-stu-id="09877-133">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="09877-134">`-eq` iguais</span><span class="sxs-lookup"><span data-stu-id="09877-134">`-eq` (equal)</span></span>
- <span data-ttu-id="09877-135">`-gt` (maior que)</span><span class="sxs-lookup"><span data-stu-id="09877-135">`-gt` (greater-than)</span></span>
- <span data-ttu-id="09877-136">`-lt` (menor que)</span><span class="sxs-lookup"><span data-stu-id="09877-136">`-lt` (less-than)</span></span>

<span data-ttu-id="09877-137">Não são permitidas instruções de atribuição, referências de propriedade e chamadas de método.</span><span class="sxs-lookup"><span data-stu-id="09877-137">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="09877-138">SEM idioma (nolanguage)</span><span class="sxs-lookup"><span data-stu-id="09877-138">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="09877-139">O modo nolanguage só pode ser usado por meio da API.</span><span class="sxs-lookup"><span data-stu-id="09877-139">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="09877-140">O modo nolanguage significa que nenhum texto de script de qualquer formulário é permitido.</span><span class="sxs-lookup"><span data-stu-id="09877-140">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="09877-141">Isso impede o uso do método **addScript ()** que envia fragmentos de script do PowerShell a serem analisados e executados.</span><span class="sxs-lookup"><span data-stu-id="09877-141">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="09877-142">Você só pode usar **AddCommand ()** e **AddParameter ()** que não passam pelo analisador.</span><span class="sxs-lookup"><span data-stu-id="09877-142">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="09877-143">IDIOMA restrito (idioma restrito)</span><span class="sxs-lookup"><span data-stu-id="09877-143">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="09877-144">O modo ConstrainedLanguage permite todos os cmdlets e todos os elementos de linguagem do PowerShell, mas limita os tipos permitidos.</span><span class="sxs-lookup"><span data-stu-id="09877-144">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="09877-145">O modo ConstrainedLanguage foi projetado para dar suporte à integridade de código do modo de usuário (UMCI) no Windows RT.</span><span class="sxs-lookup"><span data-stu-id="09877-145">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="09877-146">É o único modo de linguagem com suporte no Windows RT, mas está disponível em todos os sistemas com suporte.</span><span class="sxs-lookup"><span data-stu-id="09877-146">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="09877-147">O UMCI protege os dispositivos ARM, permitindo que apenas aplicativos assinados pela Microsoft e Microsoft sejam instalados em dispositivos baseados no Windows RT.</span><span class="sxs-lookup"><span data-stu-id="09877-147">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="09877-148">O modo ConstrainedLanguage impede que os usuários usem o PowerShell para burlar ou violar UMCI.</span><span class="sxs-lookup"><span data-stu-id="09877-148">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="09877-149">Os recursos do modo ConstrainedLanguage são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="09877-149">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="09877-150">Todos os cmdlets em módulos do Windows e outros cmdlets aprovados por UMCI, são totalmente funcionais e têm acesso completo aos recursos do sistema, exceto quando observado.</span><span class="sxs-lookup"><span data-stu-id="09877-150">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="09877-151">Todos os elementos da linguagem de script do PowerShell são permitidos.</span><span class="sxs-lookup"><span data-stu-id="09877-151">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="09877-152">Todos os módulos incluídos no Windows podem ser importados e todos os comandos que os módulos exportam são executados na sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-152">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="09877-153">No fluxo de trabalho do PowerShell, você pode gravar e executar fluxos de trabalho de script (fluxos de trabalho escritos na linguagem do PowerShell).</span><span class="sxs-lookup"><span data-stu-id="09877-153">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="09877-154">Não há suporte para fluxos de trabalho baseados em XAML e você não pode executar XAML em um fluxo de trabalho de script, como usando `Invoke-Expression -Language XAML` .</span><span class="sxs-lookup"><span data-stu-id="09877-154">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="09877-155">Além disso, os fluxos de trabalho não podem chamar outros fluxos de trabalho, embora os fluxos de trabalho aninhados sejam permitidos.</span><span class="sxs-lookup"><span data-stu-id="09877-155">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="09877-156">O `Add-Type` cmdlet pode carregar assemblies assinados, mas não pode carregar código C# arbitrário ou APIs do Win32.</span><span class="sxs-lookup"><span data-stu-id="09877-156">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="09877-157">O `New-Object` cmdlet pode ser usado somente em tipos permitidos (listados abaixo).</span><span class="sxs-lookup"><span data-stu-id="09877-157">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="09877-158">Somente os tipos permitidos (listados abaixo) podem ser usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09877-158">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="09877-159">Outros tipos não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="09877-159">Other types are not permitted.</span></span>

- <span data-ttu-id="09877-160">A conversão de tipo é permitida, mas somente quando o resultado é um tipo permitido.</span><span class="sxs-lookup"><span data-stu-id="09877-160">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="09877-161">Parâmetros de cmdlet que convertem entrada de cadeia de caracteres em tipos só funcionam quando o tipo resultante é um tipo permitido.</span><span class="sxs-lookup"><span data-stu-id="09877-161">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="09877-162">O método **ToString ()** e os métodos .net de tipos permitidos (listados abaixo) podem ser invocados.</span><span class="sxs-lookup"><span data-stu-id="09877-162">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="09877-163">Outros métodos não podem ser invocados.</span><span class="sxs-lookup"><span data-stu-id="09877-163">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="09877-164">Os usuários podem obter todas as propriedades de tipos permitidos.</span><span class="sxs-lookup"><span data-stu-id="09877-164">Users can get all properties of allowed types.</span></span> <span data-ttu-id="09877-165">Os usuários podem definir os valores de propriedades somente em tipos de núcleo.</span><span class="sxs-lookup"><span data-stu-id="09877-165">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="09877-166">Somente os seguintes objetos COM são permitidos:</span><span class="sxs-lookup"><span data-stu-id="09877-166">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="09877-167">**Script. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="09877-167">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="09877-168">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="09877-168">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="09877-169">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="09877-169">**VBScript.RegExp**</span></span>

<span data-ttu-id="09877-170">Os tipos a seguir são permitidos no modo ConstrainedLanguage.</span><span class="sxs-lookup"><span data-stu-id="09877-170">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="09877-171">Os usuários podem obter propriedades, invocar métodos e converter objetos para esses tipos.</span><span class="sxs-lookup"><span data-stu-id="09877-171">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="09877-172">Tipos permitidos:</span><span class="sxs-lookup"><span data-stu-id="09877-172">Allowed Types:</span></span>

- <span data-ttu-id="09877-173">AliasAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-173">AliasAttribute</span></span>
- <span data-ttu-id="09877-174">AllowEmptyCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-174">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="09877-175">AllowEmptyStringAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-175">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="09877-176">AllowNullAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-176">AllowNullAttribute</span></span>
- <span data-ttu-id="09877-177">Array</span><span class="sxs-lookup"><span data-stu-id="09877-177">Array</span></span>
- <span data-ttu-id="09877-178">Bool</span><span class="sxs-lookup"><span data-stu-id="09877-178">Bool</span></span>
- <span data-ttu-id="09877-179">byte</span><span class="sxs-lookup"><span data-stu-id="09877-179">byte</span></span>
- <span data-ttu-id="09877-180">char</span><span class="sxs-lookup"><span data-stu-id="09877-180">char</span></span>
- <span data-ttu-id="09877-181">CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-181">CmdletBindingAttribute</span></span>
- <span data-ttu-id="09877-182">Datetime</span><span class="sxs-lookup"><span data-stu-id="09877-182">DateTime</span></span>
- <span data-ttu-id="09877-183">decimal</span><span class="sxs-lookup"><span data-stu-id="09877-183">decimal</span></span>
- <span data-ttu-id="09877-184">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="09877-184">DirectoryEntry</span></span>
- <span data-ttu-id="09877-185">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="09877-185">DirectorySearcher</span></span>
- <span data-ttu-id="09877-186">double</span><span class="sxs-lookup"><span data-stu-id="09877-186">double</span></span>
- <span data-ttu-id="09877-187">FLOAT</span><span class="sxs-lookup"><span data-stu-id="09877-187">float</span></span>
- <span data-ttu-id="09877-188">Guid</span><span class="sxs-lookup"><span data-stu-id="09877-188">Guid</span></span>
- <span data-ttu-id="09877-189">Hashtable</span><span class="sxs-lookup"><span data-stu-id="09877-189">Hashtable</span></span>
- <span data-ttu-id="09877-190">INT</span><span class="sxs-lookup"><span data-stu-id="09877-190">int</span></span>
- <span data-ttu-id="09877-191">Int16</span><span class="sxs-lookup"><span data-stu-id="09877-191">Int16</span></span>
- <span data-ttu-id="09877-192">long</span><span class="sxs-lookup"><span data-stu-id="09877-192">long</span></span>
- <span data-ttu-id="09877-193">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="09877-193">ManagementClass</span></span>
- <span data-ttu-id="09877-194">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="09877-194">ManagementObject</span></span>
- <span data-ttu-id="09877-195">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="09877-195">ManagementObjectSearcher</span></span>
- <span data-ttu-id="09877-196">Valor nulo</span><span class="sxs-lookup"><span data-stu-id="09877-196">NullString</span></span>
- <span data-ttu-id="09877-197">OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-197">OutputTypeAttribute</span></span>
- <span data-ttu-id="09877-198">Parâmetroattribute</span><span class="sxs-lookup"><span data-stu-id="09877-198">ParameterAttribute</span></span>
- <span data-ttu-id="09877-199">PSCredential</span><span class="sxs-lookup"><span data-stu-id="09877-199">PSCredential</span></span>
- <span data-ttu-id="09877-200">PSDefaultValueAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-200">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="09877-201">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="09877-201">PSListModifier</span></span>
- <span data-ttu-id="09877-202">PSObject</span><span class="sxs-lookup"><span data-stu-id="09877-202">PSObject</span></span>
- <span data-ttu-id="09877-203">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="09877-203">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="09877-204">PSReference</span><span class="sxs-lookup"><span data-stu-id="09877-204">PSReference</span></span>
- <span data-ttu-id="09877-205">PSTypeNameAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-205">PSTypeNameAttribute</span></span>
- <span data-ttu-id="09877-206">Regex</span><span class="sxs-lookup"><span data-stu-id="09877-206">Regex</span></span>
- <span data-ttu-id="09877-207">SByte</span><span class="sxs-lookup"><span data-stu-id="09877-207">SByte</span></span>
- <span data-ttu-id="09877-208">string</span><span class="sxs-lookup"><span data-stu-id="09877-208">string</span></span>
- <span data-ttu-id="09877-209">SupportsWildcardsAttribute</span><span class="sxs-lookup"><span data-stu-id="09877-209">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="09877-210">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="09877-210">SwitchParameter</span></span>
- <span data-ttu-id="09877-211">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="09877-211">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="09877-212">System .net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="09877-212">System.Net.IPAddress</span></span>
- <span data-ttu-id="09877-213">System .net. mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="09877-213">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="09877-214">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="09877-214">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="09877-215">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="09877-215">System.Security.SecureString</span></span>
- <span data-ttu-id="09877-216">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="09877-216">TimeSpan</span></span>
- <span data-ttu-id="09877-217">UInt16</span><span class="sxs-lookup"><span data-stu-id="09877-217">UInt16</span></span>
- <span data-ttu-id="09877-218">UInt32</span><span class="sxs-lookup"><span data-stu-id="09877-218">UInt32</span></span>
- <span data-ttu-id="09877-219">UInt64</span><span class="sxs-lookup"><span data-stu-id="09877-219">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="09877-220">LOCALIZANDO O MODO DE LINGUAGEM DE UMA CONFIGURAÇÃO DE SESSÃO</span><span class="sxs-lookup"><span data-stu-id="09877-220">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="09877-221">Quando uma configuração de sessão é criada usando um arquivo de configuração de sessão, a configuração de sessão tem uma propriedade Languagemode.</span><span class="sxs-lookup"><span data-stu-id="09877-221">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="09877-222">Você pode encontrar o modo de linguagem obtendo o valor da propriedade Languagemode.</span><span class="sxs-lookup"><span data-stu-id="09877-222">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="09877-223">Em outras configurações de sessão, você pode encontrar o modo de linguagem indiretamente encontrando o modo de linguagem de uma sessão que é criada usando a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-223">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="09877-224">LOCALIZANDO O MODO DE LINGUAGEM DE UMA SESSÃO</span><span class="sxs-lookup"><span data-stu-id="09877-224">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="09877-225">Você pode encontrar o modo de linguagem de uma sessão FullLanguage ou ConstrainedLanguage obtendo o valor da propriedade Languagemode do estado da sessão.</span><span class="sxs-lookup"><span data-stu-id="09877-225">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="09877-226">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="09877-226">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="09877-227">No entanto, em sessões com modos RestrictedLanguage e nolanguage, você não pode usar o método dot para obter valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="09877-227">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="09877-228">Em vez disso, a mensagem de erro revela o modo de linguagem.</span><span class="sxs-lookup"><span data-stu-id="09877-228">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="09877-229">Quando você executa o `$ExecutionContext.SessionState.LanguageMode` comando em uma sessão RestrictedLanguage, o PowerShell retorna as mensagens de erro PropertyReferenceNotSupportedInDataSection e VariableReferenceNotSupportedInDataSection.</span><span class="sxs-lookup"><span data-stu-id="09877-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="09877-230">PropertyReferenceNotSupportedInDataSection: referências de propriedade não são permitidas no modo de linguagem restrita ou em uma seção de dados.</span><span class="sxs-lookup"><span data-stu-id="09877-230">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="09877-231">VariableReferenceNotSupportedInDataSection uma variável que não pode ser referenciada no modo de linguagem restrita ou uma seção de dados está sendo referenciada.</span><span class="sxs-lookup"><span data-stu-id="09877-231">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="09877-232">Quando você executa o `$ExecutionContext.SessionState.LanguageMode` comando em uma sessão nolanguage, o PowerShell retorna a mensagem de erro ScriptsNotAllowed.</span><span class="sxs-lookup"><span data-stu-id="09877-232">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="09877-233">ScriptsNotAllowed: não há suporte para a sintaxe neste runspace.</span><span class="sxs-lookup"><span data-stu-id="09877-233">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="09877-234">Isso pode ocorrer porque ele não está no modo de linguagem.</span><span class="sxs-lookup"><span data-stu-id="09877-234">This might be because it is in no-language mode.</span></span>

## <a name="keywords"></a><span data-ttu-id="09877-235">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="09877-235">KEYWORDS</span></span>

- <span data-ttu-id="09877-236">about_ConstrainedLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-236">about_ConstrainedLanguage</span></span>
- <span data-ttu-id="09877-237">about_FullLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-237">about_FullLanguage</span></span>
- <span data-ttu-id="09877-238">about_NoLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-238">about_NoLanguage</span></span>
- <span data-ttu-id="09877-239">about_RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="09877-239">about_RestrictedLanguage</span></span>

## <a name="see-also"></a><span data-ttu-id="09877-240">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="09877-240">SEE ALSO</span></span>

- [<span data-ttu-id="09877-241">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="09877-241">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="09877-242">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="09877-242">about_Session_Configurations</span></span>](about_Session_Configurations.md)
