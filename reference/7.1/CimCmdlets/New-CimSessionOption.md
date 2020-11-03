---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 08e01b73e7e44ca6fc80920e4a2dfe8856ba317f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194788"
---
# New-CimSessionOption

## SINOPSE
Especifica opções avançadas para o cmdlet New-CimSession.

## SYNTAX

### ProtocolTypeSet (padrão)

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### WSManParameterSet

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### DcomParameterSet

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION

O `New-CimSessionOption` cmdlet cria uma instância de um objeto de opções de sessão CIM. Você usa um objeto de opções de sessão CIM como entrada para o `New-CimSession` cmdlet para especificar as opções para uma sessão CIM.

Esse cmdlet tem dois conjuntos de parâmetros, um para opções WsMan e outro para as opções distribuídas de Component Object Model (DCOM). Dependendo de quais parâmetros você usa, o cmdlet retorna uma instância de opções de sessão DCOM ou retorna opções de sessão do WsMan.

## EXEMPLOS

### Exemplo 1: criar um objeto de opções de sessão CIM para DCOM

Este exemplo cria um objeto de opções de sessão CIM para o protocolo DCOM e o armazena em uma variável chamada `$so` . O conteúdo da variável é passado para o `New-CimSession` cmdlet.
`New-CimSession` em seguida, cria uma nova sessão CIM com o servidor remoto chamado Server01, usando as opções definidas na variável.

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### Exemplo 2: criar um objeto de opções de sessão CIM para WsMan

Este exemplo cria um objeto de opções de sessão CIM para o protocolo WsMan. O objeto contém a configuração para o modo de autenticação do **Kerberos** especificado pelo parâmetro **ProxyAuthentication** , as credenciais especificadas pelo parâmetro **ProxyCredential** e especifica que o comando é para ignorar a verificação de autoridade de certificação, ignorar a verificação de CN e usar SSL.

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### Exemplo 3: criar um objeto de opções de sessão CIM com a cultura especificada

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

Este exemplo especifica a cultura que é usada para a sessão CIM. Por padrão, a cultura do cliente é usada durante a execução de operações. No entanto, a cultura padrão pode ser substituída usando o parâmetro **Culture** .

## PARAMETERS

### -Culture

Especifica a cultura da interface do usuário a ser usada para a sessão CIM. Especifique o valor para esse parâmetro usando um dos seguintes formatos:

- Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".
- Uma variável que contém um objeto **CultureInfo** .
- Um comando que obtém um objeto **CultureInfo** , como [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncodePortInServicePrincipalName

Indica que a conexão Kerberos está se conectando a um serviço cujo nome da entidade de serviço (SPN) inclui o número da porta de serviço. Esse tipo de conexão não é comum.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Codificação

Especifica a codificação usada para o protocolo WsMan. Os valores aceitáveis para esse parâmetro são: **Default** , **UTF8** ou **Utf16** .

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HttpPrefix

Especifica a parte da URL HTTP após o nome do computador e o número da porta. Alterar isso não é comum. Por padrão, o valor desse parâmetro é **/WSMan** .

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Representação

Cria uma sessão DCOM para Instrumentação de Gerenciamento do Windows (WMI) usando a representação.

Os valores válidos para esse parâmetro são:

- Padrão: o DCOM pode escolher o nível de representação usando seu algoritmo de negociação de segurança normal.
- Nenhum: o cliente é anônimo para o servidor. O processo do servidor pode representar o cliente, mas o token de representação não contém nenhuma informação e não pode ser usado.
- Identificar: permite que os objetos consultem as credenciais do chamador.
- Impersonate: permite que os objetos usem as credenciais do chamador.
- Delegate: permite que os objetos permitam que outros objetos usem as credenciais do chamador.

Se a **representação** não for especificada, o `New-CimSession` cmdlet usará o valor de **Impersonate** .

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxEnvelopeSizeKB

Especifica o limite de tamanho de mensagens de XML WsMan para qualquer direção.

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoEncryption

Especifica que a criptografia de dados está desativada.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketIntegrity

Especifica que a sessão DCOM criada para o WMI usa Component Object Model a funcionalidade _PacketIntegrity_ (com). Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketIntegrity** definido como **true** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketPrivacy

Cria uma sessão DCOM para o WMI usando o _PACKETPRIVACY_ com. Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketPrivacy** definido como **true** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Especifica o protocolo a ser usado. Os valores aceitáveis para esse parâmetro são: **DCOM** , **Default** ou **WSMan** .

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyAuthentication

Especifica o método de autenticação a ser usado para a resolução de proxy. Os valores aceitáveis para esse parâmetro são: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** ou **CredSsp** .

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCertificateThumbprint

Especifica o certificado de chave pública digital (x. 509) de uma conta de usuário para autenticação de proxy.
Insira a impressão digital do certificado. Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles só podem ser mapeados para contas de usuário locais e não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na unidade certificado do PowerShell:.

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential

Especifica as credenciais a usar para autenticação de proxy. Insira um dos seguintes:

- Uma variável que contém um objeto PSCredential.
- Um comando que obtém um objeto PSCredential, como `Get-Credential`

Se essa opção não for definida, você não poderá especificar nenhuma credencial.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyType

Especifica o mecanismo de resolução de nomes de host a ser usado. Os valores aceitáveis para esse parâmetro são: **None** , **WinHTTP** , **auto** ou **InternetExplorer** .

O valor padrão desse parâmetro é **InternetExplorer** .

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipCACheck

Indica que, ao se conectar via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.

Use esse parâmetro somente quando o computador remoto for confiável usando outro mecanismo, como quando o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada, ou quando o computador remoto estiver listado como um host confiável em uma configuração do WinRM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipCNCheck

Indica que o nome comum do certificado (CN) do servidor não precisa corresponder ao hostname do servidor. Use esse parâmetro para operações remotas somente com computadores confiáveis que usam o protocolo HTTPS.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipRevocationCheck

Indica que a verificação de revogação para certificados de servidor é ignorada. Use esse parâmetro somente para computadores confiáveis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UICulture

Especifica a cultura da interface do usuário a ser usada para a sessão CIM. Especifique o valor para esse parâmetro usando um dos seguintes formatos:

- Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".
- Uma variável que contém um objeto CultureInfo.
- Um comando que obtém um objeto CultureInfo, como `Get-Culture` .

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSsl

Indica que o SSL deve ser usado para estabelecer uma conexão com o computador remoto. Por padrão, SSL não é usado. O WsMan criptografa todo o conteúdo transmitido pela rede, mesmo ao usar HTTP.

Esse parâmetro permite especificar a proteção adicional do HTTPS em vez de HTTP. Se o SSL não estiver disponível na porta usada para a conexão e você especificar esse parâmetro, o comando falhará.

É recomendável que você use esse parâmetro somente quando o parâmetro **PacketPrivacy** não for especificado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita nenhum objeto de entrada.

## SAÍDAS

### CIMSessionOption

Esse cmdlet retorna um objeto que contém informações de opções de sessão CIM.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-ChildItem](../microsoft.powershell.management/get-childitem.md)

[Get-Credential](../microsoft.powershell.security/get-credential.md)

[Get-Culture](../microsoft.powershell.utility/get-culture.md)

[Get-Item](../microsoft.powershell.management/get-item.md)

[New-CimSession](New-CimSession.md)

