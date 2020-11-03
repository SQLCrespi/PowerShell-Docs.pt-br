---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: a69faa564b8d411bd6f36091f00240784a7a2f7f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193784"
---
# <span data-ttu-id="68490-103">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="68490-103">Import-LocalizedData</span></span>

## <span data-ttu-id="68490-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="68490-104">SYNOPSIS</span></span>
<span data-ttu-id="68490-105">Importa dados específicos de idioma para scripts e funções com base na cultura de interface de usuário selecionada para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="68490-105">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="68490-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68490-106">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="68490-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68490-107">DESCRIPTION</span></span>
<span data-ttu-id="68490-108">O cmdlet **Import-LocalizedData** recupera cadeias de caracteres dinamicamente de um subdiretório, cujo nome corresponde ao idioma da interface do usuário definido para o usuário atual do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="68490-108">The **Import-LocalizedData** cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span>
<span data-ttu-id="68490-109">Ele foi projetado para permitir que scripts exibam mensagens de usuário no idioma da interface do usuário selecionada pelo usuário atual.</span><span class="sxs-lookup"><span data-stu-id="68490-109">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="68490-110">O **Import-LocalizedData** importa dados de arquivos. psd1 em subdiretórios específicos do idioma do diretório de script e os salva em uma variável local especificada no comando.</span><span class="sxs-lookup"><span data-stu-id="68490-110">**Import-LocalizedData** imports data from .psd1 files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span>
<span data-ttu-id="68490-111">O cmdlet seleciona o subdiretório e o arquivo com base no valor da variável automática $PSUICulture.</span><span class="sxs-lookup"><span data-stu-id="68490-111">The cmdlet selects the subdirectory and file based on the value of the $PSUICulture automatic variable.</span></span>
<span data-ttu-id="68490-112">Quando você usa a variável local no script para exibir uma mensagem do usuário, a mensagem é exibida no idioma da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="68490-112">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="68490-113">Você pode usar os parâmetros de **Import-LocalizedData** para especificar uma cultura de interface de usuário, caminho e nome de arquivo alternativos, para adicionar comandos suportados e para suprimir a mensagem de erro que aparece se os arquivos .psd1 não são encontrados.</span><span class="sxs-lookup"><span data-stu-id="68490-113">You can use the parameters of **Import-LocalizedData** to specify an alternate UI culture, path, and file name, to add supported commands, and to suppress the error message that appears if the .psd1 files are not found.</span></span>

<span data-ttu-id="68490-114">O cmdlet **Import-LocalizedData** oferece suporte à iniciativa de internacionalização de script introduzida no Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="68490-114">The **Import-LocalizedData** cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span>
<span data-ttu-id="68490-115">Essa iniciativa visa atender melhor os usuários do mundo todo, tornando mais fácil para scripts exibir mensagens de usuário no idioma da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="68490-115">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span>
<span data-ttu-id="68490-116">Para obter mais informações sobre isso e sobre o formato dos arquivos. psd1, consulte about_Script_Internationalization.</span><span class="sxs-lookup"><span data-stu-id="68490-116">For more information about this and about the format of the .psd1 files, see about_Script_Internationalization.</span></span>

## <span data-ttu-id="68490-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="68490-117">EXAMPLES</span></span>

### <span data-ttu-id="68490-118">Exemplo 1: importar cadeias de texto</span><span class="sxs-lookup"><span data-stu-id="68490-118">Example 1: Import text strings</span></span>

```
PS C:\> Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="68490-119">Este comando importa cadeias de caracteres de texto na variável $Messages.</span><span class="sxs-lookup"><span data-stu-id="68490-119">This command imports text strings into the $Messages variable.</span></span>
<span data-ttu-id="68490-120">Ele usa os valores padrão de todos os outros parâmetros de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="68490-120">It uses the default values of all other cmdlet parameters.</span></span>

<span data-ttu-id="68490-121">Se o comando está incluído no script Archives.ps1 no diretório C:\Test e o valor da variável automática $PsUICulture for zh-CN, o **Import-LocalizedData** importa o arquivo Archives.psd1 no diretório C:\test\zh-CN na variável $Messages.</span><span class="sxs-lookup"><span data-stu-id="68490-121">If the command is included in the Archives.ps1 script in the C:\Test directory, and the value of the $PsUICulture automatic variable is zh-CN, **Import-LocalizedData** imports the Archives.psd1 file in the C:\test\zh-CN directory into the $Messages variable.</span></span>

### <span data-ttu-id="68490-122">Exemplo 2: importar cadeias de dados localizadas</span><span class="sxs-lookup"><span data-stu-id="68490-122">Example 2: Import localized data strings</span></span>

```
PS C:\> Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"

Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="68490-123">Esse comando é executado na linha de comando; não em um script.</span><span class="sxs-lookup"><span data-stu-id="68490-123">This command is run at the command line; not in a script.</span></span>
<span data-ttu-id="68490-124">Ele obtém cadeias de caracteres de dados localizados do arquivo Test.psd1 e os exibe na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="68490-124">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span>
<span data-ttu-id="68490-125">Como o comando não é usado em um script, o parâmetro *FileName* é necessário.</span><span class="sxs-lookup"><span data-stu-id="68490-125">Because the command is not used in a script, the *FileName* parameter is required.</span></span>
<span data-ttu-id="68490-126">O comando usa o parâmetro *UICulture* para especificar a cultura en-US.</span><span class="sxs-lookup"><span data-stu-id="68490-126">The command uses the *UICulture* parameter to specify the en-US culture.</span></span>

<span data-ttu-id="68490-127">**Import-LocalizedData** retorna uma tabela de hash que contém as cadeias de caracteres de dados localizadas.</span><span class="sxs-lookup"><span data-stu-id="68490-127">**Import-LocalizedData** returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="68490-128">Exemplo 3: importar cadeias de caracteres de cultura da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="68490-128">Example 3: Import UI culture strings</span></span>

```
PS C:\> Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="68490-129">Esse comando importa cadeias de caracteres de texto para a variável $MsgTbl de um script.</span><span class="sxs-lookup"><span data-stu-id="68490-129">This command imports text strings into the $MsgTbl variable of a script.</span></span>

<span data-ttu-id="68490-130">Ele usa o parâmetro *UICulture* para direcionar o cmdlet para importar dados do arquivo Simple.psd1 no subdiretório ar-SA em C:\Data\Localized.</span><span class="sxs-lookup"><span data-stu-id="68490-130">It uses the *UICulture* parameter to direct the cmdlet to import data from the Simple.psd1 file in the ar-SA subdirectory of C:\Data\Localized.</span></span>

### <span data-ttu-id="68490-131">Exemplo 4: importar dados localizados em um script</span><span class="sxs-lookup"><span data-stu-id="68490-131">Example 4: Import localized data into a script</span></span>

```
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

<span data-ttu-id="68490-132">Este exemplo mostra como usar dados localizados em um script simples.</span><span class="sxs-lookup"><span data-stu-id="68490-132">This example shows how to use localized data in a simple script.</span></span>

<span data-ttu-id="68490-133">A primeira parte do exemplo mostra o conteúdo do arquivo Test.psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-133">The first part of the example shows the contents of the Test.psd1 file.</span></span>
<span data-ttu-id="68490-134">Ele contém um comando ConvertFrom-StringData que converte uma série de cadeias de caracteres de texto nomeadas em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="68490-134">It contains a ConvertFrom-StringData command that converts a series of named text strings into a hash table.</span></span>
<span data-ttu-id="68490-135">O arquivo Test.psd1 está localizado no subdiretório en-US do diretório C:\Test que contém o script.</span><span class="sxs-lookup"><span data-stu-id="68490-135">The Test.psd1 file is located in the en-US subdirectory of the C:\Test directory that contains the script.</span></span>

<span data-ttu-id="68490-136">A segunda parte do exemplo mostra o conteúdo do script Test.ps1.</span><span class="sxs-lookup"><span data-stu-id="68490-136">The second part of the example shows the contents of the Test.ps1 script.</span></span>
<span data-ttu-id="68490-137">Ele contém um comando **Import-LocalizedData** que importa os dados do arquivo. psd1 correspondente para a variável $messages e um comando Write-Host que grava uma das mensagens na variável $messages para o programa host.</span><span class="sxs-lookup"><span data-stu-id="68490-137">It contains an **Import-LocalizedData** command that imports the data from the matching .psd1 file into the $Messages variable and a Write-Host command that writes one of the messages in the $Messages variable to the host program.</span></span>

<span data-ttu-id="68490-138">A última parte do exemplo executa o script.</span><span class="sxs-lookup"><span data-stu-id="68490-138">The last part of the example runs the script.</span></span>
<span data-ttu-id="68490-139">A saída mostra que ele exibe a mensagem do usuário correta no idioma da interface do usuário definido para o atual usuário do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="68490-139">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="68490-140">Exemplo 5: substituir cadeias de caracteres de texto padrão em um script</span><span class="sxs-lookup"><span data-stu-id="68490-140">Example 5: Replace default text strings in a script</span></span>

```
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@ }
Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="68490-141">Este exemplo mostra como usar **Import-LocalizedData** para substituir cadeias de caracteres de texto padrão definidas na seção DATA de um script.</span><span class="sxs-lookup"><span data-stu-id="68490-141">This example shows how to use **Import-LocalizedData** to replace default text strings defined in the DATA section of a script.</span></span>

<span data-ttu-id="68490-142">Neste exemplo, a seção de dados do script TestScript.ps1 contém um comando ConvertFrom-StringData que converte o conteúdo da seção de dados em uma tabela de hash e armazena no valor da variável $UserMessages.</span><span class="sxs-lookup"><span data-stu-id="68490-142">In this example, the DATA section of the TestScript.ps1 script contains a ConvertFrom-StringData command that converts the contents of the DATA section to a hash table and stores in the value of the $UserMessages variable.</span></span>

<span data-ttu-id="68490-143">O script também inclui um comando **Import-LocalizedData** que importa uma tabela de hash de cadeias de caracteres de texto traduzido do arquivo TestScript.psd1 no subdiretório especificado pelo valor da variável $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="68490-143">The script also includes an **Import-LocalizedData** command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the $PsUICulture variable.</span></span>
<span data-ttu-id="68490-144">Se o comando localizar o arquivo .psd1, ele salva as cadeias de caracteres traduzidas do arquivo no valor da mesma variável $UserMessages, substituindo a tabela de hash salva pela lógica da seção DATA.</span><span class="sxs-lookup"><span data-stu-id="68490-144">If the command finds the .psd1 file, it saves the translated strings from the file in the value of the same $UserMessages variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="68490-145">O terceiro comando exibe a primeira mensagem na variável $UserMessages.</span><span class="sxs-lookup"><span data-stu-id="68490-145">The third command displays the first message in the $UserMessages variable.</span></span>

<span data-ttu-id="68490-146">Se o comando **Import-LocalizedData** localiza um arquivo .psd1 para o idioma $PsUICulture, o valor da variável $UserMessages contém as cadeias de caracteres do texto traduzidas.</span><span class="sxs-lookup"><span data-stu-id="68490-146">If the **Import-LocalizedData** command finds a .psd1 file for the $PsUICulture language, the value of the $UserMessages variable contains the translated text strings.</span></span>
<span data-ttu-id="68490-147">Se o comando falhar por algum motivo, o comando exibe as cadeias de caracteres de texto padrão definidas na seção DATA do script.</span><span class="sxs-lookup"><span data-stu-id="68490-147">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="68490-148">Exemplo 6: suprimir mensagens de erro se a cultura da interface do usuário não for encontrada</span><span class="sxs-lookup"><span data-stu-id="68490-148">Example 6: Suppress error messages if the UI culture is not found</span></span>

```
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="68490-149">Este exemplo mostra como suprimir as mensagens de erro que aparecem quando o **Import-LocalizedData** não localiza os diretórios que correspondem à cultura de interface do usuário e nem um arquivo .psd1 para o script nesses diretórios.</span><span class="sxs-lookup"><span data-stu-id="68490-149">This example shows how to suppress the error messages that appear when **Import-LocalizedData** cannot find the directories that match the user's UI culture or cannot find a .psd1 file for the script in those directories.</span></span>

<span data-ttu-id="68490-150">Você pode usar o parâmetro comum *ErrorAction* com um valor de SilentlyContinue para suprimir a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="68490-150">You can use the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the error message.</span></span>
<span data-ttu-id="68490-151">Isso é especialmente útil quando você forneceu mensagens de usuário em um idioma padrão ou de fallback, e nenhuma mensagem de erro é necessária.</span><span class="sxs-lookup"><span data-stu-id="68490-151">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="68490-152">Este exemplo compara dois scripts, Day1.ps1 e Day2.ps1, que incluem um comando **Import-LocalizedData** .</span><span class="sxs-lookup"><span data-stu-id="68490-152">This example compares two scripts, Day1.ps1 and Day2.ps1, that include an **Import-LocalizedData** command.</span></span>
<span data-ttu-id="68490-153">Os scripts são idênticos, exceto pelo fato de que Day2 usa o parâmetro comum *ErrorAction* com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="68490-153">The scripts are identical, except that Day2 uses the *ErrorAction* common parameter with a value of SilentlyContinue.</span></span>

<span data-ttu-id="68490-154">O exemplo de saída mostra os resultados da execução de ambos os scripts quando a cultura de interface de usuário está definida para fr-BE e não há arquivos ou pastas para aquela cultura de interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="68490-154">The sample output shows the results of running both scripts when the UI culture is set to fr-BE and there are no matching files or directories for that UI culture.</span></span>
<span data-ttu-id="68490-155">Day1.ps1 exibe uma mensagem de erro e uma saída em inglês.</span><span class="sxs-lookup"><span data-stu-id="68490-155">Day1.ps1 displays an error message and English output.</span></span>
<span data-ttu-id="68490-156">Day2.ps1 apenas exibe a saída em inglês.</span><span class="sxs-lookup"><span data-stu-id="68490-156">Day2.ps1 just displays the English output.</span></span>

## <span data-ttu-id="68490-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68490-157">PARAMETERS</span></span>

### <span data-ttu-id="68490-158">-BaseDirectory</span><span class="sxs-lookup"><span data-stu-id="68490-158">-BaseDirectory</span></span>
<span data-ttu-id="68490-159">Especifica o diretório base onde se encontram os arquivos .psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-159">Specifies the base directory where the .psd1 files are located.</span></span>
<span data-ttu-id="68490-160">O padrão é o diretório onde o script está localizado.</span><span class="sxs-lookup"><span data-stu-id="68490-160">The default is the directory where the script is located.</span></span>
<span data-ttu-id="68490-161">O **Import-LocalizedData** procura pelo arquivo .psd1 para o script em um subdiretório específico do idioma do diretório base.</span><span class="sxs-lookup"><span data-stu-id="68490-161">**Import-LocalizedData** searches for the .psd1 file for the script in a language-specific subdirectory of the base directory.</span></span>

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

### <span data-ttu-id="68490-162">-BindingVariable</span><span class="sxs-lookup"><span data-stu-id="68490-162">-BindingVariable</span></span>
<span data-ttu-id="68490-163">Especifica a variável na qual as cadeias de caracteres de texto são importadas.</span><span class="sxs-lookup"><span data-stu-id="68490-163">Specifies the variable into which the text strings are imported.</span></span>
<span data-ttu-id="68490-164">Insira um nome de variável sem um sinal de dólar ($).</span><span class="sxs-lookup"><span data-stu-id="68490-164">Enter a variable name without a dollar sign ($).</span></span>

<span data-ttu-id="68490-165">No Windows PowerShell 2.0, esse parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="68490-165">In Windows PowerShell 2.0, this parameter is required.</span></span>
<span data-ttu-id="68490-166">No Windows PowerShell 3.0, este parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="68490-166">In Windows PowerShell 3.0, this parameter is optional.</span></span>
<span data-ttu-id="68490-167">Se você omitir esse parâmetro, o **Import-LocalizedData** retorna uma tabela de hash das cadeias de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="68490-167">If you omit this parameter, **Import-LocalizedData** returns a hash table of the text strings.</span></span>
<span data-ttu-id="68490-168">A tabela de hash é passada pelo pipeline ou exibida na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="68490-168">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="68490-169">Ao usar o **Import-LocalizedData** para substituir cadeias de caracteres de texto padrão especificadas na seção DATA de um script, atribua a seção DATA a uma variável e insira o nome da variável da seção DATA no valor do parâmetro *BindingVariable* .</span><span class="sxs-lookup"><span data-stu-id="68490-169">When using **Import-LocalizedData** to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the *BindingVariable* parameter.</span></span>
<span data-ttu-id="68490-170">Então, quando o **Import-LocalizedData** salva o conteúdo importado no *BindingVariable* , os dados importados substituirão as cadeias de caracteres de texto padrão.</span><span class="sxs-lookup"><span data-stu-id="68490-170">Then, when **Import-LocalizedData** saves the imported content in the *BindingVariable* , the imported data will replace the default text strings.</span></span>
<span data-ttu-id="68490-171">Se não especificar cadeias de caracteres de texto padrão, você pode selecionar qualquer nome de variável.</span><span class="sxs-lookup"><span data-stu-id="68490-171">If you are not specifying default text strings, you can select any variable name.</span></span>

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

### <span data-ttu-id="68490-172">-Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="68490-172">-FileName</span></span>
<span data-ttu-id="68490-173">Especifica o nome do arquivo de dados (.psd1) a ser importado.</span><span class="sxs-lookup"><span data-stu-id="68490-173">Specifies the name of the data file (.psd1) to be imported.</span></span>
<span data-ttu-id="68490-174">Insira um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="68490-174">Enter a file name.</span></span>
<span data-ttu-id="68490-175">Você pode especificar um nome de arquivo que não inclua sua extensão de nome de arquivo .psd1 ou especificar o nome do arquivo incluindo a extensão de nome de arquivo .psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-175">You can specify a file name that does not include its .psd1 file name extension, or you can specify the file name including the .psd1 file name extension.</span></span>
<span data-ttu-id="68490-176">Os arquivos de dados devem ser salvos como Unicode ou UTF-8.</span><span class="sxs-lookup"><span data-stu-id="68490-176">Data files should be saved as Unicode or UTF-8.</span></span>

<span data-ttu-id="68490-177">O parâmetro *FileName* é obrigatório quando o **Import-LocalizedData** não é usado em um script.</span><span class="sxs-lookup"><span data-stu-id="68490-177">The *FileName* parameter is required when **Import-LocalizedData** is not used in a script.</span></span>
<span data-ttu-id="68490-178">Caso contrário, o parâmetro é opcional e o valor padrão é o nome base do script.</span><span class="sxs-lookup"><span data-stu-id="68490-178">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span>
<span data-ttu-id="68490-179">Você pode usar esse parâmetro para direcionar **Import-LocalizedData** para procurar um arquivo .psd1 diferente.</span><span class="sxs-lookup"><span data-stu-id="68490-179">You can use this parameter to direct **Import-LocalizedData** to search for a different .psd1 file.</span></span>

<span data-ttu-id="68490-180">Por exemplo, se o nome do *arquivo* for omitido e o nome do script for FindFiles.ps1, o **Import-LocalizedData** pesquisará o arquivo de dados do FindFiles.psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-180">For example, if the *FileName* is omitted and the script name is FindFiles.ps1, **Import-LocalizedData** searches for the FindFiles.psd1 data file.</span></span>

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

### <span data-ttu-id="68490-181">-SupportedCommand</span><span class="sxs-lookup"><span data-stu-id="68490-181">-SupportedCommand</span></span>
<span data-ttu-id="68490-182">Especifica os cmdlets e funções que geram somente dados.</span><span class="sxs-lookup"><span data-stu-id="68490-182">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="68490-183">Use esse parâmetro para incluir cmdlets e funções que você tenha escrito ou testado.</span><span class="sxs-lookup"><span data-stu-id="68490-183">Use this parameter to include cmdlets and functions that you have written or tested.</span></span>
<span data-ttu-id="68490-184">Para obter mais informações, consulte about_Script_Internationalization.</span><span class="sxs-lookup"><span data-stu-id="68490-184">For more information, see about_Script_Internationalization.</span></span>

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

### <span data-ttu-id="68490-185">-UICulture</span><span class="sxs-lookup"><span data-stu-id="68490-185">-UICulture</span></span>
<span data-ttu-id="68490-186">Especifica uma cultura de interface de usuário alternativa.</span><span class="sxs-lookup"><span data-stu-id="68490-186">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="68490-187">O padrão é o valor da variável automática $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="68490-187">The default is the value of the $PsUICulture automatic variable.</span></span>
<span data-ttu-id="68490-188">Insira uma cultura de interface do usuário no \<language\> - \<region\> formato, como en-US, de-de ou ar-SA.</span><span class="sxs-lookup"><span data-stu-id="68490-188">Enter a UI culture in \<language\>-\<region\> format, such as en-US, de-DE, or ar-SA.</span></span>

<span data-ttu-id="68490-189">O valor do parâmetro *UICulture* determina o subdiretório específico do idioma (dentro do diretório base) de onde o **Import-LocalizedData** obtém o arquivo .psd1 para o script.</span><span class="sxs-lookup"><span data-stu-id="68490-189">The value of the *UICulture* parameter determines the language-specific subdirectory (within the base directory) from which **Import-LocalizedData** gets the .psd1 file for the script.</span></span>

<span data-ttu-id="68490-190">O cmdlet pesquisa um subdiretório com o mesmo nome que o valor do parâmetro *UICulture* ou o $PsUICulture variável automática, como DE-de ou ar-SA.</span><span class="sxs-lookup"><span data-stu-id="68490-190">The cmdlet searches for a subdirectory with the same name as the value of the *UICulture* parameter or the $PsUICulture automatic variable, such as de-DE or ar-SA.</span></span>
<span data-ttu-id="68490-191">Se não for possível localizar o diretório ou o diretório não contiver um arquivo. psd1 para o script, ele pesquisará um subdiretório com o nome do código de idioma, como de ou ar.</span><span class="sxs-lookup"><span data-stu-id="68490-191">If it cannot find the directory, or the directory does not contain a .psd1 file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span>
<span data-ttu-id="68490-192">Se ele não encontra o subdiretório ou o arquivo .psd1, o comando falha e os dados são exibidos no idioma padrão especificado no script.</span><span class="sxs-lookup"><span data-stu-id="68490-192">If it cannot find the subdirectory or .psd1 file, the command fails and the data is displayed in the default language specified in the script.</span></span>

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

### <span data-ttu-id="68490-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="68490-193">CommonParameters</span></span>
<span data-ttu-id="68490-194">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68490-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68490-195">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68490-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68490-196">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="68490-196">INPUTS</span></span>

### <span data-ttu-id="68490-197">Nenhum</span><span class="sxs-lookup"><span data-stu-id="68490-197">None</span></span>
<span data-ttu-id="68490-198">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="68490-198">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="68490-199">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="68490-199">OUTPUTS</span></span>

### <span data-ttu-id="68490-200">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="68490-200">System.Collections.Hashtable</span></span>
<span data-ttu-id="68490-201">O **Import-LocalizedData** salva a tabela de hash na variável que é especificada pelo valor do parâmetro **BindingVariable** .</span><span class="sxs-lookup"><span data-stu-id="68490-201">**Import-LocalizedData** saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="68490-202">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="68490-202">NOTES</span></span>

* <span data-ttu-id="68490-203">Antes de usar o **Import-LocalizedData** , localize suas mensagens de usuário.</span><span class="sxs-lookup"><span data-stu-id="68490-203">Before using **Import-LocalizedData** , localize your user messages.</span></span> <span data-ttu-id="68490-204">Formate as mensagens para cada localidade (cultura de interface de usuário) em uma tabela de hash em pares chave/valor e salve a tabela de hash em um arquivo com o mesmo nome que o script e uma extensão de nome de arquivo .psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-204">Format the messages for each locale (UI culture) in a hash table of key/value pairs, and save the hash table in a file with the same name as the script and a .psd1 file name extension.</span></span> <span data-ttu-id="68490-205">Crie um diretório no diretório de scripts para cada cultura de interface de usuário com suporte e salve o arquivo .psd1 para cada cultura de interface de usuário no diretório com o nome da cultura de interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="68490-205">Create a directory under the script directory for each supported UI culture, and then save the .psd1 file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="68490-206">Por exemplo, localize suas mensagens de usuário para a localidade de-DE e as formate em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="68490-206">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
<span data-ttu-id="68490-207">Salve uma tabela de hash em um arquivo \<ScriptName\>.psd1.</span><span class="sxs-lookup"><span data-stu-id="68490-207">Save the hash table in a \<ScriptName\>.psd1 file.</span></span>
<span data-ttu-id="68490-208">Em seguida, crie um subdiretório de-DE no diretório de scripts e salve o arquivo \<ScriptName\>.psd1 no subdiretório de-DE.</span><span class="sxs-lookup"><span data-stu-id="68490-208">Then create a de-DE subdirectory under the script directory, and save the de-DE \<ScriptName\>.psd1 file in the de-DE subdirectory.</span></span>
<span data-ttu-id="68490-209">Repita esse método para cada localidade que você suporta.</span><span class="sxs-lookup"><span data-stu-id="68490-209">Repeat this method for each locale that you support.</span></span>

* <span data-ttu-id="68490-210">**Import-LocalizedData** executa uma pesquisa estruturada para as mensagens de usuário localizadas para um script.</span><span class="sxs-lookup"><span data-stu-id="68490-210">**Import-LocalizedData** performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="68490-211">**Import-LocalizedData** inicia a pesquisa no diretório onde o arquivo de script está localizado (ou o valor do parâmetro *BaseDirectory* ).</span><span class="sxs-lookup"><span data-stu-id="68490-211">**Import-LocalizedData** begins the search in the directory where the script file is located (or the value of the *BaseDirectory* parameter).</span></span>
<span data-ttu-id="68490-212">Em seguida, ele pesquisa dentro do diretório base um subdiretório com o mesmo nome que o valor da variável $PsUICulture (ou o valor do parâmetro *UICulture* ), como DE-de ou ar-SA.</span><span class="sxs-lookup"><span data-stu-id="68490-212">It then searches within the base directory for a subdirectory with the same name as the value of the $PsUICulture variable (or the value of the *UICulture* parameter), such as de-DE or ar-SA.</span></span>
<span data-ttu-id="68490-213">Em seguida, ele procura no subdiretório por um arquivo .psd1 com o mesmo nome do script (ou o valor do parâmetro *FileName* ).</span><span class="sxs-lookup"><span data-stu-id="68490-213">Then, it searches in that subdirectory for a .psd1 file with the same name as the script (or the value of the *FileName* parameter).</span></span>

  <span data-ttu-id="68490-214">Se **Import-LocalizedData** não conseguir localizar um subdiretório com o nome da cultura da interface do usuário, ou o subdiretório não contiver um arquivo. psd1 para o script, ele pesquisará um arquivo. psd1 para o script em um subdiretório com o nome do código de idioma, como de ou ar.</span><span class="sxs-lookup"><span data-stu-id="68490-214">If **Import-LocalizedData** cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a .psd1 file for the script, it searches for a .psd1 file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span>
<span data-ttu-id="68490-215">Se ele não encontra o subdiretório ou o arquivo .psd1, o comando falha, os dados são exibidos no idioma padrão no script e uma mensagem de erro, explicando que os dados não puderam ser importados, é exibida.</span><span class="sxs-lookup"><span data-stu-id="68490-215">If it cannot find the subdirectory or .psd1 file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span>
<span data-ttu-id="68490-216">Para suprimir a mensagem e reprovar normalmente, use o parâmetro *ErrorAction* comum com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="68490-216">To suppress the message and fail gracefully, use the *ErrorAction* common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="68490-217">Se o **Import-LocalizedData** localizar o subdiretório e o arquivo .psd1, ele importa a tabela de hash das mensagens de usuário para o valor do parâmetro *BindingVariable* no comando.</span><span class="sxs-lookup"><span data-stu-id="68490-217">If **Import-LocalizedData** finds the subdirectory and the .psd1 file, it imports the hash table of user messages into the value of the *BindingVariable* parameter in the command.</span></span>
<span data-ttu-id="68490-218">Em seguida, quando você exibe uma mensagem da tabela de hash na variável, a mensagem localizada é exibida.</span><span class="sxs-lookup"><span data-stu-id="68490-218">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="68490-219">Para obter mais informações, consulte about_Script_Internationalization ( https://go.microsoft.com/fwlink/?LinkID=113262) .</span><span class="sxs-lookup"><span data-stu-id="68490-219">For more information, see about_Script_Internationalization (https://go.microsoft.com/fwlink/?LinkID=113262).</span></span>

## <span data-ttu-id="68490-220">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="68490-220">RELATED LINKS</span></span>

[<span data-ttu-id="68490-221">Write-Host</span><span class="sxs-lookup"><span data-stu-id="68490-221">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="68490-222">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="68490-222">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)
