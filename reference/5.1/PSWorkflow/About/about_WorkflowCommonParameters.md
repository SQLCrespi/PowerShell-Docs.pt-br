---
description: Este tópico descreve os parâmetros que são válidos em todos os comandos de fluxo de trabalho do Windows PowerShell. Como o mecanismo do Windows PowerShell as adiciona aos fluxos de trabalho, você pode usar esses parâmetros em qualquer fluxo de trabalho e eles são automaticamente habilitados nos fluxos de trabalho que você cria.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WorkflowCommonParameters
ms.openlocfilehash: 386200475c1dab9735921edd60abbde20ee354c4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195798"
---
# <a name="about-workflowcommonparameters"></a>Sobre o WorkflowCommonParameters

## <a name="short-description"></a>DESCRIÇÃO BREVE

Este tópico descreve os parâmetros que são válidos em todos os comandos de fluxo de trabalho do Windows PowerShell. Como o mecanismo do Windows PowerShell as adiciona aos fluxos de trabalho, você pode usar esses parâmetros em qualquer fluxo de trabalho e eles são automaticamente habilitados nos fluxos de trabalho que você cria.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os parâmetros comuns do fluxo de trabalho do Windows PowerShell são um conjunto de parâmetros de cmdlet que você pode usar com todos os fluxos de trabalho e atividades do Windows PowerShell. Eles são adicionados pelo mecanismo de fluxo de trabalho do Windows PowerShell, não pelo autor do fluxo de trabalho, e estão automaticamente disponíveis em fluxos de trabalho e atividades. No entanto, os fluxos de trabalho aninhados em três níveis de profundidade não dão suporte a parâmetros comuns, incluindo parâmetros comuns de fluxo de trabalho.

Todos os parâmetros de fluxo de trabalho são opcionais e nomeados (não posicional). Eles não assumem a entrada do pipeline.

A maioria dos parâmetros comuns do fluxo de trabalho tem um prefixo de PS, como `PSComputerName` e `PSCredential` . Os parâmetros de PS-prefixados configuram a conexão e o ambiente de execução para os computadores de destino, também conhecidos como "nós remotos".

Muitos dos parâmetros comuns do fluxo de trabalho, como `PSAllowRedirection` e `AsJob` , têm nomes semelhantes aos parâmetros usados em trabalhos de comunicação remota e em segundo plano do Windows PowerShell. Esses parâmetros funcionam da mesma forma que os parâmetros de comunicação remota e de trabalho nomeados de forma semelhante, para que você possa usar o conhecimento que desenvolveu em comunicação remota e trabalhos para gerenciar fluxos de trabalho.

Os fluxos de trabalho são introduzidos no Windows PowerShell 3,0.

### <a name="parameter-descriptions"></a>DESCRIÇÕES DE PARÂMETROS

Esta seção descreve os parâmetros comuns do fluxo de trabalho.

#### <a name="-asjob-switchparameter"></a>-AsJob \<SwitchParameter\>

Executa o fluxo de trabalho como uma tarefa de Workflow. O comando Workflow retorna imediatamente um objeto que representa um trabalho pai. O trabalho pai contém os trabalhos filho que estão em execução em cada um dos computadores de destino. Para gerenciar o trabalho, use os cmdlets Job. Para obter os resultados do trabalho, use [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job).

#### <a name="-jobname-string"></a>-JobName \<String\>

Especifica um nome amigável para a tarefa de fluxo de trabalho. Por padrão, os trabalhos são nomeados "Job\<n\>", onde \<n\> é um número ordinal.

Se você usar o parâmetro JobName em um comando de fluxo de trabalho, ele será executado como um trabalho e o comando Workflow retornará um objeto Job, mesmo se você não incluir o `AsJob` parâmetro no comando.

Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

#### <a name="-psallowredirection-switchparameter"></a>-PSAllowRedirection \<SwitchParameter\>

Permite o redirecionamento da conexão com os computadores de destino.

Quando você usa o `PSConnectionURI` parâmetro, o destino remoto pode retornar uma instrução para redirecionar para um URI diferente. Por padrão, o Windows PowerShell não redireciona conexões, mas você pode usar o `PSAllowRedirection` parâmetro para permitir o redirecionamento da conexão com o computador de destino.

Você também pode limitar o número de vezes que a conexão é redirecionada definindo a `MaximumConnectionRedirectionCount` propriedade da variável de `$PSSessionOption` preferência ou a `MaximumConnectionRedirectionCount` Propriedade do valor de `PSSessionOption parameter` . O valor padrão é 5. Para obter mais informações, consulte a descrição do `PSSessionOption` parâmetro e [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

#### <a name="-psapplicationname-string"></a>-PSApplicationName \<String\>

Especifica o segmento de nome de aplicativo do URI de conexão que é usado para se conectar aos computadores de destino. Use esse parâmetro para especificar o nome do aplicativo quando você não estiver usando o `ConnectionURI` parâmetro no comando.

O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local. Se esta variável de preferência não estiver definida, o valor padrão é WSMAN. Esse valor é adequado para a maioria dos usos. Para obter mais informações, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão. O valor desse parâmetro deve corresponder ao valor da `URLPrefix` propriedade de um ouvinte no computador remoto.

#### <a name="-psauthentication-authenticationmechanism"></a>-PSAuthentication \<AuthenticationMechanism\>

Especifica o mecanismo usado para autenticar as credenciais do usuário ao conectar-se aos computadores de destino.

Os valores válidos são:

- **Default**
- **Basic**
- **CredSSP**
- **Resumo da mensagem**
- **Kerberos**
- **Inicia**
- **NegotiateWithImplicitCredential**

O valor padrão é **Default** .

Para obter informações sobre os valores desse parâmetro, consulte a descrição da `System.Management.Automation.Runspaces.AuthenticationMechanism` enumeração no msdn.

> [!WARNING]
> A autenticação CredSSP (Credencial Security Service Provider), na qual as credenciais do usuário são transmitidas a um computador remoto para autenticação, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remota. Esse mecanismo aumenta o risco de segurança da operação remota. Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.

#### <a name="-psauthenticationlevel-authenticationlevel"></a>-PSAuthenticationLevel \<AuthenticationLevel\>

Especifica o nível de autenticação para as conexões com os computadores de destino.
O valor padrão é **Default** .

Os valores válidos são:

|Name |Descrição |
|---------|---------|
|**Inalterado** | O nível de autenticação é o mesmo que o comando anterior. |
|**Default** | Autenticação do Windows. |
|**Nenhum** | Sem autenticação COM.   |
|**Connect** | Autenticação COM no nível da Conexão.|
|**Chamar** | Autenticação COM no nível da Chamada.   |
|**Pacote** | Autenticação COM no nível do Pacote.|
|**PacketIntegrity** | Autenticação COM no nível da Integridade de Pacote.  |
|**PacketPrivacy** | Autenticação COM no nível da Privacidade de Pacote. |

#### <a name="-pscertificatethumbprint-string"></a>-PSCertificateThumbprint \<String\>

Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Insira a impressão digital do certificado.

Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles só podem ser mapeados para contas de usuário local. eles não funcionam com contas de domínio.

Para obter um certificado, use [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) ou [Get-ChildItem] (.. /.. /Microsoft.PowerShell.Management/Get-Childitem.md) no Windows PowerShell CERT: Drive.

#### <a name="-pscomputername-string"></a>-PSComputerName \<String[]\>

Especifica a lista de computadores que são os nós de destino do fluxo de trabalho.
Comandos ou atividades em um fluxo de trabalho são executados nos computadores especificados usando esse parâmetro. O padrão é o computador local.

Digite o nome NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas. Para especificar o computador local, digite o nome do computador, "localhost" ou um ponto (.).

Para incluir o computador local no valor do `PSComputerName` parâmetro, abra o Windows PowerShell com a opção "executar como administrador".

Se esse parâmetro for omitido do comando ou o valor for `$null` ou uma cadeia de caracteres vazia, o destino do fluxo de trabalho será o computador local e a comunicação remota do Windows PowerShell não será usada para executar o comando.

Para usar um endereço IP no valor do `ComputerName` parâmetro, o comando deve incluir o `PSCredential` parâmetro. Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local. Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte *"como adicionar um computador à lista de hosts confiáveis"* em [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

#### <a name="-psconfigurationname-string"></a>-PSConfigurationName \<String\>

Especifica as configurações de sessão que são usadas para configurar sessões nos computadores de destino. Insira uma configuração de sessão nos computadores de destino (não no computador do servidor de fluxo de trabalho). O padrão é `Microsoft.PowerShell.Workflow`.

#### <a name="-psconnectionretrycount-uint"></a>-PSConnectionRetryCount \<UInt\>

Especifica o número máximo de tentativas de conexão com cada computador de destino se a primeira tentativa de conexão falhar. Insira um número entre 1 e 4.294.967.295 (UInt. MaxValue). O valor padrão, zero (0), não representa novas tentativas.

#### <a name="-psconnectionretryintervalsec-uint"></a>-PSConnectionRetryIntervalSec \<UInt\>

Especifica o atraso entre as tentativas de repetição de conexão em segundos. O valor padrão é zero (0). Esse parâmetro é válido somente quando o valor de PSConnectionRetryCount é pelo menos 1.

#### <a name="-psconnectionuri-systemuri"></a>-PSConnectionURI \<System.Uri\>

Especifica um Uniform Resource Identifier (URI) que define o ponto de extremidade de conexão para o fluxo de trabalho no computador de destino. O URI deve ser totalmente qualificado.

O formato dessa cadeia de caracteres é o seguinte:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

O valor padrão é `http://localhost:5985/WSMAN`.

Se você não especificar um `PSConnectionURI` , poderá usar os `PSUseSSL` `PSComputerName` parâmetros,, `PSPort` e `PSApplicationName` para especificar os `PSConnectionURI` valores.

Os valores válidos para o segmento de transporte do URI são **http** e **https** .
Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS. Para utilizar as portas padrão para comunicação remota do Windows PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.

#### <a name="-pscredential-pscredential"></a>-PSCredential \<PSCredential\>

Especifica uma conta de usuário que tem permissão para executar um fluxo de trabalho no computador de destino. O padrão é o usuário atual. Esse parâmetro é válido somente quando o parâmetro PSComputerName é incluído no comando.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira uma variável que contenha um `PSCredential` objeto, como um que o `Get-Credential` cmdlet retorne. Se você inserir apenas um nome de usuário, uma senha será solicitada.

#### <a name="-pselapsedtimeoutsec-uint32"></a>-Pselapsedtimeoutsec comum \<UInt32\>

Determina por quanto tempo o fluxo de trabalho e todos os recursos relacionados são mantidos no sistema. Quando o tempo limite expira, o fluxo de trabalho é excluído, mesmo que ainda esteja sendo processado. Insira um valor entre 10 e 4.294.967.295. O valor padrão, 0 (zero), significa que não há tempo limite decorrido.

#### <a name="-psparametercollection-hashtable"></a>-PSParameterCollection \<Hashtable[]\>

Especifica valores de parâmetros comuns de fluxo de trabalho diferentes para computadores de destino diferentes.

Insira uma lista separada por vírgulas de tabelas de hash com uma tabela de hash para cada computador de destino. Em cada tabela de hash, a primeira chave é `PSComputerName` e seu valor é o nome do computador de destino. Caracteres curinga são permitidos no nome do computador. Para as chaves restantes na tabela de hash, a chave é o nome do parâmetro e o valor é o valor do parâmetro.

Por exemplo:

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

No exemplo acima, todas as conexões terão um Pselapsedtimeoutsec comum padrão de 20 segundos, exceto para Server01 que substitui o valor padrão especificando seu próprio tempo limite de 10 segundos.

#### <a name="-pspersist-boolean"></a>-PSPersist \<Boolean\>

Adiciona pontos de verificação ao fluxo de trabalho, além de quaisquer pontos de verificação especificados no fluxo de trabalho.

Esse parâmetro não pode suprimir os pontos de verificação em um fluxo de trabalho, como aqueles especificados usando o `PSPersist` parâmetro Common da atividade, a `Checkpoint-Workflow` atividade ou a `$PSPersistPreference` variável.

Um "ponto de verificação" ou "pontos de persistência" é um instantâneo do estado do fluxo de trabalho e dos dados que são capturados enquanto o fluxo de trabalho é executado e é salvo em um repositório de persistência em disco ou em um banco de dados SQL. O fluxo de trabalho do Windows PowerShell usa os dados salvos para retomar um fluxo de trabalho suspenso ou interrompido do último ponto de persistência, em vez de reiniciar o fluxo de trabalho.

Valores válidos: 

- ( *Padrão* ) Se você omitir esse parâmetro, um ponto de verificação será adicionado ao início e ao final do fluxo de trabalho, além de quaisquer pontos de verificação especificados no fluxo de trabalho.

- `$True`. Adiciona um ponto de verificação ao início e ao final do fluxo de trabalho e a um ponto de verificação após cada atividade, além de quaisquer pontos de verificação especificados no fluxo de trabalho.

- `$False`. Nenhum ponto de verificação é adicionado. Os pontos de verificação são obtidos somente quando especificado no fluxo de trabalho.

#### <a name="-psport-int32"></a>-PSPort \<Int32\>

Especifica a porta de rede nos computadores de destino. As portas padrão são 5985 (a porta de WinRM para HTTP) e 5986 (a porta de WinRM para HTTPS).

Não use o parâmetro PSPort, a menos que você precise. A porta definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado. Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores. Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.

#### <a name="-psprivatemetadata-hashtable"></a>-PSPrivateMetadata \<Hashtable\>

Fornece informações personalizadas para trabalhos de fluxo de trabalho. Insira uma tabela de hash. As chaves e os valores são personalizados para cada fluxo de trabalho. Para obter informações sobre os metadados privados de um fluxo de trabalho, consulte o tópico da ajuda para o fluxo de trabalho.

Esse parâmetro não é processado pelo mecanismo de fluxo de trabalho do Windows PowerShell.
Em vez disso, o mecanismo passa a tabela de hash diretamente para o fluxo de trabalho.

#### <a name="-psrunningtimeoutsec-uint32"></a>-PSRunningTimeoutSec \<UInt32\>

Especifica o tempo de execução do fluxo de trabalho em segundos, excluindo a hora em que o fluxo de trabalho é suspenso. Se a execução do fluxo de trabalho não for concluída quando o tempo expirar, o mecanismo de fluxo de trabalho do Windows PowerShell interromperá a execução do fluxo de trabalho.

#### <a name="-pssessionoption-pssessionoption"></a>-PSSessionOption \<PSSessionOption\>

Define opções avançadas para as sessões para os computadores de destino. Insira um `PSSessionOption` objeto, como um que você cria usando o `New-PSSessionOption` cmdlet.

Os valores padrão para as opções de sessão são determinados pelo valor da `$PSSessionOption` variável de preferência, se estiver definido. Caso contrário, a sessão usará os valores especificados na configuração da sessão.

Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte o tópico da ajuda para o `New-PSSessionOption` cmdlet (.. /.. /Microsoft.PowerShell.Core/New-PSSessionOption.md). Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

#### <a name="-psusessl-switchparameter"></a>-PSUseSSL \<SwitchParameter\>

Usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador de destino. Por padrão, SSL não é usado.

O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede. O UseSSL é uma proteção adicional que envia os dados em um HTTPS, em vez de HTTP. Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_ActivityCommonParameters](about_ActivityCommonParameters.md)
- [about_Workflows](about_Workflows.md)
- [Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [New-PSWorkflowExecutionOption](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [New-PSWorkflowSession](xref:PSWorkflow.New-PSWorkflowSession)
