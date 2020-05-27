---
title: Migrando do Windows PowerShell 5.1 para o PowerShell 7
description: Atualize do PowerShell 5.1 para o PowerShell 7 em suas plataformas Windows.
ms.date: 03/25/2020
ms.openlocfilehash: cb14a4f159b6dc33f31386da4264c0ebb640aef8
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809202"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a>Migrando do Windows PowerShell 5.1 para o PowerShell 7

Projetado para ambientes locais, híbridos e de nuvem, o PowerShell 7 é fornecido com aprimoramentos e [novos recursos](../whats-new/What-s-New-in-PowerShell-70.md).

- É instalado e executado lado a lado com o Windows PowerShell
- Melhorias na compatibilidade com os módulos existentes do Windows PowerShell
- Novos recursos de linguagem, como operadores ternários e `ForEach-Object -Parallel`
- desempenho aprimorado
- Comunicação remota baseada em SSH
- Interoperabilidade entre plataformas
- Suporte para os contêineres do Docker

O PowerShell 7 funciona em conjunto com o Windows PowerShell, permitindo testar e comparar facilmente as edições antes da implantação. A migração é simples, rápida e segura.

O PowerShell 7 é compatível com os seguintes sistemas operacionais Windows:

- Windows 8.1 e 10
- Windows Server 2012, 2012 R2, 2016 e 2019

O PowerShell 7 também é executado no macOS e em várias distribuições do Linux. Para obter uma lista dos sistemas operacionais compatíveis e informações do ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle).

## <a name="installing-powershell-7"></a>Instalar o PowerShell 7

Para obter flexibilidade e dar suporte às necessidades de TI, aos engenheiros de DevOps e aos desenvolvedores, há várias opções disponíveis para instalação do PowerShell 7. Na maioria dos casos, as opções de instalação podem ser reduzidas aos seguintes métodos:

- Implantar o PowerShell usando o [pacote MSI](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)
- Implantar o PowerShell usando o [pacote ZIP](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)

> [!NOTE]
> O pacote MSI pode ser implantado e atualizado com produtos de gerenciamento, como o [SCCM (System Center Configuration Manager)](/configmgr/apps/). Baixe os pacotes da [página de versões do GitHub](https://github.com/PowerShell/PowerShell/releases).

A implantação do pacote MSI requer permissão de administrador. O pacote ZIP pode ser implantado por qualquer usuário. O pacote ZIP é a maneira mais fácil de instalar o PowerShell 7 para testes, antes de se comprometer com uma instalação completa.

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a>Usar o PowerShell 7 em conjunto com o Windows PowerShell 5.1

O PowerShell 7 foi projetado para coexistir com o Windows PowerShell 5.1. Os recursos a seguir garantem que seu investimento no PowerShell esteja protegido e que a migração para o PowerShell 7 seja simples.

- Caminho de instalação e nome do executável separados
- PSModulePath separado
- Perfis separados para cada versão
- Compatibilidade de módulo aprimorada
- Novos pontos de extremidade de comunicação remota
- Suporte à política de grupo
- Logs de eventos separados

### <a name="separate-installation-path-and-executable-name"></a>Caminho de instalação e nome do executável separados

O PowerShell 7 é instalado em um novo diretório, permitindo a execução em conjunto com o Windows PowerShell 5.1.

Locais de instalação por versão:

- Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`
- PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`
- PowerShell 7: `$env:ProgramFiles\PowerShell\7`

O novo local é adicionado ao seu caminho, permitindo que você execute o Windows PowerShell 5.1 e o PowerShell 7. Se você estiver migrando do PowerShell Core 6.x para o PowerShell 7, o PowerShell 6 será removido e o caminho substituído.

No Windows PowerShell, o executável do PowerShell é denominado `powershell.exe`. Na versão 6 e posteriores, o executável é denominado `pwsh.exe`. O novo nome torna facilita o suporte à execução lado a lado das duas versões.

### <a name="separate-psmodulepath"></a>PSModulePath separado

Por padrão, o Windows PowerShell e o PowerShell 7 armazenam seus módulos em locais diferentes. O PowerShell 7 combina esses locais na variável de ambiente `$Env:PSModulePath`. Ao importar um módulo por nome, o PowerShell verifica o local especificado no `$Env:PSModulePath`. Assim, o PowerShell 7 pode carregar os módulos Core e Desktop.

|            Escopo de instalação            |                Windows PowerShell 5.1                 |             PowerShell 7.0             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| Módulos do PowerShell                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| Instalado pelo usuário<br>Escopo AllUsers    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| Instalado pelo usuário<br>Escopo CurrentUser | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

Os exemplos a seguir mostram os valores padrão de `$Env:PSModulePath` para cada versão.

- Para o Windows PowerShell 5.1:

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- Para o PowerShell 7:

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

Observe que o PowerShell 7 inclui os caminhos do Windows PowerShell e do PowerShell 7 para fornecer o carregamento automático de módulos.

> [!NOTE]
> Poderá haver caminhos adicionais se você tiver alterado a variável de ambiente PSModulePath ou instalado módulos ou aplicativos personalizados.

Confira mais informações sobre `PSModulePath` em [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).

Para obter mais informações sobre módulos, confira [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).

### <a name="separate-profiles"></a>Perfis separados

Um perfil do PowerShell é um script executado quando o PowerShell é iniciado. Esse script personaliza seu ambiente adicionando comandos, aliases, funções, variáveis, módulos e unidades do PowerShell. O script de perfil disponibiliza essas personalizações em cada sessão sem precisar recriá-las manualmente.

O caminho para o local do perfil foi alterado no PowerShell 7.

- No Windows PowerShell 5.1, o local do perfil é `$HOME\Documents\WindowsPowerShell`.
- No PowerShell 7, o local do perfil é `$HOME\Documents\PowerShell`.

Os nomes de arquivos de perfil também foram alterados:

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

Confira mais informações em [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a>Compatibilidade do PowerShell 7 com os módulos do Windows PowerShell 5.1

A maioria dos módulos que você usa no Windows PowerShell 5.1 já funciona com o PowerShell 7, incluindo o Azure PowerShell e o Active Directory. Continuamos a trabalhar com outras equipes para adicionar suporte nativo do PowerShell 7 em mais módulos, incluindo o Microsoft Graph, Office 365 e outros. Confira a lista atual de módulos compatíveis em [Compatibilidade de módulos do PowerShell 7](/powershell/scripting/whats-new/module-compatibility).

> [!NOTE]
> No Windows, também adicionamos uma opção **UseWindowsPowerShell** a `Import-Module` a fim de facilitar a transição para o PowerShell 7 de quem usa módulos incompatíveis. Para obter mais informações sobre essa funcionalidade, confira [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).

### <a name="powershell-remoting"></a>Comunicação remota do PowerShell

A comunicação remota do PowerShell permite executar qualquer comando do PowerShell em um ou vários computadores remotos. Você pode estabelecer conexões persistentes, iniciar sessões interativas e executar scripts em computadores remotos.

#### <a name="ws-management-remoting"></a>Comunicação remota do WS-Management

O Windows PowerShell 5.1 e as versões anteriores usam o protocolo WSMAN (WS-Management) para negociação de conexão e transporte de dados. O WinRM (Gerenciamento Remoto do Windows) usa o protocolo WSMAN. Se o WinRM estiver habilitado, o PowerShell 7 usará o ponto de extremidade existente do Windows PowerShell 5.1 chamado `Microsoft.PowerShell` para conexões de comunicação remota. Para atualizar o PowerShell 7 de modo que inclua seu próprio ponto de extremidade, execute o cmdlet `Enable-PSRemoting`. Confira mais informações sobre como se conectar a pontos de extremidade específicos em [Comunicação remota do WS-Management no PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)

Para usar a comunicação remota do Windows PowerShell, o computador remoto deve ser configurado para gerenciamento remoto.
Para obter mas informações, incluindo instruções consulte [Sobre requisitos remotos](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).

Confira mais informações sobre a comunicação remota em [Sobre comunicação remota](/powershell/module/microsoft.powershell.core/about/about_remote)

#### <a name="ssh-based-remoting"></a>Comunicação remota baseada em SSH

A comunicação remota baseada em SSH foi adicionada ao PowerShell Core 6.x para dar suporte a outros sistemas operacionais que não podem usar componentes nativos do Windows, como o **WinRM**. A comunicação remota do SSH cria um processo de hospedagem do PowerShell no computador de destino como um subsistema de SSH. Confira detalhes e exemplos sobre como configurar a comunicação remota baseada em SSH no Windows ou no Linux em: [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

> [!NOTE]
> A PSGallery (Galeria do PowerShell) contém um módulo e um cmdlet que configura automaticamente a comunicação remota baseada em SSH. Instale o módulo `Microsoft.PowerShell.RemotingTools` da [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) e execute o cmdlet `Enable-SSH`.

Os cmdlets `New-PSSession`, `Enter-PSSession` e `Invoke-Command` têm novos conjuntos de parâmetros para dar suporte a conexões SSH.

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

Para criar uma sessão remota, especifique o computador de destino com o parâmetro **HostName** e forneça o nome de usuário com **UserName**. Ao executar os cmdlets interativamente, você receberá uma solicitação de senha.

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

Como alternativa, ao usar o parâmetro **HostName**, forneça as informações de nome de usuário seguidas pelo sinal de arroba (`@`) e pelo nome do computador.

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

Você também pode configurar a autenticação de chave SSH usando um arquivo de chave privada com o parâmetro **KeyFilePath**.
Confira mais informações em [Gerenciamento de chaves OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).

### <a name="group-policy-supported"></a>Política de Grupo compatível

O PowerShell inclui configurações de Política de Grupo para ajudar você a definir valores consistentes de opções nos servidores de um ambiente empresarial. Essas configurações incluem:

- Configuração de sessão do console: define um ponto de extremidade de configuração em que o PowerShell é executado.
- Ativar Registro em Log do Módulo: define a propriedade LogPipelineExecutionDetails dos módulos.
- Ativar o Registro em Log de Blocos de Script do PowerShell: ativa o registro em log detalhado de todos os scripts do PowerShell.
- Ativar a Execução do Script: define a política de execução do PowerShell.
- Ativar a Transcrição do PowerShell: ativa a captura de entradas e saídas dos comandos do PowerShell como transcrições baseadas em texto.
- Definir o caminho de origem padrão para Update-Help: define a origem para a Ajuda Atualizável como um diretório, e não a Internet.

Confira mais informações em [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).

O PowerShell 7 inclui modelos de Política de Grupo e um script de instalação em `$PSHOME`.

As ferramentas de Política de Grupo usam arquivos de modelos administrativos (`.admx`, `.adml`) para preencher as configurações de políticas na interface do usuário. Assim, os administradores podem gerenciar as configurações de políticas com base no registro. O script `InstallPSCorePolicyDefinitions.ps1` instala os Modelos Administrativos do PowerShell Core no computador local.

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a>Logs de Eventos Separados

O Windows PowerShell e o PowerShell 7 registram eventos em logs de eventos separados. Use o comando a seguir para obter uma lista de logs do PowerShell.

```powershell
Get-WinEvent -ListLog *PowerShell*
```

Confira mais informações em [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).

## <a name="improved-editing-experience-with-visual-studio-code"></a>Melhoria da experiência de edição no Visual Studio Code

O [VSCode (Visual Studio Code)](https://code.visualstudio.com/) com a [Extensão do PowerShell](https://code.visualstudio.com/docs/languages/powershell) é o ambiente de script compatível com o PowerShell 7. O ISE (Ambiente de Script Integrado) do Windows PowerShell dá suporte somente ao Windows PowerShell.

A extensão atualizada do PowerShell inclui:

- Novo modo de Compatibilidade do ISE
- PSReadLine no Console Integrado, incluindo realce de sintaxe, edição de várias linhas e pesquisa de retorno
- Melhorias de desempenho e estabilidade
- Nova integração do CodeLens
- Melhoria do preenchimento automático de caminho

Para facilitar a transição para o Visual Studio Code, use a função **Habilitar o Modo ISE** disponível na **Paleta de Comandos**. Essa função alterna o VSCode para um layout no estilo do ISE. O layout no estilo do ISE fornece todos os novos recursos e funcionalidades do PowerShell em uma experiência de usuário conhecida.

Para alternar para o novo layout do ISE, pressione <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> a fim de abrir a **Paleta de Comandos**, digite `PowerShell` e selecione **PowerShell: Habilitar o Modo ISE**.

Para definir o layout para o original, abra a **Paleta de Comandos**, selecione **PowerShell: Desabilitar o Modo ISE (restaurar padrões)** .

Para obter detalhes sobre como personalizar o layout do VSCode para o ISE, confira [Como Replicar a Experiência do ISE no Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)

> [!NOTE]
> Não há planos para atualizar o ISE com novos recursos. Agora, o ISE é um recurso desinstalável pelo usuário nas versões mais recentes do Windows 10 e do Windows Server. Não há planos para remover permanentemente o ISE. A equipe do PowerShell e seus parceiros concentram-se em melhorar a experiência de script na extensão do PowerShell para o Visual Studio Code.

## <a name="next-steps"></a>Próximas etapas

Munido do conhecimento para migrar efetivamente, [instale o PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) agora mesmo!
