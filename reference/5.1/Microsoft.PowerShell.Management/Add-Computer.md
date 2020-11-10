---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388341"
---
# <span data-ttu-id="f371e-103">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-103">Add-Computer</span></span>

## <span data-ttu-id="f371e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f371e-104">SYNOPSIS</span></span>
<span data-ttu-id="f371e-105">Adicione o computador local para um domínio ou grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f371e-105">Add the local computer to a domain or workgroup.</span></span>

## <span data-ttu-id="f371e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f371e-106">SYNTAX</span></span>

### <span data-ttu-id="f371e-107">Domínio (padrão)</span><span class="sxs-lookup"><span data-stu-id="f371e-107">Domain (Default)</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f371e-108">Grupo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f371e-108">Workgroup</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="f371e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f371e-109">DESCRIPTION</span></span>

<span data-ttu-id="f371e-110">O `Add-Computer` cmdlet adiciona o computador local ou os computadores remotos a um domínio ou grupo de trabalho, ou os move de um domínio para outro.</span><span class="sxs-lookup"><span data-stu-id="f371e-110">The `Add-Computer` cmdlet adds the local computer or remote computers to a domain or workgroup, or moves them from one domain to another.</span></span> <span data-ttu-id="f371e-111">Ele também cria uma conta de domínio caso o computador seja adicionado ao domínio sem uma conta.</span><span class="sxs-lookup"><span data-stu-id="f371e-111">It also creates a domain account if the computer is added to the domain without an account.</span></span>

<span data-ttu-id="f371e-112">Você pode usar os parâmetros desse cmdlet para especificar uma unidade organizacional (UO) e um controlador de domínio ou para realizar uma junção não segura.</span><span class="sxs-lookup"><span data-stu-id="f371e-112">You can use the parameters of this cmdlet to specify an organizational unit (OU) and domain controller or to perform an unsecure join.</span></span>

<span data-ttu-id="f371e-113">Para obter os resultados do comando, utilize os parâmetros **Verbose** e **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="f371e-113">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span>

## <span data-ttu-id="f371e-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f371e-114">EXAMPLES</span></span>

### <span data-ttu-id="f371e-115">Exemplo 1: adicionar um computador local a um domínio e reiniciar o computador</span><span class="sxs-lookup"><span data-stu-id="f371e-115">Example 1: Add a local computer to a domain then restart the computer</span></span>

```powershell
Add-Computer -DomainName Domain01 -Restart
```

<span data-ttu-id="f371e-116">Este comando adiciona o computador local ao domínio Domain01 e, em seguida, reinicia o computador para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="f371e-116">This command adds the local computer to the Domain01 domain and then restarts the computer to make the change effective.</span></span>

### <span data-ttu-id="f371e-117">Exemplo 2: adicionar um computador local a um grupo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f371e-117">Example 2: Add a local computer to a workgroup</span></span>

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

<span data-ttu-id="f371e-118">Este comando adiciona o computador local ao grupo de trabalho Workgroup-A.</span><span class="sxs-lookup"><span data-stu-id="f371e-118">This command adds the local computer to the Workgroup-A workgroup.</span></span>

### <span data-ttu-id="f371e-119">Exemplo 3: adicionar um computador local a um domínio</span><span class="sxs-lookup"><span data-stu-id="f371e-119">Example 3: Add a local computer to a domain</span></span>

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

<span data-ttu-id="f371e-120">Este comando adiciona o computador local ao domínio Domain01 usando o controlador de domínio Domain01\DC01.</span><span class="sxs-lookup"><span data-stu-id="f371e-120">This command adds the local computer to the Domain01 domain by using the Domain01\DC01 domain controller.</span></span>

<span data-ttu-id="f371e-121">O comando usa os parâmetros **PassThru** e **Verbose** para obter informações detalhadas sobre os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="f371e-121">The command uses the **PassThru** and **Verbose** parameters to get detailed information about the results of the command.</span></span>

### <span data-ttu-id="f371e-122">Exemplo 4: adicionar um computador local a um domínio usando o parâmetro OUPath</span><span class="sxs-lookup"><span data-stu-id="f371e-122">Example 4: Add a local computer to a domain using the OUPath parameter</span></span>

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

<span data-ttu-id="f371e-123">Este comando adiciona o computador local ao domínio Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-123">This command adds the local computer to the Domain02 domain.</span></span>
<span data-ttu-id="f371e-124">Ele usa o parâmetro OUPath para especificar a unidade organizacional das novas contas.</span><span class="sxs-lookup"><span data-stu-id="f371e-124">It uses the OUPath parameter to specify the organizational unit for the new accounts.</span></span>

### <span data-ttu-id="f371e-125">Exemplo 5: adicionar um computador local a um domínio usando credenciais</span><span class="sxs-lookup"><span data-stu-id="f371e-125">Example 5: Add a local computer to a domain using credentials</span></span>

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

<span data-ttu-id="f371e-126">Este comando adiciona o computador Server01 ao domínio Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-126">This command adds the Server01 computer to the Domain02 domain.</span></span> <span data-ttu-id="f371e-127">Ele usa o parâmetro **LocalCredential** para especificar uma conta de usuário com permissão para se conectar ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f371e-127">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the Server01 computer.</span></span> <span data-ttu-id="f371e-128">Ele usa o parâmetro **Credential** para especificar uma conta de usuário com permissão para adicionar computadores ao domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-128">It uses the **Credential** parameter to specify a user account that has permission to join computers to the domain.</span></span> <span data-ttu-id="f371e-129">Ele usa o parâmetro **Restart** para reiniciar o computador após a conclusão da operação de junção e o parâmetro **Force** para suprimir mensagens de confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="f371e-129">It uses the **Restart** parameter to restart the computer after the join operation completes and the **Force** parameter to suppress user confirmation messages.</span></span>

### <span data-ttu-id="f371e-130">Exemplo 6: mover um grupo de computadores para um novo domínio</span><span class="sxs-lookup"><span data-stu-id="f371e-130">Example 6: Move a group of computers to a new domain</span></span>

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="f371e-131">Este comando move os computadores Server01 e Server02 e o computador local, de Domain01 para Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-131">This command moves the Server01 and Server02 computers, and the local computer, from Domain01 to Domain02.</span></span>

<span data-ttu-id="f371e-132">Ele usa o parâmetro **LocalCredential** para especificar uma conta de usuário com permissão para conectar-se a três computadores afetados.</span><span class="sxs-lookup"><span data-stu-id="f371e-132">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the three affected computers.</span></span> <span data-ttu-id="f371e-133">Ele usa o parâmetro **UnjoinDomainCredential** para especificar uma conta de usuário com permissão para sair dos computadores do domínio Domain01 e o parâmetro **Credential** para especificar uma conta de usuário com permissão para ingressar computadores ao domínio Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-133">It uses the **UnjoinDomainCredential** parameter to specify a user account that has permission to unjoin the computers from the Domain01 domain and the **Credential** parameter to specify a user account that has permission to join the computers to the Domain02 domain.</span></span> <span data-ttu-id="f371e-134">Ele usa o parâmetro **Restart** reiniciar todos os três computadores após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="f371e-134">It uses the **Restart** parameter to restart all three computers after the move is complete.</span></span>

### <span data-ttu-id="f371e-135">Exemplo 7: mover um computador para um novo domínio e alterar o nome do computador</span><span class="sxs-lookup"><span data-stu-id="f371e-135">Example 7: Move a computer to a new domain and change the name of the computer</span></span>

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="f371e-136">Este comando move o computador Server01 para o Domain02 e altera o nome do computador para Server044.</span><span class="sxs-lookup"><span data-stu-id="f371e-136">This command moves the Server01 computer to the Domain02 and changes the machine name to Server044.</span></span>

<span data-ttu-id="f371e-137">O comando usa as credenciais do usuário atual para se conectar ao computador Server01 e removê-lo do seu domínio atual.</span><span class="sxs-lookup"><span data-stu-id="f371e-137">The command uses the credential of the current user to connect to the Server01 computer and unjoin it from its current domain.</span></span> <span data-ttu-id="f371e-138">Ele usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para ingressar o computador no domínio Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-138">It uses the **Credential** parameter to specify a user account that has permission to join the computer to the Domain02 domain.</span></span>

### <span data-ttu-id="f371e-139">Exemplo 8: adicionar computadores listados em um arquivo a um novo domínio</span><span class="sxs-lookup"><span data-stu-id="f371e-139">Example 8: Add computers listed in a file to a new domain</span></span>

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

<span data-ttu-id="f371e-140">Este comando adiciona os computadores listados no arquivo Servers.txt no domínio Domain02.</span><span class="sxs-lookup"><span data-stu-id="f371e-140">This command adds the computers that are listed in the Servers.txt file to the Domain02 domain.</span></span> <span data-ttu-id="f371e-141">Ele usa o parâmetro **Options** para especificar a opção **Win9xUpgrade**.</span><span class="sxs-lookup"><span data-stu-id="f371e-141">It uses the **Options** parameter to specify the **Win9xUpgrade** option.</span></span> <span data-ttu-id="f371e-142">O parâmetro **Restart** reinicia todos os computadores recentemente adicionados após a conclusão da operação de junção.</span><span class="sxs-lookup"><span data-stu-id="f371e-142">The **Restart** parameter restarts all of the newly added computers after the join operation completes.</span></span>

### <span data-ttu-id="f371e-143">Exemplo 9: adicionar um computador a um domínio usando credenciais de computador predefinidas</span><span class="sxs-lookup"><span data-stu-id="f371e-143">Example 9: Add a computer to a domain using predefined computer credentials</span></span>

<span data-ttu-id="f371e-144">Esse primeiro comando deve ser executado por um administrador de um computador que já tenha ingressado no domínio `Domain03` :</span><span class="sxs-lookup"><span data-stu-id="f371e-144">This first command should be run by an administrator from a computer that is already joined to domain `Domain03`:</span></span>

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

<span data-ttu-id="f371e-145">Essa combinação de comandos cria uma nova conta de computador com um nome predefinido e uma senha de junção temporária em um domínio usando um computador ingressado no domínio existente.</span><span class="sxs-lookup"><span data-stu-id="f371e-145">This combination of commands creates a new computer account with a predefined name and temporary join password in a domain using an existing domain-joined computer.</span></span> <span data-ttu-id="f371e-146">Em seguida, separadamente, um computador com o nome predefinido une o domínio usando apenas o nome do computador e a senha de junção temporária.</span><span class="sxs-lookup"><span data-stu-id="f371e-146">Then separately, a computer with the predefined name joins the domain using only the computer name and the temporary join password.</span></span>
<span data-ttu-id="f371e-147">A senha predefinida é usada apenas para dar suporte à operação de junção e é substituída como parte dos procedimentos de conta de computador normal depois que o computador conclui a junção.</span><span class="sxs-lookup"><span data-stu-id="f371e-147">The predefined password is only used to support the join operation and is replaced as part of normal computer account procedures after the computer completes the join.</span></span>

## <span data-ttu-id="f371e-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f371e-148">PARAMETERS</span></span>

### <span data-ttu-id="f371e-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f371e-149">-ComputerName</span></span>

<span data-ttu-id="f371e-150">Especifica os computadores a serem adicionados a um domínio ou grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f371e-150">Specifies the computers to add to a domain or workgroup.</span></span>
<span data-ttu-id="f371e-151">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="f371e-151">The default is the local computer.</span></span>

<span data-ttu-id="f371e-152">Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um nome de domínio totalmente qualificado de cada um dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f371e-152">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of each of the remote computers.</span></span> <span data-ttu-id="f371e-153">Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou "localhost".</span><span class="sxs-lookup"><span data-stu-id="f371e-153">To specify the local computer, type the computer name, a dot (`.`), or "localhost".</span></span>

<span data-ttu-id="f371e-154">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f371e-154">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="f371e-155">Você pode usar o parâmetro **ComputerName** de `Add-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="f371e-155">You can use the **ComputerName** parameter of `Add-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="f371e-156">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-156">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="f371e-157">-Credential</span></span>

<span data-ttu-id="f371e-158">Especifica uma conta de usuário que tenha permissão para ingressar os computadores em um novo domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-158">Specifies a user account that has permission to join the computers to a new domain.</span></span>
<span data-ttu-id="f371e-159">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f371e-159">The default is the current user.</span></span>

<span data-ttu-id="f371e-160">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f371e-160">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f371e-161">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="f371e-161">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="f371e-162">Para especificar uma conta de usuário que tenha permissão para remover o computador do seu domínio atual, utilize o parâmetro **UnjoinDomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-162">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span> <span data-ttu-id="f371e-163">Para especificar uma conta de usuário que tenha permissão para conectar um computador remoto, use o parâmetro **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-163">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-164">-DomainName</span><span class="sxs-lookup"><span data-stu-id="f371e-164">-DomainName</span></span>

<span data-ttu-id="f371e-165">Especifica o domínio ao qual os computadores são adicionados.</span><span class="sxs-lookup"><span data-stu-id="f371e-165">Specifies the domain to which the computers are added.</span></span> <span data-ttu-id="f371e-166">Este parâmetro é necessário ao adicionar computadores a um domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-166">This parameter is required when adding the computers to a domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-167">-Force</span><span class="sxs-lookup"><span data-stu-id="f371e-167">-Force</span></span>

<span data-ttu-id="f371e-168">Suprime o aviso de confirmação de usuário.</span><span class="sxs-lookup"><span data-stu-id="f371e-168">Suppresses the user confirmation prompt.</span></span> <span data-ttu-id="f371e-169">Sem esse parâmetro, `Add-Computer` o exige que você confirme a adição de cada computador.</span><span class="sxs-lookup"><span data-stu-id="f371e-169">Without this parameter, `Add-Computer` requires you to confirm the addition of each computer.</span></span>

<span data-ttu-id="f371e-170">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-170">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-171">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="f371e-171">-LocalCredential</span></span>

<span data-ttu-id="f371e-172">Especifica uma conta de usuário que tenha permissão para conectar-se aos computadores que são especificados pelo parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="f371e-172">Specifies a user account that has permission to connect to the computers that are specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="f371e-173">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f371e-173">The default is the current user.</span></span>

<span data-ttu-id="f371e-174">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f371e-174">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f371e-175">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="f371e-175">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="f371e-176">Para especificar uma conta de usuário que tem permissão para adicionar computadores a um novo domínio, use o parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-176">To specify a user account that has permission to add the computers to a new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="f371e-177">Para especificar uma conta de usuário com permissão para remover os computadores dos seus domínios atuais, use o parâmetro **UnjoinDomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-177">To specify a user account that has permission to remove the computers from their current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="f371e-178">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-179">-NewName</span><span class="sxs-lookup"><span data-stu-id="f371e-179">-NewName</span></span>

<span data-ttu-id="f371e-180">Especifica um novo nome para o computador no novo domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-180">Specifies a new name for the computer in the new domain.</span></span> <span data-ttu-id="f371e-181">Este parâmetro é válido somente quando um computador está sendo adicionado ou movido.</span><span class="sxs-lookup"><span data-stu-id="f371e-181">This parameter is valid only when one computer is being added or moved.</span></span>

<span data-ttu-id="f371e-182">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-182">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-183">-Opções</span><span class="sxs-lookup"><span data-stu-id="f371e-183">-Options</span></span>

<span data-ttu-id="f371e-184">Especifica opções avançadas para a operação Adicionar ingresso no **computador** .</span><span class="sxs-lookup"><span data-stu-id="f371e-184">Specifies advanced options for the **Add-Computer** join operation.</span></span> <span data-ttu-id="f371e-185">Insira um ou mais valores em uma cadeia de caracteres separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f371e-185">Enter one or more values in a comma-separated string.</span></span>

<span data-ttu-id="f371e-186">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f371e-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f371e-187">**AccountCreate** : cria uma conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-187">**AccountCreate** : Creates a domain account.</span></span> <span data-ttu-id="f371e-188">O cmdlet **Add-Computer** cria automaticamente uma conta de domínio quando adiciona um computador a um domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-188">The **Add-Computer** cmdlet automatically creates a domain account when it adds a computer to a domain.</span></span> <span data-ttu-id="f371e-189">Essa opção está incluída para fins de integridade.</span><span class="sxs-lookup"><span data-stu-id="f371e-189">This option is included for completeness.</span></span>

- <span data-ttu-id="f371e-190">**Win9XUpgrade** : indica que a operação de junção faz parte de uma atualização do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="f371e-190">**Win9XUpgrade** : Indicates that the join operation is part of a Windows operating system upgrade.</span></span>

- <span data-ttu-id="f371e-191">**UnsecuredJoin** : executa uma junção não segura.</span><span class="sxs-lookup"><span data-stu-id="f371e-191">**UnsecuredJoin** : Performs an unsecured join.</span></span> <span data-ttu-id="f371e-192">Para solicitar uma junção não segura, use o parâmetro *Unsecure* ou essa opção.</span><span class="sxs-lookup"><span data-stu-id="f371e-192">To request an unsecured join, use the *Unsecure* parameter or this option.</span></span> <span data-ttu-id="f371e-193">Se você quiser passar uma senha de computador, deverá usar essa opção em combinação com a `PasswordPass` opção.</span><span class="sxs-lookup"><span data-stu-id="f371e-193">If you want to pass a machine password, then you must use this option in combination with `PasswordPass` option.</span></span>

- <span data-ttu-id="f371e-194">**PasswordPass** : define a senha do computador para o valor do parâmetro *Credential* (DomainCredential) após a execução de uma junção não segura.</span><span class="sxs-lookup"><span data-stu-id="f371e-194">**PasswordPass** : Sets the machine password to the value of the *Credential* (DomainCredential) parameter after performing an unsecured join.</span></span> <span data-ttu-id="f371e-195">Essa opção também indica que o valor do parâmetro *Credential* (DomainCredential) é uma senha de computador, não uma senha de usuário.</span><span class="sxs-lookup"><span data-stu-id="f371e-195">This option also indicates that the value of the *Credential* (DomainCredential) parameter is a machine password, not a user password.</span></span> <span data-ttu-id="f371e-196">Essa opção é válida somente quando a `UnsecuredJoin` opção é especificada.</span><span class="sxs-lookup"><span data-stu-id="f371e-196">This option is valid only when the `UnsecuredJoin` option is specified.</span></span> <span data-ttu-id="f371e-197">Ao usar essa opção, a credencial fornecida ao `-Credential` parâmetro *deve* ter um nome de usuário nulo.</span><span class="sxs-lookup"><span data-stu-id="f371e-197">When using this option, the credential provided to the `-Credential` parameter *must* have a null username.</span></span>

- <span data-ttu-id="f371e-198">**JoinWithNewName** : renomeia o nome do computador no novo domínio para o nome especificado pelo parâmetro *NewName* .</span><span class="sxs-lookup"><span data-stu-id="f371e-198">**JoinWithNewName** : Renames the computer name in the new domain to the name specified by the *NewName* parameter.</span></span> <span data-ttu-id="f371e-199">Quando você usa o parâmetro *NewName* , essa opção é definida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f371e-199">When you use the *NewName* parameter, this option is set automatically.</span></span> <span data-ttu-id="f371e-200">Essa opção foi projetada para ser usada com o cmdlet Rename-Computer.</span><span class="sxs-lookup"><span data-stu-id="f371e-200">This option is designed to be used with the Rename-Computer cmdlet.</span></span> <span data-ttu-id="f371e-201">Se você usar o cmdlet **Rename-Computer** para renomear o computador, mas não reiniciar o computador para que a alteração entre em vigor, poderá usar esse parâmetro para ingressar o computador em um domínio com seu novo nome.</span><span class="sxs-lookup"><span data-stu-id="f371e-201">If you use the **Rename-Computer** cmdlet to rename the computer, but do not restart the computer to make the change effective, you can use this parameter to join the computer to a domain with its new name.</span></span>

- <span data-ttu-id="f371e-202">**JoinReadOnly** : usa uma conta de computador existente para ingressar o computador em um controlador de domínio somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f371e-202">**JoinReadOnly** : Uses an existing machine account to join the computer to a read-only domain controller.</span></span> <span data-ttu-id="f371e-203">A conta da máquina deve ser adicionada à lista de permissões para a política de replicação de senha e a senha da conta deve ser replicada para o controlador de domínio somente leitura antes da operação de junção.</span><span class="sxs-lookup"><span data-stu-id="f371e-203">The machine account must be added to the allowed list for password replication policy and the account password must be replicated to the read-only domain controller prior to the join operation.</span></span>

- <span data-ttu-id="f371e-204">**InstallInvoke** : define os sinalizadores Create (0x2) e Delete (0x4) do parâmetro **FJoinOptions** do método **JoinDomainOrWorkgroup** .</span><span class="sxs-lookup"><span data-stu-id="f371e-204">**InstallInvoke** : Sets the create (0x2) and delete (0x4) flags of the **FJoinOptions** parameter of the **JoinDomainOrWorkgroup** method.</span></span> <span data-ttu-id="f371e-205">Para obter mais informações sobre o método **JoinDomainOrWorkgroup** , consulte [método JoinDomainOrWorkgroup da classe Win32_ComputerSystem](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span><span class="sxs-lookup"><span data-stu-id="f371e-205">For more information about the **JoinDomainOrWorkgroup** method, see [JoinDomainOrWorkgroup method of the Win32_ComputerSystem class](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span></span>
  <span data-ttu-id="f371e-206">Para obter mais informações sobre essas opções, consulte [função NetJoinDomain](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span><span class="sxs-lookup"><span data-stu-id="f371e-206">For more information about these options, see [NetJoinDomain function](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span></span>

<span data-ttu-id="f371e-207">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-208">-OUPath</span><span class="sxs-lookup"><span data-stu-id="f371e-208">-OUPath</span></span>

<span data-ttu-id="f371e-209">Especifica uma unidade organizacional (UO) para a conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-209">Specifies an organizational unit (OU) for the domain account.</span></span> <span data-ttu-id="f371e-210">Digite o nome distinto completo da UO entre aspas.</span><span class="sxs-lookup"><span data-stu-id="f371e-210">Enter the full distinguished name of the OU in quotation marks.</span></span> <span data-ttu-id="f371e-211">O valor padrão é o padrão da UO para objetos do computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-211">The default value is the default OU for machine objects in the domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-212">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f371e-212">-PassThru</span></span>

<span data-ttu-id="f371e-213">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f371e-213">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="f371e-214">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f371e-214">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-215">-Restart</span><span class="sxs-lookup"><span data-stu-id="f371e-215">-Restart</span></span>

<span data-ttu-id="f371e-216">Reinicia os computadores que foram adicionados ao domínio ou grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f371e-216">Restarts the computers that were added to the domain or workgroup.</span></span> <span data-ttu-id="f371e-217">Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="f371e-217">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="f371e-218">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-218">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-219">-Server</span><span class="sxs-lookup"><span data-stu-id="f371e-219">-Server</span></span>

<span data-ttu-id="f371e-220">Especifica o nome de um controlador de domínio que adiciona o computador ao domínio.</span><span class="sxs-lookup"><span data-stu-id="f371e-220">Specifies the name of a domain controller that adds the computer to the domain.</span></span> <span data-ttu-id="f371e-221">Digite o nome no formato DomainName\ComputerName.</span><span class="sxs-lookup"><span data-stu-id="f371e-221">Enter the name in DomainName\ComputerName format.</span></span> <span data-ttu-id="f371e-222">Por padrão, nenhum controlador de domínio é especificado.</span><span class="sxs-lookup"><span data-stu-id="f371e-222">By default, no domain controller is specified.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-223">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="f371e-223">-UnjoinDomainCredential</span></span>

<span data-ttu-id="f371e-224">Especifica uma conta de usuário que tenha permissão para remover os computadores de seus domínios atuais.</span><span class="sxs-lookup"><span data-stu-id="f371e-224">Specifies a user account that has permission to remove the computers from their current domains.</span></span> <span data-ttu-id="f371e-225">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f371e-225">The default is the current user.</span></span>

<span data-ttu-id="f371e-226">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f371e-226">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f371e-227">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="f371e-227">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="f371e-228">Use esse parâmetro quando você estiver movendo computadores para um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="f371e-228">Use this parameter when you are moving computers to a different domain.</span></span> <span data-ttu-id="f371e-229">Para especificar uma conta de usuário que tenha permissão para ingressar no novo domínio, use o parâmetro **Credential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-229">To specify a user account that has permission to join the new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="f371e-230">Para especificar uma conta de usuário que tenha permissão para conectar um computador remoto, use o parâmetro **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="f371e-230">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="f371e-231">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f371e-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-232">-Sem segurança</span><span class="sxs-lookup"><span data-stu-id="f371e-232">-Unsecure</span></span>

<span data-ttu-id="f371e-233">Executa um ingresso não seguro no domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="f371e-233">Performs an unsecure join to the specified domain.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-234">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="f371e-234">-WorkgroupName</span></span>

<span data-ttu-id="f371e-235">Especifica o nome de um grupo de trabalho para o qual os computadores são adicionados.</span><span class="sxs-lookup"><span data-stu-id="f371e-235">Specifies the name of a workgroup to which the computers are added.</span></span> <span data-ttu-id="f371e-236">O valor padrão é "WORKGROUP".</span><span class="sxs-lookup"><span data-stu-id="f371e-236">The default value is "WORKGROUP".</span></span>

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-237">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f371e-237">-Confirm</span></span>

<span data-ttu-id="f371e-238">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f371e-238">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f371e-239">-WhatIf</span></span>

<span data-ttu-id="f371e-240">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f371e-240">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f371e-241">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f371e-241">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f371e-242">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f371e-242">CommonParameters</span></span>

<span data-ttu-id="f371e-243">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f371e-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f371e-244">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f371e-244">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f371e-245">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f371e-245">INPUTS</span></span>

### <span data-ttu-id="f371e-246">System.String</span><span class="sxs-lookup"><span data-stu-id="f371e-246">System.String</span></span>

<span data-ttu-id="f371e-247">É possível canalizar nomes de computador e novos nomes para o `Add-Computer` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f371e-247">You can pipe computer names and new names to the `Add-Computer` Cmdlet.</span></span>

## <span data-ttu-id="f371e-248">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f371e-248">OUTPUTS</span></span>

### <span data-ttu-id="f371e-249">Microsoft. PowerShell. Commands. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="f371e-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="f371e-250">Quando você usa o parâmetro **PassThru** , `Add-Computer` retorna um objeto **ComputerChangeInfo** .</span><span class="sxs-lookup"><span data-stu-id="f371e-250">When you use the **PassThru** parameter, `Add-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="f371e-251">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f371e-251">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f371e-252">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f371e-252">NOTES</span></span>

- <span data-ttu-id="f371e-253">No Windows PowerShell 2,0, o **Server** parâmetro de servidor `Add-Computer` falha mesmo quando o servidor está presente.</span><span class="sxs-lookup"><span data-stu-id="f371e-253">In Windows PowerShell 2.0, the **Server** parameter of `Add-Computer` fails even when the server is present.</span></span> <span data-ttu-id="f371e-254">No Windows PowerShell 3.0, a implementação do parâmetro **Server** é alterada para que ele funcione de forma confiável.</span><span class="sxs-lookup"><span data-stu-id="f371e-254">In Windows PowerShell 3.0, the implementation of the **Server** parameter is changed so that it works reliably.</span></span>

## <span data-ttu-id="f371e-255">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f371e-255">RELATED LINKS</span></span>

[<span data-ttu-id="f371e-256">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-256">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="f371e-257">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-257">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="f371e-258">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-258">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="f371e-259">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-259">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="f371e-260">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-260">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="f371e-261">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="f371e-261">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="f371e-262">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="f371e-262">Test-Connection</span></span>](Test-Connection.md)
