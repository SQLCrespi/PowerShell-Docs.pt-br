---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Recursos de Função JEA
ms.openlocfilehash: 5b5b5977d4fec1ed850f1146fe7c09463908651b
ms.sourcegitcommit: ea7d87a7a56f368e3175219686dfa2870053c644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818168"
---
# <a name="jea-role-capabilities"></a>Recursos de Função JEA

Ao criar um ponto de extremidade JEA, é necessário definir uma ou mais capacidades de função que descrevam o que alguém pode fazer em uma sessão JEA. Uma capacidade de função é um arquivo de dados do PowerShell com a extensão `.psrc` que lista todos os cmdlets, as funções, os provedores e os programas externos que devem ser disponibilizados para os usuários que estão se conectando.

## <a name="determine-which-commands-to-allow"></a>Determinar quais comandos permitir

A primeira etapa na criação de um arquivo de capacidade de função é considerar o que os usuários precisam acessar. O processo de coleta de requisitos pode levar algum tempo, mas é um processo importante. Conceder aos usuários acesso a poucos cmdlets e funções pode impedi-los de cumprir suas tarefas. Permitir acesso a muitos cmdlets e muitas funções pode permitir que os usuários façam mais do que você pretendia e enfraquecer sua postura de segurança.

Como você efetuará esse processo depende de suas metas e da organização. As dicas a seguir podem ajudar a garantir que você está no caminho certo.

1. **Identificar** os comandos que os usuários estão usando para executar seus trabalhos. Isso pode envolver a pesquisa da equipe de TI, a verificação de scripts de automação ou a análise de transcrições e logs de sessão do PowerShell.
2. **Atualize** o uso das ferramentas de linha de comando para equivalentes do PowerShell, sempre que possível, para uma melhor experiência de auditoria e personalização do JEA. Os programas externos não podem ser restritos de forma tão granular como os cmdlets e as funções nativas do PowerShell no JEA.
3. **Restrinja** o escopo dos cmdlets para permitir apenas parâmetros ou valores de parâmetro específicos. Isso é especialmente importante se os usuários precisam gerenciar apenas uma parte de um sistema.
4. **Crie** funções personalizadas para substituir comandos complexos ou comandos que são difíceis de restringir no JEA. Uma função simples que encapsula um comando complexo ou que aplica lógica de validação adicional pode oferecer controle adicional para administradores e simplicidade para usuários finais.
5. **Teste** a lista de escopo de comandos permitidos com seus usuários ou seus serviços de automação e ajuste-a conforme necessário.

### <a name="examples-of-potentially-dangerous-commands"></a>Exemplos de comandos potencialmente perigosos

Uma seleção cuidadosa de comandos é importante para garantir que o ponto de extremidade JEA não permita que o usuário eleve suas permissões.

> [!IMPORTANT]
> As informações essenciais necessárias para os successCommands do usuário em uma sessão JEA são geralmente executadas com privilégios elevados.

A tabela a seguir contém exemplos de comandos que poderão ser usados maliciosamente se forem permitidos em um estado irrestrito. Essa não é uma lista completa e só deve ser usada como um ponto de partida preventivo.

|                                            Risco                                            |                                Exemplo                                |                                                                              Comandos relacionados                                                                              |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Concedendo privilégios de administrador ao usuário que está se conectando, para ignorar o JEA                                | `Add-LocalGroupMember -Member 'CONTOSO\jdoe' -Group 'Administrators'` | `Add-ADGroupMember`, `Add-LocalGroupMember`, `net.exe`, `dsadd.exe`                                                                                                        |
| Execução de código arbitrário, como malware, explorações ou scripts personalizados para ignorar proteções | `Start-Process -FilePath '\\san\share\malware.exe'`                   | `Start-Process`, `New-Service`, `Invoke-Item`, `Invoke-WmiMethod`, `Invoke-CimMethod`, `Invoke-Expression`, `Invoke-Command`, `New-ScheduledTask`, `Register-ScheduledJob` |

## <a name="create-a-role-capability-file"></a>Criar um arquivo de capacidade de função

Você pode criar um novo arquivo de capacidade de função do PowerShell com o cmdlet [New-PSRoleCapabilityFile](/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-6).

```powershell
New-PSRoleCapabilityFile -Path .\MyFirstJEARole.psrc
```

O arquivo de capacidade de função resultante deve ser editado para permitir os comandos necessários para a função. A documentação de ajuda do PowerShell contém vários exemplos de como você pode configurar o arquivo.

### <a name="allowing-powershell-cmdlets-and-functions"></a>Permitir cmdlets e funções do PowerShell

Para autorizar usuários a executar funções ou cmdlets do PowerShell, adicione o nome do cmdlet ou da função nos campos VisibleCmdlets ou VisibleFunctions. Se você não tiver certeza se um comando é um cmdlet ou uma função, execute `Get-Command <name>` e verifique a propriedade **CommandType** na saída.

```powershell
VisibleCmdlets = 'Restart-Computer', 'Get-NetIPAddress'
```

Às vezes, o escopo de um cmdlet ou de uma função específica é muito amplo para as necessidades dos usuários. Um administrador de DNS, por exemplo, provavelmente só precisa de acesso para reiniciar o serviço DNS. Em ambientes de multilocatário, os locatários têm acesso a ferramentas de gerenciamento de autoatendimento. Os locatários devem ser limitados ao gerenciamento de seus próprios recursos. Nesses casos, você pode restringir quais parâmetros são expostos do cmdlet ou da função.

```powershell
VisibleCmdlets = @{ Name = 'Restart-Computer'; Parameters = @{ Name = 'Name' }}
```

Em cenários mais avançados, talvez você também precise restringir os valores que um usuário pode usar com esses parâmetros. As capacidades de função permitem que você defina um conjunto de valores ou um padrão de expressão regular que determina qual entrada é permitida.

```powershell
VisibleCmdlets = @{ Name = 'Restart-Service'; Parameters = @{ Name = 'Name'; ValidateSet = 'Dns', 'Spooler' }},
                 @{ Name = 'Start-Website'; Parameters = @{ Name = 'Name'; ValidatePattern = 'HR_*' }}
```

> [!NOTE]
> Os [parâmetros comuns do PowerShell](/powershell/module/microsoft.powershell.core/about/about_commonparameters) são sempre permitidos, mesmo que você restrinja os parâmetros disponíveis.
> Você não deve listá-los explicitamente no campo Parâmetros.

A tabela a seguir descreve as várias maneiras que podem ser usadas para personalizar um cmdlet ou função visível.
Você pode combinar e fazer a correspondência de qualquer item abaixo no campo **VisibleCmdlets**.

|                                           Exemplo                                           |                                                             Caso de uso                                                              |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `'My-Func'` ou `@{ Name = 'My-Func' }`                                                      | Permite que o usuário execute `My-Func` sem quaisquer restrições nos parâmetros.                                                      |
| `'MyModule\My-Func'`                                                                        | Permite que o usuário execute `My-Func` do módulo `MyModule` sem quaisquer restrições nos parâmetros.                           |
| `'My-*'`                                                                                    | Permite que o usuário execute qualquer cmdlet ou função com o verbo `My`.                                                                 |
| `'*-Func'`                                                                                  | Permite que o usuário execute qualquer cmdlet ou função com o substantivo `Func`.                                                               |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'}, @{ Name = 'Param2' }}`              | Permite que o usuário execute `My-Func` com os parâmetros `Param1` e `Param2`. Qualquer valor pode ser fornecido para os parâmetros.          |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidateSet = 'Value1', 'Value2' }}` | Permite que o usuário execute `My-Func` com o parâmetro `Param1`. Somente "Value1" e "Value2" podem ser fornecidos ao parâmetro.        |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidatePattern = 'contoso.*' }}`    | Permite que o usuário execute `My-Func` com o parâmetro `Param1`. Qualquer valor começando com "contoso" pode ser fornecido ao parâmetro. |

> [!WARNING]
> Como práticas recomendadas de segurança, não é recomendável usar curingas ao definir cmdlets ou funções visíveis. Em vez disso, você deve listar explicitamente cada comando confiável para garantir que outros comandos que compartilham o mesmo esquema de nomenclatura não sejam acidentalmente autorizados.

Não é possível aplicar um **ValidatePattern** e um **ValidateSet** ao mesmo cmdlet ou à mesma função.

Se você fizer isso, **ValidatePattern** substituirá **ValidateSet**.

Para obter mais informações sobre **ValidatePattern**, confira [esta postagem no *Hey, Scripting Guy!* ](https://devblogs.microsoft.com/scripting/validate-powershell-parameters-before-running-the-script/) e o conteúdo de referência [Expressões regulares do PowerShell](/powershell/module/microsoft.powershell.core/about/about_regular_expressions).

### <a name="allowing-external-commands-and-powershell-scripts"></a>Permitindo comandos externos e scripts do PowerShell

Para permitir que os usuários executem scripts do PowerShell (.ps1) e executáveis em uma sessão JEA, é necessário adicionar o caminho completo a cada programa no campo **VisibleExternalCommands**.

```powershell
VisibleExternalCommands = 'C:\Windows\System32\whoami.exe', 'C:\Program Files\Contoso\Scripts\UpdateITSoftware.ps1'
```

Sempre que possível, use funções ou cmdlets do PowerShell equivalentes aos executáveis externos que autorizar, pois você tem controle sobre os parâmetros permitidos com cmdlets e funções do PowerShell.

Muitos executáveis permitem que você leia o estado atual e, em seguida, altere-o fornecendo parâmetros diferentes.

Por exemplo, considere a função de um administrador de servidor de arquivos que gerencia os compartilhamentos de rede hospedados em um sistema. Uma maneira de gerenciar os compartilhamentos é usar `net share`. No entanto, permitir o **net.exe** é perigoso, pois o usuário pode usar o comando para obter privilégios de administrador com `net group Administrators unprivilegedjeauser /add`. Uma opção mais segura é permitir [Get-SmbShare](/powershell/module/smbshare/get-smbshare), que obtém o mesmo resultado, mas tem um escopo muito mais limitado.

Ao disponibilizar comandos externos aos usuários em uma sessão JEA, sempre especifique o caminho completo para o executável. Isso impede a execução de programas nomeados da mesma forma e potencialmente mal-intencionados localizados em outros lugares no sistema.

### <a name="allowing-access-to-powershell-providers"></a>Permitindo acesso aos provedores do PowerShell

Por padrão, nenhum provedor de PowerShell está disponível em sessões JEA. Isso reduz o risco de divulgação de informações confidenciais e definições de configuração ao usuário que está se conectando.

Quando necessário, você pode permitir acesso aos provedores do PowerShell usando o comando `VisibleProviders`. Para obter uma lista completa dos provedores, execute o `Get-PSProvider`.

```powershell
VisibleProviders = 'Registry'
```

Para tarefas simples que exigem acesso ao sistema de arquivos, ao Registro, ao repositório de certificados ou a outros provedores confidenciais, considere escrever uma função personalizada que funcione com o provedor em nome do usuário. As funções, os cmdlets e os programas externos disponíveis em uma sessão JEA não estão sujeitos às mesmas restrições que o JEA. Eles podem acessar qualquer provedor por padrão. Considere também o uso da [unidade de usuário](session-configurations.md#user-drive) quando for necessário copiar arquivos bidirecionalmente em um ponto de extremidade JEA.

### <a name="creating-custom-functions"></a>Criando funções personalizadas

Você pode criar funções personalizadas em um arquivo de capacidade de função para simplificar tarefas complexas para os seus usuários finais. As funções personalizadas também são úteis quando você precisar de lógica de validação avançada para valores de parâmetro de cmdlet. É possível escrever funções simples no campo **FunctionDefinitions**:

```powershell
VisibleFunctions = 'Get-TopProcess'

FunctionDefinitions = @{
    Name = 'Get-TopProcess'

    ScriptBlock = {
        param($Count = 10)

        Get-Process | Sort-Object -Property CPU -Descending |
            Microsoft.PowerShell.Utility\Select-Object -First $Count
    }
}
```

> [!IMPORTANT]
> Não se esqueça de adicionar o nome de suas funções personalizadas no campo **VisibleFunctions** para que elas possam ser executadas pelos usuários JEA.

O corpo (bloco de script) de funções personalizadas é executado no modo de idioma padrão do sistema e não está sujeito às restrições de linguagem do JEA. Isso significa que as funções podem acessar o sistema de arquivos e o Registro e executar comandos que não estavam visíveis no arquivo de capacidade de função. Tome cuidado para evitar a execução de código arbitrário ao usar parâmetros. Evite o redirecionamento da entrada do usuário diretamente para cmdlets como `Invoke-Expression`.

No exemplo acima, observe que o FQMN (nome do módulo totalmente qualificado) `Microsoft.PowerShell.Utility\Select-Object` foi usado em vez da abreviação `Select-Object`.
As funções definidas em arquivos de capacidade de função ainda estão sujeitas ao escopo das sessões JEA, que inclui as funções de proxy que o JEA cria para restringir os comandos existentes.

Por padrão, o `Select-Object` é um cmdlet restrito em todas as sessões JEA que não permite a seleção de propriedades arbitrárias em objetos. Para usar o `Select-Object` irrestrito em funções, é necessário solicitar explicitamente a implementação completa usando o FQMN. Qualquer cmdlet restrito em uma sessão JEA tem as mesmas restrições quando invocado em uma função. Para obter mais informações, confira [about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence).

Se você estiver escrevendo várias funções personalizadas, será mais conveniente colocá-las em um módulo de script do PowerShell. Em seguida, você poderá tornar essas funções visíveis na sessão JEA usando o campo **VisibleFunctions**, assim como faria com módulos internos e de terceiros.

Para que o preenchimento da guia funcione corretamente em sessões JEA, você deve incluir a função interna `tabexpansion2` na lista **VisibleFunctions**.

## <a name="make-the-role-capabilities-available-to-a-configuration"></a>Disponibilize os recursos de função para uma configuração

Antes do PowerShell 6, para o PowerShell encontrar um arquivo de recurso de função, ele deveria estar armazenado em uma pasta **RoleCapabilities** em um módulo do PowerShell. O módulo poderia ser armazenado em qualquer pasta, inclusive na variável de ambiente `$env:PSModulePath`. No entanto, você não deveria colocá-lo em `$env:SystemRoot\System32` ou em uma pasta em que usuários não confiáveis podem modificar os arquivos.

O exemplo a seguir cria um módulo de script do PowerShell chamado **ContosoJEA** no caminho `$env:ProgramFiles` para hospedar o arquivo de recursos de funções.

```powershell
# Create a folder for the module
$modulePath = Join-Path $env:ProgramFiles "WindowsPowerShell\Modules\ContosoJEA"
New-Item -ItemType Directory -Path $modulePath

# Create an empty script module and module manifest.
# At least one file in the module folder must have the same name as the folder itself.
New-Item -ItemType File -Path (Join-Path $modulePath "ContosoJEAFunctions.psm1")
New-ModuleManifest -Path (Join-Path $modulePath "ContosoJEA.psd1") -RootModule "ContosoJEAFunctions.psm1"

# Create the RoleCapabilities folder and copy in the PSRC file
$rcFolder = Join-Path $modulePath "RoleCapabilities"
New-Item -ItemType Directory $rcFolder
Copy-Item -Path .\MyFirstJEARole.psrc -Destination $rcFolder
```

Para obter mais informações sobre módulos do PowerShell, confira [Noções básicas sobre um módulo do PowerShell](/powershell/scripting/developer/windows-powershell).

Após o PowerShell 6, a propriedade **RoleDefinitions** foi adicionada ao arquivo de configuração de sessão. Essa propriedade permite especificar o local de um arquivo de configuração de função para você definir uma função. Veja exemplos em [New-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile).

## <a name="updating-role-capabilities"></a>Atualizando recursos de função

Você pode editar um arquivo de capacidade de função para atualizar as configurações a qualquer momento. Qualquer nova sessão JEA iniciada depois que a capacidade de função foi atualizado refletirá os recursos revisados.

É por isso que é tão importante controlar o acesso à pasta de recursos de função. Apenas administradores altamente confiáveis devem ter a permissão de alterar os arquivos de capacidade de função. Se um usuário não confiável puder alterar os arquivos de capacidade de função, ele poderá, com facilidade, fornecer a si próprio o acesso aos cmdlets que permitem elevar seus privilégios.

Para os administradores que desejam bloquear o acesso às capacidades de função, verifique se a Sistema Local tem acesso de leitura aos arquivos de capacidade de função e aos módulos nesses arquivos.

## <a name="how-role-capabilities-are-merged"></a>Como os recursos de função são mesclados

Os usuários obtêm acesso a todas as capacidades de função correspondentes no [arquivo de configuração de sessão](session-configurations.md) quando entram em uma sessão JEA. O JEA tenta fornecer ao usuário o conjunto mais permissivo de comandos permitido por uma das funções.

### <a name="visiblecmdlets-and-visiblefunctions"></a>VisibleCmdlets e VisibleFunctions

A lógica mais complexa de mesclagem afeta cmdlets e funções, que podem ter seus parâmetros e valores de parâmetro limitados no JEA.

As regras são as seguintes:

1. Se um cmdlet só se tornar visível em uma função, ele ficará visível para o usuário com qualquer restrição de parâmetro aplicável.
2. Se um cmdlet se tornar visível em mais de uma função e cada função tiver as mesmas restrições sobre o cmdlet, o cmdlet ficará visível para o usuário com essas restrições.
3. Se um cmdlet se tornar visível em mais de uma função e cada função permitir um conjunto diferente de parâmetros, o cmdlet e todos os parâmetros definidos em cada função ficarão visíveis ao usuário.
   Se uma função não tiver restrições sobre os parâmetros, todos os parâmetros serão permitidos.
4. Se uma função definir um conjunto ou um padrão de validação para um parâmetro de cmdlet e a outra função permitir o parâmetro, mas não restringir os valores do parâmetro, o conjunto ou o padrão de validação será ignorado.
5. Se um conjunto de validação for definido para o mesmo parâmetro de cmdlet em mais de uma função, todos os valores de todos os conjuntos de validação serão permitidos.
6. Se um padrão de validação for definido para o mesmo parâmetro de cmdlet em mais de uma função, qualquer valor que corresponda a um dos padrões será permitido.
7. Se um conjunto de validação for definido em uma ou mais funções e um padrão de validação for definido em outra função para o mesmo parâmetro de cmdlet, o conjunto de validação será ignorado e a regra (6) se aplica aos padrões de validação restantes.

O exemplo abaixo mostra como as funções são mescladas de acordo com essas regras:

```powershell
# Role A Visible Cmdlets
$roleA = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client' } }
}

# Role B Visible Cmdlets
$roleB = @{
    VisibleCmdlets = @{ Name = 'Get-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidatePattern = 'DNS.*' } },
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Server' } }
}

# Resulting permissions for a user who belongs to both role A and B
# - The constraint in role B for the DisplayName parameter on Get-Service
#   is ignored because of rule #4
# - The ValidateSets for Restart-Service are merged because both roles use
#   ValidateSet on the same parameter per rule #5
$mergedAandB = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client', 'DNS Server' } }
}
```

### <a name="visibleexternalcommands-visiblealiases-visibleproviders-scriptstoprocess"></a>VisibleExternalCommands, VisibleAliases, VisibleProviders e ScriptsToProcess

Todos os outros campos do arquivo de capacidade de função são adicionados a um conjunto cumulativo de comandos externos permitidos, aliases, provedores e scripts de inicialização. Um comando, alias, provedor ou script disponível em uma capacidade de função está disponível para o usuário JEA.

Verifique com cuidado se o conjunto combinado de provedores de uma capacidade de função e cmdlets/funções/comandos de outra não permitem aos usuários o acesso não intencional aos recursos do sistema.
Por exemplo, se uma função permite o cmdlet `Remove-Item` e outra função permite o provedor `FileSystem`, haverá um risco de um usuário JEA excluir arquivos arbitrários no seu computador. Encontre mais informações sobre como identificar as permissões efetivas dos usuários no artigo [Auditoria do JEA](audit-and-report.md).

## <a name="next-steps"></a>Próximas etapas

[Criar um arquivo de configuração de sessão](session-configurations.md)
