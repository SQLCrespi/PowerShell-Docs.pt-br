---
ms.date: 05/14/2020
keywords: powershell, cmdlet
title: Dando o segundo salto na Comunicação Remota do PowerShell
description: Este artigo explica os vários métodos para configurar a autenticação de segundo salto para comunicação remota do PowerShell, incluindo as implicações e as recomendações de segurança.
ms.openlocfilehash: 905b27b4e6c612249c945a741bbe0d2ba9ae28aa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501364"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="157ac-104">Dando o segundo salto na Comunicação Remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="157ac-104">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="157ac-105">O "problema do segundo salto" refere-se a uma situação semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="157ac-105">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="157ac-106">Você está conectado no _ServerA_.</span><span class="sxs-lookup"><span data-stu-id="157ac-106">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="157ac-107">No _ServerA_, você inicia uma sessão remota do PowerShell para se conectar ao _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="157ac-107">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="157ac-108">Um comando executado no _ServerB_ por meio de sua sessão de Conexão Remota do PowerShell tenta acessar um recurso no _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="157ac-108">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="157ac-109">O acesso ao recurso no _ServerC_ é negado, pois as credenciais usadas para criar a sessão de Comunicação Remota do PowerShell não foram passadas do _ServerB_ para o _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="157ac-109">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="157ac-110">Há várias maneiras de resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="157ac-110">There are several ways to address this problem.</span></span> <span data-ttu-id="157ac-111">A tabela a seguir lista os métodos por ordem de preferência.</span><span class="sxs-lookup"><span data-stu-id="157ac-111">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="157ac-112">Configuração</span><span class="sxs-lookup"><span data-stu-id="157ac-112">Configuration</span></span>                       |                                  <span data-ttu-id="157ac-113">Observação</span><span class="sxs-lookup"><span data-stu-id="157ac-113">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="157ac-114">CredSSP</span><span class="sxs-lookup"><span data-stu-id="157ac-114">CredSSP</span></span>                                                  | <span data-ttu-id="157ac-115">Equilibra a facilidade de uso e a segurança</span><span class="sxs-lookup"><span data-stu-id="157ac-115">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="157ac-116">Delegação restrita de Kerberos com base em recursos</span><span class="sxs-lookup"><span data-stu-id="157ac-116">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="157ac-117">Maior segurança com configuração mais simples</span><span class="sxs-lookup"><span data-stu-id="157ac-117">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="157ac-118">Delegação restrita de Kerberos</span><span class="sxs-lookup"><span data-stu-id="157ac-118">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="157ac-119">Alta segurança, mas requer administrador de domínio</span><span class="sxs-lookup"><span data-stu-id="157ac-119">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="157ac-120">Delegação Kerberos (irrestrita)</span><span class="sxs-lookup"><span data-stu-id="157ac-120">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="157ac-121">Não recomendado</span><span class="sxs-lookup"><span data-stu-id="157ac-121">Not recommended</span></span>                                                        |
| <span data-ttu-id="157ac-122">JEA (Administração Just Enough)</span><span class="sxs-lookup"><span data-stu-id="157ac-122">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="157ac-123">Pode fornecer a melhor segurança, mas requer configuração mais detalhada</span><span class="sxs-lookup"><span data-stu-id="157ac-123">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="157ac-124">PSSessionConfiguration usando RunAs</span><span class="sxs-lookup"><span data-stu-id="157ac-124">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="157ac-125">Mais simples de configurar, mas requer gerenciamento de credenciais</span><span class="sxs-lookup"><span data-stu-id="157ac-125">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="157ac-126">Passar credenciais dentro de um bloco de script `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="157ac-126">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="157ac-127">Mais simples de usar, mas é necessário fornecer credenciais</span><span class="sxs-lookup"><span data-stu-id="157ac-127">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="157ac-128">CredSSP</span><span class="sxs-lookup"><span data-stu-id="157ac-128">CredSSP</span></span>

<span data-ttu-id="157ac-129">Você pode usar o [CredSSP (Credential Security Support Provider)][credssp] para autenticação.</span><span class="sxs-lookup"><span data-stu-id="157ac-129">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="157ac-130">O CredSSP armazena em cache as credenciais no servidor remoto (_ServerB_), portanto, usá-lo abre para ataques de roubo de credenciais.</span><span class="sxs-lookup"><span data-stu-id="157ac-130">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="157ac-131">Se o computador remoto estiver comprometido, o invasor terá acesso às credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="157ac-131">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="157ac-132">O CredSSP é desabilitado por padrão nos computadores cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="157ac-132">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="157ac-133">Você só deve habilitar o CredSSP nos ambientes mais confiáveis.</span><span class="sxs-lookup"><span data-stu-id="157ac-133">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="157ac-134">Por exemplo, um administrador de domínio que se conecta a um controlador de domínio porque o controlador de domínio é altamente confiável.</span><span class="sxs-lookup"><span data-stu-id="157ac-134">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="157ac-135">Para saber mais sobre questões de segurança ao usar o CredSSP para comunicação remota do PowerShell, confira [Sabotagem acidental: cuidado com o CredSSP][beware].</span><span class="sxs-lookup"><span data-stu-id="157ac-135">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="157ac-136">Para obter mais informações sobre ataques de roubo de credenciais, consulte [Mitigando ataques PtH (Pass-the-Hash) e outro roubo de credenciais][pth].</span><span class="sxs-lookup"><span data-stu-id="157ac-136">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="157ac-137">Para obter um exemplo de como habilitar e usar o CredSSP para comunicação remota do PowerShell, confira [Habilitar a funcionalidade de "Segundo Salto" do PowerShell com o CredSSP][credssp-psblog].</span><span class="sxs-lookup"><span data-stu-id="157ac-137">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="157ac-138">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-138">**Pros**</span></span>

- <span data-ttu-id="157ac-139">Ele funciona para todos os servidores com o Windows Server 2008 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="157ac-139">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="157ac-140">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-140">**Cons**</span></span>

- <span data-ttu-id="157ac-141">Tem vulnerabilidades de segurança.</span><span class="sxs-lookup"><span data-stu-id="157ac-141">Has security vulnerabilities.</span></span>
- <span data-ttu-id="157ac-142">Requer a configuração de funções de cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="157ac-142">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="157ac-143">Não funciona com o grupo de usuários protegidos.</span><span class="sxs-lookup"><span data-stu-id="157ac-143">Does not work with the Protected Users group.</span></span> <span data-ttu-id="157ac-144">Para obter mais informações, confira [Grupo de segurança de usuários protegidos][protected-users].</span><span class="sxs-lookup"><span data-stu-id="157ac-144">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="157ac-145">Delegação restrita de Kerberos</span><span class="sxs-lookup"><span data-stu-id="157ac-145">Kerberos constrained delegation</span></span>

<span data-ttu-id="157ac-146">Você pode usar a delegação restrita herdada (não baseada em recursos) para realizar o segundo salto.</span><span class="sxs-lookup"><span data-stu-id="157ac-146">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="157ac-147">Configure a delegação restrita de Kerberos com a opção "Usar qualquer protocolo de autenticação" para permitir a transição de protocolo.</span><span class="sxs-lookup"><span data-stu-id="157ac-147">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="157ac-148">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-148">**Pros**</span></span>

- <span data-ttu-id="157ac-149">Não exige nenhuma codificação especial</span><span class="sxs-lookup"><span data-stu-id="157ac-149">Requires no special coding</span></span>
- <span data-ttu-id="157ac-150">As credenciais não são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-150">Credentials are not stored.</span></span>

<span data-ttu-id="157ac-151">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-151">**Cons**</span></span>

- <span data-ttu-id="157ac-152">Não oferece suporte ao segundo salto para o WinRM.</span><span class="sxs-lookup"><span data-stu-id="157ac-152">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="157ac-153">Requer acesso de administrador de domínio para configuração.</span><span class="sxs-lookup"><span data-stu-id="157ac-153">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="157ac-154">Deve ser configurada no objeto do Active Directory do servidor remoto (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="157ac-154">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="157ac-155">Limitado a um domínio.</span><span class="sxs-lookup"><span data-stu-id="157ac-155">Limited to one domain.</span></span> <span data-ttu-id="157ac-156">Não pode cruzar domínios ou florestas.</span><span class="sxs-lookup"><span data-stu-id="157ac-156">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="157ac-157">Requer direitos para atualizar objetos e SPNs (Nomes de Entidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="157ac-157">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="157ac-158">O _ServerB_ pode adquirir um tíquete Kerberos para o _ServerC_ em nome do usuário sem que este intervenha.</span><span class="sxs-lookup"><span data-stu-id="157ac-158">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="157ac-159">As contas do Active Directory que tiverem a propriedade **A conta é confidencial e não pode ser delegada** definida não poderão ser delegadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-159">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="157ac-160">Para saber mais, confira [Foco de Segurança: analisar "Conta é confidencial e não pode ser delegada" para Contas Privilegiadas][blog] e [Configurações e Ferramentas da Autenticação Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="157ac-160">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="157ac-161">Delegação restrita de Kerberos com base em recursos</span><span class="sxs-lookup"><span data-stu-id="157ac-161">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="157ac-162">A utilização da delegação restrita de Kerberos baseada em recursos (introduzida no Windows Server 2012) permite que seja configurada a delegação de credencial no objeto do servidor no qual os recursos residem.</span><span class="sxs-lookup"><span data-stu-id="157ac-162">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="157ac-163">No cenário do segundo salto descrito acima, você configura o _ServerC_ para especificar de onde ele aceita credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-163">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="157ac-164">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-164">**Pros**</span></span>

- <span data-ttu-id="157ac-165">As credenciais não são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-165">Credentials are not stored.</span></span>
- <span data-ttu-id="157ac-166">Configurada usando cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="157ac-166">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="157ac-167">Nenhuma codificação especial é necessária.</span><span class="sxs-lookup"><span data-stu-id="157ac-167">No special coding required.</span></span>
- <span data-ttu-id="157ac-168">Não requer acesso de administrador de domínio para configuração.</span><span class="sxs-lookup"><span data-stu-id="157ac-168">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="157ac-169">Funciona entre domínios e florestas.</span><span class="sxs-lookup"><span data-stu-id="157ac-169">Works across domains and forests.</span></span>

<span data-ttu-id="157ac-170">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-170">**Cons**</span></span>

- <span data-ttu-id="157ac-171">Requer o Windows Server 2012 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="157ac-171">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="157ac-172">Não oferece suporte ao segundo salto para o WinRM.</span><span class="sxs-lookup"><span data-stu-id="157ac-172">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="157ac-173">Requer direitos para atualizar objetos e SPNs (Nomes de Entidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="157ac-173">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="157ac-174">As contas do Active Directory que tiverem a propriedade **A conta é confidencial e não pode ser delegada** definida não poderão ser delegadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-174">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="157ac-175">Para saber mais, confira [Foco de Segurança: analisar "Conta é confidencial e não pode ser delegada" para Contas Privilegiadas][blog] e [Configurações e Ferramentas da Autenticação Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="157ac-175">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="157ac-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="157ac-176">Example</span></span>

<span data-ttu-id="157ac-177">Vejamos um exemplo do PowerShell que configura a delegação restrita baseada em recursos no _ServerC_ para permitir credenciais delegadas de um _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="157ac-177">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="157ac-178">Este exemplo pressupõe que todos os servidores estão executando o Windows Server 2012 ou posterior, e que há pelo menos um controlador de domínio do Windows Server 2012 em cada domínio aos quais os servidores pertencem.</span><span class="sxs-lookup"><span data-stu-id="157ac-178">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="157ac-179">Antes de configurar a delegação restrita, você deve adicionar o recurso `RSAT-AD-PowerShell` para instalar o módulo Active Directory PowerShell e, em seguida, importar esse módulo na sua sessão:</span><span class="sxs-lookup"><span data-stu-id="157ac-179">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="157ac-180">Vários cmdlets disponíveis agora têm um parâmetro **PrincipalsAllowedToDelegateToAccount**:</span><span class="sxs-lookup"><span data-stu-id="157ac-180">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="157ac-181">O parâmetro **PrincipalsAllowedToDelegateToAccount** define o atributo do objeto do Active Directory **msDS-AllowedToActOnBehalfOfOtherIdentity**, que contém uma ACL (lista de controle de acesso) que especifica quais contas têm permissão para delegar credenciais à conta associada (em nosso exemplo, será a conta da máquina do _ServerA_).</span><span class="sxs-lookup"><span data-stu-id="157ac-181">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="157ac-182">Agora vamos configurar as variáveis que usaremos para representar os servidores:</span><span class="sxs-lookup"><span data-stu-id="157ac-182">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="157ac-183">O WinRM (e, portanto, comunicação remota do PowerShell) é executado como a conta de computador por padrão.</span><span class="sxs-lookup"><span data-stu-id="157ac-183">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="157ac-184">Você pode ver isso examinando a propriedade **StartName** do serviço `winrm`:</span><span class="sxs-lookup"><span data-stu-id="157ac-184">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="157ac-185">Para que o _ServerC_ permita a delegação de uma sessão de comunicação remota do PowerShell no _ServerB_, é necessário definir o parâmetro **PrincipalsAllowedToDelegateToAccount** no _ServerC_ como o objeto de computador do _ServerB_:</span><span class="sxs-lookup"><span data-stu-id="157ac-185">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="157ac-186">O [KDC (Centro de distribuição de chaves)](/windows/win32/secauthn/key-distribution-center) Kerberos armazena em cache as tentativas de acesso negado (cache negativo) por 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="157ac-186">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="157ac-187">Se _ServerB_ tentou acessar anteriormente o _ServerC_, será necessário limpar o cache no _ServerB_ invocando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="157ac-187">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="157ac-188">Você também pode reiniciar o computador ou aguardar pelo menos 15 minutos para limpar o cache.</span><span class="sxs-lookup"><span data-stu-id="157ac-188">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="157ac-189">Depois de limpar o cache, é possível executar com êxito o código do _ServerA_ por meio do _ServerB_ no _ServerC_:</span><span class="sxs-lookup"><span data-stu-id="157ac-189">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

<span data-ttu-id="157ac-190">Neste exemplo, a variável `$using` é usada para tornar a variável `$ServerC` visível ao _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="157ac-190">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="157ac-191">Para obter mais informações sobre a variável `$using`, consulte [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span><span class="sxs-lookup"><span data-stu-id="157ac-191">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="157ac-192">Para permitir que vários servidores deleguem credenciais ao _ServerC_, defina o valor do parâmetro **PrincipalsAllowedToDelegateToAccount** no _ServerC_ em uma matriz:</span><span class="sxs-lookup"><span data-stu-id="157ac-192">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

<span data-ttu-id="157ac-193">Se você quiser realizar o segundo salto entre domínios, adicione o FQDN (nome de domínio totalmente qualificado) do controlador de domínio do domínio ao qual o _ServerB_ pertence:</span><span class="sxs-lookup"><span data-stu-id="157ac-193">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="157ac-194">Para remover a capacidade de delegar credenciais para o ServerC, defina o valor do parâmetro **PrincipalsAllowedToDelegateToAccount** no _ServerC_ como `$null`:</span><span class="sxs-lookup"><span data-stu-id="157ac-194">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="157ac-195">Informações sobre delegação restrita de Kerberos baseada em recursos</span><span class="sxs-lookup"><span data-stu-id="157ac-195">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="157ac-196">[Novidades na Autenticação Kerberos][whats-new]</span><span class="sxs-lookup"><span data-stu-id="157ac-196">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="157ac-197">[Como o Windows Server 2012 Ameniza a Dificuldade da Delegação Restrita de Kerberos, Parte 1][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="157ac-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="157ac-198">[Como o Windows Server 2012 Ameniza a Dificuldade da Delegação Restrita de Kerberos, Parte 2][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="157ac-198">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="157ac-199">[Noções básicas sobre a Delegação Restrita de Kerberos para Implantações de Proxy de Aplicativo do Azure Active Directory com a Autenticação Integrada do Windows][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="157ac-199">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="157ac-200">[[MS-ADA2]: Atributos de esquema do Active Directory, atributo M2.210 msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="157ac-200">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="157ac-201">[[MS-SFU]: Extensões de protocolo Kerberos: Serviço para usuário e protocolo de delegação restrita 1.3.2 S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="157ac-201">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="157ac-202">[Administração remota sem a delegação restrita usando PrincipalsAllowedToDelegateToAccount][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="157ac-202">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="157ac-203">Delegação Kerberos (irrestrita)</span><span class="sxs-lookup"><span data-stu-id="157ac-203">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="157ac-204">Você pode também pode usar a delegação Kerberos irrestrita para realizar o segundo salto.</span><span class="sxs-lookup"><span data-stu-id="157ac-204">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="157ac-205">Como todos os cenários do Kerberos, as credenciais não são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-205">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="157ac-206">Este método não dá suporte ao segundo salto para o WinRM.</span><span class="sxs-lookup"><span data-stu-id="157ac-206">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="157ac-207">Ele não fornece nenhum controle sobre onde as credenciais delegadas são usadas.</span><span class="sxs-lookup"><span data-stu-id="157ac-207">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="157ac-208">É menos seguro que o CredSSP.</span><span class="sxs-lookup"><span data-stu-id="157ac-208">It is less secure than CredSSP.</span></span> <span data-ttu-id="157ac-209">E só deve ser usado em cenários de teste.</span><span class="sxs-lookup"><span data-stu-id="157ac-209">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="157ac-210">JEA (Administração Just Enough)</span><span class="sxs-lookup"><span data-stu-id="157ac-210">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="157ac-211">O JEA permite restringir os comandos que um administrador pode executar durante uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="157ac-211">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="157ac-212">Pode ser usado para resolver o problema do segundo salto.</span><span class="sxs-lookup"><span data-stu-id="157ac-212">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="157ac-213">Para obter informações sobre o JEA, consulte [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span><span class="sxs-lookup"><span data-stu-id="157ac-213">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="157ac-214">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-214">**Pros**</span></span>

- <span data-ttu-id="157ac-215">Não necessita manutenção de senha ao usar uma conta virtual.</span><span class="sxs-lookup"><span data-stu-id="157ac-215">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="157ac-216">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-216">**Cons**</span></span>

- <span data-ttu-id="157ac-217">Requer o WMF 5.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="157ac-217">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="157ac-218">Requer a configuração em cada servidor intermediário (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="157ac-218">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="157ac-219">PSSessionConfiguration usando RunAs</span><span class="sxs-lookup"><span data-stu-id="157ac-219">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="157ac-220">Você pode criar uma configuração de sessão no _ServerB_ e definir o parâmetro **RunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="157ac-220">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="157ac-221">Para obter mais informações sobre como usar **PSSessionConfiguration** e **RunAs** para solucionar o problema do segundo salto, confira [Outra solução para a comunicação remota do PowerShell com vários saltos][pssessionconfig].</span><span class="sxs-lookup"><span data-stu-id="157ac-221">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="157ac-222">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-222">**Pros**</span></span>

- <span data-ttu-id="157ac-223">Funciona com qualquer servidor com o WMF 3.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="157ac-223">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="157ac-224">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-224">**Cons**</span></span>

- <span data-ttu-id="157ac-225">Requer a configuração de **PSSessionConfiguration** e de **RunAs** em cada servidor intermediário (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="157ac-225">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="157ac-226">Requer manutenção de senha ao usar uma conta **RunAs** de domínio</span><span class="sxs-lookup"><span data-stu-id="157ac-226">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="157ac-227">Passar credenciais dentro de um bloco de script Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="157ac-227">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="157ac-228">É possível passar credenciais dentro do parâmetro **ScriptBlock** de uma chamada do cmdlet [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="157ac-228">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="157ac-229">**Prós**</span><span class="sxs-lookup"><span data-stu-id="157ac-229">**Pros**</span></span>

- <span data-ttu-id="157ac-230">Não requer configuração especial do servidor.</span><span class="sxs-lookup"><span data-stu-id="157ac-230">Does not require special server configuration.</span></span>
- <span data-ttu-id="157ac-231">Funciona em qualquer servidor que executa o WMF 2.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="157ac-231">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="157ac-232">**Contras**</span><span class="sxs-lookup"><span data-stu-id="157ac-232">**Cons**</span></span>

- <span data-ttu-id="157ac-233">Requer uma técnica de código complicada.</span><span class="sxs-lookup"><span data-stu-id="157ac-233">Requires an awkward code technique.</span></span>
- <span data-ttu-id="157ac-234">Se estiver executando o WMF 2.0, necessita de uma sintaxe diferente para passar argumentos para uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="157ac-234">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="157ac-235">Exemplo</span><span class="sxs-lookup"><span data-stu-id="157ac-235">Example</span></span>

<span data-ttu-id="157ac-236">O exemplo a seguir mostra como passar credenciais em um bloco de script **Invoke-Command**:</span><span class="sxs-lookup"><span data-stu-id="157ac-236">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="157ac-237">Confira também</span><span class="sxs-lookup"><span data-stu-id="157ac-237">See also</span></span>

[<span data-ttu-id="157ac-238">Considerações de segurança de comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="157ac-238">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
