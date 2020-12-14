---
description: Explica como instalar, importar e usar módulos do PowerShell.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 30af4ed84e2332aecd60838f3bcd7741965c2ba1
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564332"
---
# <a name="about-modules"></a>Sobre os módulos

## <a name="short-description"></a>Descrição breve
Explica como instalar, importar e usar módulos do PowerShell.

## <a name="long-description"></a>Descrição longa

Um módulo é um pacote que contém membros do PowerShell, como cmdlets, provedores, funções, fluxos de trabalho, variáveis e aliases.

As pessoas que escrevem comandos podem usar módulos para organizar seus comandos e compartilhá-los com outras pessoas. As pessoas que recebem módulos podem adicionar os comandos nos módulos às suas sessões do PowerShell e usá-los exatamente como os comandos internos.

Este tópico explica como usar os módulos do PowerShell. Para obter informações sobre como escrever módulos do PowerShell, consulte [escrevendo um módulo do PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="what-is-a-module"></a>O que é um módulo?

Um módulo é um pacote que contém membros do PowerShell, como cmdlets, provedores, funções, fluxos de trabalho, variáveis e aliases. Os membros desse pacote podem ser implementados em um script do PowerShell, uma DLL compilada ou uma combinação de ambos. Esses arquivos geralmente são agrupados em um único diretório. Para obter mais informações, consulte [noções básicas sobre um módulo do Windows PowerShell](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) na documentação do SDK do.

## <a name="module-auto-loading"></a>Módulo de carregamento automático

A partir do PowerShell 3,0, o PowerShell importa módulos automaticamente na primeira vez que você executa qualquer comando em um módulo instalado. Agora você pode usar os comandos em um módulo sem qualquer configuração de instalação ou perfil; portanto, não é necessário gerenciar módulos depois de instalá-los em seu computador.

Os comandos em um módulo também são mais fáceis de localizar. O `Get-Command` cmdlet agora Obtém todos os comandos em todos os módulos instalados, mesmo que eles ainda não estejam na sessão. Você pode encontrar um comando e usá-lo sem importar a necessidade de importar o módulo primeiro.

Cada um dos exemplos a seguir faz com que o módulo CimCmdlets, que contém `Get-CimInstance` , seja importado para sua sessão.

- Execute o comando

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- Obter o comando

  ```powershell
  Get-Command Get-CimInstance
  ```

- Obter ajuda para o comando

  ```powershell
  Get-Help Get-CimInstance
  ```

`Get-Command` os comandos que incluem um caractere curinga ( `*` ) são considerados para descoberta, não para uso e não importam nenhum módulo.

Somente os módulos armazenados no local especificado pela variável de ambiente PSModulePath são automaticamente importados. Os módulos em outros locais devem ser importados executando o `Import-Module` cmdlet.

Além disso, os comandos que usam provedores do PowerShell não importam automaticamente um módulo. Por exemplo, se você usar um comando que exija a unidade WSMan:, como o `Get-PSSessionConfiguration` cmdlet, talvez seja necessário executar o `Import-Module` cmdlet para importar o módulo **Microsoft. WSMan. Management** que inclui a `WSMan:` unidade.

Você ainda pode executar o `Import-Module` comando para importar um módulo e usar a `$PSModuleAutoloadingPreference` variável para habilitar, desabilitar e configurar a importação automática de módulos. Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).

## <a name="how-to-use-a-module"></a>Como usar um módulo

Para usar um módulo, execute as seguintes tarefas:

1. Instale o módulo. (Isso é geralmente feito para você.)
1. Localize os comandos que o módulo adicionou.
1. Use os comandos que o módulo adicionou.

Este tópico explica como executar essas tarefas. Ele também inclui outras informações úteis sobre o gerenciamento de módulos.

## <a name="how-to-install-a-module"></a>Como instalar um módulo

Se você receber um módulo como uma pasta com arquivos, será necessário instalá-lo em seu computador antes de poder usá-lo no PowerShell.

A maioria dos módulos é instalada por você. O PowerShell vem com vários módulos pré-instalados, às vezes chamados de módulos _principais_ . Em computadores baseados no Windows, se os recursos incluídos no sistema operacional tiverem cmdlets para gerenciá-los, esses módulos serão pré-instalados. Quando você instala um recurso do Windows, usando, por exemplo, o assistente Adicionar funções e recursos no Gerenciador do Servidor ou a caixa de diálogo ativar ou desativar recursos do Windows no painel de controle, todos os módulos do PowerShell que fazem parte do recurso são instalados. Muitos outros módulos têm um instalador ou um programa de Instalação que instala o módulo.

Use o seguinte comando para criar um diretório de **módulos** para o usuário atual:

```powershell
New-Item -Type Directory -Path $HOME\Documents\WindowsPowerShell\Modules
```

Copie a pasta de módulo inteira para o diretório Modules. Você pode usar qualquer método para copiar a pasta, incluindo o Windows Explorer e Cmd.exe, bem como o PowerShell. No PowerShell, use o `Copy-Item` cmdlet. Por exemplo, para copiar a pasta MyModule de `C:\ps-test\MyModule` para o diretório Modules, digite:

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\WindowsPowerShell\Modules
```

Você pode instalar um módulo em qualquer local, mas instalar os módulos em um local padrão de módulo torna-os mais fáceis de gerenciar. Para obter mais informações sobre os locais de módulo padrão, consulte o [módulo e os locais de recursos de DSC e](#module-and-dsc-resource-locations-and-psmodulepath) a seção PSModulePath.

## <a name="how-to-find-installed-modules"></a>Como localizar os módulos instalados

Para localizar os módulos que são instalados em um local de módulo padrão, mas ainda não foram importados para a sessão, digite:

```powershell
Get-Module -ListAvailable
```

Para localizar os módulos que já foram importados para a sessão, no prompt do PowerShell, digite:

```powershell
Get-Module
```

Para obter mais informações sobre o `Get-Module` cmdlet, consulte [obter-módulo](xref:Microsoft.PowerShell.Core.Get-Module).

## <a name="how-to-find-the-commands-in-a-module"></a>Como localizar os comandos em um módulo

Use o `Get-Command` cmdlet para localizar todos os comandos disponíveis. Você pode usar os parâmetros do `Get-Command` cmdlet para filtrar comandos, como por módulo, nome e substantivo.

Para localizar todos os comandos em um módulo, digite:

```powershell
Get-Command -Module <module-name>
```

Por exemplo, para localizar os comandos no módulo BitsTransfer, digite:

```powershell
Get-Command -Module BitsTransfer
```

Para obter mais informações sobre o `Get-Command` cmdlet, consulte [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).

## <a name="how-to-get-help-for-the-commands-in-a-module"></a>Como obter ajuda para os comandos em um módulo

Se o módulo contiver arquivos de ajuda para os comandos que ele exporta, o `Get-Help` cmdlet exibirá os tópicos da ajuda. Use o mesmo `Get-Help` formato de comando que você usaria para obter ajuda para qualquer comando no PowerShell.

A partir do PowerShell 3,0, você pode baixar arquivos de ajuda para um módulo e baixar atualizações para os arquivos de ajuda para que eles nunca sejam obsoletos.

Para obter ajuda para os comandos em um módulo, digite:

```powershell
Get-Help <command-name>
```

Para obter ajuda online para o comando em um módulo, digite:

```powershell
Get-Help <command-name> -Online
```

Para baixar e instalar os arquivos de ajuda para os comandos em um módulo, digite:

```powershell
Update-Help -Module <module-name>
```

Para obter mais informações, consulte [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) e [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).

## <a name="how-to-import-a-module"></a>Como importar um módulo

Você pode precisar importar um módulo ou importar um arquivo de módulo. A importação é necessária quando um módulo não está instalado nos locais especificados pela variável de ambiente **PSModulePath** , `$env:PSModulePath` ou o módulo consiste em um arquivo, como um arquivo. dll ou. psm1, em vez de um módulo típico que é entregue como uma pasta.

Você também pode optar por importar um módulo para que possa usar os parâmetros do `Import-Module` comando, como o parâmetro Prefix, que adiciona um prefixo distintivo aos nomes de substantivo de todos os comandos importados, ou o parâmetro **NoClobber** , que impede que o módulo adicione comandos que ocultam ou substituem os comandos existentes na sessão.

Para importar módulos, use o `Import-Module` cmdlet.

Para importar os módulos em um local de PSModulePath para a sessão atual, use o seguinte formato de comando.

```powershell
Import-Module <module-name>
```

Por exemplo, o comando a seguir importa o módulo BitsTransfer para a sessão atual.

```powershell
Import-Module BitsTransfer
```

Para importar um módulo que não está em um local padrão de módulo, use o caminho totalmente qualificado para a pasta de módulo no comando.

Por exemplo, para adicionar o módulo TestCmdlets no `C:\ps-test` diretório à sua sessão, digite:

```powershell
Import-Module C:\ps-test\TestCmdlets
```

Para importar um arquivo de módulo que não está contido em uma pasta de módulo, use o caminho totalmente qualificado para o arquivo de módulo no comando.

Por exemplo, para adicionar o módulo TestCmdlets.dll no `C:\ps-test` diretório à sua sessão, digite:

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

Para obter mais informações sobre como adicionar módulos à sua sessão, consulte [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).

## <a name="how-to-import-a-module-into-every-session"></a>Como importar um módulo para cada sessão

O `Import-Module` comando importa módulos para sua sessão atual do PowerShell. Para importar um módulo para cada sessão do PowerShell que você iniciar, adicione o `Import-Module` comando ao seu perfil do PowerShell.

Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).

## <a name="how-to-remove-a-module"></a>Como remover um módulo

Quando você remove um módulo, os comandos que o módulo adicionou são excluídos da sessão.

Para remover um módulo da sua sessão, use o seguinte formato de comando.

```powershell
Remove-Module <module-name>
```

Por exemplo, o comando a seguir remove o módulo BitsTransfer da sessão atual.

```powershell
Remove-Module BitsTransfer
```

Remover um módulo inverte a operação de importação de um módulo. Remover um módulo não desinstala o módulo. Para obter mais informações, consulte [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a>Locais de recursos de módulo e DSC e PSModulePath

A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.

Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:

- Locais de todo o sistema: `$PSHOME\Modules`

  Essas pastas contêm módulos que acompanham o Windows e o PowerShell.

  Os recursos de DSC incluídos com o PowerShell são armazenados na `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` pasta.

- Módulos específicos do usuário: são módulos instalados pelo usuário no escopo do usuário. `Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários. Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).

  O local **CurrentUser** específico do usuário no Windows é a `PowerShell\Modules` pasta localizada no local **documentos** em seu perfil de usuário. O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta. O Microsoft OneDrive também pode alterar o local da sua pasta de **documentos** .

  Por padrão, no Windows 10, esse local é `$HOME\Documents\PowerShell\Modules` . No Linux ou Mac, o local **CurrentUser** é `$HOME/.local/share/powershell/Modules` .

  > [!NOTE]
  > Você pode verificar o local da pasta **documentos** usando o seguinte comando: `[Environment]::GetFolderPath('MyDocuments')` .

- O local **AllUsers** está `$env:PROGRAMFILES\PowerShell\Modules` no Windows. No Linux ou Mac, os módulos são armazenados em `/usr/local/share/powershell/Modules` .

> [!NOTE]
> Para adicionar ou alterar arquivos no `$env:Windir\System32` diretório, inicie o PowerShell com a opção **Executar como administrador** .

Você pode alterar os locais de módulo padrão no sistema alterando o valor da variável de ambiente **PSModulePath** , `$Env:PSModulePath` . A variável de ambiente **PSModulePath** é modelada na variável de ambiente Path e tem o mesmo formato.

Para exibir os locais padrão de módulo, digite:

```powershell
$Env:PSModulePath
```

Para adicionar um local padrão de módulo, use o seguinte formato de comando.

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

O ponto e vírgula ( `;` ) no comando separa o novo caminho do caminho que o precede na lista.

Por exemplo, para adicionar o `C:\ps-test\Modules` diretório, digite:

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

Quando você adiciona um caminho ao **PSModulePath** `Get-Module` e os `Import-Module` comandos incluem módulos nesse caminho.

O valor que você define afeta apenas a sessão atual. Para fazer a alteração persistente, adicione o comando ao seu perfil do PowerShell ou use o sistema no painel de controle para alterar o valor da variável de ambiente **PSModulePath** no registro.

Além disso, para fazer a alteração persistente, você também pode usar o método **SetEnvironmentVariable não** da classe **System. Environment** para adicionar um caminho à variável de ambiente **PSModulePath** .

Para obter mais informações sobre a variável **PSModulePath** , consulte [about_Environment_Variables](about_Environment_Variables.md).

## <a name="modules-and-name-conflicts"></a>Conflitos de módulos e nomes

Os conflitos de nome ocorrem quando mais de um comando na sessão tem o mesmo nome. Importar um módulo provoca um conflito de nome quando os comandos no módulo têm os mesmos nomes de comandos ou itens na sessão.

Os conflitos de nome podem resultar em comandos sendo ocultados ou substituídos.

### <a name="hidden"></a>Hidden

Um comando é ocultado quando ele não é o comando que é executado quando você digita o nome do comando, mas você pode executá-lo usando outro método, como qualificar o nome do comando com o nome do módulo ou snap-in na qual ele se originou.

### <a name="replaced"></a>Substituído

Um comando é substituído quando você não pode executá-lo porque ele foi substituído por um comando com o mesmo nome. Mesmo quando você remove o módulo que causou o conflito, não é possível executar um comando substituído, a menos que você reinicie a sessão.

`Import-Module` pode adicionar comandos que ocultam e substituem comandos na sessão atual. Além disso, os comandos na sessão podem ocultar os comandos que o módulo adicionou.

Para detectar conflitos de nome, use o parâmetro **All** do `Get-Command` cmdlet. A partir do PowerShell 3,0, `Get-Command` obtém somente os comandos que são executados quando você digita o nome do comando. O parâmetro **All** Obtém todos os comandos com o nome específico na sessão.

Para evitar conflitos de nome, use os parâmetros **NoClobber** ou **prefix** do `Import-Module` cmdlet. O parâmetro **prefix** adiciona um prefixo aos nomes dos comandos importados para que eles sejam exclusivos na sessão. O parâmetro **NoClobber** não importa nenhum comando que oculte ou substitua os comandos existentes na sessão.

Você também pode usar o **alias**, o **cmdlet**, a **função** e os parâmetros **variáveis** do `Import-Module` para selecionar apenas os comandos que deseja importar e pode excluir comandos que causam conflitos de nome em sua sessão.

Os autores de módulo podem evitar conflitos de nome usando a propriedade **DefaultCommandPrefix** do manifesto do módulo para adicionar um prefixo padrão a todos os nomes de comando.
O valor do parâmetro **prefix** tem precedência sobre o valor de **DefaultCommandPrefix**.

Mesmo se um comando estiver oculto, você poderá executá-lo qualificando o nome de comando com o nome do módulo ou snap-in no qual ele foi originado.

As regras de precedência de comando do PowerShell determinam qual comando é executado quando a sessão inclui comandos com o mesmo nome.

Por exemplo, quando uma sessão inclui uma função e um cmdlet com o mesmo nome, o PowerShell executa a função por padrão. Quando a sessão inclui comandos do mesmo tipo com o mesmo nome, como dois cmdlets com o mesmo nome, por padrão, ela executa o comando adicionado mais recentemente.

Para obter mais informações, incluindo uma explicação das regras de precedência e instruções para executar comandos ocultos, consulte [about_Command_Precedence](about_Command_Precedence.md).

## <a name="modules-and-snap-ins"></a>Módulos e snap-ins

Você pode adicionar comandos à sua sessão por meio de módulos e snap-ins. Os módulos podem adicionar todos os tipos de comandos, incluindo cmdlets, provedores e funções, e itens, como variáveis, aliases e unidades do PowerShell. Os Snap-ins podem adicionar apenas os cmdlets e provedores.

Antes de remover um módulo ou snap-in da sessão, use os comandos a seguir para determinar quais comandos serão removidos.

Para localizar a origem de um cmdlet em sua sessão, use o seguinte formato de comando:

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

Por exemplo, para localizar a origem do `Get-Date` cmdlet, digite:

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

Para obter mais informações sobre snap-ins do PowerShell, consulte [about_Pssnapins](about_PSSnapins.md).

## <a name="module-related-warnings-and-errors"></a>Avisos e erros relacionados ao módulo

Os comandos exportados por um módulo devem seguir as regras de nomenclatura de comando do PowerShell. Se o módulo que você importar exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o `Import-Module` cmdlet exibe a seguinte mensagem de aviso.

> Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis. Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."

A mensagem é apenas um aviso. O módulo completo ainda é importado, incluindo os comandos não autorizados. Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.

Para suprimir a mensagem de aviso, use o parâmetro **DisableNameChecking** do `Import-Module` cmdlet.

## <a name="built-in-modules-and-snap-ins"></a>Módulos internos e snap-ins

No PowerShell 2,0 e em programas de host de estilo mais antigo no PowerShell 3,0 e posteriores, os comandos principais instalados com o PowerShell são empacotados em snap-ins que são adicionados automaticamente a todas as sessões do PowerShell.

A partir do PowerShell 3,0, para programas de host que implementam a `InitialSessionState.CreateDefault2` API de estado de sessão inicial, o snap-in do Microsoft. PowerShell. Core é adicionado a cada sessão por padrão. Os módulos são carregados automaticamente no primeiro uso.

> [!NOTE]
> Sessões remotas, incluindo sessões que são iniciadas usando o `New-PSSession` cmdlet, são sessões de estilo mais antigas nas quais os comandos internos são empacotados em snap-ins.

Os seguintes módulos (ou snap-ins) são instalados com o PowerShell.

- CimCmdlets
- Microsoft.PowerShell.Archive
- Microsoft.PowerShell.Core
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.ODataUtils
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management
- PackageManagement
- PowerShellGet
- PSDesiredStateConfiguration
- PSDiagnostics
- PSScheduledJob
- PSWorkflow
- PSWorkflowUtility
- ISE

## <a name="logging-module-events"></a>Log de eventos do módulo

A partir do PowerShell 3,0, você pode registrar eventos de execução para os cmdlets e funções nos módulos e snap-ins do PowerShell definindo a propriedade **LogPipelineExecutionDetails** de módulos e snap-ins no `$True` .
Você também pode usar uma configuração de Política de Grupo, ativar o registro em log de módulo para habilitar o log de módulo em todas as sessões do PowerShell. Para obter mais informações, consulte [about_EventLogs](about_EventLogs.md) e [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="see-also"></a>Consulte Também

[about_Command_Precedence](about_Command_Precedence.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_PSSnapins](about_PSSnapins.md)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)
