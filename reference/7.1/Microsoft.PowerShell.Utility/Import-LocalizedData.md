---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: a5b66295b29daf1a8f0354b40c51f987849e34b7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193559"
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

O cmdlet **Import-LocalizedData** recupera cadeias de caracteres dinamicamente de um subdiretório, cujo nome corresponde ao idioma da interface do usuário definido para o usuário atual do sistema operacional.
Ele foi projetado para permitir que scripts exibam mensagens de usuário no idioma da interface do usuário selecionada pelo usuário atual.

O **Import-LocalizedData** importa dados de arquivos. psd1 em subdiretórios específicos do idioma do diretório de script e os salva em uma variável local especificada no comando.
O cmdlet seleciona o subdiretório e o arquivo com base no valor da variável automática $PSUICulture.
Quando você usa a variável local no script para exibir uma mensagem do usuário, a mensagem é exibida no idioma da interface do usuário.

Você pode usar os parâmetros de **Import-LocalizedData** para especificar uma cultura de interface de usuário, caminho e nome de arquivo alternativos, para adicionar comandos suportados e para suprimir a mensagem de erro que aparece se os arquivos .psd1 não são encontrados.

O cmdlet **Import-LocalizedData** oferece suporte à iniciativa de internacionalização de script introduzida no Windows PowerShell 2.0.
Essa iniciativa visa atender melhor os usuários do mundo todo, tornando mais fácil para scripts exibir mensagens de usuário no idioma da interface do usuário atual.
Para obter mais informações sobre isso e sobre o formato dos arquivos. psd1, consulte about_Script_Internationalization.

## EXEMPLOS

### Exemplo 1: importar cadeias de texto

```
PS C:\> Import-LocalizedData -BindingVariable "Messages"
```

Este comando importa cadeias de caracteres de texto na variável $Messages.
Ele usa os valores padrão de todos os outros parâmetros de cmdlet.

Se o comando está incluído no script Archives.ps1 no diretório C:\Test e o valor da variável automática $PsUICulture for zh-CN, o **Import-LocalizedData** importa o arquivo Archives.psd1 no diretório C:\test\zh-CN na variável $Messages.

### Exemplo 2: importar cadeias de dados localizadas

```
PS C:\> Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"

Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

Esse comando é executado na linha de comando; não em um script.
Ele obtém cadeias de caracteres de dados localizados do arquivo Test.psd1 e os exibe na linha de comando.
Como o comando não é usado em um script, o parâmetro *FileName* é necessário.
O comando usa o parâmetro *UICulture* para especificar a cultura en-US.

**Import-LocalizedData** retorna uma tabela de hash que contém as cadeias de caracteres de dados localizadas.

### Exemplo 3: importar cadeias de caracteres de cultura da interface do usuário

```
PS C:\> Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

Esse comando importa cadeias de caracteres de texto para a variável $MsgTbl de um script.

Ele usa o parâmetro *UICulture* para direcionar o cmdlet para importar dados do arquivo Simple.psd1 no subdiretório ar-SA em C:\Data\Localized.

### Exemplo 4: importar dados localizados em um script

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

# In PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

Este exemplo mostra como usar dados localizados em um script simples.

A primeira parte do exemplo mostra o conteúdo do arquivo Test.psd1.
Ele contém um comando ConvertFrom-StringData que converte uma série de cadeias de caracteres de texto nomeadas em uma tabela de hash.
O arquivo Test.psd1 está localizado no subdiretório en-US do diretório C:\Test que contém o script.

A segunda parte do exemplo mostra o conteúdo do script Test.ps1.
Ele contém um comando **Import-LocalizedData** que importa os dados do arquivo. psd1 correspondente para a variável $messages e um comando Write-Host que grava uma das mensagens na variável $messages para o programa host.

A última parte do exemplo executa o script.
A saída mostra que ele exibe a mensagem do usuário correta no idioma da interface do usuário definido para o atual usuário do sistema operacional.

### Exemplo 5: substituir cadeias de caracteres de texto padrão em um script

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

Este exemplo mostra como usar **Import-LocalizedData** para substituir cadeias de caracteres de texto padrão definidas na seção DATA de um script.

Neste exemplo, a seção de dados do script TestScript.ps1 contém um comando ConvertFrom-StringData que converte o conteúdo da seção de dados em uma tabela de hash e armazena no valor da variável $UserMessages.

O script também inclui um comando **Import-LocalizedData** que importa uma tabela de hash de cadeias de caracteres de texto traduzido do arquivo TestScript.psd1 no subdiretório especificado pelo valor da variável $PsUICulture.
Se o comando localizar o arquivo .psd1, ele salva as cadeias de caracteres traduzidas do arquivo no valor da mesma variável $UserMessages, substituindo a tabela de hash salva pela lógica da seção DATA.

O terceiro comando exibe a primeira mensagem na variável $UserMessages.

Se o comando **Import-LocalizedData** localiza um arquivo .psd1 para o idioma $PsUICulture, o valor da variável $UserMessages contém as cadeias de caracteres do texto traduzidas.
Se o comando falhar por algum motivo, o comando exibe as cadeias de caracteres de texto padrão definidas na seção DATA do script.

### Exemplo 6: suprimir mensagens de erro se a cultura da interface do usuário não for encontrada

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

Este exemplo mostra como suprimir as mensagens de erro que aparecem quando o **Import-LocalizedData** não localiza os diretórios que correspondem à cultura de interface do usuário e nem um arquivo .psd1 para o script nesses diretórios.

Você pode usar o parâmetro comum *ErrorAction* com um valor de SilentlyContinue para suprimir a mensagem de erro.
Isso é especialmente útil quando você forneceu mensagens de usuário em um idioma padrão ou de fallback, e nenhuma mensagem de erro é necessária.

Este exemplo compara dois scripts, Day1.ps1 e Day2.ps1, que incluem um comando **Import-LocalizedData** .
Os scripts são idênticos, exceto pelo fato de que Day2 usa o parâmetro comum *ErrorAction* com um valor de SilentlyContinue.

O exemplo de saída mostra os resultados da execução de ambos os scripts quando a cultura de interface de usuário está definida para fr-BE e não há arquivos ou pastas para aquela cultura de interface de usuário.
Day1.ps1 exibe uma mensagem de erro e uma saída em inglês.
Day2.ps1 apenas exibe a saída em inglês.

## PARAMETERS

### -BaseDirectory

Especifica o diretório base onde se encontram os arquivos .psd1.
O padrão é o diretório onde o script está localizado.
O **Import-LocalizedData** procura pelo arquivo .psd1 para o script em um subdiretório específico do idioma do diretório base.

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

Especifica a variável na qual as cadeias de caracteres de texto são importadas.
Insira um nome de variável sem um sinal de dólar ($).

No Windows PowerShell 2.0, esse parâmetro é necessário.
No Windows PowerShell 3.0, este parâmetro é opcional.
Se você omitir esse parâmetro, o **Import-LocalizedData** retorna uma tabela de hash das cadeias de caracteres de texto.
A tabela de hash é passada pelo pipeline ou exibida na linha de comando.

Ao usar o **Import-LocalizedData** para substituir cadeias de caracteres de texto padrão especificadas na seção DATA de um script, atribua a seção DATA a uma variável e insira o nome da variável da seção DATA no valor do parâmetro *BindingVariable* .
Então, quando o **Import-LocalizedData** salva o conteúdo importado no *BindingVariable* , os dados importados substituirão as cadeias de caracteres de texto padrão.
Se não especificar cadeias de caracteres de texto padrão, você pode selecionar qualquer nome de variável.

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

Especifica o nome do arquivo de dados (.psd1) a ser importado.
Insira um nome de arquivo.
Você pode especificar um nome de arquivo que não inclua sua extensão de nome de arquivo .psd1 ou especificar o nome do arquivo incluindo a extensão de nome de arquivo .psd1.

O parâmetro *FileName* é obrigatório quando o **Import-LocalizedData** não é usado em um script.
Caso contrário, o parâmetro é opcional e o valor padrão é o nome base do script.
Você pode usar esse parâmetro para direcionar **Import-LocalizedData** para procurar um arquivo .psd1 diferente.

Por exemplo, se o nome do *arquivo* for omitido e o nome do script for FindFiles.ps1, o **Import-LocalizedData** pesquisará o arquivo de dados do FindFiles.psd1.

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

Use esse parâmetro para incluir cmdlets e funções que você tenha escrito ou testado.
Para obter mais informações, consulte about_Script_Internationalization.

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
O padrão é o valor da variável automática $PsUICulture.
Insira uma cultura de interface do usuário no \<language\> - \<region\> formato, como en-US, de-de ou ar-SA.

O valor do parâmetro *UICulture* determina o subdiretório específico do idioma (dentro do diretório base) de onde o **Import-LocalizedData** obtém o arquivo .psd1 para o script.

O cmdlet pesquisa um subdiretório com o mesmo nome que o valor do parâmetro *UICulture* ou o $PsUICulture variável automática, como DE-de ou ar-SA.
Se não for possível localizar o diretório ou o diretório não contiver um arquivo. psd1 para o script, ele pesquisará um subdiretório com o nome do código de idioma, como de ou ar.
Se ele não encontra o subdiretório ou o arquivo .psd1, o comando falha e os dados são exibidos no idioma padrão especificado no script.

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

O **Import-LocalizedData** salva a tabela de hash na variável que é especificada pelo valor do parâmetro **BindingVariable** .

## OBSERVAÇÕES

* Antes de usar o **Import-LocalizedData** , localize suas mensagens de usuário. Formate as mensagens para cada localidade (cultura de interface de usuário) em uma tabela de hash em pares chave/valor e salve a tabela de hash em um arquivo com o mesmo nome que o script e uma extensão de nome de arquivo .psd1. Crie um diretório no diretório de scripts para cada cultura de interface de usuário com suporte e salve o arquivo .psd1 para cada cultura de interface de usuário no diretório com o nome da cultura de interface de usuário.

  Por exemplo, localize suas mensagens de usuário para a localidade de-DE e as formate em uma tabela de hash.
Salve uma tabela de hash em um arquivo \<ScriptName\>.psd1.
Em seguida, crie um subdiretório de-DE no diretório de scripts e salve o arquivo \<ScriptName\>.psd1 no subdiretório de-DE.
Repita esse método para cada localidade que você suporta.

* **Import-LocalizedData** executa uma pesquisa estruturada para as mensagens de usuário localizadas para um script.

  **Import-LocalizedData** inicia a pesquisa no diretório onde o arquivo de script está localizado (ou o valor do parâmetro *BaseDirectory* ).
Em seguida, ele pesquisa dentro do diretório base um subdiretório com o mesmo nome que o valor da variável $PsUICulture (ou o valor do parâmetro *UICulture* ), como DE-de ou ar-SA.
Em seguida, ele procura no subdiretório por um arquivo .psd1 com o mesmo nome do script (ou o valor do parâmetro *FileName* ).

  Se **Import-LocalizedData** não conseguir localizar um subdiretório com o nome da cultura da interface do usuário, ou o subdiretório não contiver um arquivo. psd1 para o script, ele pesquisará um arquivo. psd1 para o script em um subdiretório com o nome do código de idioma, como de ou ar.
Se ele não encontra o subdiretório ou o arquivo .psd1, o comando falha, os dados são exibidos no idioma padrão no script e uma mensagem de erro, explicando que os dados não puderam ser importados, é exibida.
Para suprimir a mensagem e reprovar normalmente, use o parâmetro *ErrorAction* comum com um valor de SilentlyContinue.

  Se o **Import-LocalizedData** localizar o subdiretório e o arquivo .psd1, ele importa a tabela de hash das mensagens de usuário para o valor do parâmetro *BindingVariable* no comando.
Em seguida, quando você exibe uma mensagem da tabela de hash na variável, a mensagem localizada é exibida.

  Para obter mais informações, consulte [about_Script_Internationalization](../Microsoft.PowerShell.Core/about/about_Script_Internationalization.md).

## LINKS RELACIONADOS

[Write-Host](Write-Host.md)

[Import-PowerShellDataFile](Import-PowerShellDataFile.md)

