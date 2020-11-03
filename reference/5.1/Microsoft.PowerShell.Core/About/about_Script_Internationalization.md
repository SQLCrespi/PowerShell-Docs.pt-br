---
description: Descreve os recursos de internacionalização de script que tornam mais fácil para os scripts exibir mensagens e instruções para os usuários em sua linguagem de interface do usuário.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 51772eeb7517b5c61d9bc7a4333642684de6c37e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195968"
---
# <a name="about-script-internationalization"></a><span data-ttu-id="9e0d5-104">Sobre a internacionalização de script</span><span class="sxs-lookup"><span data-stu-id="9e0d5-104">About Script Internationalization</span></span>

## <a name="short-description"></a><span data-ttu-id="9e0d5-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="9e0d5-105">Short Description</span></span>
<span data-ttu-id="9e0d5-106">Descreve os recursos de internacionalização de script que tornam mais fácil para os scripts exibir mensagens e instruções para os usuários em sua linguagem de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-106">Describes the script internationalization features that make it easy for scripts to display messages and instructions to users in their user interface (UI) language.</span></span>

## <a name="long-description"></a><span data-ttu-id="9e0d5-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="9e0d5-107">Long Description</span></span>

<span data-ttu-id="9e0d5-108">Os recursos de internacionalização de script do PowerShell permitem que você atenda melhor aos usuários em todo o mundo, exibindo ajuda e mensagens de usuário no idioma do usuário.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-108">The PowerShell script internationalization features allow you to better serve users throughout the world by displaying help and user messages in the user's language.</span></span>

<span data-ttu-id="9e0d5-109">Os recursos de internacionalização de script consultam a cultura da interface do usuário do sistema operacional durante a execução, importam as cadeias de caracteres de texto traduzidas apropriadas e as exibem para o usuário.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-109">The script internationalization features query the UI culture of the operating system during execution, import the appropriate translated text strings, and display them to the user.</span></span> <span data-ttu-id="9e0d5-110">A seção de dados permite que você armazene cadeias de caracteres de texto separadas do código para que elas sejam facilmente identificadas e extraídas.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-110">The Data section lets you store text strings separate from code so they are easily identified and extracted.</span></span> <span data-ttu-id="9e0d5-111">Um novo cmdlet, `ConvertFrom-StringData` , converte cadeias de caracteres de texto em tabelas de hash do tipo dicionário para facilitar a tradução.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-111">A new cmdlet, `ConvertFrom-StringData`, converts text strings into dictionary-like hash tables to facilitate translation.</span></span>

<span data-ttu-id="9e0d5-112">Para dar suporte ao texto de ajuda internacional, o PowerShell inclui os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-112">To support international Help text, PowerShell includes the following features:</span></span>

- <span data-ttu-id="9e0d5-113">Uma seção de dados que separa cadeias de caracteres de texto das instruções de código.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-113">A Data section that separates text strings from code instructions.</span></span> <span data-ttu-id="9e0d5-114">Para obter mais informações sobre a seção de dados, consulte [about_Data_Sections](about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="9e0d5-114">For more information about the Data section, see [about_Data_Sections](about_Data_Sections.md).</span></span>

- <span data-ttu-id="9e0d5-115">Novas variáveis automáticas `$PSCulture` e `$PSUICulture` .</span><span class="sxs-lookup"><span data-stu-id="9e0d5-115">New automatic variables, `$PSCulture` and `$PSUICulture`.</span></span> <span data-ttu-id="9e0d5-116">`$PSCulture` armazena o nome do idioma da interface do usuário usado no sistema para elementos como data, hora e moeda.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-116">`$PSCulture` stores the name of the UI language used on the system for elements such as the date, time, and currency.</span></span> <span data-ttu-id="9e0d5-117">A `$PSUICulture` variável armazena o nome do idioma da interface do usuário usado no sistema para elementos de interface de usuários, como menus e cadeias de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-117">The `$PSUICulture` variable stores the name of the UI language used on the system for user interface elements such as menus and text strings.</span></span>

- <span data-ttu-id="9e0d5-118">Um cmdlet, `ConvertFrom-StringData` , que converte cadeias de caracteres de texto em tabelas de hash do tipo dicionário para facilitar a tradução.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-118">A cmdlet, `ConvertFrom-StringData`, that converts text strings into dictionary-like hash tables to facilitate translation.</span></span> <span data-ttu-id="9e0d5-119">Para obter mais informações, consulte [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span><span class="sxs-lookup"><span data-stu-id="9e0d5-119">For more information, see [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span></span>

- <span data-ttu-id="9e0d5-120">Um novo tipo de arquivo, `.psd1` , que armazena cadeias de caracteres de texto traduzidas.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-120">A new file type, `.psd1`, that stores translated text strings.</span></span> <span data-ttu-id="9e0d5-121">Os `.psd1` arquivos são armazenados em subdiretórios específicos do idioma do diretório do script.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-121">The `.psd1` files are stored in language-specific subdirectories of the script directory.</span></span>

- <span data-ttu-id="9e0d5-122">Um cmdlet, `Import-LocalizedData` , que importa cadeias de caracteres de texto traduzidas para um idioma especificado em um script em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-122">A cmdlet, `Import-LocalizedData`, that imports translated text strings for a specified language into a script at runtime.</span></span> <span data-ttu-id="9e0d5-123">Esse cmdlet reconhece e importa cadeias de caracteres em qualquer idioma com suporte do Windows.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-123">This cmdlet recognizes and imports strings in any Windows-supported language.</span></span> <span data-ttu-id="9e0d5-124">Para obter mais informações, consulte [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span><span class="sxs-lookup"><span data-stu-id="9e0d5-124">For more information see [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span></span>

### <a name="the-data-section-storing-default-strings"></a><span data-ttu-id="9e0d5-125">A seção de dados: armazenando cadeias de caracteres padrão</span><span class="sxs-lookup"><span data-stu-id="9e0d5-125">The Data Section: Storing Default Strings</span></span>

<span data-ttu-id="9e0d5-126">Use uma seção de dados no script para armazenar as cadeias de caracteres de texto no idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-126">Use a Data section in the script to store the text strings in the default language.</span></span> <span data-ttu-id="9e0d5-127">Organize as cadeias de caracteres em pares de chave/valor em uma cadeia aqui.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-127">Arrange the strings in key/value pairs in a here-string.</span></span> <span data-ttu-id="9e0d5-128">Cada par chave/valor deve estar em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-128">Each key/value pair must be on a separate line.</span></span> <span data-ttu-id="9e0d5-129">Se você incluir comentários, os comentários deverão estar em linhas separadas.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-129">If you include comments, the comments must be on separate lines.</span></span>

<span data-ttu-id="9e0d5-130">O `ConvertFrom-StringData` cmdlet converte os pares de chave/valor na cadeia de caracteres here em uma tabela de hash do tipo dicionário que é armazenada no valor da variável da seção de dados.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-130">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a dictionary-like hash table that is stored in the value of the Data section variable.</span></span>

<span data-ttu-id="9e0d5-131">No exemplo a seguir, a seção de dados do `World.ps1` script inclui o conjunto de mensagens de prompt do English-United Estados (en-US) de um script.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-131">In the following example, the Data section of the `World.ps1` script includes the English-United States (en-US) set of prompt messages for a script.</span></span> <span data-ttu-id="9e0d5-132">O `ConvertFrom-StringData` cmdlet converte as cadeias de caracteres em uma tabela de hash e as armazena na `$msgtable` variável.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-132">The `ConvertFrom-StringData` cmdlet converts the strings into a hash table and stores them in the `$msgtable` variable.</span></span>

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

<span data-ttu-id="9e0d5-133">Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9e0d5-133">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

### <a name="psd1-files-storing-translated-strings"></a><span data-ttu-id="9e0d5-134">Arquivos PSD1: armazenando cadeias de caracteres traduzidas</span><span class="sxs-lookup"><span data-stu-id="9e0d5-134">PSD1 Files: Storing Translated Strings</span></span>

<span data-ttu-id="9e0d5-135">Salve as mensagens de script para cada idioma da interface do usuário em arquivos de texto separados com o mesmo nome que o script e a `.psd1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-135">Save the script messages for each UI language in separate text files with the same name as the script and the `.psd1` file name extension.</span></span> <span data-ttu-id="9e0d5-136">Armazene os arquivos em subdiretórios do diretório de script com nomes de culturas no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-136">Store the files in subdirectories of the script directory with names of cultures in the following format:</span></span>

`<language>-<region>`

<span data-ttu-id="9e0d5-137">Exemplos: de-DE, ar-SA e zh-Hans</span><span class="sxs-lookup"><span data-stu-id="9e0d5-137">Examples: de-DE, ar-SA, and zh-Hans</span></span>

<span data-ttu-id="9e0d5-138">Por exemplo, se o `World.ps1` script for armazenado no `C:\Scripts` diretório, você criaria uma estrutura de diretório de arquivos semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-138">For example, if the `World.ps1` script is stored in the `C:\Scripts` directory, you would create a file directory structure that resembles the following:</span></span>

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

<span data-ttu-id="9e0d5-139">O `World.psd1` arquivo no subdiretório de de um do diretório de script pode incluir a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-139">The `World.psd1` file in the de-DE subdirectory of the script directory might include the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

<span data-ttu-id="9e0d5-140">Da mesma forma, o `World.psd1` arquivo no subdiretório ar-SA do diretório de script pode incluir a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-140">Similarly, the `World.psd1` file in the ar-SA subdirectory of the script directory might includes the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a><span data-ttu-id="9e0d5-141">Import-LocalizedData: recuperação dinâmica de cadeias de caracteres traduzidas</span><span class="sxs-lookup"><span data-stu-id="9e0d5-141">Import-LocalizedData: Dynamic Retrieval of Translated Strings</span></span>

<span data-ttu-id="9e0d5-142">Para recuperar as cadeias de caracteres no idioma da interface do usuário atual, use o `Import-LocalizedData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-142">To retrieve the strings in the UI language of the current user, use the `Import-LocalizedData` cmdlet.</span></span>

<span data-ttu-id="9e0d5-143">`Import-LocalizedData` localiza o valor da `$PSUICulture` variável automática e importa o conteúdo dos `<script-name>.psd1` arquivos no subdiretório que corresponde ao `$PSUICulture` valor.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-143">`Import-LocalizedData` finds the value of the `$PSUICulture` automatic variable and imports the content of the `<script-name>.psd1` files in the subdirectory that matches the `$PSUICulture` value.</span></span> <span data-ttu-id="9e0d5-144">Em seguida, ele salva o conteúdo importado na variável especificada pelo valor do parâmetro **BindingVariable** .</span><span class="sxs-lookup"><span data-stu-id="9e0d5-144">Then, it saves the imported content in the variable specified by the value of the **BindingVariable** parameter.</span></span>

```powershell
Import-LocalizedData -BindingVariable msgTable
```

<span data-ttu-id="9e0d5-145">Por exemplo, se o `Import-LocalizedData` comando aparecer no `C:\Scripts\World.ps1` script e o valor de `$PSUICulture` for "ar-SA", `Import-LocalizedData` o encontrará o seguinte arquivo:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-145">For example, if the `Import-LocalizedData` command appears in the `C:\Scripts\World.ps1` script and the value of `$PSUICulture` is "ar-SA", `Import-LocalizedData` finds the following file:</span></span>

`C:\Scripts\ar-SA\World.psd1`

<span data-ttu-id="9e0d5-146">Em seguida, ele importa as cadeias de caracteres de texto árabes do arquivo para a `$msgTable` variável, substituindo quaisquer cadeias de caracteres padrão que possam ser definidas na seção de dados do `World.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-146">Then, it imports the Arabic text strings from the file into the `$msgTable` variable, replacing any default strings that might be defined in the Data section of the `World.ps1` script.</span></span>

<span data-ttu-id="9e0d5-147">Como resultado, quando o script usa a `$msgTable` variável para exibir mensagens do usuário, as mensagens são exibidas em árabe.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-147">As a result, when the script uses the `$msgTable` variable to display user messages, the messages are displayed in Arabic.</span></span>

<span data-ttu-id="9e0d5-148">Por exemplo, o script a seguir exibe a mensagem "Insira seu nome de usuário" em árabe:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-148">For example, the following script displays the "Please enter your user name" message in Arabic:</span></span>

```powershell
if (!($username)) { $msgTable.promptMsg }
```

<span data-ttu-id="9e0d5-149">Se o `Import-LocalizedData` não puder encontrar um `.psd1` arquivo que corresponda ao valor de `$PSUIculture` , o valor de `$msgTable` não será substituído e a chamada para `$msgTable.promptMsg` exibirá as cadeias de caracteres de fallback en-US.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-149">If `Import-LocalizedData` cannot find a `.psd1` file that matches the value of `$PSUIculture`, the value of `$msgTable` is not replaced, and the call to `$msgTable.promptMsg` displays the fallback en-US strings.</span></span>

## <a name="examples"></a><span data-ttu-id="9e0d5-150">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9e0d5-150">Examples</span></span>

<span data-ttu-id="9e0d5-151">Este exemplo mostra como os recursos de internacionalização de script são usados em um script para exibir um dia da semana para os usuários no idioma definido no computador.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-151">This example shows how the script internationalization features are used in a script to display a day of the week to users in the language that is set on the computer.</span></span>

<span data-ttu-id="9e0d5-152">A seguir está uma lista completa do arquivo de script Sample1.ps1.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-152">The following is a complete listing of the Sample1.ps1 script file.</span></span>

<span data-ttu-id="9e0d5-153">O script começa com uma seção de dados denominada Day ($Day) que contém um `ConvertFrom-StringData` comando.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-153">The script begins with a Data section named Day ($Day) that contains a `ConvertFrom-StringData` command.</span></span> <span data-ttu-id="9e0d5-154">A expressão enviada para `ConvertFrom-StringData` é uma cadeia de caracteres aqui que contém os nomes de dia na cultura da interface do usuário padrão, en-US, em pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-154">The expression submitted to `ConvertFrom-StringData` is a here-string that contains the day names in the default UI culture, en-US, in key/value pairs.</span></span> <span data-ttu-id="9e0d5-155">O `ConvertFrom-StringData` cmdlet converte os pares de chave/valor na cadeia de caracteres here em uma tabela de hash e, em seguida, salva-os no valor da `$Day` variável.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-155">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a hash table and then saves it in the value of the `$Day` variable.</span></span>

<span data-ttu-id="9e0d5-156">O `Import-LocalizedData` comando importa o conteúdo do `.psd1` arquivo no diretório que corresponde ao valor da `$PSUICulture` variável automática e, em seguida, salva-o na `$Day` variável, substituindo os valores de `$Day` definidos na seção de dados.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-156">The `Import-LocalizedData` command imports the contents of the `.psd1` file in the directory that matches the value of the `$PSUICulture` automatic variable and then saves it in the `$Day` variable, replacing the values of `$Day` that are defined in the Data section.</span></span>

<span data-ttu-id="9e0d5-157">Os comandos restantes carregam as cadeias de caracteres em uma matriz e as exibem.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-157">The remaining commands load the strings into an array and display them.</span></span>

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

<span data-ttu-id="9e0d5-158">Os `.psd1` arquivos que oferecem suporte ao script são salvos em subdiretórios do diretório de script com nomes que correspondem aos `$PSUICulture` valores.</span><span class="sxs-lookup"><span data-stu-id="9e0d5-158">The `.psd1` files that support the script are saved in subdirectories of the script directory with names that match the `$PSUICulture` values.</span></span>

<span data-ttu-id="9e0d5-159">A seguir está uma lista completa de `.\de-DE\sample1.psd1` :</span><span class="sxs-lookup"><span data-stu-id="9e0d5-159">The following is a complete listing of `.\de-DE\sample1.psd1`:</span></span>

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

<span data-ttu-id="9e0d5-160">Como resultado, quando você executa Sample.ps1 em um sistema no qual o valor de `$PSUICulture` é de-de, a saída do script é:</span><span class="sxs-lookup"><span data-stu-id="9e0d5-160">As a result, when you run Sample.ps1 on a system on which the value of `$PSUICulture` is de-DE, the output of the script is:</span></span>

```Output
Heute ist Freitag
```

## <a name="see-also"></a><span data-ttu-id="9e0d5-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e0d5-161">See also</span></span>

- [<span data-ttu-id="9e0d5-162">about_Data_Sections</span><span class="sxs-lookup"><span data-stu-id="9e0d5-162">about_Data_Sections</span></span>](about_Data_Sections.md)
- [<span data-ttu-id="9e0d5-163">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9e0d5-163">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="9e0d5-164">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="9e0d5-164">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="9e0d5-165">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="9e0d5-165">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="9e0d5-166">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="9e0d5-166">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [<span data-ttu-id="9e0d5-167">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="9e0d5-167">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
