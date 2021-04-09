---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 49fa39807a522c86b94f950ba63c8ff54a112953
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027219"
---
# Invoke-WebRequest

## Sinopse
Obtém o conteúdo de uma página da Web na Internet.

## Syntax

### StandardMethod (padrão)

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

### StandardMethodNoProxy

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

### CustomMethod

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

### CustomMethodNoProxy

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

## Descrição

O `Invoke-WebRequest` cmdlet envia solicitações HTTP e HTTPS para uma página da Web ou serviço Web. Ele analisa a resposta e retorna conjuntos de links, imagens e outros elementos HTML significativos.

Esse cmdlet foi introduzido no PowerShell 3,0.

A partir do PowerShell 7,0, `Invoke-WebRequest` dá suporte à configuração de proxy definida por variáveis de ambiente. Consulte a seção [observações](#notes) deste artigo.

## Exemplos

### Exemplo 1: Enviar uma solicitação da Web

Este exemplo usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação da Web para o site Bing.com.

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

O primeiro comando emite a solicitação e salva a resposta na `$Response` variável.

O segundo comando obtém qualquer **InputField** em que a propriedade **Name** é semelhante `"* Value"` . Os resultados filtrados são canalizados para `Select-Object` para selecionar as propriedades **Name** e **Value** .

### Exemplo 2: usar um serviço Web com estado

Este exemplo mostra como usar o `Invoke-WebRequest` cmdlet com um serviço Web com estado.

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

A primeira chamada para `Invoke-WebRequest` envia uma solicitação de entrada. O comando especifica um valor de "Session" para o valor do parâmetro **-SessionVariable** e salva o resultado na `$LoginResponse` variável. Quando o comando é concluído, a `$LoginResponse` variável contém um `BasicHtmlWebResponseObject` e a `$Session` variável contém um `WebRequestSession` objeto. Isso faz o logon do usuário no site.

A chamada para `$Session` por si só mostra o `WebRequestSession` objeto na variável.

A segunda chamada para `Invoke-WebRequest` busca o perfil do usuário que exige que o usuário seja conectado ao site. Os dados de sessão armazenados na `$Session` variável são usados para fornecer cookies de sessão para o site criado durante o logon. O resultado é salvo na `$ProfileResponse` variável.

A chamada para `$ProfileResponse` por si só mostra o `BasicHtmlWebResponseObject` na variável.

### Exemplo 3: obter links de uma página da Web

Este exemplo obtém os links em uma página da Web. Ele usa o `Invoke-WebRequest` cmdlet para obter o conteúdo da página da Web. Em seguida, ele usa a propriedade **links** do `BasicHtmlWebResponseObject` que `Invoke-WebRequest` retorna e a propriedade **href** de cada link.

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### Exemplo 4: grava o conteúdo da resposta em um arquivo usando a codificação definida na página solicitada.

Este exemplo usa o `Invoke-WebRequest` cmdlet para recuperar o conteúdo da página da Web de uma página de documentação do PowerShell.

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

O primeiro comando recupera a página e salva o objeto de resposta na `$Response` variável.

O segundo comando cria um `StreamWriter` para usar para gravar o conteúdo da resposta em um arquivo. A propriedade **Encoding** do objeto Response é usada para definir a codificação para o arquivo.

Os poucos comandos gravam a propriedade **Content** no arquivo e, em seguida, descarta o `StreamWriter` .

Observe que a propriedade **Encoding** será nula se a solicitação da Web não retornar o conteúdo de texto.

### Exemplo 5: enviar um arquivo com diversas partes/dados de formulário

Este exemplo usa o `Invoke-WebRequest` cmdlet para carregar um arquivo como um `multipart/form-data` envio. O arquivo `c:\document.txt` é enviado como o campo `document` de formulário com o `Content-Type` de `text/plain` .

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

### Exemplo 6: multipart/forma simplificada – envio de dados

Algumas APIs exigem `multipart/form-data` envios de arquivos e conteúdo misto. Este exemplo demonstra a atualização de um perfil de usuário.

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

O formulário de perfil requer estes campos:,,,, `firstName` `lastName` `email` `avatar` `birthday` e `hobbies` . A API está esperando uma imagem para que a PIC do perfil do usuário seja fornecida no `avatar` campo. A API também aceita `hobbies` que várias entradas sejam enviadas na mesma forma.

Ao criar a `$Form` tabela de hash, os nomes de chave são usados como nomes de campo de formulário. Por padrão, os valores da tabela de hash são convertidos em cadeias de caracteres. Se um valor de **System. IO. FileInfo** estiver presente, o conteúdo do arquivo será enviado. Se uma coleção, como matrizes ou listas, estiver presente, o campo de formulário será enviado várias vezes.

Usando `Get-Item` na `avatar` chave, o `FileInfo` objeto é definido como o valor. O resultado é que os dados da imagem para `jdoe.png` são enviados.

Ao fornecer uma lista à `hobbies` chave, o `hobbies` campo está presente nos envios uma vez para cada item de lista.

### Exemplo 7: capturar mensagens de não êxito de Invoke-WebRequest

Quando `Invoke-WebRequest` o encontra uma mensagem http sem êxito (404, 500, etc.), ela não retorna nenhuma saída e gera um erro de encerramento. Para capturar o erro e exibir o **StatusCode** , você pode colocar a execução em um `try/catch` bloco.

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

O erro de encerramento é capturado pelo `catch` bloco, que recupera o **StatusCode** do objeto de **exceção** .

## Parâmetros

### -AllowUnencryptedAuthentication

Permite o envio de credenciais e segredos em conexões não criptografadas. Por padrão, o fornecimento de **credenciais** ou qualquer opção de **autenticação** com um **URI** que não começa com `https://` resulta em um erro e a solicitação é anulada para evitar a comunicação involuntária de segredos em texto sem formatação em conexões não criptografadas. Para substituir esse comportamento por sua conta e risco, forneça o parâmetro **AllowUnencryptedAuthentication** .

> [!WARNING]
> O uso desse parâmetro não é seguro e não é recomendado. Ele é fornecido apenas para compatibilidade com sistemas herdados que não podem fornecer conexões criptografadas. Use por sua conta e risco.

Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -Autenticação

Especifica o tipo de autenticação explícito a ser usado para a solicitação. O padrão é **Nenhum**.
A **autenticação** não pode ser usada com **UseDefaultCredentials**.

Opções de autenticação disponíveis:

- `None`: Essa é a opção padrão quando a **autenticação** não é fornecida; nenhuma autenticação explícita é usada.
- `Basic`: Requer **credencial**. As credenciais são enviadas em um cabeçalho de autenticação básica do RFC 7617 no formato de `base64(user:password)` .
- `Bearer`: Requer **token**. Envia um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido. Este é um alias para **OAuth**
- `OAuth`: Requer **token**. Envia um cabeçalho RFC 6750 `Authorization: Bearer` com o token fornecido. Este é um alias para **portador**

O fornecimento de **autenticação** substitui todos os `Authorization` cabeçalhos fornecidos aos **cabeçalhos** ou incluídos na sessão da **websession**.

Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -Corpo

Especifica o corpo da solicitação. O corpo é o conteúdo da solicitação que segue os cabeçalhos.
Também é possível canalizar um valor de corpo para `Invoke-WebRequest` .

O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.

Quando a entrada é uma solicitação GET e o corpo é um `IDictionary` (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta. Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão `name=value` .

O parâmetro **Body** também pode aceitar um `System.Net.Http.MultipartFormDataContent` objeto. Isso facilita `multipart/form-data` as solicitações. Quando um objeto **MultipartFormDataContent** é fornecido para **o corpo**, todos os cabeçalhos relacionados ao conteúdo fornecidos aos parâmetros **ContentType**, **Headers** ou **websession** são substituídos pelos cabeçalhos de conteúdo do objeto **MultipartFormDataContent** . Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -Certificado

Especifica o certificado do cliente que é usado para uma solicitação da Web segura. Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.

Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de certificado ( `Cert:` ). Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.

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

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; Eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.

> [!NOTE]
> Atualmente, esse recurso só tem suporte em plataformas de sistema operacional Windows.

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

### -ContentType

Especifica o tipo de conteúdo da solicitação da Web.

Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-WebRequest` o definirá o tipo de conteúdo como `application/x-www-form-urlencoded` . Caso contrário, o tipo de conteúdo não será especificado na chamada.

**ContentType** é substituído quando um objeto **MultipartFormDataContent** é fornecido para o **corpo**.

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

### -Credential

Especifica uma conta de usuário com permissão para enviar a solicitação. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.

A **credencial** pode ser usada sozinha ou em conjunto com determinadas opções de parâmetro de **autenticação** . Quando usado sozinho, ele fornece apenas as credenciais para o servidor remoto se o servidor remoto enviar uma solicitação de desafio de autenticação. Quando usado com as opções de **autenticação** , as credenciais são enviadas explicitamente.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomMethod

Especifica um método personalizado usado para a solicitação da Web. Isso pode ser usado se o método de solicitação exigido pelo ponto de extremidade não for uma opção disponível no **método**. O **método** e o **CustomMethod** não podem ser usados juntos.

Este exemplo faz uma `TEST` solicitação HTTP para a API:

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

Esse recurso foi adicionado no PowerShell 6.0.0.

```yaml
Type: System.String
Parameter Sets: CustomMethod, CustomMethodNoProxy
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableKeepAlive

Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como **false**. Por padrão, **KeepAlive** é **true**. **KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.

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

### -Formulário

Converte um dicionário em um `multipart/form-data` envio. O **formulário** não pode ser usado com o **corpo**.
Se **ContentType** for usado, ele será ignorado.

As chaves do dicionário são usadas como os nomes de campo de formulário. Por padrão, os valores de formulário são convertidos em valores de cadeia de caracteres.

Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado. O nome do arquivo é enviado como a propriedade **filename** . O tipo MIME é definido como `application/octet-stream` . `Get-Item` pode ser usado para simplificar o fornecimento do objeto **System. IO. FileInfo** .

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

Se o valor for um tipo de coleção, tais matrizes ou listas, o campo para será enviado várias vezes.
Os valores da lista são tratados como cadeias de caracteres por padrão. Se o valor for um objeto **System. IO. FileInfo** , o conteúdo do arquivo binário será enviado. Não há suporte para coleções aninhadas.

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

No exemplo acima, o `tags` campo é fornecido três vezes no formulário, uma vez para cada `Vacation` , `Italy` e `2017` . O `pictures` campo também é enviado uma vez para cada arquivo na `2017-Italy` pasta. O conteúdo binário dos arquivos nessa pasta é enviado como os valores.

Esse recurso foi adicionado no PowerShell 6.1.0.

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

### -Cabeçalhos

Especifica os cabeçalhos da solicitação da Web. Insira uma tabela de hash ou dicionário.

Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent**. Você não pode usar esse parâmetro para especificar cabeçalhos de **usuário** ou de cookie.

Cabeçalhos relacionados ao conteúdo, como `Content-Type` é substituído quando um objeto **MultipartFormDataContent** é fornecido para o **corpo**.

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

### -InFile

Obtém o conteúdo da solicitação da Web de um arquivo. Digite um caminho e nome de arquivo. Se você omitir o caminho, o padrão será o local atual.

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

### -MaximumRedirection

Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar. O valor padrão é 5. Um valor de 0 (zero) impede qualquer redirecionamento.

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

### -MaximumRetryCount

Especifica quantas vezes o PowerShell tenta novamente uma conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido. Consulte também o parâmetro **RetryIntervalSec** para especificar o número de repetições.

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

### -Método

Especifica o método usado para a solicitação da Web. Os valores aceitáveis para esse parâmetro são:

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

O parâmetro **CustomMethod** pode ser usado para métodos de solicitação não listados acima.

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

### -NoProxy

Indica que o cmdlet não deve usar um proxy para acessar o destino. Quando precisar ignorar o proxy configurado no ambiente, use essa opção. Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -Outfile

Especifica o arquivo de saída para o qual esse cmdlet salva o corpo da resposta. Digite um caminho e nome de arquivo.
Se você omitir o caminho, o padrão será o local atual. O nome é tratado como um caminho literal.
Os nomes que contêm colchetes ( `[]` ) devem ser colocados entre aspas simples ( `'` ).

Por padrão, `Invoke-WebRequest` o retorna os resultados para o pipeline. Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru**.

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

### -PassThru

Indica que o cmdlet retorna os resultados, além de gravá-los em um arquivo. Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.

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

### -PreserveAuthorizationOnRedirect

Indica que o cmdlet deve preservar o `Authorization` cabeçalho, quando presente, entre redirecionamentos.

Por padrão, o cmdlet retira o `Authorization` cabeçalho antes de redirecionar. A especificação desse parâmetro desabilita essa lógica nos casos em que o cabeçalho precisa ser enviado para o local de redirecionamento.

Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.
Digite o URI de um servidor de proxy da rede.

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

### -ProxyCredential

Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**. O padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, **User@Domain.Com** ou insira um `PSCredential` objeto, como um gerado pelo `Get-Credential` cmdlet.

Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando. Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.

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

### -ProxyUseDefaultCredentials

Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .

Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando. Você não pode usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.

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

### -Retomar

Executa uma tentativa de melhor esforço para retomar o download de um arquivo parcial. **Retomar** requer **outfile**.

**Retomar** opera apenas no tamanho do arquivo local e no arquivo remoto e não executa nenhuma outra validação que o arquivo local e o arquivo remoto sejam os mesmos.

Se o tamanho do arquivo local for menor do que o tamanho do arquivo remoto, o cmdlet tentará retomar o download do arquivo e acrescentará os bytes restantes ao final do arquivo.

Se o tamanho do arquivo local for igual ao tamanho do arquivo remoto, nenhuma ação será executada e o cmdlet assumirá que o download já foi concluído.

Se o tamanho do arquivo local for maior que o tamanho do arquivo remoto, o arquivo local será substituído e todo o arquivo remoto será baixado novamente. Esse comportamento é o mesmo que usar **outfile** sem **retomar**.

Se o servidor remoto não oferecer suporte a retomada de download, o arquivo local será substituído e todo o arquivo remoto será baixado novamente. Esse comportamento é o mesmo que usar **outfile** sem **retomar**.

Se o arquivo local não existir, o arquivo local será criado e todo o arquivo remoto será baixado. Esse comportamento é o mesmo que usar **outfile** sem **retomar**.

Esse recurso foi adicionado no PowerShell 6.1.0.

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

### -RetryIntervalSec

Especifica o intervalo entre as repetições para a conexão quando um código de falha entre 400 e 599, inclusive ou 304 é recebido. Consulte também o parâmetro **MaximumRetryCount** para especificar o número de repetições.

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

### -SessionVariable

Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.
Insira um nome de variável sem o símbolo de cifrão ( `$` ).

Quando você especifica uma variável de sessão, `Invoke-WebRequest` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell. Você pode usar a variável na sessão, assim que o comando for concluído.

Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente. É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário. Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.

Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession**. O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão. Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**. Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.

Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.

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

### -SkipCertificateCheck

Ignora as verificações de validação de certificado. Isso inclui todas as validações, como expiração, revogação, autoridade raiz confiável, etc.

> [!WARNING]
> O uso desse parâmetro não é seguro e não é recomendado. Essa opção destina-se apenas a ser usada em hosts conhecidos usando um certificado autoassinado para fins de teste. Use por sua conta e risco.

Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -SkipHeaderValidation

Indica que o cmdlet deve adicionar cabeçalhos à solicitação sem validação.

Essa opção deve ser usada para sites que exigem valores de cabeçalho que não estão em conformidade com os padrões.
A especificação dessa opção desabilita a validação para permitir que o valor seja passado desmarcado. Quando especificado, todos os cabeçalhos são adicionados sem validação.

Essa opção desabilita a validação de valores passados para os parâmetros **ContentType**, **Headers** e **UserAgent** .

Esse recurso foi adicionado no PowerShell 6.0.0.

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

### -SkipHttpErrorCheck

Esse parâmetro faz com que o cmdlet ignore os status de erro HTTP e continue a processar as respostas.
As respostas de erro são gravadas no pipeline da mesma forma como se fossem bem-sucedidas.

Esse parâmetro foi introduzido no PowerShell 7.

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

### -SslProtocol

Define os protocolos SSL/TLS que são permitidos para a solicitação da Web. Por padrão, todos os protocolos SSL/TLS com suporte do sistema são permitidos. O **SslProtocol** permite limitar a protocolos específicos para fins de conformidade.

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro **SslProtocol** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores. Talvez você não consiga definir várias opções em todas as plataformas.

> [!NOTE]
> Em plataformas não Windows, talvez não seja possível fornecer `Tls` ou `Tls12` como uma opção. O suporte para o `Tls13` não está disponível em todos os sistemas operacionais e precisará ser verificado por sistema operacional.

Esse recurso foi adicionado no PowerShell 6.0.0 e o suporte para `Tls13` foi adicionado no powershell 7,1.

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

### -TimeoutSec

Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos. O valor padrão, 0, especifica um tempo limite indefinido.

Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.

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

### -Token

O token de portador ou OAuth a ser incluído na solicitação. O **token** é exigido por determinadas opções de **autenticação** . Ele não pode ser usado de forma independente.

O **token** recebe um `SecureString` que contém o token. Para fornecer o token manualmente, use o seguinte:

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

Esse parâmetro foi introduzido no PowerShell 6,0.

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

### -TransferEncoding

Especifica um valor para o cabeçalho de resposta HTTP de codificação de transferência. Os valores aceitáveis para esse parâmetro são:

- Em bloco
- Compactar
- Desinflar
- GZip
- Identidade

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

### -URI

Especifica o Uniform Resource Identifier (URI) do recurso da Internet para o qual a solicitação da Web é enviada. Insira um URI. Esse parâmetro dá suporte apenas a HTTP ou HTTPS.

Este parâmetro é necessário. O **URI** do nome do parâmetro é opcional.

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

### -UseBasicParsing

Esse parâmetro foi preterido. A partir do PowerShell 6.0.0, todas as solicitações da Web usam somente a análise básica. Esse parâmetro é incluído somente para compatibilidade com versões anteriores e qualquer uso dele não tem nenhum efeito sobre a operação do cmdlet.

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

### -UseDefaultCredentials

Indica que o cmdlet usa as credenciais do usuário atual para enviar a solicitação da Web. Isso não pode ser usado com **autenticação** ou **credencial** e pode não ter suporte em todas as plataformas.

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

### -UserAgent

Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web.

O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` com pequenas variações para cada sistema operacional e plataforma.

Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari.

Por exemplo, o comando a seguir usa a cadeia de caracteres do agente do usuário para o Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`

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

### -Websession

Especifica uma sessão de solicitação da Web. Insira o nome da variável, incluindo o cifrão ( `$` ).

Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential**. Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web. Cabeçalhos relacionados ao conteúdo, como `Content-Type` , também são substituídos quando um objeto **MultipartFormDataContent** é fornecido para o **corpo**.

Ao contrário de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente. É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor de redirecionamento máximo e a cadeia de caracteres do agente do usuário. Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.

Para criar uma sessão de solicitação da Web, insira um nome de variável, sem um sinal de cifrão, no valor do parâmetro **SessionVariable** de um `Invoke-WebRequest` comando. `Invoke-WebRequest` cria a sessão e salva-a na variável. Em comandos posteriores, use a variável como o valor do parâmetro **WebSession**.

Você não pode usar os parâmetros **SessionVariable** e **websession** no mesmo comando.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System.Object

Você pode canalizar o corpo de uma solicitação da Web para `Invoke-WebRequest` .

## Saídas

### Microsoft. PowerShell. Commands. BasicHtmlWebResponseObject

## Observações

A partir do PowerShell, o 6.0.0 `Invoke-WebRequest` dá suporte apenas à análise básica.

Para obter mais informações, consulte [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).

Devido às alterações no .NET Core 3,1, o PowerShell 7,0 e superior usam a propriedade [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) para determinar a configuração do proxy.

O valor dessa propriedade é determinado pela sua plataforma:

- **Para o Windows**: lê a configuração de proxy de variáveis de ambiente. Se essas variáveis não forem definidas, a propriedade será derivada das configurações de proxy do usuário.
- **Para MacOS**: lê a configuração de proxy de variáveis de ambiente. Se essas variáveis não forem definidas, a propriedade será derivada das configurações de proxy do sistema.
- **Para Linux**: lê a configuração de proxy de variáveis de ambiente. Se essas variáveis não forem definidas, a propriedade inicializará uma instância não configurada que ignora todos os endereços.

As variáveis de ambiente usadas para `DefaultProxy` inicialização em plataformas baseadas no Windows e no Unix são:

- `HTTP_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTP.
- `HTTPS_PROXY`: o nome de host ou endereço IP do servidor proxy usado em solicitações HTTPS.
- `ALL_PROXY`: o nome do host ou endereço IP do servidor proxy usado em solicitações HTTP e HTTPS no caso `HTTP_PROXY` ou `HTTPS_PROXY` não estão definidas.
- `NO_PROXY`: uma lista separada por vírgulas de nomes de host que devem ser excluídos do proxy.

## Links Relacionados

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
