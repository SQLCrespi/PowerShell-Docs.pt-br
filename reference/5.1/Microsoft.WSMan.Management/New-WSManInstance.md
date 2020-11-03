---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: 3936fb0a68b029ca2fcacbd2ab04853fccf09f0c
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196538"
---
# New-WSManInstance

## SINOPSE
Cria uma nova instância de um recurso de gerenciamento.

## SYNTAX

### ComputerName (padrão)

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-WSManInstance` cmdlet cria uma nova instância de um recurso de gerenciamento. Ele usa um URI de recurso e um conjunto de valores ou arquivo de entrada para criar a nova instância do recurso de gerenciamento.

Esse cmdlet usa a camada de transporte/conexão do WinRM para criar a instância do recurso de gerenciamento.

## EXEMPLOS

### Exemplo 1: criar um ouvinte HTTPS

Este comando cria uma instância de um ouvinte HTTPS do WS-Management em todos os endereços IP.

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## PARAMETERS

### -ApplicationName

Especifica o nome do aplicativo na conexão. O valor padrão do parâmetro **ApplicationName** é **WSMan** . O identificador completo para o ponto de extremidade remoto é no seguinte formato:

`<transport>://<server>:<port>/<ApplicationName>`

Por exemplo:

`http://server01:8080/WSMAN`

Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado. Essa configuração padrão de **WSMan** é apropriada para a maioria dos usos. Esse parâmetro é projetado para ser utilizado quando diversos computadores estabelecem conexões remotas com um computador que esteja executando o Windows PowerShell. Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autenticação

Especifica o mecanismo de autenticação a ser usado no servidor. Os valores possíveis são:

- Básico: básico é um esquema no qual o nome de usuário e a senha são enviados em texto não criptografado para o servidor ou proxy.
- Padrão: Use o método de autenticação implementado pelo protocolo WS-Management. Esse é o padrão.
- Resumo: o resumo é um esquema de desafio/resposta que usa uma cadeia de caracteres de dados especificada pelo servidor para o desafio.
- Kerberos: o computador cliente e o servidor se autenticam mutuamente usando certificados Kerberos.
- Negotiate: Negotiate é um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser usado para autenticação. Por exemplo, esse valor de parâmetro permite uma negociação para determinar se o protocolo Kerberos ou NTLM será utilizado.
- CredSSP: Use a autenticação do Credential Security Support Provider (CredSSP), que permite ao usuário delegar credenciais. Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.

> [!CAUTION]
> O CredSSP delega as credenciais do usuário do computador local para um computador remoto. Essa prática aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.

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

### -ComputerName

Especifica o computador no qual se deseja executar a operação de gerenciamento. O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP. Use o nome do computador local, use localhost ou use um ponto ( `.` ) para especificar o computador local. O computador local é o padrão. Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado. É possível redirecionar um valor desse parâmetro para o cmdlet.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Conexãouri

Especifica o ponto de extremidade de conexão.
O formato dessa cadeia de caracteres é:

`<Transport>://<Server>:<Port>/<ApplicationName>`

A seguinte cadeia de caracteres é um valor formatado corretamente para este parâmetro:

`http://Server01:8080/WSMAN`

O URI deve ser totalmente qualificado.

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual. Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou " User@Domain.com ". Ou insira um objeto PSCredential, como um retornado pelo `Get-Credential` cmdlet. Quando você digitar um nome de usuário, uma senha será solicitada.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath

Especifica o caminho de um arquivo usado para criar um recurso de gerenciamento. Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** . Por exemplo, o comando a seguir usa o parâmetro **File** :

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo. O arquivo, `Input.xml` , contém o seguinte conteúdo:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

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

### -OptionSet

Passa um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação. Elas são semelhantes às opções usadas nos shells de linha de comando porque são específicas para o serviço. Qualquer número de opções pode ser especificado.

O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM. Quando o transporte é HTTP, a porta padrão é 80. Quando o transporte é HTTPS, a porta padrão é 443.

Quando você usa HTTPS como o transporte, o valor do parâmetro **ComputerName** deve corresponder ao CN (nome comum) do certificado do servidor. No entanto, se o parâmetro **SkipCNCheck** for especificado como parte do parâmetro **SessionOption** , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor. O parâmetro **SkipCNCheck** deve ser usado somente para computadores confiáveis.

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceURI

Contém o Uniform Resource Identifier (URI) da instância ou classe do recurso. O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.

Um URI consiste em um prefixo e um caminho para um recurso. Por exemplo:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectorSet

Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico. O parâmetro **SelectorSet** é usado quando há mais de uma instância do recurso. O valor do parâmetro **SelectorSet** deve ser uma tabela de hash.

O exemplo a seguir mostra como inserir um valor para esse parâmetro:

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SessionOption

Define um conjunto de opções estendidas para a sessão do WS-Management. Insira um objeto **SessionOption** que você cria usando o `New-WSManSessionOption` cmdlet. Para obter mais informações sobre as opções disponíveis, consulte `New-WSManSessionOption` .

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Especifica que o protocolo Secure Sockets Layer (SSL) deve ser utilizado para estabelecer uma conexão com o computador remoto. Por padrão, SSL não é usado.

O WS-Management criptografa todo o conteúdo do Windows PowerShell que é transmitido pela rede. O parâmetro **UseSSL** permite especificar a proteção adicional do HTTPS em vez de http. Se o SSL não estiver disponível na porta utilizada para a conexão e o parâmetro for especificado, o comando falhará.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Valorset

Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento. Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** . O valor do parâmetro **ValueSet** deve ser uma tabela de hash.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

O `Set-WmiInstance` cmdlet, um cmdlet Instrumentação de gerenciamento do Windows (WMI), é semelhante.
`Set-WmiInstance` usa a camada de conexão/transporte DCOM para criar ou atualizar instâncias do WMI.

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
