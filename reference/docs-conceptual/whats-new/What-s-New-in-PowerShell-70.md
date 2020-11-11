---
title: Novidades no PowerShell 7.0
description: Novos recursos e alterações lançados no PowerShell 7.0
ms.date: 03/04/2020
ms.openlocfilehash: 3a5a1aaa0bd9dd1e0df7d6f5e6021678ed21dce4
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355265"
---
# <a name="whats-new-in-powershell-70"></a>Novidades no PowerShell 7.0

O PowerShell 7.0 é uma edição do PowerShell que é open-source, multiplataforma (Windows, macOS e Linux) e criada para ambientes heterogêneos e nuvem híbrida.

Nessa versão, apresentamos uma série de novos recursos, incluindo:

- Paralelização de pipeline com `ForEach-Object -Parallel`
- Novos operadores:
  - Operador ternário: `a ? b : c`
  - Operadores de cadeia de pipeline: `||` e `&&`
  - Operadores condicionais nulos: `??` e `??=`
- Uma exibição de erro simplificada e dinâmica e cmdlet `Get-Error` para facilitar a investigação de erros
- Uma camada de compatibilidade que permite aos usuários importar módulos em uma sessão implícita do Windows PowerShell
- Notificações automáticas de nova versão
- A capacidade de invocar recursos de DSC diretamente do PowerShell 7 (experimental)

Para ver uma lista completa de recursos e correções, confira os [logs de alterações](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).

## <a name="where-can-i-install-powershell"></a>Onde posso instalar o PowerShell?

Atualmente, o PowerShell 7 dá suporte aos seguintes sistemas operacionais em x64, incluindo:

- Windows 8.1 e 10
- Windows Server 2012, 2012 R2, 2016 e 2019
- macOS 10.13 ou posterior
- RHEL (Red Hat Enterprise Linux) / CentOS 7
- Fedora 30 ou posterior
- Debian 9
- Ubuntu LTS 16.04 ou posterior
- Alpine Linux 3.8 ou posterior

Além disso, o PowerShell 7.0 oferece suporte às variantes ARM32 e ARM64 do Debian, Ubuntu e ARM64 Alpine Linux.

Confira as instruções de instalação do seu sistema operacional preferencial [Windows](/powershell/scripting/install/installing-powershell-core-on-windows), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos) ou [Linux](/powershell/scripting/install/installing-powershell-core-on-linux).

Embora não tenha suporte oficial, a comunidade também forneceu pacotes para o [Arch](https://aur.archlinux.org/packages/powershell/) e o Kali Linux.

> [!NOTE]
> Atualmente, o Debian 10 e o CentOS 8 não dão suporte à comunicação remota do WinRM. Para obter detalhes sobre como configurar a comunicação remota baseada em SSH, confira [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Para obter informações mais atualizadas sobre os sistemas operacionais com suporte e o ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle).

## <a name="running-powershell-7"></a>Executar o PowerShell 7

O PowerShell 7 é instalado em um diretório separado do Windows PowerShell.
Isso permite a execução do PowerShell 7 lado a lado com o Windows PowerShell 5.1. Para o PowerShell Core 6.x, o PowerShell 7 é uma atualização in-loco que remove o PowerShell Core 6.x.

- O PowerShell 7 é instalado em `%programfiles%\PowerShell\7`
- A pasta `%programfiles%\PowerShell\7` é adicionada ao `$env:PATH`

O pacote do instalador do PowerShell 7 atualiza as versões anteriores do PowerShell Core 6.x:

- PowerShell Core 6.x no Windows: `%programfiles%\PowerShell\6` é substituído por `%programfiles%\PowerShell\7`
- Linux: `/opt/microsoft/powershell/6` é substituído por `/opt/microsoft/powershell/7`
- macOS: `/usr/local/microsoft/powershell/6` é substituído por `/usr/local/microsoft/powershell/7`

> [!NOTE]
> No Windows PowerShell, o executável para iniciar o PowerShell é denominado `powershell.exe`. Da versão 6 em diante, o nome do executável é alterado para dar suporte à execução lado a lado. O novo nome do executável para iniciar o PowerShell 7 é `pwsh.exe`. Os builds de versão prévia permanecem no local como `pwsh-preview` em vez de `pwsh` no diretório da versão prévia da versão 7.

## <a name="improved-backwards-compatibility-with-windows-powershell"></a>Melhor compatibilidade com versões anteriores do Windows PowerShell

O PowerShell 7.0 marca uma mudança para o .NET Core 3.1, permitindo significativamente mais compatibilidade com os módulos existentes do Windows PowerShell. Isso inclui muitos módulos no Windows que exigem funcionalidade da GUI, como `Out-GridView` e `Show-Command`, bem como muitos módulos de gerenciamento de funções fornecidos como parte do Windows.

Para o Windows, um novo parâmetro de opção **UseWindowsPowerShell** é adicionado ao `Import-Module`. Essa opção cria um módulo proxy no PowerShell 7 que usa um processo local do Windows PowerShell para executar implicitamente todos os cmdlets contidos nesse módulo. Saiba mais informações sobre [ Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7&preserve-view=true).

Para obter mais informações sobre quais módulos da Microsoft funcionam com o PowerShell 7.0, confira a [Tabela de Compatibilidade de Módulos](https://aka.ms/PSModuleCompat).

## <a name="parallel-execution-added-to-foreach-object"></a>Execução paralela adicionada ao ForEach-Object

O cmdlet `ForEach-Object`, que itera itens em uma coleção, agora possui paralelismo interno com o novo parâmetro **Parallel**.

Por padrão, os blocos de script paralelos usam o diretório de trabalho atual do chamador que iniciou as tarefas paralelas.

Este exemplo recupera 50.000 entradas de log de 5 logs do sistema em um computador Windows local:

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count

50000
```

O parâmetro **Parallel** especifica o bloco de script que é executado em paralelo para cada nome de log de entrada.

O novo parâmetro **ThrottleLimit** limita o número de blocos de script em execução paralelamente em determinado momento. O padrão é 5.

Use a variável `$_` para representar o objeto de entrada atual no bloco de script. Use o escopo `$using:` para passar referências de variáveis ao bloco de script em execução.

Saiba mais informações sobre [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7&preserve-view=true).

## <a name="ternary-operator"></a>Operador ternário

O PowerShell 7.0 apresenta um operador ternário que se comporta como uma instrução simplificada `if-else`.
O operador ternário do PowerShell é modelado de perto a partir da sintaxe do operador ternário em C#:

```
<condition> ? <if-true> : <if-false>
```

A expressão de condição é sempre avaliada, e seu resultado é convertido em um **booliano** para determinar qual branch é avaliado a seguir:

- A expressão `<if-true>` será executada se a expressão `<condition>` for verdadeira
- A expressão `<if-false>` será executada se a expressão `<condition>` for falsa

Por exemplo:

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

Nesse exemplo, se o caminho existir, **Caminho existente** será exibido. Se o caminho não existir, **Caminho não encontrado** será exibido.

Saiba mais informações sobre [About If](/powershell/module/microsoft.powershell.core/about/about_if).

## <a name="pipeline-chain-operators"></a>Operadores de cadeia de pipeline

O PowerShell 7 implementa os operadores `&&` e `||` para encadear pipelines condicionalmente. Esses operadores são conhecidos no PowerShell como "operadores de cadeia de pipeline" e são semelhantes às listas AND e OR em shells como **Bash** e **Zsh** , além de símbolos de processamento condicional no Shell de Comando do Windows ( **cmd.exe** ).

O operador `&&` executa o pipeline à direita, se o pipeline à esquerda foi bem-sucedido. Por outro lado, o operador `||` executa o pipeline à direita, se o pipeline à esquerda falhou.

> [!NOTE]
> Esses operadores usam as variáveis `$?` e `$LASTEXITCODE` para determinar se um pipeline falhou. Isso permite que você os utilize com comandos nativos, e não apenas com cmdlets ou funções.

Aqui, o primeiro comando é bem-sucedido, e o segundo comando é executado:

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

Aqui, o primeiro comando falha, o segundo não é executado:

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

Aqui, o primeiro comando é bem-sucedido, o segundo comando não é executado:

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

Aqui, o primeiro comando falha, então o segundo comando é executado:

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error 'Bad'
Second
```

Saiba mais informações [Sobre operadores de cadeia de pipeline](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7&preserve-view=true).

## <a name="null-coalescing-assignment-and-conditional-operators"></a>Operadores de avaliação de nulo, de atribuição e condicionais

O PowerShell 7 inclui o operador de avaliação de nulo `??`, atribuição condicional nula `??=` e operadores de acesso de membro condicional nulo `?.` e `?[]`.

### <a name="null-coalescing-operator-"></a>Operador de avaliação de nulo??

O operador de avaliação de nulo `??` retorna o valor do seu operando esquerdo caso não seja nulo.
Caso contrário, ele avalia o operando do lado direito e retorna seu resultado. O operador `??` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.

```powershell
$x = $null
$x ?? 100
100
```

No seguinte exemplo, o operando à direita não será avaliado:

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-assignment-operator-"></a>Operador de atribuição condicional nula ?? =

O operador de atribuição condicional nula `??=` atribuirá o valor de seu operando do lado direito para seu operando esquerdo somente se o operando esquerdo for avaliado como nulo. O operador `??=` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.

```powershell
$x = $null
$x ??= 100
$x
100
```

No seguinte exemplo, o operando à direita não é avaliado:

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-member-access-operators--and--experimental"></a>Operadores de acesso de membro condicional nulo ?. e ?[] (Experimental)

> [!NOTE]
> Este é um recurso experimental chamado **PSNullConditionalOperators**. Para mais informações, confira [Usar recursos experimentais](/powershell/scripting/learn/experimental-features).

Um operador condicional nulo permitirá acesso de membro `?.` ou acesso de elemento `?[]` ao seu operando somente se esse operando for avaliado como não nulo; caso contrário, ele retornará nulo.

> [!NOTE]
> Como o PowerShell permite que `?` faça parte do nome da variável, é necessária uma especificação formal do nome da variável para usar esses operadores. Portanto, é necessário usar `{}` em torno dos nomes de variáveis, como `${a}` ou quando `?` faz parte do nome da variável `${a?}`.

No seguinte exemplo, o valor da propriedade membro **Status** é retornado:

```powershell
$Service = Get-Service -Name 'bits'
${Service}?.status
Stopped
```

O seguinte exemplo retorna nulo sem tentar acessar o nome do membro **Status** :

```powershell
$service = $Null
${Service}?.status
```

Da mesma forma, usando `?[]`, o valor do elemento é retornado:

```powershell
$a = 1..10
${a}?[0]
1
```

Quando o operando é nulo, o elemento não é acessado, e nulo é retornado:

```powershell
$a = $null
${a}?[0]
```

Saiba mais informações [Sobre operadores](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7&preserve-view=true).

## <a name="new-view-conciseview-and-cmdlet-get-error"></a>Novo modo de exibição ConciseView e cmdlet Get-Error

O PowerShell 7.0 aprimora a exibição de mensagens de erro para aumentar a legibilidade dos erros interativos e de script com um novo modo de exibição padrão **ConciseView**. Os modos de exibição são selecionáveis pelo usuário por meio da variável de preferência `$ErrorView`.

Com **ConciseView** , se um erro não for de script ou do analisador, será exibida uma mensagem de erro de linha única:

```powershell
Get-Childitem -Path c:\NotReal
```

```Output
Get-ChildItem: Cannot find path 'C:\NotReal' because it does not exist
```

Se o erro ocorrer durante a execução do script ou for um erro de análise, o PowerShell retornará uma mensagem de erro de várias linhas que contém o erro, um ponteiro e uma mensagem mostrando onde o erro está nessa linha. Se o terminal não oferecer suporte a sequências de escape de cor ANSI (VT100), as cores não serão exibidas.

![Exibição de erro de um script](./media/What-s-New-in-PowerShell-70/myscript-error.png)

O modo de exibição padrão no PowerShell 7 é **ConciseView**. O modo de exibição padrão anterior era **NormalView** , que você pode selecionar ao definir a variável de preferência `$ErrorView`.

```powershell
$ErrorView = 'NormalView' # Sets the error view to NormalView
$ErrorView = 'ConciseView' # Sets the error view to ConciseView
```

> [!NOTE]
> Uma nova propriedade **ErrorAccentColor** é adicionada a `$Host.PrivateData` para dar suporte à alteração da cor de destaque da mensagem de erro.

Quando desejado, um novo cmdlet `Get-Error` fornece um modo de exibição detalhado e completo do erro totalmente qualificado.
Por padrão, o cmdlet exibe os detalhes completos, incluindo as exceções internas, do último erro que ocorreu.

![Exibir de Get-Error](./media/What-s-New-in-PowerShell-70/myscript-geterror.png)

O cmdlet `Get-Error` dá suporte à entrada do pipeline usando a variável interna `$Error`.
`Get-Error` exibe todos os erros direcionados.

```powershell
$Error | Get-Error
```

O cmdlet `Get-Error` dá suporte ao parâmetro **Newest** , permitindo especificar quantos erros da sessão atual você deseja exibir.

```powershell
Get-Error -Newest 3 # Displays the lst three errors that occurred in the session
```

Saiba mais informações sobre [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&preserve-view=true).

## <a name="new-version-notification"></a>Notificação de nova versão

O PowerShell 7 usa notificações de atualização para alertar os usuários sobre a existência de atualizações no PowerShell.
Uma vez por dia, o PowerShell consulta um serviço online para determinar se uma versão mais recente está disponível.

> [!NOTE]
> A verificação de atualização ocorre durante a primeira sessão em determinado período de 24 horas. Por motivos de desempenho, a verificação de atualização é iniciada três segundos após o início da sessão. A notificação é mostrada apenas no início das sessões subsequentes.

Por padrão, o PowerShell assina um dos dois canais de notificação diferentes dependendo de sua versão/branch. As versões GA (em disponibilidade geral) com suporte do PowerShell retornam apenas notificações para versões GA atualizadas. As versões RC (Release Candidate) e Versão prévia notificam atualizações para RC, GA e versão prévia.

O comportamento da notificação de atualização pode ser alterado usando a variável de ambiente `$Env:POWERSHELL_UPDATECHECK`. Os seguintes valores têm suporte:

- **Padrão** é o mesmo que não definir `$Env:POWERSHELL_UPDATECHECK`
  - As versões GA notificam atualizações de versões GA
  - As versões RC/Versão prévia notificam atualizações de GA e versão prévia
- **Desativar** desativa o recurso de notificação de atualização
- **LTS** notifica apenas sobre atualizações de versões GA de LTS (manutenção em longo prazo)

> [!NOTE]
> A variável de ambiente `$Env:POWERSHELL_UPDATECHECK` não existe até que seja definida pela primeira vez.

Para definir a notificação de versão apenas para versões `LTS`:

```powershell
$Env:POWERSHELL_UPDATECHECK = 'LTS'
```

Para definir a notificação de versão para o comportamento `Default`:

```powershell
$Env:POWERSHELL_UPDATECHECK = 'Default'
```

Saiba mais informações [Sobre notificações de atualização](/powershell/module/microsoft.powershell.core/about/about_update_notifications).

## <a name="new-dsc-resource-support-with-invoke-dscresource-experimental"></a>Novo suporte a recursos DSC com Invoke-DSCResource (experimental)

> [!NOTE]
> Este é um recurso experimental chamado **PSDesiredStateConfiguration.InvokeDscResource**. Para mais informações, confira [Usar recursos experimentais](/powershell/scripting/learn/experimental-features).

O cmdlet `Invoke-DscResource` executa um método de um recurso de DSC (Desired State Configuration) do PowerShell especificado.

Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração. Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows ou o Linux usando recursos de DSC. Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC está em execução com a depuração habilitada.

Esse comando invoca o método **Set** de um recurso chamado **WindowsProcess** e fornece propriedades obrigatórias de **Caminho** e **Argumentos** para iniciar o processo especificado do Windows.

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

Saiba mais informações sobre [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&preserve-view=true).

## <a name="breaking-changes-and-improvements"></a>Alterações de falha e melhorias

### <a name="breaking-changes"></a>Alterações de quebra

- Dar suporte à notificação de atualização para canais padrão e LTS (nº 11132)
- Atualizar Test-Connection para funcionar mais como a do Windows PowerShell (nº 10697) (Obrigado, @vexx32!)
- Preservar $? para ParenExpression, SubExpression e ArrayExpression (nº 11040)
- Definir o diretório de trabalho para o diretório atual em Start-Job (nº 10920) (Obrigado, @iSazonov!)
- Fazer $PSCulture refletir consistentemente as alterações de cultura na sessão (nº 10138) (Obrigado, @iSazonov!)

### <a name="engine-updates-and-fixes"></a>Atualizações e correções do mecanismo

- Melhorias nas APIs de ponto de interrupção para cenários remotos (nº 11312)
- Corrigir vazamento de definição de classe do PowerShell em outro Runspace (nº 11273)
- Corrigir uma regressão na formatação causada pelo primitivo FirstOrDefault adicionado em 7.0.0-Preview1 (nº 11258)
- Módulos adicionais da Microsoft para acompanhar na Telemetria PS7 (nº 10751)
- Tornar os recursos aprovados não experimentais (nº 11303)
- Atualizar ConciseView para usar TargetObject se aplicável (nº 11075)
- Corrigir NullReferenceException em métodos públicos CompletionCompleters (nº 11274)
- Corrigir verificação do estado do thread apartment em plataformas não Windows (nº 11301)
- Atualizar a configuração PSModulePath para concatenar as variáveis de ambiente de processo e computador (nº 11276)
- Elevar o .NET Core para 3.1.0 (nº 11260)
- Corrigir a detecção de $PSHOME na frente de $env:PATH (nº 11141)
- Permitir que pwsh herde $env:P SModulePath e habilite powerShell.exe para ser iniciado corretamente (nº 11057)
- Mover para a versão prévia 1 do .NET Core 3.1 (nº 10798)
- Refatorar verificações de marcas de nova análise no provedor do sistema de arquivos (nº 10431) (Obrigado, @iSazonov!)
- Substituir CR e nova linha por um caractere 0x23CE no registro em log de scripts (nº 10616)
- Corrigir um vazamento de recurso ao cancelar o registro do manipulador de eventos de AppDomain.CurrentDomain.ProcessExit (nº 10626)
- Adicionar suporte a ActionPreference.Break para entrar no depurador quando forem geradas mensagens de depuração, erro, informações, progresso, detalhadas ou de aviso (nº 8205) (Obrigado, @KirkMunro!)
- Habilitar os suplementos iniciais do painel de controle no PowerShell Core sem especificar a extensão .CPL. (nº 9828)
- Suporte a números negativos no operador -split (#8960) (obrigado, @ece-jacob-scott!)

### <a name="general-cmdlet-updates-and-fixes"></a>Atualizações e correções gerais do Cmdlet

- Correção do problema no Raspbian para definir a data das alterações de arquivo no recurso experimental do UnixStat (nº 11313)
- Adicionar -AsPlainText a ConvertFrom-SecureString (nº 11142)
- Adicionada verificação de versão do WindowsPS para WinCompat (nº 11148)
- Corrigir relatório de erros em alguns cenários do WinCompat (nº 11259)
- Adicionar resolvedor binário nativo (nº 11032) (Obrigado, @iSazonov!)
- Atualizar o cálculo da largura de caractere para respeitar caracteres CJK corretamente (nº 11262)
- Adicionar arquivo de desbloqueio para macOS (nº 11137)
- Corrigir regressão no Get-PSCallStack (nº 11210) (Obrigado, @iSazonov!)
- Remover o carregamento automático do módulo ScheduledJob ao usar cmdlets Job (nº 11194)
- Adicionar OutputType ao cmdlet Get-Error e preservar os nomes de tipos originais (nº 10856)
- Corrigir a referência nula na propriedade SupportsVirtualTerminal (nº 11105)
- Adicionar verificação de limite em Get-WinEvent (nº 10648) (Obrigado, @iSazonov!)
- Corrigir o runtime do comando para que StopUpstreamCommandsException não seja preenchido em ErrorVariable (nº 10840)
- Definir a codificação de saída como [Console]::OutputEncoding para comandos nativos (nº 10824)
- Suporte a blocos de código de várias linhas nos exemplos (nº 10776) (Obrigado, @Greg-Smulko!)
- Adicionar o parâmetro Culture ao cmdlet Select-String (nº 10943) (Obrigado, @iSazonov!)
- Corrigir o caminho do diretório de trabalho Start-Job com barra invertida (nº 11041)
- ConvertFrom-Json: Desencapsular coleções por padrão (nº 10861) (Obrigado, @danstur!)
- Usar Hashtable que diferencia maiúsculas de minúsculas para o cmdlet Group-Object com opções -CaseSensitive e -AsHashTable (nº 11030) (Obrigado, @vexx32!)
- Tratar exceção se a enumeração de arquivos falhar ao recompilar o caminho para ter a capitalização correta (nº 11014)
- Corrigir ConciseView para mostrar Activity em vez de myCommand (nº 11007)
- Permitir que cmdlets da Web ignorem status de erro HTTP (nº 10466) (Obrigado, @vdamewood!)
- Corrigir o direcionamento de mais de um CommandInfo para Get-Command (nº 10929)
- Adicionar novamente o cmdlet Get-Counter para Windows (nº 10933)
- Fazer ConvertTo-JSON tratar [AutomationNull]::Value e [NullString]::Value como $null (nº 10957)
- Remover os colchetes do endereço ipv6 para a comunicação remota SSH (nº 10968)
- Corrigir a falha se o comando enviado ao pwsh for apenas espaço em branco (nº 10977)
- Adicionar Get-Clipboard e Set-Clipboard de plataforma cruzada (nº 10340)
- Corrigir a configuração do caminho original do objeto do sistema de arquivos para não ter barra final (nº 10959)
- Suporte a $null para ConvertTo-Json (nº 10947)
- Adicionar novamente o comando Out-Printer no Windows (nº 10906)
- Corrigir Start-Job-WorkingDirectory com espaço em branco (nº 10951)
- Retornar o valor padrão ao obter nulo para uma configuração em PSConfiguration.cs (nº 10963) (Obrigado, @iSazonov!)
- Manipular a exceção de E/S como não finalizável (nº 10950)
- Adicionar o assembly GraphicalHost para habilitar Out-GridView, Show-Command e Get-Help -ShowWindow (nº 10899)
- Colocar ComputerName via pipeline em Get-HotFix (nº 10852) (Obrigado, @kvprasoon!)
- Corrigir o preenchimento da guia para parâmetros para que ele mostre parâmetros comuns conforme disponíveis (nº 10850)
- Corrigir GetCorrectCasedPath() para primeiro verificar se alguma entrada de arquivo do sistema é retornada antes de chamar First() (nº 10930)
- Definir o diretório de trabalho para o diretório atual em Start-Job (nº 10920) (Obrigado, @iSazonov!)
- Alterar TabExpansion2 para não exigir -CursorColumn e tratar como $InputScript.Length (nº 10849)
- Manipular caso em que o host não pode retornar linhas ou colunas de tela (nº 10938)
- Corrigir o uso de cores de destaque para hosts que não dão suporte a elas (nº 10937)
- Adicionar novamente o comando Update-List (nº 10922)
- Atualizar FWLink Id para Clear-RecycleBin (nº 10925)
- Durante o preenchimento da guia, ignorar arquivo se não for possível ler atributos de arquivo (nº 10910)
- Adicionar novamente Clear-RecycleBin para Windows (nº 10909)
- Adicionar `$env:__SuppressAnsiEscapeSequences` para controlar se a sequência de escape VT deve ser adicionada na saída (nº 10814)
- Adicionar parâmetro -NoEmphasize para colorir a saída de Select-String (nº 8963) (Obrigado, @derek-xia!)
- Adicionar novamente o cmdlet Get-HotFix (nº 10740)
- Tornar Add-Type utilizável em aplicativos que hospedam o PowerShell (nº 10587)
- Usar uma ordem de avaliação mais efetiva em LanguagePrimitives.IsNullLike () (nº 10781) (Obrigado, @vexx32!)
- Melhorar o tratamento de entrada direcionada de coleção mista e fluxos de entrada direcionados de entradas em Format-Hex (nº 8674) (Obrigado, @vexx32!)
- Usar a conversão de tipo nas hashtables SSHConnection quando o valor não corresponder ao tipo esperado (nº 10720) (Obrigado, @SeeminglyScience!)
- Corrigir o comportamento de Get-Content-ReadCount 0 quando -TotalCount for definido (nº 10749) (Obrigado, @eugenesmlv!)
- Reescrever mensagem de erro de acesso negado em Get-WinEvent (nº 10639) (Obrigado, @iSazonov!)
- Ativar preenchimento de guia para atribuição de variável com enumeração ou tipo restrito (nº 10646)
- Remover a propriedade de comunicação remota do SourceLength não utilizada que causa problemas de formatação (nº 10765)
- Adicionar parâmetro -Delimiter a ConvertFrom-StringData (nº 10665) (Obrigado, @steviecoaster!)
- Adicionar parâmetro posicional para ScriptBlock ao usar Invoke-Command com SSH (nº 10721) (Obrigado, @machgo!)
- Mostrar informações de contexto de linha se houver várias linhas, mas nenhum nome de script para ConciseView (nº 10746)
- Adicionar suporte aos caminhos \\wsl$\ para o provedor do sistema de arquivos (nº 10674)
- Adicionar o texto do token ausente a TokenKind.Question Mark no analisador (nº 10706)
- Definir o diretório de trabalho atual de cada script ForEach-Object-Parallel em execução no mesmo local que o script de chamada. (nº 10672)
- Substituir api-ms-win-core-file-l1-2-2.dll por Kernel32.dll em APIs FindFirst Stream e FindNextStreamW (nº 10680) (Obrigado, @iSazonov!)
- Ajustar o script de formatação de ajuda para ser mais tolerante ao StrictMode (nº 10563)
- Adicionar parâmetro -SecurityDescriptorSDDL a New-Service (nº 10483) (Obrigado, @kvprasoon!)
- Remover saída informativa, consolidar o uso de ping em Test-Connection (nº 10478) (Obrigado, @vexx32!)
- Ler pontos de nova análise especiais sem acessá-los (nº 10662) (Obrigado, @iSazonov!)
- Direcionar saída Clear-Host para terminal (nº 10681) (Obrigado, @iSazonov!)
- Adicionar nova linha de volta para agrupar com Format-Table e -Property (nº 10653)
- Remover [ValidateNotNullOrEmpty] de -InputObject em Get-Random para permitir cadeia de caracteres vazia (nº 10644)
- Fazer com que o algoritmo de distância da string do sistema de sugestões não diferencie maiúsculas de minúsculas (nº 10549) (Obrigado, @iSazonov!)
- Corrigir exceção de referência nula no processamento de entrada de ForEach-Object -Parallel (nº 10577)
- Adicionar definições de política de grupo do PowerShell Core (nº 10468)
- Atualizar o host do console para dar suporte às sequências de controle XTPUSHSGR/XTPOPSGR VT usadas em cenários de composição. (nº 10208)
- Adicionar o parâmetro WorkingDirectory a Start-Job (nº 10324) (Obrigado, @davinci26!)
- Remover o manipulador de eventos que estava fazendo com que as alterações no ponto de interrupção fossem replicadas erroneamente no depurador de runtime do host (nº 10503) (Obrigado, @KirkMunro!)
- Substituir api-ms-win-core-job-12-1-0.dll por Kernell32.dll na API Microsoft.PowerShell.Commands.NativeMethods P/Invoke (nº 10417) (Obrigado, @iSazonov!)
- Corrigir a saída errada para New-Service em atribuição de variável e -OutVariable (nº 10444) (Obrigado, @kvprasoon!)
- Corrigir problemas de ferramenta global em torno do código de saída, parâmetros de linha de comando e caminho com espaços (nº 10461)
- Corrigir recursão no OneDrive -change FindFirstFileEx() para usar o tipo SafeFindHandle (nº 10405)
- Ignorar o PSReadLine de carregamento automático no Windows se o leitor de tela NVDA estiver ativo (nº 10385)
- Elevar as versões de módulos feitos com PowerShell para 7.0.0.0 (nº 10356)
- Adicionar um erro no Add-Type se já existir um tipo com o mesmo nome (nº 9609) (Obrigado, @iSazonov!)

### <a name="performance"></a>Desempenho

- Evitar o uso de fechamento em Parser.SaveError (nº 11006)
- Melhorar o cache ao criar novas instâncias de Regex (nº 10657) (Obrigado, @iSazonov!)
- Melhorar o processamento dos dados de tipo interno do PowerShell de types.ps1xml, typesV3.ps1xml e GetEvent.types.ps1xml (nº 10898)
- Atualizar o PSConfiguration.ReadValueFromFile para torná-lo mais rápido e mais eficiente no uso de memória (nº 10839)
- Adicionar pequenas melhorias de desempenho para a inicialização do runspace (nº 10569) (Obrigado, @iSazonov!)
- Tornar ForEach-Object mais rápido em seus cenários mais usados (nº 10454) e corrigir o problema de desempenho de ForEach-Object-Parallel com muitos runspaces (nº 10455)

### <a name="code-cleanup"></a>Limpeza de código

- Alterar o comentário e o texto do elemento para atender aos padrões da Microsoft (nº 11304)
- Limpar problemas de estilo no Compiler.cs (nº 10368) (Obrigado, @iSazonov!)
- Remover o conversor de tipo não utilizado para CommaDelimitedStringCollection (nº 11000) (Obrigado, @iSazonov!)
- Limpar o estilo em InitialSessionState.cs (nº 10865) (Obrigado, @iSazonov!)
- Limpeza de código para classe PSSession (nº 11001)
- Remover o recurso "executar Update-Help de Get-Help quando Get-Help for executado pela primera vez", que não funciona (nº 10974)
- Corrigir problemas de estilo (nº 10998) (Obrigado, @iSazonov!)
- Limpeza: usar o alias de tipo interno (nº 10882) (Obrigado, @iSazonov!)
- Remover a chave de configuração não utilizada ConsolePrompting e evitar a criação desnecessária de cadeia de caracteres ao consultar a configuração ExecutionPolicy (nº 10985)
- Desabilitar a verificação de notificação de atualização para builds diários (nº 10903) (Obrigado, @bergmeister!)
- Restabelecer API de depuração perdida em nº 10338 (nº 10808)
- Remover a referência de WorkflowJobSourceAdapter que não é mais usada (nº 10326) (Obrigado, @KirkMunro!)
- Limpar interfaces COM no código de lista de atalhos corrigindo atributos PreserveSig (nº 9899) (Obrigado, @weltkante!)
- Adicionar um comentário que descreve por que -ia não é o alias para o parâmetro comum -Informationaction (nº 10703) (Obrigado, @KirkMunro!)
- Renomear InvokeCommandCmdlet.cs para InvokeExpressionCommand.cs (nº 10659) (Obrigado, @kilasuit!)
- Adicionar limpezas de código secundárias relacionadas às notificações de atualização (nº 10698)
- Remover a lógica de fluxo de trabalho preterida dos scripts de configuração de comunicação remota (nº 10320) (Obrigado, @KirkMunro!)
- Atualizar o formato de ajuda para usar maiúsculas e minúsculas corretamente (nº 10678) (Obrigado, @tnieto88!)
- Limpar problemas de estilo de CodeFactor provenientes de commits no último mês (nº 10591) (Obrigado, @iSazonov!)
- Corrigir erro de digitação na descrição do recurso experimental PSTernaryOperator (nº 10586) (Obrigado, @bergmeister!)
- Converter o valor de enumeração ActionPreference.Suspend em um estado reservado sem suporte e remover a restrição do uso de ActionPreference.Ignore nas variáveis de preferência (nº 10317) (Obrigado, @KirkMunro!)
- Substituir ArrayList por List\<T> para obter um código mais legível e confiável sem alterar a funcionalidade (nº 10333) (Obrigado, @iSazonov!)
- Fazer correções de estilo de código em TestConnectionCommand (nº 10439) (Obrigado, @vexx32!)
- Limpar AutomationEngine e remover a chamada de método extra SetSessionStateDrive (nº 10416) (Obrigado, @iSazonov!)
- Renomear ParameterSetName padrão de volta para Delimiter em ConvertTo-Csv e ConvertFrom-Csv (nº 10425)

### <a name="tools"></a>Ferramentas

- Adicionar a configuração padrão à propriedade SDKToUse para que ela seja criada no VS (nº 11085)
- Install-Powershell.ps1: Adicionar parâmetro para usar a instalação do MSI (nº 10921) (Obrigado, @MJECloud!)
- Adicionar exemplos básicos para install-powershell.ps1 (nº 10914) (Obrigado, @kilasuit!)
- Fazer Install-PowerShellRemoting. ps1 manipular uma cadeia de caracteres vazia no parâmetro PowerShellHome (nº 10526) (Obrigado, @Orca88!)
- Alternar de /etc/lsb-release para /etc/os-release em install-powershell.sh (nº 10773) (Obrigado, @Himura2la!)
- Verificar pwsh. exe e pwsh na versão diária no Windows (nº 10738) (Obrigado, @centreboard!)
- Remover toque desnecessário em installpsh-osx.sh (nº 10752)
- Atualize install-powershell.ps1 para verificar build diário já instalado (nº 10489)

### <a name="tests"></a>Testes

- Tornar o teste de DSC não confiável pendente (nº 11131)
- Corrigir o teste de stringdata para validar corretamente as chaves das hashtables (nº 10810)
- Descarregar módulos de teste (nº 11061) (Obrigado, @iSazonov!)
- Aumentar o tempo entre novas tentativas de teste de URL (nº 11015)
- Atualizar testes para descrever as ações de teste com precisão. (nº 10928) (Obrigado, @romero126!)
- Pular temporariamente o teste instável TestAppDomainProcessExitEvenHandlerNotLeaking (nº 10827)
- Tornar estável o teste de vazamento do manipulador de eventos (nº 10790)
- Sincronizar o uso de maiúsculas no CI YAML (nº 10767) (Obrigado, @RDIL!)
- Adicionar teste para a correção de vazamento do manipulador de eventos (nº 10768)
- Adicionar teste Get-ChildItem (nº 10507) (Obrigado, @iSazonov!)
- Substituir linguagem ambígua nos testes de opção para parâmetro para fins de precisão (nº 10666) (Obrigado, @romero126!)
- Adicionar verificação experimental a testes ForEach-Object -Parallel (nº 10354) (Obrigado, @KirkMunro!)
- Atualizar testes para a validação Alpine (nº 10428)

### <a name="build-and-package-improvements"></a>Melhorias de build e pacote

- Corrigir assinatura de pacote Nuget para build de Pacote Coordenado (nº 11316)
- Atualizar dependências da Galeria do PowerShell e NuGet (nº 11323)
- Elevar Microsoft.ApplicationInsights de 2.11.0 para 2.12.0 (nº 11305)
- Elevar Microsoft.CodeAnalysis.CSharp de 3.3.1 para 3.4.0 (nº 11265)
- Atualizar pacotes para Debian 10 e 11 (nº 11236)
- Habilitar apenas os recursos experimentais anteriores à versão RC (nº 11162)
- Atualizar a versão mínima do macOS (nº 11163)
- Elevar NJsonSchema de 10.0.27 para 10.0.28 (nº 11170)
- Atualizar links em README.md e metadata.json para Preview.5 (nº 10854)
- Selecionar os arquivos para testes de conformidade que são de propriedade do PowerShell (nº 10837)
- Permitir que o pacote win7x86 msix seja compilado. (interno 10515)
- Permitir que versões semânticas sejam passadas para a função NormalizeVersion (nº 11087)
- Elevar a estrutura do .NET Core para 3.1-preview.3 (nº 11079)
- Elevar PSReadLine de 2.0.0-beta5 para 2.0.0-beta6 in /src/Modules (nº 11078)
- Elevar Newparansoft.Json de 12.0.2 para 12.0.3 (nº 11037) (nº 11038)
- Adicionar pacotes Debian 10, 11 e CentOS 8 (nº 11028)
- Carregar arquivo JSON Build-Info com o campo ReleaseDate (nº 10986)
- Elevar estrutura do .NET Core para 3.1-preview.2 (nº 10993)
- Habilitar build do pacote MSIX x86 (nº 10934)
- Atualizar a URL do script de instalação do dotnet SDK em build.psm1 (nº 10927)
- Elevar Markdig.Signed de 0.17.1 para 0.18.0 (nº 10887)
- Elevar ThreadJob de 2.0.1 para 2.0.2 (nº 10886)
- Atualizar o módulo AppX Manifest and Packaging para ficar em conformidade com os requisitos da MS Store (nº 10878)
- Atualizar referência do pacote do PowerShell SDK para preview.5 (interno 10295)
- Atualizar ThirdPartyNotices.txt (nº 10834)
- Elevar Microsoft.PowerShell.Native para 7.0.0-preview.3 (nº 10826)
- Elevar Microsoft.ApplicationInsights de 2.10.0 para 2.11.0 (nº 10608)
- Elevar NJsonSchema de 10.0.24 para 10.0.27 (nº 10756)
- Adicionar suporte a MacPorts ao sistema de build (nº 10736) (Obrigado, @Lucius-Q-User!)
- Elevar PackageManagement de 1.4.4 para 1.4.5 (nº 10728)
- Elevar NJsonSchema de 10.0.23 para 10.0.24 (nº 10635)
- Adicionar variável de ambiente para diferenciar a telemetria de cliente/servidor no MSI (nº 10612)
- Elevar PSDesiredStateConfiguration de 2.0.3 para 2.0.4 (nº 10603)
- Elevar Microsoft.CodeAnalysis.CSharp de 3.2.1 para 3.3.1 (nº 10607)
- Atualizar para .Net Core 3.0 RTM (nº 10604) (Obrigado, @bergmeister!)
- Atualizar o pacote MSIX para que a versão atenda aos requisitos da Windows Store (nº 10588)
- Elevar PowerShellGet de 2.2 para 2.2.1 (nº 10382)
- Elevar PackageManagement de 1.4.3 para 1.4.4 (nº 10383)
- Atualizar README.md e metadata.json para 7.0.0-preview.4 (nº 10011)
- Atualizar .Net Core versão 3.0 da Versão prévia 9 para a RC1 (nº 10552) (Obrigado, @bergmeister!)
- Corrigir a geração da lista ExperimentalFeature (Internal 9996)
- Elevar PSReadLine de 2.0.0-beta4 para 2.0.0-beta5 (nº 10536)
- Corrigir script de build da versão para definir a marca de versão
- Atualizar versão do Microsoft.PowerShell.Native para 7.0.0-preview.2 (nº 10519)
- Atualizar para Netcoreapp 3.0 versão prévia 9 (nº 10484) (Obrigado, @bergmeister!)
- Verificar se o build coordenado diário sabe que é um build diário (nº 10464)
- Atualizar o build do pacote combinado para liberar os builds diários (nº 10449)
- Remover referência de appveyor (nº 10445) (Obrigado, @RDIL!)
- Elevar NJsonSchema de 10.0.22 para 10.0.23 (nº 10421)
- Remover a exclusão da pasta de builds do Linux-x64 porque algumas dependências do Alpine precisam dela (nº 10407)

### <a name="documentation-and-help-content"></a>Documentação e conteúdo da ajuda

- Refatorar logs de alterações em um log por versão (nº 11165)
- Corrigir os documentos de ajuda online do FWLinks para PowerShell 7 (nº 11071)
- Atualizar CONTRIBUTING.md (nº 11096) (Obrigado, @mklement0!)
- Corrigir os links do documento de instalação no README.md (nº 11083)
- Adicionar exemplos ao script install-powershell.ps1 (nº 11024) (Obrigado, @kilasuit!)
- Corrigir a ênfase de Select-String e Import-DscResource em CHANGELOG.md (nº 10890)
- Remover o link obsoleto de powershell-beginners-guide.md (nº 10926)
- Mesclar logs de alterações estáveis e de manutenção (nº 10527)
- Atualizar versão .NET usada em documentos de build (nº 10775) (Obrigado, @Greg-Smulko!)
- Substituir os links do MSDN para docs.microsoft.com em powershell-beginners-guide.md (nº 10778) (Obrigado, @iSazonov!)
- Corrigir link desfeito da visão geral do DSC (nº 10702)
- Atualizar Support_Question.md para vincular ao Stack Overflow como outro recurso da comunidade (nº 10638) (Obrigado, @mklement0!)
- Adicionar arquitetura de processador ao modelo de solicitação de distribuição (nº 10661)
- Adicionar novo livro sobre MoL do PowerShell a documentos de aprendizagem do PowerShell (nº 10602)
- Atualizar README.md e metadados para as versões v6.1.6 e v6.2.3 (nº 10523)
- Corrigir um erro de digitação no arquivo README.md (nº 10465) (Obrigado, @vedhasp!)
- Adicionar uma referência ao módulo PSKoans à documentação de Recursos de aprendizagem (nº 10369) (Obrigado, @vexx32!)
- Atualizar README.md e metadata.json para 7.0.0-preview.3 (nº 10393)
