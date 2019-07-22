---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Configurações de Sessão de JEA
ms.openlocfilehash: 650d0d11ef13605847d0822249e29e3491180629
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726554"
---
# <a name="jea-session-configurations"></a>Configurações de Sessão de JEA

Um ponto de extremidade JEA é registrado em um sistema pela criação e pelo registro de um arquivo de configuração de sessão do PowerShell. As configurações de sessão definem quem pode usar o ponto de extremidade JEA e a quais funções ele terá acesso. Elas também definem configurações globais que se aplicam a todos os usuários da sessão JEA.

## <a name="create-a-session-configuration-file"></a>Criar um arquivo de configuração de sessão

Para registrar um ponto de extremidade JEA, é necessário especificar como esse ponto de extremidade é configurado. Há muitas opções a serem consideradas. As opções mais importantes são:

- Quem tem acesso ao ponto de extremidade JEA
- Quais funções são atribuídas a essas pessoas
- Qual identidade é usada pelo JEA nos bastidores
- O nome do ponto de extremidade JEA

Essas opções são definidas em um arquivo de dados do PowerShell com uma extensão `.pssc` conhecida como um arquivo de configuração de sessão do PowerShell. O arquivo de configuração de sessão pode ser editado usando qualquer editor de texto.

Execute o comando a seguir para criar um arquivo de configuração de modelo em branco.

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> Apenas as opções de configuração mais comuns são incluídas no arquivo de modelo por padrão. Use a opção `-Full` para incluir todas as configurações aplicáveis no PSSC gerado.

O campo `-SessionType RestrictedRemoteServer` indica que a configuração de sessão é usada pelo JEA para gerenciamento seguro. As sessões desse tipo operam no modo **NoLanguage** e só tem acesso aos seguintes comandos padrão (e aliases):

- Clear-Host (cls, limpar)
- Exit-PSSession (exsn, sair)
- Get-Command (gcm)
- Get-FormatData
- Get-Help
- Measure-Object (medida)
- Out-Default
- Select-Object (selecionar)

Não há nenhum provedor do PowerShell disponível, nem programas externos (executáveis ou scripts).

Para obter mais informações sobre os modos de linguagem, confira [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).

### <a name="choose-the-jea-identity"></a>Escolha a identidade JEA

Nos bastidores, o JEA precisa de uma identidade (conta) para usar ao executar os comandos do usuário conectado.
Você define qual identidade será usada pelo JEA no arquivo de configuração de sessão.

#### <a name="local-virtual-account"></a>Conta Virtual Local

As contas virtuais locais são úteis quando todas as funções definidas para o ponto de extremidade JEA são usadas para gerenciar o computador local e uma conta de administrador local é suficiente para executar os comandos com êxito.
As contas virtuais são contas temporárias exclusivas para um usuário específico e permanecem ativas apenas durante a sessão do PowerShell. Em um servidor membro ou uma estação de trabalho, as contas virtuais pertencem ao grupo **Administradores** do computador local. Em um Controlador de Domínio do Active Directory, as contas virtuais pertencem ao grupo **Administradores do domínio** do domínio.

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

Se as funções definidas pela configuração de sessão não exigirem privilégio administrativo completo, você poderá especificar os grupos de segurança aos quais a conta virtual pertencerá. Em um servidor membro ou estação de trabalho, os grupos de segurança especificados devem ser grupos locais e não grupos de um domínio.

Quando um ou mais grupos de segurança forem especificados, a conta virtual não pertencerá mais ao grupo local de administradores nem ao grupo de administradores de domínio.

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

> [!NOTE]
> As contas virtuais recebem temporariamente o direito de Logon como serviço na política de segurança do servidor local. Se um dos VirtualAccountGroups especificados já tiver esse direito na política, a conta virtual individual não será adicionada e removida da política. Isso pode ser útil em cenários como controladores de domínio, em que as revisões da política de segurança do controlador de domínio são auditadas minuciosamente. Isso está disponível apenas no Windows Server 2016 com o pacote cumulativo de atualizações de novembro de 2018 ou posterior e no Windows Server 2019 com o pacote cumulativo de atualizações de janeiro de 2019 ou posterior.

#### <a name="group-managed-service-account"></a>Conta de serviço gerenciado de grupo

Uma GMSA (conta de serviço gerenciado de grupo) é a identidade apropriada a ser usada quando os usuários JEA precisarem acessar os recursos de rede, como compartilhamentos de arquivo e serviços Web. As GMSAs oferecem uma identidade de domínio que é usada para autenticação com recursos em qualquer computador no domínio. Os direitos fornecidos por uma GMSA são determinados pelos recursos que você está acessando. Você não tem direitos de administrador nos computadores ou nos serviços, a menos que o administrador do computador ou de serviços tenha concedido explicitamente esses direitos à GMSA.

```powershell
# Configure JEA sessions to use the GMSA in the local computer's domain
# with the sAMAccountName of 'MyJEAGMSA'
GroupManagedServiceAccount = 'Domain\MyJEAGMSA'
```

As GMSAs só devem ser usadas quando necessário:

- É difícil rastrear as ações até um usuário ao usar uma GMSA. Cada usuário compartilha a mesma identidade Executar como. Você precisará examinar as transcrições e os logs de sessão do PowerShell para correlacionar os usuários individuais com suas ações.

- A GMSA pode ter acesso a muitos recursos de rede que o usuário que está se conectando não precisa acessar. Sempre tente limitar as permissões efetivas em uma sessão JEA para seguir o princípio de privilégio mínimo.

> [!NOTE]
> As contas de serviço gerenciado de grupo só estão disponíveis em computadores ingressados no domínio que usam o PowerShell 5.1 ou mais recente.

Para obter mais informações sobre como proteger uma sessão JEA, confira o artigo [Considerações sobre segurança](security-considerations.md).

### <a name="session-transcripts"></a>Transcrições de sessão

É recomendável configurar um ponto de extremidade JEA para registrar automaticamente as transcrições das sessões dos usuários. As transcrições de sessão do PowerShell contêm informações sobre o usuário conectado, a identidade Run As atribuída a ele e os comandos executados pelo usuário. Elas podem ser úteis para uma equipe de auditoria que precisa entender quem fez uma alteração específica em um sistema.

Para configurar a transcrição automática no arquivo de configuração de sessão, forneça um caminho para uma pasta em que as transcrições devem ser armazenadas.

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

As transcrições são gravadas na pasta pela conta **Sistema Local**, que exige acesso de leitura e gravação no diretório. Os usuários padrão não devem ter nenhum acesso à pasta. Limite o número de administradores de segurança que têm acesso para auditar as transcrições.

### <a name="user-drive"></a>Unidade de usuário

Se os usuários que estão se conectando precisarem copiar arquivos bidirecionalmente no ponto de extremidade JEA, você poderá habilitar a unidade de usuário no arquivo de configuração de sessão. A unidade de usuário é um **PSDrive** que é mapeada para uma pasta exclusiva para cada usuário que está se conectando. Essa pasta permite que os usuários copiem arquivos bidirecionalmente no sistema sem fornecer acesso ao sistema de arquivos completo ou expor o provedor FileSystem. Os conteúdos da unidade de usuário são persistentes entre as sessões para se adaptar a situações em que a conectividade de rede pode ser interrompida.

```powershell
MountUserDrive = $true
```

Por padrão, a unidade de usuário permite que seja armazenado um máximo de 50 MB de dados por usuário. Você pode limitar a quantidade de dados que um usuário pode consumir com o campo *UserDriveMaximumSize*.

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

Se você não desejar que os dados da unidade de usuário sejam persistentes, configure uma tarefa agendada no sistema para limpar a pasta automaticamente toda noite.

> [!NOTE]
> A unidade de usuário só está disponível no PowerShell 5.1 ou mais recente.

Para obter mais informações sobre PSDrives, confira [Como gerenciar unidades do PowerShell](/powershell/scripting/samples/managing-windows-powershell-drives).

### <a name="role-definitions"></a>Definições de função

As definições de função em um arquivo de configuração de sessão definem o mapeamento de **usuários** para as **funções**. Cada usuário ou grupo incluído nesse campo recebe permissão no ponto de extremidade JEA quando ele é registrado.
Cada usuário ou grupo pode ser incluído como uma chave na tabela de hash somente uma vez, mas pode ser atribuído a várias funções. O nome da capacidade de função deve ser o nome do arquivo de capacidade de função, sem a extensão `.psrc`.

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

Se um usuário pertencer a mais de um grupo na definição de função, ele obterá acesso às funções de cada grupo. Quando duas funções permitirem acesso aos mesmos cmdlets, o conjunto de parâmetros mais permissivo será concedido ao usuário.

Ao especificar usuários ou grupos locais no campo de definições de função, use o nome do computador, não **localhost** ou curingas. Você pode verificar o nome do computador inspecionando a variável `$env:COMPUTERNAME`.

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a>Ordem de pesquisa de capacidade de função

Conforme mostrado no exemplo acima, as capacidades de função são referenciadas pelo nome base do arquivo de capacidade de função. O nome base de um arquivo é o nome do arquivo sem a extensão. Se várias capacidades de função estiverem disponíveis no sistema com o mesmo nome, o PowerShell usará sua ordem de pesquisa implícita para selecionar o arquivo de capacidade de função efetivo. O JEA **não** fornece acesso a todos os arquivos de capacidade de função com o mesmo nome.

A JEA usa a variável de ambiente do `$env:PSModulePath` para determinar quais caminhos verificar para os arquivos de capacidade da função. Em cada um desses caminhos, o JEA procura módulos válidos do PowerShell que contenham uma subpasta "RoleCapabilities". Como com a importação de módulos, a JEA prefere as capacidades de função que são fornecidas com o Windows para capacidades de função personalizadas com o mesmo nome.

Para todos os outros conflitos de nomenclatura, a precedência é determinada pela ordem na qual o Windows enumera os arquivos no diretório. Não há a garantia de que isso será apresentado em ordem alfabética. O primeiro arquivo de capacidade de função encontrado que corresponder ao nome especificado é usado para o usuário que está se conectando. Como a ordem de pesquisa da capacidade de função não é determinística, é **altamente recomendável** que as capacidades de função tenham nomes de arquivo exclusivos.

### <a name="conditional-access-rules"></a>Regras de acesso condicional

Todos os usuários e grupos incluídos no campo **RoleDefinitions** recebem automaticamente acesso aos pontos de extremidade JEA. As regras de acesso condicional permitem que você refine esse acesso e exigem que os usuários façam parte de grupos de segurança adicionais que não afetem as funções atribuídas a eles. Isso é útil quando você deseja integrar uma solução de gerenciamento de acesso privilegiado just-in-time, uma autenticação de cartão inteligente ou outra solução de autenticação multifator com o JEA.

As regras de acesso condicional são definidas no campo RequiredGroups em um arquivo de configuração de sessão.
Lá, você pode fornecer uma tabela de hash (opcionalmente aninhada) que usa chaves 'E' e 'Ou' para construir suas regras. Veja alguns exemplos de como utilizar esse campo:

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

> [!NOTE]
> As regras de acesso condicional só estão disponíveis no PowerShell 5.1 ou mais recente.

### <a name="other-properties"></a>Outras propriedades

Os arquivos de configuração de sessão também podem fazer tudo o que um arquivo de recurso de função pode fazer, mas sem a capacidade de fornecer aos usuários que estão se conectando o acesso a comandos diferentes. Se quiser permitir que todos os usuários acessem provedores, funções ou cmdlets específicos, você poderá fazer isso diretamente no arquivo de configuração de sessão.
Para obter uma lista completa das propriedades com suporte no arquivo de configuração de sessão, execute `Get-Help New-PSSessionConfigurationFile -Full`.

## <a name="testing-a-session-configuration-file"></a>Testando um arquivo de configuração de sessão

Você pode testar uma configuração de sessão usando o cmdlet [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile). É recomendável que você teste o arquivo de configuração de sessão caso edite o arquivo `.pssc` manualmente. O teste garante que a sintaxe esteja correta. Se um arquivo de configuração de sessão falhar nesse teste, ele não poderá ser registrado no sistema.

## <a name="sample-session-configuration-file"></a>Arquivo de configuração de sessão de exemplo

O exemplo a seguir mostra como criar e validar uma configuração de sessão para o JEA. As definições de função são criadas e armazenadas na variável `$roles` para conveniência e legibilidade. Seguir esse procedimento não é um requisito.

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a>Atualizando arquivos de configuração de sessão

Para alterar as propriedades de uma configuração de sessão JEA, incluindo o mapeamento de usuários às funções, é necessário [cancelar o registro](register-jea.md#unregistering-jea-configurations). Em seguida, [registre novamente](register-jea.md) a configuração de sessão JEA usando um arquivo de configuração de sessão atualizado.

## <a name="next-steps"></a>Próximas etapas

- [Registrar uma configuração de JEA](register-jea.md)
- [Funções de autor de JEA](role-capabilities.md)
