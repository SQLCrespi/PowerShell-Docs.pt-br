---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: d19279133a42e3aea17f02348e44aec161ba5a23
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239987"
---
# Import-LocalizedData

## SINOPSE
Importa dados específicos de idioma para scripts e funções com base na cultura de interface de usuário selecionada para o sistema operacional.

## SYNTAX

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Import-LocalizedData` cmdlet recupera dinamicamente as cadeias de caracteres de um subdiretório cujo nome corresponde ao idioma da interface de usuário definido para o usuário atual do sistema operacional. Ele foi projetado para permitir que scripts exibam mensagens de usuário no idioma da interface do usuário selecionada pelo usuário atual.

`Import-LocalizedData` importa dados de `.psd1` arquivos em subdiretórios específicos do idioma do diretório de script e os salva em uma variável local especificada no comando. O cmdlet seleciona o subdiretório e o arquivo com base no valor da `$PSUICulture` variável automática. Quando você usa a variável local no script para exibir uma mensagem do usuário, a mensagem é exibida no idioma da interface do usuário.

Você pode usar os parâmetros de `Import-LocalizedData` para especificar uma cultura de interface de usuário alternativa, um caminho e um nome de arquivo, para adicionar comandos com suporte e para suprimir a mensagem de erro que aparece se os `.psd1` arquivos não forem encontrados.

O `Import-LocalizedData` cmdlet dá suporte à iniciativa de internacionalização de script que foi introduzida no Windows PowerShell 2,0. Essa iniciativa visa atender melhor os usuários do mundo todo, tornando mais fácil para scripts exibir mensagens de usuário no idioma da interface do usuário atual. Para obter mais informações sobre isso e sobre o formato dos `.psd1` arquivos, consulte [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

## EXEMPLOS

### Exemplo 1: importar cadeias de texto

Este exemplo importa cadeias de texto para a `$Messages` variável. Ele usa os valores padrão de todos os outros parâmetros de cmdlet.

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

Se o comando estiver incluído no script de Archives.ps1 no `C:\Test` diretório, e o valor da `$PsUICulture` variável automática for zh-CN, `Import-LocalizedData` o importará o `Archives.psd1` arquivo no `C:\test\zh-CN` diretório para a `$Messages` variável.

### Exemplo 2: importar cadeias de dados localizadas

Este exemplo é executado na linha de comando que não está em um script. Ele obtém cadeias de caracteres de dados localizados do arquivo Test.psd1 e os exibe na linha de comando. Como o comando não é usado em um script, o parâmetro **FileName** é necessário. O comando usa o parâmetro **UICulture** para especificar a cultura en-US.

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

`Import-LocalizedData` Retorna uma tabela de hash que contém as cadeias de caracteres de dados localizadas.

### Exemplo 3: importar cadeias de caracteres de cultura da interface do usuário

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

Esse comando importa cadeias de texto para a `$MsgTbl` variável de um script.

Ele usa o parâmetro **UICulture** para direcionar o cmdlet para importar dados do `Simple.psd1` arquivo no `ar-SA` subdiretório de `C:\Data\Localized` .

### Exemplo 4: importar dados localizados em um script

Este exemplo mostra como usar dados localizados em um script simples.

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

A primeira parte do exemplo mostra o conteúdo do `Test.psd1` arquivo. Ele contém um `ConvertFrom-StringData` comando que converte uma série de cadeias de caracteres de texto nomeadas em uma tabela de hash. O `Test.psd1` arquivo está localizado no subdiretório en-US do `C:\Test` diretório que contém o script.

A segunda parte do exemplo mostra o conteúdo do `Test.ps1` script. Ele contém um `Import-LocalizedData` comando que importa os dados do arquivo correspondente `.psd1` para a `$Messages` variável e um `Write-Host` comando que grava uma das mensagens na `$Messages` variável para o programa de host.

A última parte do exemplo executa o script. A saída mostra que ele exibe a mensagem do usuário correta no idioma da interface do usuário definido para o atual usuário do sistema operacional.

### Exemplo 5: substituir cadeias de caracteres de texto padrão em um script

Este exemplo mostra como usar `Import-LocalizedData` para substituir as cadeias de caracteres de texto padrão definidas na seção de dados de um script.

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

Neste exemplo, a seção de dados do script TestScript.ps1 contém um `ConvertFrom-StringData` comando que converte o conteúdo da seção de dados em uma tabela de hash e armazena no valor da `$UserMessages` variável.

O script também inclui um `Import-LocalizedData` comando, que importa uma tabela de hash de cadeias de caracteres de texto traduzidas do arquivo TestScript.psd1 no subdiretório especificado pelo valor da `$PsUICulture` variável. Se o comando Localizar o `.psd1` arquivo, ele salvará as cadeias de caracteres traduzidas do arquivo no valor da mesma `$UserMessages` variável, substituindo a tabela de hash salva pela lógica da seção de dados.

O terceiro comando exibe a primeira mensagem na `$UserMessages` variável.

Se o `Import-LocalizedData` comando encontrar um `.psd1` arquivo para o `$PsUICulture` idioma, o valor da `$UserMessages` variável conterá as cadeias de caracteres de texto traduzidas. Se o comando falhar por algum motivo, o comando exibe as cadeias de caracteres de texto padrão definidas na seção DATA do script.

### Exemplo 6: suprimir mensagens de erro se a cultura da interface do usuário não for encontrada

Este exemplo mostra como suprimir as mensagens de erro que aparecem quando `Import-LocalizedData` o não consegue encontrar os diretórios que correspondem à cultura da interface do usuário ou não pode encontrar um `.psd1` arquivo para o script nesses diretórios.

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

Você pode usar o parâmetro comum **ErrorAction** com um valor de SilentlyContinue para suprimir a mensagem de erro. Isso é especialmente útil quando você forneceu mensagens de usuário em um idioma padrão ou de fallback, e nenhuma mensagem de erro é necessária.

Este exemplo compara dois scripts `Day1.ps1` e Day2.ps1, que incluem um `Import-LocalizedData` comando. Os scripts são idênticos, exceto pelo fato de que Day2 usa o parâmetro comum **ErrorAction** com um valor de `SilentlyContinue` .

A saída de exemplo mostra os resultados da execução de ambos os scripts quando a cultura da interface do usuário é definida como e não há `fr-BE` arquivos ou diretórios correspondentes para essa cultura de interface do usuário. `Day1.ps1` exibe uma mensagem de erro e uma saída em inglês. `Day2.ps1` apenas exibe a saída em inglês.

## PARAMETERS

### -BaseDirectory

Especifica o diretório base onde os `.psd1` arquivos estão localizados. O padrão é o diretório onde o script está localizado. `Import-LocalizedData` pesquisa o `.psd1` arquivo para o script em um subdiretório específico de idioma do diretório base.

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

### -BindingVariable

Especifica a variável na qual as cadeias de caracteres de texto são importadas. Insira um nome de variável sem um cifrão ( `$` ).

No Windows PowerShell 2.0, esse parâmetro é necessário. No Windows PowerShell 3.0, este parâmetro é opcional. Se você omitir esse parâmetro, `Import-LocalizedData` o retornará uma tabela de hash das cadeias de caracteres de texto. A tabela de hash é passada pelo pipeline ou exibida na linha de comando.

Ao usar `Import-LocalizedData` para substituir as cadeias de caracteres de texto padrão especificadas na seção de dados de um script, atribua a seção de dados a uma variável e insira o nome da variável de seção de dados no valor do parâmetro **BindingVariable** . Em seguida, quando `Import-LocalizedData` o salva o conteúdo importado no **BindingVariable** , os dados importados substituirão as cadeias de caracteres de texto padrão. Se não especificar cadeias de caracteres de texto padrão, você pode selecionar qualquer nome de variável.

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

### -Nome do arquivo

Especifica o nome do arquivo de dados ( `.psd1)` a ser importado. Insira um nome de arquivo. Você pode especificar um nome de arquivo que não inclua sua `.psd1` extensão de nome de arquivo, ou pode especificar o nome do arquivo, incluindo a `.psd1` extensão de nome de arquivo. Os arquivos de dados devem ser salvos como Unicode ou UTF-8.

O parâmetro **filename** é necessário quando `Import-LocalizedData` não é usado em um script.
Caso contrário, o parâmetro é opcional e o valor padrão é o nome base do script. Você pode usar esse parâmetro para direcionar `Import-LocalizedData` a pesquisa de um `.psd1` arquivo diferente.

Por exemplo, se o nome do **arquivo** for omitido e o nome do script for FindFiles.ps1, `Import-LocalizedData` o procurará o arquivo de dados do FindFiles.psd1.

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

### -SupportedCommand

Especifica os cmdlets e funções que geram somente dados.

Use esse parâmetro para incluir cmdlets e funções que você tenha escrito ou testado. Para obter mais informações, consulte [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

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

### -UICulture

Especifica uma cultura de interface de usuário alternativa.
O padrão é o valor da `$PsUICulture` variável automática.
Insira uma cultura de interface do usuário no `<language>-<region>` formato, como `en-US` , `de-DE` ou `ar-SA` .

O valor do parâmetro **UICulture** determina o subdiretório específico do idioma (dentro do diretório base) a partir do qual `Import-LocalizedData` Obtém o `.psd1` arquivo para o script.

O cmdlet pesquisa um subdiretório com o mesmo nome que o valor do parâmetro **UICulture** ou a `$PsUICulture` variável automática, como `de-DE` ou `ar-SA` . Se não for possível localizar o diretório, ou se o diretório não contiver um `.psd1` arquivo para o script, ele pesquisará um subdiretório com o nome do código de idioma, como de ou ar. Se não for possível localizar o subdiretório ou `.psd1` arquivo, o comando falhará e os dados serão exibidos no idioma padrão especificado no script.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System.Collections.Hashtable

`Import-LocalizedData` salva a tabela de hash na variável que é especificada pelo valor do parâmetro **BindingVariable** .

## OBSERVAÇÕES

- Antes `Import-LocalizedData` de usar o, localize suas mensagens de usuário. Formate as mensagens para cada localidade (cultura da interface do usuário) em uma tabela de hash de pares chave-valor e salve a tabela de hash em um arquivo com o mesmo nome que o script e uma `.psd1` extensão de nome de arquivo. Crie um diretório no diretório de script para cada cultura de interface do usuário com suporte e salve o `.psd1` arquivo para cada cultura da interface do usuário no diretório com o nome de cultura da interface do usuário.

  Por exemplo, localize suas mensagens de usuário para a localidade de-DE e as formate em uma tabela de hash.
  Salve a tabela de hash em um `<ScriptName>.psd1` arquivo. Em seguida, crie um `de-DE` subdiretório no diretório de script e salve o `<ScriptName\>.psd1` arquivo alemão no `de-DE` subdiretório.
  Repita esse método para cada localidade que você suporta.

- `Import-LocalizedData` executa uma pesquisa estruturada para as mensagens de usuário localizadas de um script.

  `Import-LocalizedData` inicia a pesquisa no diretório onde o arquivo de script está localizado (ou o valor do parâmetro **BaseDirectory** ). Em seguida, ele pesquisa no diretório base um subdiretório com o mesmo nome que o valor da `$PsUICulture` variável (ou o valor do parâmetro **UICulture** ), como `de-DE` ou `ar-SA` . Em seguida, ele pesquisa o subdiretório em busca de um `.psd1` arquivo com o mesmo nome do script (ou o valor do parâmetro **filename** ).

  Se `Import-LocalizedData` o não conseguir encontrar um subdiretório com o nome da cultura da interface do usuário ou o subdiretório não contiver um `.psd1` arquivo para o script, ele pesquisará um `.psd1` arquivo para o script em um subdiretório com o nome do código de idioma, como de ou ar. Se não for possível localizar o subdiretório ou `.psd1` arquivo, o comando falhará, os dados serão exibidos no idioma padrão no script e uma mensagem de erro será exibida explicando que os dados não puderam ser importados. Para suprimir a mensagem e reprovar normalmente, use o parâmetro **ErrorAction** comum com um valor de SilentlyContinue.

  Se `Import-LocalizedData` o encontrar o subdiretório e o `.psd1` arquivo, ele importará a tabela de hash de mensagens de usuário para o valor do parâmetro **BindingVariable** no comando. Em seguida, quando você exibe uma mensagem da tabela de hash na variável, a mensagem localizada é exibida.

  Para obter mais informações, consulte [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).

## LINKS RELACIONADOS

[Write-Host](Write-Host.md)

[Import-PowerShellDataFile](Import-PowerShellDataFile.md)

