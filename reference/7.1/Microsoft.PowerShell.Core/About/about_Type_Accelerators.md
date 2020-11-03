---
description: Descreve os aceleradores de tipo disponíveis para classes do .NET Framework
keywords: powershell, cmdlet
Locale: en-US
ms.date: 05/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_accelerators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Accelerators
ms.openlocfilehash: 3c7f7f0d993819da1efbc7ba9f4c26bd2827bc84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195918"
---
# <a name="about-type-accelerators"></a>Sobre aceleradores de tipo

## <a name="short-desription"></a>DESCRIÇÃO COMPLETA DO CURTO
Descreve os aceleradores de tipo disponíveis para classes do .NET Framework

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os aceleradores de tipo são aliases para classes do .NET Framework. Eles permitem que você acesse classes específicas do .NET Framework sem precisar digitar explicitamente o nome inteiro da classe. Por exemplo, você pode encurtar a classe **AliasAttribute** de `[System.Management.Automation.AliasAttribute]` para `[Alias]` .

> [!NOTE]
> Todos os aceleradores de tipo ainda precisam ser encapsulados entre colchetes ( `[]` ).

## <a name="available-type-accelerators"></a>Aceleradores de tipo disponíveis

|        Acelerador          |                           Nome Completo da Classe                           |
|---------------------------- | ------------------------------------------------------------------- |
|editor                         | System. DirectoryServices. DirectoryEntry                             |
|adsisearcher                 | System. DirectoryServices. DirectorySearcher                          |
|Alias                        | System. Management. Automation. AliasAttribute                         |
|AllowEmptyCollection         | System. Management. Automation. AllowEmptyCollectionAttribute          |
|AllowEmptyString             | System. Management. Automation. AllowEmptyStringAttribute              |
|AllowNull                    | System. Management. Automation. AllowNullAttribute                     |
|ArgumentCompleter            | System. Management. Automation. ArgumentCompleterAttribute             |
|ArgumentCompletions          | System. Management. Automation. ArgumentCompletionsAttribute           |
|matriz                        | System.Array                                                        |
|bigint                       | System. Numerics. BigInteger                                          |
|bool                         | System.Boolean                                                      |
|byte                         | System.Byte                                                         |
|char                         | System.Char                                                         |
|cimclass                     | Microsoft. Management. Infrastructure. CimClass                        |
|cimconverter                 | Microsoft. Management. Infrastructure. CimConverter                    |
|ciminstance                  | Microsoft. Management. Infrastructure. CimInstance                     |
|CimSession                   | Microsoft.Management.Infrastructure.CimSession                      |
|CimType                      | Microsoft. Management. Infrastructure. CimType                         |
|CmdletBinding                | System. Management. Automation. CmdletBindingAttribute                 |
|CultureInfo                  | System. Globalization. CultureInfo                                    |
|DATETIME                     | System.DateTime                                                     |
|decimal                      | System.Decimal                                                      |
|double                       | System.Double                                                       |
|DscLocalConfigurationManager | System. Management. Automation. DscLocalConfigurationManagerAttribute  |
|DscProperty                  | System. Management. Automation. DscPropertyAttribute                   |
|DscResource                  | System. Management. Automation. DscResourceAttribute                   |
|Experimentoaction             | System. Management. Automation. Experimentoaction                       |
|Habilitação                 | System. Management. Automation. ExperimentalAttribute                  |
|ExperimentalFeature          | System. Management. Automation. ExperimentalFeature                    |
|float                        | System.Single                                                       |
|guid                         | System.Guid                                                         |
|tabela                    | System.Collections.Hashtable                                        |
|initialsessionstate          | System.Management.Automation.Runspaces.InitialSessionState          |
|INT                          | System.Int32                                                        |
|int16                        | System.Int16                                                        |
|int32                        | System.Int32                                                        |
|int64                        | System.Int64                                                        |
|IP                    | System .net. IPAddress                                                |
|IPEndpoint                   | System .net. IPEndPoint                                               |
|long                         | System.Int64                                                        |
|MailAddress                  | System .net. mail. MailAddress                                         |
|Valor nulo                   | System. Management. Automation. Language. NullString                    |
|ObjectSecurity               | System. Security. AccessControl. ObjectSecurity                        |
|OutputType                   | System. Management. Automation. OutputTypeAttribute                    |
|Parâmetro                    | System. Management. Automation. ParameterAttribute                     |
|PhysicalAddress              | System .net. NetworkInformation. PhysicalAddress                       |
|powershell                   | System. Management. Automation. PowerShell                             |
|psaliasproperty              | System. Management. Automation. PSAliasProperty                        |
|pscredential                 | System. Management. Automation. PSCredential                           |
|pscustomobject               | System. Management. Automation. PSObject                               |
|PSDefaultValue               | System.Management.Automation.PSDefaultValueAttribute                |
|pslistmodifier               | System. Management. Automation. PSListModifier                         |
|PSModuleInfo                 | System. Management. Automation. PSModuleInfo                           |
|psnoteproperty               | System. Management. Automation. PSNoteProperty                         |
|PSObject                     | System. Management. Automation. PSObject                               |
|psprimitivedictionary        | System. Management. Automation. PSPrimitiveDictionary                  |
|pspropertyexpression         | Microsoft. PowerShell. Commands. PSPropertyExpression                  |
|psscriptmethod               | System. Management. Automation. PSScriptMethod                         |
|psscriptproperty             | System. Management. Automation. PSScriptProperty                       |
|PSTypeNameAttribute          | System. Management. Automation. PSTypeNameAttribute                    |
|PSVariable                   | System. Management. Automation. PSVariable                             |
|psvariableproperty           | System. Management. Automation. PSVariableProperty                     |
|ref                          | System. Management. Automation. PSReference                            |
|regex                        | System.Text.RegularExpressions.Regex                                |
|runspace                     | System. Management. Automation. Runspaces. runspace                     |
|runspacefactory              | System. Management. Automation. Runspaces. RunspaceFactory              |
|sbyte                        | System.SByte                                                        |
|scriptblock                  | System. Management. Automation. ScriptBlock                            |
|secureString                 | System.Security.SecureString                                        |
|semver                       | System. Management. Automation. SemanticVersion                        |
|short                        | System.Int16                                                        |
|único                       | System.Single                                                       |
|string                       | System.String                                                       |
|SupportsWildcards            | System. Management. Automation. SupportsWildcardsAttribute             |
|switch                       | System.Management.Automation.SwitchParameter                        |
|TimeSpan                     | System.TimeSpan                                                     |
|tipo                         | System.Type                                                         |
|uint                         | System.UInt32                                                       |
|uint16                       | System.UInt16                                                       |
|uint32                       | System.UInt32                                                       |
|uint64                       | System.UInt64                                                       |
|ulong                        | System.UInt64                                                       |
|uri                          | System.Uri                                                          |
|ushort                       | System.UInt16                                                       |
|ValidateCount                | System. Management. Automation. ValidateCountAttribute                 |
|ValidateDrive                | System. Management. Automation. ValidateDriveAttribute                 |
|ValidateLength               | System. Management. Automation. ValidateLengthAttribute                |
|ValidateNotNull              | System. Management. Automation. ValidateNotNullAttribute               |
|ValidateNotNullOrEmpty       | System. Management. Automation. ValidateNotNullOrEmptyAttribute        |
|ValidatePattern              | System. Management. Automation. ValidatePatternAttribute               |
|ValidateRange                | System. Management. Automation. ValidateRangeAttribute                 |
|ValidateScript               | System. Management. Automation. ValidateScriptAttribute                |
|ValidateSet                  | System. Management. Automation. ValidateSetAttribute                   |
|ValidateTrustedData          | System. Management. Automation. ValidateTrustedDataAttribute           |
|ValidateUserDrive            | System. Management. Automation. ValidateUserDriveAttribute             |
|version                      | System.Version                                                      |
|void                         | System.Void                                                         |
|WildcardPattern              | System. Management. Automation. WildcardPattern                        |
|esses                          | System. Management. ManagementObject                                  |
|wmiclass                     | System. Management. ManagementClass                                   |
|wmisearcher                  | System. Management. ManagementObjectSearcher                          |
|X500DistinguishedName        | System. Security. Cryptography. X509Certificates. X500DistinguishedName |
|X509Certificate              | System. Security. Cryptography. X509Certificates. X509Certificate       |
|xml                          | System.Xml.XmlDocument                                              |

