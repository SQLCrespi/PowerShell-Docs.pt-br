---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/13/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: c89f7351e9c874cea2cc0cd5e0912e3ca0d8b0bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193777"
---
# Invoke-RestMethod

## Sinopse
Envia uma solicitação HTTP ou HTTPS para um serviço Web RESTful.

## Sintaxe

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## Descrição

O `Invoke-RestMethod` cmdlet envia solicitações HTTP e HTTPS para serviços Web de REST (transferência de estado de reapresentação) que retornam dados estruturados de ricos.

O Windows PowerShell formata a resposta com base no tipo de dados. Para um RSS ou ATOM feed, o Windows PowerShell retorna o nós de Item ou do XML de entrada. Para JSON (JavaScript Object Notation) ou XML, o Windows PowerShell converte (ou desserializa) o conteúdo em objetos.

Este cmdlet é introduzido no Windows PowerShell 3.0.

> [!NOTE]
> Por padrão, o código de script na página da Web pode ser executado quando a página está sendo analisada para popular a `ParsedHtml` propriedade. Use a opção **UseBasicParsing** para suprimir isso.

## Exemplos

### Exemplo 1: obter o feed RSS do PowerShell

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

Esse comando usa o `Invoke-RestMethod` cmdlet para obter informações do feed RSS do blog do PowerShell. O comando usa o `Format-Table` cmdlet para exibir os valores das propriedades **title** e **pubDate** de cada blog em uma tabela.

### Exemplo 2

No exemplo a seguir, um usuário executa `Invoke-RestMethod` para executar uma solicitação post em um site da intranet na organização do usuário.

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

### Exemplo 3: passar vários cabeçalhos

Este exemplo demonstra como passar vários cabeçalhos de um `hash-table` para uma API REST.

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

As APIs geralmente exigem cabeçalhos passados para autenticação, validação, etc.

### Exemplo 3: enviando dados de formulário

Quando o corpo é um formulário ou é a saída de outra `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.

Por exemplo:

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## Parâmetros

### -Corpo

Especifica o corpo da solicitação. O corpo é o conteúdo da solicitação que segue os cabeçalhos.
Também é possível canalizar um valor de corpo para `Invoke-RestMethod` .

O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.

Quando a entrada é uma solicitação GET e o corpo é um IDictionary (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta. Para outros tipos de solicitação (como POST), o corpo é definido como o valor do corpo da solicitação no formato padrão name=value.

> [!WARNING]
> A saída detalhada de um corpo de POSTAgem terminará com `with -1-byte payload` , embora o tamanho do corpo seja conhecido e enviado no `Content-Length` cabeçalho http.

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

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade do Windows PowerShell ( `Cert:` ).

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

Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-RestMethod` o definirá o tipo de conteúdo como "application/x-www-form-urlencoded". Caso contrário, o tipo de conteúdo não será especificado na chamada.

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

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.

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

### -DisableKeepAlive

Define o valor de **KeepAlive** no cabeçalho HTTP como False. Por padrão, **KeepAlive** é Verdadeiro.
**KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.

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

### -Cabeçalhos

Especifica os cabeçalhos da solicitação da Web. Insira uma tabela de hash ou dicionário.

Para definir cabeçalhos UserAgent, use o parâmetro **UserAgent** . Você não pode usar esse parâmetro para especificar cabeçalhos UserAgent ou de cookie.

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

Obtém o conteúdo da solicitação da Web de um arquivo.

Digite um caminho e nome de arquivo. Se você omitir o caminho, o padrão será o local atual.

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

Determina quantas vezes o Windows PowerShell redireciona uma conexão para um URI (Uniform Resource Identifier) alternativo antes de a conexão falhar. O valor padrão é 5. Um valor de 0 (zero) impede qualquer redirecionamento.

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

### -Método

Especifica o método usado para a solicitação da Web. Os valores aceitáveis para esse parâmetro são:

- Padrão
- Excluir
- Obter
- Head
- Mesclar
- Opções
- Patch
- Postar
- Put
- Trace

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

### -Outfile

Salva o corpo da resposta no arquivo de saída especificado. Digite um caminho e nome de arquivo. Se você omitir o caminho, o padrão será o local atual.

Por padrão, `Invoke-RestMethod` o retorna os resultados para o pipeline. Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru** .

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

Retorna os resultados, além de gravá-los em um arquivo. Esse parâmetro será válido somente quando o parâmetro **OutFile** também for utilizado no comando.

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

### -Proxy

Usa um servidor proxy para a solicitação, em vez de se conectar diretamente ao recurso de Internet. Digite o URI de um servidor de proxy da rede.

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

### -ProxyCredential

Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** . O padrão é o usuário atual.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.

Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando. Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.

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

### -ProxyUseDefaultCredentials

Usa as credenciais do usuário atual para acessar o servidor de proxy especificado pelo parâmetro **Proxy** .

Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando. Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.

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

### -SessionVariable

Cria uma sessão de solicitação da Web e salva-a no valor da variável especificada. Insira um nome de variável sem o símbolo de cifrão ( `$` ).

Quando você especifica uma variável de sessão, `Invoke-RestMethod` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell. Você pode usar a variável na sessão, assim que o comando for concluído.

Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente. É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário. Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.

Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession** . O Windows PowerShell usa os dados no objeto de sessão de solicitação da web ao estabelecer a nova conexão. Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** . Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.

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

### -TimeoutSec

Especifica por quanto tempo a solicitação pode estar pendente antes de expirar. Insira um valor em segundos. O valor padrão, 0, especifica um tempo limite indefinido.

Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir TimeoutSec como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma WebException seja lançada e a solicitação atingir o tempo limite.

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

Especifica o identificador de URI (Uniform Resource Identifier) do recurso da Internet para o qual a solicitação da Web é enviada. Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.

Este parâmetro é necessário. O nome do parâmetro ( **URI** ) é opcional.

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

Indica que o cmdlet usa análise básica. O cmdlet retorna o HTML bruto em um objeto de **cadeia de caracteres** .

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

Usa as credenciais do usuário atual para enviar a solicitação da Web.

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

O agente de usuário padrão é semelhante a "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0 "com pequenas variações para cada plataforma e sistema operacional.

Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands) , como Chrome, Firefox, Internet Explorer, Opera e Safari.

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

Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** . Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.

Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente. É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário. Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.

Para criar uma sessão de solicitação da Web, insira um nome de variável (sem um cifrão) no valor do parâmetro **SessionVariable** de um `Invoke-RestMethod` comando. `Invoke-RestMethod` cria a sessão e salva-a na variável. Em comandos posteriores, use a variável como o valor do parâmetro **WebSession** .

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

Você pode canalizar o corpo de uma solicitação da Web para `Invoke-RestMethod` .

## Saídas

### System.Xml.Xmldocumento, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System. String

A saída do cmdlet depende do formato do conteúdo que é obtido.

### PSObject

Se a solicitação retornar cadeias de caracteres JSON, `Invoke-RestMethod` retornará um PSObject que representa as cadeias de caracteres.

## Observações

## Links Relacionados

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)
