---
description: Descreve os parâmetros que o fluxo de trabalho do Windows PowerShell adiciona às atividades.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: b745bf17e4ae26156042ecdc25211830177bc692
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195813"
---
# <a name="about-activitycommonparameters"></a>Sobre o ActivityCommonParameters

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os parâmetros que o fluxo de trabalho do Windows PowerShell adiciona às atividades.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O fluxo de trabalho do Windows PowerShell adiciona os parâmetros comuns da atividade às atividades derivadas da classe base PSActivity. Essa categoria inclui a atividade InlineScript e os cmdlets do Windows PowerShell que são implementados como atividades, como Get-Process e Get-WinEvent.

Os parâmetros comuns da atividade não são válidos nas atividades Suspend-Workflow e Checkpoint-Workflow e não são adicionados a cmdlets ou expressões que o fluxo de trabalho do Windows PowerShell executa automaticamente em um bloco de script InlineScript ou atividade semelhante. Os parâmetros comuns de atividade estão disponíveis na atividade InlineScript, mas não em comandos do bloco de script InlineScript.

Vários parâmetros comuns de atividade também são parâmetros comuns de fluxo de trabalho ou parâmetros comuns do Windows PowerShell. Outros parâmetros comuns de atividade são exclusivos das atividades.

Para obter informações sobre os parâmetros comuns de fluxos de trabalho, consulte about_WorkflowCommonParameters. Para obter informações sobre os parâmetros comuns do Windows PowerShell, consulte about_CommonParameters.

### <a name="list-of-activity-common-parameters"></a>LISTA DE PARÂMETROS COMUNS DE ATIVIDADE

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a>DESCRIÇÕES DE PARÂMETROS

Esta seção descreve os parâmetros comuns da atividade.

#### <a name="appendoutput-boolean"></a>AppendOutput \<Boolean\>

Um valor de `$True` adiciona a saída da atividade ao valor da variável.
Um valor de `$False` não tem nenhum efeito. De modo padrão, atribuir um valor a uma variável substitui o valor da variável.

Por exemplo, os comandos a seguir adicionam um objeto de processo ao objeto de serviço na `$x` variável.

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

Esse parâmetro é projetado para fluxos de trabalho baseados em XAML. Em fluxos de trabalho de script, você também pode usar o operador de atribuição + = para adicionar saída ao valor de uma variável, conforme mostrado no exemplo a seguir.

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a>Verificação \<SwitchParameter\>

Exibe detalhes no nível do programador sobre a operação executada pelo comando.
O parâmetro Debug substitui o valor da variável $DebugPreference para o comando atual. Esse parâmetro funciona somente quando o comando gera mensagens de depuração. Esse parâmetro também é um parâmetro comum do Windows PowerShell.

#### <a name="displayname-string"></a>DisplayName \<String\>

Especifica um nome amigável para a atividade. O valor DisplayName é exibido na barra de progresso enquanto o fluxo de trabalho é executado e no valor da Propriedade Progress da tarefa Workflow. Quando o parâmetro PSProgressMessage também é incluído no comando, o conteúdo da barra de progresso aparece em \<DisplayName\> : \<PSProgressMessage\> Format.

#### <a name="erroraction-actionpreference"></a>ErrorAction \<ActionPreference\>

Determina como a atividade responde a um erro de não finalização do comando. Ele não tem nenhum efeito sobre erros de encerramento. Esse parâmetro funciona somente quando o comando gera um erro de não finalização, como os do cmdlet Write-Error. O parâmetro ErrorAction substitui o valor da variável $ErrorActionPreference para o comando atual. Esse parâmetro também é um parâmetro comum do Windows PowerShell.

Valores válidos: 

- Continua. Exibe a mensagem de erro e continua executando o comando. "Continue" é o valor padrão.

- Ignorar. Suprime a mensagem de erro e continua executando o comando.
  Ao contrário de SilentlyContinue, ignorar não adiciona a mensagem de erro à $Error variável automática. O valor de ignorar é introduzido no Windows PowerShell 3,0.

- Inquire. Exibe a mensagem de erro e solicita a confirmação antes de continuar a execução. Esse valor raramente é usado.

- Suspend. Suspende automaticamente uma tarefa de fluxo de trabalho para permitir uma investigação adicional. Após a investigação, o fluxo de trabalho pode ser retomado.

- SilentlyContinue. Suprime a mensagem de erro e continua executando o comando.

- Deixar. Exibe a mensagem de erro e para a execução do comando.

#### <a name="input-object"></a>Entrada \<Object[]\>

Envia uma coleção de objetos a uma atividade. Essa é uma alternativa ao redirecionamento de objetos para a atividade, um de cada vez.

#### <a name="mergeerrortooutput-boolean"></a>MergeErrorToOutput \<Boolean\>

Um valor de `$True` adiciona erros ao fluxo de saída. Um valor de `$False` não tem efeito. Use esse parâmetro com as `ForEach -Parallel` palavras-chave e paralelas para coletar erros e saída de vários comandos paralelos em uma única coleção.

#### <a name="psactionretrycount-int32"></a>PSActionRetryCount \<Int32\>

Tenta repetidamente executar a atividade, caso a primeira tentativa falhe. O valor padrão, 0, não tenta novamente.

#### <a name="psactionretryintervalsec-int32"></a>PSActionRetryIntervalSec \<Int32\>

Determina o intervalo entre as tentativas de ação em segundos. O valor padrão, 0, repete a ação imediatamente. Esse parâmetro é válido somente quando o parâmetro PSActionRetryCount também é usado no comando.

#### <a name="psactionrunningtimeoutsec-int32"></a>PSActionRunningTimeoutSec \<Int32\>

Determina quanto tempo a atividade pode ser executada em cada computador de destino. Se a atividade não for concluída antes do tempo limite expirar, o fluxo de trabalho do Windows PowerShell gerará um erro de encerramento e interromperá o processamento do fluxo de trabalho no computador de destino afetado.

#### <a name="psallowredirection-boolean"></a>PSAllowRedirection \<Boolean\>

Um valor de $True permite o redirecionamento da conexão para os computadores de destino.
Um valor de $False não tem nenhum efeito. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Quando você usa o parâmetro PSConnectionURI, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o Windows PowerShell não redireciona conexões, mas você pode usar o parâmetro PSAllowRedirection com um valor de $True para permitir o redirecionamento da conexão com o computador de destino.

Você também pode limitar o número de vezes que a conexão é redirecionada definindo a propriedade MaximumConnectionRedirectionCount da variável de `$PSSessionOption` preferência ou a propriedade MaximumConnectionRedirectionCount do valor do parâmetro SSessionOption de cmdlets que criam uma sessão. O valor padrão é 5.

#### <a name="psapplicationname-string"></a>PSApplicationName \<String\>

Especifica o segmento de nome de aplicativo do URI de conexão que é usado para se conectar aos computadores de destino. Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro ConnectionURI no comando. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador de destino. Se esta variável de preferência não estiver definida, o valor padrão é WSMAN. Esse valor é adequado para a maioria dos usos. Para obter mais informações, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão. O valor desse parâmetro deve corresponder ao valor da propriedade URLPrefix de um ouvinte no computador remoto.

#### <a name="psauthentication-authenticationmechanism"></a>PSAuthentication \<AuthenticationMechanism\>

Especifica o mecanismo usado para autenticar as credenciais do usuário ao conectar-se aos computadores de destino. Os valores válidos são Default, Basic, Credssp, Digest, Kerberos, Negotiate e NegotiateWithImplicitCredential. O valor padrão é Default. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Para obter informações sobre os valores desse parâmetro, consulte a descrição da enumeração **System.Management.Automation.Runspaces.AuthenticationMechanism** no MSDN.

> [!WARNING]
> A autenticação CredSSP (Credencial Security Service Provider), na qual as credenciais do usuário são transmitidas a um computador remoto para autenticação, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remota. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

#### <a name="pscertificatethumbprint-string"></a>PSCertificateThumbprint \<String\>

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Insira a impressão digital do certificado. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles só podem ser mapeados para contas de usuário local. eles não funcionam com contas de domínio.

Para obter um certificado, use os cmdlets [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) ou [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) na unidade CERT: do Windows PowerShell.

#### <a name="pscomputername-string"></a>PSComputerName \<String[]\>

Especifica os computadores de destino nos quais a atividade é executada. O padrão é o computador local. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Digite o nome NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas. Para especificar o computador local, digite o nome do computador, "localhost" ou um ponto (.).

Para incluir o computador local no valor do parâmetro PSComputerName, abra o Windows PowerShell com a opção "executar como administrador".

Se esse parâmetro for omitido do comando ou o valor for $null ou uma cadeia de caracteres vazia, o destino do fluxo de trabalho será o computador local e a comunicação remota do Windows PowerShell não será usada para executar o comando.

Para usar um endereço IP no valor do parâmetro ComputerName, o comando deve incluir o parâmetro PSCredential. Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local. Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

#### <a name="psconfigurationname-string"></a>PSConfigurationName \<String\>

Especifica as configurações de sessão que são usadas para criar sessões nos computadores de destino. Insira o nome de uma configuração de sessão nos computadores de destino (não no computador que está executando o fluxo de trabalho. O padrão é Microsoft. PowerShell. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

#### <a name="psconnectionretrycount-uint"></a>PSConnectionRetryCount \<UInt\>

Especifica o número máximo de tentativas de conexão com cada computador de destino se a primeira tentativa de conexão falhar. Insira um número entre 1 e 4.294.967.295 (UInt. MaxValue). O valor padrão, zero (0), não representa novas tentativas.
Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

#### <a name="psconnectionretryintervalsec-uint"></a>PSConnectionRetryIntervalSec \<UInt\>

Especifica o atraso entre as tentativas de repetição de conexão em segundos. O valor padrão é zero (0). Esse parâmetro é válido somente quando o valor de PSConnectionRetryCount é pelo menos 1. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

#### <a name="psconnectionuri-systemuri"></a>PSConnectionURI \<System.Uri\>

Especifica um Uniform Resource Identifier (URI) que define o ponto de extremidade de conexão para a atividade no computador de destino. O URI deve ser totalmente qualificado. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

O formato dessa cadeia de caracteres é o seguinte:

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

O valor padrão é `http://localhost:5985/WSMAN`.

Se você não especificar um PSConnectionURI, poderá usar os parâmetros PSUseSSL, PSComputerName, PSPort e PSApplicationName para especificar os valores de PSConnectionURI.

Os valores válidos para o segmento Transport do URI são HTTP e HTTPS. Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS. Para utilizar as portas padrão para comunicação remota do Windows PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

#### <a name="pscredential-pscredential"></a>PSCredential \<PSCredential\>

Especifica uma conta de usuário que tem permissão para executar a atividade no computador de destino. O padrão é o usuário atual. Esse parâmetro é válido somente quando o parâmetro PSComputerName é incluído no comando. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira uma variável que contenha um objeto PSCredential, como um que o cmdlet Get-Credential retorna. Se você inserir apenas um nome de usuário, uma senha será solicitada.

#### <a name="psdebug-psdatacollectiondebugrecord"></a>PSDebug \<PSDataCollection[DebugRecord]\>

Adiciona mensagens de depuração da atividade para a coleção de registros de depuração especificada, em vez de gravar as mensagens de depuração no console ou para o valor da Propriedade Debug do trabalho de Workflow. Você pode adicionar mensagens de depuração de várias atividades ao mesmo objeto de coleção de registros de depuração.

Para usar esse parâmetro comum de atividade, use o cmdlet New-Object para criar um objeto PSDataCollection com um tipo de DebugRecord e salve o objeto em uma variável. Em seguida, use a variável como o valor do parâmetro PSDebug de uma ou mais atividades, conforme mostrado no exemplo a seguir.

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a>PSDisableSerialization \<Boolean\>

Direciona a atividade para retornar objetos “ativos” (não serializados) ao fluxo de trabalho.
Os objetos resultantes têm métodos, bem como propriedades, mas não podem ser salvos quando um ponto de verificação é obtido.

#### <a name="psdisableserializationpreference-boolean"></a>PSDisableSerializationPreference \<Boolean\>

Aplica o equivalente ao parâmetro PSDisableSerialization ao fluxo de trabalho inteiro, não apenas à atividade. A adição desse parâmetro geralmente não é recomendada, pois um fluxo de trabalho que não serializa seus objetos não pode ser retomado ou persistido.

Valores válidos: 

- Os Se omitido, e você também não tiver adicionado o parâmetro PSDisableSerialization a uma atividade, os objetos serão serializados.

- `$True`. direciona todas as atividades de um fluxo de trabalho a retornar objetos “ativos” (não serializados). Os objetos resultantes têm métodos, bem como propriedades, mas não podem ser salvos quando um ponto de verificação é obtido.
- `$False`. os objetos de fluxo de trabalho são serializados.

#### <a name="pserror-psdatacollectionerrorrecord"></a>PSError \<PSDataCollection[ErrorRecord]\>

Adiciona mensagens de erro da atividade à coleção de registros de erros especificada, em vez de gravar as mensagens de erro no console ou no valor da Propriedade Error do trabalho de fluxo de trabalho. Você pode adicionar mensagens de erro de várias atividades ao mesmo objeto de coleção de registros de erro.

Para usar esse parâmetro comum de atividade, use o `New-Object` cmdlet para criar um objeto PSDataCollection com um tipo de ErrorRecord e salve o objeto em uma variável. Em seguida, use a variável como o valor do parâmetro PSError de uma ou mais atividades, conforme mostrado no exemplo a seguir.

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a>PSPersist \<Boolean\>

Usa um ponto de verificação após a atividade. Esse ponto de verificação é adicional aos pontos de verificação especificados no fluxo de trabalho. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Um "ponto de verificação" ou "pontos de persistência" é um instantâneo do estado do fluxo de trabalho e dos dados que são capturados enquanto o fluxo de trabalho é executado e salvo em um repositório de persistência no disco. O fluxo de trabalho do Windows PowerShell usa os dados salvos para retomar um fluxo de trabalho suspenso ou interrompido do último ponto de persistência, em vez de reiniciar o fluxo de trabalho.

Valores válidos: 

- Os Se você omitir esse parâmetro, nenhum ponto de verificação será adicionado. Os pontos de verificação são obtidos com base nas configurações do fluxo de trabalho.

- `$True`. Usa um ponto de verificação após a conclusão da atividade.
  Esse ponto de verificação é adicional aos pontos de verificação especificados no fluxo de trabalho.

- `$False`. Nenhum ponto de verificação é adicionado. Os pontos de verificação são obtidos somente quando especificado no fluxo de trabalho.

#### <a name="psport-int32"></a>PSPort \<Int32\>

Especifica a porta de rede nos computadores de destino. As portas padrão são 5985 (a porta de WinRM para HTTP) e 5986 (a porta de WinRM para HTTPS). Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Não use o parâmetro PSPort, a menos que você precise. A porta definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores. Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.

#### <a name="psprogress-psdatacollectionprogressrecord"></a>PSProgress \<PSDataCollection[ProgressRecord]\>

Adiciona as mensagens de progresso da atividade à coleção de registros de andamento especificada, em vez de gravar as mensagens de progresso no console ou no valor da Propriedade Progress do trabalho de fluxo. Você pode adicionar mensagens de progresso de várias atividades ao mesmo objeto de coleção de registros de progresso.

#### <a name="psprogressmessage-string"></a>PSProgressMessage \<String\>

Especifica uma descrição amigável da atividade. O valor PSProgressMessage aparece na barra de progresso enquanto o fluxo de trabalho é executado. Quando o DisplayName também é incluído no comando, o conteúdo da barra de progresso aparece em \<DisplayName\> : \<PSProgressMessage\> Format.

Esse parâmetro é particularmente útil para identificar atividades em um bloco de script ForEach-Parallel. Sem essa mensagem, as atividades em todas as ramificações paralelas são identificadas pelo mesmo nome.

#### <a name="psremotingbehavior-remotingbehavior"></a>PSRemotingBehavior \<RemotingBehavior\>

Especifica como a comunicação remota é gerenciada quando a atividade é executada em computadores de destino.
O PowerShell é o padrão.

Os valores válidos são:

- Nenhum: a atividade não é executada em computadores remotos.

- PowerShell: a comunicação remota do Windows PowerShell é usada para executar a atividade em computadores de destino.

- Personalizado: a atividade dá suporte a seu próprio tipo de comunicação remota. Esse valor é válido quando o cmdlet que está sendo implementado como uma atividade define o valor do atributo RemotingCapability como SupportedByCommand e o comando inclui o parâmetro ComputerName.

#### <a name="psrequiredmodules-string"></a>PSRequiredModules \<String[]\>

Importa os módulos especificados antes de executar o comando. Insira os nomes do módulo. Os módulos devem ser instalados no computador de destino.

Os módulos instalados em um caminho especificado na variável de ambiente PSModulePath são automaticamente importados na primeira utilização de qualquer comando no módulo.
Use esse parâmetro para importar módulos que não estão em um local PSModulePath.

Já que cada atividade em um fluxo de trabalho é executada em sua própria sessão, um comando Import-Module importa um módulo somente para a sessão na qual ele é executado. Ela não importa o módulo para sessões em que há outras atividades em execução.

#### <a name="pssessionoption-pssessionoption"></a>PSSessionOption \<PSSessionOption\>

Define opções avançadas para as sessões para os computadores de destino. Insira um objeto PSSessionOption, como um que você cria usando o cmdlet New-PSSessionOption. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

Os valores padrão para as opções de sessão são determinados pelo valor da `$PSSessionOption` variável de preferência, se estiver definido. Caso contrário, a sessão usará os valores especificados na configuração da sessão.

Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte o tópico da ajuda para o cmdlet New-PSSessionOption [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Para obter mais informações sobre a variável de preferência $PSSessionOption, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

#### <a name="psusessl-boolean"></a>PSUseSSL \<Boolean\>

Um valor de $True usa o protocolo de protocolo SSL (SSL) para estabelecer uma conexão com o computador de destino. Por padrão, SSL não é usado. Um valor de $False não tem nenhum efeito. Esse parâmetro comum de atividade também é um parâmetro comum de fluxo de trabalho.

O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede. O UseSSL é uma proteção adicional que envia os dados em um HTTPS, em vez de HTTP. Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.

#### <a name="psverbose-psdatacollectionverboserecord"></a>PSVerbose \<PSDataCollection[VerboseRecord]\>

Adiciona mensagens detalhadas da atividade à coleção de registros detalhados especificada, em vez de gravar as mensagens detalhadas no console ou no valor da propriedade Verbose do trabalho de fluxo. Você pode adicionar mensagens detalhadas de várias atividades ao mesmo objeto de coleção de registros detalhados.

#### <a name="pswarning-psdatacollectionwarningrecord"></a>PSWarning \<PSDataCollection[WarningRecord]\>

Adiciona mensagens de aviso da atividade à coleção de registros de aviso especificada, em vez de gravar as mensagens de aviso no console ou no valor da propriedade de aviso do trabalho de fluxo. Você pode adicionar mensagens de aviso de várias atividades ao mesmo objeto de coleção de registros de aviso.

#### <a name="result"></a>Resultado

Esse parâmetro só é válido em fluxos de trabalho XAML.

#### <a name="usedefaultinput-boolean"></a>UseDefaultInput \<Boolean\>

Aceita todas as entradas de fluxo de trabalho como entrada para a atividade por valor.

Por exemplo, a atividade Get-Process do exemplo de fluxo de trabalho a seguir usa o parâmetro comum de atividade UseDefaultInput para obter a entrada que é passada ao fluxo de trabalho. Quando você executa o fluxo de trabalho com a entrada, essa entrada é usada pela atividade.

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a>Extensa \<SwitchParameter\>

Exibe informações detalhadas sobre a operação executada pelo comando.
Essas informações se assemelham às informações em um rastreamento ou em um log de transações.
O parâmetro Verbose substitui o valor da variável $VerbosePreference para o comando atual. Esse parâmetro funciona somente quando o comando gera uma mensagem detalhada. Esse parâmetro também é um parâmetro comum do Windows PowerShell.

#### <a name="warningaction-actionpreference"></a>WarningAction \<ActionPreference\>

Determina como a atividade responde a um aviso. "Continue" é o valor padrão. O parâmetro WarningAction substitui o valor da variável $WarningPreference para o comando atual. Esse parâmetro funciona somente quando o comando gera uma mensagem de aviso. Esse parâmetro também é um parâmetro comum do Windows PowerShell.

Valores válidos:

- SilentlyContinue. Suprime a mensagem de aviso e continua executando o comando.

- Continua. Exibe a mensagem de aviso e continua executando o comando.
  "Continue" é o valor padrão.

- Inquire. Exibe a mensagem de aviso e solicita sua confirmação antes de continuar a execução. Esse valor raramente é usado.

- Deixar. Exibe a mensagem de aviso e para a execução do comando.

> [!NOTE]
> O parâmetro WarningAction não substitui o valor da variável de preferência $WarningAction quando o parâmetro é usado em um comando para executar um script ou uma função.

### <a name="examples"></a>EXEMPLOS

Os parâmetros comuns de atividades são extremamente úteis. Por exemplo, você pode usar o parâmetro PSComputerName para executar atividades específicas apenas em um subconjunto dos computadores de destino.

Ou, você pode usar os parâmetros PSConnectionRetryCount e PSConnectionRetryIntervalSec para ajustar os valores de repetição para atividades específicas.

O exemplo a seguir mostra como usar os parâmetros comuns da atividade PSComputerName para executar uma atividade de Get-EventLog somente em computadores que um domínio específico.

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Workflows](about_workflows.md) 
 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)
