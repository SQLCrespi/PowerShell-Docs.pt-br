---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 367cd4c193d9cee2375d9ef119bbf7731364351e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194387"
---
# <span data-ttu-id="94466-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="94466-103">Send-MailMessage</span></span>

## <span data-ttu-id="94466-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="94466-104">SYNOPSIS</span></span>
<span data-ttu-id="94466-105">Envia uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-105">Sends an email message.</span></span>

## <span data-ttu-id="94466-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94466-106">SYNTAX</span></span>

### <span data-ttu-id="94466-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="94466-107">All</span></span>

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [-Subject] <String> [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="94466-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94466-108">DESCRIPTION</span></span>

<span data-ttu-id="94466-109">O `Send-MailMessage` cmdlet envia uma mensagem de email de dentro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94466-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="94466-110">Você deve especificar um servidor de protocolo SMTP ou o `Send-MailMessage` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="94466-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="94466-111">Use o parâmetro **SmtpServer** ou defina a `$PSEmailServer` variável para um servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="94466-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="94466-112">O valor atribuído a `$PSEmailServer` é a configuração de SMTP padrão para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94466-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="94466-113">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="94466-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="94466-114">O `Send-MailMessage` cmdlet está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="94466-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="94466-115">Esse cmdlet não garante conexões seguras com servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="94466-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="94466-116">Embora não haja substituição imediata disponível no PowerShell, recomendamos que você não use o `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="94466-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="94466-117">Para obter mais informações, consulte [Nota de compatibilidade de plataforma DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="94466-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="94466-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="94466-118">EXAMPLES</span></span>

### <span data-ttu-id="94466-119">Exemplo 1: enviar um email de uma pessoa para outra pessoa</span><span class="sxs-lookup"><span data-stu-id="94466-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="94466-120">Este exemplo envia uma mensagem de email de uma pessoa para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="94466-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="94466-121">Os parâmetros **from** , **to** e **Subject** são exigidos pelo `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="94466-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="94466-122">Este exemplo usa a `$PSEmailServer` variável padrão para o servidor SMTP, portanto, o parâmetro **SmtpServer** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="94466-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="94466-123">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="94466-124">O parâmetro **to** especifica o destinatário da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="94466-125">O parâmetro **Subject** usa o email de **teste** da cadeia de texto como a mensagem porque o parâmetro de **corpo** opcional não está incluído.</span><span class="sxs-lookup"><span data-stu-id="94466-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="94466-126">Exemplo 2: enviar um anexo</span><span class="sxs-lookup"><span data-stu-id="94466-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="94466-127">Este exemplo envia uma mensagem de email com um anexo.</span><span class="sxs-lookup"><span data-stu-id="94466-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="94466-128">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="94466-129">O parâmetro **to** especifica os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="94466-130">O parâmetro **Subject** descreve o conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="94466-131">O parâmetro **Body** é o conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="94466-132">O parâmetro **Attachments** especifica o arquivo no diretório atual que é anexado à mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="94466-133">O parâmetro **Priority** define a mensagem como prioridade **alta** .</span><span class="sxs-lookup"><span data-stu-id="94466-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="94466-134">O parâmetro **-DeliveryNotificationOption** especifica dois valores, **OnSuccess** e **OnFailure** .</span><span class="sxs-lookup"><span data-stu-id="94466-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="94466-135">O remetente receberá notificações por email para confirmar o êxito ou a falha da entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="94466-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="94466-136">O parâmetro **SmtpServer** define o servidor SMTP como **SMTP.fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="94466-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="94466-137">Exemplo 3: enviar email para uma lista de endereçamento</span><span class="sxs-lookup"><span data-stu-id="94466-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="94466-138">Este exemplo envia uma mensagem de email para uma lista de endereçamento.</span><span class="sxs-lookup"><span data-stu-id="94466-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="94466-139">O `Send-MailMessage` cmdlet usa o parâmetro **from** para especificar o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="94466-140">O parâmetro **to** especifica os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="94466-141">O parâmetro **CC** envia uma cópia da mensagem para o destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="94466-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="94466-142">O parâmetro **BCC** envia uma cópia oculta da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="94466-143">Uma cópia oculta é um endereço de email oculto dos outros destinatários.</span><span class="sxs-lookup"><span data-stu-id="94466-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="94466-144">O parâmetro **Subject** é a mensagem porque o parâmetro de **corpo** opcional não está incluído.</span><span class="sxs-lookup"><span data-stu-id="94466-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="94466-145">O parâmetro **Credential** especifica que as credenciais de um administrador de domínio são usadas para enviar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="94466-146">O parâmetro **UseSsl** especifica que o SSL (Secure Socket Layer) cria uma conexão segura.</span><span class="sxs-lookup"><span data-stu-id="94466-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="94466-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94466-147">PARAMETERS</span></span>

### <span data-ttu-id="94466-148">-Anexos</span><span class="sxs-lookup"><span data-stu-id="94466-148">-Attachments</span></span>

<span data-ttu-id="94466-149">Especifica o caminho e os nomes de arquivo dos arquivos a serem anexados à mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="94466-150">Você pode usar esse parâmetro ou canalizar os caminhos e nomes de arquivo para `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="94466-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

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

### <span data-ttu-id="94466-151">-Cco</span><span class="sxs-lookup"><span data-stu-id="94466-151">-Bcc</span></span>

<span data-ttu-id="94466-152">Especifica os endereços de email que recebem uma cópia do email, mas que não estão listados como destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="94466-153">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="94466-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="94466-154">-Corpo</span><span class="sxs-lookup"><span data-stu-id="94466-154">-Body</span></span>

<span data-ttu-id="94466-155">Especifica o conteúdo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-155">Specifies the content of the email message.</span></span>

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

### <span data-ttu-id="94466-156">-BodyAsHtml</span><span class="sxs-lookup"><span data-stu-id="94466-156">-BodyAsHtml</span></span>

<span data-ttu-id="94466-157">Especifica que o valor do parâmetro **Body** contém HTML.</span><span class="sxs-lookup"><span data-stu-id="94466-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

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

### <span data-ttu-id="94466-158">-CC</span><span class="sxs-lookup"><span data-stu-id="94466-158">-Cc</span></span>

<span data-ttu-id="94466-159">Especifica os endereços de email para os quais uma cópia carbono (CC) da mensagem de email é enviada.</span><span class="sxs-lookup"><span data-stu-id="94466-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="94466-160">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="94466-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="94466-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="94466-161">-Credential</span></span>

<span data-ttu-id="94466-162">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="94466-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="94466-163">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="94466-163">The default is the current user.</span></span>

<span data-ttu-id="94466-164">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** .</span><span class="sxs-lookup"><span data-stu-id="94466-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="94466-165">Ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94466-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="94466-166">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="94466-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="94466-167">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="94466-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="94466-168">-DeliveryNotificationOption</span><span class="sxs-lookup"><span data-stu-id="94466-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="94466-169">Especifica as opções de notificação de entrega para a mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="94466-170">Você pode especificar vários valores.</span><span class="sxs-lookup"><span data-stu-id="94466-170">You can specify multiple values.</span></span>
<span data-ttu-id="94466-171">None é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="94466-171">None is the default value.</span></span> <span data-ttu-id="94466-172">O alias para esse parâmetro é **DNO** .</span><span class="sxs-lookup"><span data-stu-id="94466-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="94466-173">As notificações de entrega são enviadas para o endereço no parâmetro **from** .</span><span class="sxs-lookup"><span data-stu-id="94466-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="94466-174">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="94466-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="94466-175">`None`: Nenhuma notificação.</span><span class="sxs-lookup"><span data-stu-id="94466-175">`None`: No notification.</span></span>
- <span data-ttu-id="94466-176">`OnSuccess`: Notificar se a entrega for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="94466-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="94466-177">`OnFailure`: Notificar se a entrega não for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="94466-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="94466-178">`Delay`: Notificar se a entrega estiver atrasada.</span><span class="sxs-lookup"><span data-stu-id="94466-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="94466-179">`Never`: Nunca notificar.</span><span class="sxs-lookup"><span data-stu-id="94466-179">`Never`: Never notify.</span></span>

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

### <span data-ttu-id="94466-180">-Codificação</span><span class="sxs-lookup"><span data-stu-id="94466-180">-Encoding</span></span>

<span data-ttu-id="94466-181">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="94466-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="94466-182">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="94466-182">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="94466-183">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="94466-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="94466-184">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="94466-184">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="94466-185">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="94466-185">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="94466-186">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="94466-186">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="94466-187">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="94466-187">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="94466-188">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="94466-188">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="94466-189">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="94466-189">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="94466-190">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="94466-190">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="94466-191">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="94466-191">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="94466-192">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="94466-192">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="94466-193">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="94466-193">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="94466-194">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="94466-194">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="94466-195">-De</span><span class="sxs-lookup"><span data-stu-id="94466-195">-From</span></span>

<span data-ttu-id="94466-196">O parâmetro **from** é necessário.</span><span class="sxs-lookup"><span data-stu-id="94466-196">The **From** parameter is required.</span></span> <span data-ttu-id="94466-197">Esse parâmetro especifica o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="94466-197">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="94466-198">Insira um nome (opcional) e um endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="94466-198">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="94466-199">-Port</span><span class="sxs-lookup"><span data-stu-id="94466-199">-Port</span></span>

<span data-ttu-id="94466-200">Especifica uma porta alternativa no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="94466-200">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="94466-201">O valor padrão é 25, que é a porta SMTP padrão.</span><span class="sxs-lookup"><span data-stu-id="94466-201">The default value is 25, which is the default SMTP port.</span></span>

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

### <span data-ttu-id="94466-202">-Priority</span><span class="sxs-lookup"><span data-stu-id="94466-202">-Priority</span></span>

<span data-ttu-id="94466-203">Especifica a prioridade da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-203">Specifies the priority of the email message.</span></span> <span data-ttu-id="94466-204">Normal é o padrão.</span><span class="sxs-lookup"><span data-stu-id="94466-204">Normal is the default.</span></span> <span data-ttu-id="94466-205">Os valores aceitáveis para esse parâmetro são normal, alta e baixa.</span><span class="sxs-lookup"><span data-stu-id="94466-205">The acceptable values for this parameter are Normal, High, and Low.</span></span>

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

### <span data-ttu-id="94466-206">-ReplyTo</span><span class="sxs-lookup"><span data-stu-id="94466-206">-ReplyTo</span></span>

<span data-ttu-id="94466-207">Especifica endereços de email adicionais (diferentes do endereço de) a serem usados para responder a esta mensagem.</span><span class="sxs-lookup"><span data-stu-id="94466-207">Specifies additional email addresses (other than the From address) to use to reply to this message.</span></span>
<span data-ttu-id="94466-208">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="94466-208">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

<span data-ttu-id="94466-209">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="94466-209">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="94466-210">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="94466-210">-SmtpServer</span></span>

<span data-ttu-id="94466-211">Especifica o nome do servidor SMTP que envia a mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-211">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="94466-212">O valor padrão é o valor da `$PSEmailServer` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="94466-212">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="94466-213">Se a variável de preferência não estiver definida e esse parâmetro não for usado, o `Send-MailMessage` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="94466-213">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

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

### <span data-ttu-id="94466-214">-Assunto</span><span class="sxs-lookup"><span data-stu-id="94466-214">-Subject</span></span>

<span data-ttu-id="94466-215">O parâmetro **Subject** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="94466-215">The **Subject** parameter is required.</span></span> <span data-ttu-id="94466-216">Esse parâmetro especifica o assunto da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="94466-216">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="94466-217">-Para</span><span class="sxs-lookup"><span data-stu-id="94466-217">-To</span></span>

<span data-ttu-id="94466-218">O parâmetro **to** é necessário.</span><span class="sxs-lookup"><span data-stu-id="94466-218">The **To** parameter is required.</span></span> <span data-ttu-id="94466-219">Esse parâmetro especifica o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="94466-219">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="94466-220">Se houver vários destinatários, separe seus endereços com uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="94466-220">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="94466-221">Insira nomes (opcional) e o endereço de email, como `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="94466-221">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="94466-222">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="94466-222">-UseSsl</span></span>

<span data-ttu-id="94466-223">O protocolo protocolo SSL (SSL) é usado para estabelecer uma conexão segura com o computador remoto para enviar email.</span><span class="sxs-lookup"><span data-stu-id="94466-223">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="94466-224">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="94466-224">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="94466-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="94466-225">CommonParameters</span></span>

<span data-ttu-id="94466-226">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="94466-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94466-227">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="94466-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94466-228">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="94466-228">INPUTS</span></span>

### <span data-ttu-id="94466-229">System.String</span><span class="sxs-lookup"><span data-stu-id="94466-229">System.String</span></span>

<span data-ttu-id="94466-230">Você pode canalizar o caminho e os nomes de arquivo dos anexos para `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="94466-230">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="94466-231">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="94466-231">OUTPUTS</span></span>

### <span data-ttu-id="94466-232">Nenhum</span><span class="sxs-lookup"><span data-stu-id="94466-232">None</span></span>

<span data-ttu-id="94466-233">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="94466-233">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="94466-234">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="94466-234">NOTES</span></span>

## <span data-ttu-id="94466-235">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="94466-235">RELATED LINKS</span></span>

[<span data-ttu-id="94466-236">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="94466-236">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="94466-237">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="94466-237">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
