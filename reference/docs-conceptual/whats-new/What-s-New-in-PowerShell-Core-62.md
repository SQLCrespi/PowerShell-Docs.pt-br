---
title: Novidades no PowerShell Core 6.2
description: Novos recursos e alterações liberados no PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 2f5f5d11ba46d53966093c5e3ed6d0c7d47308d0
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737127"
---
# <a name="whats-new-in-powershell-core-62"></a>Novidades no PowerShell Core 6.2

A versão 6.2 do PowerShell Core concentrou-se nas melhorias de desempenho, correções de bug e aprimoramentos secundários de cmdlet e linguagem que elevam a qualidade. Para ver uma lista completa de melhorias, consulte nossos [logs de alterações](https://github.com/PowerShell/PowerShell/releases) no GitHub.

## <a name="experimental-features"></a>Recursos experimentais

Anteriormente, habilitamos o suporte aos [Recursos experimentais][]. Na versão 6.2, temos quatro recursos experimentais para testar. Forneça seus comentários para que possamos fazer melhorias e decidir se vale a pena promover o recurso para a versão final.

Use `Get-ExperimentalFeature` para obter uma lista de recursos experimentais disponíveis. Você pode habilitar ou desabilitar esses recursos com `Enable-ExperimentalFeature` e `Disable-ExperimentalFeature`.

### <a name="command-not-found-suggestions"></a>Sugestões de comando não encontrado

Esse recurso usa a correspondência difusa para localizar sugestões de comandos ou cmdlets que você possa ter digitado incorretamente.

```powershell
Enable-ExperimentalFeature -Name PSCommandNotFoundSuggestion
```

#### <a name="example"></a>Exemplo

Neste exemplo, o nome do cmdlet grafado incorretamente tem correspondência difusa com várias sugestões, das mais prováveis às menos prováveis.

```powershell
Get-Commnd
```

```Output
Get-Commnd : The term 'Get-Commnd' is not recognized as the name of a cmdlet, function, script file, or operable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-Commnd
+ ~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (Get-Commnd:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CommandNotFoundException


Suggestion [4,General]: The most similar commands are: Get-Command, Get-Content, Get-Job, Get-Module, Get-Event, Get-Host, Get-Member, Get-Item, Set-Content.
```

### <a name="implicit-remoting-batching"></a>Envio em lote para comunicação remota implícita

Ao usar a [comunicação remota implícita](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) em um pipeline, o PowerShell trata cada comando no pipeline de maneira independente. Os objetos são repetidamente serializados e `de-serialized` entre o sistema remoto e cliente durante a execução do pipeline.

Com esse recurso, o PowerShell analisa o pipeline para determinar se o comando é seguro para execução e se existe no sistema de destino. Em caso positivo, o PowerShell executa todo o pipeline remotamente e serializa e `de-serializes` os resultados de volta somente para o cliente.

```powershell
Enable-ExperimentalFeature -Name PSImplicitRemotingBatching
```

Um teste real de `Get-Process | Sort-Object` pelo localhost diminui de 10 s a 15 segundos para 20 ms a 30 **milissegundos**. O recurso só precisa ser habilitado no cliente. Não é preciso fazer qualquer alteração no servidor.

### <a name="temp-drive"></a>Unidade Temp

```powershell
Enable-ExperimentalFeature -Name PSTempDrive
```

Se estiver usando o PowerShell Core em diferentes sistemas operacionais, você descobrirá que a variável de ambiente para encontrar o diretório temporário é diferente no Windows, macOS e Linux! Com esse recurso, você obtém um [PSDrive][] chamado `Temp:` que é mapeado automaticamente para a pasta temporária do sistema operacional que você está usando.

#### <a name="example"></a>Exemplo

```powershell
PS> "Hello World!" > Temp:/hello.txt
PS> Get-Content Temp:/hello.txt
Hello World!
```

Esteja ciente de que os comandos do arquivo nativo (como `ls` no Linux) não reconhecem PSDrives e não verão essa unidade `Temp:`.

### <a name="abbreviation-expansion"></a>Expansão de abreviação

Os cmdlets do PowerShell costumam ter nomes descritivos. Isso resulta em nomes longos que são mais difíceis de digitar. Esse recurso permite que você digite apenas os caracteres maiúsculos do cmdlet e use o preenchimento com Tab para encontrar uma correspondência.

```powershell
Enable-ExperimentalFeature -Name PSUseAbbreviationExpansion
```

#### <a name="example"></a>Exemplo

```powershell
PS> i-arsavsf
```

Se você pressionar Tab e tiver o módulo [Az](https://www.powershellgallery.com/packages/Az) do Azure PowerShell instalado, o cmdlet será preenchido automaticamente desta forma:

```Output
PS> Import-AzRecoveryServicesAsrVaultSettingsFile
```

> [!NOTE]
> Esse recurso deve ser usado de modo interativo. As formas abreviadas dos cmdlets não podem ser executadas.
> Esse recurso não é uma substituição de aliases.

## <a name="breaking-changes"></a>Alterações de quebra

- Correção do comportamento `-NoEnumerate` em `Write-Output` para ser consistente com o Windows PowerShell. (nº 9069)
- Transformação do resultado de `Join-String -InputObject 1,2,3` para ser igual ao resultado de `1,2,3 | Join-String` (nº 8611) (Obrigado @sethvs!)
- Adição de `-Stable` a `Sort-Object` e testes relacionados (nº 7862) (Obrigado @KirkMunro!)
- Aprimoramento do cmdlet `Start-Sleep` para aceitar fração de segundos (nº 8537) (Obrigado @Prototyyppi!)
- Alteração da tabela de hash para usar OrdinalIgnoreCase de modo a ser `case-insensitive` em todas as Culturas (nº 8566)
- Correção de **LiteralPath** em `Import-Csv` para associação à saída `Get-ChildItem` (nº 8277) (Obrigado @iSazonov!)
- Não ignora mais uma coluna sem nome se o delimitador de aspas duplas for usado em `Import-Csv` (nº 7899) (Obrigado @Topping!)
- `Get-ExperimentalFeature` não tem mais a opção `-ListAvailable` (nº 8318)
- O parâmetro de depuração agora define `$DebugPreference` como **Continuar** ao invés de **Consultar** (nº 8195) (Obrigado @KirkMunro!)
- Cumprimento de `-OutputFormat` se especificado no comando não interativo, redirecionado, codificado usado com pwsh (nº 8115)
- Carregamento do assembly do caminho base do módulo antes de tentar carregar do GAC (nº 8073)
- Remoção do til dos pacotes de visualização do Linux (nº 8244)
- Movimentação do processamento de `-WorkingDirectory` antes do processamentos dos perfis (nº 8079)
- Não adicione a variável de ambiente `PATHEXT` no Unix (nº 7697) (Obrigado @iSazonov!)

## <a name="known-issues"></a>Problemas conhecidos

- A comunicação remota em plataformas ARM do Windows IOT apresenta um problema de carregamento de módulos. Consulte (nº 8053)

## <a name="general-updates-and-fixes"></a>Correções e atualizações gerais

- Habilitação do preenchimento automático com Tab sem diferenciação entre maiúsculas e minúsculas para arquivos e pastas em sistemas de arquivos que diferenciam maiúsculas de minúsculas (nº 8128)
- Mudança de PSVersionInfo.PSVersion e PSVersionInfo.PSEdition para estado público (nº 8054) (Obrigado @KirkMunro!)
- Adição de Inferência de Tipos para `$_` / `$PSItem` nos blocos `catch{ }` (nº 8020) (Obrigado @vexx32!)
- Correção da inferência de tipos da invocação de método estático (nº 8018) (Obrigado @SeeminglyScience!)
- Criação de tipos deduzidos para `Select-Object`, `Group-Object`, **PSObject** e **Hashtable** (nº 7231) (Obrigado @powercode!)
- Suporte ao método de chamada com parâmetros de tipo `ByRef-like` (nº 7721)
- Tratamento de caso em que o caminho do módulo do Windows PowerShell já está no PSModulePath do ambiente (nº 7727)
- Habilitação de cmdlets `SecureString` para sistemas diferentes do Windows pelo armazenamento do texto sem formatação (nº 9199)
- Aprimoramento da mensagem de erro em sistemas diferentes do Windows ao importar clixml com securestring (nº 7997)
- Adição do parâmetro ReplyTo a `Send-MailMessage` (nº 8727) (Obrigado @replicaJunction!)
- Adição da mensagem Obsoleto a `Send-MailMessage` (nº 9178)
- Correção de `Restart-Computer` para funcionar no `localhost` quando WinRM não estiver presente (nº 9160)
- Fazer `Start-Job` lançar um erro de encerramento quando o PowerShell estiver sendo hospedado (nº 9128)
- Adição de aceleradores e sufixos do tipo de estilo C# para ushort, uint, ulong e literais curtos (nº 7813) (Obrigado @vexx32!)
- Adição de novos sufixos para literais numéricos; consulte [about_Numeric_Literals][] (nº 7901) (Obrigado @vexx32!)
- Relato correto do nível de impacto quando SupportsShouldProcess não é definido como 'true' (nº 8209) (Obrigado @vexx32!)
- Correção dos problemas do conjunto de caracteres de solicitação nos cmdlets da Web (nº 8742) (Obrigado @markekraus!)
- Correção do problema de esperar `100-continue` com cmdlets da Web (nº 8679) (Obrigado @markekraus!)
- Correção do problema de bloqueio de arquivo com cmdlets da Web (nº 7676) (Obrigado @Claustn!)
- Correção do problema de análise da página de código em `Invoke-RestMethod` (nº 8694) (Obrigado @markekraus!)
- Refatoração de `ConvertTo-Json` para exposição de JsonObject.ConvertToJson como uma API pública (nº 8682)
- Adição de profundidade máxima configurável em `ConvertFrom-Json` com -Depth (nº 8199) (Obrigado @louistio!)
- Adição do parâmetro EscapeHandling no cmdlet `ConvertTo-Json` (nº 7775) (Obrigado @iSazonov!)
- Adição de `-CustomPipeName` a pwsh e `Enter-PSHostProcess` (nº 8889)
- Habilitação da criação de links simbólicos relativos no Windows com `New-Item` (nº 8783)
- Permissão para que usuários do Windows no modo de desenvolvedor criem links simbólicos sem elevação (nº 8534)
- Habilitação de `Write-Information` para aceitar `$null` (nº 8774)
- Correção de `Get-Help` para funções avançadas com conteúdo de ajuda MAML (nº 8353)
- Correção do problema PSTypeName `Get-Help` com -Parameter quando apenas um parâmetro é declarado (nº 8754) (Obrigado @pougetat!)
- Correção do cálculo do token para `Get-Help` executado em ScriptBlock para ajuda de comentário. (nº 8238) (Obrigado @hubuk!)
- Alteração do parâmetro -Parameter do cmdlet `Get-Help` para que ele aceite matrizes de cadeia de caracteres (nº 8454) (Obrigado @sethvs!)
- Resolução de PAGER se o caminho contiver espaços (nº 8571) (Obrigado @pougetat!)
- Adição de prompt ao uso de `less` na função 'help' para orientar o usuário sobre como encerrar (nº 7998)
- Adição de enumeração e tipos de caractere de suporte no cmdlet `Format-Hex` (nº 8191) (Obrigado @iSazonov!)
- Remoção de ShouldProcess de `Format-Hex` (nº 8178)
- Adição dos novos parâmetros Offset e Count a `Format-Hex` e refatoração do cmdlet (nº 7877) (Obrigado @iSazonov!)
- Permissão de 'name' como uma chave de alias para 'label' em `ConvertTo-Html`, permissão para que a entrada 'width' seja um inteiro (nº 8426) (Obrigado @mklement0!)
- Propriedades calculadas com base em scriptblock voltam a funcionar em `ConvertTo-Html` (nº 8427) (Obrigado @mklement0!)
- Adição do cmdlet `Join-String` para criação de texto da entrada do pipeline (nº 7660) (Obrigado @powercode!)
- Correção da lógica do parâmetro FormatString do cmdlet `Join-String` (nº 8449) (Obrigado @sethvs!)
- Alteração de `Clear-Host` para usar `$RAWUI` e liberação para trabalhar por comunicação remota (nº 8609)
- Alteração de `Clear-Host` para a chamada simples de `[console]::clear` e remoção do alias de limpeza do Unix (nº 8603)
- Correção de LiteralPath em `Import-Csv` para associação à saída `Get-ChildItem` (nº 8277) (Obrigado @iSazonov!)
- A função de ajuda não deve usar pager para AliasHelpInfo (nº 8552)
- Adição de `-UseMinimalHeader` a `Start-Transcript` para minimizar um cabeçalho de transcrição (nº 8402) (Obrigado @lukexjeremy!)
- Adição dos cmdlets `Enable-ExperimentalFeature` e `Disable-ExperimentalFeature` (nº 8318)
- Exposição de todos os cmdlets de **PSDiagnostics** se logman.exe estiver disponível (nº 8366)
- Remoção do parâmetro **Persist** de `New-PSDrive` em plataforma `non-Windows` (nº 8291) (Obrigado @lukexjeremy!)
- Adição de suporte para `cd +` (nº 7206) (Obrigado @bergmeister!)
- Habilitação de `Set-Location -LiteralPath` para trabalhar com pastas chamadas - e + (nº 8089)
- `Test-Path` retorna `$false` quando é fornecido um valor de caminho vazio ou `$null` (nº 8080) (Obrigado @vexx32!)
- Permissão para que o parâmetro dinâmico seja retornado mesmo se o caminho não corresponder a qualquer provedor (nº 7957)
- Suporte a `Get-PSHostProcessInfo` e `Enter-PSHostProcess` em plataformas Unix (nº 8232)
- Redução de alocações no cmdlet `Get-Content` (nº 8103) (Obrigado @iSazonov!)
- Habilitação de `Add-Content` para compartilhar acesso de leitura com outras ferramentas durante a gravação de conteúdo (nº 8091)
- `Get/Add-Content` gera erro aprimorado ao visar um contêiner (nº 7823) (Obrigado @kvprasoon!)
- Adição dos parâmetros `-Name`, `-NoUserOverrides` e `-ListAvailable` ao cmdlet `Get-Culture` (nº 7702) (Obrigado @iSazonov!)
- Adição de atributo unificado para preenchimento do parâmetro **Encoding**. (nº 7732) (Obrigado @ThreeFive-O!)
- Permissão de Ids numéricas e nome de páginas de código registradas nos parâmetros **Encoding** (nº 7636) (Obrigado @iSazonov!)
- Correção de `Rename-Item -Path` com o caractere curinga (nº 7398) (Obrigado @kwkam!)
- Ao usar `Start-Transcript` e o arquivo existir, esvazie o arquivo em vez de excluir (nº 8131) (Obrigado @paalbra!)
- Criação explícita de arquivos de software livre `Add-Type` com **FileAccess.Read** e **FileShare.Read** (nº 7915) (Obrigado @IISResetMe!)
- Correção de `Enter-PSSession -ContainerId` para o Windows mais recente (nº 7883)
- Garantia de que a propriedade **NestedModules** seja preenchida por `Test-ModuleManifest` (nº 7859)
- Adição de `%F` a `Get-Date` -UFormat (nº 7630) (Obrigado @britishben!)
- Correção de `Set-Service -Status Stopped` para interrupção de serviços com dependências (nº 5525) (Obrigado @zhenggu!)

<!-- Link references -->
[about_Numeric_Literals]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[Recursos experimentais]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[PSDrive]: /powershell/module/microsoft.powershell.management/new-psdrive
