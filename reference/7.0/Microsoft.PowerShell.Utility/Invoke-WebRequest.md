---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: b81074e14461b0bf481232553b614e06c23b90b6
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195189"
---
# <span data-ttu-id="354a3-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="354a3-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="354a3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="354a3-104">SYNOPSIS</span></span>
<span data-ttu-id="354a3-105">Obtém o conteúdo de uma página da Web na Internet.</span><span class="sxs-lookup"><span data-stu-id="354a3-105">Gets content from a web page on the internet.</span></span>

## <span data-ttu-id="354a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="354a3-106">SYNTAX</span></span>

### <span data-ttu-id="354a3-107">StandardMethod (padrão)</span><span class="sxs-lookup"><span data-stu-id="354a3-107">StandardMethod (Default)</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="354a3-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="354a3-108">StandardMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>] -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="354a3-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="354a3-109">CustomMethod</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="354a3-110">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="354a3-110">CustomMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="354a3-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="354a3-111">DESCRIPTION</span></span>

<span data-ttu-id="354a3-112">O `Invoke-WebRequest` cmdlet envia solicitações HTTP e HTTPS para uma página da Web ou serviço Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-112">The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service.</span></span> <span data-ttu-id="354a3-113">Ele analisa a resposta e retorna coleções de links, imagens e outros elementos HTML significativos.</span><span class="sxs-lookup"><span data-stu-id="354a3-113">It parses the response and returns collections of links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="354a3-114">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="354a3-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="354a3-115">A partir do PowerShell 7,0, `Invoke-WebRequest` dá suporte à configuração de proxy definida por variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="354a3-115">Beginning in PowerShell 7.0, `Invoke-WebRequest` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="354a3-116">Consulte a seção [observações](#notes) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="354a3-116">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="354a3-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="354a3-117">EXAMPLES</span></span>

### <span data-ttu-id="354a3-118">Exemplo 1: Enviar uma solicitação da Web</span><span class="sxs-lookup"><span data-stu-id="354a3-118">Example 1: Send a web request</span></span>

<span data-ttu-id="354a3-119">Este exemplo usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação da Web para o site Bing.com.</span><span class="sxs-lookup"><span data-stu-id="354a3-119">This example uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$Response = Invoke-WebRequest -URI https://www.bing.com/search?q=how+many+feet+in+a+mile
$Response.InputFields | Where-Object {
    $_.name -like "* Value*"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="354a3-120">O primeiro comando emite a solicitação e salva a resposta na `$Response` variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-120">The first command issues the request and saves the response in the `$Response` variable.</span></span>

<span data-ttu-id="354a3-121">O segundo comando obtém qualquer **InputField** em que a propriedade **Name** é semelhante `"* Value"` .</span><span class="sxs-lookup"><span data-stu-id="354a3-121">The second command gets any **InputField** where the **Name** property is like `"* Value"`.</span></span> <span data-ttu-id="354a3-122">Os resultados filtrados são canalizados para `Select-Object` para selecionar as propriedades **Name** e **Value** .</span><span class="sxs-lookup"><span data-stu-id="354a3-122">The filtered results are piped to `Select-Object` to select the **Name** and **Value** properties.</span></span>

### <span data-ttu-id="354a3-123">Exemplo 2: usar um serviço Web com estado</span><span class="sxs-lookup"><span data-stu-id="354a3-123">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="354a3-124">Este exemplo mostra como usar o `Invoke-WebRequest` cmdlet com um serviço Web com estado.</span><span class="sxs-lookup"><span data-stu-id="354a3-124">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service.</span></span>

```powershell
$Body = @{
    User = 'jdoe'
    password = 'P@S$w0rd!'
}
$LoginResponse = Invoke-WebRequest 'https://www.contoso.com/login/' -SessionVariable 'Session' -Body $Body -Method 'POST'

$Session

$ProfileResponse = Invoke-WebRequest 'https://www.contoso.com/profile/' -WebSession $Session

$ProfileResponse
```

<span data-ttu-id="354a3-125">A primeira chamada para `Invoke-WebRequest` envia uma solicitação de entrada.</span><span class="sxs-lookup"><span data-stu-id="354a3-125">The first call to `Invoke-WebRequest` sends a sign-in request.</span></span> <span data-ttu-id="354a3-126">O comando especifica um valor de "Session" para o valor do parâmetro **-SessionVariable** e salva o resultado na `$LoginResponse` variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-126">The command specifies a value of "Session" for the value of the **-SessionVariable** parameter, and saves the result in the `$LoginResponse` variable.</span></span> <span data-ttu-id="354a3-127">Quando o comando é concluído, a `$LoginResponse` variável contém um `BasicHtmlWebResponseObject` e a `$Session` variável contém um `WebRequestSession` objeto.</span><span class="sxs-lookup"><span data-stu-id="354a3-127">When the command completes, the `$LoginResponse` variable contains an `BasicHtmlWebResponseObject` and the `$Session` variable contains a `WebRequestSession` object.</span></span> <span data-ttu-id="354a3-128">Isso faz o logon do usuário no site.</span><span class="sxs-lookup"><span data-stu-id="354a3-128">This logs the user into the site.</span></span>

<span data-ttu-id="354a3-129">A chamada para `$Session` por si só mostra o `WebRequestSession` objeto na variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-129">The call to `$Session` by itself shows the `WebRequestSession` object in the variable.</span></span>

<span data-ttu-id="354a3-130">A segunda chamada para `Invoke-WebRequest` busca o perfil do usuário que exige que o usuário seja conectado ao site.</span><span class="sxs-lookup"><span data-stu-id="354a3-130">The second call to `Invoke-WebRequest` fetches the user's profile which requires that the user be logged into the site.</span></span> <span data-ttu-id="354a3-131">Os dados de sessão armazenados na `$Session` variável são usados para fornecer cookies de sessão para o site criado durante o logon.</span><span class="sxs-lookup"><span data-stu-id="354a3-131">The session data stored in the `$Session` variable is used to provide session cookies to the site created during the login.</span></span> <span data-ttu-id="354a3-132">O resultado é salvo na `$ProfileResponse` variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-132">The result is saved in the `$ProfileResponse` variable.</span></span>

<span data-ttu-id="354a3-133">A chamada para `$ProfileResponse` por si só mostra o `BasicHtmlWebResponseObject` na variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-133">The call to `$ProfileResponse` by itself shows the `BasicHtmlWebResponseObject` in the variable.</span></span>

### <span data-ttu-id="354a3-134">Exemplo 3: obter links de uma página da Web</span><span class="sxs-lookup"><span data-stu-id="354a3-134">Example 3: Get links from a web page</span></span>

<span data-ttu-id="354a3-135">Este exemplo obtém os links em uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-135">This example gets the links in a web page.</span></span> <span data-ttu-id="354a3-136">Ele usa o `Invoke-WebRequest` cmdlet para obter o conteúdo da página da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-136">It uses the `Invoke-WebRequest` cmdlet to get the web page content.</span></span> <span data-ttu-id="354a3-137">Em seguida, ele usa a propriedade **links** do `BasicHtmlWebResponseObject` que `Invoke-WebRequest` retorna e a propriedade **href** de cada link.</span><span class="sxs-lookup"><span data-stu-id="354a3-137">Then it uses the **Links** property of the `BasicHtmlWebResponseObject` that `Invoke-WebRequest` returns, and the **Href** property of each link.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### <span data-ttu-id="354a3-138">Exemplo 4: grava o conteúdo da resposta em um arquivo usando a codificação definida na página solicitada.</span><span class="sxs-lookup"><span data-stu-id="354a3-138">Example 4: Writes the response content to a file using the encoding defined in the requested page.</span></span>

<span data-ttu-id="354a3-139">Este exemplo usa o `Invoke-WebRequest` cmdlet para recuperar o conteúdo da página da Web de uma página de documentação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="354a3-139">This example uses the `Invoke-WebRequest` cmdlet to retrieve the web page content of a PowerShell documentation page.</span></span>

```powershell
$Response = Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs"
$Stream = [System.IO.StreamWriter]::new('.\docspage.html', $false, $Response.Encoding)
try {
    $Stream.Write($Response.Content)
}
finally {
    $Stream.Dispose()
}
```

<span data-ttu-id="354a3-140">O primeiro comando recupera a página e salva o objeto de resposta na `$Response` variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-140">The first command retrieves the page and saves the response object in the `$Response` variable.</span></span>

<span data-ttu-id="354a3-141">O segundo comando cria um `StreamWriter` para usar para gravar o conteúdo da resposta em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-141">The second command creates a `StreamWriter` to use to write the response content to a file.</span></span> <span data-ttu-id="354a3-142">A propriedade **Encoding** do objeto Response é usada para definir a codificação para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-142">The **Encoding** property of the response object is used to set the encoding for the file.</span></span>

<span data-ttu-id="354a3-143">Os poucos comandos gravam a propriedade **Content** no arquivo e, em seguida, descarta o `StreamWriter` .</span><span class="sxs-lookup"><span data-stu-id="354a3-143">The final few commands write the **Content** property to the file then disposes the `StreamWriter`.</span></span>

<span data-ttu-id="354a3-144">Observe que a propriedade **Encoding** será nula se a solicitação da Web não retornar o conteúdo de texto.</span><span class="sxs-lookup"><span data-stu-id="354a3-144">Note that the **Encoding** property is null if the web request doesn't return text content.</span></span>

### <span data-ttu-id="354a3-145">Exemplo 5: enviar um arquivo com diversas partes/dados de formulário</span><span class="sxs-lookup"><span data-stu-id="354a3-145">Example 5: Submit a multipart/form-data file</span></span>

<span data-ttu-id="354a3-146">Este exemplo usa o `Invoke-WebRequest` cmdlet para carregar um arquivo como um `multipart/form-data` envio.</span><span class="sxs-lookup"><span data-stu-id="354a3-146">This example uses the `Invoke-WebRequest` cmdlet upload a file as a `multipart/form-data` submission.</span></span> <span data-ttu-id="354a3-147">O arquivo `c:\document.txt` é enviado como o campo `document` de formulário com o `Content-Type` de `text/plain` .</span><span class="sxs-lookup"><span data-stu-id="354a3-147">The file `c:\document.txt` is submitted as the form field `document` with the `Content-Type` of `text/plain`.</span></span>

```powershell
$FilePath = 'c:\document.txt'
$FieldName = 'document'
$ContentType = 'text/plain'

$FileStream = [System.IO.FileStream]::new($filePath, [System.IO.FileMode]::Open)
$FileHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new('form-data')
$FileHeader.Name = $FieldName
$FileHeader.FileName = Split-Path -leaf $FilePath
$FileContent = [System.Net.Http.StreamContent]::new($FileStream)
$FileContent.Headers.ContentDisposition = $FileHeader
$FileContent.Headers.ContentType = [System.Net.Http.Headers.MediaTypeHeaderValue]::Parse($ContentType)

$MultipartContent = [System.Net.Http.MultipartFormDataContent]::new()
$MultipartContent.Add($FileContent)

$Response = Invoke-WebRequest -Body $MultipartContent -Method 'POST' -Uri 'https://api.contoso.com/upload'
```

### <span data-ttu-id="354a3-148">Exemplo 6: multipart/forma simplificada – envio de dados</span><span class="sxs-lookup"><span data-stu-id="354a3-148">Example 6: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="354a3-149">Algumas APIs exigem `multipart/form-data` envios de arquivos e conteúdo misto.</span><span class="sxs-lookup"><span data-stu-id="354a3-149">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="354a3-150">Este exemplo demonstra a atualização de um perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="354a3-150">This example demonstrates updating a user profile.</span></span>

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
$Result = Invoke-WebRequest -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="354a3-151">O formulário de perfil requer estes campos:,,,, `firstName` `lastName` `email` `avatar` `birthday` e `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="354a3-151">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="354a3-152">A API está esperando uma imagem para que a PIC do perfil do usuário seja fornecida no `avatar` campo.</span><span class="sxs-lookup"><span data-stu-id="354a3-152">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="354a3-153">A API também aceita `hobbies` que várias entradas sejam enviadas na mesma forma.</span><span class="sxs-lookup"><span data-stu-id="354a3-153">The API also accepts multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="354a3-154">Ao criar a `$Form` tabela de hash, os nomes de chave são usados como nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="354a3-154">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="354a3-155">Por padrão, os valores da tabela de hash são convertidos em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="354a3-155">By default, the values of the HashTable are converted to strings.</span></span> <span data-ttu-id="354a3-156">Se um valor de **System. IO. FileInfo** estiver presente, o conteúdo do arquivo será enviado.</span><span class="sxs-lookup"><span data-stu-id="354a3-156">If a **System.IO.FileInfo** value is present, the file contents are submitted.</span></span> <span data-ttu-id="354a3-157">Se uma coleção, como matrizes ou listas, estiver presente, o campo de formulário será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="354a3-157">If a collection such as arrays or lists are present, the form field is submitted multiple times.</span></span>

<span data-ttu-id="354a3-158">Usando `Get-Item` na `avatar` chave, o `FileInfo` objeto é definido como o valor.</span><span class="sxs-lookup"><span data-stu-id="354a3-158">By using `Get-Item` on the `avatar` key, the `FileInfo` object is set as the value.</span></span> <span data-ttu-id="354a3-159">O resultado é que os dados da imagem para `jdoe.png` são enviados.</span><span class="sxs-lookup"><span data-stu-id="354a3-159">The result is that the image data for `jdoe.png` is submitted.</span></span>

<span data-ttu-id="354a3-160">Ao fornecer uma lista à `hobbies` chave, o `hobbies` campo está presente nos envios uma vez para cada item de lista.</span><span class="sxs-lookup"><span data-stu-id="354a3-160">By supplying a list to the `hobbies` key, the `hobbies` field is present in the submissions once for each list item.</span></span>

### <span data-ttu-id="354a3-161">Exemplo 7: capturar mensagens de não êxito de Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="354a3-161">Example 7: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="354a3-162">Quando `Invoke-WebRequest` o encontra uma mensagem http sem êxito (404, 500, etc.), ela não retorna nenhuma saída e gera um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="354a3-162">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="354a3-163">Para capturar o erro e exibir o **StatusCode** , você pode colocar a execução em um `try/catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="354a3-163">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
    # This will only execute if the Invoke-WebRequest is successful.
    $StatusCode = $Response.StatusCode
}
catch
{
    $StatusCode = $_.Exception.Response.StatusCode.value__
}
$StatusCode
```

```Output
404
```

<span data-ttu-id="354a3-164">O comando chama `Invoke-WebRequest` com **ErrorAction** de **Stop** , que força `Invoke-WebRequest` a gerar um erro de encerramento em todas as solicitações com falha.</span><span class="sxs-lookup"><span data-stu-id="354a3-164">The command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="354a3-165">O erro de encerramento é capturado pelo `catch` bloco que recupera o **StatusCode** do objeto de **exceção** .</span><span class="sxs-lookup"><span data-stu-id="354a3-165">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="354a3-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="354a3-166">PARAMETERS</span></span>

### <span data-ttu-id="354a3-167">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="354a3-167">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="354a3-168">Permite o envio de credenciais e segredos em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="354a3-168">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="354a3-169">Por padrão, o fornecimento de **credenciais** ou qualquer opção de **autenticação** com um **URI** que não começa com `https://` resulta em um erro e a solicitação é anulada para evitar a comunicação involuntária de segredos em texto sem formatação em conexões não criptografadas.</span><span class="sxs-lookup"><span data-stu-id="354a3-169">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` results in an error and the request is aborted to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="354a3-170">Para substituir esse comportamento por sua conta e risco, forneça o parâmetro **AllowUnencryptedAuthentication** .</span><span class="sxs-lookup"><span data-stu-id="354a3-170">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="354a3-171">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="354a3-171">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="354a3-172">Ele é fornecido apenas para compatibilidade com sistemas herdados que não podem fornecer conexões criptografadas.</span><span class="sxs-lookup"><span data-stu-id="354a3-172">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="354a3-173">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="354a3-173">Use at your own risk.</span></span>

<span data-ttu-id="354a3-174">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-174">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-175">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="354a3-175">-Authentication</span></span>

<span data-ttu-id="354a3-176">Especifica o tipo de autenticação explícito a ser usado para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="354a3-176">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="354a3-177">O padrão é **Nenhum** .</span><span class="sxs-lookup"><span data-stu-id="354a3-177">The default is **None** .</span></span>
<span data-ttu-id="354a3-178">A **autenticação** não pode ser usada com **UseDefaultCredentials** .</span><span class="sxs-lookup"><span data-stu-id="354a3-178">**Authentication** cannot be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="354a3-179">Opções de autenticação disponíveis:</span><span class="sxs-lookup"><span data-stu-id="354a3-179">Available Authentication Options:</span></span>

- <span data-ttu-id="354a3-180">**Nenhum** : essa é a opção padrão quando a **autenticação** não é fornecida; nenhuma autenticação explícita é usada.</span><span class="sxs-lookup"><span data-stu-id="354a3-180">**None** : This is the default option when **Authentication** isn't supplied; no explicit authentication is used.</span></span>
- <span data-ttu-id="354a3-181">**Básico** : requer **credencial** .</span><span class="sxs-lookup"><span data-stu-id="354a3-181">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="354a3-182">As credenciais são enviadas em um cabeçalho de autenticação básica do RFC 7617 no formato de `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="354a3-182">The credentials are sent in an RFC 7617 Basic Authentication header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="354a3-183">**Portador** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="354a3-183">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="354a3-184">Envia um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="354a3-184">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="354a3-185">Este é um alias para **OAuth**</span><span class="sxs-lookup"><span data-stu-id="354a3-185">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="354a3-186">**OAuth** : requer **token** .</span><span class="sxs-lookup"><span data-stu-id="354a3-186">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="354a3-187">Envia um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido.</span><span class="sxs-lookup"><span data-stu-id="354a3-187">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="354a3-188">Este é um alias para **portador**</span><span class="sxs-lookup"><span data-stu-id="354a3-188">This is an alias for **Bearer**</span></span>

<span data-ttu-id="354a3-189">O fornecimento de **autenticação** substitui todos os `Authorization` cabeçalhos fornecidos aos **cabeçalhos** ou incluídos na sessão da **websession** .</span><span class="sxs-lookup"><span data-stu-id="354a3-189">Supplying **Authentication** overrides any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="354a3-190">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-190">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-191">-Corpo</span><span class="sxs-lookup"><span data-stu-id="354a3-191">-Body</span></span>

<span data-ttu-id="354a3-192">Especifica o corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="354a3-192">Specifies the body of the request.</span></span> <span data-ttu-id="354a3-193">O corpo é o conteúdo da solicitação que segue os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="354a3-193">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="354a3-194">Também é possível canalizar um valor de corpo para `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="354a3-194">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="354a3-195">O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.</span><span class="sxs-lookup"><span data-stu-id="354a3-195">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="354a3-196">Quando a entrada é uma solicitação GET e o corpo é um `IDictionary` (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="354a3-196">When the input is a GET request and the body is an `IDictionary` (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="354a3-197">Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão `name=value` .</span><span class="sxs-lookup"><span data-stu-id="354a3-197">For other request types (such as POST), the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="354a3-198">O parâmetro **Body** também pode aceitar um `System.Net.Http.MultipartFormDataContent` objeto.</span><span class="sxs-lookup"><span data-stu-id="354a3-198">The **Body** parameter may also accept a `System.Net.Http.MultipartFormDataContent` object.</span></span> <span data-ttu-id="354a3-199">Isso facilita `multipart/form-data` as solicitações.</span><span class="sxs-lookup"><span data-stu-id="354a3-199">This facilitates `multipart/form-data` requests.</span></span> <span data-ttu-id="354a3-200">Quando um objeto **MultipartFormDataContent** é fornecido para **o corpo** , todos os cabeçalhos relacionados ao conteúdo fornecidos aos parâmetros **ContentType** , **Headers** ou **websession** são substituídos pelos cabeçalhos de conteúdo do objeto **MultipartFormDataContent** .</span><span class="sxs-lookup"><span data-stu-id="354a3-200">When a **MultipartFormDataContent** object is supplied for **Body** , any Content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters is overridden by the Content headers of the **MultipartFormDataContent** object.</span></span> <span data-ttu-id="354a3-201">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-201">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-202">-Certificado</span><span class="sxs-lookup"><span data-stu-id="354a3-202">-Certificate</span></span>

<span data-ttu-id="354a3-203">Especifica o certificado do cliente que é usado para uma solicitação da Web segura.</span><span class="sxs-lookup"><span data-stu-id="354a3-203">Specifies the client certificate that's used for a secure web request.</span></span> <span data-ttu-id="354a3-204">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="354a3-204">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="354a3-205">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de certificado ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="354a3-205">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="354a3-206">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="354a3-206">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="354a3-207">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="354a3-207">-CertificateThumbprint</span></span>

<span data-ttu-id="354a3-208">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="354a3-208">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="354a3-209">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="354a3-209">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="354a3-210">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="354a3-210">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="354a3-211">Eles podem ser mapeados somente para contas de usuário local; Eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="354a3-211">They can be mapped only to local user accounts; they don't work with domain accounts.</span></span>

<span data-ttu-id="354a3-212">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="354a3-212">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="354a3-213">Atualmente, esse recurso só tem suporte em plataformas de sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="354a3-213">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="354a3-214">-ContentType</span><span class="sxs-lookup"><span data-stu-id="354a3-214">-ContentType</span></span>

<span data-ttu-id="354a3-215">Especifica o tipo de conteúdo da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-215">Specifies the content type of the web request.</span></span>

<span data-ttu-id="354a3-216">Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-WebRequest` o definirá o tipo de conteúdo como `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="354a3-216">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="354a3-217">Caso contrário, o tipo de conteúdo não será especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="354a3-217">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="354a3-218">**ContentType** é substituído quando um objeto **MultipartFormDataContent** é fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="354a3-218">**ContentType** is overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="354a3-219">-Credential</span><span class="sxs-lookup"><span data-stu-id="354a3-219">-Credential</span></span>

<span data-ttu-id="354a3-220">Especifica uma conta de usuário com permissão para enviar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="354a3-220">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="354a3-221">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="354a3-221">The default is the current user.</span></span>

<span data-ttu-id="354a3-222">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="354a3-222">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="354a3-223">A **credencial** pode ser usada sozinha ou em conjunto com determinadas opções de parâmetro de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="354a3-223">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="354a3-224">Quando usado sozinho, ele fornece apenas as credenciais para o servidor remoto se o servidor remoto enviar uma solicitação de desafio de autenticação.</span><span class="sxs-lookup"><span data-stu-id="354a3-224">When used alone, it only supplies credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="354a3-225">Quando usado com as opções de **autenticação** , as credenciais são enviadas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="354a3-225">When used with **Authentication** options, the credentials are explicitly sent.</span></span>

<span data-ttu-id="354a3-226">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="354a3-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="354a3-227">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="354a3-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="354a3-228">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="354a3-228">-CustomMethod</span></span>

<span data-ttu-id="354a3-229">Especifica um método personalizado usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-229">Specifies a custom method used for the web request.</span></span> <span data-ttu-id="354a3-230">Isso pode ser usado se o método de solicitação exigido pelo ponto de extremidade não for uma opção disponível no **método** .</span><span class="sxs-lookup"><span data-stu-id="354a3-230">This can be used if the Request Method required by the endpoint isn't an available option on the **Method** .</span></span> <span data-ttu-id="354a3-231">O **método** e o **CustomMethod** não podem ser usados juntos.</span><span class="sxs-lookup"><span data-stu-id="354a3-231">**Method** and **CustomMethod** can't be used together.</span></span>

<span data-ttu-id="354a3-232">Este exemplo faz uma `TEST` solicitação HTTP para a API:</span><span class="sxs-lookup"><span data-stu-id="354a3-232">This example makes a `TEST` HTTP request to the API:</span></span>

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="354a3-233">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-233">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-234">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="354a3-234">-DisableKeepAlive</span></span>

<span data-ttu-id="354a3-235">Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como **false** .</span><span class="sxs-lookup"><span data-stu-id="354a3-235">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False** .</span></span> <span data-ttu-id="354a3-236">Por padrão, **KeepAlive** é **true** .</span><span class="sxs-lookup"><span data-stu-id="354a3-236">By default, **KeepAlive** is **True** .</span></span> <span data-ttu-id="354a3-237">**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.</span><span class="sxs-lookup"><span data-stu-id="354a3-237">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="354a3-238">-Formulário</span><span class="sxs-lookup"><span data-stu-id="354a3-238">-Form</span></span>

<span data-ttu-id="354a3-239">Converte um dicionário em um `multipart/form-data` envio.</span><span class="sxs-lookup"><span data-stu-id="354a3-239">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="354a3-240">O **formulário** não pode ser usado com o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="354a3-240">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="354a3-241">Se **ContentType** for usado, ele será ignorado.</span><span class="sxs-lookup"><span data-stu-id="354a3-241">If **ContentType** is used, it's ignored.</span></span>

<span data-ttu-id="354a3-242">As chaves do dicionário são usadas como os nomes de campo de formulário.</span><span class="sxs-lookup"><span data-stu-id="354a3-242">The keys of the dictionary are used as the form field names.</span></span> <span data-ttu-id="354a3-243">Por padrão, os valores de formulário são convertidos em valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="354a3-243">By default, form values are converted to string values.</span></span>

<span data-ttu-id="354a3-244">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="354a3-244">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="354a3-245">O nome do arquivo é enviado como a propriedade **filename** .</span><span class="sxs-lookup"><span data-stu-id="354a3-245">The name of the file is submitted as the **filename** property.</span></span> <span data-ttu-id="354a3-246">O tipo MIME é definido como `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="354a3-246">The MIME type is set as `application/octet-stream`.</span></span> <span data-ttu-id="354a3-247">`Get-Item` pode ser usado para simplificar o fornecimento do objeto **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="354a3-247">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="354a3-248">Se o valor for um tipo de coleção, tais matrizes ou listas, o campo para será enviado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="354a3-248">If the value is a collection type, such Arrays or Lists, the for field are submitted multiple times.</span></span>
<span data-ttu-id="354a3-249">Os valores da lista são tratados como cadeias de caracteres por padrão.</span><span class="sxs-lookup"><span data-stu-id="354a3-249">The values of the list are treated as strings by default.</span></span> <span data-ttu-id="354a3-250">Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado.</span><span class="sxs-lookup"><span data-stu-id="354a3-250">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="354a3-251">Não há suporte para coleções aninhadas.</span><span class="sxs-lookup"><span data-stu-id="354a3-251">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="354a3-252">No exemplo acima, o `tags` campo é fornecido três vezes no formulário, uma vez para cada `Vacation` , `Italy` e `2017` .</span><span class="sxs-lookup"><span data-stu-id="354a3-252">In the above example the `tags` field are supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="354a3-253">O `pictures` campo também é enviado uma vez para cada arquivo na `2017-Italy` pasta.</span><span class="sxs-lookup"><span data-stu-id="354a3-253">The `pictures` field is also submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="354a3-254">O conteúdo binário dos arquivos nessa pasta é enviado como os valores.</span><span class="sxs-lookup"><span data-stu-id="354a3-254">The binary contents of the files in that folder are submitted as the values.</span></span>

<span data-ttu-id="354a3-255">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-255">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="354a3-256">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="354a3-256">-Headers</span></span>

<span data-ttu-id="354a3-257">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-257">Specifies the headers of the web request.</span></span> <span data-ttu-id="354a3-258">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="354a3-258">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="354a3-259">Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="354a3-259">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="354a3-260">Você não pode usar esse parâmetro para especificar cabeçalhos de **usuário** ou de cookie.</span><span class="sxs-lookup"><span data-stu-id="354a3-260">You can't use this parameter to specify **User-Agent** or cookie headers.</span></span>

<span data-ttu-id="354a3-261">Cabeçalhos relacionados ao conteúdo, como `Content-Type` é substituído quando um objeto **MultipartFormDataContent** é fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="354a3-261">Content related headers, such as `Content-Type` is overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="354a3-262">-InFile</span><span class="sxs-lookup"><span data-stu-id="354a3-262">-InFile</span></span>

<span data-ttu-id="354a3-263">Obtém o conteúdo da solicitação da Web de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-263">Gets the content of the web request from a file.</span></span> <span data-ttu-id="354a3-264">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-264">Enter a path and file name.</span></span> <span data-ttu-id="354a3-265">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="354a3-265">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="354a3-266">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="354a3-266">-MaximumRedirection</span></span>

<span data-ttu-id="354a3-267">Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="354a3-267">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="354a3-268">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="354a3-268">The default value is 5.</span></span> <span data-ttu-id="354a3-269">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="354a3-269">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="354a3-270">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="354a3-270">-MaximumRetryCount</span></span>

<span data-ttu-id="354a3-271">Especifica quantas vezes o PowerShell tenta novamente uma conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="354a3-271">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="354a3-272">Consulte também o parâmetro **RetryIntervalSec** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="354a3-272">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="354a3-273">-Método</span><span class="sxs-lookup"><span data-stu-id="354a3-273">-Method</span></span>

<span data-ttu-id="354a3-274">Especifica o método usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-274">Specifies the method used for the web request.</span></span> <span data-ttu-id="354a3-275">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="354a3-275">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="354a3-276">Padrão</span><span class="sxs-lookup"><span data-stu-id="354a3-276">Default</span></span>
- <span data-ttu-id="354a3-277">Excluir</span><span class="sxs-lookup"><span data-stu-id="354a3-277">Delete</span></span>
- <span data-ttu-id="354a3-278">Obter</span><span class="sxs-lookup"><span data-stu-id="354a3-278">Get</span></span>
- <span data-ttu-id="354a3-279">Head</span><span class="sxs-lookup"><span data-stu-id="354a3-279">Head</span></span>
- <span data-ttu-id="354a3-280">Mesclar</span><span class="sxs-lookup"><span data-stu-id="354a3-280">Merge</span></span>
- <span data-ttu-id="354a3-281">Opções</span><span class="sxs-lookup"><span data-stu-id="354a3-281">Options</span></span>
- <span data-ttu-id="354a3-282">Patch</span><span class="sxs-lookup"><span data-stu-id="354a3-282">Patch</span></span>
- <span data-ttu-id="354a3-283">Postar</span><span class="sxs-lookup"><span data-stu-id="354a3-283">Post</span></span>
- <span data-ttu-id="354a3-284">Put</span><span class="sxs-lookup"><span data-stu-id="354a3-284">Put</span></span>
- <span data-ttu-id="354a3-285">Trace</span><span class="sxs-lookup"><span data-stu-id="354a3-285">Trace</span></span>

<span data-ttu-id="354a3-286">O parâmetro **CustomMethod** pode ser usado para métodos de solicitação não listados acima.</span><span class="sxs-lookup"><span data-stu-id="354a3-286">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="354a3-287">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="354a3-287">-NoProxy</span></span>

<span data-ttu-id="354a3-288">Indica que o cmdlet não deve usar um proxy para acessar o destino.</span><span class="sxs-lookup"><span data-stu-id="354a3-288">Indicates that the cmdlet shouldn't use a proxy to reach the destination.</span></span> <span data-ttu-id="354a3-289">Quando precisar ignorar o proxy configurado no ambiente, use essa opção.</span><span class="sxs-lookup"><span data-stu-id="354a3-289">When you need to bypass the proxy configured in the environment, use this switch.</span></span> <span data-ttu-id="354a3-290">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-290">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-291">-Outfile</span><span class="sxs-lookup"><span data-stu-id="354a3-291">-OutFile</span></span>

<span data-ttu-id="354a3-292">Especifica o arquivo de saída para o qual esse cmdlet salva o corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="354a3-292">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="354a3-293">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-293">Enter a path and file name.</span></span>
<span data-ttu-id="354a3-294">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="354a3-294">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="354a3-295">Por padrão, `Invoke-WebRequest` o retorna os resultados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="354a3-295">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="354a3-296">Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru** .</span><span class="sxs-lookup"><span data-stu-id="354a3-296">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="354a3-297">-PassThru</span><span class="sxs-lookup"><span data-stu-id="354a3-297">-PassThru</span></span>

<span data-ttu-id="354a3-298">Indica que o cmdlet retorna os resultados, além de gravá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-298">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="354a3-299">Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-299">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="354a3-300">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="354a3-300">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="354a3-301">Indica que o cmdlet deve preservar o `Authorization` cabeçalho, quando presente, entre redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="354a3-301">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="354a3-302">Por padrão, o cmdlet retira o `Authorization` cabeçalho antes de redirecionar.</span><span class="sxs-lookup"><span data-stu-id="354a3-302">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="354a3-303">A especificação desse parâmetro desabilita essa lógica nos casos em que o cabeçalho precisa ser enviado para o local de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="354a3-303">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="354a3-304">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-304">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-305">-Proxy</span><span class="sxs-lookup"><span data-stu-id="354a3-305">-Proxy</span></span>

<span data-ttu-id="354a3-306">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="354a3-306">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>
<span data-ttu-id="354a3-307">Digite o URI de um servidor de proxy da rede.</span><span class="sxs-lookup"><span data-stu-id="354a3-307">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="354a3-308">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="354a3-308">-ProxyCredential</span></span>

<span data-ttu-id="354a3-309">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="354a3-309">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="354a3-310">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="354a3-310">The default is the current user.</span></span>

<span data-ttu-id="354a3-311">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , **User@Domain.Com** ou insira um `PSCredential` objeto, como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="354a3-311">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="354a3-312">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-312">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="354a3-313">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-313">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="354a3-314">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="354a3-314">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="354a3-315">Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="354a3-315">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="354a3-316">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-316">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="354a3-317">Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-317">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="354a3-318">-Retomar</span><span class="sxs-lookup"><span data-stu-id="354a3-318">-Resume</span></span>

<span data-ttu-id="354a3-319">Executa uma tentativa de melhor esforço para retomar o download de um arquivo parcial.</span><span class="sxs-lookup"><span data-stu-id="354a3-319">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="354a3-320">**Retomar** requer **outfile** .</span><span class="sxs-lookup"><span data-stu-id="354a3-320">**Resume** requires **OutFile** .</span></span>

<span data-ttu-id="354a3-321">**Retomar** opera apenas no tamanho do arquivo local e no arquivo remoto e não executa nenhuma outra validação que o arquivo local e o arquivo remoto sejam os mesmos.</span><span class="sxs-lookup"><span data-stu-id="354a3-321">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="354a3-322">Se o tamanho do arquivo local for menor do que o tamanho do arquivo remoto, o cmdlet tentará retomar o download do arquivo e acrescentará os bytes restantes ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="354a3-322">If the local file size is smaller than the remote file size, then the cmdlet attempts to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="354a3-323">Se o tamanho do arquivo local for igual ao tamanho do arquivo remoto, nenhuma ação será executada e o cmdlet assumirá que o download já foi concluído.</span><span class="sxs-lookup"><span data-stu-id="354a3-323">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already complete.</span></span>

<span data-ttu-id="354a3-324">Se o tamanho do arquivo local for maior que o tamanho do arquivo remoto, o arquivo local será substituído e todo o arquivo remoto será baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="354a3-324">If the local file size is larger than the remote file size, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="354a3-325">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="354a3-325">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="354a3-326">Se o servidor remoto não oferecer suporte a retomada de download, o arquivo local será substituído e todo o arquivo remoto será baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="354a3-326">If the remote server does not support download resuming, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="354a3-327">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="354a3-327">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="354a3-328">Se o arquivo local não existir, o arquivo local será criado e todo o arquivo remoto será baixado.</span><span class="sxs-lookup"><span data-stu-id="354a3-328">If the local file does not exist, then the local file is created and the entire remote file is downloaded.</span></span> <span data-ttu-id="354a3-329">Esse comportamento é o mesmo que usar **outfile** sem **retomar** .</span><span class="sxs-lookup"><span data-stu-id="354a3-329">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="354a3-330">Esse recurso foi adicionado no PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-330">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="354a3-331">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="354a3-331">-RetryIntervalSec</span></span>

<span data-ttu-id="354a3-332">Especifica o intervalo entre as repetições para a conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido.</span><span class="sxs-lookup"><span data-stu-id="354a3-332">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="354a3-333">Consulte também o parâmetro **MaximumRetryCount** para especificar o número de repetições.</span><span class="sxs-lookup"><span data-stu-id="354a3-333">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="354a3-334">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="354a3-334">-SessionVariable</span></span>

<span data-ttu-id="354a3-335">Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.</span><span class="sxs-lookup"><span data-stu-id="354a3-335">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="354a3-336">Insira um nome de variável sem o símbolo de cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="354a3-336">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="354a3-337">Quando você especifica uma variável de sessão, `Invoke-WebRequest` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="354a3-337">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="354a3-338">Você pode usar a variável na sessão, assim que o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="354a3-338">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="354a3-339">Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="354a3-339">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="354a3-340">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="354a3-340">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="354a3-341">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-341">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="354a3-342">Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="354a3-342">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="354a3-343">O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="354a3-343">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="354a3-344">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="354a3-344">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="354a3-345">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-345">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="354a3-346">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-346">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="354a3-347">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="354a3-347">-SkipCertificateCheck</span></span>

<span data-ttu-id="354a3-348">Ignora as verificações de validação de certificado.</span><span class="sxs-lookup"><span data-stu-id="354a3-348">Skips certificate validation checks.</span></span> <span data-ttu-id="354a3-349">Isso inclui todas as validações, como expiração, revogação, autoridade raiz confiável, etc.</span><span class="sxs-lookup"><span data-stu-id="354a3-349">This includes all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="354a3-350">O uso desse parâmetro não é seguro e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="354a3-350">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="354a3-351">Essa opção destina-se apenas a ser usada em hosts conhecidos usando um certificado autoassinado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="354a3-351">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="354a3-352">Use por sua conta e risco.</span><span class="sxs-lookup"><span data-stu-id="354a3-352">Use at your own risk.</span></span>

<span data-ttu-id="354a3-353">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-353">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-354">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="354a3-354">-SkipHeaderValidation</span></span>

<span data-ttu-id="354a3-355">Indica que o cmdlet deve adicionar cabeçalhos à solicitação sem validação.</span><span class="sxs-lookup"><span data-stu-id="354a3-355">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="354a3-356">Essa opção deve ser usada para sites que exigem valores de cabeçalho que não estão em conformidade com os padrões.</span><span class="sxs-lookup"><span data-stu-id="354a3-356">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="354a3-357">A especificação dessa opção desabilita a validação para permitir que o valor seja passado desmarcado.</span><span class="sxs-lookup"><span data-stu-id="354a3-357">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="354a3-358">Quando especificado, todos os cabeçalhos são adicionados sem validação.</span><span class="sxs-lookup"><span data-stu-id="354a3-358">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="354a3-359">Essa opção desabilita a validação de valores passados para os parâmetros **ContentType** , **Headers** e **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="354a3-359">This switch disables validation for values passed to the **ContentType** , **Headers** and **UserAgent** parameters.</span></span>

<span data-ttu-id="354a3-360">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-360">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="354a3-361">-SkipHttpErrorCheck</span><span class="sxs-lookup"><span data-stu-id="354a3-361">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="354a3-362">Esse parâmetro faz com que o cmdlet ignore os status de erro HTTP e continue a processar as respostas.</span><span class="sxs-lookup"><span data-stu-id="354a3-362">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="354a3-363">As respostas de erro são gravadas no pipeline da mesma forma como se fossem bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="354a3-363">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="354a3-364">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="354a3-364">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="354a3-365">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="354a3-365">-SslProtocol</span></span>

<span data-ttu-id="354a3-366">Define os protocolos SSL/TLS que são permitidos para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-366">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="354a3-367">Por padrão, todos os protocolos SSL/TLS com suporte do sistema são permitidos.</span><span class="sxs-lookup"><span data-stu-id="354a3-367">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="354a3-368">O **SslProtocol** permite limitar a protocolos específicos para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="354a3-368">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="354a3-369">**SslProtocol** usa a enumeração de sinalizador **WebSslProtocol** .</span><span class="sxs-lookup"><span data-stu-id="354a3-369">**SslProtocol** uses the **WebSslProtocol** Flag Enum.</span></span> <span data-ttu-id="354a3-370">É possível fornecer mais de um protocolo usando a notação de sinalizador ou combinando várias opções **WebSslProtocol** com **Bor** , no entanto, não há suporte para o fornecimento de vários protocolos em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="354a3-370">It is possible to supply more than one protocol using flag notation or combining multiple **WebSslProtocol** options with **bor** , however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="354a3-371">Em plataformas não Windows, talvez não seja possível fornecer `'Tls, Tls12'` uma opção.</span><span class="sxs-lookup"><span data-stu-id="354a3-371">On non-Windows platforms it may not be possible to supply `'Tls, Tls12'` as an option.</span></span>

<span data-ttu-id="354a3-372">Esse recurso foi adicionado no PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="354a3-372">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="354a3-373">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="354a3-373">-TimeoutSec</span></span>

<span data-ttu-id="354a3-374">Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="354a3-374">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="354a3-375">O valor padrão, 0, especifica um tempo limite indefinido.</span><span class="sxs-lookup"><span data-stu-id="354a3-375">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="354a3-376">Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="354a3-376">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="354a3-377">-Token</span><span class="sxs-lookup"><span data-stu-id="354a3-377">-Token</span></span>

<span data-ttu-id="354a3-378">O token de portador ou OAuth a ser incluído na solicitação.</span><span class="sxs-lookup"><span data-stu-id="354a3-378">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="354a3-379">O **token** é exigido por determinadas opções de **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="354a3-379">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="354a3-380">Ele não pode ser usado de forma independente.</span><span class="sxs-lookup"><span data-stu-id="354a3-380">It cannot be used independently.</span></span>

<span data-ttu-id="354a3-381">O **token** recebe um `SecureString` que contém o token.</span><span class="sxs-lookup"><span data-stu-id="354a3-381">**Token** takes a `SecureString` containing the token.</span></span> <span data-ttu-id="354a3-382">Para fornecer o token manualmente, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="354a3-382">To supply the token manually use the following:</span></span>

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="354a3-383">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="354a3-383">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="354a3-384">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="354a3-384">-TransferEncoding</span></span>

<span data-ttu-id="354a3-385">Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência.</span><span class="sxs-lookup"><span data-stu-id="354a3-385">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="354a3-386">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="354a3-386">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="354a3-387">Em bloco</span><span class="sxs-lookup"><span data-stu-id="354a3-387">Chunked</span></span>
- <span data-ttu-id="354a3-388">Compactar</span><span class="sxs-lookup"><span data-stu-id="354a3-388">Compress</span></span>
- <span data-ttu-id="354a3-389">Desinflar</span><span class="sxs-lookup"><span data-stu-id="354a3-389">Deflate</span></span>
- <span data-ttu-id="354a3-390">GZip</span><span class="sxs-lookup"><span data-stu-id="354a3-390">GZip</span></span>
- <span data-ttu-id="354a3-391">Identidade</span><span class="sxs-lookup"><span data-stu-id="354a3-391">Identity</span></span>

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

### <span data-ttu-id="354a3-392">-URI</span><span class="sxs-lookup"><span data-stu-id="354a3-392">-Uri</span></span>

<span data-ttu-id="354a3-393">Especifica o Uniform Resource Identifier (URI) do recurso da Internet para o qual a solicitação da Web é enviada.</span><span class="sxs-lookup"><span data-stu-id="354a3-393">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="354a3-394">Insira um URI.</span><span class="sxs-lookup"><span data-stu-id="354a3-394">Enter a URI.</span></span> <span data-ttu-id="354a3-395">Esse parâmetro dá suporte apenas a HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="354a3-395">This parameter supports HTTP or HTTPS only.</span></span>

<span data-ttu-id="354a3-396">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="354a3-396">This parameter is required.</span></span> <span data-ttu-id="354a3-397">O **URI** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="354a3-397">The parameter name **Uri** is optional.</span></span>

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

### <span data-ttu-id="354a3-398">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="354a3-398">-UseBasicParsing</span></span>

<span data-ttu-id="354a3-399">Esse parâmetro foi preterido.</span><span class="sxs-lookup"><span data-stu-id="354a3-399">This parameter has been deprecated.</span></span> <span data-ttu-id="354a3-400">A partir do PowerShell 6.0.0, todas as solicitações da Web usam somente a análise básica.</span><span class="sxs-lookup"><span data-stu-id="354a3-400">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="354a3-401">Esse parâmetro é incluído somente para compatibilidade com versões anteriores e qualquer uso dele não tem nenhum efeito sobre a operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="354a3-401">This parameter is included for backwards compatibility only and any use of it has no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="354a3-402">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="354a3-402">-UseDefaultCredentials</span></span>

<span data-ttu-id="354a3-403">Indica que o cmdlet usa as credenciais do usuário atual para enviar a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-403">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="354a3-404">Isso não pode ser usado com **autenticação** ou **credencial** e pode não ter suporte em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="354a3-404">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="354a3-405">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="354a3-405">-UserAgent</span></span>

<span data-ttu-id="354a3-406">Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.</span><span class="sxs-lookup"><span data-stu-id="354a3-406">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="354a3-407">O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` com pequenas variações para cada sistema operacional e plataforma.</span><span class="sxs-lookup"><span data-stu-id="354a3-407">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="354a3-408">Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari.</span><span class="sxs-lookup"><span data-stu-id="354a3-408">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

<span data-ttu-id="354a3-409">Por exemplo, o comando a seguir usa a cadeia de caracteres do agente do usuário para o Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="354a3-409">For example, the following command uses the user agent string for Internet Explorer:</span></span>

```powershell
Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)
```

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

### <span data-ttu-id="354a3-410">-Websession</span><span class="sxs-lookup"><span data-stu-id="354a3-410">-WebSession</span></span>

<span data-ttu-id="354a3-411">Especifica uma sessão de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-411">Specifies a web request session.</span></span> <span data-ttu-id="354a3-412">Insira o nome da variável, incluindo o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="354a3-412">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="354a3-413">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** .</span><span class="sxs-lookup"><span data-stu-id="354a3-413">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="354a3-414">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-414">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="354a3-415">Cabeçalhos relacionados ao conteúdo, como `Content-Type` , também são substituídos quando um objeto **MultipartFormDataContent** é fornecido para o **corpo** .</span><span class="sxs-lookup"><span data-stu-id="354a3-415">Content related headers, such as `Content-Type`, are also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="354a3-416">Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="354a3-416">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="354a3-417">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="354a3-417">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="354a3-418">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="354a3-418">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="354a3-419">Para criar uma sessão de solicitação da Web, insira um nome de variável, sem um sinal de cifrão, no valor do parâmetro **SessionVariable** de um `Invoke-WebRequest` comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-419">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="354a3-420">`Invoke-WebRequest` cria a sessão e salva-a na variável.</span><span class="sxs-lookup"><span data-stu-id="354a3-420">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="354a3-421">Em comandos posteriores, use a variável como o valor do parâmetro **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="354a3-421">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="354a3-422">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="354a3-422">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="354a3-423">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="354a3-423">CommonParameters</span></span>

<span data-ttu-id="354a3-424">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="354a3-424">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="354a3-425">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="354a3-425">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="354a3-426">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="354a3-426">INPUTS</span></span>

### <span data-ttu-id="354a3-427">System.Object</span><span class="sxs-lookup"><span data-stu-id="354a3-427">System.Object</span></span>

<span data-ttu-id="354a3-428">Você pode canalizar o corpo de uma solicitação da Web para `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="354a3-428">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="354a3-429">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="354a3-429">OUTPUTS</span></span>

### <span data-ttu-id="354a3-430">Microsoft. PowerShell. Commands. BasicHtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="354a3-430">Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject</span></span>

## <span data-ttu-id="354a3-431">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="354a3-431">NOTES</span></span>

<span data-ttu-id="354a3-432">A partir do PowerShell, o 6.0.0 `Invoke-WebRequest` dá suporte apenas à análise básica.</span><span class="sxs-lookup"><span data-stu-id="354a3-432">Beginning with PowerShell 6.0.0 `Invoke-WebRequest` supports basic parsing only.</span></span>

<span data-ttu-id="354a3-433">Para obter mais informações, consulte [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span><span class="sxs-lookup"><span data-stu-id="354a3-433">For more information, see [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span></span>

<span data-ttu-id="354a3-434">Devido às alterações no .NET Core 3,1, o PowerShell 7,0 e superior usam a propriedade [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) para determinar a configuração do proxy.</span><span class="sxs-lookup"><span data-stu-id="354a3-434">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="354a3-435">O valor dessa propriedade é determinado pela sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="354a3-435">The value of this property is determined by your platform:</span></span>

- <span data-ttu-id="354a3-436">**Para o Windows** : lê a configuração de proxy de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="354a3-436">**For Windows** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="354a3-437">Se essas variáveis não forem definidas, a propriedade será derivada das configurações de proxy do usuário.</span><span class="sxs-lookup"><span data-stu-id="354a3-437">If those variables are not defined the property is derived from the user's proxy settings.</span></span>
- <span data-ttu-id="354a3-438">**Para MacOS** : lê a configuração de proxy de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="354a3-438">**For macOS** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="354a3-439">Se essas variáveis não forem definidas, a propriedade será derivada das configurações de proxy do sistema.</span><span class="sxs-lookup"><span data-stu-id="354a3-439">If those variables are not defined the property is derived from the system's proxy settings.</span></span>
- <span data-ttu-id="354a3-440">**Para Linux** : lê a configuração de proxy de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="354a3-440">**For Linux** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="354a3-441">Se essas variáveis não forem definidas, a propriedade inicializará uma instância não configurada que ignora todos os endereços.</span><span class="sxs-lookup"><span data-stu-id="354a3-441">If those variables are not defined the property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="354a3-442">As variáveis de ambiente usadas para `DefaultProxy` inicialização em plataformas baseadas no Windows e no Unix são:</span><span class="sxs-lookup"><span data-stu-id="354a3-442">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="354a3-443">` HTTP_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTP.</span><span class="sxs-lookup"><span data-stu-id="354a3-443">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="354a3-444">`HTTPS_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTPS.</span><span class="sxs-lookup"><span data-stu-id="354a3-444">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="354a3-445">`ALL_PROXY`: o nome do host ou endereço IP do servidor proxy usado em solicitações HTTP e HTTPS no caso `HTTP_PROXY` ou `HTTPS_PROXY` não estão definidas.</span><span class="sxs-lookup"><span data-stu-id="354a3-445">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="354a3-446">`NO_PROXY`: uma lista separada por vírgulas de nomes de host que devem ser excluídos do proxy.</span><span class="sxs-lookup"><span data-stu-id="354a3-446">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="354a3-447">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="354a3-447">RELATED LINKS</span></span>

[<span data-ttu-id="354a3-448">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="354a3-448">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="354a3-449">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="354a3-449">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="354a3-450">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="354a3-450">ConvertTo-Json</span></span>](ConvertTo-Json.md)
