---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 916c221a4fb0886494a4632e38f25a639d5d414e
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555492"
---
# <span data-ttu-id="23ea9-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="23ea9-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="23ea9-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="23ea9-104">Synopsis</span></span>
<span data-ttu-id="23ea9-105">Envia uma solicitação HTTP ou HTTPS para um serviço Web RESTful.</span><span class="sxs-lookup"><span data-stu-id="23ea9-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="23ea9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="23ea9-106">Syntax</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="23ea9-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="23ea9-107">Description</span></span>

<span data-ttu-id="23ea9-108">O `Invoke-RestMethod` cmdlet envia solicitações HTTP e HTTPS para serviços Web de REST (transferência de estado de reapresentação) que retornam dados estruturados de ricos.</span><span class="sxs-lookup"><span data-stu-id="23ea9-108">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.</span></span>

<span data-ttu-id="23ea9-109">O Windows PowerShell formata a resposta com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="23ea9-109">Windows PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="23ea9-110">Para um RSS ou ATOM feed, o Windows PowerShell retorna o nós de Item ou do XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="23ea9-110">For an RSS or ATOM feed, Windows PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="23ea9-111">Para JSON (JavaScript Object Notation) ou XML, o Windows PowerShell converte (ou desserializa) o conteúdo em objetos.</span><span class="sxs-lookup"><span data-stu-id="23ea9-111">For JavaScript Object Notation (JSON) or XML, Windows PowerShell converts (or deserializes) the content into objects.</span></span>

<span data-ttu-id="23ea9-112">Este cmdlet é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="23ea9-112">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="23ea9-113">Por padrão, o código de script na página da Web pode ser executado quando a página está sendo analisada para popular a `ParsedHtml` propriedade.</span><span class="sxs-lookup"><span data-stu-id="23ea9-113">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="23ea9-114">Use a opção **UseBasicParsing** para suprimir isso.</span><span class="sxs-lookup"><span data-stu-id="23ea9-114">Use the **UseBasicParsing** switch to suppress this.</span></span>

## <span data-ttu-id="23ea9-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="23ea9-115">Examples</span></span>

### <span data-ttu-id="23ea9-116">Exemplo 1: obter o feed RSS do PowerShell</span><span class="sxs-lookup"><span data-stu-id="23ea9-116">Example 1: Get the PowerShell RSS feed</span></span>

```powershell
Invoke-RestMethod -Uri https://devblogs.microsoft.com/powershell/feed/ |
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

<span data-ttu-id="23ea9-117">Esse comando usa o `Invoke-RestMethod` cmdlet para obter informações do feed RSS do blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23ea9-117">This command uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="23ea9-118">O comando usa o `Format-Table` cmdlet para exibir os valores das propriedades **title** e **pubDate** de cada blog em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="23ea9-118">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

### <span data-ttu-id="23ea9-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="23ea9-119">Example 2</span></span>

<span data-ttu-id="23ea9-120">No exemplo a seguir, um usuário executa `Invoke-RestMethod` para executar uma solicitação post em um site da intranet na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-120">In the following example, a user runs `Invoke-RestMethod` to perform a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential

# Next, allow the use of self-signed SSL certificates.

[System.Net.ServicePointManager]::ServerCertificateValidationCallback = { $True }

# Create variables to store the values consumed by the Invoke-RestMethod command.
# The search variable contents are later embedded in the body variable.

$Server = 'server.contoso.com'
$Url = "https://${server}:8089/services/search/jobs/export"
$Search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"

# The cmdlet handles URL encoding. The body variable describes the search criteria, specifies CSV as
# the output mode, and specifies a time period for returned data that starts two days ago and ends
# one day ago. The body variable specifies values for parameters that apply to the particular REST
# API with which Invoke-RestMethod is communicating.

$Body = @{
    search = $Search
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}

# Now, run the Invoke-RestMethod command with all variables in place, specifying a path and file
# name for the resulting CSV output file.

Invoke-RestMethod -Method Post -Uri $url -Credential $Cred -Body $body -OutFile output.csv

{"preview":true,"offset":0,"result":{"sourcetype":"contoso1","count":"9624"}}

{"preview":true,"offset":1,"result":{"sourcetype":"contoso2","count":"152"}}

{"preview":true,"offset":2,"result":{"sourcetype":"contoso3","count":"88494"}}

{"preview":true,"offset":3,"result":{"sourcetype":"contoso4","count":"15277"}}
```

### <span data-ttu-id="23ea9-121">Exemplo 3: passar vários cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="23ea9-121">Example 3: Pass multiple headers</span></span>

<span data-ttu-id="23ea9-122">Este exemplo demonstra como passar vários cabeçalhos de um `hash-table` para uma API REST.</span><span class="sxs-lookup"><span data-stu-id="23ea9-122">This example demonstrates, how to pass multiple headers in from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

<span data-ttu-id="23ea9-123">As APIs geralmente exigem cabeçalhos passados para autenticação, validação, etc.</span><span class="sxs-lookup"><span data-stu-id="23ea9-123">APIs often require passed headers for authentication, validation etc.</span></span>

### <span data-ttu-id="23ea9-124">Exemplo 3: enviando dados de formulário</span><span class="sxs-lookup"><span data-stu-id="23ea9-124">Example 3: Submitting form data</span></span>

<span data-ttu-id="23ea9-125">Quando o corpo é um formulário ou é a saída de outra `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-125">When the body is a form, or it is the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="23ea9-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="23ea9-126">For example:</span></span>

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## <span data-ttu-id="23ea9-127">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="23ea9-127">Parameters</span></span>

### <span data-ttu-id="23ea9-128">-Corpo</span><span class="sxs-lookup"><span data-stu-id="23ea9-128">-Body</span></span>

<span data-ttu-id="23ea9-129">Especifica o corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="23ea9-129">Specifies the body of the request.</span></span> <span data-ttu-id="23ea9-130">O corpo é o conteúdo da solicitação que segue os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="23ea9-130">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="23ea9-131">Também é possível canalizar um valor de corpo para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="23ea9-131">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="23ea9-132">O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.</span><span class="sxs-lookup"><span data-stu-id="23ea9-132">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="23ea9-133">Quando a entrada é uma solicitação GET e o corpo é um IDictionary (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="23ea9-133">When the input is a GET request, and the body is an IDictionary (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="23ea9-134">Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão name=value.</span><span class="sxs-lookup"><span data-stu-id="23ea9-134">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

> [!WARNING]
> <span data-ttu-id="23ea9-135">A saída detalhada de um corpo de POSTAgem terminará com `with -1-byte payload` , embora o tamanho do corpo seja conhecido e enviado no `Content-Length` cabeçalho http.</span><span class="sxs-lookup"><span data-stu-id="23ea9-135">The verbose output of a POST body will end with `with -1-byte payload`, even though the size of the body is both known and sent in the `Content-Length` HTTP header.</span></span>

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

### <span data-ttu-id="23ea9-136">-Certificado</span><span class="sxs-lookup"><span data-stu-id="23ea9-136">-Certificate</span></span>

<span data-ttu-id="23ea9-137">Especifica o certificado do cliente que é usado para uma solicitação da Web segura.</span><span class="sxs-lookup"><span data-stu-id="23ea9-137">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="23ea9-138">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="23ea9-138">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="23ea9-139">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de certificado ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="23ea9-139">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="23ea9-140">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="23ea9-140">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="23ea9-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="23ea9-141">-CertificateThumbprint</span></span>

<span data-ttu-id="23ea9-142">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="23ea9-142">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="23ea9-143">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="23ea9-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="23ea9-144">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="23ea9-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="23ea9-145">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="23ea9-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="23ea9-146">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade do Windows PowerShell ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="23ea9-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell (`Cert:`) drive.</span></span>

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

### <span data-ttu-id="23ea9-147">-ContentType</span><span class="sxs-lookup"><span data-stu-id="23ea9-147">-ContentType</span></span>

<span data-ttu-id="23ea9-148">Especifica o tipo de conteúdo da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-148">Specifies the content type of the web request.</span></span>

<span data-ttu-id="23ea9-149">Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-RestMethod` o definirá o tipo de conteúdo como "application/x-www-form-urlencoded".</span><span class="sxs-lookup"><span data-stu-id="23ea9-149">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to "application/x-www-form-urlencoded".</span></span> <span data-ttu-id="23ea9-150">Caso contrário, o tipo de conteúdo não será especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="23ea9-150">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="23ea9-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="23ea9-151">-Credential</span></span>

<span data-ttu-id="23ea9-152">Especifica uma conta de usuário com permissão para enviar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="23ea9-152">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="23ea9-153">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="23ea9-153">The default is the current user.</span></span>

<span data-ttu-id="23ea9-154">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23ea9-154">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="23ea9-155">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="23ea9-155">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="23ea9-156">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="23ea9-156">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="23ea9-157">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="23ea9-157">-DisableKeepAlive</span></span>

<span data-ttu-id="23ea9-158">Define o valor de **KeepAlive** no cabeçalho HTTP como False.</span><span class="sxs-lookup"><span data-stu-id="23ea9-158">Sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="23ea9-159">Por padrão, **KeepAlive** é Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="23ea9-159">By default, **KeepAlive** is True.</span></span>
<span data-ttu-id="23ea9-160">**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.</span><span class="sxs-lookup"><span data-stu-id="23ea9-160">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: KeepAlive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23ea9-161">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="23ea9-161">-Headers</span></span>

<span data-ttu-id="23ea9-162">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-162">Specifies the headers of the web request.</span></span> <span data-ttu-id="23ea9-163">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-163">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="23ea9-164">Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-164">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="23ea9-165">Você não pode usar esse parâmetro para especificar cabeçalhos UserAgent ou de cookie.</span><span class="sxs-lookup"><span data-stu-id="23ea9-165">You cannot use this parameter to specify UserAgent or cookie headers.</span></span>

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

### <span data-ttu-id="23ea9-166">-InFile</span><span class="sxs-lookup"><span data-stu-id="23ea9-166">-InFile</span></span>

<span data-ttu-id="23ea9-167">Obtém o conteúdo da solicitação da Web de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="23ea9-167">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="23ea9-168">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="23ea9-168">Enter a path and file name.</span></span> <span data-ttu-id="23ea9-169">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="23ea9-169">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="23ea9-170">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="23ea9-170">-MaximumRedirection</span></span>

<span data-ttu-id="23ea9-171">Determina quantas vezes o Windows PowerShell redireciona uma conexão para um URI (Uniform Resource Identifier) alternativo antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="23ea9-171">Determines how many times Windows PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="23ea9-172">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="23ea9-172">The default value is 5.</span></span> <span data-ttu-id="23ea9-173">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="23ea9-173">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="23ea9-174">-Método</span><span class="sxs-lookup"><span data-stu-id="23ea9-174">-Method</span></span>

<span data-ttu-id="23ea9-175">Especifica o método usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-175">Specifies the method used for the web request.</span></span> <span data-ttu-id="23ea9-176">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="23ea9-176">The acceptable values for this parameter are:</span></span>

- `Default`
- `Delete`
- `Get`
- `Head`
- `Merge`
- `Options`
- `Patch`
- `Post`
- `Put`
- `Trace`

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23ea9-177">-Outfile</span><span class="sxs-lookup"><span data-stu-id="23ea9-177">-OutFile</span></span>

<span data-ttu-id="23ea9-178">Salva o corpo da resposta no arquivo de saída especificado.</span><span class="sxs-lookup"><span data-stu-id="23ea9-178">Saves the response body in the specified output file.</span></span> <span data-ttu-id="23ea9-179">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="23ea9-179">Enter a path and file name.</span></span> <span data-ttu-id="23ea9-180">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="23ea9-180">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="23ea9-181">Por padrão, `Invoke-RestMethod` o retorna os resultados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="23ea9-181">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="23ea9-182">Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-182">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="23ea9-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="23ea9-183">-PassThru</span></span>

<span data-ttu-id="23ea9-184">Retorna os resultados, além de gravá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="23ea9-184">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="23ea9-185">Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-185">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="23ea9-186">-Proxy</span><span class="sxs-lookup"><span data-stu-id="23ea9-186">-Proxy</span></span>

<span data-ttu-id="23ea9-187">Usa um servidor proxy para a solicitação, em vez de se conectar diretamente ao recurso de Internet.</span><span class="sxs-lookup"><span data-stu-id="23ea9-187">Uses a proxy server for the request, rather than connecting directly to the Internet resource.</span></span> <span data-ttu-id="23ea9-188">Digite o URI de um servidor de proxy da rede.</span><span class="sxs-lookup"><span data-stu-id="23ea9-188">Enter the URI of a network proxy server.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23ea9-189">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="23ea9-189">-ProxyCredential</span></span>

<span data-ttu-id="23ea9-190">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="23ea9-191">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="23ea9-191">The default is the current user.</span></span>

<span data-ttu-id="23ea9-192">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23ea9-192">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="23ea9-193">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-193">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="23ea9-194">Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-194">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="23ea9-195">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="23ea9-195">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="23ea9-196">Usa as credenciais do usuário atual para acessar o servidor de proxy especificado pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-196">Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="23ea9-197">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-197">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="23ea9-198">Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-198">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="23ea9-199">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="23ea9-199">-SessionVariable</span></span>

<span data-ttu-id="23ea9-200">Cria uma sessão de solicitação da Web e salva-a no valor da variável especificada.</span><span class="sxs-lookup"><span data-stu-id="23ea9-200">Creates a web request session and saves it in the value of the specified variable.</span></span> <span data-ttu-id="23ea9-201">Insira um nome de variável sem o símbolo de cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="23ea9-201">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="23ea9-202">Quando você especifica uma variável de sessão, `Invoke-RestMethod` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23ea9-202">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="23ea9-203">Você pode usar a variável na sessão, assim que o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="23ea9-203">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="23ea9-204">Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="23ea9-204">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="23ea9-205">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-205">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="23ea9-206">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-206">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="23ea9-207">Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-207">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="23ea9-208">O Windows PowerShell usa os dados no objeto de sessão de solicitação da web ao estabelecer a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="23ea9-208">Windows PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="23ea9-209">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-209">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="23ea9-210">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-210">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="23ea9-211">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-211">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="23ea9-212">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="23ea9-212">-TimeoutSec</span></span>

<span data-ttu-id="23ea9-213">Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="23ea9-213">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="23ea9-214">O valor padrão, 0, especifica um tempo limite indefinido.</span><span class="sxs-lookup"><span data-stu-id="23ea9-214">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="23ea9-215">Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir TimeoutSec como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="23ea9-215">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set TimeoutSec to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="23ea9-216">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="23ea9-216">-TransferEncoding</span></span>

<span data-ttu-id="23ea9-217">Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência.</span><span class="sxs-lookup"><span data-stu-id="23ea9-217">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="23ea9-218">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="23ea9-218">The acceptable values for this parameter are:</span></span>

- `Chunked`
- `Compress`
- `Deflate`
- `GZip`
- `Identity`

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

### <span data-ttu-id="23ea9-219">-URI</span><span class="sxs-lookup"><span data-stu-id="23ea9-219">-Uri</span></span>

<span data-ttu-id="23ea9-220">Especifica o identificador de URI (Uniform Resource Identifier) do recurso da Internet para o qual a solicitação da Web é enviada.</span><span class="sxs-lookup"><span data-stu-id="23ea9-220">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="23ea9-221">Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.</span><span class="sxs-lookup"><span data-stu-id="23ea9-221">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="23ea9-222">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-222">This parameter is required.</span></span> <span data-ttu-id="23ea9-223">O nome do parâmetro (**URI**) é opcional.</span><span class="sxs-lookup"><span data-stu-id="23ea9-223">The parameter name (**Uri**) is optional.</span></span>

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

### <span data-ttu-id="23ea9-224">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="23ea9-224">-UseBasicParsing</span></span>

<span data-ttu-id="23ea9-225">Indica que o cmdlet usa análise básica.</span><span class="sxs-lookup"><span data-stu-id="23ea9-225">Indicates that the cmdlet uses basic parsing.</span></span> <span data-ttu-id="23ea9-226">O cmdlet retorna o HTML bruto em um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="23ea9-226">The cmdlet returns the raw HTML in a **String** object.</span></span>

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

### <span data-ttu-id="23ea9-227">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="23ea9-227">-UseDefaultCredentials</span></span>

<span data-ttu-id="23ea9-228">Usa as credenciais do usuário atual para enviar a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-228">Uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="23ea9-229">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="23ea9-229">-UserAgent</span></span>

<span data-ttu-id="23ea9-230">Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-230">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="23ea9-231">O agente de usuário padrão é semelhante a "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0 "com pequenas variações para cada plataforma e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="23ea9-231">The default user agent is similar to "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="23ea9-232">Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands) , como Chrome, Firefox, Internet Explorer, Opera e Safari.</span><span class="sxs-lookup"><span data-stu-id="23ea9-232">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands) class, such as Chrome, FireFox, Internet Explorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="23ea9-233">-Websession</span><span class="sxs-lookup"><span data-stu-id="23ea9-233">-WebSession</span></span>

<span data-ttu-id="23ea9-234">Especifica uma sessão de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-234">Specifies a web request session.</span></span> <span data-ttu-id="23ea9-235">Insira o nome da variável, incluindo o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="23ea9-235">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="23ea9-236">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-236">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="23ea9-237">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-237">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="23ea9-238">Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="23ea9-238">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="23ea9-239">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="23ea9-239">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="23ea9-240">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="23ea9-240">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="23ea9-241">Para criar uma sessão de solicitação da Web, insira um nome de variável (sem um cifrão) no valor do parâmetro **SessionVariable** de um `Invoke-RestMethod` comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-241">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="23ea9-242">`Invoke-RestMethod` cria a sessão e salva-a na variável.</span><span class="sxs-lookup"><span data-stu-id="23ea9-242">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="23ea9-243">Em comandos posteriores, use a variável como o valor do parâmetro **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="23ea9-243">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="23ea9-244">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="23ea9-244">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="23ea9-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23ea9-245">CommonParameters</span></span>

<span data-ttu-id="23ea9-246">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23ea9-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23ea9-247">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23ea9-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23ea9-248">Entradas</span><span class="sxs-lookup"><span data-stu-id="23ea9-248">Inputs</span></span>

### <span data-ttu-id="23ea9-249">System.Object</span><span class="sxs-lookup"><span data-stu-id="23ea9-249">System.Object</span></span>

<span data-ttu-id="23ea9-250">Você pode canalizar o corpo de uma solicitação da Web para `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="23ea9-250">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="23ea9-251">Saídas</span><span class="sxs-lookup"><span data-stu-id="23ea9-251">Outputs</span></span>

### <span data-ttu-id="23ea9-252">System.Xml.Xmldocumento, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System. String</span><span class="sxs-lookup"><span data-stu-id="23ea9-252">System.Xml.XmlDocument, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System.String</span></span>

<span data-ttu-id="23ea9-253">A saída do cmdlet depende do formato do conteúdo que é obtido.</span><span class="sxs-lookup"><span data-stu-id="23ea9-253">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="23ea9-254">PSObject</span><span class="sxs-lookup"><span data-stu-id="23ea9-254">PSObject</span></span>

<span data-ttu-id="23ea9-255">Se a solicitação retornar cadeias de caracteres JSON, `Invoke-RestMethod` retornará um PSObject que representa as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="23ea9-255">If the request returns JSON strings, `Invoke-RestMethod` returns a PSObject that represents the strings.</span></span>

## <span data-ttu-id="23ea9-256">Observações</span><span class="sxs-lookup"><span data-stu-id="23ea9-256">Notes</span></span>

## <span data-ttu-id="23ea9-257">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="23ea9-257">Related Links</span></span>

[<span data-ttu-id="23ea9-258">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="23ea9-258">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="23ea9-259">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="23ea9-259">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="23ea9-260">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="23ea9-260">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
