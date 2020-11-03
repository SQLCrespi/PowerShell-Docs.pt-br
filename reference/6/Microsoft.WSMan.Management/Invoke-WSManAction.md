---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: b969449d3e2e888138f783c17e16fa696fe40efe
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194984"
---
# Invoke-WSManAction

## SINOPSE
Invoca uma ação no objeto especificado pelo URI de recurso e os seletores.

## SYNTAX

### URI (padrão)

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### ComputerName

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
O **Invoke-WSManAction** executa uma ação no objeto especificado por RESOURCE_URI, em que os parâmetros são especificados por pares chave-valor.

Este cmdlet usa a camada de conexão/transporte do WSMan para realizar a ação.

## EXEMPLOS

### Exemplo 1: invocar um método

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.

O valor de retorno indica se a ação foi ou não bem-sucedida.
Nesse caso, um valor de retorno 0 indica êxito.
Um valor de retorno de 5 indica que o serviço já foi iniciado.

### Exemplo 2: invocar um método

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo.
O arquivo, Input.xml, contém o seguinte conteúdo:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### Exemplo 3: invocar um método com valores de parâmetro especificados

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

Esse comando chama o método **Create** da classe Win32_Process.
Ele passa o método dois valores de parâmetro, Notepad.exe e C:\.
Como resultado, um novo processo é criado para executar o bloco de notas e o diretório atual do novo processo é definido como C:\.

### Exemplo 4: invocar um método em um computador remoto

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.
Como o parâmetro *ComputerName* é especificado, o comando é executado no computador remoto Server01.

## PARAMETERS

### -Action
Especifica o método a ser executado no objeto de gerenciamento especificado pelo ResourceURI e pelos seletores.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName
Especifica o nome do aplicativo na conexão.
O valor padrão do parâmetro *ApplicationName* é WSMan.
O identificador completo para o ponto de extremidade remoto é no seguinte formato:

\<transport\>://\<server\>:\<port\>/\<ApplicationName\>

Por exemplo: `http://server01:8080/WSMAN`

Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.
Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.
Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.
Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autenticação
Especifica o mecanismo de autenticação a ser usado no servidor.
Os valores aceitáveis para esse parâmetro são:

- Básica.
É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.
- Padrão.
Utiliza o método de autenticação implementado pelo protocolo WS-Management.
Esse é o padrão.
- Digest.
É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.
- Kerberos.
O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.
- Negotiate.
É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.
Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.
- CredSSP.
Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.
Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.

Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.
Essa prática aumenta o risco de segurança da operação remota.
Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.

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
Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.
Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente.
Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.

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
Especifica o computador no qual executar a operação de gerenciamento.
O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.
Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.
O computador local é o padrão.
Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.
É possível redirecionar um valor desse parâmetro para o cmdlet.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Conexãouri
Especifica o ponto de extremidade de conexão.
O formato dessa cadeia de caracteres é o seguinte:

\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\>

A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:

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
Especifica uma conta de usuário que tem permissão para executar esta ação.
O padrão é o usuário atual.
Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .
Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.
Quando você digita um nome de usuário, esse cmdlet solicita uma senha.

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
Especifica o caminho de um arquivo usado para atualizar um recurso de gerenciamento.
Você especifica o recurso de gerenciamento usando o parâmetro *ResourceURI* e o parâmetro *SelectorSet* .
Por exemplo, o comando a seguir usa o parâmetro *FilePath* :

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

Esse comando chama o método **StopService** no serviço de **spooler** usando a entrada de um arquivo.
O arquivo, Input.xml, contém o seguinte conteúdo:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptionSet
Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.
Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.
Qualquer número de opções pode ser especificado.

O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Port
Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.
Quando o transporte é HTTP, a porta padrão é 80.
Quando o transporte é HTTPS, a porta padrão é 443.

Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.
No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.
O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.

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
Especifica o URI da classe ou instância de recurso.
O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.

Um URI consiste em um prefixo e um caminho de um recurso.
Por exemplo:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SelectorSet
Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.
*SelectorSet* é usado quando há mais de uma instância do recurso.
O valor de *SelectorSet* deve ser uma tabela de hash.

O exemplo a seguir mostra como inserir um valor para esse parâmetro:

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption
Especifica as opções estendidas para a sessão de WS-Management.
Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.
Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .

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
Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.
Por padrão, SSL não é usado.

WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.
O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.
Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.

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
Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.
Você especifica o recurso de gerenciamento usando *ResourceURI* e *SelectorSet* .
O valor do parâmetro *ValueSet* deve ser uma tabela de hash.

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
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
