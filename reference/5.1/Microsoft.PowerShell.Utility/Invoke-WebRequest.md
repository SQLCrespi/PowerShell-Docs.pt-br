---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 25da6262e93be3e3749aabaf4950e2fbcd91ff5c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195141"
---
# Invoke-WebRequest

## SINOPSE
Obtém o conteúdo de uma página da web na Internet.

## SYNTAX

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-WebRequest` cmdlet envia solicitações de http, HTTPS, FTP e arquivos para uma página da Web ou serviço Web.
Ele analisa a resposta e retorna conjuntos de formulários, links, imagens e outros elementos HTML significativos.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

> [!NOTE]
> Por padrão, o código de script na página da Web pode ser executado quando a página está sendo analisada para popular a `ParsedHtml` propriedade.
> Use a `-UseBasicParsing` opção para suprimir isso.

## EXEMPLOS

### Exemplo 1: Enviar uma solicitação da Web

Esse comando usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação da Web para o site Bing.com.

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

O primeiro comando emite a solicitação e salva a resposta na `$R` variável.

O segundo comando filtra os objetos **na propriedade** itempropertys, em que a propriedade **Name** é como "* value" e **TagName** é "Input". Os resultados filtrados são canalizados para `Select-Object` para selecionar as propriedades **Name** e **Value** .

### Exemplo 2: usar um serviço Web com estado

Este exemplo mostra como usar o `Invoke-WebRequest` cmdlet com um serviço Web com estado, como o Facebook.

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

O primeiro comando usa o `Invoke-WebRequest` cmdlet para enviar uma solicitação de entrada. O comando especifica um valor de "FB" para o valor do parâmetro **SessionVariable** e salva o resultado na `$R` variável. Quando o comando é concluído, a `$R` variável contém um **HtmlWebResponseObject** e a `$FB` variável contém um objeto **WebRequestSession** .

Depois `Invoke-WebRequest` que o cmdlet entrar no Facebook, a propriedade **StatusDescription** do objeto de resposta da Web na `$R` variável indica que o usuário está conectado com êxito.

### Exemplo 3: obter links de uma página da Web

Este comando obtém os links em uma página da Web.

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

O `Invoke-WebRequest` cmdlet obtém o conteúdo da página da Web. Em seguida, a propriedade **links** do **HtmlWebResponseObject** retornado é usada para exibir a propriedade **href** de cada link.

### Exemplo 4: capturar mensagens de não êxito de Invoke-WebRequest

Quando `Invoke-WebRequest` o encontra uma mensagem http sem êxito (404, 500, etc.), ela não retorna nenhuma saída e gera um erro de encerramento. Para capturar o erro e exibir o **StatusCode** , você pode colocar a execução em um `try/catch` bloco. O exemplo a seguir mostra como fazer isso.

```powershell
try
{
    $response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
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

O primeiro comando chama `Invoke-WebRequest` **ErrorAction** de **Stop** , que força `Invoke-WebRequest` a gerar um erro de encerramento em todas as solicitações com falha. O erro de encerramento é capturado pelo `catch` bloco que recupera o **StatusCode** do objeto de **exceção** .

## PARAMETERS

### -Corpo

Especifica o corpo da solicitação.
O corpo é o conteúdo da solicitação que segue os cabeçalhos.
Também é possível canalizar um valor de corpo para `Invoke-WebRequest` .

O parâmetro **Body** pode ser usado para especificar uma lista de parâmetros de consulta ou especificar o conteúdo da resposta.

Quando a entrada é uma solicitação GET e o corpo é um **IDictionary** (normalmente, uma tabela de hash), o corpo é adicionado ao URI como parâmetros de consulta. Para outras solicitações GET, o corpo é definido como o valor do corpo da solicitação no formato padrão `name=value` .

Quando o corpo é um formulário ou é a saída de uma `Invoke-WebRequest` chamada, o PowerShell define o conteúdo da solicitação para os campos de formulário.
Por exemplo:

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- ou –

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

### -Certificado

Especifica o certificado do cliente que é usado para uma solicitação da Web segura. Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.

Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade de **certificado** ( `Cert:` ). Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.

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

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa solicitação. Insira a impressão digital do certificado. Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.

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

Se esse parâmetro for omitido e o método de solicitação for POST, `Invoke-WebRequest` o definirá o tipo de conteúdo como application/x-www-form-urlencoded. Caso contrário, o tipo de conteúdo não será especificado na chamada.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableKeepAlive

Indica que o cmdlet define o valor **KeepAlive** no cabeçalho HTTP como **false** . Por padrão, **KeepAlive** é **true** . **KeepAlive** estabelece uma conexão persistente com o servidor para facilitar as solicitações posteriores.

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

### -Cabeçalhos

Especifica os cabeçalhos da solicitação da Web. Insira uma tabela de hash ou dicionário.

Para definir os cabeçalhos **UserAgent** , use o parâmetro **UserAgent** . Você não pode usar esse parâmetro para especificar cabeçalhos **UserAgent** ou cookie.

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

Especifica quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar. O valor padrão é 5. Um valor de 0 (zero) impede qualquer redirecionamento.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outfile

Especifica o arquivo de saída para o qual esse cmdlet salva o corpo da resposta. Digite um caminho e nome de arquivo.
Se você omitir o caminho, o padrão será o local atual.

Por padrão, `Invoke-WebRequest` o retorna os resultados para o pipeline. Para enviar os resultados para um arquivo e para o pipeline, use o parâmetro **Passthru** .

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

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.
Digite o URI de um servidor de proxy da rede.

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

Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.

Esse parâmetro é válido somente quando o parâmetro de **proxy** também é usado no comando. Não é possível usar os parâmetros **ProxyCredential** e **ProxyUseDefaultCredentials** no mesmo comando.

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

### -ProxyUseDefaultCredentials

Indica que o cmdlet usa as credenciais do usuário atual para acessar o servidor proxy especificado pelo parâmetro de **proxy** .

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

Especifica uma variável para a qual esse cmdlet cria uma sessão de solicitação da Web e salva-a no valor.
Insira um nome de variável sem o símbolo de cifrão ( `$` ).

Quando você especifica uma variável de sessão, `Invoke-WebRequest` o cria um objeto de sessão de solicitação da Web e o atribui a uma variável com o nome especificado na sua sessão do PowerShell. Você pode usar a variável na sessão, assim que o comando for concluído.

Diferente de uma sessão remota, a sessão de solicitação da Web não é uma conexão persistente. É um objeto que contém informações sobre a conexão e a solicitação, incluindo cookies, credenciais, o valor máximo de redirecionamento e a cadeia de caracteres de agente do usuário. Você pode usá-lo para compartilhar o estado e os dados entre solicitações da Web.

Para usar a sessão de solicitação da web nas solicitações da Web posteriores, especifique a variável de sessão no valor do parâmetro **WebSession** . O PowerShell usa os dados no objeto de sessão de solicitação da Web ao estabelecer a nova conexão. Para substituir um valor na sessão de solicitação da Web, use um parâmetro de cmdlet, como **UserAgent** ou **Credential** . Valores de parâmetro têm precedência sobre valores na seção de solicitação da Web.

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

Uma consulta DNS (sistema de nomes de domínio) pode levar até 15 segundos para retornar ou atingir o tempo limite. Se sua solicitação contiver um nome de host que requer resolução e você definir **TimeoutSec** como um valor maior que zero, mas menos de 15 segundos, poderá levar 15 segundos ou mais antes que uma **WebException** seja lançada e a solicitação atingir o tempo limite.

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

Especifica o identificador de URI (Uniform Resource Identifier) do recurso da Internet para o qual a solicitação da Web é enviada. Insira um URI. Esse parâmetro oferece suporte a valores HTTP, HTTPS, FTP e FILE.

Este parâmetro é necessário.

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

Indica que o cmdlet usa o objeto de resposta para conteúdo HTML sem análise Modelo de Objeto do Documento (DOM). Este parâmetro é obrigatório quando o Internet Explorer não está instalado nos computadores, como em uma instalação Server Core de um sistema operacional Windows Server.

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

Indica que o cmdet usa as credenciais do usuário atual para enviar a solicitação da Web.

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

Especifica uma cadeia de caracteres de agente do usuário para a solicitação da web. O agente do usuário padrão é semelhante a `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` com pequenas variações para cada sistema operacional e plataforma.

Para testar um site com a cadeia de caracteres do agente de usuário padrão usada pela maioria dos navegadores da Internet, use as propriedades da classe [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) , como Chrome, Firefox, InternetExplorer, Opera e Safari. Por exemplo, o comando a seguir usa a cadeia de caracteres do agente do usuário para o Internet Explorer

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

Para criar uma sessão de solicitação da Web, insira um nome de variável (sem um cifrão) no valor do parâmetro **SessionVariable** de um `Invoke-WebRequest` comando. `Invoke-WebRequest` cria a sessão e salva-a na variável. Em comandos posteriores, use a variável como o valor do parâmetro **WebSession** .

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

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Object

Você pode canalizar o corpo de uma solicitação da Web para `Invoke-WebRequest` .

## SAÍDAS

### Microsoft.PowerShell.Commands.HtmlWebResponseObject

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
