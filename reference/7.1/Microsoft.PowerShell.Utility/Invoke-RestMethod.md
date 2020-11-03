---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: d00885d0911d20dee0e5c498e5e339af4fa39a34
ms.sourcegitcommit: eaac7af89171379df2e20464ebee9fc7e7d7674a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2020
ms.locfileid: "93195298"
---
# <span data-ttu-id="2f09d-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="2f09d-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="2f09d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2f09d-104">SYNOPSIS</span></span>
<span data-ttu-id="2f09d-105">Envia uma solicitação HTTP ou HTTPS para um serviço Web RESTful.</span><span class="sxs-lookup"><span data-stu-id="2f09d-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="2f09d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f09d-106">SYNTAX</span></span>

### <span data-ttu-id="2f09d-107">StandardMethod (padrão)</span><span class="sxs-lookup"><span data-stu-id="2f09d-107">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2f09d-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="2f09d-108">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2f09d-109">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="2f09d-109">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2f09d-110">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="2f09d-110">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="2f09d-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="2f09d-111">Description</span></span>

<span data-ttu-id="2f09d-112">O `Invoke-RestMethod` cmdlet envia solicitações HTTP e HTTPS para serviços Web de REST (transferência de estado de reapresentação) que retornam dados estruturados de ricos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-112">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="2f09d-113">O PowerShell formata a resposta com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="2f09d-113">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="2f09d-114">Para um feed RSS ou ATOM, o PowerShell retorna os nós XML de item ou de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f09d-114">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="2f09d-115">Para JavaScript Object Notation (JSON) ou XML, o PowerShell converte ou desserializa o conteúdo em objetos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-115">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="2f09d-116">Este cmdlet é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-116">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="2f09d-117">A partir do PowerShell 7,0, `Invoke-RestMethod` dá suporte à configuração de proxy definida por variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-117">Beginning in PowerShell 7.0, `Invoke-RestMethod` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="2f09d-118">Consulte a seção [observações](#notes) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-118">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="2f09d-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2f09d-119">EXAMPLES</span></span>

### <span data-ttu-id="2f09d-120">Exemplo 1: obter o feed RSS do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f09d-120">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="2f09d-121">Este exemplo usa o `Invoke-RestMethod` cmdlet para obter informações do feed RSS do blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f09d-121">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="2f09d-122">O comando usa o `Format-Table` cmdlet para exibir os valores das propriedades **title** e **pubDate** de cada blog em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2f09d-122">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

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

### <span data-ttu-id="2f09d-123">Exemplo 2: executar uma solicitação POST</span><span class="sxs-lookup"><span data-stu-id="2f09d-123">Example 2: Run a POST request</span></span>

<span data-ttu-id="2f09d-124">Neste exemplo, um usuário é executado `Invoke-RestMethod` para fazer uma solicitação post em um site da intranet na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-124">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

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

<span data-ttu-id="2f09d-125">As credenciais são solicitadas e, em seguida, armazenadas em `$Cred` e a URL que será acessada é definida em `$Url` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-125">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="2f09d-126">A `$Body` variável descreve os critérios de pesquisa, especifica o CSV como o modo de saída e especifica um período de tempo para os dados retornados que começam dois dias atrás e termina um dia atrás.</span><span class="sxs-lookup"><span data-stu-id="2f09d-126">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="2f09d-127">A variável Body especifica valores para parâmetros que se aplicam à API REST específica com a qual `Invoke-RestMethod` está se comunicando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-127">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="2f09d-128">O `Invoke-RestMethod` comando é executado com todas as variáveis em vigor, especificando um caminho e um nome de arquivo para o arquivo de saída CSV resultante.</span><span class="sxs-lookup"><span data-stu-id="2f09d-128">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="2f09d-129">Exemplo 3: siga os links de relação</span><span class="sxs-lookup"><span data-stu-id="2f09d-129">Example 3: Follow relation links</span></span>

<span data-ttu-id="2f09d-130">Algumas APIs REST dão suporte à paginação por meio de links de relações por [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="2f09d-130">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="2f09d-131">Em vez de analisar o cabeçalho para obter a URL para a próxima página, você pode fazer com que o cmdlet faça isso para você.</span><span class="sxs-lookup"><span data-stu-id="2f09d-131">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="2f09d-132">Este exemplo retorna as duas primeiras páginas de problemas do repositório GitHub do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f09d-132">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="2f09d-133">Exemplo 4: multipart/forma simplificada – envio de dados</span><span class="sxs-lookup"><span data-stu-id="2f09d-133">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="2f09d-134">Algumas APIs exigem `multipart/form-data` envios de arquivos e conteúdo misto.</span><span class="sxs-lookup"><span data-stu-id="2f09d-134">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="2f09d-135">Este exemplo demonstra como atualizar o perfil de um usuário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-135">This example demonstrates how to update a user's profile.</span></span>

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

<span data-ttu-id="2f09d-136">O formulário de perfil requer estes campos:,,,, `firstName` `lastName` `email` `avatar` `birthday` e `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-136">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="2f09d-137">A API está esperando uma imagem para que a PIC do perfil do usuário seja fornecida no `avatar` campo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-137">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="2f09d-138">A API também aceitará `hobbies` que várias entradas sejam enviadas na mesma forma.</span><span class="sxs-lookup"><span data-stu-id="2f09d-138">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="2f09d-139">Ao criar a `$Form` tabela de hash, os nomes de chave são usados como nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-139">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="2f09d-140">Por padrão, os valores da tabela de hash serão convertidos em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2f09d-140">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="2f09d-141">Se um `System.IO.FileInfo` valor estiver presente, o conteúdo do arquivo será enviado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-141">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="2f09d-142">Se uma coleção, como matrizes ou listas, estiver presente, o campo de formulário será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="2f09d-142">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="2f09d-143">Usando `Get-Item` na `avatar` chave, o `FileInfo` objeto será definido como o valor.</span><span class="sxs-lookup"><span data-stu-id="2f09d-143">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="2f09d-144">O resultado é que os dados de imagem para `jdoe.png` serão enviados.</span><span class="sxs-lookup"><span data-stu-id="2f09d-144">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="2f09d-145">Ao fornecer uma lista à `hobbies` chave, o `hobbies` campo estará presente nos envios uma vez para cada item de lista.</span><span class="sxs-lookup"><span data-stu-id="2f09d-145">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="2f09d-146">Exemplo 5: passar vários cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="2f09d-146">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="2f09d-147">As APIs geralmente exigem cabeçalhos passados para autenticação ou validação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-147">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="2f09d-148">Este exemplo demonstra como passar vários cabeçalhos de um `hash-table` para uma API REST.</span><span class="sxs-lookup"><span data-stu-id="2f09d-148">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="2f09d-149">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2f09d-149">Parameters</span></span>

### <span data-ttu-id="2f09d-150">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="2f09d-150">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="2f09d-151">Permite o envio de credenciais e segredos em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-151">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="2f09d-152">Por padrão, o fornecimento de **credenciais** ou qualquer opção de **autenticação** com um **URI** que não começa com `https://` resultará em um erro e a solicitação será anulada para impedir a comunicação involuntária de segredos em texto sem formatação em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-152">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="2f09d-153">Para substituir esse comportamento por sua conta e risco, forneça o parâmetro **AllowUnencryptedAuthentication** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-153">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="2f09d-154">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-154">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="2f09d-155">Ele é fornecido apenas para compatibilidade com sistemas herdados que não podem fornecer conexões criptografadas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-155">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="2f09d-156">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="2f09d-156">Use at your own risk.</span></span>

<span data-ttu-id="2f09d-157">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-157">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-158">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="2f09d-158">-Authentication</span></span>

<span data-ttu-id="2f09d-159">Especifica o tipo de autenticação explícito a ser usado para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-159">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="2f09d-160">O padrão é **Nenhum** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-160">The default is **None** .</span></span>
<span data-ttu-id="2f09d-161">A **autenticação** não pode ser usada com **UseDefaultCredentials** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-161">**Authentication** can't be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="2f09d-162">Opções de autenticação disponíveis:</span><span class="sxs-lookup"><span data-stu-id="2f09d-162">Available Authentication Options:</span></span>

- <span data-ttu-id="2f09d-163">**Nenhum** : essa é a opção padrão quando a **autenticação** não é fornecida.</span><span class="sxs-lookup"><span data-stu-id="2f09d-163">**None** : This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="2f09d-164">Nenhuma autenticação explícita será usada.</span><span class="sxs-lookup"><span data-stu-id="2f09d-164">No explicit authentication will be used.</span></span>
- <span data-ttu-id="2f09d-165">**Básico** : requer **credencial** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-165">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="2f09d-166">As credenciais serão usadas para enviar um cabeçalho de autenticação básica do RFC 7617 `Authorization: Basic` no formato de `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-166">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="2f09d-167">**Portador** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-167">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="2f09d-168">Enviará e `Authorization: Bearer` o cabeçalho RFC 6750 com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-168">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="2f09d-169">Este é um alias para **OAuth**</span><span class="sxs-lookup"><span data-stu-id="2f09d-169">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="2f09d-170">**OAuth** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-170">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="2f09d-171">Enviará um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-171">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="2f09d-172">Este é um alias para **portador**</span><span class="sxs-lookup"><span data-stu-id="2f09d-172">This is an alias for **Bearer**</span></span>

<span data-ttu-id="2f09d-173">O fornecimento de **autenticação** substituirá todos os `Authorization` cabeçalhos fornecidos aos **cabeçalhos** ou incluídos na sessão da **websession** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-173">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="2f09d-174">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-174">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-175">-Corpo</span><span class="sxs-lookup"><span data-stu-id="2f09d-175">-Body</span></span>

<span data-ttu-id="2f09d-176">Especifica o corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-176">Specifies the body of the request.</span></span> <span data-ttu-id="2f09d-177">O corpo é o conteúdo da solicitação que segue os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-177">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="2f09d-178">Também é possível canalizar um valor de corpo para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-178">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="2f09d-179">O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.</span><span class="sxs-lookup"><span data-stu-id="2f09d-179">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="2f09d-180">Quando a entrada é uma solicitação GET e o corpo é um `IDictionary` (normalmente, uma tabela de hash), o corpo é adicionado ao Uniform Resource Identifier (URI) como parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="2f09d-180">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="2f09d-181">Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão name=value.</span><span class="sxs-lookup"><span data-stu-id="2f09d-181">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="2f09d-182">Quando o corpo é um formulário, ou é a saída de outra `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-182">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="2f09d-183">O parâmetro **Body** também pode aceitar um objeto **System .net. http. MultipartFormDataContent** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-183">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="2f09d-184">Isso facilitará `multipart/form-data` as solicitações.</span><span class="sxs-lookup"><span data-stu-id="2f09d-184">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="2f09d-185">Quando um objeto **MultipartFormDataContent** é fornecido para **o corpo** , todos os cabeçalhos relacionados ao conteúdo fornecidos aos parâmetros **ContentType** , **Headers** ou **websession** serão substituídos pelos cabeçalhos de conteúdo do `MultipartFormDataContent` objeto.</span><span class="sxs-lookup"><span data-stu-id="2f09d-185">When a **MultipartFormDataContent** object is supplied for **Body** , any content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="2f09d-186">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-186">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-187">-Certificado</span><span class="sxs-lookup"><span data-stu-id="2f09d-187">-Certificate</span></span>

<span data-ttu-id="2f09d-188">Especifica o certificado do cliente que é usado para uma solicitação da Web segura.</span><span class="sxs-lookup"><span data-stu-id="2f09d-188">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="2f09d-189">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-189">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="2f09d-190">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de certificado ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="2f09d-190">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="2f09d-191">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="2f09d-191">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="2f09d-192">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="2f09d-192">-CertificateThumbprint</span></span>

<span data-ttu-id="2f09d-193">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-193">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="2f09d-194">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-194">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="2f09d-195">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-195">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="2f09d-196">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="2f09d-196">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="2f09d-197">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f09d-197">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="2f09d-198">Atualmente, esse recurso só tem suporte em plataformas de sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="2f09d-198">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="2f09d-199">-ContentType</span><span class="sxs-lookup"><span data-stu-id="2f09d-199">-ContentType</span></span>

<span data-ttu-id="2f09d-200">Especifica o tipo de conteúdo da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-200">Specifies the content type of the web request.</span></span>

<span data-ttu-id="2f09d-201">Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-RestMethod` o definirá o tipo de conteúdo como `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-201">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="2f09d-202">Caso contrário, o tipo de conteúdo não será especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="2f09d-202">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="2f09d-203">**ContentType** será substituído quando um `MultipartFormDataContent` objeto for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-203">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="2f09d-204">-Credential</span><span class="sxs-lookup"><span data-stu-id="2f09d-204">-Credential</span></span>

<span data-ttu-id="2f09d-205">Especifica uma conta de usuário com permissão para enviar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-205">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="2f09d-206">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2f09d-206">The default is the current user.</span></span>

<span data-ttu-id="2f09d-207">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f09d-207">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="2f09d-208">A **credencial** pode ser usada sozinha ou em conjunto com determinadas opções de parâmetro de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-208">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="2f09d-209">Quando usado sozinho, ele só fornecerá credenciais para o servidor remoto se o servidor remoto enviar uma solicitação de desafio de autenticação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-209">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="2f09d-210">Quando usado com as opções de **autenticação** , as credenciais serão enviadas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-210">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="2f09d-211">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="2f09d-211">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2f09d-212">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2f09d-212">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2f09d-213">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="2f09d-213">-CustomMethod</span></span>

<span data-ttu-id="2f09d-214">Especifica o método personalizado usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-214">Specifies custom method used for the web request.</span></span> <span data-ttu-id="2f09d-215">Isso pode ser usado com o método de solicitação exigido pelo ponto de extremidade não é uma opção disponível no **método** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-215">This can be used with the Request Method required by the endpoint is not an available option on the **Method** .</span></span> <span data-ttu-id="2f09d-216">O **método** e o **CustomMethod** não podem ser usados juntos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-216">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="2f09d-217">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="2f09d-217">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="2f09d-218">Isso faz uma `TEST` solicitação HTTP para a API.</span><span class="sxs-lookup"><span data-stu-id="2f09d-218">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="2f09d-219">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-219">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-220">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="2f09d-220">-DisableKeepAlive</span></span>

<span data-ttu-id="2f09d-221">Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como false.</span><span class="sxs-lookup"><span data-stu-id="2f09d-221">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="2f09d-222">Por padrão, **KeepAlive** é Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="2f09d-222">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="2f09d-223">**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.</span><span class="sxs-lookup"><span data-stu-id="2f09d-223">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="2f09d-224">-FollowRelLink</span><span class="sxs-lookup"><span data-stu-id="2f09d-224">-FollowRelLink</span></span>

<span data-ttu-id="2f09d-225">Indica que o cmdlet deve seguir os links de relação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-225">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="2f09d-226">Algumas APIs REST dão suporte à paginação por meio de links de relações por [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="2f09d-226">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="2f09d-227">Em vez de analisar o cabeçalho para obter a URL para a próxima página, você pode fazer com que o cmdlet faça isso para você.</span><span class="sxs-lookup"><span data-stu-id="2f09d-227">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="2f09d-228">Para definir quantas vezes seguir os links de relação, use o parâmetro **MaximumFollowRelLink** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-228">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="2f09d-229">Ao usar essa opção, o cmdlet retorna uma coleção de páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="2f09d-229">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="2f09d-230">Cada página de resultados pode conter vários itens de resultado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-230">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="2f09d-231">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-231">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-232">-Formulário</span><span class="sxs-lookup"><span data-stu-id="2f09d-232">-Form</span></span>

<span data-ttu-id="2f09d-233">Converte um dicionário em um `multipart/form-data` envio.</span><span class="sxs-lookup"><span data-stu-id="2f09d-233">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="2f09d-234">O **formulário** não pode ser usado com o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-234">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="2f09d-235">Se **ContentType** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-235">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="2f09d-236">As chaves do dicionário serão usadas como os nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-236">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="2f09d-237">Por padrão, os valores de formulário serão convertidos em valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2f09d-237">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="2f09d-238">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-238">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="2f09d-239">O nome do arquivo será enviado como o `filename` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-239">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="2f09d-240">O MIME será definido como `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-240">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="2f09d-241">`Get-Item` pode ser usado para simplificar o fornecimento do objeto **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-241">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="2f09d-242">Se o valor for um tipo de coleção, como uma matriz ou lista, o campo para será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="2f09d-242">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="2f09d-243">Os valores da lista serão tratados como cadeias de caracteres por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f09d-243">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="2f09d-244">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-244">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="2f09d-245">Não há suporte para coleções aninhadas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-245">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="2f09d-246">No exemplo acima, o `tags` campo será fornecido três vezes no formulário, uma vez para cada `Vacation` , `Italy` e `2017` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-246">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="2f09d-247">O `pictures` campo também será enviado uma vez para cada arquivo na `2017-Italy` pasta.</span><span class="sxs-lookup"><span data-stu-id="2f09d-247">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="2f09d-248">O conteúdo binário dos arquivos nessa pasta será enviado como os valores.</span><span class="sxs-lookup"><span data-stu-id="2f09d-248">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="2f09d-249">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-249">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="2f09d-250">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="2f09d-250">-Headers</span></span>

<span data-ttu-id="2f09d-251">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-251">Specifies the headers of the web request.</span></span> <span data-ttu-id="2f09d-252">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-252">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="2f09d-253">Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-253">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="2f09d-254">Você não pode usar esse parâmetro para especificar `User-Agent` cabeçalhos de cookie ou.</span><span class="sxs-lookup"><span data-stu-id="2f09d-254">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="2f09d-255">Cabeçalhos relacionados ao conteúdo, como, `Content-Type` serão substituídos quando um `MultipartFormDataContent` objeto for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-255">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="2f09d-256">-InFile</span><span class="sxs-lookup"><span data-stu-id="2f09d-256">-InFile</span></span>

<span data-ttu-id="2f09d-257">Obtém o conteúdo da solicitação da Web de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-257">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="2f09d-258">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-258">Enter a path and file name.</span></span> <span data-ttu-id="2f09d-259">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="2f09d-259">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="2f09d-260">-MaximumFollowRelLink</span><span class="sxs-lookup"><span data-stu-id="2f09d-260">-MaximumFollowRelLink</span></span>

<span data-ttu-id="2f09d-261">Especifica quantas vezes seguir os links de relação se **FollowRelLink** for usado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-261">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="2f09d-262">Um valor menor pode ser necessário se a API REST for limitada devido a muitas solicitações.</span><span class="sxs-lookup"><span data-stu-id="2f09d-262">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="2f09d-263">O valor padrão é `[Int32]::MaxValue`.</span><span class="sxs-lookup"><span data-stu-id="2f09d-263">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="2f09d-264">Um valor de 0 (zero) impede os links de relação A seguir.</span><span class="sxs-lookup"><span data-stu-id="2f09d-264">A value of 0 (zero) prevents following relation links.</span></span>

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

### <span data-ttu-id="2f09d-265">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="2f09d-265">-MaximumRedirection</span></span>

<span data-ttu-id="2f09d-266">Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="2f09d-266">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="2f09d-267">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="2f09d-267">The default value is 5.</span></span> <span data-ttu-id="2f09d-268">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="2f09d-268">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="2f09d-269">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="2f09d-269">-MaximumRetryCount</span></span>

<span data-ttu-id="2f09d-270">Especifica quantas vezes o PowerShell tenta novamente uma conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-270">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="2f09d-271">Consulte também o parâmetro **RetryIntervalSec** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="2f09d-271">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="2f09d-272">-Método</span><span class="sxs-lookup"><span data-stu-id="2f09d-272">-Method</span></span>

<span data-ttu-id="2f09d-273">Especifica o método usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-273">Specifies the method used for the web request.</span></span> <span data-ttu-id="2f09d-274">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="2f09d-274">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2f09d-275">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f09d-275">Default</span></span>
- <span data-ttu-id="2f09d-276">Excluir</span><span class="sxs-lookup"><span data-stu-id="2f09d-276">Delete</span></span>
- <span data-ttu-id="2f09d-277">Obter</span><span class="sxs-lookup"><span data-stu-id="2f09d-277">Get</span></span>
- <span data-ttu-id="2f09d-278">Head</span><span class="sxs-lookup"><span data-stu-id="2f09d-278">Head</span></span>
- <span data-ttu-id="2f09d-279">Mesclar</span><span class="sxs-lookup"><span data-stu-id="2f09d-279">Merge</span></span>
- <span data-ttu-id="2f09d-280">Opções</span><span class="sxs-lookup"><span data-stu-id="2f09d-280">Options</span></span>
- <span data-ttu-id="2f09d-281">Patch</span><span class="sxs-lookup"><span data-stu-id="2f09d-281">Patch</span></span>
- <span data-ttu-id="2f09d-282">Postar</span><span class="sxs-lookup"><span data-stu-id="2f09d-282">Post</span></span>
- <span data-ttu-id="2f09d-283">Put</span><span class="sxs-lookup"><span data-stu-id="2f09d-283">Put</span></span>
- <span data-ttu-id="2f09d-284">Trace</span><span class="sxs-lookup"><span data-stu-id="2f09d-284">Trace</span></span>

<span data-ttu-id="2f09d-285">O parâmetro **CustomMethod** pode ser usado para métodos de solicitação não listados acima.</span><span class="sxs-lookup"><span data-stu-id="2f09d-285">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="2f09d-286">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="2f09d-286">-NoProxy</span></span>

<span data-ttu-id="2f09d-287">Indica que o cmdlet não usará um proxy para acessar o destino.</span><span class="sxs-lookup"><span data-stu-id="2f09d-287">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="2f09d-288">Quando você precisar ignorar o proxy configurado no Internet Explorer ou um proxy especificado no ambiente, use essa opção.</span><span class="sxs-lookup"><span data-stu-id="2f09d-288">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="2f09d-289">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-289">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="2f09d-290">-Outfile</span><span class="sxs-lookup"><span data-stu-id="2f09d-290">-OutFile</span></span>

<span data-ttu-id="2f09d-291">Salva o corpo da resposta no arquivo de saída especificado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-291">Saves the response body in the specified output file.</span></span> <span data-ttu-id="2f09d-292">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-292">Enter a path and file name.</span></span> <span data-ttu-id="2f09d-293">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="2f09d-293">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="2f09d-294">O nome é tratado como um caminho literal.</span><span class="sxs-lookup"><span data-stu-id="2f09d-294">The name is treated as a literal path.</span></span> <span data-ttu-id="2f09d-295">Os nomes que contêm colchetes ( `[]` ) devem ser colocados entre aspas simples ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="2f09d-295">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="2f09d-296">Por padrão, `Invoke-RestMethod` o retorna os resultados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="2f09d-296">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="2f09d-297">Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-297">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="2f09d-298">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2f09d-298">-PassThru</span></span>

<span data-ttu-id="2f09d-299">Retorna os resultados, além de gravá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-299">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="2f09d-300">Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-300">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="2f09d-301">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="2f09d-301">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="2f09d-302">Indica que o cmdlet deve preservar o `Authorization` cabeçalho, quando presente, entre redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-302">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="2f09d-303">Por padrão, o cmdlet retira o `Authorization` cabeçalho antes de redirecionar.</span><span class="sxs-lookup"><span data-stu-id="2f09d-303">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="2f09d-304">A especificação desse parâmetro desabilita essa lógica nos casos em que o cabeçalho precisa ser enviado para o local de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="2f09d-304">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="2f09d-305">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-305">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-306">-Proxy</span><span class="sxs-lookup"><span data-stu-id="2f09d-306">-Proxy</span></span>

<span data-ttu-id="2f09d-307">Usa um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="2f09d-307">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="2f09d-308">Insira o Uniform Resource Identifier (URI) de um servidor de proxy de rede.</span><span class="sxs-lookup"><span data-stu-id="2f09d-308">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="2f09d-309">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-309">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-310">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2f09d-310">-ProxyCredential</span></span>

<span data-ttu-id="2f09d-311">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-311">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="2f09d-312">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2f09d-312">The default is the current user.</span></span>

<span data-ttu-id="2f09d-313">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , **User@Domain.Com** ou insira um `PSCredential` objeto, como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f09d-313">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="2f09d-314">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="2f09d-315">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="2f09d-316">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="2f09d-316">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="2f09d-317">Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-317">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="2f09d-318">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-318">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="2f09d-319">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-319">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="2f09d-320">-ResponseHeadersVariable</span><span class="sxs-lookup"><span data-stu-id="2f09d-320">-ResponseHeadersVariable</span></span>

<span data-ttu-id="2f09d-321">Cria um dicionário de cabeçalhos de resposta e o salva no valor da variável especificada.</span><span class="sxs-lookup"><span data-stu-id="2f09d-321">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="2f09d-322">As chaves do dicionário conterão os nomes de campo do cabeçalho de resposta retornado pelo servidor Web e os valores serão os respectivos valores de campo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-322">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="2f09d-323">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-323">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-324">-Retomar</span><span class="sxs-lookup"><span data-stu-id="2f09d-324">-Resume</span></span>

<span data-ttu-id="2f09d-325">Executa uma tentativa de melhor esforço para retomar o download de um arquivo parcial.</span><span class="sxs-lookup"><span data-stu-id="2f09d-325">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="2f09d-326">O parâmetro **resume** requer o parâmetro **outfile** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-326">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="2f09d-327">**Retomar** opera apenas no tamanho do arquivo local e no arquivo remoto e não executa nenhuma outra validação que o arquivo local e o arquivo remoto sejam os mesmos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-327">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="2f09d-328">Se o tamanho do arquivo local for menor que o tamanho do arquivo remoto, o cmdlet tentará retomar o download do arquivo e acrescentará os bytes restantes ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f09d-328">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="2f09d-329">Se o tamanho do arquivo local for igual ao tamanho do arquivo remoto, nenhuma ação será executada e o cmdlet assumirá que o download já foi concluído.</span><span class="sxs-lookup"><span data-stu-id="2f09d-329">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="2f09d-330">Se o tamanho do arquivo local for maior que o tamanho do arquivo remoto, o arquivo local será substituído e todo o arquivo remoto será completamente baixado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-330">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="2f09d-331">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-331">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="2f09d-332">Se o servidor remoto não oferecer suporte a retomada de download, o arquivo local será substituído e todo o arquivo remoto será completamente baixado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-332">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="2f09d-333">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-333">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="2f09d-334">Se o arquivo local não existir, o arquivo local será criado e todo o arquivo remoto será baixado completamente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-334">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="2f09d-335">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-335">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="2f09d-336">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-336">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="2f09d-337">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="2f09d-337">-RetryIntervalSec</span></span>

<span data-ttu-id="2f09d-338">Especifica o intervalo entre as repetições para a conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-338">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="2f09d-339">Consulte também o parâmetro **MaximumRetryCount** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="2f09d-339">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="2f09d-340">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="2f09d-340">-SessionVariable</span></span>

<span data-ttu-id="2f09d-341">Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.</span><span class="sxs-lookup"><span data-stu-id="2f09d-341">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="2f09d-342">Insira um nome de variável sem o símbolo de cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2f09d-342">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="2f09d-343">Quando você especifica uma variável de sessão, `Invoke-RestMethod` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f09d-343">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="2f09d-344">Você pode usar a variável na sessão, assim que o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="2f09d-344">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="2f09d-345">Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-345">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="2f09d-346">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-346">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="2f09d-347">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-347">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="2f09d-348">Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-348">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="2f09d-349">O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="2f09d-349">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="2f09d-350">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-350">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="2f09d-351">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-351">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="2f09d-352">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-352">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="2f09d-353">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="2f09d-353">-SkipCertificateCheck</span></span>

<span data-ttu-id="2f09d-354">Ignora as verificações de validação de certificado que incluem todas as validações, como expiração, revogação, autoridade raiz confiável etc.</span><span class="sxs-lookup"><span data-stu-id="2f09d-354">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="2f09d-355">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-355">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="2f09d-356">Essa opção destina-se apenas a ser usada em hosts conhecidos usando um certificado autoassinado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="2f09d-356">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="2f09d-357">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="2f09d-357">Use at your own risk.</span></span>

<span data-ttu-id="2f09d-358">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-358">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-359">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="2f09d-359">-SkipHeaderValidation</span></span>

<span data-ttu-id="2f09d-360">Indica que o cmdlet deve adicionar cabeçalhos à solicitação sem validação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-360">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="2f09d-361">Essa opção deve ser usada para sites que exigem valores de cabeçalho que não estão em conformidade com os padrões.</span><span class="sxs-lookup"><span data-stu-id="2f09d-361">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="2f09d-362">A especificação dessa opção desabilita a validação para permitir que o valor seja passado desmarcado.</span><span class="sxs-lookup"><span data-stu-id="2f09d-362">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="2f09d-363">Quando especificado, todos os cabeçalhos são adicionados sem validação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-363">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="2f09d-364">Isso desabilitará a validação para valores passados para os parâmetros **ContentType** , **Headers** e **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-364">This will disable validation for values passed to the **ContentType** , **Headers** , and **UserAgent** parameters.</span></span>

<span data-ttu-id="2f09d-365">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-365">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2f09d-366">-SkipHttpErrorCheck</span><span class="sxs-lookup"><span data-stu-id="2f09d-366">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="2f09d-367">Esse parâmetro faz com que o cmdlet ignore os status de erro HTTP e continue a processar as respostas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-367">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="2f09d-368">As respostas de erro são gravadas no pipeline da mesma forma como se fossem bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-368">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="2f09d-369">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="2f09d-369">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-370">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="2f09d-370">-SslProtocol</span></span>

<span data-ttu-id="2f09d-371">Define os protocolos SSL/TLS que são permitidos para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-371">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="2f09d-372">Por padrão, todos os protocolos SSL/TLS com suporte do sistema são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-372">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="2f09d-373">O **SslProtocol** permite limitar a protocolos específicos para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2f09d-373">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="2f09d-374">**SslProtocol** usa o `WebSslProtocol` sinalizador enum.</span><span class="sxs-lookup"><span data-stu-id="2f09d-374">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="2f09d-375">É possível fornecer mais de um protocolo usando a notação de sinalizador ou combinando várias `WebSslProtocol` opções com o `-bor` , no entanto, não há suporte para o fornecimento de vários protocolos em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-375">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="2f09d-376">Em plataformas não Windows, talvez não seja possível fornecer `Tls` ou `Tls12` como uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f09d-376">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="2f09d-377">O suporte para o `Tls13` não está disponível em todos os sistemas operacionais e precisará ser verificado por sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2f09d-377">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="2f09d-378">Esse recurso foi adicionado no PowerShell 6.0.0 e o suporte para `Tls13` foi adicionado no powershell 7,1.</span><span class="sxs-lookup"><span data-stu-id="2f09d-378">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12, Tls13

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-379">-StatusCodeVariable</span><span class="sxs-lookup"><span data-stu-id="2f09d-379">-StatusCodeVariable</span></span>

<span data-ttu-id="2f09d-380">Esse parâmetro especifica uma variável que é atribuída ao valor inteiro de um código de status.</span><span class="sxs-lookup"><span data-stu-id="2f09d-380">This parameter specifies a variable that's assigned a status code's integer value.</span></span> <span data-ttu-id="2f09d-381">O parâmetro pode identificar mensagens de êxito ou mensagens de falha quando usado com o parâmetro **SkipHttpErrorCheck** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-381">The parameter can identify success messages or failure messages when used with the **SkipHttpErrorCheck** parameter.</span></span>

<span data-ttu-id="2f09d-382">Insira o nome da variável do parâmetro como uma cadeia de caracteres como `-StatusCodeVariable "scv"` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-382">Input the parameter's variable name as a string such as `-StatusCodeVariable "scv"`.</span></span>

<span data-ttu-id="2f09d-383">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="2f09d-383">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-384">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="2f09d-384">-TimeoutSec</span></span>

<span data-ttu-id="2f09d-385">Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="2f09d-385">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="2f09d-386">O valor padrão, 0, especifica um tempo limite indefinido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-386">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="2f09d-387">Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="2f09d-387">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="2f09d-388">-Token</span><span class="sxs-lookup"><span data-stu-id="2f09d-388">-Token</span></span>

<span data-ttu-id="2f09d-389">O token de portador ou OAuth a ser incluído na solicitação.</span><span class="sxs-lookup"><span data-stu-id="2f09d-389">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="2f09d-390">O **token** é exigido por determinadas opções de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-390">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="2f09d-391">Ele não pode ser usado de forma independente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-391">It can't be used independently.</span></span>

<span data-ttu-id="2f09d-392">O **token** usa um `SecureString` que contém o token.</span><span class="sxs-lookup"><span data-stu-id="2f09d-392">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="2f09d-393">Para fornecer o token, use manualmente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f09d-393">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="2f09d-394">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="2f09d-394">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-395">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="2f09d-395">-TransferEncoding</span></span>

<span data-ttu-id="2f09d-396">Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência.</span><span class="sxs-lookup"><span data-stu-id="2f09d-396">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="2f09d-397">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="2f09d-397">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2f09d-398">Em bloco</span><span class="sxs-lookup"><span data-stu-id="2f09d-398">Chunked</span></span>
- <span data-ttu-id="2f09d-399">Compactar</span><span class="sxs-lookup"><span data-stu-id="2f09d-399">Compress</span></span>
- <span data-ttu-id="2f09d-400">Desinflar</span><span class="sxs-lookup"><span data-stu-id="2f09d-400">Deflate</span></span>
- <span data-ttu-id="2f09d-401">GZip</span><span class="sxs-lookup"><span data-stu-id="2f09d-401">GZip</span></span>
- <span data-ttu-id="2f09d-402">Identidade</span><span class="sxs-lookup"><span data-stu-id="2f09d-402">Identity</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-403">-URI</span><span class="sxs-lookup"><span data-stu-id="2f09d-403">-Uri</span></span>

<span data-ttu-id="2f09d-404">Especifica o Uniform Resource Identifier (URI) do recurso da Internet para o qual a solicitação da Web é enviada.</span><span class="sxs-lookup"><span data-stu-id="2f09d-404">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="2f09d-405">Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.</span><span class="sxs-lookup"><span data-stu-id="2f09d-405">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="2f09d-406">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-406">This parameter is required.</span></span> <span data-ttu-id="2f09d-407">O nome do parâmetro ( **URI** ) é opcional.</span><span class="sxs-lookup"><span data-stu-id="2f09d-407">The parameter name ( **Uri** ) is optional.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-408">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="2f09d-408">-UseBasicParsing</span></span>

<span data-ttu-id="2f09d-409">Esse parâmetro foi preterido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-409">This parameter has been deprecated.</span></span> <span data-ttu-id="2f09d-410">A partir do PowerShell 6.0.0, todas as solicitações da Web usam somente a análise básica.</span><span class="sxs-lookup"><span data-stu-id="2f09d-410">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="2f09d-411">Esse parâmetro é incluído somente para compatibilidade com versões anteriores e qualquer uso dele não terá nenhum efeito sobre a operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f09d-411">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="2f09d-412">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="2f09d-412">-UseDefaultCredentials</span></span>

<span data-ttu-id="2f09d-413">Indica que o cmdlet usa as credenciais do usuário atual para enviar a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-413">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="2f09d-414">Isso não pode ser usado com **autenticação** ou **credencial** e pode não ter suporte em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-414">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="2f09d-415">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="2f09d-415">-UserAgent</span></span>

<span data-ttu-id="2f09d-416">Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-416">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="2f09d-417">O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` com pequenas variações para cada sistema operacional e plataforma.</span><span class="sxs-lookup"><span data-stu-id="2f09d-417">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="2f09d-418">Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari.</span><span class="sxs-lookup"><span data-stu-id="2f09d-418">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="2f09d-419">-Websession</span><span class="sxs-lookup"><span data-stu-id="2f09d-419">-WebSession</span></span>

<span data-ttu-id="2f09d-420">Especifica uma sessão de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-420">Specifies a web request session.</span></span> <span data-ttu-id="2f09d-421">Insira o nome da variável, incluindo o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2f09d-421">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="2f09d-422">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-422">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="2f09d-423">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-423">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="2f09d-424">Cabeçalhos relacionados ao conteúdo, como `Content-Type` , também serão substituídos quando um objeto **MultipartFormDataContent** for fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-424">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="2f09d-425">Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="2f09d-425">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="2f09d-426">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-426">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="2f09d-427">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="2f09d-427">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="2f09d-428">Para criar uma sessão de solicitação da Web, insira um nome de variável, sem um sinal de cifrão, no valor do parâmetro **SessionVariable** de um `Invoke-RestMethod` comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-428">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="2f09d-429">`Invoke-RestMethod` cria a sessão e salva-a na variável.</span><span class="sxs-lookup"><span data-stu-id="2f09d-429">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="2f09d-430">Em comandos posteriores, use a variável como o valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="2f09d-430">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="2f09d-431">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2f09d-431">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f09d-432">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2f09d-432">CommonParameters</span></span>

<span data-ttu-id="2f09d-433">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2f09d-433">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f09d-434">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2f09d-434">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f09d-435">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2f09d-435">INPUTS</span></span>

### <span data-ttu-id="2f09d-436">System.Object</span><span class="sxs-lookup"><span data-stu-id="2f09d-436">System.Object</span></span>

<span data-ttu-id="2f09d-437">Você pode canalizar o corpo de uma solicitação da Web para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="2f09d-437">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="2f09d-438">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2f09d-438">OUTPUTS</span></span>

### <span data-ttu-id="2f09d-439">System. Int64, System. String, System.Xml.Xmldocumento</span><span class="sxs-lookup"><span data-stu-id="2f09d-439">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="2f09d-440">A saída do cmdlet depende do formato do conteúdo que é obtido.</span><span class="sxs-lookup"><span data-stu-id="2f09d-440">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="2f09d-441">PSObject</span><span class="sxs-lookup"><span data-stu-id="2f09d-441">PSObject</span></span>

<span data-ttu-id="2f09d-442">Se a solicitação retornar cadeias de caracteres JSON, `Invoke-RestMethod` retornará um **PSObject** que representa as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2f09d-442">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="2f09d-443">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2f09d-443">NOTES</span></span>

<span data-ttu-id="2f09d-444">Alguns recursos podem não estar disponíveis em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-444">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="2f09d-445">Devido às alterações no .NET Core 3,1, o PowerShell 7,0 e superior usam a propriedade [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) para determinar a configuração do proxy.</span><span class="sxs-lookup"><span data-stu-id="2f09d-445">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="2f09d-446">O valor dessa propriedade é diferente das regras, dependendo da sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="2f09d-446">The value of this property is different rules depending on your platform:</span></span>

- <span data-ttu-id="2f09d-447">**Para o Windows** : lê a configuração de proxy de variáveis de ambiente ou, se elas não estiverem definidas, nas configurações de proxy do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f09d-447">**For Windows** : Reads proxy configuration from environment variables or, if those are not defined, from the user's proxy settings.</span></span>
- <span data-ttu-id="2f09d-448">**Para MacOS** : lê a configuração de proxy de variáveis de ambiente ou, se elas não estiverem definidas, nas configurações de proxy do sistema.</span><span class="sxs-lookup"><span data-stu-id="2f09d-448">**For macOS** : Reads proxy configuration from environment variables or, if those are not defined, from the system's proxy settings.</span></span>
- <span data-ttu-id="2f09d-449">**Para Linux** : lê a configuração de proxy de variáveis de ambiente ou, caso não estejam definidas, essa propriedade Inicializa uma instância não configurada que ignora todos os endereços.</span><span class="sxs-lookup"><span data-stu-id="2f09d-449">**For Linux** : Reads proxy configuration from environment variables or, in case those are not defined, this property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="2f09d-450">As variáveis de ambiente usadas para `DefaultProxy` inicialização em plataformas baseadas no Windows e no Unix são:</span><span class="sxs-lookup"><span data-stu-id="2f09d-450">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="2f09d-451">` HTTP_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTP.</span><span class="sxs-lookup"><span data-stu-id="2f09d-451">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="2f09d-452">`HTTPS_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2f09d-452">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="2f09d-453">`ALL_PROXY`: o nome do host ou endereço IP do servidor proxy usado em solicitações HTTP e HTTPS no caso `HTTP_PROXY` ou `HTTPS_PROXY` não estão definidas.</span><span class="sxs-lookup"><span data-stu-id="2f09d-453">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="2f09d-454">`NO_PROXY`: uma lista separada por vírgulas de nomes de host que devem ser excluídos do proxy.</span><span class="sxs-lookup"><span data-stu-id="2f09d-454">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="2f09d-455">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2f09d-455">RELATED LINKS</span></span>

[<span data-ttu-id="2f09d-456">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2f09d-456">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="2f09d-457">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="2f09d-457">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="2f09d-458">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="2f09d-458">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
