---
description: Explica os modos de linguagem e seu efeito nas sessões do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: a75afd5149f3d290a8ec377417d4920b0ad6b526
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196007"
---
# <a name="about-language-modes"></a>Sobre os modos de linguagem

## <a name="short-description"></a>DESCRIÇÃO BREVE
Explica os modos de linguagem e seu efeito nas sessões do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O modo de linguagem de uma sessão do PowerShell determina, em parte, quais elementos da linguagem do PowerShell podem ser usados na sessão.

O PowerShell dá suporte aos seguintes modos de linguagem:

- FullLanguage
- ConstrainedLanguage (introduzido no PowerShell 3,0)
- RestrictedLanguage
- NoLanguage

### <a name="what-is-a-language-mode"></a>O QUE É UM MODO DE LINGUAGEM?

O modo de linguagem determina os elementos de linguagem que são permitidos na sessão.

O modo de linguagem é, na verdade, uma propriedade da configuração de sessão (ou "ponto de extremidade") usada para criar a sessão. Todas as sessões que usam uma configuração de sessão específica têm o modo de linguagem da configuração de sessão.

Todas as sessões do PowerShell têm um modo de linguagem, incluindo PSSessions que você cria usando o `New-PSSession` cmdlet, sessões temporárias que usam o parâmetro ComputerName e as sessões padrão que aparecem quando você inicia o PowerShell.

As sessões remotas são criadas usando as configurações de sessão no computador remoto. O modo de linguagem definido na configuração de sessão determina o modo de linguagem da sessão. Para especificar a configuração de sessão de uma PSSession, use o parâmetro ConfigurationName de cmdlets que criam uma sessão.

### <a name="language-modes"></a>MODOS DE LINGUAGEM

Esta seção descreve os modos de linguagem em sessões do PowerShell.

#### <a name="full-language-fulllanguage"></a>LINGUAGEM completa (FullLanguage)

O modo FullLanguage permite todos os elementos de linguagem na sessão.
FullLanguage é o modo de idioma padrão para sessões padrão em todas as versões do Windows, exceto para o Windows RT.

#### <a name="restricted-language-restrictedlanguage"></a>LINGUAGEM restrita (RestrictedLanguage)

No modo RestrictedLanguage, os usuários podem executar comandos (cmdlets, funções, comandos CIM e fluxos de trabalho), mas não têm permissão para usar blocos de script.

Por padrão, somente as seguintes variáveis são permitidas no modo RestrictedLanguage:

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

Somente os seguintes operadores de comparação são permitidos:

- `-eq` iguais
- `-gt` (maior que)
- `-lt` (menor que)

Não são permitidas instruções de atribuição, referências de propriedade e chamadas de método.

#### <a name="no-language-nolanguage"></a>SEM idioma (nolanguage)

O modo nolanguage só pode ser usado por meio da API. O modo nolanguage significa que nenhum texto de script de qualquer formulário é permitido. Isso impede o uso do método **addScript ()** que envia fragmentos de script do PowerShell a serem analisados e executados. Você só pode usar **AddCommand ()** e **AddParameter ()** que não passam pelo analisador.

#### <a name="constrained-language-constrained-language"></a>IDIOMA restrito (idioma restrito)

O modo ConstrainedLanguage permite todos os cmdlets e todos os elementos de linguagem do PowerShell, mas limita os tipos permitidos.

O modo ConstrainedLanguage foi projetado para dar suporte à integridade de código do modo de usuário (UMCI) no Windows RT. É o único modo de linguagem com suporte no Windows RT, mas está disponível em todos os sistemas com suporte.

O UMCI protege os dispositivos ARM, permitindo que apenas aplicativos assinados pela Microsoft e Microsoft sejam instalados em dispositivos baseados no Windows RT.
O modo ConstrainedLanguage impede que os usuários usem o PowerShell para burlar ou violar UMCI.

Os recursos do modo ConstrainedLanguage são os seguintes:

- Todos os cmdlets em módulos do Windows e outros cmdlets aprovados por UMCI, são totalmente funcionais e têm acesso completo aos recursos do sistema, exceto quando observado.

- Todos os elementos da linguagem de script do PowerShell são permitidos.

- Todos os módulos incluídos no Windows podem ser importados e todos os comandos que os módulos exportam são executados na sessão.

- No fluxo de trabalho do PowerShell, você pode gravar e executar fluxos de trabalho de script (fluxos de trabalho escritos na linguagem do PowerShell). Não há suporte para fluxos de trabalho baseados em XAML e você não pode executar XAML em um fluxo de trabalho de script, como usando `Invoke-Expression -Language XAML` . Além disso, os fluxos de trabalho não podem chamar outros fluxos de trabalho, embora os fluxos de trabalho aninhados sejam permitidos.

- O `Add-Type` cmdlet pode carregar assemblies assinados, mas não pode carregar código C# arbitrário ou APIs do Win32.

- O `New-Object` cmdlet pode ser usado somente em tipos permitidos (listados abaixo).

- Somente os tipos permitidos (listados abaixo) podem ser usados no PowerShell. Outros tipos não são permitidos.

- A conversão de tipo é permitida, mas somente quando o resultado é um tipo permitido.

- Parâmetros de cmdlet que convertem entrada de cadeia de caracteres em tipos só funcionam quando o tipo resultante é um tipo permitido.

- O método **ToString ()** e os métodos .net de tipos permitidos (listados abaixo) podem ser invocados. Outros métodos não podem ser invocados.

- Os usuários podem obter todas as propriedades de tipos permitidos. Os usuários podem definir os valores de propriedades somente em tipos de núcleo. Somente os seguintes objetos COM são permitidos:

  - **Script. Dictionary**
  - **Scripting.FileSystemObject**
  - **VBScript. RegExp**

Os tipos a seguir são permitidos no modo ConstrainedLanguage. Os usuários podem obter propriedades, invocar métodos e converter objetos para esses tipos.

Tipos permitidos:

- AliasAttribute
- AllowEmptyCollectionAttribute
- AllowEmptyStringAttribute
- AllowNullAttribute
- Array
- Bool
- byte
- char
- CmdletBindingAttribute
- Datetime
- decimal
- DirectoryEntry
- DirectorySearcher
- double
- FLOAT
- Guid
- Hashtable
- INT
- Int16
- long
- ManagementClass
- ManagementObject
- ManagementObjectSearcher
- Valor nulo
- OutputTypeAttribute
- Parâmetroattribute
- PSCredential
- PSDefaultValueAttribute
- PSListModifier
- PSObject
- PSPrimitiveDictionary
- PSReference
- PSTypeNameAttribute
- Regex
- SByte
- string
- SupportsWildcardsAttribute
- SwitchParameter
- System. Globalization. CultureInfo
- System .net. IPAddress
- System .net. mail. MailAddress
- System. Numerics. BigInteger
- System.Security.SecureString
- TimeSpan
- UInt16
- UInt32
- UInt64

### <a name="finding-the-language-mode-of-a-session-configuration"></a>LOCALIZANDO O MODO DE LINGUAGEM DE UMA CONFIGURAÇÃO DE SESSÃO

Quando uma configuração de sessão é criada usando um arquivo de configuração de sessão, a configuração de sessão tem uma propriedade Languagemode. Você pode encontrar o modo de linguagem obtendo o valor da propriedade Languagemode.

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

Em outras configurações de sessão, você pode encontrar o modo de linguagem indiretamente encontrando o modo de linguagem de uma sessão que é criada usando a configuração de sessão.

### <a name="finding-the-language-mode-of-a-session"></a>LOCALIZANDO O MODO DE LINGUAGEM DE UMA SESSÃO

Você pode encontrar o modo de linguagem de uma sessão FullLanguage ou ConstrainedLanguage obtendo o valor da propriedade Languagemode do estado da sessão.

Por exemplo:

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

No entanto, em sessões com modos RestrictedLanguage e nolanguage, você não pode usar o método dot para obter valores de propriedade. Em vez disso, a mensagem de erro revela o modo de linguagem.

Quando você executa o `$ExecutionContext.SessionState.LanguageMode` comando em uma sessão RestrictedLanguage, o PowerShell retorna as mensagens de erro PropertyReferenceNotSupportedInDataSection e VariableReferenceNotSupportedInDataSection.

- PropertyReferenceNotSupportedInDataSection: referências de propriedade não são permitidas no modo de linguagem restrita ou em uma seção de dados.
- VariableReferenceNotSupportedInDataSection uma variável que não pode ser referenciada no modo de linguagem restrita ou uma seção de dados está sendo referenciada.

Quando você executa o `$ExecutionContext.SessionState.LanguageMode` comando em uma sessão nolanguage, o PowerShell retorna a mensagem de erro ScriptsNotAllowed.

- ScriptsNotAllowed: não há suporte para a sintaxe neste runspace. Isso pode ocorrer porque ele não está no modo de linguagem.

## <a name="keywords"></a>Palavras-chave

- about_ConstrainedLanguage
- about_FullLanguage
- about_NoLanguage
- about_RestrictedLanguage

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Session_Configuration_Files](about_Session_Configuration_Files.md)
- [about_Session_Configurations](about_Session_Configurations.md)
