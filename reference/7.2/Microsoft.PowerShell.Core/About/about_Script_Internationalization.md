---
description: Descreve os recursos de internacionalização de script que tornam mais fácil para os scripts exibir mensagens e instruções para os usuários em sua linguagem de interface do usuário.
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 283ea6788e76b481c912fc5672350efd2e8bafaa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596607"
---
# <a name="about-script-internationalization"></a>Sobre a internacionalização de script

## <a name="short-description"></a>Descrição breve
Descreve os recursos de internacionalização de script que tornam mais fácil para os scripts exibir mensagens e instruções para os usuários em sua linguagem de interface do usuário.

## <a name="long-description"></a>Descrição longa

Os recursos de internacionalização de script do PowerShell permitem que você atenda melhor aos usuários em todo o mundo, exibindo ajuda e mensagens de usuário no idioma do usuário.

Os recursos de internacionalização de script consultam a cultura da interface do usuário do sistema operacional durante a execução, importam as cadeias de caracteres de texto traduzidas apropriadas e as exibem para o usuário. A seção de dados permite que você armazene cadeias de caracteres de texto separadas do código para que elas sejam facilmente identificadas e extraídas. Um novo cmdlet, `ConvertFrom-StringData` , converte cadeias de caracteres de texto em tabelas de hash do tipo dicionário para facilitar a tradução.

Para dar suporte ao texto de ajuda internacional, o PowerShell inclui os seguintes recursos:

- Uma seção de dados que separa cadeias de caracteres de texto das instruções de código. Para obter mais informações sobre a seção de dados, consulte [about_Data_Sections](about_Data_Sections.md).

- Novas variáveis automáticas `$PSCulture` e `$PSUICulture` . `$PSCulture` armazena o nome do idioma da interface do usuário usado no sistema para elementos como data, hora e moeda. A `$PSUICulture` variável armazena o nome do idioma da interface do usuário usado no sistema para elementos de interface de usuários, como menus e cadeias de caracteres de texto.

- Um cmdlet, `ConvertFrom-StringData` , que converte cadeias de caracteres de texto em tabelas de hash do tipo dicionário para facilitar a tradução. Para obter mais informações, consulte [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).

- Um novo tipo de arquivo, `.psd1` , que armazena cadeias de caracteres de texto traduzidas. Os `.psd1` arquivos são armazenados em subdiretórios específicos do idioma do diretório do script.

- Um cmdlet, `Import-LocalizedData` , que importa cadeias de caracteres de texto traduzidas para um idioma especificado em um script em tempo de execução. Esse cmdlet reconhece e importa cadeias de caracteres em qualquer idioma com suporte do Windows. Para obter mais informações, consulte [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).

### <a name="the-data-section-storing-default-strings"></a>A seção de dados: armazenando cadeias de caracteres padrão

Use uma seção de dados no script para armazenar as cadeias de caracteres de texto no idioma padrão. Organize as cadeias de caracteres em pares de chave/valor em uma cadeia aqui. Cada par chave/valor deve estar em uma linha separada. Se você incluir comentários, os comentários deverão estar em linhas separadas.

O `ConvertFrom-StringData` cmdlet converte os pares de chave/valor na cadeia de caracteres here em uma tabela de hash do tipo dicionário que é armazenada no valor da variável da seção de dados.

No exemplo a seguir, a seção de dados do `World.ps1` script inclui o conjunto de mensagens de prompt do English-United Estados (en-US) de um script. O `ConvertFrom-StringData` cmdlet converte as cadeias de caracteres em uma tabela de hash e as armazena na `$msgtable` variável.

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

Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).

### <a name="psd1-files-storing-translated-strings"></a>Arquivos PSD1: armazenando cadeias de caracteres traduzidas

Salve as mensagens de script para cada idioma da interface do usuário em arquivos de texto separados com o mesmo nome que o script e a `.psd1` extensão de nome de arquivo. Armazene os arquivos em subdiretórios do diretório de script com nomes de culturas no seguinte formato:

`<language>-<region>`

Exemplos: de-DE, ar-SA e zh-Hans

Por exemplo, se o `World.ps1` script for armazenado no `C:\Scripts` diretório, você criaria uma estrutura de diretório de arquivos semelhante à seguinte:

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

O `World.psd1` arquivo no subdiretório de de um do diretório de script pode incluir a seguinte instrução:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

Da mesma forma, o `World.psd1` arquivo no subdiretório ar-SA do diretório de script pode incluir a seguinte instrução:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a>Import-LocalizedData: recuperação dinâmica de cadeias de caracteres traduzidas

Para recuperar as cadeias de caracteres no idioma da interface do usuário atual, use o `Import-LocalizedData` cmdlet.

`Import-LocalizedData` localiza o valor da `$PSUICulture` variável automática e importa o conteúdo dos `<script-name>.psd1` arquivos no subdiretório que corresponde ao `$PSUICulture` valor. Em seguida, ele salva o conteúdo importado na variável especificada pelo valor do parâmetro **BindingVariable** .

```powershell
Import-LocalizedData -BindingVariable msgTable
```

Por exemplo, se o `Import-LocalizedData` comando aparecer no `C:\Scripts\World.ps1` script e o valor de `$PSUICulture` for "ar-SA", `Import-LocalizedData` o encontrará o seguinte arquivo:

`C:\Scripts\ar-SA\World.psd1`

Em seguida, ele importa as cadeias de caracteres de texto árabes do arquivo para a `$msgTable` variável, substituindo quaisquer cadeias de caracteres padrão que possam ser definidas na seção de dados do `World.ps1` script.

Como resultado, quando o script usa a `$msgTable` variável para exibir mensagens do usuário, as mensagens são exibidas em árabe.

Por exemplo, o script a seguir exibe a mensagem "Insira seu nome de usuário" em árabe:

```powershell
if (!($username)) { $msgTable.promptMsg }
```

Se o `Import-LocalizedData` não puder encontrar um `.psd1` arquivo que corresponda ao valor de `$PSUIculture` , o valor de `$msgTable` não será substituído e a chamada para `$msgTable.promptMsg` exibirá as cadeias de caracteres de fallback en-US.

## <a name="examples"></a>Exemplos

Este exemplo mostra como os recursos de internacionalização de script são usados em um script para exibir um dia da semana para os usuários no idioma definido no computador.

A seguir está uma lista completa do arquivo de script Sample1.ps1.

O script começa com uma seção de dados denominada Day ($Day) que contém um `ConvertFrom-StringData` comando. A expressão enviada para `ConvertFrom-StringData` é uma cadeia de caracteres aqui que contém os nomes de dia na cultura da interface do usuário padrão, en-US, em pares de chave/valor. O `ConvertFrom-StringData` cmdlet converte os pares de chave/valor na cadeia de caracteres here em uma tabela de hash e, em seguida, salva-os no valor da `$Day` variável.

O `Import-LocalizedData` comando importa o conteúdo do `.psd1` arquivo no diretório que corresponde ao valor da `$PSUICulture` variável automática e, em seguida, salva-o na `$Day` variável, substituindo os valores de `$Day` definidos na seção de dados.

Os comandos restantes carregam as cadeias de caracteres em uma matriz e as exibem.

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

Os `.psd1` arquivos que oferecem suporte ao script são salvos em subdiretórios do diretório de script com nomes que correspondem aos `$PSUICulture` valores.

A seguir está uma lista completa de `.\de-DE\sample1.psd1` :

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

Como resultado, quando você executa Sample.ps1 em um sistema no qual o valor de `$PSUICulture` é de-de, a saída do script é:

```Output
Heute ist Freitag
```

## <a name="see-also"></a>Consulte também

- [about_Data_Sections](about_Data_Sections.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

