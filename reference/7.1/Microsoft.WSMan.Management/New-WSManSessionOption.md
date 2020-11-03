---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: c0730daaed26fac1e8e8023532f201233fd90013
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194264"
---
# New-WSManSessionOption

## SINOPSE
Cria a tabela de hash de opção de sessão para usar como parâmetros de entrada para WS-Management cmdlets.

## SYNTAX

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **New-WSManSessionOption** cria uma tabela de hash de opção de sessão WSMan que pode ser passada para cmdlets WSMan:

- Get-WSManInstance
- Set-WSManInstance
- Invoke-WSManAction
- Connect-WSMan

## EXEMPLOS

### Exemplo 1: criar uma conexão que usa opções de conexão

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Este exemplo cria uma conexão com o computador Server01 remoto usando as opções de conexão definidas por **New-WSManSessionOption** .

O primeiro comando usa **New-WSManSessionOption** para armazenar um conjunto de opções de configuração de conexão na variável $a.
Nesse caso, as opções da sessão definem um tempo de conexão de 30 segundos (30.000 milissegundos).

O segundo comando usa o parâmetro *SessionOption* para passar as credenciais que são armazenadas na variável $A para **Connect-WSMan** .
Em seguida, **Connect-WSMan** se conecta ao computador remoto Server01 usando as opções de sessão especificadas.

O **Connect-WSMan** geralmente é usado no contexto do provedor WSMan para se conectar a um computador remoto, neste caso, o computador Server01.
No entanto, você pode usar o cmdlet para estabelecer conexões com computadores remotos, antes de alterar para o provedor WSMan.
Essas conexões aparecem na lista **ComputerName** .

## PARAMETERS

### -NoEncryption
Indica que a conexão não usa criptografia para operações remotas via HTTP.

Por padrão, o tráfego não criptografado não está habilitado.
Ele deve ser habilitado na configuração local.

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

### -OperationTimeout
Especifica o tempo limite, em milissegundos, para a operação de WS-Management.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyAccessType
Especifica o mecanismo pelo qual o servidor proxy é localizado.
Os valores aceitáveis para esse parâmetro são:

- ProxyIEConfig.
Use a configuração de proxy do Internet Explorer para o usuário atual.
- ProxyWinHttpConfig.
O cliente WSMan usa as configurações de proxy configuradas para WinHTTP, usando o utilitário ProxyCfg.exe.
- ProxyAutoDetect.
Forçar detecção automática de um servidor proxy.
- ProxyNoProxyServer.
Não use um servidor proxy.
Resolva todos os nomes de host localmente.

O valor padrão é ProxyIEConfig.

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyAuthentication
Especifica o método de autenticação a ser usado no proxy.
Os valores aceitáveis para esse parâmetro são:

- Básica.
É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.
- Digest.
É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.
- Negotiate.
É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.
Os exemplos são o protocolo Kerberos e NTLM.

O valor padrão é Negotiate.

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential
Especifica uma conta de usuário que tem permissão para obter acesso por meio de um proxy da Web intermediário.

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

### -SkipCACheck
Especifica que, quando se conecta via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.
Use esta opção somente quando o computador remoto for confiável por outro método, por exemplo, se o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada ou o computador remoto estiver listado como um host confiável na configuração do WS-Management.

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

### -SkipCNCheck
Especifica que o nome comum do certificado (CN) do servidor não precisa corresponder ao nome do host do servidor.
É usado somente em operações remotas usando HTTPS.
Essa opção deve ser usada somente para computadores confiáveis.

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

### -SkipRevocationCheck
Indica que a conexão não valida o status de revogação no certificado do servidor.

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

### -SPNPort
Especifica um número de porta para acrescentar ao SPN (nome da entidade de serviço) de conexão do servidor remoto.
Um SPN é usado quando o mecanismo de autenticação é Kerberos ou Negotiate.

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

### -UseUTF16
Indica que a conexão codifica a solicitação no formato UTF16 em vez do formato UTF8.
O padrão é a codificação UTF8.

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### SessionOption

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

