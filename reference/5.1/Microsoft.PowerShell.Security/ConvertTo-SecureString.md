---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: 6e536681f78a79660e80951d0dcc446fbba32553
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "93196621"
---
# ConvertTo-SecureString

## SINOPSE
Converte texto sem formatação ou cadeias de caracteres criptografadas para proteger cadeias de caracteres.

## SYNTAX

### Seguro (padrão)

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### Texto sem formatação

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### Aberto

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertTo-SecureString` cmdlet converte cadeias de caracteres padrão criptografadas em cadeias de caracteres seguras. Também pode converter o texto sem formatação em cadeias de caracteres seguras. Ele é usado com `ConvertFrom-SecureString` e `Read-Host` . A cadeia de caracteres segura criada pelo cmdlet pode ser usada com cmdlets ou funções que exigem um parâmetro do tipo **SecureString** . A cadeia de caracteres segura pode ser convertida novamente em uma cadeia de caracteres criptografada padrão usando o `ConvertFrom-SecureString` cmdlet. Isso permite que ele seja armazenada em um arquivo para uso posterior.

Se a cadeia de caracteres padrão que está sendo convertida tiver sido criptografada com o `ConvertFrom-SecureString` usando uma chave especificada, essa mesma chave deverá ser fornecida como o valor do parâmetro **Key** ou **SecureKey** do `ConvertTo-SecureString` cmdlet.

## EXEMPLOS

### Exemplo 1: converter uma cadeia de caracteres segura em uma cadeia de caracteres criptografada

Este exemplo mostra como criar uma cadeia de caracteres segura da entrada do usuário, converter a cadeia de caracteres segura em uma cadeia de caracteres criptografada padrão e converter a cadeia de caracteres criptografada padrão novamente em uma cadeia de caracteres segura.

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

O primeiro comando usa o parâmetro **AsSecureString** do `Read-Host` cmdlet para criar uma cadeia de caracteres segura. Depois de inserir o comando, todos os caracteres que você digitar serão convertidos em uma cadeia de caracteres segura e, em seguida, salvos na `$Secure` variável.

O segundo comando exibe o conteúdo da `$Secure` variável. Como a `$Secure` variável contém uma cadeia de caracteres segura, o PowerShell exibe somente o tipo **System. Security. SecureString** .

O terceiro comando usa o `ConvertFrom-SecureString` cmdlet para converter a cadeia de caracteres segura na `$Secure` variável em uma cadeia de caracteres criptografada padrão. Ele salva o resultado na `$Encrypted` variável.

O quarto comando exibe a cadeia de caracteres criptografada no valor da `$Encrypted` variável.

O quinto comando usa o `ConvertTo-SecureString` cmdlet para converter a cadeia de caracteres criptografada padrão na `$Encrypted` variável de volta em uma cadeia de caracteres segura. Ele salva o resultado na `$Secure2` variável.
O sexto comando exibe o valor da `$Secure2` variável. O tipo SecureString indica que o comando foi bem-sucedido.

### Exemplo 2: criar uma cadeia de caracteres segura de uma cadeia de caracteres criptografada em um arquivo

Este exemplo mostra como criar uma cadeia de caracteres segura de uma cadeia de caracteres criptografada padrão que é salva em um arquivo.

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

O primeiro comando usa o parâmetro **AsSecureString** do `Read-Host` cmdlet para criar uma cadeia de caracteres segura. Depois de inserir o comando, todos os caracteres que você digitar serão convertidos em uma cadeia de caracteres segura e, em seguida, salvos na `$Secure` variável.

O segundo comando usa o `ConvertFrom-SecureString` cmdlet para converter a cadeia de caracteres segura na `$Secure` variável em uma cadeia de caracteres padrão criptografada usando a chave especificada. O conteúdo é salvo na `$Encrypted` variável.

O terceiro comando usa um operador de pipeline ( `|` ) para enviar o valor da `$Encrypted` variável para o `Set-Content` cmdlet, que salva o valor no arquivo de Encrypted.txt.

O quarto comando usa o `Get-Content` cmdlet para obter a cadeia de caracteres criptografada padrão no arquivo de Encrypted.txt. O comando usa um operador de pipeline para enviar a cadeia de caracteres criptografada para o `ConvertTo-SecureString` cmdlet, que converte-o em uma cadeia de caracteres segura usando a chave especificada.
Os resultados são salvos na `$Secure2` variável.

### Exemplo 3: converter uma cadeia de caracteres de texto sem formatação em uma cadeia de caracteres segura

Esse comando converte a cadeia de texto sem formatação `P@ssW0rD!` em uma cadeia de caracteres segura e armazena o resultado na `$Secure_String_Pwd` variável. Para usar o parâmetro **Astexto não criptografado** , o parâmetro **Force** também deve ser incluído no comando.

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> Evite usar cadeias de caracteres de texto sem formatação no script ou na linha de comando. O texto sem formatação pode aparecer nos logs de eventos e nos logs de histórico de comandos.

## PARAMETERS

### -Astexto não criptografado

Especifica uma cadeia de caracteres de texto sem formatação para converter em uma cadeia de caracteres segura. Os cmdlets de cadeia de caracteres segura protegem texto confidencial. O texto é criptografado para privacidade e é excluído da memória do computador depois que ele é usado. Se você usar esse parâmetro para fornecer texto sem formatação como entrada, o sistema não poderá proteger essa entrada dessa maneira. Para usar esse parâmetro, você também deve especificar o parâmetro **Force** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Confirma que você entende as implicações de usar o parâmetro **Astexto não criptografado** e ainda deseja usá-lo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Chave

Especifica a chave de criptografia usada para converter a cadeia de caracteres segura original na cadeia de caracteres padrão criptografada. Os comprimentos de chave válidos são 16, 24 e 32 bytes.

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureKey

Especifica a chave de criptografia usada para converter a cadeia de caracteres segura original na cadeia de caracteres padrão criptografada. A chave deve ser fornecida no formato de uma cadeia de caracteres segura. A cadeia de caracteres segura será convertida em uma matriz de bytes a ser usada como chave. Os comprimentos de chave segura válidos são 8, 12 e 16 pontos de código.

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cadeia de caracteres

Especifica a cadeia de caracteres a ser convertida em uma cadeia de caracteres segura.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres criptografada padrão para `ConvertTo-SecureString` .

## SAÍDAS

### System.Security.SecureString

`ConvertTo-SecureString` Retorna um objeto **SecureString** .

## OBSERVAÇÕES

Alguns caracteres, como emoticons, correspondem a vários pontos de código na cadeia de caracteres que os contém. Evite usar esses caracteres, pois eles podem causar problemas e mal-entendidos incompreendidos quando usados em uma senha.

## LINKS RELACIONADOS

[ConvertFrom-SecureString](ConvertFrom-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)
