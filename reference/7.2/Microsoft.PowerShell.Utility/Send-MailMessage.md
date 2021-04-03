---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: e1363b2f30420c130093fd92d4da2f7c8037d640
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274318"
---
# Send-MailMessage

## Sinopse
Envia uma mensagem de email.

## Sintaxe

### Todos

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [[-Subject] <String>] [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## Descrição

O `Send-MailMessage` cmdlet envia uma mensagem de email de dentro do PowerShell.

Você deve especificar um servidor de protocolo SMTP ou o `Send-MailMessage` comando falhará. Use o parâmetro **SmtpServer** ou defina a `$PSEmailServer` variável para um servidor SMTP válido.
O valor atribuído a `$PSEmailServer` é a configuração de SMTP padrão para o PowerShell. Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

> [!WARNING]
> O `Send-MailMessage` cmdlet está obsoleto. Esse cmdlet não garante conexões seguras com servidores SMTP. Embora não haja substituição imediata disponível no PowerShell, recomendamos que você não use o `Send-MailMessage` . Para obter mais informações, consulte [Nota de compatibilidade de plataforma DE0005](https://aka.ms/SendMailMessage).

## Exemplos

### Exemplo 1: enviar um email de uma pessoa para outra pessoa

Este exemplo envia uma mensagem de email de uma pessoa para outra pessoa.

Os parâmetros **from**, **to** e **Subject** são exigidos pelo `Send-MailMessage` . Este exemplo usa a `$PSEmailServer` variável padrão para o servidor SMTP, portanto, o parâmetro **SmtpServer** não é necessário.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem. O parâmetro **to** especifica o destinatário da mensagem. O parâmetro **Subject** usa o email de **teste** da cadeia de texto como a mensagem porque o parâmetro de **corpo** opcional não está incluído.

### Exemplo 2: enviar um anexo

Este exemplo envia uma mensagem de email com um anexo.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem. O parâmetro **to** especifica os destinatários da mensagem. O parâmetro **Subject** descreve o conteúdo da mensagem. O parâmetro **Body** é o conteúdo da mensagem.

O parâmetro **Attachments** especifica o arquivo no diretório atual que é anexado à mensagem de email. O parâmetro **Priority** define a mensagem como prioridade **alta** . O parâmetro **-DeliveryNotificationOption** especifica dois valores, **OnSuccess** e **OnFailure**. O remetente receberá notificações por email para confirmar o êxito ou a falha da entrega de mensagens.
O parâmetro **SmtpServer** define o servidor SMTP como **SMTP.fabrikam.com**.

### Exemplo 3: enviar email para uma lista de endereçamento

Este exemplo envia uma mensagem de email para uma lista de endereçamento.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem. O parâmetro **to** especifica os destinatários da mensagem. O parâmetro **CC** envia uma cópia da mensagem para o destinatário especificado. O parâmetro **BCC** envia uma cópia oculta da mensagem. Uma cópia oculta é um endereço de email oculto dos outros destinatários. O parâmetro **Subject** é a mensagem porque o parâmetro de **corpo** opcional não está incluído.

O parâmetro **Credential** especifica que as credenciais de um administrador de domínio são usadas para enviar a mensagem. O parâmetro **UseSsl** especifica que o SSL (Secure Socket Layer) cria uma conexão segura.

## Parâmetros

### -Anexos

Especifica o caminho e os nomes de arquivo dos arquivos a serem anexados à mensagem de email. Você pode usar esse parâmetro ou canalizar os caminhos e nomes de arquivo para `Send-MailMessage` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Cco

Especifica os endereços de email que recebem uma cópia do email, mas que não estão listados como destinatários da mensagem. Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Corpo

Especifica o conteúdo da mensagem de email.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BodyAsHtml

Especifica que o valor do parâmetro **Body** contém HTML.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CC

Especifica os endereços de email para os quais uma cópia carbono (CC) da mensagem de email é enviada. Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**. Ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeliveryNotificationOption

Especifica as opções de notificação de entrega para a mensagem de email. Você pode especificar vários valores.
None é o valor padrão. O alias para esse parâmetro é **DNO**.

As notificações de entrega são enviadas para o endereço no parâmetro **from** .

Os valores aceitáveis para esse parâmetro são os seguintes:

- `None`: Nenhuma notificação.
- `OnSuccess`: Notificar se a entrega for bem-sucedida.
- `OnFailure`: Notificar se a entrega não for bem-sucedida.
- `Delay`: Notificar se a entrega estiver atrasada.
- `Never`: Nunca notificar.

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro **DeliveryNotification** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Codificação

Especifica o tipo de codificação para o arquivo de destino. O valor padrão é `utf8NoBOM`.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).
- `bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.
- `bigendianutf32`: Codifica em formato UTF-32 usando a ordem de byte big-endian.
- `oem`: Usa a codificação padrão para MS-DOS e programas de console.
- `unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.
- `utf7`: Codifica em formato UTF-7.
- `utf8`: Codifica em formato UTF-8.
- `utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)
- `utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)
- `utf32`: Codifica no formato UTF-32.

A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ). Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -De

O parâmetro **from** é necessário. Esse parâmetro especifica o endereço de email do remetente. Insira um nome (opcional) e um endereço de email, como `Name <someone@fabrikam.com>` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Especifica uma porta alternativa no servidor SMTP. O valor padrão é 25, que é a porta SMTP padrão.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Priority

Especifica a prioridade da mensagem de email. Normal é o padrão. Os valores aceitáveis para esse parâmetro são normal, alta e baixa.

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplyTo

Especifica endereços de email adicionais (diferentes do endereço de) a serem usados para responder a esta mensagem.
Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .

Esse parâmetro foi introduzido no PowerShell 6,2.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmtpServer

Especifica o nome do servidor SMTP que envia a mensagem de email.

O valor padrão é o valor da `$PSEmailServer` variável de preferência. Se a variável de preferência não estiver definida e esse parâmetro não for usado, o `Send-MailMessage` comando falhará.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Assunto

O parâmetro **Subject** não é obrigatório. Esse parâmetro especifica o assunto da mensagem de email.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Para

O parâmetro **to** é necessário. Esse parâmetro especifica o endereço de email do destinatário. Se houver vários destinatários, separe seus endereços com uma vírgula ( `,` ). Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSsl

O protocolo protocolo SSL (SSL) é usado para estabelecer uma conexão segura com o computador remoto para enviar email. Por padrão, SSL não é usado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System.String

Você pode canalizar o caminho e os nomes de arquivo dos anexos para `Send-MailMessage` .

## Saídas

### Nenhum

Este cmdlet não gera saída.

## Observações

## Links Relacionados

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

