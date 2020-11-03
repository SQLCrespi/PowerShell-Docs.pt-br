---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 0b4ec4902df2b2e93def549586e3f6cde70fadee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194930"
---
# Enable-WSManCredSSP

## SINOPSE
Habilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um computador.

## SYNTAX

### Tudo

```
Enable-WSManCredSSP [-Role] <String> [[-DelegateComputer] <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

O `Enable-WSManCredSSP` cmdlet habilita a autenticação CredSSP em um cliente ou em um computador servidor.
Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado. Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota. Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.

`Enable-WSManCredSSP` pode habilitar CredSSP em um **cliente** ou um **servidor** . Para habilitar o CredSSP em um cliente, especifique o **cliente** no parâmetro de **função** . Os clientes delegam credenciais explícitas a um servidor quando a autenticação do servidor é obtida. Para habilitar o CredSSP em um servidor, especifique **servidor** no parâmetro **função** . Um servidor atua como um delegado para clientes. Para obter mais detalhes, consulte **role** na seção Parameters.

> [!CAUTION]
> A autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto. Essa prática aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.

## EXEMPLOS

### Exemplo 1: delegar credenciais de cliente

Este exemplo permite que as credenciais do cliente sejam delegadas a um computador usando o nome de domínio totalmente qualificado.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Exemplo 2: delegar credenciais de cliente a todos os computadores em um domínio

Este exemplo permite que as credenciais do cliente sejam delegadas a todos os computadores no domínio **fabrikam.com** . O curinga asterisco ( `*` ) especifica todos os computadores.

> [!NOTE]
> O uso de caracteres curinga com o parâmetro **DelegateComputer** pode habilitar o CredSSP em mais computadores do que o necessário.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Exemplo 3: delegar credenciais de cliente a vários computadores

Este exemplo permite que as credenciais do cliente sejam delegadas a vários computadores.

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

A `$servers` variável contém uma lista de nomes de servidor. `Enable-WSManCredSSP` usa o parâmetro de **função** para especificar a função de **cliente** . O **DelegateComputer** Obtém os nomes de computador da `$servers` variável.

### Exemplo 4: permitir que um computador atue como um delegado

Este exemplo permite que um computador atue como um delegado para outro. O `Enable-WSManCredSSP` cmdlet, mostrado nos exemplos anteriores, habilita apenas a autenticação CredSSP no cliente e especifica os computadores remotos que podem agir em seu nome. Para que o computador remoto atue como um delegado para o cliente, o item CredSSP no nó de **serviço** do WSMan deve ser definido como true. Este exemplo define o item CredSSP no nó de **serviço** do WSMan como true.

```powershell
Enable-WSManCredSSP -Role "Server"
```

### Exemplo 5: permitir que um computador atue como um delegado usando Set-Item

Este exemplo permite que um computador atue como um delegado para outro computador. Os `Enable-WSManCredSSP` comandos, mostrados nos exemplos anteriores, habilitam a autenticação CredSSP somente no computador cliente e especificam os computadores remotos que podem agir em nome do computador cliente. Para que o computador remoto atue como um delegado do cliente remoto, o item CredSSP do diretório de Serviço do provedor WSMan deve ser definido como true.

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

`Connect-WSMan` Cria uma conexão com o computador remoto, Server02. `Set-Item` usa o parâmetro **path** para especificar o local do provedor do **WSMan** . O parâmetro **Value** define a configuração de **serviço** como true.

## PARAMETERS

### -DelegateComputer

Especifica os servidores para os quais as credenciais de cliente são delegadas. A prática recomendada é usar nomes de domínio totalmente qualificados.

Caracteres curinga são aceitos, mas podem habilitar o CredSSP em mais computadores do que o necessário.

Se o parâmetro de **função** for **cliente** , você deverá especificar esse parâmetro. Se a **função** for **servidor** , não especifique esse parâmetro.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

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

### -Função

Especifica se o CredSSP deve ser habilitado como um cliente ou como um servidor. Os valores aceitáveis para esse parâmetro são: **cliente** e **servidor** .

Se você especificar **cliente** , as ações a seguir serão executadas. Essas configurações permitem que o cliente delegue credenciais explícitas a um servidor quando a autenticação do servidor é obtida.

- Habilita o CredSSP no cliente.
- Define a configuração de WS-Management `\<localhost|computername\>\Client\Auth\CredSSP` como true.
- Define a política **AllowFreshCredentials** do Windows CredSSP como **WSMan/delegate** no cliente.

Se você especificar **servidor** , as ações a seguir serão executadas. Essa configuração de política permite que o servidor aja como um delegado para clientes.

- Habilita CredSSP no servidor.
- Define a configuração de WS-Management `\<localhost|computername\>\Service\Auth\CredSSP` como true.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
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

### Elemento System.Xml.Xml

Se a autenticação CredSSP for habilitada com êxito, esse cmdlet gerará um objeto **XmlElement** .

## OBSERVAÇÕES

Para desabilitar a autenticação CredSSP, use o `Disable-WSManCredSSP` cmdlet.

## LINKS RELACIONADOS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
