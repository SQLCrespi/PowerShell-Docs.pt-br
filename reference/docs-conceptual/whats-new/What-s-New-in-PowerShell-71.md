---
title: Novidades no PowerShell 7.1
description: Novos recursos e alterações lançados no PowerShell 7.1
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577200"
---
# <a name="whats-new-in-powershell-71"></a>Novidades no PowerShell 7.1

Em 11 de novembro de 2020, [anunciamos](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) a disponibilidade geral do PowerShell 7.1. Aproveitando a base estabelecida no PowerShell 7.0, nossos esforços se concentram nos problemas da comunidade e incluem vários aprimoramentos e correções. Estamos comprometidos em garantir que o PowerShell continue sendo uma plataforma estável e de alto desempenho.

O PowerShell 7.1 inclui os recursos, as atualizações e as alterações interruptivas a seguir.

- PSReadLine 2.1.0, que inclui o Predictive IntelliSense
- O PowerShell 7.1 foi publicado na Microsoft Store
- Pacotes do instalador atualizados para novas versões do sistema operacional compatíveis com ARM64
- Quatro novos recursos experimentais e dois recursos experimentais promovidos para o básico
- Várias alterações interruptivas para melhorar a usabilidade

Para ver uma lista completa das alterações, confira o [LOG DE MUDANÇAS](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) no repositório do GitHub.

## <a name="psreadline-210"></a>PSReadLine 2.1.0

O PowerShell 7.1 também inclui PSReadLine 2.1.0. Essa versão inclui o Predictive IntelliSense. Para obter mais informações sobre o recurso Predictive IntelliSense, confira o[anúncio](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) no blog do PowerShell.

## <a name="microsoft-store-installer-package"></a>Pacote do instalador da Microsoft Store

O PowerShell 7.1 foi publicado na Microsoft Store. Você pode encontrar a versão do PowerShell no site da [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) ou no aplicativo da Store no Windows.

Benefícios do pacote da Microsoft Store:

- Atualizações automáticas integradas diretamente no Windows 10
- Integra-se a outros mecanismos de distribuição de software, como Intune e SCCM

> [!NOTE]
> Nenhuma definição de configuração no nível do sistema armazenada em `$PSHOME` pode ser modificada. Isso inclui a configuração do WSMAN. Isso impede que as sessões remotas se conectem a instalações baseadas na Store do PowerShell. Há suporte para configurações no nível do usuário e para comunicação remota SSH.

## <a name="other-installers"></a>Outros instaladores

Para obter informações mais atualizadas sobre os sistemas operacionais com suporte e o ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle).

Confira as instruções de instalação do seu sistema operacional preferido:

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

Além disso, o PowerShell 7.1 dá suporte às variantes ARM32 e ARM64 do Debian, Ubuntu e ARM64 Alpine Linux.

Embora não tenha suporte oficial, a comunidade também forneceu pacotes para o [Arch](https://aur.archlinux.org/packages/powershell/) e o Kali Linux.

> [!NOTE]
> Atualmente, o Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine e Arm não dão suporte à comunicação remota do WinRM. Para obter detalhes sobre como configurar a comunicação remota baseada em SSH, confira [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="experimental-features"></a>Recursos experimentais

Para obter mais informações sobre os recursos experimentais, confira [Usar recursos experimentais](../learn/experimental-features.md).

Estes recursos experimentais agora são recursos básicos nesta versão:

- [PSNullConditionalOperators](../learn/experimental-features.md#psnullconditionaloperators)
- [PSUnixFileStat](../learn/experimental-features.md#psunixfilestat)

Estes recursos experimentais foram adicionados a esta versão:

- [Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - O PowerShell 7.1 estende este recurso experimental para adicionar o parâmetro **Runspace** a todos os cmdlets `*-PSBreakpoint`. O parâmetro **Runspace** especifica um objeto **Runspace** para interagir com pontos de interrupção no runspace especificado.

- [PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) – Permite passar caminhos do provedor do PowerShell para comandos nativos incompatíveis com a sintaxe de caminho do PowerShell.

- [PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) – Quando o operando à esquerda em uma instrução do operador `-replace` não for uma cadeia de caracteres, esse operando será convertido em uma cadeia de caracteres. Com o recurso habilitado, as configurações de cultura não são usadas na conversão em cadeia de caracteres.

- [PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) – Estabelece a base para dar suporte a futuros plug-ins do Predictive IntelliSense.

## <a name="breaking-changes-and-improvements"></a>Alterações de falha e melhorias

- Corrigir `$?` para não ser `$false` quando o comando nativo for gravado em `stderr` ([nº 13395](https://github.com/PowerShell/PowerShell/pull/13395))

  É comum que comandos nativos gravem em `stderr` sem a intenção de indicar uma falha.
  Com essa alteração, `$?` será definido como `$false` somente quando o comando nativo também tiver um código de saída diferente de zero. Essa alteração não tem relação com o recurso experimental `PSNotApplyErrorActionToStderr`.

- Fazer `$ErrorActionPreference` não afetar a saída `stderr` de comandos nativos ([nº 13361](https://github.com/PowerShell/PowerShell/pull/13361))

  É comum que comandos nativos gravem em `stderr` sem a intenção de indicar uma falha.
  Com essa alteração, a saída `stderr` ainda será capturada em objetos **ErrorRecord**, mas o runtime não aplicará `$ErrorActionPreference` se o **ErrorRecord** vier de um comando nativo.

- Renomear `-FromUnixTime` para `-UnixTimeSeconds` no `Get-Date` para permitir a entrada de horário do Unix ([nº 13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Obrigado, @aetos382!)

  O parâmetro `-FromUnixTime` foi adicionado durante a 7.1 – versão prévia 2. O parâmetro foi renomeado para corresponder melhor ao tipo de dados. Esse parâmetro usa um valor inteiro que representa em segundos desde 1º de janeiro de 1970, 0:00:00.

  Esse exemplo converte o horário do Unix (representado pelo número de segundos desde 1970-01-01 0:00:00) para DateTime.

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- Permitir que o parâmetro nomeado especificado explicitamente substitua o mesmo no nivelamento de tabela de hash (nº 13162)

  Com essa alteração, os parâmetros nomeados do nivelamento são movidos para o final da lista de parâmetros. Dessa maneira, eles ficam associados após todos os parâmetros nomeados especificados serem explicitamente associados. A associação de parâmetros para funções simples não gera erros quando um parâmetro nomeado especificado não pode ser encontrado. Parâmetros nomeados desconhecidos são associados ao parâmetro `$args` da função simples. Mover o nivelamento para o final da lista de argumentos altera a ordem em que os parâmetros aparecem em `$args`.

  Por exemplo:

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  No comportamento anterior, **MyPath** não está associado a `-Path` porque está em terceiro na lista de argumentos. ## Por isso, é colocado em '$args' junto com `Blah = "World"`.

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  Com essa alteração, os argumentos de `@hash` são movidos para o final da lista de argumentos. **MyPath** se torna o primeiro argumento na lista, portanto, associado a `-Path`.

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- Tornar o parâmetro de opção `-Qualifier` não posicional para `Split-Path` ([nº 12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Obrigado, @yecril71pl!)

- Resolver o diretório de trabalho como caminho literal para `Start-Process` quando ele não é especificado ([nº 11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Obrigado, @NoMoreFood!)

- Fazer o parâmetro `-OutFile` nos cmdlets da Web funcionar como `-LiteralPath` ([nº 11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Obrigado, @iSazonov!)

- Corrigir a associação de parâmetro de cadeia de caracteres para literais numéricos `BigInteger` ([nº 11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Obrigado, @vexx32!)

- No Windows, `Start-Process` cria um ambiente de processo com todas as variáveis de ambiente da sessão atual. Usar `-UseNewEnvironment` cria um ambiente de processo padrão ([nº 10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Obrigado, @iSazonov!)

- Não encapsular o resultado de retorno para `PSObject` ao converter `ScriptBlock` para um delegado ([nº 10619](https://github.com/PowerShell/PowerShell/pull/10619))

  Quando um `ScriptBlock` é convertido em um tipo delegado a ser usado no contexto de C#, encapsulando o resultado em um `PSObject`, gera problemas desnecessários:

  - Quando o valor é convertido no tipo de retorno delegado, o `PSObject` é essencialmente desencapsulado. Portanto, o `PSObject` é desnecessário.
  - Quando o tipo de retorno delegado é `object`, é encapsulado em um `PSObject`, tornando difícil trabalhar com ele em código C#.

  Após essa alteração, o objeto retornado será o objeto subjacente.
