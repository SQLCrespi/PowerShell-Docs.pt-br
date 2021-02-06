---
description: Descreve como o PowerShell usa a codificação de caracteres para entrada e saída de dados de cadeia de caracteres.
Locale: en-US
ms.date: 10/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Character_Encoding
ms.openlocfilehash: 3b47a528b0beae5e8142157454cbc676ffd7e795
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "99598231"
---
# <a name="about_character_encoding"></a>about_Character_Encoding

## <a name="short-description"></a>Descrição breve
Descreve como o PowerShell usa a codificação de caracteres para entrada e saída de dados de cadeia de caracteres.

## <a name="long-description"></a>Descrição longa

O Unicode é um padrão mundial de codificação de caracteres. O sistema usa Unicode exclusivamente para manipulação de caracteres e cadeias de caracteres. Para obter uma descrição detalhada de todos os aspectos do Unicode, consulte [o padrão Unicode](https://www.unicode.org/standard/standard.html).

O Windows dá suporte a conjuntos de caracteres Unicode e tradicionais. Conjuntos de caracteres tradicionais, como páginas de código do Windows, usam valores de 8 bits ou combinações de valores de 8 bits para representar os caracteres usados em uma linguagem específica ou configurações de região geográfica.

O PowerShell usa um conjunto de caracteres Unicode por padrão. No entanto, vários cmdlets têm um parâmetro de **codificação** que pode especificar a codificação para um conjunto de caracteres diferente. Esse parâmetro permite que você escolha a codificação de caracteres específica necessária para interoperabilidade com outros sistemas e aplicativos.

Os cmdlets a seguir têm o parâmetro **Encoding** :

- Microsoft.PowerShell.Management
  - Add-Content
  - Get-Content
  - Set-Content
- Microsoft.PowerShell.Utility
  - Export-Clixml
  - Export-Csv
  - Export-PSSession
  - Format-Hex
  - Import-Csv
  - Out-File
  - Select-String
  - Send-MailMessage

## <a name="the-byte-order-mark"></a>A marca de ordem de byte

A BOM (marca de ordem de byte) é uma _assinatura Unicode_ nos primeiros bytes de um fluxo de arquivo ou de texto que indica a codificação Unicode usada para os dados. Para obter mais informações, consulte a documentação de [marca de ordem de byte](/globalization/encoding/byte-order-mark) .

No Windows PowerShell, qualquer codificação Unicode, exceto `UTF7` , sempre cria uma bom. O PowerShell Core usa como padrão `utf8NoBOM` para toda a saída de texto.

Para obter a melhor compatibilidade geral, evite usar BOMs em arquivos UTF-8. As plataformas UNIX e os utilitários Unix-Heritage também usados em plataformas Windows não dão suporte a BOMs.

Da mesma forma, a `UTF7` codificação deve ser evitada. O UTF-7 não é uma codificação Unicode padrão e é escrito sem uma BOM em todas as versões do PowerShell.

Criar scripts do PowerShell em uma plataforma semelhante a UNIX ou usar um editor de plataforma cruzada no Windows, como Visual Studio Code, resulta em um arquivo codificado usando `UTF8NoBOM` . Esses arquivos funcionam bem no PowerShell Core, mas podem interromper o Windows PowerShell se o arquivo contiver caracteres não ASCII.

Se você precisar usar caracteres não ASCII em seus scripts, salve-os como UTF-8 com a BOM. Sem a BOM, o Windows PowerShell interpreta incorretamente seu script como codificado na página de código "ANSI" herdada. Por outro lado, os arquivos que têm a BOM UTF-8 podem ser problemáticos em plataformas semelhantes ao Unix. Muitas ferramentas Unix, como,, `cat` `sed` `awk` e alguns editores, como `gedit` não sabem como tratar a bom.

## <a name="character-encoding-in-windows-powershell"></a>Codificação de caracteres no Windows PowerShell

No PowerShell 5,1, o parâmetro de **codificação** dá suporte aos seguintes valores:

- `Ascii` Usa conjunto de caracteres ASCII (7 bits).
- `BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.
- `BigEndianUTF32` Usa UTF-32 com a ordem de byte big-endian.
- `Byte` Codifica um conjunto de caracteres em uma sequência de bytes.
- `Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).
- `Oem` Usa a codificação que corresponde à página de código OEM atual do sistema.
- `String` Igual a `Unicode`.
- `Unicode` Usa UTF-16 com a ordem de byte little-endian.
- `Unknown` Igual a `Unicode`.
- `UTF32` Usa UTF-32 com a ordem de byte little-endian.
- `UTF7` Usa UTF-7.
- `UTF8` Usa UTF-8 (com BOM).

Em geral, o Windows PowerShell usa a codificação [UTF-16Le](https://wikipedia.org/wiki/UTF-16) Unicode por padrão. No entanto, a codificação padrão usada por cmdlets no Windows PowerShell não é consistente.

> [!NOTE]
> Usar qualquer codificação Unicode, exceto `UTF7` , sempre cria uma bom.

Para cmdlets que gravam a saída em arquivos:

- `Out-File` e os operadores de redirecionamento `>` e `>>` criar UTF-16LE, que notavelmente difere de `Set-Content` e `Add-Content` .

- `New-ModuleManifest` e `Export-CliXml` também criar arquivos UTF-16LE.

- Quando o arquivo de destino estiver vazio ou não existir, `Set-Content` e `Add-Content` usar a `Default` codificação. `Default` é a codificação especificada pela página de código herdado do ANSI da localidade do sistema ativa.

- `Export-Csv` cria `Ascii` arquivos, mas usa codificação diferente ao usar o parâmetro **Append** (veja abaixo).

- `Export-PSSession` cria arquivos UTF-8 com a BOM por padrão.

- `New-Item -Type File -Value` Cria um arquivo UTF-8 sem BOM.

- `Send-MailMessage` usa `Default` a codificação por padrão.

- `Start-Transcript` cria `Utf8` arquivos com uma bom. Quando o parâmetro **Append** é usado, a codificação pode ser diferente (veja abaixo).

Para comandos que acrescentam a um arquivo existente:

- `Out-File -Append` e o `>>` operador de redirecionamento não faz nenhuma tentativa de corresponder à codificação do conteúdo do arquivo de destino existente. Em vez disso, eles usam a codificação padrão, a menos que o parâmetro de **codificação** seja usado. Você deve usar a codificação original de arquivos ao acrescentar conteúdo.

- Na ausência de um parâmetro de **codificação** explícito, `Add-Content` o detecta a codificação existente e a aplica automaticamente ao novo conteúdo. Se o conteúdo existente não tiver uma BOM, a `Default` codificação ANSI será usada. O comportamento do `Add-Content` é o mesmo no PowerShell Core (V6 e superior), exceto pela codificação padrão `Utf8` .

- `Export-Csv -Append` faz a correspondência da codificação existente quando o arquivo de destino contém uma BOM. Na ausência de uma BOM, ela usa `Utf8` codificação.

- `Start-Transcript -Append` corresponde à codificação existente de arquivos que incluem uma BOM. Na ausência de uma BOM, o padrão é a `Ascii` codificação. Essa codificação pode resultar em perda de dados ou corrupção de caracteres quando os dados na transcrição contiverem caracteres multibyte.

Para cmdlets que lêem dados de cadeia de caracteres na ausência de uma BOM:

- `Get-Content` e `Import-PowerShellDataFile` usa a `Default` codificação ANSI. O ANSI também é o que o mecanismo do PowerShell usa quando lê o código-fonte dos arquivos.

- `Import-Csv`, `Import-CliXml` e `Select-String` assumem `Utf8` a ausência de uma bom.

## <a name="character-encoding-in-powershell-core"></a>Codificação de caracteres no PowerShell Core

No PowerShell Core (V6 e superior), o parâmetro **Encoding** oferece suporte aos seguintes valores:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8 (sem BOM).
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.

O PowerShell Core usa como padrão `utf8NoBOM` para todas as saídas.

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage).

## <a name="changing-the-default-encoding"></a>Alterando a codificação padrão

O PowerShell tem duas variáveis padrão que podem ser usadas para alterar o comportamento de codificação padrão.

- `$PSDefaultParameterValues`
- `$OutputEncoding`

Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).

A partir do PowerShell 5,1, os operadores de redirecionamento ( `>` e `>>` ) chamam o `Out-File` cmdlet. Portanto, você pode definir a codificação padrão deles usando a `$PSDefaultParameterValues` variável de preferência, conforme mostrado neste exemplo:

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

Use a instrução a seguir para alterar a codificação padrão para todos os cmdlets que têm o parâmetro de **codificação** .

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> Colocar esse comando em seu perfil do PowerShell torna a preferência uma configuração global da sessão que afeta todos os comandos e scripts que não especificam explicitamente uma codificação.
>
> Da mesma forma, você deve incluir esses comandos em seus scripts ou módulos que você deseja que se comportem da mesma maneira. O uso desses comandos garante que os cmdlets se comportem da mesma maneira mesmo quando executados por outro usuário, em um computador diferente ou em uma versão diferente do PowerShell.

A variável automática `$OutputEncoding` afeta a codificação que o PowerShell usa para se comunicar com programas externos. Ele não tem nenhum efeito sobre a codificação que os operadores de redirecionamento de saída e os cmdlets do PowerShell usam para salvar em arquivos.

## <a name="see-also"></a>Consulte também

- [Introdução à codificação de caracteres no .NET](/dotnet/standard/base-types/character-encoding-introduction)
- [Páginas de código-aplicativos Win32](/windows/win32/intl/code-pages)
- [O padrão Unicode](https://www.unicode.org/standard/standard.html)
- [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage)
- [UTF-16LE](https://wikipedia.org/wiki/UTF-16)
- [Marca de ordem de byte](https://wikipedia.org/wiki/Byte_order_mark)
- [about_Preference_Variables](about_Preference_Variables.md)
