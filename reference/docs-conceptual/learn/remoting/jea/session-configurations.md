---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Configurações de Sessão de JEA
ms.openlocfilehash: 650d0d11ef13605847d0822249e29e3491180629
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "70017727"
---
# <a name="jea-session-configurations"></a><span data-ttu-id="0e155-103">Configurações de Sessão de JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-103">JEA Session Configurations</span></span>

<span data-ttu-id="0e155-104">Um ponto de extremidade JEA é registrado em um sistema pela criação e pelo registro de um arquivo de configuração de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e155-104">A JEA endpoint is registered on a system by creating and registering a PowerShell session configuration file.</span></span> <span data-ttu-id="0e155-105">As configurações de sessão definem quem pode usar o ponto de extremidade JEA e a quais funções ele terá acesso.</span><span class="sxs-lookup"><span data-stu-id="0e155-105">Session configurations define who can use the JEA endpoint and which roles they have access to.</span></span> <span data-ttu-id="0e155-106">Elas também definem configurações globais que se aplicam a todos os usuários da sessão JEA.</span><span class="sxs-lookup"><span data-stu-id="0e155-106">They also define global settings that apply to all users of the JEA session.</span></span>

## <a name="create-a-session-configuration-file"></a><span data-ttu-id="0e155-107">Criar um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="0e155-107">Create a session configuration file</span></span>

<span data-ttu-id="0e155-108">Para registrar um ponto de extremidade JEA, é necessário especificar como esse ponto de extremidade é configurado.</span><span class="sxs-lookup"><span data-stu-id="0e155-108">To register a JEA endpoint, you must specify how that endpoint is configured.</span></span> <span data-ttu-id="0e155-109">Há muitas opções a serem consideradas.</span><span class="sxs-lookup"><span data-stu-id="0e155-109">There are many options to consider.</span></span> <span data-ttu-id="0e155-110">As opções mais importantes são:</span><span class="sxs-lookup"><span data-stu-id="0e155-110">The most important options are:</span></span>

- <span data-ttu-id="0e155-111">Quem tem acesso ao ponto de extremidade JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-111">Who has access to the JEA endpoint</span></span>
- <span data-ttu-id="0e155-112">Quais funções são atribuídas a essas pessoas</span><span class="sxs-lookup"><span data-stu-id="0e155-112">Which roles they be assigned</span></span>
- <span data-ttu-id="0e155-113">Qual identidade é usada pelo JEA nos bastidores</span><span class="sxs-lookup"><span data-stu-id="0e155-113">Which identity JEA uses under the covers</span></span>
- <span data-ttu-id="0e155-114">O nome do ponto de extremidade JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-114">The name of the JEA endpoint</span></span>

<span data-ttu-id="0e155-115">Essas opções são definidas em um arquivo de dados do PowerShell com uma extensão `.pssc` conhecida como um arquivo de configuração de sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e155-115">These options are defined in a PowerShell data file with a `.pssc` extension known as a PowerShell session configuration file.</span></span> <span data-ttu-id="0e155-116">O arquivo de configuração de sessão pode ser editado usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="0e155-116">The session configuration file can be edited using any text editor.</span></span>

<span data-ttu-id="0e155-117">Execute o comando a seguir para criar um arquivo de configuração de modelo em branco.</span><span class="sxs-lookup"><span data-stu-id="0e155-117">Run the following command to create a blank template configuration file.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> <span data-ttu-id="0e155-118">Apenas as opções de configuração mais comuns são incluídas no arquivo de modelo por padrão.</span><span class="sxs-lookup"><span data-stu-id="0e155-118">Only the most common configuration options are included in the template file by default.</span></span> <span data-ttu-id="0e155-119">Use a opção `-Full` para incluir todas as configurações aplicáveis no PSSC gerado.</span><span class="sxs-lookup"><span data-stu-id="0e155-119">Use the `-Full` switch to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="0e155-120">O campo `-SessionType RestrictedRemoteServer` indica que a configuração de sessão é usada pelo JEA para gerenciamento seguro.</span><span class="sxs-lookup"><span data-stu-id="0e155-120">The `-SessionType RestrictedRemoteServer` field indicates that the session configuration is used by JEA for secure management.</span></span> <span data-ttu-id="0e155-121">As sessões desse tipo operam no modo **NoLanguage** e só tem acesso aos seguintes comandos padrão (e aliases):</span><span class="sxs-lookup"><span data-stu-id="0e155-121">Sessions of this type operate in **NoLanguage** mode and only have access to the following default commands (and aliases):</span></span>

- <span data-ttu-id="0e155-122">Clear-Host (cls, limpar)</span><span class="sxs-lookup"><span data-stu-id="0e155-122">Clear-Host (cls, clear)</span></span>
- <span data-ttu-id="0e155-123">Exit-PSSession (exsn, sair)</span><span class="sxs-lookup"><span data-stu-id="0e155-123">Exit-PSSession (exsn, exit)</span></span>
- <span data-ttu-id="0e155-124">Get-Command (gcm)</span><span class="sxs-lookup"><span data-stu-id="0e155-124">Get-Command (gcm)</span></span>
- <span data-ttu-id="0e155-125">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="0e155-125">Get-FormatData</span></span>
- <span data-ttu-id="0e155-126">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0e155-126">Get-Help</span></span>
- <span data-ttu-id="0e155-127">Measure-Object (medida)</span><span class="sxs-lookup"><span data-stu-id="0e155-127">Measure-Object (measure)</span></span>
- <span data-ttu-id="0e155-128">Out-Default</span><span class="sxs-lookup"><span data-stu-id="0e155-128">Out-Default</span></span>
- <span data-ttu-id="0e155-129">Select-Object (selecionar)</span><span class="sxs-lookup"><span data-stu-id="0e155-129">Select-Object (select)</span></span>

<span data-ttu-id="0e155-130">Não há nenhum provedor do PowerShell disponível, nem programas externos (executáveis ou scripts).</span><span class="sxs-lookup"><span data-stu-id="0e155-130">No PowerShell providers are available, nor are any external programs (executables or scripts).</span></span>

<span data-ttu-id="0e155-131">Para obter mais informações sobre os modos de linguagem, confira [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).</span><span class="sxs-lookup"><span data-stu-id="0e155-131">For more information about language modes, see [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).</span></span>

### <a name="choose-the-jea-identity"></a><span data-ttu-id="0e155-132">Escolha a identidade JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-132">Choose the JEA identity</span></span>

<span data-ttu-id="0e155-133">Nos bastidores, o JEA precisa de uma identidade (conta) para usar ao executar os comandos do usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="0e155-133">Behind the scenes, JEA needs an identity (account) to use when running a connected user's commands.</span></span>
<span data-ttu-id="0e155-134">Você define qual identidade será usada pelo JEA no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e155-134">You define which identity JEA uses in the session configuration file.</span></span>

#### <a name="local-virtual-account"></a><span data-ttu-id="0e155-135">Conta Virtual Local</span><span class="sxs-lookup"><span data-stu-id="0e155-135">Local Virtual Account</span></span>

<span data-ttu-id="0e155-136">As contas virtuais locais são úteis quando todas as funções definidas para o ponto de extremidade JEA são usadas para gerenciar o computador local e uma conta de administrador local é suficiente para executar os comandos com êxito.</span><span class="sxs-lookup"><span data-stu-id="0e155-136">Local virtual accounts are useful when all roles defined for the JEA endpoint are used to manage the local machine and a local administrator account is sufficient to run the commands successfully.</span></span>
<span data-ttu-id="0e155-137">As contas virtuais são contas temporárias exclusivas para um usuário específico e permanecem ativas apenas durante a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e155-137">Virtual accounts are temporary accounts that are unique to a specific user and only last for the duration of their PowerShell session.</span></span> <span data-ttu-id="0e155-138">Em um servidor membro ou uma estação de trabalho, as contas virtuais pertencem ao grupo **Administradores** do computador local.</span><span class="sxs-lookup"><span data-stu-id="0e155-138">On a member server or workstation, virtual accounts belong to the local computer's **Administrators** group.</span></span> <span data-ttu-id="0e155-139">Em um Controlador de Domínio do Active Directory, as contas virtuais pertencem ao grupo **Administradores do domínio** do domínio.</span><span class="sxs-lookup"><span data-stu-id="0e155-139">On an Active Directory Domain Controller, virtual accounts belong to the domain's **Domain Admins** group.</span></span>

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

<span data-ttu-id="0e155-140">Se as funções definidas pela configuração de sessão não exigirem privilégio administrativo completo, você poderá especificar os grupos de segurança aos quais a conta virtual pertencerá.</span><span class="sxs-lookup"><span data-stu-id="0e155-140">If the roles defined by the session configuration don't require full administrative privilege, you can specify the security groups to which the virtual account will belong.</span></span> <span data-ttu-id="0e155-141">Em um servidor membro ou estação de trabalho, os grupos de segurança especificados devem ser grupos locais e não grupos de um domínio.</span><span class="sxs-lookup"><span data-stu-id="0e155-141">On a member server or workstation, the specified security groups must be local groups, not groups from a domain.</span></span>

<span data-ttu-id="0e155-142">Quando um ou mais grupos de segurança forem especificados, a conta virtual não pertencerá mais ao grupo local de administradores nem ao grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="0e155-142">When one or more security groups are specified, the virtual account isn't assigned to the local or domain administrators group.</span></span>

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

> [!NOTE]
> <span data-ttu-id="0e155-143">As contas virtuais recebem temporariamente o direito de Logon como serviço na política de segurança do servidor local.</span><span class="sxs-lookup"><span data-stu-id="0e155-143">Virtual accounts are temporarily granted the Logon as a service right in the local server security policy.</span></span> <span data-ttu-id="0e155-144">Se um dos VirtualAccountGroups especificados já tiver esse direito na política, a conta virtual individual não será adicionada e removida da política.</span><span class="sxs-lookup"><span data-stu-id="0e155-144">If one of the VirtualAccountGroups specified has already been granted this right in the policy, the individual virtual account will no longer be added and removed from the policy.</span></span> <span data-ttu-id="0e155-145">Isso pode ser útil em cenários como controladores de domínio, em que as revisões da política de segurança do controlador de domínio são auditadas minuciosamente.</span><span class="sxs-lookup"><span data-stu-id="0e155-145">This can be useful in scenarios such as domain controllers where revisions to the domain controller security policy are closely audited.</span></span> <span data-ttu-id="0e155-146">Isso está disponível apenas no Windows Server 2016 com o pacote cumulativo de atualizações de novembro de 2018 ou posterior e no Windows Server 2019 com o pacote cumulativo de atualizações de janeiro de 2019 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0e155-146">This is only available in Windows Server 2016 with the November 2018 or later rollup and Windows Server 2019 with the January 2019 or later rollup.</span></span>

#### <a name="group-managed-service-account"></a><span data-ttu-id="0e155-147">Conta de serviço gerenciado de grupo</span><span class="sxs-lookup"><span data-stu-id="0e155-147">Group-managed service account</span></span>

<span data-ttu-id="0e155-148">Uma GMSA (conta de serviço gerenciado de grupo) é a identidade apropriada a ser usada quando os usuários JEA precisarem acessar os recursos de rede, como compartilhamentos de arquivo e serviços Web.</span><span class="sxs-lookup"><span data-stu-id="0e155-148">A group-managed service account (GMSA) is the appropriate identity to use when JEA users need to access network resources such as file shares and web services.</span></span> <span data-ttu-id="0e155-149">As GMSAs oferecem uma identidade de domínio que é usada para autenticação com recursos em qualquer computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="0e155-149">GMSAs give you a domain identity that is used to authenticate with resources on any machine within the domain.</span></span> <span data-ttu-id="0e155-150">Os direitos fornecidos por uma GMSA são determinados pelos recursos que você está acessando.</span><span class="sxs-lookup"><span data-stu-id="0e155-150">The rights that a GMSA provides are determined by the resources you're accessing.</span></span> <span data-ttu-id="0e155-151">Você não tem direitos de administrador nos computadores ou nos serviços, a menos que o administrador do computador ou de serviços tenha concedido explicitamente esses direitos à GMSA.</span><span class="sxs-lookup"><span data-stu-id="0e155-151">You don't have admin rights on any machines or services unless the machine or service administrator has explicitly granted those rights to the GMSA.</span></span>

```powershell
# Configure JEA sessions to use the GMSA in the local computer's domain
# with the sAMAccountName of 'MyJEAGMSA'
GroupManagedServiceAccount = 'Domain\MyJEAGMSA'
```

<span data-ttu-id="0e155-152">As GMSAs só devem ser usadas quando necessário:</span><span class="sxs-lookup"><span data-stu-id="0e155-152">GMSAs should only be used when necessary:</span></span>

- <span data-ttu-id="0e155-153">É difícil rastrear as ações até um usuário ao usar uma GMSA.</span><span class="sxs-lookup"><span data-stu-id="0e155-153">It's difficult to trace back actions to a user when using a GMSA.</span></span> <span data-ttu-id="0e155-154">Cada usuário compartilha a mesma identidade Executar como.</span><span class="sxs-lookup"><span data-stu-id="0e155-154">Every user shares the same run-as identity.</span></span> <span data-ttu-id="0e155-155">Você precisará examinar as transcrições e os logs de sessão do PowerShell para correlacionar os usuários individuais com suas ações.</span><span class="sxs-lookup"><span data-stu-id="0e155-155">You must review PowerShell session transcripts and logs to correlate individual users with their actions.</span></span>

- <span data-ttu-id="0e155-156">A GMSA pode ter acesso a muitos recursos de rede que o usuário que está se conectando não precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="0e155-156">The GMSA may have access to many network resources that the connecting user doesn't need access to.</span></span> <span data-ttu-id="0e155-157">Sempre tente limitar as permissões efetivas em uma sessão JEA para seguir o princípio de privilégio mínimo.</span><span class="sxs-lookup"><span data-stu-id="0e155-157">Always try to limit effective permissions in a JEA session to follow the principle of least privilege.</span></span>

> [!NOTE]
> <span data-ttu-id="0e155-158">As contas de serviço gerenciado de grupo só estão disponíveis em computadores ingressados no domínio que usam o PowerShell 5.1 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="0e155-158">Group managed service accounts are only available on domain-joined machines using PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="0e155-159">Para obter mais informações sobre como proteger uma sessão JEA, confira o artigo [Considerações sobre segurança](security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="0e155-159">For more information about securing a JEA session, see the [security considerations](security-considerations.md) article.</span></span>

### <a name="session-transcripts"></a><span data-ttu-id="0e155-160">Transcrições de sessão</span><span class="sxs-lookup"><span data-stu-id="0e155-160">Session transcripts</span></span>

<span data-ttu-id="0e155-161">É recomendável configurar um ponto de extremidade JEA para registrar automaticamente as transcrições das sessões dos usuários.</span><span class="sxs-lookup"><span data-stu-id="0e155-161">It's recommended that you configure a JEA endpoint to automatically record transcripts of users' sessions.</span></span> <span data-ttu-id="0e155-162">As transcrições de sessão do PowerShell contêm informações sobre o usuário conectado, a identidade Run As atribuída a ele e os comandos executados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0e155-162">PowerShell session transcripts contain information about the connecting user, the run as identity assigned to them, and the commands run by the user.</span></span> <span data-ttu-id="0e155-163">Elas podem ser úteis para uma equipe de auditoria que precisa entender quem fez uma alteração específica em um sistema.</span><span class="sxs-lookup"><span data-stu-id="0e155-163">They can be useful to an auditing team who needs to understand who made a specific change to a system.</span></span>

<span data-ttu-id="0e155-164">Para configurar a transcrição automática no arquivo de configuração de sessão, forneça um caminho para uma pasta em que as transcrições devem ser armazenadas.</span><span class="sxs-lookup"><span data-stu-id="0e155-164">To configure automatic transcription in the session configuration file, provide a path to a folder where the transcripts should be stored.</span></span>

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

<span data-ttu-id="0e155-165">As transcrições são gravadas na pasta pela conta **Sistema Local**, que exige acesso de leitura e gravação no diretório.</span><span class="sxs-lookup"><span data-stu-id="0e155-165">Transcripts are written to the folder by the **Local System** account, which requires read and write access to the directory.</span></span> <span data-ttu-id="0e155-166">Os usuários padrão não devem ter nenhum acesso à pasta.</span><span class="sxs-lookup"><span data-stu-id="0e155-166">Standard users should have no access to the folder.</span></span> <span data-ttu-id="0e155-167">Limite o número de administradores de segurança que têm acesso para auditar as transcrições.</span><span class="sxs-lookup"><span data-stu-id="0e155-167">Limit the number of security administrators that have access to audit the transcripts.</span></span>

### <a name="user-drive"></a><span data-ttu-id="0e155-168">Unidade de usuário</span><span class="sxs-lookup"><span data-stu-id="0e155-168">User drive</span></span>

<span data-ttu-id="0e155-169">Se os usuários que estão se conectando precisarem copiar arquivos bidirecionalmente no ponto de extremidade JEA, você poderá habilitar a unidade de usuário no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e155-169">If your connecting users need to copy files to or from the JEA endpoint, you can enable the user drive in the session configuration file.</span></span> <span data-ttu-id="0e155-170">A unidade de usuário é um **PSDrive** que é mapeada para uma pasta exclusiva para cada usuário que está se conectando.</span><span class="sxs-lookup"><span data-stu-id="0e155-170">The user drive is a **PSDrive** that is mapped to a unique folder for each connecting user.</span></span> <span data-ttu-id="0e155-171">Essa pasta permite que os usuários copiem arquivos bidirecionalmente no sistema sem fornecer acesso ao sistema de arquivos completo ou expor o provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="0e155-171">This folder allows users to copy files to or from the system without giving them access to the full file system or exposing the FileSystem provider.</span></span> <span data-ttu-id="0e155-172">Os conteúdos da unidade de usuário são persistentes entre as sessões para se adaptar a situações em que a conectividade de rede pode ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="0e155-172">The user drive contents are persistent across sessions to accommodate situations where network connectivity may be interrupted.</span></span>

```powershell
MountUserDrive = $true
```

<span data-ttu-id="0e155-173">Por padrão, a unidade de usuário permite que seja armazenado um máximo de 50 MB de dados por usuário.</span><span class="sxs-lookup"><span data-stu-id="0e155-173">By default, the user drive allows you to store a maximum of 50MB of data per user.</span></span> <span data-ttu-id="0e155-174">Você pode limitar a quantidade de dados que um usuário pode consumir com o campo *UserDriveMaximumSize*.</span><span class="sxs-lookup"><span data-stu-id="0e155-174">You can limit the amount of data a user can consume with the *UserDriveMaximumSize* field.</span></span>

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

<span data-ttu-id="0e155-175">Se você não desejar que os dados da unidade de usuário sejam persistentes, configure uma tarefa agendada no sistema para limpar a pasta automaticamente toda noite.</span><span class="sxs-lookup"><span data-stu-id="0e155-175">If you don't want data in the user drive to be persistent, you can configure a scheduled task on the system to automatically clean up the folder every night.</span></span>

> [!NOTE]
> <span data-ttu-id="0e155-176">A unidade de usuário só está disponível no PowerShell 5.1 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="0e155-176">The user drive is only available in PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="0e155-177">Para obter mais informações sobre PSDrives, confira [Como gerenciar unidades do PowerShell](/powershell/scripting/samples/managing-windows-powershell-drives).</span><span class="sxs-lookup"><span data-stu-id="0e155-177">For more information about PSDrives, see [Managing PowerShell drives](/powershell/scripting/samples/managing-windows-powershell-drives).</span></span>

### <a name="role-definitions"></a><span data-ttu-id="0e155-178">Definições de função</span><span class="sxs-lookup"><span data-stu-id="0e155-178">Role definitions</span></span>

<span data-ttu-id="0e155-179">As definições de função em um arquivo de configuração de sessão definem o mapeamento de **usuários** para as **funções**.</span><span class="sxs-lookup"><span data-stu-id="0e155-179">Role definitions in a session configuration file define the mapping of **users** to **roles**.</span></span> <span data-ttu-id="0e155-180">Cada usuário ou grupo incluído nesse campo recebe permissão no ponto de extremidade JEA quando ele é registrado.</span><span class="sxs-lookup"><span data-stu-id="0e155-180">Every user or group included in this field is granted permission to the JEA endpoint when it's registered.</span></span>
<span data-ttu-id="0e155-181">Cada usuário ou grupo pode ser incluído como uma chave na tabela de hash somente uma vez, mas pode ser atribuído a várias funções.</span><span class="sxs-lookup"><span data-stu-id="0e155-181">Each user or group can be included as a key in the hashtable only once, but can be assigned multiple roles.</span></span> <span data-ttu-id="0e155-182">O nome da capacidade de função deve ser o nome do arquivo de capacidade de função, sem a extensão `.psrc`.</span><span class="sxs-lookup"><span data-stu-id="0e155-182">The name of the role capability should be the name of the role capability file, without the `.psrc` extension.</span></span>

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

<span data-ttu-id="0e155-183">Se um usuário pertencer a mais de um grupo na definição de função, ele obterá acesso às funções de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="0e155-183">If a user belongs to more than one group in the role definition, they get access to the roles of each.</span></span> <span data-ttu-id="0e155-184">Quando duas funções permitirem acesso aos mesmos cmdlets, o conjunto de parâmetros mais permissivo será concedido ao usuário.</span><span class="sxs-lookup"><span data-stu-id="0e155-184">When two roles grant access to the same cmdlets, the most permissive parameter set is granted to the user.</span></span>

<span data-ttu-id="0e155-185">Ao especificar usuários ou grupos locais no campo de definições de função, use o nome do computador, não **localhost** ou curingas.</span><span class="sxs-lookup"><span data-stu-id="0e155-185">When specifying local users or groups in the role definitions field, be sure to use the computer name, not **localhost** or wildcards.</span></span> <span data-ttu-id="0e155-186">Você pode verificar o nome do computador inspecionando a variável `$env:COMPUTERNAME`.</span><span class="sxs-lookup"><span data-stu-id="0e155-186">You can check the computer name by inspecting the `$env:COMPUTERNAME` variable.</span></span>

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a><span data-ttu-id="0e155-187">Ordem de pesquisa de capacidade de função</span><span class="sxs-lookup"><span data-stu-id="0e155-187">Role capability search order</span></span>

<span data-ttu-id="0e155-188">Conforme mostrado no exemplo acima, as capacidades de função são referenciadas pelo nome base do arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="0e155-188">As shown in the example above, role capabilities are referenced by the base name of the role capability file.</span></span> <span data-ttu-id="0e155-189">O nome base de um arquivo é o nome do arquivo sem a extensão.</span><span class="sxs-lookup"><span data-stu-id="0e155-189">The base name of a file is the filename without the extension.</span></span> <span data-ttu-id="0e155-190">Se várias capacidades de função estiverem disponíveis no sistema com o mesmo nome, o PowerShell usará sua ordem de pesquisa implícita para selecionar o arquivo de capacidade de função efetivo.</span><span class="sxs-lookup"><span data-stu-id="0e155-190">If multiple role capabilities are available on the system with the same name, PowerShell uses its implicit search order to select the effective role capability file.</span></span> <span data-ttu-id="0e155-191">O JEA **não** fornece acesso a todos os arquivos de capacidade de função com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="0e155-191">JEA does **not** give access to all role capability files with the same name.</span></span>

<span data-ttu-id="0e155-192">A JEA usa a variável de ambiente do `$env:PSModulePath` para determinar quais caminhos verificar para os arquivos de capacidade da função.</span><span class="sxs-lookup"><span data-stu-id="0e155-192">JEA uses the `$env:PSModulePath` environment variable to determine which paths to scan for role capability files.</span></span> <span data-ttu-id="0e155-193">Em cada um desses caminhos, o JEA procura módulos válidos do PowerShell que contenham uma subpasta "RoleCapabilities".</span><span class="sxs-lookup"><span data-stu-id="0e155-193">Within each of those paths, JEA looks for valid PowerShell modules that contain a "RoleCapabilities" subfolder.</span></span> <span data-ttu-id="0e155-194">Como com a importação de módulos, a JEA prefere as capacidades de função que são fornecidas com o Windows para capacidades de função personalizadas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="0e155-194">As with importing modules, JEA prefers role capabilities that are shipped with Windows to custom role capabilities with the same name.</span></span>

<span data-ttu-id="0e155-195">Para todos os outros conflitos de nomenclatura, a precedência é determinada pela ordem na qual o Windows enumera os arquivos no diretório.</span><span class="sxs-lookup"><span data-stu-id="0e155-195">For all other naming conflicts, precedence is determined by the order in which Windows enumerates the files in the directory.</span></span> <span data-ttu-id="0e155-196">Não há a garantia de que isso será apresentado em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="0e155-196">The order isn't guaranteed to be alphabetical.</span></span> <span data-ttu-id="0e155-197">O primeiro arquivo de capacidade de função encontrado que corresponder ao nome especificado é usado para o usuário que está se conectando.</span><span class="sxs-lookup"><span data-stu-id="0e155-197">The first role capability file found that matches the specified name is used for the connecting user.</span></span> <span data-ttu-id="0e155-198">Como a ordem de pesquisa da capacidade de função não é determinística, é **altamente recomendável** que as capacidades de função tenham nomes de arquivo exclusivos.</span><span class="sxs-lookup"><span data-stu-id="0e155-198">Since the role capability search order isn't deterministic, it's **strongly recommended** that role capabilities have unique filenames.</span></span>

### <a name="conditional-access-rules"></a><span data-ttu-id="0e155-199">Regras de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="0e155-199">Conditional access rules</span></span>

<span data-ttu-id="0e155-200">Todos os usuários e grupos incluídos no campo **RoleDefinitions** recebem automaticamente acesso aos pontos de extremidade JEA.</span><span class="sxs-lookup"><span data-stu-id="0e155-200">All users and groups included in the **RoleDefinitions** field are automatically granted access to JEA endpoints.</span></span> <span data-ttu-id="0e155-201">As regras de acesso condicional permitem que você refine esse acesso e exigem que os usuários façam parte de grupos de segurança adicionais que não afetem as funções atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="0e155-201">Conditional access rules allow you to refine this access and require users to belong to additional security groups that don't impact the roles to which they're assigned.</span></span> <span data-ttu-id="0e155-202">Isso é útil quando você deseja integrar uma solução de gerenciamento de acesso privilegiado just-in-time, uma autenticação de cartão inteligente ou outra solução de autenticação multifator com o JEA.</span><span class="sxs-lookup"><span data-stu-id="0e155-202">This is useful when you want to integrate a just-in-time privileged access management solution, smartcard authentication, or other multifactor authentication solution with JEA.</span></span>

<span data-ttu-id="0e155-203">As regras de acesso condicional são definidas no campo RequiredGroups em um arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e155-203">Conditional access rules are defined in the RequiredGroups field in a session configuration file.</span></span>
<span data-ttu-id="0e155-204">Lá, você pode fornecer uma tabela de hash (opcionalmente aninhada) que usa chaves 'E' e 'Ou' para construir suas regras.</span><span class="sxs-lookup"><span data-stu-id="0e155-204">There, you can provide a hashtable (optionally nested) that uses 'And' and 'Or' keys to construct your rules.</span></span> <span data-ttu-id="0e155-205">Veja alguns exemplos de como utilizar esse campo:</span><span class="sxs-lookup"><span data-stu-id="0e155-205">Here are some examples of how to use this field:</span></span>

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
> <span data-ttu-id="0e155-206">As regras de acesso condicional só estão disponíveis no PowerShell 5.1 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="0e155-206">Conditional access rules are only available in PowerShell 5.1 or newer.</span></span>

### <a name="other-properties"></a><span data-ttu-id="0e155-207">Outras propriedades</span><span class="sxs-lookup"><span data-stu-id="0e155-207">Other properties</span></span>

<span data-ttu-id="0e155-208">Os arquivos de configuração de sessão também podem fazer tudo o que um arquivo de recurso de função pode fazer, mas sem a capacidade de fornecer aos usuários que estão se conectando o acesso a comandos diferentes.</span><span class="sxs-lookup"><span data-stu-id="0e155-208">Session configuration files can also do everything a role capability file can do, just without the ability to give connecting users access to different commands.</span></span> <span data-ttu-id="0e155-209">Se quiser permitir que todos os usuários acessem provedores, funções ou cmdlets específicos, você poderá fazer isso diretamente no arquivo de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e155-209">If you want to allow all users access to specific cmdlets, functions, or providers, you can do so right in the session configuration file.</span></span>
<span data-ttu-id="0e155-210">Para obter uma lista completa das propriedades com suporte no arquivo de configuração de sessão, execute `Get-Help New-PSSessionConfigurationFile -Full`.</span><span class="sxs-lookup"><span data-stu-id="0e155-210">For a full list of supported properties in the session configuration file, run `Get-Help New-PSSessionConfigurationFile -Full`.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="0e155-211">Testando um arquivo de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="0e155-211">Testing a session configuration file</span></span>

<span data-ttu-id="0e155-212">Você pode testar uma configuração de sessão usando o cmdlet [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile).</span><span class="sxs-lookup"><span data-stu-id="0e155-212">You can test a session configuration using the [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile) cmdlet.</span></span> <span data-ttu-id="0e155-213">É recomendável que você teste o arquivo de configuração de sessão caso edite o arquivo `.pssc` manualmente.</span><span class="sxs-lookup"><span data-stu-id="0e155-213">It's recommended that you test your session configuration file if you've manually edited the `.pssc` file.</span></span> <span data-ttu-id="0e155-214">O teste garante que a sintaxe esteja correta.</span><span class="sxs-lookup"><span data-stu-id="0e155-214">Testing ensures the syntax is correct.</span></span> <span data-ttu-id="0e155-215">Se um arquivo de configuração de sessão falhar nesse teste, ele não poderá ser registrado no sistema.</span><span class="sxs-lookup"><span data-stu-id="0e155-215">If a session configuration file fails this test, it can't be registered on the system.</span></span>

## <a name="sample-session-configuration-file"></a><span data-ttu-id="0e155-216">Arquivo de configuração de sessão de exemplo</span><span class="sxs-lookup"><span data-stu-id="0e155-216">Sample session configuration file</span></span>

<span data-ttu-id="0e155-217">O exemplo a seguir mostra como criar e validar uma configuração de sessão para o JEA.</span><span class="sxs-lookup"><span data-stu-id="0e155-217">The following example shows how to create and validate a session configuration for JEA.</span></span> <span data-ttu-id="0e155-218">As definições de função são criadas e armazenadas na variável `$roles` para conveniência e legibilidade.</span><span class="sxs-lookup"><span data-stu-id="0e155-218">The role definitions are created and stored in the `$roles` variable for convenience and readability.</span></span> <span data-ttu-id="0e155-219">Seguir esse procedimento não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="0e155-219">It isn't a requirement to do so.</span></span>

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a><span data-ttu-id="0e155-220">Atualizando arquivos de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="0e155-220">Updating session configuration files</span></span>

<span data-ttu-id="0e155-221">Para alterar as propriedades de uma configuração de sessão JEA, incluindo o mapeamento de usuários às funções, é necessário [cancelar o registro](register-jea.md#unregistering-jea-configurations).</span><span class="sxs-lookup"><span data-stu-id="0e155-221">To change the properties of a JEA session configuration, including the mapping of users to roles, you must [unregister](register-jea.md#unregistering-jea-configurations).</span></span> <span data-ttu-id="0e155-222">Em seguida, [registre novamente](register-jea.md) a configuração de sessão JEA usando um arquivo de configuração de sessão atualizado.</span><span class="sxs-lookup"><span data-stu-id="0e155-222">Then, [re-register](register-jea.md) the JEA session configuration using an updated session configuration file.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0e155-223">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0e155-223">Next steps</span></span>

- [<span data-ttu-id="0e155-224">Registrar uma configuração de JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-224">Register a JEA configuration</span></span>](register-jea.md)
- [<span data-ttu-id="0e155-225">Funções de autor de JEA</span><span class="sxs-lookup"><span data-stu-id="0e155-225">Author JEA roles</span></span>](role-capabilities.md)
