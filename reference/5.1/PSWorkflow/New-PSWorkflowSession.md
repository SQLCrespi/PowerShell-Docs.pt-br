---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193657"
---
# New-PSWorkflowSession

## SINOPSE
Cria uma sessão de fluxo de trabalho.

## SYNTAX

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-PSWorkflowSession` cmdlet cria uma sessão gerenciada pelo usuário ( **PSSession** ) que é especialmente projetada para executar fluxos de trabalho do Windows PowerShell. Ele usa a configuração de sessão do Microsoft.PowerShell.Workflow, que inclui scripts, arquivos de tipo e formatação e opções que são necessárias para fluxos de trabalho.

Você pode usar `New-PSWorkflowSession` o ou seu alias, `nwsn` .

Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando. Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: criar uma sessão de fluxo de trabalho em um computador remoto

Este exemplo cria a sessão **WorkflowTests** no computador remoto ServerNode01.

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

O valor do parâmetro **SessionOption** é um `New-PSSessionOption` comando que define o modo de buffer de saída na sessão a ser **descartada** .

### Exemplo 2: criar sessões de fluxo de trabalho em vários computadores remotos

Este exemplo cria sessões de fluxo de trabalho nos computadores ServerNode01 e Server12. O comando usa o parâmetro **Credential** para ser executado com as permissões de um administrador de domínio.

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

O comando usa o parâmetro **ThrottleLimit** para aumentar o limite de restrição por comando para 150.
Esse valor tem precedência sobre o limite de limitação padrão de 100 que é definido na configuração de sessão **Microsoft. PowerShell. Workflow** .

## PARAMETERS

### -ApplicationName

Especifica o segmento de nome de aplicativo do URI de conexão.

O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local. Se esta variável de preferência não estiver definida, o valor padrão é WSMAN. Esse valor é adequado para a maioria dos usos. Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.
O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.

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

### -Autenticação

Especifica o mecanismo usado para autenticar as credenciais do usuário.
Os valores aceitáveis para esse parâmetro são:

- Padrão
- Básico
- CredSSP
- Digest
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

O valor padrão é Default.

A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.

Para obter uma impressão digital do certificado, use o `Get-Item` cmdlet ou o `Get-ChildItem` cmdlet na unidade CERT: do Windows PowerShell.

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

Cria uma conexão persistente ( **PSSession** ) para o computador especificado. Se você inserir vários nomes de computador, o Windows PowerShell criará várias **PSSessions** , uma para cada computador. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos. Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.). Quando o computador está em um domínio diferente do usuário, é necessário o nome de domínio totalmente qualificado. Também é possível canalizar um nome de computador, entre aspas `New-PSWorkflowSession` .

Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** . Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local. Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual. Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com , ou insira um objeto **PSCredential** , como um retornado pelo `Get-Credential` cmdlet.

Quando você digita um nome de usuário, esse cmdlet solicita uma senha.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback. O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores. Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.

Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador. Para criar uma sessão de loopback, não especifique o parâmetro **ComputerName** ou defina seu valor como ponto, localhost ou o nome do computador local.

Por padrão, são criadas sessões de loopback que têm um token de rede, o que pode não fornecer permissão suficiente para autenticar em computadores remotos.

O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback. Se você especificar o parâmetro **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.

Também é possível permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro **Authentication** , que delega as credenciais de sessão a outros computadores.

Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, aquelas criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada. Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores. Para obter mais informações, consulte o cmdlet `Disconnect-PSSession`.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -Name

Especifica um nome amigável para a sessão de fluxo de trabalho. Você pode usar o nome com outros cmdlets, como `Get-PSSession` e `Enter-PSSession` . Não é necessário que o nome do computador ou da sessão atual seja exclusivo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Especifica a porta de rede no computador remoto que é usada para esta conexão. Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão. As portas padrão são 5985 (porta do WinRM para HTTP) e 5986 (porta do WinRM para HTTPS).

Antes de usar outra porta, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta. Use os seguintes comandos para configurar o ouvinte:

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Não use o parâmetro **Port** a menos que seja necessário. A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.

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

### -SessionOption

Especifica as opções avançadas para a sessão. Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet.

Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido. Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.

Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão. Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).

Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .
Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Se você omitir esse parâmetro ou inserir um valor de 0 (zero), o valor padrão para a configuração de sessão **Microsoft. PowerShellWorkflow** , 100, será usado.

O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto. Por padrão, SSL não é usado.

O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede. O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.

Se você especificar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.

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

### System. Management. Automation. Runspaces. PSSession [], System. String

É possível canalizar uma sessão ou um nome de computador para esse cmdlet.

## SAÍDAS

### System. Management. Automation. Runspaces. PSSession

## OBSERVAÇÕES

Um `New-PSWorkflowSession` comando é equivalente ao seguinte comando:

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## LINKS RELACIONADOS

[Disconnect-PSSession](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSTransportOption](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[Register-PSSessionConfiguration](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
