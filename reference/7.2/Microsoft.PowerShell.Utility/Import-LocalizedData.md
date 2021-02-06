---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: fa5de857b70ec05d30c42fbf8e51a9411d823018
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598018"
---
# <span data-ttu-id="1665b-102">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="1665b-102">Import-LocalizedData</span></span>

## <span data-ttu-id="1665b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1665b-103">SYNOPSIS</span></span>
<span data-ttu-id="1665b-104">Importa dados específicos de idioma para scripts e funções com base na cultura de interface de usuário selecionada para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1665b-104">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="1665b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1665b-105">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1665b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1665b-106">DESCRIPTION</span></span>

<span data-ttu-id="1665b-107">O `Import-LocalizedData` cmdlet recupera dinamicamente as cadeias de caracteres de um subdiretório cujo nome corresponde ao idioma da interface de usuário definido para o usuário atual do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1665b-107">The `Import-LocalizedData` cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span> <span data-ttu-id="1665b-108">Ele foi projetado para permitir que scripts exibam mensagens de usuário no idioma da interface do usuário selecionada pelo usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1665b-108">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="1665b-109">`Import-LocalizedData` importa dados de `.psd1` arquivos em subdiretórios específicos do idioma do diretório de script e os salva em uma variável local especificada no comando.</span><span class="sxs-lookup"><span data-stu-id="1665b-109">`Import-LocalizedData` imports data from `.psd1` files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span> <span data-ttu-id="1665b-110">O cmdlet seleciona o subdiretório e o arquivo com base no valor da `$PSUICulture` variável automática.</span><span class="sxs-lookup"><span data-stu-id="1665b-110">The cmdlet selects the subdirectory and file based on the value of the `$PSUICulture` automatic variable.</span></span> <span data-ttu-id="1665b-111">Quando você usa a variável local no script para exibir uma mensagem do usuário, a mensagem é exibida no idioma da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="1665b-111">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="1665b-112">Você pode usar os parâmetros de `Import-LocalizedData` para especificar uma cultura de interface de usuário alternativa, um caminho e um nome de arquivo, para adicionar comandos com suporte e para suprimir a mensagem de erro que aparece se os `.psd1` arquivos não forem encontrados.</span><span class="sxs-lookup"><span data-stu-id="1665b-112">You can use the parameters of `Import-LocalizedData` to specify an alternate UI culture, path, and filename, to add supported commands, and to suppress the error message that appears if the `.psd1` files are not found.</span></span>

<span data-ttu-id="1665b-113">O `Import-LocalizedData` cmdlet dá suporte à iniciativa de internacionalização de script que foi introduzida no Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="1665b-113">The `Import-LocalizedData` cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span> <span data-ttu-id="1665b-114">Essa iniciativa visa atender melhor os usuários do mundo todo, tornando mais fácil para scripts exibir mensagens de usuário no idioma da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1665b-114">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span> <span data-ttu-id="1665b-115">Para obter mais informações sobre isso e sobre o formato dos `.psd1` arquivos, consulte [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="1665b-115">For more information about this and about the format of the `.psd1` files, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="1665b-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1665b-116">EXAMPLES</span></span>

### <span data-ttu-id="1665b-117">Exemplo 1: importar cadeias de texto</span><span class="sxs-lookup"><span data-stu-id="1665b-117">Example 1: Import text strings</span></span>

<span data-ttu-id="1665b-118">Este exemplo importa cadeias de texto para a `$Messages` variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-118">This example imports text strings into the `$Messages` variable.</span></span> <span data-ttu-id="1665b-119">Ele usa os valores padrão de todos os outros parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1665b-119">It uses the default values of all other cmdlet parameters.</span></span>

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="1665b-120">Se o comando estiver incluído no script de Archives.ps1 no `C:\Test` diretório, e o valor da `$PsUICulture` variável automática for zh-CN, `Import-LocalizedData` o importará o `Archives.psd1` arquivo no `C:\test\zh-CN` diretório para a `$Messages` variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-120">If the command is included in the Archives.ps1 script in the `C:\Test` directory, and the value of the `$PsUICulture` automatic variable is zh-CN, `Import-LocalizedData` imports the `Archives.psd1` file in the `C:\test\zh-CN` directory into the `$Messages` variable.</span></span>

### <span data-ttu-id="1665b-121">Exemplo 2: importar cadeias de dados localizadas</span><span class="sxs-lookup"><span data-stu-id="1665b-121">Example 2: Import localized data strings</span></span>

<span data-ttu-id="1665b-122">Este exemplo é executado na linha de comando que não está em um script.</span><span class="sxs-lookup"><span data-stu-id="1665b-122">This example is run at the command line not in a script.</span></span> <span data-ttu-id="1665b-123">Ele obtém cadeias de caracteres de dados localizados do arquivo Test.psd1 e os exibe na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1665b-123">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span> <span data-ttu-id="1665b-124">Como o comando não é usado em um script, o parâmetro **FileName** é necessário.</span><span class="sxs-lookup"><span data-stu-id="1665b-124">Because the command is not used in a script, the **FileName** parameter is required.</span></span> <span data-ttu-id="1665b-125">O comando usa o parâmetro **UICulture** para especificar a cultura en-US.</span><span class="sxs-lookup"><span data-stu-id="1665b-125">The command uses the **UICulture** parameter to specify the en-US culture.</span></span>

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="1665b-126">`Import-LocalizedData` Retorna uma tabela de hash que contém as cadeias de caracteres de dados localizadas.</span><span class="sxs-lookup"><span data-stu-id="1665b-126">`Import-LocalizedData` returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="1665b-127">Exemplo 3: importar cadeias de caracteres de cultura da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="1665b-127">Example 3: Import UI culture strings</span></span>

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="1665b-128">Esse comando importa cadeias de texto para a `$MsgTbl` variável de um script.</span><span class="sxs-lookup"><span data-stu-id="1665b-128">This command imports text strings into the `$MsgTbl` variable of a script.</span></span>

<span data-ttu-id="1665b-129">Ele usa o parâmetro **UICulture** para direcionar o cmdlet para importar dados do `Simple.psd1` arquivo no `ar-SA` subdiretório de `C:\Data\Localized` .</span><span class="sxs-lookup"><span data-stu-id="1665b-129">It uses the **UICulture** parameter to direct the cmdlet to import data from the `Simple.psd1` file in the `ar-SA` subdirectory of `C:\Data\Localized`.</span></span>

### <span data-ttu-id="1665b-130">Exemplo 4: importar dados localizados em um script</span><span class="sxs-lookup"><span data-stu-id="1665b-130">Example 4: Import localized data into a script</span></span>

<span data-ttu-id="1665b-131">Este exemplo mostra como usar dados localizados em um script simples.</span><span class="sxs-lookup"><span data-stu-id="1665b-131">This example shows how to use localized data in a simple script.</span></span>

```powershell
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

<span data-ttu-id="1665b-132">A primeira parte do exemplo mostra o conteúdo do `Test.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="1665b-132">The first part of the example shows the contents of the `Test.psd1` file.</span></span> <span data-ttu-id="1665b-133">Ele contém um `ConvertFrom-StringData` comando que converte uma série de cadeias de caracteres de texto nomeadas em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="1665b-133">It contains a `ConvertFrom-StringData` command that converts a series of named text strings into a hash table.</span></span> <span data-ttu-id="1665b-134">O `Test.psd1` arquivo está localizado no subdiretório en-US do `C:\Test` diretório que contém o script.</span><span class="sxs-lookup"><span data-stu-id="1665b-134">The `Test.psd1` file is located in the en-US subdirectory of the `C:\Test` directory that contains the script.</span></span>

<span data-ttu-id="1665b-135">A segunda parte do exemplo mostra o conteúdo do `Test.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="1665b-135">The second part of the example shows the contents of the `Test.ps1` script.</span></span> <span data-ttu-id="1665b-136">Ele contém um `Import-LocalizedData` comando que importa os dados do arquivo correspondente `.psd1` para a `$Messages` variável e um `Write-Host` comando que grava uma das mensagens na `$Messages` variável para o programa de host.</span><span class="sxs-lookup"><span data-stu-id="1665b-136">It contains an `Import-LocalizedData` command that imports the data from the matching `.psd1` file into the `$Messages` variable and a `Write-Host` command that writes one of the messages in the `$Messages` variable to the host program.</span></span>

<span data-ttu-id="1665b-137">A última parte do exemplo executa o script.</span><span class="sxs-lookup"><span data-stu-id="1665b-137">The last part of the example runs the script.</span></span> <span data-ttu-id="1665b-138">A saída mostra que ele exibe a mensagem do usuário correta no idioma da interface do usuário definido para o atual usuário do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1665b-138">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="1665b-139">Exemplo 5: substituir cadeias de caracteres de texto padrão em um script</span><span class="sxs-lookup"><span data-stu-id="1665b-139">Example 5: Replace default text strings in a script</span></span>

<span data-ttu-id="1665b-140">Este exemplo mostra como usar `Import-LocalizedData` para substituir as cadeias de caracteres de texto padrão definidas na seção de dados de um script.</span><span class="sxs-lookup"><span data-stu-id="1665b-140">This example shows how to use `Import-LocalizedData` to replace default text strings defined in the DATA section of a script.</span></span>

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="1665b-141">Neste exemplo, a seção de dados do script TestScript.ps1 contém um `ConvertFrom-StringData` comando que converte o conteúdo da seção de dados em uma tabela de hash e armazena no valor da `$UserMessages` variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-141">In this example, the DATA section of the TestScript.ps1 script contains a `ConvertFrom-StringData` command that converts the contents of the DATA section to a hash table and stores in the value of the `$UserMessages` variable.</span></span>

<span data-ttu-id="1665b-142">O script também inclui um `Import-LocalizedData` comando, que importa uma tabela de hash de cadeias de caracteres de texto traduzidas do arquivo TestScript.psd1 no subdiretório especificado pelo valor da `$PsUICulture` variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-142">The script also includes an `Import-LocalizedData` command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the `$PsUICulture` variable.</span></span> <span data-ttu-id="1665b-143">Se o comando Localizar o `.psd1` arquivo, ele salvará as cadeias de caracteres traduzidas do arquivo no valor da mesma `$UserMessages` variável, substituindo a tabela de hash salva pela lógica da seção de dados.</span><span class="sxs-lookup"><span data-stu-id="1665b-143">If the command finds the `.psd1` file, it saves the translated strings from the file in the value of the same `$UserMessages` variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="1665b-144">O terceiro comando exibe a primeira mensagem na `$UserMessages` variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-144">The third command displays the first message in the `$UserMessages` variable.</span></span>

<span data-ttu-id="1665b-145">Se o `Import-LocalizedData` comando encontrar um `.psd1` arquivo para o `$PsUICulture` idioma, o valor da `$UserMessages` variável conterá as cadeias de caracteres de texto traduzidas.</span><span class="sxs-lookup"><span data-stu-id="1665b-145">If the `Import-LocalizedData` command finds a `.psd1` file for the `$PsUICulture` language, the value of the `$UserMessages` variable contains the translated text strings.</span></span> <span data-ttu-id="1665b-146">Se o comando falhar por algum motivo, o comando exibe as cadeias de caracteres de texto padrão definidas na seção DATA do script.</span><span class="sxs-lookup"><span data-stu-id="1665b-146">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="1665b-147">Exemplo 6: suprimir mensagens de erro se a cultura da interface do usuário não for encontrada</span><span class="sxs-lookup"><span data-stu-id="1665b-147">Example 6: Suppress error messages if the UI culture is not found</span></span>

<span data-ttu-id="1665b-148">Este exemplo mostra como suprimir as mensagens de erro que aparecem quando `Import-LocalizedData` o não consegue encontrar os diretórios que correspondem à cultura da interface do usuário ou não pode encontrar um `.psd1` arquivo para o script nesses diretórios.</span><span class="sxs-lookup"><span data-stu-id="1665b-148">This example shows how to suppress the error messages that appear when `Import-LocalizedData` cannot find the directories that match the user's UI culture or cannot find a `.psd1` file for the script in those directories.</span></span>

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="1665b-149">Você pode usar o parâmetro comum **ErrorAction** com um valor de SilentlyContinue para suprimir a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1665b-149">You can use the **ErrorAction** common parameter with a value of SilentlyContinue to suppress the error message.</span></span> <span data-ttu-id="1665b-150">Isso é especialmente útil quando você forneceu mensagens de usuário em um idioma padrão ou de fallback, e nenhuma mensagem de erro é necessária.</span><span class="sxs-lookup"><span data-stu-id="1665b-150">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="1665b-151">Este exemplo compara dois scripts `Day1.ps1` e Day2.ps1, que incluem um `Import-LocalizedData` comando.</span><span class="sxs-lookup"><span data-stu-id="1665b-151">This example compares two scripts, `Day1.ps1` and Day2.ps1, that include an `Import-LocalizedData` command.</span></span> <span data-ttu-id="1665b-152">Os scripts são idênticos, exceto pelo fato de que Day2 usa o parâmetro comum **ErrorAction** com um valor de `SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="1665b-152">The scripts are identical, except that Day2 uses the **ErrorAction** common parameter with a value of `SilentlyContinue`.</span></span>

<span data-ttu-id="1665b-153">A saída de exemplo mostra os resultados da execução de ambos os scripts quando a cultura da interface do usuário é definida como e não há `fr-BE` arquivos ou diretórios correspondentes para essa cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="1665b-153">The sample output shows the results of running both scripts when the UI culture is set to `fr-BE` and there are no matching files or directories for that UI culture.</span></span> <span data-ttu-id="1665b-154">`Day1.ps1` exibe uma mensagem de erro e uma saída em inglês.</span><span class="sxs-lookup"><span data-stu-id="1665b-154">`Day1.ps1` displays an error message and English output.</span></span> <span data-ttu-id="1665b-155">`Day2.ps1` apenas exibe a saída em inglês.</span><span class="sxs-lookup"><span data-stu-id="1665b-155">`Day2.ps1` just displays the English output.</span></span>

## <span data-ttu-id="1665b-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1665b-156">PARAMETERS</span></span>

### <span data-ttu-id="1665b-157">-BaseDirectory</span><span class="sxs-lookup"><span data-stu-id="1665b-157">-BaseDirectory</span></span>

<span data-ttu-id="1665b-158">Especifica o diretório base onde os `.psd1` arquivos estão localizados.</span><span class="sxs-lookup"><span data-stu-id="1665b-158">Specifies the base directory where the `.psd1` files are located.</span></span> <span data-ttu-id="1665b-159">O padrão é o diretório onde o script está localizado.</span><span class="sxs-lookup"><span data-stu-id="1665b-159">The default is the directory where the script is located.</span></span> <span data-ttu-id="1665b-160">`Import-LocalizedData` pesquisa o `.psd1` arquivo para o script em um subdiretório específico de idioma do diretório base.</span><span class="sxs-lookup"><span data-stu-id="1665b-160">`Import-LocalizedData` searches for the `.psd1` file for the script in a language-specific subdirectory of the base directory.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1665b-161">-BindingVariable</span><span class="sxs-lookup"><span data-stu-id="1665b-161">-BindingVariable</span></span>

<span data-ttu-id="1665b-162">Especifica a variável na qual as cadeias de caracteres de texto são importadas.</span><span class="sxs-lookup"><span data-stu-id="1665b-162">Specifies the variable into which the text strings are imported.</span></span> <span data-ttu-id="1665b-163">Insira um nome de variável sem um cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="1665b-163">Enter a variable name without a dollar sign (`$`).</span></span>

<span data-ttu-id="1665b-164">No Windows PowerShell 2.0, esse parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="1665b-164">In Windows PowerShell 2.0, this parameter is required.</span></span> <span data-ttu-id="1665b-165">No Windows PowerShell 3.0, este parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="1665b-165">In Windows PowerShell 3.0, this parameter is optional.</span></span> <span data-ttu-id="1665b-166">Se você omitir esse parâmetro, `Import-LocalizedData` o retornará uma tabela de hash das cadeias de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="1665b-166">If you omit this parameter, `Import-LocalizedData` returns a hash table of the text strings.</span></span> <span data-ttu-id="1665b-167">A tabela de hash é passada pelo pipeline ou exibida na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1665b-167">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="1665b-168">Ao usar `Import-LocalizedData` para substituir as cadeias de caracteres de texto padrão especificadas na seção de dados de um script, atribua a seção de dados a uma variável e insira o nome da variável de seção de dados no valor do parâmetro **BindingVariable** .</span><span class="sxs-lookup"><span data-stu-id="1665b-168">When using `Import-LocalizedData` to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the **BindingVariable** parameter.</span></span> <span data-ttu-id="1665b-169">Em seguida, quando `Import-LocalizedData` o salva o conteúdo importado no **BindingVariable**, os dados importados substituirão as cadeias de caracteres de texto padrão.</span><span class="sxs-lookup"><span data-stu-id="1665b-169">Then, when `Import-LocalizedData` saves the imported content in the **BindingVariable**, the imported data will replace the default text strings.</span></span> <span data-ttu-id="1665b-170">Se não especificar cadeias de caracteres de texto padrão, você pode selecionar qualquer nome de variável.</span><span class="sxs-lookup"><span data-stu-id="1665b-170">If you are not specifying default text strings, you can select any variable name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1665b-171">-Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="1665b-171">-FileName</span></span>

<span data-ttu-id="1665b-172">Especifica o nome do arquivo de dados ( `.psd1)` a ser importado.</span><span class="sxs-lookup"><span data-stu-id="1665b-172">Specifies the name of the data file (`.psd1)` to be imported.</span></span> <span data-ttu-id="1665b-173">Insira um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1665b-173">Enter a file name.</span></span> <span data-ttu-id="1665b-174">Você pode especificar um nome de arquivo que não inclua sua `.psd1` extensão de nome de arquivo, ou pode especificar o nome do arquivo, incluindo a `.psd1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1665b-174">You can specify a file name that does not include its `.psd1` file name extension, or you can specify the file name including the `.psd1` file name extension.</span></span> <span data-ttu-id="1665b-175">Os arquivos de dados devem ser salvos como Unicode ou UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1665b-175">Data files should be saved as Unicode or UTF-8.</span></span>

<span data-ttu-id="1665b-176">O parâmetro **filename** é necessário quando `Import-LocalizedData` não é usado em um script.</span><span class="sxs-lookup"><span data-stu-id="1665b-176">The **FileName** parameter is required when `Import-LocalizedData` is not used in a script.</span></span>
<span data-ttu-id="1665b-177">Caso contrário, o parâmetro é opcional e o valor padrão é o nome base do script.</span><span class="sxs-lookup"><span data-stu-id="1665b-177">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span> <span data-ttu-id="1665b-178">Você pode usar esse parâmetro para direcionar `Import-LocalizedData` a pesquisa de um `.psd1` arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="1665b-178">You can use this parameter to direct `Import-LocalizedData` to search for a different `.psd1` file.</span></span>

<span data-ttu-id="1665b-179">Por exemplo, se o nome do **arquivo** for omitido e o nome do script for FindFiles.ps1, `Import-LocalizedData` o procurará o arquivo de dados do FindFiles.psd1.</span><span class="sxs-lookup"><span data-stu-id="1665b-179">For example, if the **FileName** is omitted and the script name is FindFiles.ps1, `Import-LocalizedData` searches for the FindFiles.psd1 data file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1665b-180">-SupportedCommand</span><span class="sxs-lookup"><span data-stu-id="1665b-180">-SupportedCommand</span></span>

<span data-ttu-id="1665b-181">Especifica os cmdlets e funções que geram somente dados.</span><span class="sxs-lookup"><span data-stu-id="1665b-181">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="1665b-182">Use esse parâmetro para incluir cmdlets e funções que você tenha escrito ou testado.</span><span class="sxs-lookup"><span data-stu-id="1665b-182">Use this parameter to include cmdlets and functions that you have written or tested.</span></span> <span data-ttu-id="1665b-183">Para obter mais informações, consulte [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="1665b-183">For more information, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1665b-184">-UICulture</span><span class="sxs-lookup"><span data-stu-id="1665b-184">-UICulture</span></span>

<span data-ttu-id="1665b-185">Especifica uma cultura de interface de usuário alternativa.</span><span class="sxs-lookup"><span data-stu-id="1665b-185">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="1665b-186">O padrão é o valor da `$PsUICulture` variável automática.</span><span class="sxs-lookup"><span data-stu-id="1665b-186">The default is the value of the `$PsUICulture` automatic variable.</span></span>
<span data-ttu-id="1665b-187">Insira uma cultura de interface do usuário no `<language>-<region>` formato, como `en-US` , `de-DE` ou `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="1665b-187">Enter a UI culture in `<language>-<region>` format, such as `en-US`, `de-DE`, or `ar-SA`.</span></span>

<span data-ttu-id="1665b-188">O valor do parâmetro **UICulture** determina o subdiretório específico do idioma (dentro do diretório base) a partir do qual `Import-LocalizedData` Obtém o `.psd1` arquivo para o script.</span><span class="sxs-lookup"><span data-stu-id="1665b-188">The value of the **UICulture** parameter determines the language-specific subdirectory (within the base directory) from which `Import-LocalizedData` gets the `.psd1` file for the script.</span></span>

<span data-ttu-id="1665b-189">O cmdlet pesquisa um subdiretório com o mesmo nome que o valor do parâmetro **UICulture** ou a `$PsUICulture` variável automática, como `de-DE` ou `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="1665b-189">The cmdlet searches for a subdirectory with the same name as the value of the **UICulture** parameter or the `$PsUICulture` automatic variable, such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="1665b-190">Se não for possível localizar o diretório, ou se o diretório não contiver um `.psd1` arquivo para o script, ele pesquisará um subdiretório com o nome do código de idioma, como de ou ar.</span><span class="sxs-lookup"><span data-stu-id="1665b-190">If it cannot find the directory, or the directory does not contain a `.psd1` file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="1665b-191">Se não for possível localizar o subdiretório ou `.psd1` arquivo, o comando falhará e os dados serão exibidos no idioma padrão especificado no script.</span><span class="sxs-lookup"><span data-stu-id="1665b-191">If it cannot find the subdirectory or `.psd1` file, the command fails and the data is displayed in the default language specified in the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1665b-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1665b-192">CommonParameters</span></span>

<span data-ttu-id="1665b-193">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1665b-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1665b-194">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1665b-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1665b-195">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1665b-195">INPUTS</span></span>

### <span data-ttu-id="1665b-196">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1665b-196">None</span></span>

<span data-ttu-id="1665b-197">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1665b-197">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1665b-198">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1665b-198">OUTPUTS</span></span>

### <span data-ttu-id="1665b-199">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="1665b-199">System.Collections.Hashtable</span></span>

<span data-ttu-id="1665b-200">`Import-LocalizedData` salva a tabela de hash na variável que é especificada pelo valor do parâmetro **BindingVariable** .</span><span class="sxs-lookup"><span data-stu-id="1665b-200">`Import-LocalizedData` saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="1665b-201">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1665b-201">NOTES</span></span>

- <span data-ttu-id="1665b-202">Antes `Import-LocalizedData` de usar o, localize suas mensagens de usuário.</span><span class="sxs-lookup"><span data-stu-id="1665b-202">Before using `Import-LocalizedData`, localize your user messages.</span></span> <span data-ttu-id="1665b-203">Formate as mensagens para cada localidade (cultura da interface do usuário) em uma tabela de hash de pares chave-valor e salve a tabela de hash em um arquivo com o mesmo nome que o script e uma `.psd1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1665b-203">Format the messages for each locale (UI culture) in a hash table of key-value pairs, and save the hash table in a file with the same name as the script and a `.psd1` file name extension.</span></span> <span data-ttu-id="1665b-204">Crie um diretório no diretório de script para cada cultura de interface do usuário com suporte e salve o `.psd1` arquivo para cada cultura da interface do usuário no diretório com o nome de cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="1665b-204">Create a directory under the script directory for each supported UI culture, and then save the `.psd1` file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="1665b-205">Por exemplo, localize suas mensagens de usuário para a localidade de-DE e as formate em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="1665b-205">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
  <span data-ttu-id="1665b-206">Salve a tabela de hash em um `<ScriptName>.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="1665b-206">Save the hash table in a `<ScriptName>.psd1` file.</span></span> <span data-ttu-id="1665b-207">Em seguida, crie um `de-DE` subdiretório no diretório de script e salve o `<ScriptName\>.psd1` arquivo alemão no `de-DE` subdiretório.</span><span class="sxs-lookup"><span data-stu-id="1665b-207">Then create a `de-DE` subdirectory under the script directory, and save the German `<ScriptName\>.psd1` file in the `de-DE` subdirectory.</span></span>
  <span data-ttu-id="1665b-208">Repita esse método para cada localidade que você suporta.</span><span class="sxs-lookup"><span data-stu-id="1665b-208">Repeat this method for each locale that you support.</span></span>

- <span data-ttu-id="1665b-209">`Import-LocalizedData` executa uma pesquisa estruturada para as mensagens de usuário localizadas de um script.</span><span class="sxs-lookup"><span data-stu-id="1665b-209">`Import-LocalizedData` performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="1665b-210">`Import-LocalizedData` inicia a pesquisa no diretório onde o arquivo de script está localizado (ou o valor do parâmetro **BaseDirectory** ).</span><span class="sxs-lookup"><span data-stu-id="1665b-210">`Import-LocalizedData` begins the search in the directory where the script file is located (or the value of the **BaseDirectory** parameter).</span></span> <span data-ttu-id="1665b-211">Em seguida, ele pesquisa no diretório base um subdiretório com o mesmo nome que o valor da `$PsUICulture` variável (ou o valor do parâmetro **UICulture** ), como `de-DE` ou `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="1665b-211">It then searches within the base directory for a subdirectory with the same name as the value of the `$PsUICulture` variable (or the value of the **UICulture** parameter), such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="1665b-212">Em seguida, ele pesquisa o subdiretório em busca de um `.psd1` arquivo com o mesmo nome do script (ou o valor do parâmetro **filename** ).</span><span class="sxs-lookup"><span data-stu-id="1665b-212">Then, it searches in that subdirectory for a `.psd1` file with the same name as the script (or the value of the **FileName** parameter).</span></span>

  <span data-ttu-id="1665b-213">Se `Import-LocalizedData` o não conseguir encontrar um subdiretório com o nome da cultura da interface do usuário ou o subdiretório não contiver um `.psd1` arquivo para o script, ele pesquisará um `.psd1` arquivo para o script em um subdiretório com o nome do código de idioma, como de ou ar.</span><span class="sxs-lookup"><span data-stu-id="1665b-213">If `Import-LocalizedData` cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a `.psd1` file for the script, it searches for a `.psd1` file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="1665b-214">Se não for possível localizar o subdiretório ou `.psd1` arquivo, o comando falhará, os dados serão exibidos no idioma padrão no script e uma mensagem de erro será exibida explicando que os dados não puderam ser importados.</span><span class="sxs-lookup"><span data-stu-id="1665b-214">If it cannot find the subdirectory or `.psd1` file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span> <span data-ttu-id="1665b-215">Para suprimir a mensagem e reprovar normalmente, use o parâmetro **ErrorAction** comum com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="1665b-215">To suppress the message and fail gracefully, use the **ErrorAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="1665b-216">Se `Import-LocalizedData` o encontrar o subdiretório e o `.psd1` arquivo, ele importará a tabela de hash de mensagens de usuário para o valor do parâmetro **BindingVariable** no comando.</span><span class="sxs-lookup"><span data-stu-id="1665b-216">If `Import-LocalizedData` finds the subdirectory and the `.psd1` file, it imports the hash table of user messages into the value of the **BindingVariable** parameter in the command.</span></span> <span data-ttu-id="1665b-217">Em seguida, quando você exibe uma mensagem da tabela de hash na variável, a mensagem localizada é exibida.</span><span class="sxs-lookup"><span data-stu-id="1665b-217">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="1665b-218">Para obter mais informações, consulte [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="1665b-218">For more information, see [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="1665b-219">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1665b-219">RELATED LINKS</span></span>

[<span data-ttu-id="1665b-220">Write-Host</span><span class="sxs-lookup"><span data-stu-id="1665b-220">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="1665b-221">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="1665b-221">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)

