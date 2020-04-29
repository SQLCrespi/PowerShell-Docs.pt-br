---
title: Verbos aprovados para comandos do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- action names [PowerShell SDK]
- verb names [PowerShell SDK]
- cmdlets [PowerShell SDK], verb names
ms.assetid: 2d4e58a9-05bc-437c-86b9-d8d55cba7d48
caps.latest.revision: 36
ms.openlocfilehash: b1e551c93540bd6769021aaa2bff08cfa3879e2c
ms.sourcegitcommit: 7c7f8bb9afdc592d07bf7ff4179d000a48716f13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82174102"
---
# <a name="approved-verbs-for-powershell-commands"></a>Verbos aprovados para comandos do PowerShell

O PowerShell usa um par verbo-substantivo para os nomes dos cmdlets e para suas classes derivadas do Microsoft .NET Framework. Por exemplo, o `Get-Command` cmdlet fornecido pelo PowerShell é usado para recuperar todos os comandos que são registrados no PowerShell. A parte de verbo do nome identifica a ação que o cmdlet executa. A parte do substantivo do nome identifica a entidade na qual a ação é executada.

> [!NOTE]
> O PowerShell usa o termo *verbo* para descrever uma palavra que implica uma ação, mesmo que essa palavra não seja um verbo padrão no idioma inglês. Por exemplo, o termo *novo* é um nome de verbo válido do PowerShell porque ele implica uma ação, embora não seja um verbo no idioma inglês.

## <a name="verb-naming-rules"></a>Regras de nomenclatura de verbo

A lista a seguir fornece diretrizes a serem consideradas quando você escolhe o verbo para um nome de cmdlet:

- Ao especificar o verbo, recomendamos que você use um dos nomes de verbo predefinidos fornecidos pelo PowerShell (aliases para esses verbos predefinidos estão incluídos nas tabelas a seguir). Ao usar um verbo predefinido, você garante a consistência entre os cmdlets criados por você, os cmdlets fornecidos pelo PowerShell e os cmdlets projetados por outros.

- Use os verbos predefinidos para descrever o escopo geral da ação e use parâmetros para refinar ainda mais a ação do cmdlet.

- Para impor a consistência entre os cmdlets, não use um sinônimo de um verbo aprovado.

- Use apenas o formulário de cada verbo listado neste tópico. Por exemplo, use "Get", mas não use "obter" ou "Gets".

- Use o uso de maiúsculas e minúsculas do Pascal para verbos. No Pascal, a letra inicial de cada palavra é capitalizada, como "ForEach".

- Não use os seguintes verbos reservados ou aliases. Esses verbos são usados pela linguagem do PowerShell ou por cmdlets de caso especial fornecidos pelo PowerShell.
  - ForEach (foreach)
  - Formato (f)
  - Grupo (GP)
  - Classificar (Sr)
  - T (te)
  - Onde (qu)

Uma lista completa de verbos pode ser exibida usando o `Get-Verb` cmdlet.

## <a name="similar-verbs-for-different-actions"></a>Verbos semelhantes para ações diferentes

Os seguintes verbos semelhantes representam ações diferentes.

### <a name="new-vs-set"></a>Novo vs. conjunto

O `New` verbo é usado para criar um novo recurso. O `Set` verbo é usado para modificar um recurso existente, criando opcionalmente o recurso se ele não existir, como o `Set-Variable` cmdlet.

### <a name="find-vs-search"></a>Localizar vs. pesquisa

O `Find` verbo é usado para procurar um objeto. O `Search` verbo é usado para criar uma referência a um recurso em um contêiner.

### <a name="get-vs-read"></a>Obter versus ler

O `Get` verbo é usado para recuperar um recurso, como um arquivo. O `Read` verbo é usado para obter informações de uma fonte, como um arquivo.

### <a name="invoke-vs-start"></a>Invocar versus iniciar

O `Invoke` verbo é usado para executar uma operação que geralmente é uma operação síncrona, como executar um comando. O `Start` verbo é usado para iniciar uma operação que geralmente é uma operação assíncrona, como iniciar um processo.

### <a name="ping-vs-test"></a>Ping versus teste

Use o `Test` verbo.

## <a name="common-verbs"></a>Verbos comuns

O PowerShell usa a classe de enumeração [System. Management. Automation. VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon) para definir ações genéricas que podem ser aplicadas a quase qualquer cmdlet. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Adicionar](/dotnet/api/System.Management.Automation.VerbsCommon.Add) (a)|Adiciona um recurso a um contêiner ou anexa um item a outro item. Por exemplo, o `Add-Content` cmdlet adiciona o conteúdo a um arquivo. Esse verbo é emparelhado com `Remove`.|Para esta ação, não use verbos como acrescentar, Attach, Concatenate ou INSERT.|
|[Limpar](/dotnet/api/System.Management.Automation.VerbsCommon.Clear) (CL)|Remove todos os recursos de um contêiner, mas não exclui o contêiner. Por exemplo, o `Clear-Content` cmdlet Remove o conteúdo de um arquivo, mas não exclui o arquivo.|Para esta ação, não use verbos como liberar, apagar, liberar, desmarcar, remover ou anular.|
|[Fechar](/dotnet/api/System.Management.Automation.VerbsCommon.Close) (CS)|Altera o estado de um recurso para torná-lo inacessível, indisponível ou inutilizável. Este verbo é emparelhado com`Open.`||
|[Copiar](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (CP)|Copia um recurso para outro nome ou para outro contêiner. Por exemplo, o `Copy-Item` cmdlet usado para acessar dados armazenados copia um item de um local no repositório de dados para outro local.|Para essa ação, não use verbos como duplicar, clonar, replicar ou sincronizar.|
|[Enter](/dotnet/api/System.Management.Automation.VerbsCommon.Enter) (et)|Especifica uma ação que permite ao usuário se mover para um recurso. Por exemplo, o `Enter-PSSession` cmdlet coloca o usuário em uma sessão interativa. Esse verbo é emparelhado com `Exit`.|Para essa ação, não use verbos como Push ou into.|
|[Sair](/dotnet/api/System.Management.Automation.VerbsCommon.Exit) (ex.)|Define o ambiente ou contexto atual para o contexto usado mais recentemente. Por exemplo, o `Exit-PSSession` cmdlet coloca o usuário na sessão que foi usada para iniciar a sessão interativa. Esse verbo é emparelhado com `Enter`.|Para essa ação, não use verbos como pop ou out.|
|[Localizar](/dotnet/api/System.Management.Automation.VerbsCommon.Find) (FD)|Procura um objeto em um contêiner que é desconhecido, implícito, opcional ou especificado.||
|[Formato](/dotnet/api/System.Management.Automation.VerbsCommon.Format) (f)|Organiza objetos em um layout ou formulário especificado.||
|[Get](/dotnet/api/System.Management.Automation.VerbsCommon.Get) (g)|Especifica uma ação que recupera um recurso. Esse verbo é emparelhado com `Set`.|Para esta ação, não use verbos como leitura, abertura, Cat, tipo, dir, obter, despejar, adquirir, examinar, localizar ou Pesquisar.|
|[Ocultar](/dotnet/api/System.Management.Automation.VerbsCommon.Hide) (h)|Torna um recurso não detectável. Por exemplo, um cmdlet cujo nome inclui o verbo ocultar pode ocultar um serviço de um usuário. Esse verbo é emparelhado com `Show`.|Para esta ação, não use um verbo como bloco.|
|[Junção](/dotnet/api/System.Management.Automation.VerbsCommon.Join) (j)|Combina recursos em um recurso. Por exemplo, o `Join-Path` cmdlet combina um caminho com um de seus caminhos filho para criar um único caminho. Esse verbo é emparelhado com `Split`.|Para esta ação, não use verbos como combinar, unir, conectar ou associar.|
|[Bloqueio](/dotnet/api/System.Management.Automation.VerbsCommon.Lock) (LK)|Protege um recurso. Esse verbo é emparelhado com `Unlock`.|Para essa ação, não use verbos como restrict ou Secure.|
|[Mover](/dotnet/api/System.Management.Automation.VerbsCommon.Move) (m)|Move um recurso de um local para outro. Por exemplo, o `Move-Item` cmdlet Move um item de um local no armazenamento de dados para outro local.|Para esta ação, não use verbos como transferência, nome ou migração.|
|[Novo](/dotnet/api/System.Management.Automation.VerbsCommon.New) (n)|Cria um recurso. (O `Set` verbo também pode ser usado ao criar um recurso que inclui dados, como o `Set-Variable` cmdlet.)|Para esta ação, não use verbos como criar, gerar, compilar, fazer ou alocar.|
|[Abrir](/dotnet/api/System.Management.Automation.VerbsCommon.Open) (op)|Altera o estado de um recurso para torná-lo acessível, disponível ou utilizável. Esse verbo é emparelhado com `Close`.||
|[Otimizar](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize) (OM)|Aumenta a eficácia de um recurso.||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|Remove um item da parte superior de uma pilha. Por exemplo, o `Pop-Location` cmdlet altera o local atual para o local que foi enviado mais recentemente para a pilha.||
|[Push](/dotnet/api/System.Management.Automation.VerbsCommon.Push) (PU)|Adiciona um item à parte superior de uma pilha. Por exemplo, o `Push-Location` cmdlet envia o local atual para a pilha.||
|[Refazer](/dotnet/api/System.Management.Automation.VerbsCommon.Redo) (re)|Redefine um recurso para o estado que foi desfeito.||
|[Remover](/dotnet/api/System.Management.Automation.VerbsCommon.Remove) (r)|Exclui um recurso de um contêiner. Por exemplo, o `Remove-Variable` cmdlet exclui uma variável e seu valor. Esse verbo é emparelhado com `Add`.|Para esta ação, não use verbos como Clear, Cut, Dispose, Discard ou Erase.|
|[Renomear](/dotnet/api/System.Management.Automation.VerbsCommon.Rename) (RN)|Altera o nome de um recurso. Por exemplo, o `Rename-Item` cmdlet, que é usado para acessar dados armazenados, altera o nome de um item no repositório de dados.|Para esta ação, não use um verbo como alterar.|
|[Redefinir](/dotnet/api/System.Management.Automation.VerbsCommon.Reset) (RS)|Define um recurso de volta para seu estado original.||
|[Pesquisar](/dotnet/api/System.Management.Automation.VerbsCommon.Search) (Sr)|Cria uma referência a um recurso em um contêiner.|Para essa ação, não use verbos como localizar ou localizar.|
|[Select](/dotnet/api/System.Management.Automation.VerbsCommon.Select) (SC)|Localiza um recurso em um contêiner. Por exemplo, o `Select-String` cmdlet localiza texto em cadeias de caracteres e arquivos.|Para essa ação, não use verbos como localizar ou localizar.|
|[Conjunto](/dotnet/api/System.Management.Automation.VerbsCommon.Set) (s)|Substitui dados em um recurso existente ou cria um recurso que contém alguns dados. Por exemplo, o `Set-Date` cmdlet altera a hora do sistema no computador local. (O `New` verbo também pode ser usado para criar um recurso.) Esse verbo é emparelhado com `Get`.|Para esta ação, não use verbos como gravar, redefinir, atribuir ou configurar.|
|[Mostrar](/dotnet/api/System.Management.Automation.VerbsCommon.Show) (SH)|Torna um recurso visível para o usuário. Esse verbo é emparelhado com `Hide`.|Para esta ação, não use verbos como exibir ou produzir.|
|[Ignorar](/dotnet/api/System.Management.Automation.VerbsCommon.Skip) (SK)|Ignora um ou mais recursos ou pontos em uma sequência.|Para esta ação, não use um verbo como ignorar ou saltar.|
|[Dividir](/dotnet/api/System.Management.Automation.VerbsCommon.Split) (SL)|Separa partes de um recurso. Por exemplo, o `Split-Path` cmdlet retorna partes diferentes de um caminho. Esse verbo é emparelhado com `Join`.|Para essa ação, não use um verbo separado.|
|[Etapa](/dotnet/api/System.Management.Automation.VerbsCommon.Step) (St)|Move para o próximo ponto ou recurso em uma sequência.||
|[Switch](/dotnet/api/System.Management.Automation.VerbsCommon.Switch) (SW)|Especifica uma ação que alterna entre dois recursos, como alterar entre dois locais, responsabilidades ou Estados.||
|[Desfazer](/dotnet/api/System.Management.Automation.VerbsCommon.Undo) (un)|Define um recurso para seu estado anterior.||
|[Desbloquear](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock) (Reino Unido)|Libera um recurso que foi bloqueado. Esse verbo é emparelhado com `Lock`.|Para esta ação, não use verbos como liberar, não restringir ou não proteger.|
|[Assista](/dotnet/api/System.Management.Automation.VerbsCommon.Watch) (WC)|Inspeciona ou monitora continuamente um recurso em busca de alterações.||

## <a name="communications-verbs"></a>Verbos de comunicação

O PowerShell usa a classe [System. Management. Automation. VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications) para definir ações que se aplicam a comunicações. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Conectar](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect) (CC)|Cria um vínculo entre uma origem e um destino. Esse verbo é emparelhado com `Disconnect`.|Para essa ação, não use verbos como join ou telnet.|
|[Desconectar](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect) (DC)|Interrompe o vínculo entre uma origem e um destino. Esse verbo é emparelhado com `Connect`.|Para essa ação, não use verbos como Break ou logoff.|
|[Leitura](/dotnet/api/System.Management.Automation.VerbsCommunications.Read) (RD)|Adquire informações de uma fonte. Esse verbo é emparelhado com `Write`.|Para esta ação, não use verbos como adquirir, avisar ou obter.|
|[Receber](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive) (RC)|Aceita informações enviadas de uma origem. Esse verbo é emparelhado com `Send`.|Para esta ação, não use verbos como Read, Accept ou Peek.|
|[Enviar](/dotnet/api/System.Management.Automation.VerbsCommunications.Send) (SD)|Fornece informações para um destino. Esse verbo é emparelhado com `Receive`.|Para esta ação, não use verbos como put, Broadcast, mail ou fax.|
|[Gravação](/dotnet/api/System.Management.Automation.VerbsCommunications.Write) (WR)|Adiciona informações a um destino. Esse verbo é emparelhado com `Read`.|Para esta ação, não use verbos como Put ou Print.|

## <a name="data-verbs"></a>Verbos de dados

O PowerShell usa a classe [System. Management. Automation. VerbsData](/dotnet/api/System.Management.Automation.VerbsData) para definir as ações que se aplicam à manipulação de dados. A tabela a seguir lista a maioria dos verbos definidos.

|Nome do verbo (alias)|Ação|Comentários|
|-------------------------|------------|--------------|
|[Backup](/dotnet/api/System.Management.Automation.VerbsData.Backup) (BA)|Armazena dados replicando-os.|Para essa ação, não use verbos como salvar, gravar, replicar ou sincronizar.|
|[Ponto de verificação](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint) (CH)|Cria um instantâneo do estado atual dos dados ou de sua configuração.|Para essa ação, não use um verbo como diff.|
|[Comparar](/dotnet/api/System.Management.Automation.VerbsData.Compare) (CR)|Avalia os dados de um recurso em relação aos dados de outro recurso.|Para essa ação, não use um verbo como diff.|
|[Compactar](/dotnet/api/System.Management.Automation.VerbsData.Compress) (cm)|Compacta os dados de um recurso. Pares com `Expand`.|Para esta ação, não use um verbo como Compact.|
|[Converter](/dotnet/api/System.Management.Automation.VerbsData.Convert) (CV)|Altera os dados de uma representação para outra quando o cmdlet dá suporte à conversão bidirecional ou quando o cmdlet dá suporte à conversão entre vários tipos de dados.|Para esta ação, não use verbos como alterar, redimensionar ou reamostrar.|
|[ConvertFrom](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (CF)|Converte um tipo principal de entrada (o substantivo do cmdlet indica a entrada) para um ou mais tipos de saída com suporte.|Para essa ação, não use verbos como exportar, saída ou sair.|
|[ConvertTo](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (CT)|Converte de um ou mais tipos de entrada para um tipo de saída primário (o substantivo do cmdlet indica o tipo de saída).|Para essa ação, não use verbos como importar, inserir ou em.|
|[Desmontar](/dotnet/api/System.Management.Automation.VerbsData.Dismount) (DM)|Desanexa uma entidade nomeada de um local. Esse verbo é emparelhado com `Mount`.|Para esta ação, não use verbos como desmontar ou desvincular.|
|[Editar](/dotnet/api/System.Management.Automation.VerbsData.Edit) (Ed)|Modifica os dados existentes adicionando ou removendo o conteúdo.|Para esta ação, não use verbos como alterar, atualizar ou modificar.|
|[Expandir](/dotnet/api/System.Management.Automation.VerbsData.Expand) (EN)|Restaura os dados de um recurso que foi compactado para seu estado original. Esse verbo é emparelhado com `Compress`.|Para essa ação, não use verbos como explosão ou descompactação.|
|[Exportar](/dotnet/api/System.Management.Automation.VerbsData.Export) (EP)|Encapsula a entrada primária em um repositório de dados persistente, como um arquivo ou em um formato de intercâmbio. Esse verbo é emparelhado com `Import`.|Para essa ação, não use verbos como Extract ou backup.|
|[Grupo](/dotnet/api/System.Management.Automation.VerbsData.Group) (GP)|Organiza ou associa um ou mais recursos.|Para esta ação, não use verbos como agregar, organizar, associar ou correlacionar.|
|[Importar](/dotnet/api/System.Management.Automation.VerbsData.Import) (IP)|Cria um recurso a partir de dados armazenados em um repositório de dados persistente (como um arquivo) ou em um formato de intercâmbio. Por exemplo, o `Import-CSV` cmdlet importa dados de um arquivo CSV (valores separados por vírgula) para objetos que podem ser usados por outros cmdlets. Esse verbo é emparelhado com `Export`.|Para essa ação, não use verbos como carregamento em massa ou Load.|
|[Inicializar](/dotnet/api/System.Management.Automation.VerbsData.Initialize) (em)|Prepara um recurso para uso e o define como um estado padrão.|Para esta ação, não use verbos como apagar, iniciar, renovar, recompilar, reinicializar ou configurar.|
|[Limite](/dotnet/api/System.Management.Automation.VerbsData.Limit) (l)|Aplica restrições a um recurso.|Para esta ação, não use um verbo como cota.|
|[Mesclar](/dotnet/api/System.Management.Automation.VerbsData.Merge) (mg)|Cria um recurso único de vários recursos.|Para esta ação, não use verbos como combinar ou unir.|
|[Montagem](/dotnet/api/System.Management.Automation.VerbsData.Mount) (MT)|Anexa uma entidade nomeada a um local. Esse verbo é emparelhado com `Dismount`.|Para esta ação, não use o verbo Connect.|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|Envia dados para fora do ambiente. Por exemplo, o `Out-Printer` cmdlet envia dados para uma impressora.||
|[Publicar](/dotnet/api/System.Management.Automation.VerbsData.Publish) (PB)|Disponibiliza um recurso para outras pessoas. Esse verbo é emparelhado com `Unpublish`.|Para essa ação, não use verbos como implantar, liberar ou instalar.|
|[Restauração](/dotnet/api/System.Management.Automation.VerbsData.Restore) (RR)|Define um recurso para um estado predefinido, como um estado definido por `Checkpoint`. Por exemplo, o `Restore-Computer` cmdlet inicia uma restauração do sistema no computador local.|Para essa ação, não use verbos como reparar, retornar, desfazer ou corrigir.|
|[Salvar](/dotnet/api/System.Management.Automation.VerbsData.Save) (VA)|Preserva os dados para evitar perda.||
|[Sincronizar](/dotnet/api/System.Management.Automation.VerbsData.Sync) (Sy)|Garante que dois ou mais recursos estejam no mesmo estado.|Para essa ação, não use verbos como replicar, forçar ou corresponder.|
|[Cancelar publicação](/dotnet/api/System.Management.Automation.VerbsData.Unpublish) (UB)|Torna um recurso indisponível para outros. Esse verbo é emparelhado com `Publish`.|Para essa ação, não use verbos como desinstalar, reverter ou ocultar.|
|[Atualização](/dotnet/api/System.Management.Automation.VerbsData.Update) (UD)|Coloca um recurso atualizado para manter seu estado, exatidão, conformidade ou conformidade. Por exemplo, o `Update-FormatData` cmdlet atualiza e adiciona arquivos de formatação ao console do PowerShell atual.|Para esta ação, não use verbos como atualizar, renovar, recalcular ou reindexar.|

## <a name="diagnostic-verbs"></a>Verbos de diagnóstico

O PowerShell usa a classe [System. Management. Automation. VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic) para definir as ações que se aplicam ao diagnóstico. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Depurar](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug) (DB)|Examina um recurso para diagnosticar problemas operacionais.|Para esta ação, não use um verbo como diagnosticar.|
|[Medida](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (MS)|Identifica os recursos que são consumidos por uma operação especificada ou recupera estatísticas sobre um recurso.|Para esta ação, não use verbos como Calculate, determine ou Analyze.|
|[Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (PI)|Use o `Test` verbo.||
|[Reparo](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair) (RP)|Restaura um recurso para uma condição utilizável|Para essa ação, não use verbos como correção ou restauração.|
|[Resolver](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve) (RV)|Mapeia uma representação abreviada de um recurso para uma representação mais completa.|Para esta ação, não use verbos como expandir ou determinar.|
|[Teste](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test) (t)|Verifica a operação ou a consistência de um recurso.|Para essa ação, não use verbos como diagnosticar, analisar, recuperar ou verificar.|
|[Trace](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace) (TR)|Controla as atividades de um recurso.|Para esta ação, não use verbos como rastrear, seguir, inspecionar ou procurar.|

## <a name="lifecycle-verbs"></a>Verbos do ciclo de vida

O PowerShell usa a classe [System. Management. Automation. VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) para definir as ações que se aplicam ao ciclo de vida de um recurso. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Aprovar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve) (AP)|Confirma ou concorda com o status de um recurso ou processo.||
|[Assert](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert) (as)|Afirma o estado de um recurso.|Para esta ação, não use um verbo como certificar.|
|[Build](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build) (BD)|Cria um artefato (geralmente um binário ou documento) de algum conjunto de arquivos de entrada (geralmente, código-fonte ou documentos declarativos)|Este verbo foi adicionado no PowerShell V6|
|[Completo](/dotnet/api/system.management.automation.host.buffercelltype?view=powershellsdk-1.1.0) (CP)|Conclui uma operação.||
|[Confirmar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm) (CN)|Reconhece, verifica ou valida o estado de um recurso ou processo.|Para esta ação, não use verbos como reconhecer, concordar, certificar, validar ou verificar.|
|[Negar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny) (DN)|Recusa, objetos, bloqueia ou oposta ao estado de um recurso ou processo.|Para esta ação, não use verbos como bloquear, objeto, recusar ou rejeitar.|
|[Implantar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy) (DP)|Envia um aplicativo, site ou solução para um destino remoto [s] de forma que um consumidor dessa solução possa acessá-lo após a conclusão da implantação|Este verbo foi adicionado no PowerShell V6|
|[Desabilitar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable) (d)|Configura um recurso para um estado indisponível ou inativo. Por exemplo, o `Disable-PSBreakpoint` cmdlet torna um ponto de interrupção inativo. Esse verbo é emparelhado com `Enable`.|Para esta ação, não use verbos como HALT ou Hide.|
|[Habilitar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable) (e)|Configura um recurso para um estado disponível ou ativo. Por exemplo, o `Enable-PSBreakpoint` cmdlet torna um ponto de interrupção ativo. Esse verbo é emparelhado com `Disable`.|Para esta ação, não use verbos como iniciar ou iniciar.|
|[Instalar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install) (is)|Coloca um recurso em um local e, opcionalmente, o inicializa. Esse verbo é emparelhado com `Uninstall`.|Para essa ação, não use um verbo, como a instalação.|
|[Invocar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke) (i)|Executa uma ação, como executar um comando ou um método.|Para essa ação, não use verbos como executar ou iniciar.|
|[Registrar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register) (RG)|Cria uma entrada para um recurso em um repositório, como um banco de dados. Esse verbo é emparelhado com `Unregister`.||
|[Solicitação](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request) (RQ)|Solicita um recurso ou solicita permissões.||
|[Reiniciar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart) (RT)|Interrompe uma operação e a inicia novamente. Por exemplo, o `Restart-Service` cmdlet para e inicia um serviço.|Para esta ação, não use um verbo como reciclar.|
|[Currículo](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume) (ru)|Inicia uma operação que foi suspensa. Por exemplo, o `Resume-Service` cmdlet inicia um serviço que foi suspenso. Esse verbo é emparelhado com `Suspend`.||
|[Início](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start) (SA)|Inicia uma operação. Por exemplo, o `Start-Service` cmdlet inicia um serviço. Esse verbo é emparelhado com `Stop`.|Para essa ação, não use verbos como iniciar, iniciar ou inicializar.|
|[Parar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop) (SP)|Descontinua uma atividade. Esse verbo é emparelhado com `Start`.|Para essa ação, não use verbos como end, Kill, Terminate ou Cancel.|
|[Enviar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit) (SB)|Apresenta um recurso para aprovação.|Para esta ação, não use um verbo como post.|
|[Suspender](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend) (SS)|Pausa uma atividade. Por exemplo, o `Suspend-Service` cmdlet pausa um serviço. Esse verbo é emparelhado com `Resume`.|Para esta ação, não use um verbo como PAUSE.|
|[Desinstalar](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall) (EUA)|Remove um recurso de um local indicado. Esse verbo é emparelhado com `Install`.||
|[Cancelar o registro](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister) (seu)|Remove a entrada de um recurso de um repositório. Esse verbo é emparelhado com `Register`.|Para esta ação, não use um verbo como remover.|
|[Espera](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait) (w)|Pausa uma operação até que um evento especificado ocorra. Por exemplo, o `Wait-Job` cmdlet pausa as operações até que um ou mais dos trabalhos em segundo plano sejam concluídos.|Para esta ação, não use verbos como Sleep ou PAUSE.|

## <a name="security-verbs"></a>Verbos de segurança

O PowerShell usa a classe [System. Management. Automation. VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity) para definir as ações que se aplicam à segurança. A tabela a seguir lista a maioria dos verbos definidos.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Bloquear](/dotnet/api/System.Management.Automation.VerbsSecurity.Block) (BL)|Restringe o acesso a um recurso. Esse verbo é emparelhado com `Unblock`.|Para essa ação, não use verbos como impedir, limitar ou negar.|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (GR)|Permite o acesso a um recurso. Esse verbo é emparelhado com `Revoke`.|Para essa ação, não use verbos como permitir ou habilitar.|
|[Proteger](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect) (pt)|Protege um recurso contra ataque ou perda. Esse verbo é emparelhado com `Unprotect`.|Para esta ação, não use verbos como Encrypt, salvaguarda ou lacre.|
|[REVOKE](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke) (r)|Especifica uma ação que não permite o acesso a um recurso. Esse verbo é emparelhado com `Grant`.|Para esta ação, não use verbos como remover ou desabilitar.|
|[Desbloquear](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock) (UL)|Remove as restrições a um recurso. Esse verbo é emparelhado com `Block`.|Para esta ação, não use verbos como Clear ou Allow.|
|[Desproteger](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect) (para cima)|Remove as proteções de um recurso que foram adicionadas para evitar ataques ou perdas. Esse verbo é emparelhado com `Protect`.|Para esta ação, não use verbos como descriptografar ou deslacrar.|

## <a name="other-verbs"></a>Outros verbos

O PowerShell usa a classe [System. Management. Automation. VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther) para definir nomes de verbo canônicos que não se ajustam a uma categoria de nome de verbo específica, como os verbos comum, de comunicações, de dados, de ciclo de vida ou de nomes de verbo de segurança.

|Verbo (alias)|Ação|Comentários|
|--------------------|------------|--------------|
|[Usar](/dotnet/api/System.Management.Automation.VerbsOther.Use) (u)|Usa ou inclui um recurso para fazer algo.||

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)

[System. Management. Automation. VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)

[System. Management. Automation. VerbsData](/dotnet/api/System.Management.Automation.VerbsData)

[System. Management. Automation. VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

[System. Management. Automation. VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

[System. Management. Automation. VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)

[System. Management. Automation. VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)

[Declaração de cmdlet](./cmdlet-class-declaration.md)

[Guia do programador do Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md)

[SDK do shell do Windows PowerShell](../windows-powershell-reference.md)
