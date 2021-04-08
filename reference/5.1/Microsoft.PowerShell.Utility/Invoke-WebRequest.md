---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 516e73b36668bcb1606df77b0c6f63c3d477ac7c
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027202"
---
# <span data-ttu-id="107a6-102">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="107a6-102">Invoke-WebRequest</span></span>

## <span data-ttu-id="107a6-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="107a6-103">Synopsis</span></span>
<span data-ttu-id="107a6-104">Obtém o conteúdo de uma página da web na Internet.</span><span class="sxs-lookup"><span data-stu-id="107a6-104">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="107a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="107a6-105">Syntax</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="107a6-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="107a6-106">Description</span></span>

<span data-ttu-id="107a6-107">O `Invoke-WebRequest` cmdlet envia solicitações de http, HTTPS, FTP e arquivos para uma página da Web ou serviço Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-107">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="107a6-108">Ele analisa a resposta e retorna conjuntos de formulários, links, imagens e outros elementos HTML significativos.</span><span class="sxs-lookup"><span data-stu-id="107a6-108">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="107a6-109">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="107a6-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="107a6-110">Por padrão, o código de script na página da Web pode ser executado quando a página está sendo analisada para popular a `ParsedHtml` propriedade.</span><span class="sxs-lookup"><span data-stu-id="107a6-110">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="107a6-111">Use a `-UseBasicParsing` opção para suprimir isso.</span><span class="sxs-lookup"><span data-stu-id="107a6-111">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="107a6-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="107a6-112">Examples</span></span>

### <span data-ttu-id="107a6-113">Exemplo 1: Enviar uma solicitação da Web</span><span class="sxs-lookup"><span data-stu-id="107a6-113">Example 1: Send a web request</span></span>

<span data-ttu-id="107a6-114">Esse comando usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação da Web para o site Bing.com.</span><span class="sxs-lookup"><span data-stu-id="107a6-114">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$R = Invoke-WebRequest -URI https://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | Where-Object {
    $_.name -like "* Value" -and $_.tagName -eq "INPUT"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="107a6-115">O primeiro comando emite a solicitação e salva a resposta na `$R` variável.</span><span class="sxs-lookup"><span data-stu-id="107a6-115">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="107a6-116">O segundo comando filtra os objetos **na propriedade** itempropertys, em que a propriedade **Name** é como "\* value" e **TagName** é "Input".</span><span class="sxs-lookup"><span data-stu-id="107a6-116">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="107a6-117">Os resultados filtrados são canalizados para `Select-Object` para selecionar as propriedades **Name** e **Value** .</span><span class="sxs-lookup"><span data-stu-id="107a6-117">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="107a6-118">Exemplo 2: usar um serviço Web com estado</span><span class="sxs-lookup"><span data-stu-id="107a6-118">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="107a6-119">Este exemplo mostra como usar o `Invoke-WebRequest` cmdlet com um serviço Web com estado, como o Facebook.</span><span class="sxs-lookup"><span data-stu-id="107a6-119">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

```powershell
$R = Invoke-WebRequest https://www.facebook.com/login.php -SessionVariable fb
# This command stores the first form in the Forms property of the $R variable in the $Form variable.
$Form = $R.Forms[0]
# This command shows the fields available in the Form.
$Form.fields
```

```Output
Key                     Value
---                     -----
...
email
pass
...
```

```powershell
# These commands populate the username and password of the respective Form fields.
$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
# This command creates the Uri that will be used to log in to facebook.
# The value of the Uri parameter is the value of the Action property of the form.
$Uri = "https://www.facebook.com" + $Form.Action
# Now the Invoke-WebRequest cmdlet is used to sign into the Facebook web service.
# The WebRequestSession object in the $FB variable is passed as the value of the WebSession parameter.
# The value of the Body parameter is the hash table in the Fields property of the form.
# The value of the *Method* parameter is POST. The command saves the output in the $R variable.
$R = Invoke-WebRequest -Uri $Uri -WebSession $FB -Method POST -Body $Form.Fields
$R.StatusDescription
```

<span data-ttu-id="107a6-120">O primeiro comando usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação de entrada.</span><span class="sxs-lookup"><span data-stu-id="107a6-120">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="107a6-121">O comando especifica um valor de "FB" para o valor do parâmetro **SessionVariable** e salva o resultado na `$R` variável.</span><span class="sxs-lookup"><span data-stu-id="107a6-121">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="107a6-122">Quando o comando é concluído, a `$R` variável contém um **HtmlWebResponseObject** e a `$FB` variável contém um objeto **WebRequestSession** .</span><span class="sxs-lookup"><span data-stu-id="107a6-122">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="107a6-123">Depois `Invoke-WebRequest` que o cmdlet entrar no Facebook, a propriedade **StatusDescription** do objeto de resposta da Web na `$R` variável indica que o usuário está conectado com êxito.</span><span class="sxs-lookup"><span data-stu-id="107a6-123">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="107a6-124">Exemplo 3: obter links de uma página da Web</span><span class="sxs-lookup"><span data-stu-id="107a6-124">Example 3: Get links from a web page</span></span>

<span data-ttu-id="107a6-125">Este comando obtém os links em uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-125">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="107a6-126">O `Invoke-WebRequest` cmdlet obtém o conteúdo da página da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-126">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="107a6-127">Em seguida, a propriedade **links** do **HtmlWebResponseObject** retornado é usada para exibir a propriedade **href** de cada link.</span><span class="sxs-lookup"><span data-stu-id="107a6-127">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="107a6-128">Exemplo 4: capturar mensagens de não êxito de Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="107a6-128">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="107a6-129">Quando `Invoke-WebRequest` o encontra uma mensagem http sem êxito (404, 500, etc.), ela não retorna nenhuma saída e gera um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="107a6-129">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="107a6-130">Para capturar o erro e exibir o **StatusCode** , você pode colocar a execução em um `try/catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="107a6-130">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="107a6-131">O exemplo a seguir mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="107a6-131">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost"
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

<span data-ttu-id="107a6-132">O erro de encerramento é capturado pelo `catch` bloco, que recupera o **StatusCode** do objeto de **exceção** .</span><span class="sxs-lookup"><span data-stu-id="107a6-132">The terminating error is caught by the `catch` block, which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="107a6-133">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="107a6-133">Parameters</span></span>

### <span data-ttu-id="107a6-134">-Corpo</span><span class="sxs-lookup"><span data-stu-id="107a6-134">-Body</span></span>

<span data-ttu-id="107a6-135">Especifica o corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="107a6-135">Specifies the body of the request.</span></span>
<span data-ttu-id="107a6-136">O corpo é o conteúdo da solicitação que segue os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="107a6-136">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="107a6-137">Também é possível canalizar um valor de corpo para `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="107a6-137">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="107a6-138">O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.</span><span class="sxs-lookup"><span data-stu-id="107a6-138">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="107a6-139">Quando a entrada é uma solicitação GET e o corpo é um **IDictionary** (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="107a6-139">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="107a6-140">Para outras solicitações GET, o corpo é definido como o valor do corpo da solicitação no formato padrão `name=value` .</span><span class="sxs-lookup"><span data-stu-id="107a6-140">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="107a6-141">Quando o corpo é um formulário ou é a saída de uma `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.</span><span class="sxs-lookup"><span data-stu-id="107a6-141">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="107a6-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="107a6-142">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="107a6-143">ou –</span><span class="sxs-lookup"><span data-stu-id="107a6-143">or -</span></span>

`Invoke-RestMethod https://website.com/service.aspx -Body $r.Forms\[0\]`

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

### <span data-ttu-id="107a6-144">-Certificado</span><span class="sxs-lookup"><span data-stu-id="107a6-144">-Certificate</span></span>

<span data-ttu-id="107a6-145">Especifica o certificado do cliente que é usado para uma solicitação da Web segura.</span><span class="sxs-lookup"><span data-stu-id="107a6-145">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="107a6-146">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="107a6-146">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="107a6-147">Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de **certificado** ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="107a6-147">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="107a6-148">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="107a6-148">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="107a6-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="107a6-149">-CertificateThumbprint</span></span>

<span data-ttu-id="107a6-150">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="107a6-150">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="107a6-151">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="107a6-151">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="107a6-152">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="107a6-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="107a6-153">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="107a6-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="107a6-154">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="107a6-154">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="107a6-155">-ContentType</span><span class="sxs-lookup"><span data-stu-id="107a6-155">-ContentType</span></span>

<span data-ttu-id="107a6-156">Especifica o tipo de conteúdo da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-156">Specifies the content type of the web request.</span></span>

<span data-ttu-id="107a6-157">Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-WebRequest` o definirá o tipo de conteúdo como application/x-www-form-urlencoded.</span><span class="sxs-lookup"><span data-stu-id="107a6-157">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="107a6-158">Caso contrário, o tipo de conteúdo não será especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="107a6-158">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="107a6-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="107a6-159">-Credential</span></span>

<span data-ttu-id="107a6-160">Especifica uma conta de usuário com permissão para enviar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="107a6-160">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="107a6-161">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="107a6-161">The default is the current user.</span></span>

<span data-ttu-id="107a6-162">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="107a6-162">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="107a6-163">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="107a6-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="107a6-164">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="107a6-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="107a6-165">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="107a6-165">-DisableKeepAlive</span></span>

<span data-ttu-id="107a6-166">Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como **false**.</span><span class="sxs-lookup"><span data-stu-id="107a6-166">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="107a6-167">Por padrão, **KeepAlive** é **true**.</span><span class="sxs-lookup"><span data-stu-id="107a6-167">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="107a6-168">**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.</span><span class="sxs-lookup"><span data-stu-id="107a6-168">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="107a6-169">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="107a6-169">-Headers</span></span>

<span data-ttu-id="107a6-170">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-170">Specifies the headers of the web request.</span></span> <span data-ttu-id="107a6-171">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="107a6-171">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="107a6-172">Para definir os cabeçalhos **UserAgent** , use o parâmetro **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="107a6-172">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="107a6-173">Você não pode usar esse parâmetro para especificar cabeçalhos **UserAgent** ou cookie.</span><span class="sxs-lookup"><span data-stu-id="107a6-173">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="107a6-174">-InFile</span><span class="sxs-lookup"><span data-stu-id="107a6-174">-InFile</span></span>

<span data-ttu-id="107a6-175">Obtém o conteúdo da solicitação da Web de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="107a6-175">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="107a6-176">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="107a6-176">Enter a path and file name.</span></span> <span data-ttu-id="107a6-177">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="107a6-177">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="107a6-178">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="107a6-178">-MaximumRedirection</span></span>

<span data-ttu-id="107a6-179">Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar.</span><span class="sxs-lookup"><span data-stu-id="107a6-179">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="107a6-180">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="107a6-180">The default value is 5.</span></span> <span data-ttu-id="107a6-181">Um valor de 0 (zero) impede qualquer redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="107a6-181">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="107a6-182">-Método</span><span class="sxs-lookup"><span data-stu-id="107a6-182">-Method</span></span>

<span data-ttu-id="107a6-183">Especifica o método usado para a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-183">Specifies the method used for the web request.</span></span> <span data-ttu-id="107a6-184">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="107a6-184">The acceptable values for this parameter are:</span></span>

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="107a6-185">-Outfile</span><span class="sxs-lookup"><span data-stu-id="107a6-185">-OutFile</span></span>

<span data-ttu-id="107a6-186">Especifica o arquivo de saída para o qual esse cmdlet salva o corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="107a6-186">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="107a6-187">Digite um caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="107a6-187">Enter a path and file name.</span></span>
<span data-ttu-id="107a6-188">Se você omitir o caminho, o padrão será o local atual.</span><span class="sxs-lookup"><span data-stu-id="107a6-188">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="107a6-189">Por padrão, `Invoke-WebRequest` o retorna os resultados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="107a6-189">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="107a6-190">Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="107a6-190">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="107a6-191">-PassThru</span><span class="sxs-lookup"><span data-stu-id="107a6-191">-PassThru</span></span>

<span data-ttu-id="107a6-192">Indica que o cmdlet retorna os resultados, além de gravá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="107a6-192">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="107a6-193">Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-193">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="107a6-194">-Proxy</span><span class="sxs-lookup"><span data-stu-id="107a6-194">-Proxy</span></span>

<span data-ttu-id="107a6-195">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="107a6-195">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="107a6-196">Digite o URI de um servidor de proxy da rede.</span><span class="sxs-lookup"><span data-stu-id="107a6-196">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="107a6-197">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="107a6-197">-ProxyCredential</span></span>

<span data-ttu-id="107a6-198">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="107a6-198">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="107a6-199">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="107a6-199">The default is the current user.</span></span>

<span data-ttu-id="107a6-200">Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="107a6-200">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="107a6-201">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-201">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="107a6-202">Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-202">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="107a6-203">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="107a6-203">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="107a6-204">Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="107a6-204">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="107a6-205">Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-205">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="107a6-206">Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-206">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="107a6-207">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="107a6-207">-SessionVariable</span></span>

<span data-ttu-id="107a6-208">Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.</span><span class="sxs-lookup"><span data-stu-id="107a6-208">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="107a6-209">Insira um nome de variável sem o símbolo de cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="107a6-209">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="107a6-210">Quando você especifica uma variável de sessão, `Invoke-WebRequest` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="107a6-210">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="107a6-211">Você pode usar a variável na sessão, assim que o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="107a6-211">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="107a6-212">Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="107a6-212">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="107a6-213">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="107a6-213">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="107a6-214">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-214">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="107a6-215">Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="107a6-215">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="107a6-216">O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="107a6-216">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="107a6-217">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**.</span><span class="sxs-lookup"><span data-stu-id="107a6-217">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="107a6-218">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-218">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="107a6-219">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-219">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="107a6-220">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="107a6-220">-TimeoutSec</span></span>

<span data-ttu-id="107a6-221">Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="107a6-221">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="107a6-222">O valor padrão, 0, especifica um tempo limite indefinido.</span><span class="sxs-lookup"><span data-stu-id="107a6-222">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="107a6-223">Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma **WebException** seja lançada e a solicitação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="107a6-223">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="107a6-224">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="107a6-224">-TransferEncoding</span></span>

<span data-ttu-id="107a6-225">Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência.</span><span class="sxs-lookup"><span data-stu-id="107a6-225">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="107a6-226">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="107a6-226">The acceptable values for this parameter are:</span></span>

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

### <span data-ttu-id="107a6-227">-URI</span><span class="sxs-lookup"><span data-stu-id="107a6-227">-Uri</span></span>

<span data-ttu-id="107a6-228">Especifica o identificador de URI (Uniform Resource Identifier) do recurso da Internet para o qual a solicitação da Web é enviada.</span><span class="sxs-lookup"><span data-stu-id="107a6-228">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="107a6-229">Insira um URI.</span><span class="sxs-lookup"><span data-stu-id="107a6-229">Enter a URI.</span></span> <span data-ttu-id="107a6-230">Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.</span><span class="sxs-lookup"><span data-stu-id="107a6-230">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="107a6-231">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="107a6-231">This parameter is required.</span></span>

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

### <span data-ttu-id="107a6-232">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="107a6-232">-UseBasicParsing</span></span>

<span data-ttu-id="107a6-233">Indica que o cmdlet usa o objeto de resposta para conteúdo HTML sem análise Modelo de Objeto do Documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="107a6-233">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="107a6-234">Este parâmetro é obrigatório quando o Internet Explorer não está instalado nos computadores, como em uma instalação Server Core de um sistema operacional Windows Server.</span><span class="sxs-lookup"><span data-stu-id="107a6-234">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="107a6-235">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="107a6-235">-UseDefaultCredentials</span></span>

<span data-ttu-id="107a6-236">Indica que o cmdlet usa as credenciais do usuário atual para enviar a solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-236">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="107a6-237">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="107a6-237">-UserAgent</span></span>

<span data-ttu-id="107a6-238">Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.</span><span class="sxs-lookup"><span data-stu-id="107a6-238">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="107a6-239">O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` com pequenas variações para cada sistema operacional e plataforma.</span><span class="sxs-lookup"><span data-stu-id="107a6-239">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="107a6-240">Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari.</span><span class="sxs-lookup"><span data-stu-id="107a6-240">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="107a6-241">Por exemplo, o comando a seguir usa a cadeia de caracteres do agente do usuário para o Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`</span><span class="sxs-lookup"><span data-stu-id="107a6-241">For example, the following command uses the user agent string for Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`</span></span>

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

### <span data-ttu-id="107a6-242">-Websession</span><span class="sxs-lookup"><span data-stu-id="107a6-242">-WebSession</span></span>

<span data-ttu-id="107a6-243">Especifica uma sessão de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-243">Specifies a web request session.</span></span> <span data-ttu-id="107a6-244">Insira o nome da variável, incluindo o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="107a6-244">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="107a6-245">Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**.</span><span class="sxs-lookup"><span data-stu-id="107a6-245">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="107a6-246">Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-246">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="107a6-247">Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente.</span><span class="sxs-lookup"><span data-stu-id="107a6-247">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="107a6-248">É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="107a6-248">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="107a6-249">Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.</span><span class="sxs-lookup"><span data-stu-id="107a6-249">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="107a6-250">Para criar uma sessão de solicitação da Web, insira um nome de variável (sem um cifrão) no valor do parâmetro **SessionVariable** de um `Invoke-WebRequest` comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-250">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="107a6-251">`Invoke-WebRequest` cria a sessão e salva-a na variável.</span><span class="sxs-lookup"><span data-stu-id="107a6-251">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="107a6-252">Em comandos posteriores, use a variável como o valor do parâmetro **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="107a6-252">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="107a6-253">Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="107a6-253">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="107a6-254">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="107a6-254">CommonParameters</span></span>

<span data-ttu-id="107a6-255">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="107a6-255">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="107a6-256">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="107a6-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="107a6-257">Entradas</span><span class="sxs-lookup"><span data-stu-id="107a6-257">Inputs</span></span>

### <span data-ttu-id="107a6-258">System.Object</span><span class="sxs-lookup"><span data-stu-id="107a6-258">System.Object</span></span>

<span data-ttu-id="107a6-259">Você pode canalizar o corpo de uma solicitação da Web para `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="107a6-259">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="107a6-260">Saídas</span><span class="sxs-lookup"><span data-stu-id="107a6-260">Outputs</span></span>

### <span data-ttu-id="107a6-261">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="107a6-261">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="107a6-262">Observações</span><span class="sxs-lookup"><span data-stu-id="107a6-262">Notes</span></span>

## <span data-ttu-id="107a6-263">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="107a6-263">Related Links</span></span>

[<span data-ttu-id="107a6-264">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="107a6-264">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="107a6-265">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="107a6-265">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="107a6-266">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="107a6-266">ConvertTo-Json</span></span>](ConvertTo-Json.md)
