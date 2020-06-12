---
title: Getting Started with PowerShell (Introdução ao PowerShell)
description: Em que local encontrar e como iniciar o PowerShell para novos usuários.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0f72fb5baf5b829142b18ed774261e9b3b66291b
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438017"
---
# <a name="chapter-1---getting-started-with-powershell"></a>Capítulo 1 – Introdução ao PowerShell

Com frequência, descubro que os apresentadores em conferências e reuniões de grupo de usuários já têm o PowerShell em execução quando iniciam apresentações no nível básico. Este livro começa respondendo às perguntas que ouvi nessas sessões de participantes que não usavam anteriormente o PowerShell.

Especificamente, este capítulo se concentra na localização e na inicialização do PowerShell e na solução de alguns dos pontos problemáticos iniciais que os novos usuários enfrentam com o PowerShell. Lembre-se de acompanhar os exemplos mostrados neste capítulo no computador do ambiente de laboratório do Windows 10.

## <a name="what-do-i-need-to-get-started-with-powershell"></a>O que é necessário para começar a usar o PowerShell?

Todas as versões modernas de sistemas operacionais Windows são fornecidas com o PowerShell instalado. Se você estiver executando uma versão mais antiga que a 5.1, instale a última versão.

- Para fazer a atualização para o Windows PowerShell 5.1, confira [Como atualizar um Windows PowerShell existente][]
- Instale a última versão do PowerShell, confira [Instalando o PowerShell][]

## <a name="where-do-i-find-powershell"></a>Em que local posso encontrar o PowerShell?

A maneira mais fácil de encontrar o PowerShell no Windows 10 é digitar **PowerShell** na barra de pesquisa, conforme mostrado na Figura 1-1.

![Figura 1-1](media/figure1-1.png)

Observe que quatro atalhos diferentes para o PowerShell são mostrados na Figura 1-1. O computador usado para fins de demonstração neste livro executa a versão de 64 bits do Windows 10 e, portanto, há uma versão de 64 bits do console do PowerShell e do ISE (Ambiente de Script Integrado) do PowerShell e uma versão de 32 bits de cada um, conforme indicado pelo sufixo (x86) nos atalhos. Se você estiver executando uma versão de 32 bits do Windows 10, terá apenas dois atalhos. Esses itens não têm o sufixo (x86), mas são versões de 32 bits. Se você tem um sistema operacional de 64 bits, minha recomendação é executar a versão de 64 bits do PowerShell, a menos que você tenha um motivo específico para executar a versão de 32 bits.

Para obter informações sobre como iniciar o PowerShell em outras versões do Windows, confira [Iniciando o Windows PowerShell][].

## <a name="how-do-i-launch-powershell"></a>Como fazer para iniciar o PowerShell?

Nos ambientes corporativos de produção aos quais dou suporte, uso três contas de usuário diferentes do Active Directory. Espelhei essas contas no ambiente de laboratório usado neste livro. Faço logon no computador Windows 10 como um usuário de domínio que não seja um administrador local ou de domínio.

Iniciei o console do PowerShell clicando no atalho "Windows PowerShell", conforme mostrado na Figura 1-1.

![Figura 1-4](media/figure1-4.png)

Observe que a barra de título do console do PowerShell indica "Windows PowerShell", conforme mostrado na Figura 1-4. Alguns comandos são executados corretamente, mas o PowerShell não pode participar do UAC (Controle de Acesso do Usuário). Isso significa que não é possível solicitar a elevação para tarefas que exigem a aprovação de um administrador.
A seguinte mensagem de erro é gerada:

```powershell
Get-Service -Name W32Time | Stop-Service
```

```Output
Stop-Service : Service 'Windows Time (W32Time)' cannot be stopped due to the following
error: Cannot open W32Time service on computer '.'.
At line:1 char:29
+ Get-Service -Name W32Time | Stop-Service
+
    + CategoryInfo          : CloseError: (System.ServiceProcess.ServiceController:ServiceController)
     [Stop-Service], ServiceCommandException
    + FullyQualifiedErrorId : CouldNotStopService,Microsoft.PowerShell.Commands.StopServiceCommand
```

A solução para esse problema é executar o PowerShell como um usuário de domínio que seja um administrador local.
É assim que a minha segunda conta de usuário de domínio está configurada. Usando a entidade de privilégio mínimo, essa conta NÃO deve ser um administrador de domínio nem ter privilégios elevados no domínio.

Feche o PowerShell. Reinicie o console do PowerShell, mas, desta vez, clique com o botão direito do mouse no atalho do **Windows PowerShell** e selecione **Executar como administrador**, conforme mostrado na Figura 1-5.

![Figura 1-5](media/figure1-5.png)

Se você estiver conectado ao Windows como um usuário normal, precisará fornecer suas credenciais. Vou inserir as credenciais da minha conta de usuário que é um usuário de domínio e um administrador local, conforme mostrado na Figura 1-6.

![Figura 1-6](media/figure1-6.png)

Depois que o PowerShell for reiniciado como administrador, a barra de título deverá indicar "Administrador: Windows PowerShell", conforme mostrado na Figura 1-7.

![Figura 1-7](media/figure1-7.png)

Agora que o PowerShell está sendo executado com privilégios elevados como um administrador local, o UAC não será mais um problema quando um comando for executado no computador local que normalmente exigirá uma solicitação de elevação. Lembre-se de que qualquer comando executado nessa instância com privilégios elevados do console do PowerShell também é executado com privilégios elevados.

Para simplificar a localização do PowerShell e iniciá-lo como administrador, recomendo fixá-lo na barra de tarefas e defini-lo para ser iniciado automaticamente como administrador toda vez que for executado.

Pesquise o PowerShell novamente, mas, desta vez, clique com o botão direito do mouse nele e selecione "Fixar na barra de tarefas", conforme mostrado na Figura 1-8.

![Figura 1-8](media/figure1-8.png)

Clique com o botão direito do mouse no atalho do PowerShell que agora está fixado à barra de tarefas e selecione Propriedades, conforme mostrado na Figura 1-9.

![Figura 1-9](media/figure1-9.png)

Clique em "Avançado", como indicado no nº 1 na Figura 1-10, marque a caixa de seleção "Executar como administrador", como indicado no nº 2 na Figura 1-10 e clique em OK duas vezes para aceitar as alterações e sair das duas caixas de diálogo.

![Figura 1-10](media/figure1-10.png)

Você nunca precisará se preocupar em localizar o PowerShell ou se ele está sendo executado como administrador novamente.

A execução do PowerShell com privilégios elevados como administrador para evitar problemas com o UAC afeta apenas os comandos executados no computador local. Ele não tem nenhum efeito sobre os comandos direcionados para computadores remotos.

## <a name="what-version-of-powershell-am-i-running"></a>Qual versão do PowerShell estou executando?

Há várias variáveis automáticas no PowerShell que armazenam informações de estado. Uma dessas variáveis é `$PSVersionTable`, que contém uma tabela de hash que pode ser usada para exibir as informações relevantes da versão do PowerShell:

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      5.1.19041.1
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.19041.1
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

As versões mais recentes do Windows PowerShell são distribuídas como parte do WMF (Windows Management Framework). Uma versão específica do .NET Framework é necessária, dependendo da versão do WMF. Para fazer a atualização para o Windows PowerShell 5.1, confira [Como atualizar um Windows PowerShell existente][].

## <a name="execution-policy"></a>Política de execução

Ao contrário da crença popular, a política de execução no PowerShell não é um limite de segurança. Ela foi projetada para impedir que um usuário execute um script sem perceber. Um usuário determinado pode facilmente ignorar a política de execução no PowerShell. A Tabela 1-2 mostra a política de execução padrão para os sistemas operacionais Windows atuais.

| Versão do sistema operacional do Windows | Política de execução padrão |
| -------------------------------- | ------------------------ |
| Server 2019                      | Remota assinada            |
| Server 2016                      | Remota assinada            |
| Windows 10                       | Restrito               |

Seja qual for a configuração de política de execução, qualquer comando do PowerShell pode ser executado de maneira interativa. A política de execução afeta somente os comandos em execução em um script. O cmdlet `Get-ExecutionPolicy` é usado para determinar qual é a configuração de política de execução atual, e o cmdlet `Set-ExecutionPolicy` é usado para alterar a política de execução. Minha recomendação é usar a política **RemoteSigned**, que exige que os scripts baixados sejam assinados por um editor confiável para serem executados.

Verifique a política de execução atual:

```powershell
Get-ExecutionPolicy
```

```Output
Restricted
```

Os scripts do PowerShell não poderão ser executados quando a política de execução estiver definida como **Restrita**. Essa é a configuração padrão em todos os sistemas operacionais do cliente Windows. Para demonstrar o problema, salve o código a seguir como um arquivo `.ps1` chamado `Stop-TimeService.ps1`.

```powershell
Get-Service -Name W32Time | Stop-Service -PassThru
```

Esse comando é executado de maneira interativa sem erros, desde que o PowerShell seja executado com privilégios elevados como administrador. Mas assim que ele é salvo como um arquivo de script e você tenta executar o script, ele gera um erro:

```powershell
.\Stop-TimeService.ps1
```

```Output
.\Stop-TimeService.ps1 : File C:\demo\Stop-TimeService.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see
about_Execution_Policies at http://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Stop-TimeService.ps1
+
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

Observe que o erro mostrado no conjunto de resultados anterior informa exatamente qual é o problema (a execução de scripts está desabilitada nesse sistema). Quando você executa um comando no PowerShell que gera uma mensagem de erro, leia a mensagem de erro em vez de apenas executar novamente o comando e esperar que ele seja executado com êxito.

Altere a política de execução do PowerShell para remota assinada.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

```Output
Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution
policy might expose you to the security risks described in the about_Execution_Policies help topic
at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default is "N"):y
```

Lembre-se de ler o aviso que é exibido ao alterar a política de execução. Também recomendo dar uma olhada no tópico da Ajuda [about_Execution_Policies][] para verificar se você entendeu as implicações de segurança da alteração da política de execução.

Agora que a política de execução foi definida como **RemoteSigned**, o script `Stop-TimeService.ps1` é executado sem erros.

```powershell
.\Stop-TimeService.ps1
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  W32Time            Windows Time
```

Não se esqueça de iniciar o serviço de Tempo do Windows antes de continuar, caso contrário, você poderá ter problemas imprevistos.

```powershell
Start-Service -Name w32time
```

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu a localizar e iniciar o PowerShell e a criar um atalho que inicia o PowerShell como administrador. Você também aprendeu mais sobre a política de execução padrão e como alterá-la.

## <a name="review"></a>Revisão

1. Como determinar qual versão do PowerShell um computador está executando?
1. Por que é importante iniciar o PowerShell com privilégios elevados como administrador?
1. Como determinar a política de execução atual do PowerShell?
1. O que a política de execução padrão do PowerShell nos computadores cliente Windows impede que ocorra?
1. Como alterar a política de execução do PowerShell?

## <a name="recommended-reading"></a>Leitura recomendada

Para aqueles que desejam saber mais sobre os tópicos abordados neste capítulo, recomendo a leitura dos tópicos da Ajuda do PowerShell a seguir.

- [about_Automatic_Variables][]
- [about_Execution_Policies][]

No próximo capítulo, você aprenderá mais sobre a detectabilidade de comandos no PowerShell. Uma das coisas que será abordada é como atualizar o PowerShell para que esses tópicos da Ajuda possam ser exibidos diretamente no PowerShell, em vez de precisar exibi-los na Internet.

<!-- link references -->
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[about_Execution_Policies]: /powershell//powershell/module/microsoft.powershell.core/about/about_execution_policies
[Como atualizar um Windows PowerShell existente]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Instalando o PowerShell]: /powershell/scripting/install/installing-powershell
[Iniciando o Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
