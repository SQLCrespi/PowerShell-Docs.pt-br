---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 541cceacab7462cc66483a2b75abedcd5c8abb7d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194056"
---
# <span data-ttu-id="59f5a-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="59f5a-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="59f5a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="59f5a-104">SYNOPSIS</span></span>
<span data-ttu-id="59f5a-105">Envia uma solicitação HTTP ou HTTPS para um serviço Web RESTful.</span><span class="sxs-lookup"><span data-stu-id="59f5a-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="59f5a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59f5a-106">SYNTAX</span></span>

### <span data-ttu-id="59f5a-107">StandardMethod (padrão)</span><span class="sxs-lookup"><span data-stu-id="59f5a-107">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="59f5a-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="59f5a-108">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="59f5a-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="59f5a-109">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="59f5a-110">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="59f5a-110">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="59f5a-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="59f5a-111">Description</span></span>

<span data-ttu-id="59f5a-112">O `Invoke-RestMethod` cmdlet envia solicitações HTTP e HTTPS para serviços Web de REST (transferência de estado de reapresentação) que retornam dados estruturados de ricos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-112">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="59f5a-113">O PowerShell formata a resposta com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="59f5a-113">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="59f5a-114">Para um feed RSS ou ATOM, o PowerShell retorna os nós XML de item ou de entrada.</span><span class="sxs-lookup"><span data-stu-id="59f5a-114">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="59f5a-115">Para JavaScript Object Notation (JSON) ou XML, o PowerShell converte ou desserializa o conteúdo em objetos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-115">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="59f5a-116">Este cmdlet é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-116">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="59f5a-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="59f5a-117">EXAMPLES</span></span>

### <span data-ttu-id="59f5a-118">Exemplo 1: obter o feed RSS do PowerShell</span><span class="sxs-lookup"><span data-stu-id="59f5a-118">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="59f5a-119">Este exemplo usa o `Invoke-RestMethod` cmdlet para obter informações do feed RSS do blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59f5a-119">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="59f5a-120">O comando usa o `Format-Table` cmdlet para exibir os valores das propriedades **title** e **pubDate** de cada blog em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="59f5a-120">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

```powershell
Invoke-RestMethod -Uri https://blogs.msdn.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

### <span data-ttu-id="59f5a-121">Exemplo 2: executar uma solicitação POST</span><span class="sxs-lookup"><span data-stu-id="59f5a-121">Example 2: Run a POST request</span></span>

<span data-ttu-id="59f5a-122">Neste exemplo, um usuário é executado `Invoke-RestMethod` para fazer uma solicitação post em um site da intranet na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-122">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential
$Url = "https://server.contoso.com:8089/services/search/jobs/export"
$Body = @{
    search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}
Invoke-RestMethod -Method 'Post' -Uri $url -Credential $Cred -Body $body -OutFile output.csv
```

<span data-ttu-id="59f5a-123">As credenciais são solicitadas e, em seguida, armazenadas em `$Cred` e a URL que será acessada é definida em `$Url` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-123">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="59f5a-124">A `$Body` variável descreve os critérios de pesquisa, especifica o CSV como o modo de saída e especifica um período de tempo para os dados retornados que começam dois dias atrás e termina um dia atrás.</span><span class="sxs-lookup"><span data-stu-id="59f5a-124">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="59f5a-125">A variável Body especifica valores para parâmetros que se aplicam à API REST específica com a qual `Invoke-RestMethod` está se comunicando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-125">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="59f5a-126">O `Invoke-RestMethod` comando é executado com todas as variáveis em vigor, especificando um caminho e um nome de arquivo para o arquivo de saída CSV resultante.</span><span class="sxs-lookup"><span data-stu-id="59f5a-126">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="59f5a-127">Exemplo 3: siga os links de relação</span><span class="sxs-lookup"><span data-stu-id="59f5a-127">Example 3: Follow relation links</span></span>

<span data-ttu-id="59f5a-128">Algumas APIs REST dão suporte à paginação por meio de links de relações por [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="59f5a-128">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="59f5a-129">Em vez de analisar o cabeçalho para obter a URL para a próxima página, você pode fazer com que o cmdlet faça isso para você.</span><span class="sxs-lookup"><span data-stu-id="59f5a-129">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="59f5a-130">Este exemplo retorna as duas primeiras páginas de problemas do repositório GitHub do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59f5a-130">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="59f5a-131">Exemplo 4: multipart/forma simplificada – envio de dados</span><span class="sxs-lookup"><span data-stu-id="59f5a-131">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="59f5a-132">Algumas APIs exigem `multipart/form-data` envios de arquivos e conteúdo misto.</span><span class="sxs-lookup"><span data-stu-id="59f5a-132">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="59f5a-133">Este exemplo demonstra como atualizar o perfil de um usuário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-133">This example demonstrates how to update a user's profile.</span></span>

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-RestMethod -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="59f5a-134">O formulário de perfil requer estes campos:,,,, `firstName` `lastName` `email` `avatar` `birthday` e `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-134">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="59f5a-135">A API está esperando uma imagem para que a PIC do perfil do usuário seja fornecida no `avatar` campo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-135">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="59f5a-136">A API também aceitará `hobbies` que várias entradas sejam enviadas na mesma forma.</span><span class="sxs-lookup"><span data-stu-id="59f5a-136">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="59f5a-137">Ao criar a `$Form` tabela de hash, os nomes de chave são usados como nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-137">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="59f5a-138">Por padrão, os valores da tabela de hash serão convertidos em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="59f5a-138">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="59f5a-139">Se um `System.IO.FileInfo` valor estiver presente, o conteúdo do arquivo será enviado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-139">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="59f5a-140">Se uma coleção, como matrizes ou listas, estiver presente, o campo de formulário será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="59f5a-140">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="59f5a-141">Usando `Get-Item` na `avatar` chave, o `FileInfo` objeto será definido como o valor.</span><span class="sxs-lookup"><span data-stu-id="59f5a-141">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="59f5a-142">O resultado é que os dados de imagem para `jdoe.png` serão enviados.</span><span class="sxs-lookup"><span data-stu-id="59f5a-142">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="59f5a-143">Ao fornecer uma lista à `hobbies` chave, o `hobbies` campo estará presente nos envios uma vez para cada item de lista.</span><span class="sxs-lookup"><span data-stu-id="59f5a-143">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="59f5a-144">Exemplo 5: passar vários cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="59f5a-144">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="59f5a-145">As APIs geralmente exigem cabeçalhos passados para autenticação ou validação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-145">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="59f5a-146">Este exemplo demonstra como passar vários cabeçalhos de um `hash-table` para uma API REST.</span><span class="sxs-lookup"><span data-stu-id="59f5a-146">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="59f5a-147">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="59f5a-147">Parameters</span></span>

### <span data-ttu-id="59f5a-148">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="59f5a-148">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="59f5a-149">Permite o envio de credenciais e segredos em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-149">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="59f5a-150">Por padrão, o fornecimento de **credenciais** ou qualquer opção de **autenticação** com um **URI** que não começa com `https://` resultará em um erro e a solicitação será anulada para impedir a comunicação involuntária de segredos em texto sem formatação em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-150">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="59f5a-151">Para substituir esse comportamento por sua conta e risco, forneça o parâmetro **AllowUnencryptedAuthentication** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-151">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="59f5a-152">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-152">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="59f5a-153">Ele é fornecido apenas para compatibilidade com sistemas herdados que não podem fornecer conexões criptografadas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-153">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="59f5a-154">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="59f5a-154">Use at your own risk.</span></span>

<span data-ttu-id="59f5a-155">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-155">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="59f5a-156">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="59f5a-156">-Authentication</span></span>

<span data-ttu-id="59f5a-157">Especifica o tipo de autenticação explícito a ser usado para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-157">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="59f5a-158">O padrão é **Nenhum** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-158">The default is **None** .</span></span>
<span data-ttu-id="59f5a-159">A **autenticação** não pode ser usada com **UseDefaultCredentials** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-159">**Authentication** can't be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="59f5a-160">Opções de autenticação disponíveis:</span><span class="sxs-lookup"><span data-stu-id="59f5a-160">Available Authentication Options:</span></span>

- <span data-ttu-id="59f5a-161">**Nenhum** : essa é a opção padrão quando a **autenticação** não é fornecida.</span><span class="sxs-lookup"><span data-stu-id="59f5a-161">**None** : This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="59f5a-162">Nenhuma autenticação explícita será usada.</span><span class="sxs-lookup"><span data-stu-id="59f5a-162">No explicit authentication will be used.</span></span>
- <span data-ttu-id="59f5a-163">**Básico** : requer **credencial** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-163">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="59f5a-164">As credenciais serão usadas para enviar um cabeçalho de autenticação básica do RFC 7617 `Authorization: Basic` no formato de `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-164">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="59f5a-165">**Portador** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-165">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="59f5a-166">Enviará e `Authorization: Bearer` o cabeçalho RFC 6750 com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-166">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="59f5a-167">Este é um alias para **OAuth**</span><span class="sxs-lookup"><span data-stu-id="59f5a-167">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="59f5a-168">**OAuth** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-168">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="59f5a-169">Enviará um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-169">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="59f5a-170">Este é um alias para **portador**</span><span class="sxs-lookup"><span data-stu-id="59f5a-170">This is an alias for **Bearer**</span></span>

<span data-ttu-id="59f5a-171">O fornecimento de **autenticação** substituirá todos os `Authorization` cabeçalhos fornecidos aos **cabeçalhos** ou incluídos na sessão da **websession** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-171">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="59f5a-172">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-172">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-173">-Corpo</span><span class="sxs-lookup"><span data-stu-id="59f5a-173">-Body</span></span>

<span data-ttu-id="59f5a-174">Especifica o corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-174">Specifies the body of the request.</span></span> <span data-ttu-id="59f5a-175">O corpo é o conteúdo da solicitação que segue os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-175">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="59f5a-176">Também é possível canalizar um valor de corpo para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-176">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="59f5a-177">O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.</span><span class="sxs-lookup"><span data-stu-id="59f5a-177">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="59f5a-178">Quando a entrada é uma solicitação GET e o corpo é um `IDictionary` (normalmente, uma tabela de hash), o corpo é adicionado ao Uniform Resource Identifier (URI) como parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="59f5a-178">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="59f5a-179">Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão name=value.</span><span class="sxs-lookup"><span data-stu-id="59f5a-179">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="59f5a-180">Quando o corpo é um formulário, ou é a saída de outra `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-180">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="59f5a-181">O parâmetro **Body** também pode aceitar um objeto **System .net. http. MultipartFormDataContent** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-181">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="59f5a-182">Isso facilitará `multipart/form-data` as solicitações.</span><span class="sxs-lookup"><span data-stu-id="59f5a-182">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="59f5a-183">Quando um objeto **MultipartFormDataContent** é fornecido para **o corpo** , todos os cabeçalhos relacionados ao conteúdo fornecidos aos parâmetros **ContentType** , **Headers** ou **websession** serão substituídos pelos cabeçalhos de conteúdo do `MultipartFormDataContent` objeto.</span><span class="sxs-lookup"><span data-stu-id="59f5a-183">When a **MultipartFormDataContent** object is supplied for **Body** , any content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="59f5a-184">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-184">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-185">-Certificado</span><span class="sxs-lookup"><span data-stu-id="59f5a-185">-Certificate</span></span>

<span data-ttu-id="59f5a-186">Especifica o certificado do cliente que é usado para uma solicitação da Web segura.</span><span class="sxs-lookup"><span data-stu-id="59f5a-186">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="59f5a-187">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-187">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="59f5a-188">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de certificado ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="59f5a-188">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="59f5a-189">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="59f5a-189">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-190">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="59f5a-190">-CertificateThumbprint</span></span>

<span data-ttu-id="59f5a-191">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-191">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="59f5a-192">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-192">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="59f5a-193">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-193">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="59f5a-194">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="59f5a-194">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="59f5a-195">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59f5a-195">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="59f5a-196">Atualmente, esse recurso só tem suporte em plataformas de sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="59f5a-196">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="59f5a-197">-ContentType</span><span class="sxs-lookup"><span data-stu-id="59f5a-197">-ContentType</span></span>

<span data-ttu-id="59f5a-198">Especifica o tipo de conteúdo da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-198">Specifies the content type of the web request.</span></span>

<span data-ttu-id="59f5a-199">Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-RestMethod` o definirá o tipo de conteúdo como `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-199">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="59f5a-200">Caso contrário, o tipo de conteúdo não será especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="59f5a-200">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="59f5a-201">**ContentType** será substituído quando um `MultipartFormDataContent` objeto for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-201">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="59f5a-202">-Credential</span><span class="sxs-lookup"><span data-stu-id="59f5a-202">-Credential</span></span>

<span data-ttu-id="59f5a-203">Especifica uma conta de usuário com permissão para enviar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-203">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="59f5a-204">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="59f5a-204">The default is the current user.</span></span>

<span data-ttu-id="59f5a-205">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59f5a-205">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="59f5a-206">A **credencial** pode ser usada sozinha ou em conjunto com determinadas opções de parâmetro de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-206">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="59f5a-207">Quando usado sozinho, ele só fornecerá credenciais para o servidor remoto se o servidor remoto enviar uma solicitação de desafio de autenticação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-207">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="59f5a-208">Quando usado com as opções de **autenticação** , as credenciais serão enviadas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-208">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="59f5a-209">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="59f5a-209">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="59f5a-210">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="59f5a-210">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="59f5a-211">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="59f5a-211">-CustomMethod</span></span>

<span data-ttu-id="59f5a-212">Especifica o método personalizado usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-212">Specifies custom method used for the web request.</span></span> <span data-ttu-id="59f5a-213">Isso pode ser usado com o método de solicitação exigido pelo ponto de extremidade não é uma opção disponível no **método** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-213">This can be used with the Request Method required by the endpoint is not an available option on the **Method** .</span></span> <span data-ttu-id="59f5a-214">O **método** e o **CustomMethod** não podem ser usados juntos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-214">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="59f5a-215">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="59f5a-215">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="59f5a-216">Isso faz uma `TEST` solicitação HTTP para a API.</span><span class="sxs-lookup"><span data-stu-id="59f5a-216">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="59f5a-217">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-217">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-218">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="59f5a-218">-DisableKeepAlive</span></span>

<span data-ttu-id="59f5a-219">Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como false.</span><span class="sxs-lookup"><span data-stu-id="59f5a-219">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="59f5a-220">Por padrão, **KeepAlive** é Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="59f5a-220">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="59f5a-221">**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.</span><span class="sxs-lookup"><span data-stu-id="59f5a-221">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="59f5a-222">-FollowRelLink</span><span class="sxs-lookup"><span data-stu-id="59f5a-222">-FollowRelLink</span></span>

<span data-ttu-id="59f5a-223">Indica que o cmdlet deve seguir os links de relação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-223">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="59f5a-224">Algumas APIs REST dão suporte à paginação por meio de links de relações por [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="59f5a-224">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="59f5a-225">Em vez de analisar o cabeçalho para obter a URL para a próxima página, você pode fazer com que o cmdlet faça isso para você.</span><span class="sxs-lookup"><span data-stu-id="59f5a-225">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="59f5a-226">Para definir quantas vezes seguir os links de relação, use o parâmetro **MaximumFollowRelLink** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-226">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="59f5a-227">Ao usar essa opção, o cmdlet retorna uma coleção de páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="59f5a-227">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="59f5a-228">Cada página de resultados pode conter vários itens de resultado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-228">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="59f5a-229">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-229">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-230">-Formulário</span><span class="sxs-lookup"><span data-stu-id="59f5a-230">-Form</span></span>

<span data-ttu-id="59f5a-231">Converte um dicionário em um `multipart/form-data` envio.</span><span class="sxs-lookup"><span data-stu-id="59f5a-231">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="59f5a-232">O **formulário** não pode ser usado com o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-232">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="59f5a-233">Se **ContentType** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-233">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="59f5a-234">As chaves do dicionário serão usadas como os nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-234">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="59f5a-235">Por padrão, os valores de formulário serão convertidos em valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="59f5a-235">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="59f5a-236">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-236">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="59f5a-237">O nome do arquivo será enviado como o `filename` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-237">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="59f5a-238">O MIME será definido como `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-238">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="59f5a-239">`Get-Item` pode ser usado para simplificar o fornecimento do objeto **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-239">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="59f5a-240">Se o valor for um tipo de coleção, como uma matriz ou lista, o campo para será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="59f5a-240">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="59f5a-241">Os valores da lista serão tratados como cadeias de caracteres por padrão.</span><span class="sxs-lookup"><span data-stu-id="59f5a-241">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="59f5a-242">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-242">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="59f5a-243">Não há suporte para coleções aninhadas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-243">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="59f5a-244">No exemplo acima, o `tags` campo será fornecido três vezes no formulário, uma vez para cada `Vacation` , `Italy` e `2017` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-244">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="59f5a-245">O `pictures` campo também será enviado uma vez para cada arquivo na `2017-Italy` pasta.</span><span class="sxs-lookup"><span data-stu-id="59f5a-245">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="59f5a-246">O conteúdo binário dos arquivos nessa pasta será enviado como os valores.</span><span class="sxs-lookup"><span data-stu-id="59f5a-246">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="59f5a-247">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-247">This feature was added in PowerShell 6.1.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-248">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="59f5a-248">-Headers</span></span>

<span data-ttu-id="59f5a-249">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-249">Specifies the headers of the web request.</span></span> <span data-ttu-id="59f5a-250">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-250">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="59f5a-251">Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-251">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="59f5a-252">Você não pode usar esse parâmetro para especificar `User-Agent` cabeçalhos de cookie ou.</span><span class="sxs-lookup"><span data-stu-id="59f5a-252">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="59f5a-253">Cabeçalhos relacionados ao conteúdo, como, `Content-Type` serão substituídos quando um `MultipartFormDataContent` objeto for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-253">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-254">-InFile</span><span class="sxs-lookup"><span data-stu-id="59f5a-254">-InFile</span></span>

<span data-ttu-id="59f5a-255">Obtém o conteúdo da solicitação da Web de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-255">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="59f5a-256">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-256">Enter a path and file name.</span></span> <span data-ttu-id="59f5a-257">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="59f5a-257">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="59f5a-258">-MaximumFollowRelLink</span><span class="sxs-lookup"><span data-stu-id="59f5a-258">-MaximumFollowRelLink</span></span>

<span data-ttu-id="59f5a-259">Especifica quantas vezes seguir os links de relação se **FollowRelLink** for usado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-259">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="59f5a-260">Um valor menor pode ser necessário se a API REST for limitada devido a muitas solicitações.</span><span class="sxs-lookup"><span data-stu-id="59f5a-260">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="59f5a-261">O valor padrão é `[Int32]::MaxValue`.</span><span class="sxs-lookup"><span data-stu-id="59f5a-261">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="59f5a-262">Um valor de 0 (zero) impede os links de relação A seguir.</span><span class="sxs-lookup"><span data-stu-id="59f5a-262">A value of 0 (zero) prevents following relation links.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: Int32.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-263">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="59f5a-263">-MaximumRedirection</span></span>

<span data-ttu-id="59f5a-264">Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="59f5a-264">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="59f5a-265">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="59f5a-265">The default value is 5.</span></span> <span data-ttu-id="59f5a-266">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="59f5a-266">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-267">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="59f5a-267">-MaximumRetryCount</span></span>

<span data-ttu-id="59f5a-268">Especifica quantas vezes o PowerShell tenta novamente uma conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-268">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="59f5a-269">Consulte também o parâmetro **RetryIntervalSec** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="59f5a-269">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-270">-Método</span><span class="sxs-lookup"><span data-stu-id="59f5a-270">-Method</span></span>

<span data-ttu-id="59f5a-271">Especifica o método usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-271">Specifies the method used for the web request.</span></span> <span data-ttu-id="59f5a-272">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="59f5a-272">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="59f5a-273">Padrão</span><span class="sxs-lookup"><span data-stu-id="59f5a-273">Default</span></span>
- <span data-ttu-id="59f5a-274">Excluir</span><span class="sxs-lookup"><span data-stu-id="59f5a-274">Delete</span></span>
- <span data-ttu-id="59f5a-275">Obter</span><span class="sxs-lookup"><span data-stu-id="59f5a-275">Get</span></span>
- <span data-ttu-id="59f5a-276">Head</span><span class="sxs-lookup"><span data-stu-id="59f5a-276">Head</span></span>
- <span data-ttu-id="59f5a-277">Mesclar</span><span class="sxs-lookup"><span data-stu-id="59f5a-277">Merge</span></span>
- <span data-ttu-id="59f5a-278">Opções</span><span class="sxs-lookup"><span data-stu-id="59f5a-278">Options</span></span>
- <span data-ttu-id="59f5a-279">Patch</span><span class="sxs-lookup"><span data-stu-id="59f5a-279">Patch</span></span>
- <span data-ttu-id="59f5a-280">Postar</span><span class="sxs-lookup"><span data-stu-id="59f5a-280">Post</span></span>
- <span data-ttu-id="59f5a-281">Put</span><span class="sxs-lookup"><span data-stu-id="59f5a-281">Put</span></span>
- <span data-ttu-id="59f5a-282">Trace</span><span class="sxs-lookup"><span data-stu-id="59f5a-282">Trace</span></span>

<span data-ttu-id="59f5a-283">O parâmetro **CustomMethod** pode ser usado para métodos de solicitação não listados acima.</span><span class="sxs-lookup"><span data-stu-id="59f5a-283">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-284">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="59f5a-284">-NoProxy</span></span>

<span data-ttu-id="59f5a-285">Indica que o cmdlet não usará um proxy para acessar o destino.</span><span class="sxs-lookup"><span data-stu-id="59f5a-285">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="59f5a-286">Quando você precisar ignorar o proxy configurado no Internet Explorer ou um proxy especificado no ambiente, use essa opção.</span><span class="sxs-lookup"><span data-stu-id="59f5a-286">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="59f5a-287">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-287">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-288">-Outfile</span><span class="sxs-lookup"><span data-stu-id="59f5a-288">-OutFile</span></span>

<span data-ttu-id="59f5a-289">Salva o corpo da resposta no arquivo de saída especificado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-289">Saves the response body in the specified output file.</span></span> <span data-ttu-id="59f5a-290">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-290">Enter a path and file name.</span></span> <span data-ttu-id="59f5a-291">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="59f5a-291">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="59f5a-292">Por padrão, `Invoke-RestMethod` o retorna os resultados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="59f5a-292">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="59f5a-293">Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-293">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="59f5a-294">-PassThru</span><span class="sxs-lookup"><span data-stu-id="59f5a-294">-PassThru</span></span>

<span data-ttu-id="59f5a-295">Retorna os resultados, além de gravá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-295">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="59f5a-296">Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-296">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-297">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="59f5a-297">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="59f5a-298">Indica que o cmdlet deve preservar o `Authorization` cabeçalho, quando presente, entre redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-298">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="59f5a-299">Por padrão, o cmdlet retira o `Authorization` cabeçalho antes de redirecionar.</span><span class="sxs-lookup"><span data-stu-id="59f5a-299">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="59f5a-300">A especificação desse parâmetro desabilita essa lógica nos casos em que o cabeçalho precisa ser enviado para o local de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="59f5a-300">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="59f5a-301">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-301">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="59f5a-302">-Proxy</span><span class="sxs-lookup"><span data-stu-id="59f5a-302">-Proxy</span></span>

<span data-ttu-id="59f5a-303">Usa um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="59f5a-303">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="59f5a-304">Insira o Uniform Resource Identifier (URI) de um servidor de proxy de rede.</span><span class="sxs-lookup"><span data-stu-id="59f5a-304">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="59f5a-305">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-305">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-306">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="59f5a-306">-ProxyCredential</span></span>

<span data-ttu-id="59f5a-307">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-307">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="59f5a-308">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="59f5a-308">The default is the current user.</span></span>

<span data-ttu-id="59f5a-309">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , **User@Domain.Com** ou insira um `PSCredential` objeto, como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59f5a-309">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="59f5a-310">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-310">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="59f5a-311">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-311">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-312">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="59f5a-312">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="59f5a-313">Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-313">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="59f5a-314">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="59f5a-315">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-316">-ResponseHeadersVariable</span><span class="sxs-lookup"><span data-stu-id="59f5a-316">-ResponseHeadersVariable</span></span>

<span data-ttu-id="59f5a-317">Cria um dicionário de cabeçalhos de resposta e o salva no valor da variável especificada.</span><span class="sxs-lookup"><span data-stu-id="59f5a-317">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="59f5a-318">As chaves do dicionário conterão os nomes de campo do cabeçalho de resposta retornado pelo servidor Web e os valores serão os respectivos valores de campo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-318">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="59f5a-319">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-319">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RHV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-320">-Retomar</span><span class="sxs-lookup"><span data-stu-id="59f5a-320">-Resume</span></span>

<span data-ttu-id="59f5a-321">Executa uma tentativa de melhor esforço para retomar o download de um arquivo parcial.</span><span class="sxs-lookup"><span data-stu-id="59f5a-321">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="59f5a-322">O parâmetro **resume** requer o parâmetro **outfile** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-322">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="59f5a-323">**Retomar** opera apenas no tamanho do arquivo local e no arquivo remoto e não executa nenhuma outra validação que o arquivo local e o arquivo remoto sejam os mesmos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-323">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="59f5a-324">Se o tamanho do arquivo local for menor que o tamanho do arquivo remoto, o cmdlet tentará retomar o download do arquivo e acrescentará os bytes restantes ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="59f5a-324">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="59f5a-325">Se o tamanho do arquivo local for igual ao tamanho do arquivo remoto, nenhuma ação será executada e o cmdlet assumirá que o download já foi concluído.</span><span class="sxs-lookup"><span data-stu-id="59f5a-325">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="59f5a-326">Se o tamanho do arquivo local for maior que o tamanho do arquivo remoto, o arquivo local será substituído e todo o arquivo remoto será completamente baixado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-326">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="59f5a-327">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-327">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="59f5a-328">Se o servidor remoto não oferecer suporte a retomada de download, o arquivo local será substituído e todo o arquivo remoto será completamente baixado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-328">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="59f5a-329">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-329">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="59f5a-330">Se o arquivo local não existir, o arquivo local será criado e todo o arquivo remoto será baixado completamente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-330">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="59f5a-331">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-331">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="59f5a-332">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-332">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="59f5a-333">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="59f5a-333">-RetryIntervalSec</span></span>

<span data-ttu-id="59f5a-334">Especifica o intervalo entre as repetições para a conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-334">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="59f5a-335">Consulte também o parâmetro **MaximumRetryCount** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="59f5a-335">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-336">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="59f5a-336">-SessionVariable</span></span>

<span data-ttu-id="59f5a-337">Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.</span><span class="sxs-lookup"><span data-stu-id="59f5a-337">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="59f5a-338">Insira um nome de variável sem o símbolo de cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="59f5a-338">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="59f5a-339">Quando você especifica uma variável de sessão, `Invoke-RestMethod` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59f5a-339">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="59f5a-340">Você pode usar a variável na sessão, assim que o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="59f5a-340">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="59f5a-341">Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-341">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="59f5a-342">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-342">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="59f5a-343">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-343">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="59f5a-344">Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-344">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="59f5a-345">O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="59f5a-345">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="59f5a-346">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-346">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="59f5a-347">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-347">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="59f5a-348">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-348">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-349">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="59f5a-349">-SkipCertificateCheck</span></span>

<span data-ttu-id="59f5a-350">Ignora as verificações de validação de certificado que incluem todas as validações, como expiração, revogação, autoridade raiz confiável etc.</span><span class="sxs-lookup"><span data-stu-id="59f5a-350">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="59f5a-351">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-351">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="59f5a-352">Essa opção destina-se apenas a ser usada em hosts conhecidos usando um certificado autoassinado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="59f5a-352">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="59f5a-353">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="59f5a-353">Use at your own risk.</span></span>

<span data-ttu-id="59f5a-354">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-354">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="59f5a-355">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="59f5a-355">-SkipHeaderValidation</span></span>

<span data-ttu-id="59f5a-356">Indica que o cmdlet deve adicionar cabeçalhos à solicitação sem validação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-356">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="59f5a-357">Essa opção deve ser usada para sites que exigem valores de cabeçalho que não estão em conformidade com os padrões.</span><span class="sxs-lookup"><span data-stu-id="59f5a-357">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="59f5a-358">A especificação dessa opção desabilita a validação para permitir que o valor seja passado desmarcado.</span><span class="sxs-lookup"><span data-stu-id="59f5a-358">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="59f5a-359">Quando especificado, todos os cabeçalhos são adicionados sem validação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-359">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="59f5a-360">Isso desabilitará a validação para valores passados para os parâmetros **ContentType** , **Headers** e **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-360">This will disable validation for values passed to the **ContentType** , **Headers** , and **UserAgent** parameters.</span></span>

<span data-ttu-id="59f5a-361">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-361">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="59f5a-362">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="59f5a-362">-SslProtocol</span></span>

<span data-ttu-id="59f5a-363">Define os protocolos SSL/TLS que são permitidos para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-363">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="59f5a-364">Por padrão, todos os protocolos SSL/TLS com suporte do sistema são permitidos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-364">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="59f5a-365">O **SslProtocol** permite limitar a protocolos específicos para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="59f5a-365">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="59f5a-366">**SslProtocol** usa o `WebSslProtocol` sinalizador enum.</span><span class="sxs-lookup"><span data-stu-id="59f5a-366">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="59f5a-367">É possível fornecer mais de um protocolo usando a notação de sinalizador ou combinando várias `WebSslProtocol` opções com o `-bor` , no entanto, não há suporte para o fornecimento de vários protocolos em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-367">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="59f5a-368">Em plataformas não Windows, talvez não seja possível fornecer `'Tls, Tls12'` uma opção.</span><span class="sxs-lookup"><span data-stu-id="59f5a-368">On non-Windows platforms it may not be possible to supply `'Tls, Tls12'` as an option.</span></span>

<span data-ttu-id="59f5a-369">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-369">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-370">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="59f5a-370">-TimeoutSec</span></span>

<span data-ttu-id="59f5a-371">Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="59f5a-371">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="59f5a-372">O valor padrão, 0, especifica um tempo limite indefinido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-372">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="59f5a-373">Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="59f5a-373">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-374">-Token</span><span class="sxs-lookup"><span data-stu-id="59f5a-374">-Token</span></span>

<span data-ttu-id="59f5a-375">O token de portador ou OAuth a ser incluído na solicitação.</span><span class="sxs-lookup"><span data-stu-id="59f5a-375">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="59f5a-376">O **token** é exigido por determinadas opções de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-376">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="59f5a-377">Ele não pode ser usado de forma independente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-377">It can't be used independently.</span></span>

<span data-ttu-id="59f5a-378">O **token** usa um `SecureString` que contém o token.</span><span class="sxs-lookup"><span data-stu-id="59f5a-378">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="59f5a-379">Para fornecer o token, use manualmente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="59f5a-379">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="59f5a-380">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="59f5a-380">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-381">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="59f5a-381">-TransferEncoding</span></span>

<span data-ttu-id="59f5a-382">Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência.</span><span class="sxs-lookup"><span data-stu-id="59f5a-382">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="59f5a-383">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="59f5a-383">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="59f5a-384">Em bloco</span><span class="sxs-lookup"><span data-stu-id="59f5a-384">Chunked</span></span>
- <span data-ttu-id="59f5a-385">Compactar</span><span class="sxs-lookup"><span data-stu-id="59f5a-385">Compress</span></span>
- <span data-ttu-id="59f5a-386">Desinflar</span><span class="sxs-lookup"><span data-stu-id="59f5a-386">Deflate</span></span>
- <span data-ttu-id="59f5a-387">GZip</span><span class="sxs-lookup"><span data-stu-id="59f5a-387">GZip</span></span>
- <span data-ttu-id="59f5a-388">Identidade</span><span class="sxs-lookup"><span data-stu-id="59f5a-388">Identity</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-389">-URI</span><span class="sxs-lookup"><span data-stu-id="59f5a-389">-Uri</span></span>

<span data-ttu-id="59f5a-390">Especifica o Uniform Resource Identifier (URI) do recurso da Internet para o qual a solicitação da Web é enviada.</span><span class="sxs-lookup"><span data-stu-id="59f5a-390">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="59f5a-391">Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.</span><span class="sxs-lookup"><span data-stu-id="59f5a-391">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="59f5a-392">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-392">This parameter is required.</span></span> <span data-ttu-id="59f5a-393">O nome do parâmetro ( **URI** ) é opcional.</span><span class="sxs-lookup"><span data-stu-id="59f5a-393">The parameter name ( **Uri** ) is optional.</span></span>

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-394">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="59f5a-394">-UseBasicParsing</span></span>

<span data-ttu-id="59f5a-395">Esse parâmetro foi preterido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-395">This parameter has been deprecated.</span></span> <span data-ttu-id="59f5a-396">A partir do PowerShell 6.0.0, todas as solicitações da Web usam somente a análise básica.</span><span class="sxs-lookup"><span data-stu-id="59f5a-396">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="59f5a-397">Esse parâmetro é incluído somente para compatibilidade com versões anteriores e qualquer uso dele não terá nenhum efeito sobre a operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59f5a-397">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-398">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="59f5a-398">-UseDefaultCredentials</span></span>

<span data-ttu-id="59f5a-399">Indica que o cmdlet usa as credenciais do usuário atual para enviar a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-399">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="59f5a-400">Isso não pode ser usado com **autenticação** ou **credencial** e pode não ter suporte em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-400">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-401">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="59f5a-401">-UserAgent</span></span>

<span data-ttu-id="59f5a-402">Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-402">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="59f5a-403">O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` com pequenas variações para cada sistema operacional e plataforma.</span><span class="sxs-lookup"><span data-stu-id="59f5a-403">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="59f5a-404">Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari.</span><span class="sxs-lookup"><span data-stu-id="59f5a-404">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-405">-Websession</span><span class="sxs-lookup"><span data-stu-id="59f5a-405">-WebSession</span></span>

<span data-ttu-id="59f5a-406">Especifica uma sessão de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-406">Specifies a web request session.</span></span> <span data-ttu-id="59f5a-407">Insira o nome da variável, incluindo o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="59f5a-407">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="59f5a-408">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-408">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="59f5a-409">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-409">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="59f5a-410">Cabeçalhos relacionados ao conteúdo, como `Content-Type` , também serão substituídos quando um objeto **MultipartFormDataContent** for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-410">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="59f5a-411">Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="59f5a-411">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="59f5a-412">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="59f5a-412">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="59f5a-413">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="59f5a-413">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="59f5a-414">Para criar uma sessão de solicitação da Web, insira um nome de variável, sem um sinal de cifrão, no valor do parâmetro **SessionVariable** de um `Invoke-RestMethod` comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-414">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="59f5a-415">`Invoke-RestMethod` cria a sessão e salva-a na variável.</span><span class="sxs-lookup"><span data-stu-id="59f5a-415">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="59f5a-416">Em comandos posteriores, use a variável como o valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="59f5a-416">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="59f5a-417">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="59f5a-417">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59f5a-418">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59f5a-418">CommonParameters</span></span>

<span data-ttu-id="59f5a-419">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59f5a-419">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59f5a-420">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59f5a-420">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59f5a-421">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="59f5a-421">INPUTS</span></span>

### <span data-ttu-id="59f5a-422">System.Object</span><span class="sxs-lookup"><span data-stu-id="59f5a-422">System.Object</span></span>

<span data-ttu-id="59f5a-423">Você pode canalizar o corpo de uma solicitação da Web para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="59f5a-423">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="59f5a-424">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="59f5a-424">OUTPUTS</span></span>

### <span data-ttu-id="59f5a-425">System. Int64, System. String, System.Xml.Xmldocumento</span><span class="sxs-lookup"><span data-stu-id="59f5a-425">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="59f5a-426">A saída do cmdlet depende do formato do conteúdo que é obtido.</span><span class="sxs-lookup"><span data-stu-id="59f5a-426">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="59f5a-427">PSObject</span><span class="sxs-lookup"><span data-stu-id="59f5a-427">PSObject</span></span>

<span data-ttu-id="59f5a-428">Se a solicitação retornar cadeias de caracteres JSON, `Invoke-RestMethod` retornará um **PSObject** que representa as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="59f5a-428">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="59f5a-429">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="59f5a-429">NOTES</span></span>

<span data-ttu-id="59f5a-430">Alguns recursos podem não estar disponíveis em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="59f5a-430">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="59f5a-431">Para obter mais informações sobre como o .NET fornece serviços de proxy para o PowerShell, consulte [acessando a Internet por meio de um proxy](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy).</span><span class="sxs-lookup"><span data-stu-id="59f5a-431">For more information about how .NET provides proxy services to PowerShell, see [Accessing the Internet Through a Proxy](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy).</span></span>

## <span data-ttu-id="59f5a-432">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="59f5a-432">RELATED LINKS</span></span>

[<span data-ttu-id="59f5a-433">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="59f5a-433">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="59f5a-434">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="59f5a-434">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="59f5a-435">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="59f5a-435">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
