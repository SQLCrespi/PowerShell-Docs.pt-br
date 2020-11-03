---
description: Descreve as configurações de Política de Grupo do PowerShell
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: c247feb5b7c604e3e1d0442a9aa142e5eb25ec08
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195903"
---
# <a name="about-group-policy-settings"></a>Sobre configurações de Política de Grupo

## <a name="short-description"></a>Descrição breve
Descreve as configurações de Política de Grupo do PowerShell

## <a name="long-description"></a>Descrição longa

O PowerShell inclui Política de Grupo configurações para ajudá-lo a definir valores de configuração consistentes para computadores Windows em um ambiente empresarial.

As configurações de Política de Grupo do PowerShell estão nos seguintes caminhos de Política de Grupo:

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

As configurações de política de grupo no caminho de configuração do usuário têm precedência sobre Política de Grupo configurações no caminho de configuração do computador.

O PowerShell 7 inclui modelos de Política de Grupo e um script de instalação em `$PSHOME`.

As ferramentas de Política de Grupo usam arquivos de modelos administrativos (`.admx`, `.adml`) para preencher as configurações de políticas na interface do usuário. Assim, os administradores podem gerenciar as configurações de políticas com base no registro. O `InstallPSCorePolicyDefinitions.ps1` script instala o **PowerShell Core modelos administrativos** no computador local.

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode       LastWriteTime         Length Name
----       -------------         ------ ----
-a---      2/27/2020 12:38 AM     15861 InstallPSCorePolicyDefinitions.ps1
-a---      2/27/2020 12:28 AM      9675 PowerShellCoreExecutionPolicy.adml
-a---      2/27/2020 12:28 AM      6201 PowerShellCoreExecutionPolicy.admx
```

Depois de instalar os modelos, você pode editar essas configurações no editor de Política de Grupo ( `gpedit.msc` ).

As políticas são as seguintes:

- Configuração de sessão do console: define um ponto de extremidade de configuração em que o PowerShell é executado.
- Ativar registro em log de módulo: define a propriedade **LogPipelineExecutionDetails** de módulos.
- Ativar o Registro em Log de Blocos de Script do PowerShell: ativa o registro em log detalhado de todos os scripts do PowerShell.
- Ativar a Execução do Script: define a política de execução do PowerShell.
- Ativar a Transcrição do PowerShell: ativa a captura de entradas e saídas dos comandos do PowerShell como transcrições baseadas em texto.
- Definir o caminho de origem padrão para `Update-Help` : define a fonte para a ajuda atualizável para um diretório, não para a Internet.

Cada configuração de Política de Grupo do PowerShell tem uma opção (' Use o campo configuração de política do Windows PowerShell ') para usar o valor de uma configuração semelhante do Windows PowerShell Política de Grupo que está localizada nos seguintes caminhos de Política de Grupo:

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

> [!NOTE]
> Essas **modelos administrativos do PowerShell Core** não incluem configurações para o Windows PowerShell. Para obter mais informações sobre como adquirir outros modelos e configurar a política de grupo, consulte [como criar e gerenciar o armazenamento central para Política de Grupo modelos administrativos no Windows][gpstore].

## <a name="console-session-configuration"></a>Configuração de sessão do console

A configuração de política de **configuração de sessão de console** especifica um ponto de extremidade de configuração no qual o PowerShell é executado. Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.

## <a name="turn-on-module-logging"></a>Ativar o registro em log de módulo

A configuração ativar política de **log de módulo** ativa o registro em log para os módulos selecionados do PowerShell. A configuração é eficaz em todas as sessões em todos os computadores afetados.

Se você habilitar essa configuração de política e especificar um ou mais módulos, os eventos de execução de pipeline para os módulos especificados serão registrados no log do Windows PowerShell em Visualizador de Eventos.

Se você desabilitar essa configuração de política, o log de eventos de execução será desabilitado para todos os módulos do PowerShell.

Se essa configuração de política não estiver configurada, a propriedade **LogPipelineExecutionDetails** de cada módulo determinará se os eventos de execução de um módulo são registrados. Por padrão, a propriedade **LogPipelineExecutionDetails** de todos os módulos é definida como false.

Para ativar o log de módulo para um módulo, use o seguinte formato de comando. O módulo deve ser importado para a sessão e a configuração só é eficaz na sessão atual.

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

Para ativar o log de módulo para todas as sessões em um computador específico, adicione os comandos anteriores ao perfil do PowerShell ' todos os usuários ' ( `$Profile.AllUsersAllHosts` ).

Para obter mais informações sobre o log de módulo, consulte [about_Modules](about_Modules.md).

## <a name="turn-on-powershell-script-block-logging"></a>Ativar o log de bloco de script do PowerShell

A configuração de política **Ativar log de bloco de script do PowerShell** habilita o log de todas as entradas de script do PowerShell para o log de eventos Microsoft-Windows-PowerShell/Operational. Se você habilitar essa configuração de política, o PowerShell Core registrará em log o processamento de comandos, blocos de script, funções e scripts – sejam invocados interativamente ou através da automação.

Se você desabilitar essa configuração de política, o registro em log da entrada de script do PowerShell será desabilitado. Se você habilitar o registro em log da invocação do bloco de script, o PowerShell registrará eventos adicionalmente quando a invocação de um comando, um bloco de script, uma função ou um script for iniciada ou interrompida. Habilitar o registro em log de invocação gera um alto volume de logs de eventos.

## <a name="turn-on-script-execution"></a>Ativar a execução do script

A configuração ativar política de **execução de script** define a política de execução para computadores e usuários, que determina quais scripts podem ser executados.

Se você habilitar a configuração de política, poderá selecionar entre as seguintes configurações de política.

- **Permitir somente scripts assinados** permite que os scripts sejam executados somente se forem assinados por um fornecedor confiável. Essa configuração de política é equivalente à política de execução AllSigned.

- **Permitir scripts locais e scripts remotos assinados** permite que todos os scripts locais sejam executados. Os scripts originados na Internet devem ser assinados por um fornecedor confiável. Essa configuração de política é equivalente à política de execução RemoteSigned.

- **Permitir todos os scripts** permite a execução de todos os scripts. Essa configuração de política é equivalente à política de execução irrestrita.

Se você desabilitar essa configuração de política, nenhum script poderá ser executado. Essa configuração de política é equivalente à política de execução restrita.

Se você desabilitar ou não definir essa configuração de política, a política de execução definida para o computador ou usuário pelo `Set-ExecutionPolicy` cmdlet determinará se os scripts têm permissão para serem executados. O valor padrão é Restricted.

Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).

## <a name="turn-on-powershell-transcription"></a>Ativar transcrição do PowerShell

A configuração da política **Ativar transcrição do PowerShell** permite capturar a entrada e a saída de comandos do PowerShell Core em transcrições baseadas em texto. Se você habilitar essa configuração de política, o PowerShell Core habilitará o log de transcrição para o PowerShell Core e quaisquer outros aplicativos que utilizem o mecanismo do PowerShell Core. Por padrão, o PowerShell Core registrará a saída da transcrição no diretório meus documentos de cada usuário, com um nome de arquivo que inclui ' PowerShell_transcript ', junto com o nome do computador e a hora de início.
Habilitar essa política é equivalente a chamar o cmdlet Start-Transcript em cada sessão do PowerShell Core.

Se você desabilitar essa configuração de política, o log de transcrição de aplicativos baseados no PowerShell será desabilitado por padrão, embora a transcrição ainda possa ser habilitada por meio do cmdlet Start-Transcript.

Se você usar a configuração OutputDirectory para habilitar o registro em log de transcrição para um local compartilhado, certifique-se de limitar o acesso a esse diretório para impedir que os usuários exibam as transcrições de outros usuários ou computadores.

## <a name="set-the-default-source-path-for-update-help"></a>Defina o caminho de origem padrão para Update-Help

A configuração **definir o caminho de origem padrão para a política de atualização-ajuda** define um valor padrão para o parâmetro **SourcePath** do `Update-Help` cmdlet.
Essa configuração impede que os usuários usem o `Update-Help` cmdlet para baixar arquivos de ajuda da Internet.

> [!NOTE]
> Essa configuração de Política de Grupo aparece em **configuração do computador** e configuração do **usuário** . No entanto, somente a configuração Política de Grupo em **configuração do computador** é eficaz. A configuração Política de Grupo em **configuração do usuário** é ignorada.

O `Update-Help` cmdlet baixa e instala os arquivos de ajuda mais recentes para os módulos do PowerShell e os instala no computador. Por padrão, `Update-Help` o baixa novos arquivos de ajuda de um local de Internet especificado pelo módulo.

No entanto, você pode usar o `Save-Help` cmdlet para baixar os arquivos de ajuda mais recentes para um local do sistema de arquivos, como um compartilhamento de rede e, em seguida, usar o `Update-Help` cmdlet para obter os arquivos de ajuda do local do sistema de arquivos e instalá-los no computador. O parâmetro **SourcePath** do `Update-Help` cmdlet especifica o local do sistema de arquivos.

Ao fornecer um valor padrão para o parâmetro **SourcePath** , essa configuração de política de grupo adiciona implicitamente o parâmetro **SourcePath** a todos os `Update-Help` comandos. Os usuários podem substituir o local do sistema de arquivos específico especificado como o valor padrão inserindo um local diferente do sistema de arquivos.
Mas não podem remover o parâmetro **SourcePath** do `Update-Help` comando.

Se você habilitar essa configuração de política, poderá especificar um valor padrão para o parâmetro **SourcePath** . Insira um local do sistema de arquivos.

Se essa configuração de política estiver desabilitada ou não estiver configurada, não haverá valor padrão para o parâmetro **SourcePath** do `Update-Help` cmdlet. Os usuários podem baixar a ajuda da Internet ou de qualquer local do sistema de arquivos.

Para obter mais informações, consulte [about_Updatable_Help](about_Updatable_Help.md).

## <a name="keywords"></a>Palavras-chave

about_Group_Policies about_GroupPolicy

## <a name="see-also"></a>Confira também

[RFC da política do PowerShell Core](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[about_Execution_Policies](about_Execution_Policies.md)

[about_Modules](about_Modules.md)

[about_Updatable_Help](about_Updatable_Help.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759
