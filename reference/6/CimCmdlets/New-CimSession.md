---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 2362940dd07cf6ca65b71660337a647c1090f4e8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194098"
---
# New-CimSession

## SINOPSE

Cria uma sessão CIM.

## SYNTAX

### CredentialParameterSet (padrão)

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### CertificateParameterSet

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## DESCRIPTION

O `New-CimSession` cmdlet cria uma sessão CIM. Uma sessão CIM é um objeto do lado do cliente que representa uma conexão com um computador local ou com um computador remoto. A sessão CIM contém informações sobre a conexão, como **ComputerName** , o protocolo usado ou vários identificadores.

Esse cmdlet retorna um objeto de sessão CIM que pode ser usado por todos os outros cmdlets de CIM.

## EXEMPLOS

### Exemplo 1: criar uma sessão CIM com opções padrão

Este exemplo cria uma sessão CIM local com opções padrão. Se **ComputerName** não for especificado, `New-CimSession` o criará uma sessão DCOM para o computador local.

```powershell
New-CimSession
```

### Exemplo 2: criar uma sessão CIM para um computador específico

Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** .
Por padrão, `New-CimSession` o cria uma sessão do WSMan quando **ComputerName** é especificado.

```powershell
New-CimSession -ComputerName Server01
```

### Exemplo 3: criar uma sessão CIM para vários computadores

Este exemplo cria uma sessão CIM para cada um dos computadores especificados por **ComputerName** , na lista separada por vírgulas.

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### Exemplo 4: criar uma sessão CIM com um nome amigável

Este exemplo cria uma sessão CIM remota para cada um dos computadores especificados por **ComputerName** , na lista separada por vírgulas, e atribui um nome amigável às novas sessões, especificando **Name** .

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

Você pode usar o nome amigável de uma sessão CIM para se referir à sessão em outros cmdlets do CIM, por exemplo, [Get-CimSession](Get-CimSession.md).

### Exemplo 5: criar uma sessão CIM para um computador usando um objeto PSCredential

Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** , usando o objeto **PSCredential** especificado por **Credential** e o tipo de autenticação especificado pela **autenticação** .

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

Você pode criar um objeto **PSCredential** usando o [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.

### Exemplo 6: criar uma sessão CIM para um computador usando uma porta específica

Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** usando a porta TCP especificada pela **porta** .

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### Exemplo 7: criar uma sessão CIM usando DCOM

Este exemplo cria uma sessão CIM usando o protocolo DCOM (Distributed COM) em vez do WSMan.

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## PARAMETERS

### -Autenticação

Especifica o tipo de autenticação usado para as credenciais do usuário. Os valores aceitáveis para esse parâmetro são:

- Padrão
- Digest
- Negotiate
- Básico
- Kerberos
- NtlmDomain
- CredSsp

Você não pode usar o tipo de autenticação **NtlmDomain** para conexão com o computador local. A autenticação **CredSSP** está disponível somente no Windows Vista, no windows Server 2008 e em versões posteriores do Windows.

> [!CAUTION]
> A autenticação CredSSP (provedor de serviços de segurança de credencial) destina-se a comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X. 509) de uma conta de usuário que tem permissão para executar esta ação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use os [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets ou no provedor de certificado do PowerShell.

Para obter mais informações, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Especifica o nome do computador para o qual criar a sessão CIM. Especifique um único nome de computador ou vários nomes de computador separados por uma vírgula.

Se **ComputerName** não for especificado, será criada uma sessão CIM para o computador local. Você pode especificar o valor para o nome do computador em um dos seguintes formatos:

- Um ou mais nomes NetBIOS
- Um ou mais endereços IP
- Um ou mais nomes de domínio totalmente qualificados.

Se o computador estiver em um domínio diferente do usuário, você deverá especificar o nome de domínio totalmente qualificado.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. Se a **credencial** não for especificada, a conta de usuário atual será usada.

Especifique o valor para **Credential** usando um dos seguintes formatos:

- Um nome de usuário: "User01"
- Um nome de domínio e um nome de usuário: "Domínio01 \ Usuário01"
- Um nome principal de usuário: " User@Domain.com "
- Um objeto PSCredential, como um retornado pelo [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.

Quando você digitar um nome de usuário, uma senha será solicitada.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um nome amigável para a sessão CIM.

Você pode usar o nome para se referir à sessão CIM ao usar outros cmdlets, como o [`Get-CimSession`](Get-CimSession.md) cmdlet.
Não é necessário que o nome do computador ou da sessão atual seja exclusivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationTimeoutSec

Duração pela qual o cmdlet aguarda uma resposta do servidor.

Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.

Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para esta conexão.
Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.
As portas padrão são 5985 (a porta de WinRM para HTTP) e 5986 (a porta de WinRM para HTTPS).

Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.
Use os seguintes comandos para configurar o ouvinte:

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

Não use o parâmetro **Port** a menos que seja necessário. A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionOption

Define opções avançadas para a nova sessão CIM. Insira o nome de um objeto **CimSessionOption** criado usando o [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipTestConnection

Por padrão, o `New-CimSession` cmdlet estabelece uma conexão com um ponto de extremidade de WS-Management remoto por dois motivos: para verificar se o servidor remoto está escutando no número da porta especificado usando o parâmetro **Port** e para verificar as credenciais da conta especificada. A verificação é realizada usando uma operação de WS-Identity padrão. Você pode adicionar o parâmetro de opção **SkipTestConnection** se o ponto de extremidade de WS-Management remota não puder usar WS-Identify ou para reduzir o tempo de transmissão de dados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita entradas.

## SAÍDAS

### Microsoft.Management.Infrastructure.CimSession

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-ChildItem](../Microsoft.Powershell.Management/Get-ChildItem.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-Item](../Microsoft.Powershell.Management/Get-Item.md)

[Get-CimSession](Get-CimSession.md)

[Remove-CimSession](Remove-CimSession.md)

[New-CimSessionOption](New-CimSessionOption.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
