---
ms.date: 09/07/2018
ms.topic: reference
title: Verbos aprovados para comandos do PowerShell
description: Verbos aprovados para comandos do PowerShell
ms.openlocfilehash: 237355ba9729cfe16c335b39f19ab20e40999457
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655825"
---
# <a name="approved-verbs-for-powershell-commands"></a>Verbos aprovados para comandos do PowerShell

O PowerShell usa um par verbo-substantivo para os nomes de cmdlets e as respectivas classes .NET derivadas.
A parte do nome correspondente ao verbo identifica a ação que o cmdlet executa. A parte do nome correspondente ao substantivo identifica a entidade sobre a qual a ação é executada. Por exemplo, o cmdlet `Get-Command` recupera todos os comandos registrados no PowerShell.

> [!NOTE]
> O PowerShell usa o termo _verbo_ para descrever uma palavra que implica uma ação, mesmo que essa palavra não seja um verbo padrão no idioma inglês. Por exemplo, o termo _New_ é um nome de verbo válido do PowerShell porque implica uma ação, embora não seja um verbo no idioma inglês.

<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->

Cada verbo aprovado tem um _prefixo de alias_ correspondente definido.
Usamos esse prefixo de alias em aliases para comandos que usam esse verbo.
Por exemplo, o prefixo do alias para `Import` é `ip` e, dessa maneira, o alias para `Import-Module` é `ipmo`.  Essa é uma recomendação, mas não uma regra; em particular, ela não precisa ser respeitada para aliases de comando que imitam comandos conhecidos de outros ambientes.

## <a name="verb-naming-recommendations"></a>Recomendações de nomenclatura de verbo

As recomendações a seguir ajudam a escolher um verbo apropriado para o cmdlet, a fim de garantir a consistência entre os cmdlets criados por você, os cmdlets fornecidos pelo PowerShell e os cmdlets criados por outras pessoas.

- Use um dos nomes de verbo predefinidos fornecidos pelo PowerShell
- Use o verbo para descrever o escopo geral da ação e parâmetros para refinar ainda mais a ação do cmdlet.
- Não use um sinônimo de um verbo aprovado. Por exemplo, sempre use `Remove`; nunca use `Delete` nem `Eliminate`.
- Use apenas a forma de cada verbo listada neste tópico. Por exemplo, use `Get`, mas não use `Getting` nem `Gets`.
- Não use os aliases ou verbos reservados a seguir. A linguagem do PowerShell ou alguns poucos cmdlets dela usam esses verbos em circunstâncias excepcionais.
    - ForEach (foreach)
    - [Format](/dotnet/api/System.Management.Automation.VerbsCommon.Format) (f): organiza objetos em uma forma ou layout especificado
    - [Group](/dotnet/api/System.Management.Automation.VerbsData.Group) (gp): organiza ou associa um ou mais recursos
    - [Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (pi)
    - Sort (sr)
    - Tee (te)
    - Where (wh)

Você pode obter uma lista completa de verbos usando o cmdlet `Get-Verb`.

## <a name="similar-verbs-for-different-actions"></a>Verbos semelhantes para ações diferentes

Os verbos semelhantes a seguir representam ações diferentes.

### <a name="new-vs-set"></a>New versus Definir

Use o verbo `New` para criar um recurso. Use o verbo `Set` para modificar um recurso existente, criando-o opcionalmente se ele não existir, como o cmdlet `Set-Variable`.

### <a name="find-vs-search"></a>Find versus Search

Use o verbo `Find` para procurar um objeto. Use o verbo `Search` para criar uma referência a um recurso em um contêiner.

### <a name="get-vs-read"></a>Get versus Ler

Use o verbo `Get` para obter informações sobre um recurso (como um arquivo) ou para obter um objeto com o qual você pode acessar o recurso no futuro. Use o verbo `Read` para abrir um recurso e extrair as informações contidas nele.

### <a name="invoke-vs-start"></a>Invoke versus Iniciar

Use o verbo `Invoke` para executar operações síncronas, como executar um comando e aguardar a conclusão dele. Use o verbo `Start` é usado para iniciar operações assíncronas, como iniciar um processo autônomo.

### <a name="ping-vs-test"></a>Ping versus Teste

Use o verbo `Test`.

## <a name="common-verbs"></a>Verbos comuns

O PowerShell usa a classe de enumeração [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon) para definir ações genéricas que podem ser aplicadas a quase qualquer cmdlet. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Add](/dotnet/api/System.Management.Automation.VerbsCommon.Add) (a)|Adiciona um recurso a um contêiner ou anexa um item a outro item. Por exemplo, o cmdlet `Add-Content` adiciona o conteúdo a um arquivo. Esse verbo é emparelhado com `Remove`.|Append, Attach, Concatenate, Insert|
|[Clear](/dotnet/api/System.Management.Automation.VerbsCommon.Clear) (cl)|Remove todos os objetos de um contêiner, mas não o exclui. Por exemplo, o cmdlet `Clear-Content` remove o conteúdo de um arquivo, mas não exclui o arquivo.|Flush, Erase, Release, Unmark, Unset, Nullify|
|[Close](/dotnet/api/System.Management.Automation.VerbsCommon.Close) (cs)|Altera o estado de um recurso para torná-lo inacessível, indisponível ou inutilizável. Esse verbo é emparelhado com `Open.`||
|[Copy](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (cp)|Copia um recurso para outro nome ou para outro contêiner. Por exemplo, o cmdlet `Copy-Item` copia um item (como um arquivo) de um local no armazenamento de dados para outro local.|Duplicate, Clone, Replicate, Sync|
|[Enter](/dotnet/api/System.Management.Automation.VerbsCommon.Enter) (et)|Especifica uma ação que permite ao usuário se mover para um recurso. Por exemplo, o cmdlet `Enter-PSSession` coloca o usuário em uma sessão interativa. Esse verbo é emparelhado com `Exit`.|Push, Into|
|[Exit](/dotnet/api/System.Management.Automation.VerbsCommon.Exit) (ex)|Define o ambiente ou contexto atual como o contexto usado mais recentemente. Por exemplo, o cmdlet `Exit-PSSession` coloca o usuário na sessão que foi usada para iniciar a sessão interativa. Esse verbo é emparelhado com `Enter`.|Pop, Out|
|[Find](/dotnet/api/System.Management.Automation.VerbsCommon.Find) (fd)|Procura um objeto em um contêiner que é desconhecido, implícito, opcional ou especificado.|Search|
|[Get](/dotnet/api/System.Management.Automation.VerbsCommon.Get) (g)|Especifica uma ação que recupera um recurso. Esse verbo é emparelhado com `Set`.|Read, Open, Cat, Type, Dir, Obtain, Dump, Acquire, Examine, Find, Search|
|[Hide](/dotnet/api/System.Management.Automation.VerbsCommon.Hide) (h)|Torna um recurso não detectável. Por exemplo, um cmdlet cujo nome inclui o verbo Hide pode ocultar um serviço de um usuário. Esse verbo é emparelhado com `Show`.|Bloquear|
|[Join](/dotnet/api/System.Management.Automation.VerbsCommon.Join) (j)|Combina recursos em um recurso. Por exemplo, o cmdlet `Join-Path` combina um caminho com um dos caminhos filho dele para criar um único caminho. Esse verbo é emparelhado com `Split`.|Combine, Unite, Connect, Associate|
|[Lock](/dotnet/api/System.Management.Automation.VerbsCommon.Lock) (lk)|Protege um recurso. Esse verbo é emparelhado com `Unlock`.|Restrict, Secure|
|[Move](/dotnet/api/System.Management.Automation.VerbsCommon.Move) (m)|Move um recurso de um local para outro. Por exemplo, o cmdlet `Move-Item` move um item de um local no armazenamento de dados para outro local.|Transfer, Name, Migrate|
|[New](/dotnet/api/System.Management.Automation.VerbsCommon.New) (n)|Cria um recurso. (O verbo `Set` também pode ser usado durante a criação de um recurso que inclui dados, como o cmdlet `Set-Variable`.)|Create, Generate, Build, Make, Allocate|
|[Open](/dotnet/api/System.Management.Automation.VerbsCommon.Open) (op)|Altera o estado de um recurso para torná-lo acessível, disponível ou utilizável. Esse verbo é emparelhado com `Close`.||
|[Optimize](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize) (om)|Aumenta a eficácia de um recurso.||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|Remove um item do tipo de uma pilha. Por exemplo, o cmdlet `Pop-Location` altera o local atual para o local mais recentemente inserido na pilha.||
|[Push](/dotnet/api/System.Management.Automation.VerbsCommon.Push) (pu)|Adiciona um item ao tipo de uma pilha. Por exemplo, o cmdlet `Push-Location` envia o local atual para cima da pilha.||
|[Redo](/dotnet/api/System.Management.Automation.VerbsCommon.Redo) (re)|Redefine um recurso para o estado desfeito.||
|[Remove](/dotnet/api/System.Management.Automation.VerbsCommon.Remove) (r)|Exclui um recurso de um contêiner. Por exemplo, o cmdlet `Remove-Variable` exclui uma variável e o valor dela. Esse verbo é emparelhado com `Add`.|Clear, Cut, Dispose, Discard, Erase|
|[Rename](/dotnet/api/System.Management.Automation.VerbsCommon.Rename) (rn)|Altera o nome de um recurso. Por exemplo, o cmdlet `Rename-Item`, que é usado para acessar dados armazenados, altera o nome de um item no armazenamento de dados.|Alterar|
|[Reset](/dotnet/api/System.Management.Automation.VerbsCommon.Reset) (rs)|Define um recurso para o estado original dele.||
|[Resize](/dotnet/api/System.Management.Automation.VerbsCommon.Resize)(rz)|Altera o tamanho de um recurso.||
|[Search](/dotnet/api/System.Management.Automation.VerbsCommon.Search) (sr)|Cria uma referência a um recurso em um contêiner.|Find, Locate|
|[Select](/dotnet/api/System.Management.Automation.VerbsCommon.Select) (sc)|Localiza um recurso em um contêiner. Por exemplo, o cmdlet `Select-String` localiza texto em cadeias de caracteres e arquivos.|Find, Locate|
|[Set](/dotnet/api/System.Management.Automation.VerbsCommon.Set) (s)|Substitui dados em um recurso existente ou cria um recurso que contém alguns dados. Por exemplo, o cmdlet `Set-Date` altera a hora do sistema no computador local. (O verbo `New` também pode ser usado para criar um recurso.) Esse verbo é emparelhado com `Get`.|Write, Reset, Assign, Configure|
|[Show](/dotnet/api/System.Management.Automation.VerbsCommon.Show) (sh)|Torna um recurso visível para o usuário. Esse verbo é emparelhado com `Hide`.|Display, Produce|
|[Skip](/dotnet/api/System.Management.Automation.VerbsCommon.Skip) (sk)|Ignora um ou mais recursos ou pontos em uma sequência.|Bypass, Jump|
|[Split](/dotnet/api/System.Management.Automation.VerbsCommon.Split) (sl)|Separa partes de um recurso. Por exemplo, o cmdlet `Split-Path` retorna partes diferentes de um caminho. Esse verbo é emparelhado com `Join`.|Separate|
|[Step](/dotnet/api/System.Management.Automation.VerbsCommon.Step) (st)|Passa para o próximo ponto ou recurso em uma sequência.||
|[Switch](/dotnet/api/System.Management.Automation.VerbsCommon.Switch) (sw)|Especifica uma ação que alterna entre dois recursos, como alterar entre dois locais, responsabilidades ou estados.||
|[Undo](/dotnet/api/System.Management.Automation.VerbsCommon.Undo) (un)|Define um recurso para o estado anterior dele.||
|[Unlock](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock) (uk)|Libera um recurso que estava bloqueado. Esse verbo é emparelhado com `Lock`.|Release, Unrestrict, Unsecure|
|[Watch](/dotnet/api/System.Management.Automation.VerbsCommon.Watch) (wc)|Inspeciona ou monitora continuamente um recurso em busca de alterações.||

## <a name="communications-verbs"></a>Verbos de comunicações

O PowerShell usa a classe [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications) para definir as ações que se aplicam a comunicações. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Connect](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect) (cc)|Cria um vínculo entre uma origem e um destino. Esse verbo é emparelhado com `Disconnect`.|Join, Telnet|
|[Disconnect](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect) (dc)|Interrompe o vínculo entre uma origem e um destino. Esse verbo é emparelhado com `Connect`.|Break, Logoff|
|[Read](/dotnet/api/System.Management.Automation.VerbsCommunications.Read) (rd)|Adquire informações de uma origem. Esse verbo é emparelhado com `Write`.|Acquire, Prompt, Get|
|[Receive](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive) (rc)|Aceita informações enviadas de uma origem. Esse verbo é emparelhado com `Send`.|Read, Accept, Peek|
|[Send](/dotnet/api/System.Management.Automation.VerbsCommunications.Send) (sd)|Entrega as informações para um destino. Esse verbo é emparelhado com `Receive`.|Put, Broadcast, Mail, Fax|
|[Write](/dotnet/api/System.Management.Automation.VerbsCommunications.Write) (wr)|Adiciona informações a um destino. Esse verbo é emparelhado com `Read`.|Put, Print|

## <a name="data-verbs"></a>Verbos de dados

O PowerShell usa a classe [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData) para definir as ações que se aplicam à manipulação de dados. A tabela a seguir lista a maioria dos verbos definidos.

|Nome do verbo (alias)|Ação|Sinônimos a serem evitados|
|-------------------------|------------|--------------|
|[Backup](/dotnet/api/System.Management.Automation.VerbsData.Backup) (ba)|Armazena dados replicando-os.|Save, Burn, Replicate, Sync|
|[Checkpoint](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint) (ch)|Cria um instantâneo do estado atual dos dados ou da configuração deles.|Diff|
|[Compare](/dotnet/api/System.Management.Automation.VerbsData.Compare) (cr)|Avalia os dados de um recurso em relação aos dados de outro recurso.|Diff|
|[Compress](/dotnet/api/System.Management.Automation.VerbsData.Compress) (cm)|Compacta os dados de um recurso. Faz o emparelhamento com `Expand`.|Compacto|
|[Convert](/dotnet/api/System.Management.Automation.VerbsData.Convert) (cv)|Altera os dados de uma representação para outra quando o cmdlet dá suporte à conversão bidirecional ou quando o cmdlet dá suporte à conversão entre vários tipos de dados.|Change, Resize, Resample|
|[ConvertFrom](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (cf)|Converte um tipo principal de entrada (o substantivo do cmdlet indica a entrada) em um ou mais tipos de saída com suporte.|Export, Output, Out|
|[ConvertTo](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (ct)|Converte de um ou mais tipos de entrada em um tipo de saída primário (o substantivo do cmdlet indica o tipo de saída).|Import, Input, In|
|[Dismount](/dotnet/api/System.Management.Automation.VerbsData.Dismount) (dm)|Desanexa uma entidade nomeada de um local. Esse verbo é emparelhado com `Mount`.|Unmount, Unlink|
|[Edit](/dotnet/api/System.Management.Automation.VerbsData.Edit) (ed)|Modifica os dados existentes adicionando ou removendo o conteúdo.|Change, Update, Modify|
|[Expand](/dotnet/api/System.Management.Automation.VerbsData.Expand) (en)|Restaura os dados de um recurso que foi compactado para o estado original dele. Esse verbo é emparelhado com `Compress`.|Explode, Uncompress|
|[Export](/dotnet/api/System.Management.Automation.VerbsData.Export) (ep)|Encapsula a entrada primária em um armazenamento de dados persistente, como um arquivo, ou em um formato de intercâmbio. Esse verbo é emparelhado com `Import`.|Extract, Backup|
|[Import](/dotnet/api/System.Management.Automation.VerbsData.Import) (ip)|Cria um recurso com base nos dados armazenados em um armazenamento de dados persistente (como um arquivo) ou em um formato de intercâmbio. Por exemplo, o cmdlet `Import-CSV` importa dados de um arquivo CSV (valores separados por vírgula) para objetos que podem ser usados por outros cmdlets. Esse verbo é emparelhado com `Export`.|BulkLoad, Load|
|[Initialize](/dotnet/api/System.Management.Automation.VerbsData.Initialize) (in)|Prepara um recurso para uso e o define como um estado padrão.|Erase, Init, Renew, Rebuild, Reinitialize, Setup|
|[Limit](/dotnet/api/System.Management.Automation.VerbsData.Limit) (l)|Aplica restrições a um recurso.|Quota|
|[Merge](/dotnet/api/System.Management.Automation.VerbsData.Merge) (mg)|Cria um recurso de vários recursos.|Combine, Join|
|[Mount](/dotnet/api/System.Management.Automation.VerbsData.Mount) (mt)|Anexa uma entidade nomeada a um local. Esse verbo é emparelhado com `Dismount`.|Conectar|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|Envia dados para fora do ambiente. Por exemplo, o cmdlet `Out-Printer` envia dados para uma impressora.||
|[Publish](/dotnet/api/System.Management.Automation.VerbsData.Publish) (pb)|Disponibiliza um recurso para outras pessoas. Esse verbo é emparelhado com `Unpublish`.|Deploy, Release, Install|
|[Restore](/dotnet/api/System.Management.Automation.VerbsData.Restore) (rr)|Define um recurso para um estado predefinido, como um estado definido por `Checkpoint`. Por exemplo, o cmdlet `Restore-Computer` inicia uma restauração do sistema no computador local.|Repair, Return, Undo, Fix|
|[Save](/dotnet/api/System.Management.Automation.VerbsData.Save) (sv)|Preserva os dados para evitar perda.||
|[Sync](/dotnet/api/System.Management.Automation.VerbsData.Sync) (sy)|Garante que dois ou mais recursos estejam no mesmo estado.|Replicate, Coerce, Match|
|[Unpublish](/dotnet/api/System.Management.Automation.VerbsData.Unpublish) (ub)|Torna um recurso indisponível para outras pessoas. Esse verbo é emparelhado com `Publish`.|Uninstall, Revert, Hide|
|[Update](/dotnet/api/System.Management.Automation.VerbsData.Update) (ud)|Atualiza um recurso para manter o estado, a precisão ou a conformidade dele. Por exemplo, o cmdlet `Update-FormatData` atualiza e adiciona arquivos de formatação ao console do PowerShell atual.|Refresh, Renew, Recalculate, Re-index|

## <a name="diagnostic-verbs"></a>Verbos de diagnóstico

O PowerShell usa a classe [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic) para definir as ações que se aplicam ao diagnóstico. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Debug](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug) (db)|Examina um recurso para diagnosticar problemas operacionais.|Diagnosticar|
|[Measure](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (ms)|Identifica os recursos que são consumidos por uma operação especificada ou recupera estatísticas sobre um recurso.|Calculate, Determine, Analyze|
|[Repair](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair) (rp)|Restaura um recurso para uma condição utilizável|Fix, Restore|
|[Resolve](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve) (rv)|Mapeia uma representação abreviada de um recurso para uma representação mais completa.|Expand, Determine|
|[Test](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test) (t)|Verifica a operação ou a consistência de um recurso.|Diagnose, Analyze, Salvage, Verify|
|[Trace](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace) (tr)|Controla as atividades de um recurso.|Track, Follow, Inspect, Dig|

## <a name="lifecycle-verbs"></a>Verbos de ciclo de vida

O PowerShell usa a classe [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) para definir as ações que se aplicam ao ciclo de vida de um recurso. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Approve](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve) (ap)|Confirma o status de um recurso ou processo ou concorda com ele.||
|[Assert](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert) (as)|Afirma o estado de um recurso.|Certify|
|[Build](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build) (bd)|Cria um artefato (geralmente um binário ou documento) de algum conjunto de arquivos de entrada (geralmente código-fonte ou documentos declarativos). O verbo foi adicionado no PowerShell 6.||
|[Complete](/dotnet/api/system.management.automation.host.buffercelltype?view=powershellsdk-1.1.0) (cp)|Conclui uma operação.||
|[Confirm](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm) (cn)|Reconhece, verifica ou valida o estado de um recurso ou processo.|Acknowledge, Agree, Certify, Validate, Verify|
|[Deny](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny) (dn)|Recusa ou bloqueia o estado de um recurso ou processo ou faz objeção ou oposição a ele.|Block, Object, Refuse, Reject|
|[Deploy](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy) (dp)|Envia um aplicativo, site ou solução para um destino remoto de modo que um consumidor dessa solução possa acessá-lo após a conclusão da implantação. O verbo foi adicionado no PowerShell 6.||
|[Disable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable) (d)|Configura um recurso para um estado indisponível ou inativo. Por exemplo, o cmdlet `Disable-PSBreakpoint` torna um ponto de interrupção inativo. Esse verbo é emparelhado com `Enable`.|Halt, Hide|
|[Enable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable) (e)|Configura um recurso para um estado disponível ou ativo. Por exemplo, o cmdlet `Enable-PSBreakpoint` torna um ponto de interrupção ativo. Esse verbo é emparelhado com `Disable`.|Start, Begin|
|[Install](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install) (is)|Coloca um recurso em um local e, opcionalmente, o inicializa. Esse verbo é emparelhado com `Uninstall`.|Instalação|
|[Invoke](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke) (i)|Executa uma ação, como executar um comando ou um método.|Run, Start|
|[Register](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register) (rg)|Cria uma entrada para um recurso em um repositório, como um banco de dados. Esse verbo é emparelhado com `Unregister`.||
|[Request](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request) (rq)|Solicita um recurso ou permissões.||
|[Restart](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart) (rt)|Interrompe uma operação e a inicia novamente. Por exemplo, o cmdlet `Restart-Service` para e inicia um serviço.|Reciclar|
|[Resume](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume) (ru)|Inicia uma operação que foi suspensa. Por exemplo, o cmdlet `Resume-Service` inicia um serviço que foi suspenso. Esse verbo é emparelhado com `Suspend`.||
|[Start](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start) (sa)|Inicia uma operação. Por exemplo, o cmdlet `Start-Service` inicia um serviço. Esse verbo é emparelhado com `Stop`.|Launch, Initiate, Boot|
|[Stop](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop) (sp)|Descontinua uma atividade. Esse verbo é emparelhado com `Start`.|End, Kill, Terminate, Cancel|
|[Submit](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit) (sb)|Apresenta um recurso para aprovação.|Postar|
|[Suspend](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend) (ss)|Pausa uma atividade. Por exemplo, o cmdlet `Suspend-Service` pausa um serviço. Esse verbo é emparelhado com `Resume`.|Pausar|
|[Uninstall](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall) (us)|Remove um recurso de um local indicado. Esse verbo é emparelhado com `Install`.||
|[Unregister](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister) (ur)|Remove a entrada de um recurso de um repositório. Esse verbo é emparelhado com `Register`.|Remover|
|[Wait](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait) (w)|Pausa uma operação até que um evento especificado ocorra. Por exemplo, o cmdlet `Wait-Job` pausa as operações até que um ou mais dos trabalhos em segundo plano sejam concluídos.|Sleep, Pause|

## <a name="security-verbs"></a>Verbos de segurança

O PowerShell usa a classe [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity) para definir as ações que se aplicam à segurança. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Block](/dotnet/api/System.Management.Automation.VerbsSecurity.Block) (bl)|Restringe o acesso a um recurso. Esse verbo é emparelhado com `Unblock`.|Prevent, Limit, Deny|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (gr)|Permite o acesso a um recurso. Esse verbo é emparelhado com `Revoke`.|Allow, Enable|
|[Protect](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect) (pt)|Protege um recurso contra ataque ou perda. Esse verbo é emparelhado com `Unprotect`.|Encrypt, Safeguard, Seal|
|[Revoke](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke) (rk)|Especifica uma ação que não permite o acesso a um recurso. Esse verbo é emparelhado com `Grant`.|Remove, Disable|
|[Unblock](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock) (ul)|Remove as restrições a um recurso. Esse verbo é emparelhado com `Block`.|Clear, Allow|
|[Unprotect](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect) (up)|Remove as proteções de um recurso que foram adicionadas para evitar ataques ou perdas. Esse verbo é emparelhado com `Protect`.|Decrypt, Unseal|

## <a name="other-verbs"></a>Outros verbos

O PowerShell usa a classe [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther) para definir nomes de verbo canônicos não adequados a uma categoria de nome de verbo específica, como os verbos de nomes comuns, de comunicações, de dados, de ciclo de vida ou de verbo de segurança.

|Verbo (alias)|Ação|Sinônimos a serem evitados|
|--------------------|------------|--------------|
|[Use](/dotnet/api/System.Management.Automation.VerbsOther.Use) (u)|Usa ou inclui um recurso para fazer algo.||

## <a name="see-also"></a>Consulte Também

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)
- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)
- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)
- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)
- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)
- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)
- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)
- [Declaração do cmdlet](./cmdlet-class-declaration.md)
- [Guia do programador do Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md)
- [SDK do Shell do Windows PowerShell](../windows-powershell-reference.md)
