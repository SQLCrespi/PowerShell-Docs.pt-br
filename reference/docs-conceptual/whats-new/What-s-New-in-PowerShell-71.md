---
title: Novidades no PowerShell 7.1
description: Novos recursos e alterações lançados no PowerShell 7.1
ms.date: 11/11/2020
ms.openlocfilehash: 5596d3ca69f5d8ea47f01ff0915e6fa33c1c463f
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625713"
---
# <a name="whats-new-in-powershell-71"></a>Novidades no PowerShell 7.1

O PowerShell 7.1 é uma edição do PowerShell que é open-source, multiplataforma (Windows, macOS e Linux) e criada para ambientes heterogêneos e nuvem híbrida.

Aproveitando a base estabelecida no PowerShell 7.0, nossos esforços se concentram nos problemas da comunidade e incluem vários aprimoramentos e correções. Estamos comprometidos em garantir que o PowerShell continue sendo uma plataforma estável e de alto desempenho.

O PowerShell 7.1 também inclui PSReadLine 2.1.0. Essa versão inclui o Predictive IntelliSense. Para obter mais informações sobre o recurso Predictive IntelliSense, confira o[anúncio](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) no blog do PowerShell.

## <a name="where-can-i-install-powershell"></a>Onde posso instalar o PowerShell?

<!-- TODO: Update list of OS below - make sure this is consistent across all docs -->

Atualmente, o PowerShell 7.1 dá suporte aos seguintes sistemas operacionais em x64, incluindo:

- Windows 8.1/10 (incluindo ARM64)
- Windows Server 2012 R2, 2016, 2019 e SAC (Canal Semestral)
- Ubuntu 16.04/18.04/20.04 (incluindo ARM64)
- Ubuntu 19.10 (via pacote Snap)
- Debian 9/10
- CentOS e RHEL 7/8
- Fedora 32
- Alpine 3.11+ (incluindo ARM64)
- macOS 10.13 ou posterior

Também temos suporte da comunidade para:

- Arch Linux
- Raspbian Linux
- Kali Linux

Para obter informações mais atualizadas sobre os sistemas operacionais com suporte e o ciclo de vida do suporte, confira o [Ciclo de vida do suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle)

O PowerShell 7.1 foi publicado na Microsoft Store. Você pode encontrar a versão do PowerShell no site da [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) ou no aplicativo da Store no Windows.

Benefícios do pacote da Microsoft Store:

- Atualizações automáticas integradas diretamente no Windows 10
- Integra-se a outros mecanismos de distribuição de software, como Intune e SCCM

> [!NOTE]
> Nenhuma definição de configuração no nível do sistema armazenada em `$PSHOME` pode ser modificada. Isso inclui a configuração do WSMAN. Isso impede que as sessões remotas se conectem a instalações baseadas na Store do PowerShell. Há suporte para configurações no nível do usuário e para comunicação remota SSH.

Confira as instruções de instalação do seu sistema operacional preferido:

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

Além disso, o PowerShell 7.1 dá suporte às variantes ARM32 e ARM64 do Debian, Ubuntu e ARM64 Alpine Linux.

Embora não tenha suporte oficial, a comunidade também forneceu pacotes para o [Arch](https://aur.archlinux.org/packages/powershell/) e o Kali Linux.

> [!NOTE]
> Atualmente, o Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine e Arm não dão suporte à comunicação remota do WinRM. Para obter detalhes sobre como configurar a comunicação remota baseada em SSH, confira [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="running-powershell-71"></a>Executar o PowerShell 7.1

O PowerShell 7.1 é instalado em um novo diretório e executado lado a lado com o Windows PowerShell 5.1.
O PowerShell 7.1 é uma atualização in-loco que substitui o PowerShell 6.x. ou PowerShell 7.0.

- O PowerShell 7.1 está instalado no `%programfiles%\PowerShell\7`
- A pasta `%programfiles%\PowerShell\7` é adicionada ao `$env:PATH`

Os pacotes do instalador do PowerShell 7.1 atualizam versões anteriores do PowerShell Core 6.x:

- PowerShell Core 6.x no Windows: `%programfiles%\PowerShell\6` é substituído por `%programfiles%\PowerShell\7`
- Linux: `/opt/microsoft/powershell/6` é substituído por `/opt/microsoft/powershell/7`
- macOS: `/usr/local/microsoft/powershell/6` é substituído por `/usr/local/microsoft/powershell/7`

> [!NOTE]
> No Windows PowerShell, o executável para iniciar o PowerShell é denominado `powershell.exe`. Na versão 6 e posterior, o executável é alterado para dar suporte à execução lado a lado. O novo executável para iniciar o PowerShell 7.1 é `pwsh.exe`. Os builds de versão prévia permanecerão no local como `pwsh-preview` em vez de `pwsh` no diretório 7-preview.

## <a name="breaking-changes-and-improvements"></a>Alterações de falha e melhorias

Para obter as informações mais recentes sobre alterações e melhorias, confira o [CHANGELOG](https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG) no repositório GitHub.

### <a name="breaking-changes"></a>Alterações de quebra

<!-- TODO: Add descriptions for each breaking change - this might need to be a separate article that we link to -->

- Corrigir `$?` para não ser `$false` quando o comando nativo for gravado em `stderr` (nº 13395)
- Renomear `-FromUnixTime` para `-UnixTimeSeconds` no `Get-Date` para permitir a entrada de tempo do Unix (nº 13084) (Obrigado, @aetos382!)
- Fazer `$ErrorActionPreference` não afetar a saída `stderr` de comandos nativos (nº 13361)
- Permitir que o parâmetro nomeado especificado explicitamente substitua o mesmo no nivelamento de tabela de hash (nº 13162)
- Tornar o parâmetro de opção `-Qualifier` não posicional para `Split-Path` (nº 12960) (Obrigado, @yecril71pl!)
- Resolver o diretório de trabalho como caminho literal para `Start-Process` quando ele não é especificado (nº 11946) (Obrigado, @NoMoreFood!)
- Fazer o parâmetro `-OutFile` nos cmdlets da Web funcionar como `-LiteralPath` (nº 11701) (Obrigado, @iSazonov!)
- Corrigir a associação de parâmetro de cadeia de caracteres para literais numéricos `BigInteger` (nº 11634) (Obrigado, @vexx32!)
- No Windows, `Start-Process` cria um ambiente de processo com todas as variáveis de ambiente da sessão atual. Usar `-UseNewEnvironment` cria um ambiente de processo padrão (nº 10830) (Obrigado, @iSazonov!)
- Não encapsular o resultado de retorno para `PSObject` ao converter ScriptBlock para representante (nº 10619)
- Usar conversão de cadeia de caracteres de cultura invariável para operador `-replace` (nº 10954) (Obrigado, @iSazonov!)

### <a name="experimental-features"></a>Recursos experimentais

Para obter mais informações sobre os recursos experimentais, confira [Usar recursos experimentais](../learn/experimental-features.md).

- Remover o recurso `PSNullConditionalOperators` do modo experimental (nº 13529)
- Remover o recurso `PSUnixFileStat` do modo experimental
- Adicionar o parâmetro `-Runspace` a todos os cmdlets `*-PSBreakpoint` (nº 10492) (Obrigado, @KirkMunro!)
- Adicionar `PSNativePSPathResolution` a fim de dar suporte à passagem de `PSPath` para comandos nativos (nº 12386)
- Usar conversão de cadeia de caracteres de cultura invariável para operador `-replace` (nº 10954) (Obrigado, @iSazonov!)
- Adicionar `PSSubsystemPluginModel` para dar suporte a futuros plug-ins do Predictive IntelliSense

### <a name="general-cmdlet-updates-and-fixes"></a>Atualizações e correções gerais do Cmdlet

- Emitir aviso se `ConvertTo-Json` exceder o valor `-Depth` (nº 13692)
- Corrigir o caso em que a mensagem de exceção contém apenas ``"`n"`` no Windows (nº 13684)
- Reconhecer `CONOUT$` e `CONIN$` como nomes de dispositivo reservados (nº 13508) (Obrigado, @davidreis97!)
- Corrigir `ConciseView` para função avançada interativa ao gravar erro (nº 13623)
- Adicionar suporte ao `TLS` 1.3 nos cmdlets da Web (nº 13409) (Obrigado, @iSazonov!)
- Adicionar verificação nula a `args` em `CommandLineParser` (nº 13451) (Obrigado, @iSazonov!)
- Processar pontos de nova análise para aplicativos da Microsoft Store (nº 13481) (Obrigado, @iSazonov!)
- Usar o campo se a propriedade não existir para `ObRoot` ao usar o PowerShell Direct para o contêiner (nº 13375) (Obrigado, @hemisphera!)
- Suprimir avisos obsoletos do `UTF-7` (nº 13484)
- Evitar várias enumerações de uma instância `IEnumerable<Expression>` em `Compiler.cs` (nº 13491)
- Alterar `Add-Type -OutputType` para não dar suporte a `ConsoleApplication` e `WindowsApplication` (nº 13440)
- Criar avisos quando `UTF-7` for especificado como uma codificação (nº 13430)
- Corrigir mensagem de erro do novo link simbólico com destino ausente (nº 13085) (Obrigado, @yecril71pl!)
- Tornar o parâmetro `args` não anulável nas APIs `ConsoleHost` públicas (nº 13429)
- Adicionar descarte ausente para `CancellationTokenSource` (nº 13420) (Obrigado, @Youssef1313!)
- Corrigir `Get-Help` não exibido corretamente se o parâmetro der suporte a curingas (nº 13353) (Obrigado, @ThomasNieto!)
- Atualizar a ajuda `pwsh` para o parâmetro `-InputFormat` (nº 13355) (Obrigado, @sethvs!)
- Declarar licença MIT para arquivos copiados de Roslyn (nº 13305) (Obrigado, @xtqqczze!)
- Melhorar os comportamentos de conversão de `BigInteger` (nº 12629) (Obrigado, @vexx32!)
- Corrigir o comportamento de `Get-Acl -LiteralPath "HKLM:Software\Classes\*"` (nº 13107) (Obrigado, @Shriram0908!)
- Adicionar o método `DefaultVisit` à interface e classe do visitante (nº 13258)
- Corrigir a opção abreviada `-s` (STA) em conflito para `pwsh` (nº 13262) (Obrigado, @iSazonov!)
- Alterar `Read-Host -MaskInput` para usar o caminho `SecureString` existente, mas retornar como texto sem formatação (nº 13256)
- Remover `ComEnumerator` como objetos COM usando `IEnumerator` agora tem suporte no .NET 5.0 (nº 13259)
- Usar caminho pessoal temporário na inicialização do Runspace quando a variável de ambiente "HOME" não estiver definida (nº 13239)
- Corrigir `Invoke-Command` para detectar uma chamada recursiva da mesma entrada do histórico (nº 13197)
- Alterar o prefixo `-in` do comutador `-inputformat` do executável `pwsh` para `-inp` a fim de corrigir o conflito com `-interactive` (nº 13205) (Obrigado, @iSazonov!)
- Manipular o caminho do sistema de arquivos WSL ao analisar a zona de segurança de um arquivo (nº 13120)
- Tornar outros comutadores obrigatórios no `Split-Path` (nº 13150) (Obrigado, @kvprasoon!)
- Novo ícone do Fluent Design para o PowerShell 7 (nº 13100) (Obrigado, @sarthakmalik!)
- Corrigir `Move-Item` para dar suporte a movimentações entre montagens no Unix (nº 13044)
- Corrigir `NullReferenceException` no `CommandSearcher.GetNextCmdlet` (nº 12659) (Obrigado, @powercode!)
- Impedir `NullReferenceException` em cmdlets do computador Unix com ganchos de teste ativos (nº 12651) (Obrigado, @vexx32!)
- Corrigir problema em `Select-Object` em que membros de `Hashtable` (por exemplo, `Keys`) não podem ser usados com `-Property` ou `-ExpandProperty` (nº 11097) (Obrigado, @vexx32!)
- Corrigir a opção abreviada conflitante `-w` para pwsh (nº 12945)
- Renomear o arquivo de recurso de `CimCmdlet` (nº 12955) (Obrigado, @iSazonov!)
- Remover o uso de `Test-Path` em `ConciseView` (nº 12778)
- Sinalizar a cláusula de condição da instrução de opção `default` como palavra-chave (nº 10487) (Obrigado, @msftrncs!)
- Adicionar o parâmetro `SchemaFile` ao cmdlet `Test-Json` (nº 11934) (Obrigado, @beatcracker!)
- Retornar parâmetros do provedor de Certificados (nº 10622) (Obrigado, @iSazonov!)
- Corrigir `New-Item` para criar um link simbólico para o destino de caminho relativo (nº 12797) (Obrigado, @iSazonov!)
- Adicionar a propriedade `CommandLine` ao Processo (nº 12288) (Obrigado, @iSazonov!)
- Adicionar o parâmetro `-MaskInput` a `Read-Host` (nº 10908) (Obrigado, @davinci26!)
- Alterar `CimCmdlets` para usar `AliasAttribute` (nº 12617) (Obrigado, @thlac!)
- Corrigir o índice incorreto na cadeia de caracteres de formato em ParameterBinderBase (nº 12630) (Obrigado, @powercode!)
- Copiar a propriedade `CommandInfo` em `Command.Clone()` (nº 12301) (Obrigado, @TylerLeonhardt!)
- Aplicar `-IncludeEqual` em `Compare-Object` quando `-ExcludeDifferent` for especificado (nº 12317) (Obrigado, @davidseibel!)
- Alterar `Get-FileHash` para fechar identificadores de arquivo antes de gravar a saída (nº 12474) (Obrigado, @HumanEquivalentUnit!)
- Corrigir mensagem de exceção inconsistente no operador `-replace` (nº 12388) (Obrigado, @jackdcasey!)
- Corrigir o carregamento do módulo `WinCompat` para tratar módulos do PowerShell 7 com prioridade mais alta (nº 12269)
- Implementar a reutilização do runspace `ForEach-Object -Parallel` (nº 12122)
- Corrigir `Get-Service` para não modificar a coleção ao enumerar (nº 11851) (Obrigado, @NextTurn!)
- Limpar o pipe nomeado do IPC na saída do PowerShell (nº 12187)
- Corrigir o regex de detecção `<img />` em cmdlets da Web (nº 12099) (Obrigado, @vexx32!)
- Permitir literais hexadecimais assinados mais curtos com sufixos de tipo apropriados (nº 11844) (Obrigado, @vexx32!)
- Atualizar o comportamento do parâmetro `UseNewEnvironment` do cmdlet `Start-Process` no Windows (nº 10830) (Obrigado, @iSazonov!)
- Adicionar o comutador `-Shuffle` ao comando `Get-Random` (nº 11093) (Obrigado, @eugenesmlv!)
- Tornar `GetWindowsPowerShellModulePath` compatível com várias instalações do PS (nº 12280)
- Corrigir `Start-Job` para trabalhar em sistemas que não têm o Windows PowerShell registrado como shell padrão (nº 12296)
- Especificar um alias e `-Syntax` para `Get-Command` retorna a sintaxe de comandos com alias (nº 10784) (Obrigado, @ChrisLGardner!)
- Fazer cmdlets CSV funcionar ao usar `-AsNeeded` e houver uma linha incompleta (nº 12281) (Obrigado, @iSazonov!)
- Em invocações locais, não exigir `-PowerShellVersion 5.1` para `Get-FormatData` a fim de ver todos os dados de formato. (nº 11270) (Obrigado, @mklement0!)
- Suporte adicionado para Big Endian `UTF-32` (nº 11947) (Obrigado, @NoMoreFood!)
- Corrigir possível corrida que causa o vazamento do descarte de objetos do PowerShell em `ForEach-Object -Parallel` (nº 12227)
- Adicionar `-FromUnixTime` a `Get-Date` para permitir a entrada de tempo do Unix (nº 12179) (Obrigado, @jackdcasey!)
- Alterar as cores de primeiro plano e da tela de fundo do andamento padrão para fornecer um contraste melhor (nº 11455) (Obrigado, @rkeithhill!)
- Corrigir `foreach -parallel` quando a unidade atual não estiver disponível (nº 12197)
- Não encapsular o resultado de retorno para `PSObject` ao converter `ScriptBlock` para `delegate` (nº 10619)
- Não gravar erros de resolução DNS em `Test-Connection -Quiet` (nº 12204) (Obrigado, @vexx32!)
- Usar threads dedicados para ler os fluxos de erro e saída redirecionados para os processos secundários para trabalhos fora de processo (nº 11713)
- Corrigir um problema de pedido de preferência do operador no código do associador (nº 12075) (Obrigado, @DamirAinullin!)
- Corrigir `NullReferenceException` ao associar parâmetros comuns do tipo `ActionPreference` (nº 12124)
- Corrigir a formatação padrão para `MatchInfo` desserializado (nº 11728) (Obrigado @iSazonov!)
- Usar fluxos assíncronos no `Invoke-RestMethod` (nº 11095) (Obrigado, @iSazonov!)
- Abordar Detecção de UTF-8 em `Get-Content -Tail` (nº 11899) (Obrigado @NoMoreFood!)
- Lidar com `IOException` em `Get-FileHash` (nº 11944) (Obrigado, @iSazonov!)
- Alterar `PowerShell Core` para `PowerShell` em uma cadeia de caracteres de recurso (nº 11928) (Obrigado, @alexandair!)
- Retornar `MainWindowTitle` em `PSHostProcessInfo` (nº 11885) (Obrigado, @iSazonov!)
- Atualizações secundárias diversas para a compatibilidade do Windows (nº 11980)
- Corrigir `ConciseView` para dividir `PositionMessage` usando `[Environment]::NewLine` (nº 12010)
- Remover a restrição de salto de rede para sessões interativas (nº 11920)
- Corrigir `NullReferenceException` em `SuspendStoppingPipeline()` e `RestoreStoppingPipeline()` (nº 11870) (Obrigado, @iSazonov!)
- Gerar GUID para `FormatViewDefinition` `InstanceId` se não for fornecido (nº 11896)
- Corrigir `ConciseView` em que a mensagem de erro é maior que a largura da janela e não tem espaço em branco (nº 11880)
- Permitir a troca de chaves remotas `CAPI-compatible` entre plataformas (nº 11185) (Obrigado, @silijon!)
- Corrigir mensagem de erro (nº 11862) (Obrigado, @NextTurn!)
- Corrigir `ConciseView` para lidar com o caso em que não há um console para obter a largura (nº 11784)
- Atualizar `CmsCommands` para usar a Store em vez do provedor de certificado (nº 11643) (Obrigado, @mikeTWC1984!)
- Permitir que `pwsh` funcione em sistemas Windows em que `mpr.dll` e STA não estão disponíveis (nº 11748)
- Refatorar e implementar `Restart-Computer` para `Un*x` e macOS (nº 11319)
- Adicionar uma implementação de `Stop-Computer` para Linux e macOS (nº 11151)
- Corrigir a função `help` para verificar se `less` está disponível antes de usar (nº 11737)
- Atualizar `PSPath` no `certificate_format_ps1.xml` (nº 11603) (Obrigado, @xtqqczze!)
- Alterar a expressão regular para corresponder aos tipos de relação sem aspas no cabeçalho do Link (nº 11711) (Obrigado, @Marusyk!)
- Corrigir a mensagem de erro durante a exclusão do link simbólico (nº 11331)
- Adicionar um tipo `Selected.*` personalizado a `PSCustomObject` no `Select-Object` apenas uma vez (nº 11548) (Obrigado, @iSazonov!)
- Adicionar `-AsUTC` ao cmdlet `Get-Date` (nº 11611)
- Corrigir o comportamento de agrupamento com valores boolianos em `Format-Hex` (nº 11587) (Obrigado, @vexx32!)
- Fazer `Test-Connection` sempre usar o contexto de sincronização padrão para enviar solicitações de ping (nº 11517)
- Corrigir mensagens de erro de inicialização (nº 11473) (Obrigado, @iSazonov!)
- Ignorar cabeçalhos com valores nulos nos cmdlets da Web (nº 11424) (Obrigado, @iSazonov!)
- Adicionar novamente a verificação para o descarte do trabalho `Invoke-Command`. (nº 11388)
- Reverter "Atualizar formatador para não escrever novas linhas se o conteúdo estiver vazio (nº 11193)" (nº 11342) (Obrigado, @iSazonov!)
- Permitir que `CompleteInput` retorne os resultados de `ArgumentCompleter` quando `AST` ou o Script tiver uma definição de função correspondente (nº 10574) (Obrigado, @M1kep!)
- Atualizar formatador para não escrever novas linhas se o conteúdo estiver vazio (nº 11193)

<!-- TODO: add more general contributor thank you listing -->
