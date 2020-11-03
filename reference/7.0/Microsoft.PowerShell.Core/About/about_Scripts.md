---
description: Descreve como executar e gravar scripts no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: f439e6600df49652d25dbd7337fa3db7cff501bb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195484"
---
# <a name="about-scripts"></a>Sobre scripts

## <a name="short-description"></a>Descrição breve
Descreve como executar e gravar scripts no PowerShell.

## <a name="long-description"></a>Descrição longa

Um script é um arquivo de texto sem formatação que contém um ou mais comandos do PowerShell.
Os scripts do PowerShell têm uma `.ps1` extensão de arquivo.

Executar um script é muito parecido com a execução de um cmdlet. Você digita o caminho e o nome do arquivo do script e usa parâmetros para enviar dados e definir opções. Você pode executar scripts em seu computador ou em uma sessão remota em um computador diferente.

Escrever um script salva um comando para uso posterior e facilita o compartilhamento com outras pessoas. O mais importante é que você executa os comandos simplesmente digitando o caminho do script e o nome do arquivo. Os scripts podem ser tão simples quanto um único comando em um arquivo ou tão extensivo quanto um programa complexo.

Os scripts têm recursos adicionais, como o `#Requires` Comentário especial, o uso de parâmetros, suporte para seções de dados e assinatura digital para segurança.
Você também pode escrever tópicos de ajuda para scripts e para qualquer função no script.

## <a name="how-to-run-a-script"></a>Como executar um script

Antes de executar um script no Windows, você precisa alterar a política de execução padrão do PowerShell. A política de execução não se aplica ao PowerShell em execução em plataformas que não são do Windows.

A política de execução padrão, `Restricted` , impede que todos os scripts sejam executados, incluindo scripts que você escreve no computador local. Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).

A política de execução é salva no registro, portanto, você precisa alterá-la apenas uma vez em cada computador.

Para alterar a política de execução, use o procedimento a seguir.

No prompt de comando, digite:

```powershell
Set-ExecutionPolicy AllSigned
```

ou

```powershell
Set-ExecutionPolicy RemoteSigned
```

A alteração entra em vigor imediatamente.

Para executar um script, digite o nome completo e o caminho completo para o arquivo de script.

Por exemplo, para executar o script de Get-ServiceLog.ps1 no diretório C:\Scripts, digite:

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

Para executar um script no diretório atual, digite o caminho para o diretório atual ou use um ponto para representar o diretório atual, seguido por uma barra invertida de caminho ( `.\` ).

Por exemplo, para executar o script de ServicesLog.ps1 no diretório local, digite:

```powershell
.\Get-ServiceLog.ps1
```

Se o script tiver parâmetros, digite os parâmetros e os valores de parâmetro após o nome de arquivo do script.

Por exemplo, o comando a seguir usa o parâmetro ServiceName do script Get-ServiceLog para solicitar um log da atividade do serviço WinRM.

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

Como um recurso de segurança, o PowerShell não executa scripts quando você clica duas vezes no ícone de script no explorador de arquivos ou quando você digita o nome do script sem um caminho completo, mesmo quando o script está no diretório atual. Para obter mais informações sobre como executar comandos e scripts no PowerShell, consulte [about_Command_Precedence](about_Command_Precedence.md).

### <a name="run-with-powershell"></a>Executar com o PowerShell

A partir do PowerShell 3,0, você pode executar scripts no explorador de arquivos.

Para usar o recurso "executar com o PowerShell":

Execute o explorador de arquivos, clique com o botão direito do mouse no nome de arquivo do script e selecione "executar com o PowerShell".

O recurso "executar com o PowerShell" foi projetado para executar scripts que não têm parâmetros obrigatórios e não retornam a saída para o prompt de comando.

Para obter mais informações, consulte [about_Run_With_PowerShell](about_Run_With_PowerShell.md).

### <a name="running-scripts-on-other-computers"></a>Executando scripts em outros computadores

Para executar um script em um ou mais computadores remotos, use o parâmetro **FilePath** do `Invoke-Command` cmdlet.

Insira o caminho e o nome de arquivo do script como o valor do parâmetro **FilePath** . O script deve residir no computador local ou em um diretório que o computador local possa acessar.

O comando a seguir executa o `Get-ServiceLog.ps1` script nos computadores remotos chamados Server01 e Server02.

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a>Obter ajuda para scripts

O cmdlet Get-Help Obtém os tópicos de ajuda para scripts, bem como para cmdlets e outros tipos de comandos. Para obter o tópico da ajuda para um script, digite `Get-Help` seguido pelo caminho e nome do arquivo do script. Se o caminho do script estiver em sua `Path` variável de ambiente, você poderá omitir o caminho.

Por exemplo, para obter ajuda para o script de ServicesLog.ps1, digite:

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a>Como escrever um script

Um script pode conter qualquer comando válido do PowerShell, incluindo comandos únicos, comandos que usam o pipeline, funções e estruturas de controle, como instruções IF e loops for.

Para gravar um script, abra um novo arquivo em um editor de texto, digite os comandos e salve-os em um arquivo com um nome de arquivo válido com a `.ps1` extensão.

O exemplo a seguir é um script simples que obtém os serviços que estão em execução no sistema atual e os salva em um arquivo de log. O nome do arquivo de log é criado a partir da data atual.

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

Para criar esse script, abra um editor de texto ou um editor de script, digite esses comandos e, em seguida, salve-os em um arquivo chamado `ServiceLog.ps1` .

### <a name="parameters-in-scripts"></a>Parâmetros em scripts

Para definir parâmetros em um script, use uma instrução param. A `Param` instrução deve ser a primeira instrução em um script, exceto comentários e quaisquer `#Require` instruções.

Parâmetros de script funcionam como parâmetros de função. Os valores de parâmetro estão disponíveis para todos os comandos no script. Todos os recursos dos parâmetros de função, incluindo o atributo de parâmetro e seus argumentos nomeados, também são válidos em scripts.

Ao executar o script, os usuários de script digitam os parâmetros após o nome do script.

O exemplo a seguir mostra um `Test-Remote.ps1` script que tem um parâmetro **ComputerName** . Ambas as funções de script podem acessar o valor do parâmetro **ComputerName** .

```powershell
param ($ComputerName = $(throw "ComputerName parameter is required."))

function CanPing {
   $error.clear()
   $tmp = test-connection $computername -erroraction SilentlyContinue

   if (!$?)
       {write-host "Ping failed: $ComputerName."; return $false}
   else
       {write-host "Ping succeeded: $ComputerName"; return $true}
}

function CanRemote {
    $s = new-pssession $computername -erroraction SilentlyContinue

    if ($s -is [System.Management.Automation.Runspaces.PSSession])
        {write-host "Remote test succeeded: $ComputerName."}
    else
        {write-host "Remote test failed: $ComputerName."}
}

if (CanPing $computername) {CanRemote $computername}
```

Para executar esse script, digite o nome do parâmetro após o nome do script. Por exemplo:

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

Para obter mais informações sobre a instrução param e os parâmetros de função, consulte [about_Functions](about_Functions.md) e [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="writing-help-for-scripts"></a>Escrevendo ajuda para scripts

Você pode escrever um tópico da ajuda para um script usando um dos dois métodos a seguir:

- Comment-Based ajuda para scripts

  Crie um tópico da ajuda usando palavras-chave especiais nos comentários. Para criar uma ajuda baseada em comentários para um script, os comentários devem ser colocados no início ou no final do arquivo de script. Para obter mais informações sobre a ajuda baseada em comentários, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).

- XML-Based ajuda para scripts

  Crie um tópico de ajuda baseado em XML, como o tipo que normalmente é criado para cmdlets. A ajuda baseada em XML é necessária se você estiver traduzindo tópicos da ajuda em vários idiomas.

Para associar o script ao tópico de ajuda baseado em XML, use o. Palavra-chave de comentário da ajuda do ExternalHelp. Para obter mais informações sobre a palavra-chave ExternalHelp, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md). Para obter mais informações sobre a ajuda baseada em XML, consulte [como gravar a ajuda do cmdlet](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

### <a name="returning-an-exit-value"></a>Retornando um valor de saída

Por padrão, os scripts não retornam um status de saída quando o script termina. Você deve usar a `exit` instrução para retornar um código de saída de um script. Por padrão, a `exit` instrução retorna `0` . Você pode fornecer um valor numérico para retornar um status de saída diferente. Um código de saída diferente de zero normalmente sinaliza uma falha.

No Windows, qualquer número entre `[int]::MinValue` e `[int]::MaxValue` é permitido.

No UNIX, somente números positivos entre `[byte]::MinValue` (0) e `[byte]::MaxValue` (255) são permitidos. Um número negativo no intervalo de `-1` até `-255` é automaticamente convertido em um número positivo adicionando
256. Por exemplo, `-2` é transformado para `254` .

No PowerShell, a `exit` instrução define o valor da `$LASTEXITCODE` variável. No Shell de comando do Windows (cmd.exe), a instrução Exit define o valor da `%ERRORLEVEL%` variável de ambiente.

Qualquer argumento que não seja numérico ou fora do intervalo específico da plataforma é convertido para o valor de `0` .

## <a name="script-scope-and-dot-sourcing"></a>Escopo do script e ponto de origem

Cada script é executado em seu próprio escopo. As funções, variáveis, aliases e unidades que são criadas no script existem somente no escopo do script. Você não pode acessar esses itens ou seus valores no escopo no qual o script é executado.

Para executar um script em um escopo diferente, você pode especificar um escopo, como global ou local, ou pode criar um ponto de origem do script.

O recurso de fornecimento de ponto permite executar um script no escopo atual em vez de no escopo do script. Quando você executa um script que tem um ponto de origem, os comandos no script são executados como se você os tivesse digitado no prompt de comando. As funções, variáveis, aliases e unidades que o script cria são criadas no escopo no qual você está trabalhando. Depois que o script for executado, você poderá usar os itens criados e acessar seus valores em sua sessão.

Para um ponto de origem de um script, digite um ponto (.) e um espaço antes do caminho do script.

Por exemplo:

```powershell
. C:\scripts\UtilityFunctions.ps1
```

ou

```powershell
. .\UtilityFunctions.ps1
```

Depois `UtilityFunctions.ps1` que o script é executado, as funções e variáveis que o script cria são adicionadas ao escopo atual.

Por exemplo, o `UtilityFunctions.ps1` script cria a `New-Profile` função e a `$ProfileName` variável.

```powershell
#In UtilityFunctions.ps1

function New-Profile
{
  Write-Host "Running New-Profile function"
  $profileName = split-path $profile -leaf

  if (test-path $profile)
    {write-error "Profile $profileName already exists on this computer."}
  else
    {new-item -type file -path $profile -force }
}
```

Se você executar o `UtilityFunctions.ps1` script em seu próprio escopo de script, a `New-Profile` função e a `$ProfileName` variável existirão somente enquanto o script estiver em execução. Quando o script é encerrado, a função e a variável são removidas, conforme mostrado no exemplo a seguir.

```powershell
C:\PS> .\UtilityFunctions.ps1

C:\PS> New-Profile
The term 'new-profile' is not recognized as a cmdlet, function, operable
program, or script file. Verify the term and try again.
At line:1 char:12
+ new-profile <<<<
   + CategoryInfo          : ObjectNotFound: (new-profile:String) [],
   + FullyQualifiedErrorId : CommandNotFoundException

C:\PS> $profileName
C:\PS>
```

Quando você origina o script e o executa, o script cria a `New-Profile` função e a `$ProfileName` variável em sua sessão em seu escopo. Depois que o script for executado, você poderá usar a `New-Profile` função em sua sessão, conforme mostrado no exemplo a seguir.

```powershell
C:\PS> . .\UtilityFunctions.ps1

C:\PS> New-Profile

    Directory: C:\Users\juneb\Documents\WindowsPowerShell

    Mode    LastWriteTime     Length Name
    ----    -------------     ------ ----
    -a---   1/14/2009 3:08 PM      0 Microsoft.PowerShellISE_profile.ps1

C:\PS> $profileName
Microsoft.PowerShellISE_profile.ps1
```

Para obter mais informações sobre escopo, consulte about_Scopes.

## <a name="scripts-in-modules"></a>Scripts em módulos

Um módulo é um conjunto de recursos do PowerShell relacionados que podem ser distribuídos como uma unidade. Você pode usar módulos para organizar seus scripts, funções e outros recursos. Você também pode usar módulos para distribuir seu código para outras pessoas e obter código de fontes confiáveis.

Você pode incluir scripts em seus módulos ou pode criar um módulo de script, que é um módulo que consiste inteiramente ou principalmente em um script e recursos de suporte. Um módulo de script é apenas um script com uma extensão de arquivo. psm1.

Para obter mais informações sobre módulos, consulte [about_Modules](about_Modules.md).

## <a name="other-script-features"></a>Outros recursos de script

O PowerShell tem muitos recursos úteis que você pode usar em scripts.

- `#Requires` -Você pode usar uma `#Requires` instrução para impedir que um script seja executado sem módulos ou snap-ins especificados e uma versão especificada do PowerShell. Para obter mais informações, consulte about_Requires.

- `$PSCommandPath` -Contém o caminho completo e o nome do script que está sendo executado. Esse parâmetro é válido em todos os scripts. Essa variável automática é introduzida no PowerShell 3,0.

- `$PSScriptRoot` -Contém o diretório do qual um script está sendo executado. No PowerShell 2,0, essa variável é válida somente em módulos de script ( `.psm1` ).
  A partir do PowerShell 3,0, ele é válido em todos os scripts.

- `$MyInvocation` -A `$MyInvocation` variável automática contém informações sobre o script atual, incluindo informações sobre como ele foi iniciado ou "invocado". Você pode usar essa variável e suas propriedades para obter informações sobre o script enquanto ele está em execução. Por exemplo, o `$MyInvocation` . A variável myCommand. Path contém o caminho e o nome do arquivo do script. `$MyInvocation`. Line contém o comando que iniciou o script, incluindo todos os parâmetros e valores.

  A partir do PowerShell 3,0, o `$MyInvocation` tem duas novas propriedades que fornecem informações sobre o script que chamou ou invocou o script atual. Os valores dessas propriedades são populados somente quando o chamador ou chamador é um script.

  - **PSCommandPath** contém o caminho completo e o nome do script que chamou ou invocou o script atual.

  - **PSScriptRoot** contém o diretório do script que chamou ou invocou o script atual.

  Ao contrário `$PSCommandPath` das `$PSScriptRoot` variáveis automáticas e que contêm informações sobre o script atual, as propriedades **PSCommandPath** e **PSScriptRoot** da `$MyInvocation` variável contêm informações sobre o script que chamou o script atual.

- Seções de dados-você pode usar a `Data` palavra-chave para separar dados da lógica em scripts. As seções de dados também podem facilitar a localização. Para obter mais informações, consulte [about_Data_Sections](about_Data_Sections.md) e [about_Script_Internationalization](about_Script_Internationalization.md).

- Assinatura de script – você pode adicionar uma assinatura digital a um script. Dependendo da política de execução, você pode usar assinaturas digitais para restringir a execução de scripts que podem incluir comandos não seguros. Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md) e [about_Signing](about_Signing.md).

## <a name="see-also"></a>Confira também

[about_Command_Precedence](about_Command_Precedence.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Execution_Policies](about_Execution_Policies.md)

[about_Functions](about_Functions.md)

[about_Modules](about_Modules.md)

[about_Profiles](about_Profiles.md)

[about_Requires](about_Requires.md)

[about_Run_With_PowerShell](about_Run_With_PowerShell.md)

[about_Scopes](about_Scopes.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Signing](about_Signing.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
