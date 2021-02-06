---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: d07942797bad3666a263e017fa8372e672936041
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595988"
---
# New-PSSessionOption

## SINOPSE
Cria um objeto que contém opções avançadas para uma PSSession.

## SYNTAX

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## DESCRIPTION

O `New-PSSessionOption` cmdlet cria um objeto que contém opções avançadas para uma sessão gerenciada pelo usuário (**PSSession**). Você pode usar o objeto como o valor do parâmetro **SessionOption** de cmdlets que criam uma **PSSession**, como `New-PSSession` , `Enter-PSSession` e `Invoke-Command` .

Sem parâmetros, `New-PSSessionOption` o gera um objeto que contém os valores padrão para todas as opções. Como todas as propriedades podem ser editadas, é possível usar o objeto resultante como um modelo e criar objetos de opção padrão para a sua empresa.

Você também pode salvar um objeto de opção de sessão na `$PSSessionOption` variável de preferência. Os valores desta variável estabelecem novos valores padrão para as opções da sessão. Eles tornam-se efetivos quando nenhuma opção de sessão está definida e têm precedência sobre as opções definidas na configuração da sessão, mas você pode substituí-los especificando opções de sessão ou um objeto de opção de sessão em um cmdlet que cria uma sessão. Para obter mais informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

Quando você usa um objeto de opção de sessão em um cmdlet que cria uma sessão, os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na variável de preferência $PSSessionOption e na configuração da sessão. No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão. Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

## EXEMPLOS

### Exemplo 1: criar uma opção de sessão padrão

Este comando cria um objeto de opção de sessão que tem todos os valores padrão.

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### Exemplo 2: configurar uma sessão usando um objeto de opção de sessão

Este exemplo mostra como usar um objeto de opção de sessão para configurar uma sessão.

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

O primeiro comando cria um novo objeto de opção de sessão e o salva no valor da `$pso` variável. O segundo comando usa o `New-PSSession` cmdlet para criar uma sessão no computador remoto Server01. O comando usa o objeto de opção de sessão no valor da `$pso` variável como o valor do parâmetro **SessionOption** do comando.

### Exemplo 3: iniciar uma sessão interativa

Esse comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com o computador Server01.

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

O valor do parâmetro **SessionOption** é um `New-PSSessionOption` comando que tem os parâmetros **NoEncryption** e **NoCompression** .

O `New-PSSessionOption` comando é colocado entre parênteses para garantir que ele seja executado antes do `Enter-PSSession` comando.

### Exemplo 4: modificar um objeto de opção de sessão

Este exemplo demonstra que você pode modificar o objeto de opção de sessão. Todas as propriedades têm valores de leitura/gravação.

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

Use esse método para criar um objeto de sessão padrão para sua empresa e, em seguida, criar versões personalizadas desse objeto para usos específicos.

### Exemplo 5: criar uma variável de preferência

Este comando cria uma `$PSSessionOption` variável de preferência.

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

Quando a `$PSSessionOption` variável de preferência ocorre na sessão, ela estabelece valores padrão para as opções nas sessões criadas usando os `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets, e.

Para disponibilizar a `$PSSessionOption` variável em todas as sessões, adicione-a à sua sessão do PowerShell e ao seu perfil do PowerShell.

Para obter mais informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).
Para obter mais informações sobre perfis, consulte [about_Profiles](About/about_Profiles.md).

### Exemplo 6: atender aos requisitos para uma configuração de sessão remota

Este exemplo mostra como usar um objeto **SessionOption** para atender os requisitos para a configuração de uma sessão remota.

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

O primeiro comando usa o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão que tem a propriedade **SkipCNCheck** . O comando salva o objeto de sessão resultante na `$skipCN` variável.

O segundo comando usa o `New-PSSession` cmdlet para criar uma nova sessão em um computador remoto. A `$skipCN` variável de verificação é usada no valor do parâmetro **SessionOption** .

Como o computador é identificado por seu endereço IP, o valor do parâmetro **ComputerName** não corresponde a nenhum dos nomes comuns no certificado usado para protocolo SSL (SSL). Como resultado, a opção **SkipCNCheck** é obrigatória.

### Exemplo 7: tornar argumentos disponíveis para uma sessão remota

Este exemplo mostra como usar o parâmetro **ApplicationArguments** do `New-PSSessionOption` cmdlet para disponibilizar dados adicionais para a sessão remota.

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

O primeiro comando cria uma tabela de hash com duas chaves, **equipe** e **uso**. O comando salva a tabela de hash na `$team` variável. Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](about/about_Hash_Tables.md).

Em seguida, o `New-PSSessionOption` cmdlet, usando o parâmetro **ApplicationArguments** , cria um objeto de opção de sessão salvo na `$team` variável. Quando `New-PSSessionOption` o cria o objeto de opção de sessão, ele converte automaticamente a tabela de hash no valor do parâmetro **ApplicationArguments** em um dicionário primitivo para que os dados possam ser transmitidos de forma confiável para a sessão remota.

O `New-PSSession` cmdlet inicia uma sessão no computador Server01. Ele usa o parâmetro **SessionOption** para incluir as opções na `$teamOption` variável.

O `Invoke-Command` cmdlet demonstra que os dados na `$team` variável estão disponíveis para comandos na sessão remota. Os dados são exibidos na propriedade **ApplicationArguments** da `$PSSenderInfo` variável automática.

O final `Invoke-Command` mostra como os dados podem ser usados.

## PARAMETERS

### -ApplicationArguments

Especifica um dicionário primitivo que é enviado à sessão remota. Os comandos e scripts na sessão remota, incluindo os scripts de inicialização na configuração da sessão, podem encontrar esse dicionário na propriedade **ApplicationArguments** da `$PSSenderInfo` variável automática. Você pode usar este parâmetro para enviar dados à sessão remota.

Para obter mais informações, consulte [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)e [about_Automatic_Variables](about/about_Automatic_Variables.md).

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CancelTimeout

Determina por quanto tempo o PowerShell aguarda uma operação de cancelamento (CTRL + C) para concluir antes de terminá-la.
Insira um valor em milissegundos.

O valor padrão é 60.000 (um minuto). Um valor de 0 (zero) significa que não há tempo limite; o comando continua indefinidamente.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Especifica a cultura a ser usada para a sessão. Insira um nome de cultura no `<languagecode2>-<country/regioncode2>` formato (como `ja-JP` ), uma variável que contém um objeto **CultureInfo** ou um comando que obtém um objeto **CultureInfo** .

O valor padrão é `$Null` , e a cultura definida no sistema operacional é usada na sessão.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout

Determina por quanto tempo a sessão permanecerá aberta se o computador remoto não receber nenhuma comunicação do computador local. Isso inclui o sinal de pulsação. Quando o intervalo expira, a sessão é fechada.

O valor de tempo limite ocioso é de importância significativa se você pretende desconectar e reconectar-se a uma sessão. Você poderá reconectar-se somente se a sessão não tiver expirado.

Insira um valor em milissegundos. O valor mínimo é 60000 (1 minuto). O máximo é o valor da propriedade **MaxIdleTimeoutms** da configuração de sessão. O valor padrão,-1, não define um tempo limite ocioso.

A sessão usa o tempo limite ocioso definido nas opções de sessão, se houver. Se nenhum for definido (-1), a sessão usará o valor da propriedade **IdleTimeoutMs** da configuração de sessão ou o valor de tempo limite do shell do WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), o que for mais curto.

Se o tempo limite de ociosidade definido nas opções da sessão excede o valor da propriedade **MaxIdleTimeoutMs** da configuração da sessão, o comando para criar uma sessão falha.

O valor de **IdleTimeoutMs** da configuração de sessão padrão do **Microsoft. PowerShell** é de 7,2 milhões milissegundos (2 horas). Seu valor de **MaxIdleTimeoutMs** é de 2147483647 milissegundos ( \> 24 dias). O valor padrão do tempo limite de ociosidade do shell do WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) é de 7,2 milhões milissegundos (2 horas).

O valor de tempo limite ocioso de uma sessão também pode ser alterado ao desconectar-se de uma sessão ou reconectar-se a uma sessão. Para obter mais informações, consulte `Disconnect-PSSession` e `Connect-PSSession`.

No Windows PowerShell 2.0, o valor padrão do parâmetro **IdleTimeout** é 240.000 milissegundos (4 minutos).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludePortInSPN

Inclui o número da porta no nome da entidade de serviço (SPN) usado para autenticação Kerberos, por exemplo, `HTTP://<ComputerName>:5985` . Esta opção permite que um cliente que usa um SPN não padrão faça a autenticação em um computador remoto que usa autenticação Kerberos.

A opção é projetada para empresas nas quais vários serviços que oferecem suporte à autenticação Kerberos estão sendo executados em diferentes contas de usuário. Por exemplo, um aplicativo IIS que permite a autenticação Kerberos pode exigir que o SPN padrão seja registrado para uma conta de usuário diferente da conta do computador. Nesses casos, a comunicação remota do PowerShell não pode usar o Kerberos para autenticar porque requer um SPN registrado na conta do computador. Para resolver esse problema, os administradores podem criar diferentes SPNs, como usando **Setspn.exe**, que são registrados em contas de usuário diferentes e podem distinguir entre eles, incluindo o número da porta no SPN.

Para obter mais informações, consulte [visão geral do SetSPN](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).

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

### -MaxConnectionRetryCount

Especifica o número de vezes que o PowerShell tentará estabelecer uma conexão com um computador de destino se a tentativa atual falhar devido a problemas de rede. O valor padrão é 5.

Esse parâmetro foi adicionado para o PowerShell versão 5,0.

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

### -MaximumReceivedDataSizePerCommand

Especifica o número máximo de bytes que o computador local pode receber do computador remoto em um único comando. Insira um valor em bytes. Por padrão, não há limite de tamanho de dados.

Esta opção foi criada para proteger os recursos no computador cliente.

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

### -MaximumReceivedObjectSize

Especifica o tamanho máximo de um objeto que o computador local pode receber do computador remoto. Esta opção foi criada para proteger os recursos no computador cliente. Insira um valor em bytes.

No Windows PowerShell 2.0, se você omite esse parâmetro, não há limite para tamanho do objeto. A partir do Windows PowerShell 3.0, se você omite esse parâmetro, o valor padrão é 200 MB.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumRedirection

Determina quantas vezes o PowerShell redireciona uma conexão para um Uniform Resource Identifier alternativo (URI) antes de a conexão falhar. O valor padrão é 5. Um valor de 0 (zero) impede qualquer redirecionamento.

Essa opção é usada na sessão somente quando o parâmetro **AllowRedirection** é usado no comando que cria a sessão.

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

### -NoCompression

Desativa a compactação de pacotes na sessão. A compactação utiliza mais ciclos do processador, mas torna a transmissão mais rápida.

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

### -NoEncryption

Desativa a criptografia de dados.

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

### -NoMachineProfile

Impede o carregamento de perfil de usuário do Windows do usuário em questão. Como resultado a sessão pode ser criada mais rapidamente, mas as configurações de registro específicas do usuário, itens como variáveis de ambiente e certificados, não estarão disponíveis nessa sessão.

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

### -OpenTimeout

Determina por quanto tempo o computador cliente aguarda para que a conexão da sessão seja estabelecida. Quando o intervalo expira, o comando para estabelecer a conexão falha. Insira um valor em milissegundos.

O valor padrão é 180.000 (3 minutos). Um valor de 0 (zero) significa que não há tempo limite; o comando continua indefinidamente.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationTimeout

Determina o tempo máximo pelo qual qualquer operação na sessão pode ser executada. Quando o intervalo expira, a operação falha. Insira um valor em milissegundos.

O valor padrão é 180.000 (3 minutos). Um valor de 0 (zero) significa que não há tempo limite; a operação continua indefinidamente.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputBufferingMode

Determina como a saída do comando é gerenciada em sessões desconectadas quando o buffer de saída fica cheio.

Se a o modo de buffering de saída não está definido na sessão ou na configuração da sessão, o valor padrão é **Block**. Os usuários também podem alterar o modo de buffering de saída ao desconectarem-se da sessão.

Se você omitir esse parâmetro, o valor de **OutputBufferingMode** do objeto de opção de sessão será None. Um valor de **Block** ou **Drop** substitui a opção de transporte do modo de buffering de saída, definida na configuração da sessão. Os valores aceitáveis para esse parâmetro são:

- Bloquear. Quando o buffer de saída está cheio, a execução é suspensa até que o buffer esteja limpo.
- Drop. Quando o buffer de saída está cheio, a execução continua. Conforme uma nova saída é salva, a saída mais antiga é descartada.
- Nenhum. Nenhum modo de buffering de saída é especificado.

Para obter mais informações sobre a opção de transporte do modo de buffer de saída, consulte `New-PSTransportOption` .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyAccessType

Determina qual mecanismo é usado para resolver o nome do host. Os valores aceitáveis para esse parâmetro são:

- IEConfig
- WinHttpConfig
- AutoDetect
- NoProxyServer
- Nenhum

O valor padrão é Nenhum.

Para obter informações sobre os valores desse parâmetro, consulte [Enumeração ProxyAccessType](/dotnet/api/system.management.automation.remoting.proxyaccesstype).

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyAuthentication

Especifica o método de autenticação que é usado para resolução de proxy. Os valores aceitáveis para esse parâmetro são: **Basic**, **Digest** e **Negotiate**. O valor padrão é **Negotiate**.

Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential

Especifica as credenciais a usar para autenticação de proxy. Insira uma variável que contém um objeto **PSCredential** ou um comando que obtém um objeto **PSCredential** , como um `Get-Credential` comando. Se esta opção não for definida, nenhuma credencial será especificada.

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

Especifica que quando ele se conecta via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.

Use esta opção somente quando o computador remoto for considerado confiável pelo uso de outro mecanismo, como por exemplo quando o computador remoto é parte de uma rede fisicamente segura e isolada, ou quando o computador remoto está listado como um host confiável em uma configuração de WinRM.

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

### -SkipCNCheck

Especifica que o nome comum do certificado (CN) do servidor não precisa corresponder ao nome do host do servidor. Esta opção é usada somente em operações remotas que usam o protocolo HTTPS.

Use esta opção somente para computadores confiáveis.

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

### -SkipRevocationCheck

Não valida o status de revogação do certificado do servidor.

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

### -UICulture

Especifica a cultura da interface de usuário a ser usada para a sessão.

Os valores válidos incluem:

- Um nome de cultura no `<languagecode2>-<country/regioncode2>` formato, como `ja-JP`
- Uma variável que contém um objeto **CultureInfo**
- Um comando que obtém um objeto **CultureInfo** , como `Get-Culture`

O valor padrão é `$null` , e a cultura da interface do usuário que é definida no sistema operacional quando a sessão é criada é usada na sessão.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseUTF16

Indica que esse cmdlet codifica a solicitação no formato UTF16 em vez do formato UTF8.

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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. Remoting. PSSessionOption

## OBSERVAÇÕES

Se o parâmetro **SessionOption** não for usado em um comando para criar uma **PSSession**, as opções de sessão serão determinadas pelos valores de propriedade da `$PSSessionOption` variável de preferência, se ela estiver definida. Para obter mais informações sobre a `$PSSessionOption` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções. Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.

## LINKS RELACIONADOS

[Enter-PSSession](Enter-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)
