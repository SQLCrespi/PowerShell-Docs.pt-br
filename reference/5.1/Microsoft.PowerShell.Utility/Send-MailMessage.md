---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 6f98c95e6c0144f76393e9d28454833097894512
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193746"
---
# <span data-ttu-id="30394-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="30394-103">Send-MailMessage</span></span>

## <span data-ttu-id="30394-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="30394-104">SYNOPSIS</span></span>
<span data-ttu-id="30394-105">Envia uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-105">Sends an email message.</span></span>

## <span data-ttu-id="30394-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30394-106">SYNTAX</span></span>

### <span data-ttu-id="30394-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="30394-107">All</span></span>

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## <span data-ttu-id="30394-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="30394-108">DESCRIPTION</span></span>

<span data-ttu-id="30394-109">O `Send-MailMessage` cmdlet envia uma mensagem de email de dentro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30394-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="30394-110">Você deve especificar um servidor de protocolo SMTP ou o `Send-MailMessage` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="30394-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="30394-111">Use o parâmetro **SmtpServer** ou defina a `$PSEmailServer` variável para um servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="30394-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="30394-112">O valor atribuído a `$PSEmailServer` é a configuração de SMTP padrão para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30394-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="30394-113">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="30394-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="30394-114">O `Send-MailMessage` cmdlet está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="30394-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="30394-115">Esse cmdlet não garante conexões seguras com servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="30394-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="30394-116">Embora não haja substituição imediata disponível no PowerShell, recomendamos que você não use o `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="30394-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="30394-117">Para obter mais informações, consulte [Nota de compatibilidade de plataforma DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="30394-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="30394-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="30394-118">EXAMPLES</span></span>

### <span data-ttu-id="30394-119">Exemplo 1: enviar um email de uma pessoa para outra pessoa</span><span class="sxs-lookup"><span data-stu-id="30394-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="30394-120">Este exemplo envia uma mensagem de email de uma pessoa para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="30394-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="30394-121">Os parâmetros **from** , **to** e **Subject** são exigidos pelo `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="30394-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="30394-122">Este exemplo usa a `$PSEmailServer` variável padrão para o servidor SMTP, portanto, o parâmetro **SmtpServer** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="30394-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="30394-123">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="30394-124">O parâmetro **to** especifica o destinatário da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="30394-125">O parâmetro **Subject** usa o email de **teste** da cadeia de texto como a mensagem porque o parâmetro de **corpo** opcional não está incluído.</span><span class="sxs-lookup"><span data-stu-id="30394-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="30394-126">Exemplo 2: enviar um anexo</span><span class="sxs-lookup"><span data-stu-id="30394-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="30394-127">Este exemplo envia uma mensagem de email com um anexo.</span><span class="sxs-lookup"><span data-stu-id="30394-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="30394-128">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="30394-129">O parâmetro **to** especifica os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="30394-130">O parâmetro **Subject** descreve o conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="30394-131">O parâmetro **Body** é o conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="30394-132">O parâmetro **Attachments** especifica o arquivo no diretório atual que é anexado à mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="30394-133">O parâmetro **Priority** define a mensagem como prioridade **alta** .</span><span class="sxs-lookup"><span data-stu-id="30394-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="30394-134">O parâmetro **-DeliveryNotificationOption** especifica dois valores, **OnSuccess** e **OnFailure** .</span><span class="sxs-lookup"><span data-stu-id="30394-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="30394-135">O remetente receberá notificações por email para confirmar o êxito ou a falha da entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="30394-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="30394-136">O parâmetro **SmtpServer** define o servidor SMTP como **SMTP.fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="30394-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="30394-137">Exemplo 3: enviar email para uma lista de endereçamento</span><span class="sxs-lookup"><span data-stu-id="30394-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="30394-138">Este exemplo envia uma mensagem de email para uma lista de endereçamento.</span><span class="sxs-lookup"><span data-stu-id="30394-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="30394-139">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="30394-140">O parâmetro **to** especifica os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="30394-141">O parâmetro **CC** envia uma cópia da mensagem para o destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="30394-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="30394-142">O parâmetro **BCC** envia uma cópia oculta da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="30394-143">Uma cópia oculta é um endereço de email oculto dos outros destinatários.</span><span class="sxs-lookup"><span data-stu-id="30394-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="30394-144">O parâmetro **Subject** é a mensagem porque o parâmetro de **corpo** opcional não está incluído.</span><span class="sxs-lookup"><span data-stu-id="30394-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="30394-145">O parâmetro **Credential** especifica que as credenciais de um administrador de domínio são usadas para enviar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="30394-146">O parâmetro **UseSsl** especifica que o SSL (Secure Socket Layer) cria uma conexão segura.</span><span class="sxs-lookup"><span data-stu-id="30394-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="30394-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30394-147">PARAMETERS</span></span>

### <span data-ttu-id="30394-148">-Anexos</span><span class="sxs-lookup"><span data-stu-id="30394-148">-Attachments</span></span>

<span data-ttu-id="30394-149">Especifica o caminho e os nomes de arquivo dos arquivos a serem anexados à mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="30394-150">Você pode usar esse parâmetro ou canalizar os caminhos e nomes de arquivo para `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="30394-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="30394-151">-Cco</span><span class="sxs-lookup"><span data-stu-id="30394-151">-Bcc</span></span>

<span data-ttu-id="30394-152">Especifica os endereços de email que recebem uma cópia do email, mas que não estão listados como destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30394-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="30394-153">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="30394-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="30394-154">-Corpo</span><span class="sxs-lookup"><span data-stu-id="30394-154">-Body</span></span>

<span data-ttu-id="30394-155">Especifica o conteúdo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-155">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-156">-BodyAsHtml</span><span class="sxs-lookup"><span data-stu-id="30394-156">-BodyAsHtml</span></span>

<span data-ttu-id="30394-157">Especifica que o valor do parâmetro **Body** contém HTML.</span><span class="sxs-lookup"><span data-stu-id="30394-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-158">-CC</span><span class="sxs-lookup"><span data-stu-id="30394-158">-Cc</span></span>

<span data-ttu-id="30394-159">Especifica os endereços de email para os quais uma cópia carbono (CC) da mensagem de email é enviada.</span><span class="sxs-lookup"><span data-stu-id="30394-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="30394-160">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="30394-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="30394-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="30394-161">-Credential</span></span>

<span data-ttu-id="30394-162">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="30394-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="30394-163">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="30394-163">The default is the current user.</span></span>

<span data-ttu-id="30394-164">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** .</span><span class="sxs-lookup"><span data-stu-id="30394-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="30394-165">Ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="30394-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="30394-166">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="30394-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="30394-167">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="30394-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-168">-DeliveryNotificationOption</span><span class="sxs-lookup"><span data-stu-id="30394-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="30394-169">Especifica as opções de notificação de entrega para a mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="30394-170">Você pode especificar vários valores.</span><span class="sxs-lookup"><span data-stu-id="30394-170">You can specify multiple values.</span></span>
<span data-ttu-id="30394-171">None é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="30394-171">None is the default value.</span></span> <span data-ttu-id="30394-172">O alias para esse parâmetro é **DNO** .</span><span class="sxs-lookup"><span data-stu-id="30394-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="30394-173">As notificações de entrega são enviadas para o endereço no parâmetro **from** .</span><span class="sxs-lookup"><span data-stu-id="30394-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="30394-174">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="30394-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="30394-175">`None`: Nenhuma notificação.</span><span class="sxs-lookup"><span data-stu-id="30394-175">`None`: No notification.</span></span>
- <span data-ttu-id="30394-176">`OnSuccess`: Notificar se a entrega for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="30394-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="30394-177">`OnFailure`: Notificar se a entrega não for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="30394-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="30394-178">`Delay`: Notificar se a entrega estiver atrasada.</span><span class="sxs-lookup"><span data-stu-id="30394-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="30394-179">`Never`: Nunca notificar.</span><span class="sxs-lookup"><span data-stu-id="30394-179">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-180">-Codificação</span><span class="sxs-lookup"><span data-stu-id="30394-180">-Encoding</span></span>

<span data-ttu-id="30394-181">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="30394-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="30394-182">O valor padrão é `Default`.</span><span class="sxs-lookup"><span data-stu-id="30394-182">The default value is `Default`.</span></span>

<span data-ttu-id="30394-183">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="30394-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="30394-184">`ASCII` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="30394-184">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="30394-185">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="30394-185">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="30394-186">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="30394-186">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="30394-187">`OEM` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="30394-187">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="30394-188">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="30394-188">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="30394-189">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="30394-189">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="30394-190">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="30394-190">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="30394-191">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="30394-191">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-192">-De</span><span class="sxs-lookup"><span data-stu-id="30394-192">-From</span></span>

<span data-ttu-id="30394-193">O parâmetro **from** é necessário.</span><span class="sxs-lookup"><span data-stu-id="30394-193">The **From** parameter is required.</span></span> <span data-ttu-id="30394-194">Esse parâmetro especifica o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="30394-194">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="30394-195">Insira um nome (opcional) e um endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="30394-195">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-196">-Port</span><span class="sxs-lookup"><span data-stu-id="30394-196">-Port</span></span>

<span data-ttu-id="30394-197">Especifica uma porta alternativa no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="30394-197">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="30394-198">O valor padrão é 25, que é a porta SMTP padrão.</span><span class="sxs-lookup"><span data-stu-id="30394-198">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-199">-Priority</span><span class="sxs-lookup"><span data-stu-id="30394-199">-Priority</span></span>

<span data-ttu-id="30394-200">Especifica a prioridade da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-200">Specifies the priority of the email message.</span></span> <span data-ttu-id="30394-201">Normal é o padrão.</span><span class="sxs-lookup"><span data-stu-id="30394-201">Normal is the default.</span></span> <span data-ttu-id="30394-202">Os valores aceitáveis para esse parâmetro são normal, alta e baixa.</span><span class="sxs-lookup"><span data-stu-id="30394-202">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-203">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="30394-203">-SmtpServer</span></span>

<span data-ttu-id="30394-204">Especifica o nome do servidor SMTP que envia a mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-204">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="30394-205">O valor padrão é o valor da `$PSEmailServer` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="30394-205">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="30394-206">Se a variável de preferência não estiver definida e esse parâmetro não for usado, o `Send-MailMessage` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="30394-206">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-207">-Assunto</span><span class="sxs-lookup"><span data-stu-id="30394-207">-Subject</span></span>

<span data-ttu-id="30394-208">O parâmetro **Subject** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="30394-208">The **Subject** parameter is required.</span></span> <span data-ttu-id="30394-209">Esse parâmetro especifica o assunto da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="30394-209">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-210">-Para</span><span class="sxs-lookup"><span data-stu-id="30394-210">-To</span></span>

<span data-ttu-id="30394-211">O parâmetro **to** é necessário.</span><span class="sxs-lookup"><span data-stu-id="30394-211">The **To** parameter is required.</span></span> <span data-ttu-id="30394-212">Esse parâmetro especifica o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="30394-212">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="30394-213">Se houver vários destinatários, separe seus endereços com uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="30394-213">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="30394-214">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="30394-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-215">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="30394-215">-UseSsl</span></span>

<span data-ttu-id="30394-216">O protocolo protocolo SSL (SSL) é usado para estabelecer uma conexão segura com o computador remoto para enviar email.</span><span class="sxs-lookup"><span data-stu-id="30394-216">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="30394-217">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="30394-217">By default, SSL is not used.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30394-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="30394-218">CommonParameters</span></span>

<span data-ttu-id="30394-219">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="30394-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30394-220">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="30394-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30394-221">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="30394-221">INPUTS</span></span>

### <span data-ttu-id="30394-222">System.String</span><span class="sxs-lookup"><span data-stu-id="30394-222">System.String</span></span>

<span data-ttu-id="30394-223">Você pode canalizar o caminho e os nomes de arquivo dos anexos para `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="30394-223">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="30394-224">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="30394-224">OUTPUTS</span></span>

### <span data-ttu-id="30394-225">Nenhum</span><span class="sxs-lookup"><span data-stu-id="30394-225">None</span></span>

<span data-ttu-id="30394-226">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="30394-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="30394-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="30394-227">NOTES</span></span>

## <span data-ttu-id="30394-228">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="30394-228">RELATED LINKS</span></span>

[<span data-ttu-id="30394-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="30394-229">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="30394-230">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="30394-230">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
