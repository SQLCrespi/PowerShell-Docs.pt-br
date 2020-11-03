---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: a6b980b022672fbc84549987e1cb5673f51e3dc4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194610"
---
# <span data-ttu-id="d3338-103">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-103">Remove-PSSession</span></span>

## <span data-ttu-id="d3338-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d3338-104">SYNOPSIS</span></span>
<span data-ttu-id="d3338-105">Fecha uma ou mais sessões do PowerShell (PSSessions).</span><span class="sxs-lookup"><span data-stu-id="d3338-105">Closes one or more PowerShell sessions (PSSessions).</span></span>

## <span data-ttu-id="d3338-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3338-106">SYNTAX</span></span>

### <span data-ttu-id="d3338-107">ID (padrão)</span><span class="sxs-lookup"><span data-stu-id="d3338-107">Id (Default)</span></span>

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-108">Session</span><span class="sxs-lookup"><span data-stu-id="d3338-108">Session</span></span>

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-109">ContainerId</span><span class="sxs-lookup"><span data-stu-id="d3338-109">ContainerId</span></span>

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-110">VMId</span><span class="sxs-lookup"><span data-stu-id="d3338-110">VMId</span></span>

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-111">VMName</span><span class="sxs-lookup"><span data-stu-id="d3338-111">VMName</span></span>

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-112">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d3338-112">InstanceId</span></span>

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-113">Name</span><span class="sxs-lookup"><span data-stu-id="d3338-113">Name</span></span>

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3338-114">ComputerName</span><span class="sxs-lookup"><span data-stu-id="d3338-114">ComputerName</span></span>

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d3338-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3338-115">DESCRIPTION</span></span>

<span data-ttu-id="d3338-116">O cmdlet **Remove-PSSession** fecha sessões do PowerShell ( **PSSessions** ) na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-116">The **Remove-PSSession** cmdlet closes PowerShell sessions ( **PSSessions** ) in the current session.</span></span>
<span data-ttu-id="d3338-117">Ele interrompe os comandos que estão em execução nas **PSSessions** , encerra a **PSSession** e libera os recursos que a **PSSession** estava usando.</span><span class="sxs-lookup"><span data-stu-id="d3338-117">It stops any commands that are running in the **PSSessions** , ends the **PSSession** , and releases the resources that the **PSSession** was using.</span></span>
<span data-ttu-id="d3338-118">Se a **PSSession** estiver conectada a um computador remoto, esse cmdlet também fechará a conexão entre os computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="d3338-118">If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.</span></span>

<span data-ttu-id="d3338-119">Para remover uma **PSSession** , insira o *nome* , *ComputerName* , *ID* ou *InstanceId* da sessão.</span><span class="sxs-lookup"><span data-stu-id="d3338-119">To remove a **PSSession** , enter the *Name* , *ComputerName* , *ID* , or *InstanceID* of the session.</span></span>

<span data-ttu-id="d3338-120">Se você salvou a *PSSession* em uma variável, o objeto de sessão permanecerá na variável, mas o estado da *PSSession* será fechado.</span><span class="sxs-lookup"><span data-stu-id="d3338-120">If you have saved the *PSSession* in a variable, the session object remains in the variable, but the state of the *PSSession* is Closed.</span></span>

## <span data-ttu-id="d3338-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d3338-121">EXAMPLES</span></span>

### <span data-ttu-id="d3338-122">Exemplo 1: remover sessões usando IDs</span><span class="sxs-lookup"><span data-stu-id="d3338-122">Example 1: Remove sessions by using IDs</span></span>

```powershell
Remove-PSSession -Id 1, 2
```

<span data-ttu-id="d3338-123">Esse comando remove as **PSSessions** que têm as IDs 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="d3338-123">This command removes the **PSSessions** that have IDs 1 and 2.</span></span>

### <span data-ttu-id="d3338-124">Exemplo 2: remover todas as sessões na sessão atual</span><span class="sxs-lookup"><span data-stu-id="d3338-124">Example 2: Remove all the sessions in the current session</span></span>

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

<span data-ttu-id="d3338-125">Esses comandos removem todas as **PSSessions** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-125">These commands remove all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="d3338-126">Embora o formato dos três comandos pareçam diferentes, eles têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="d3338-126">Although the three command formats look different, they have the same effect.</span></span>

### <span data-ttu-id="d3338-127">Exemplo 3: fechar sessões usando nomes</span><span class="sxs-lookup"><span data-stu-id="d3338-127">Example 3: Close sessions by using names</span></span>

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

<span data-ttu-id="d3338-128">Esses comandos fecham as **PSSessions** que estão conectadas a computadores que têm nomes que começam com o serv.</span><span class="sxs-lookup"><span data-stu-id="d3338-128">These commands close the **PSSessions** that are connected to computers that have names that begin with Serv.</span></span>

### <span data-ttu-id="d3338-129">Exemplo 4: fechar sessões conectadas a uma porta</span><span class="sxs-lookup"><span data-stu-id="d3338-129">Example 4: Close sessions connected to a port</span></span>

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

<span data-ttu-id="d3338-130">Esse comando fecha as **PSSessions** que estão conectadas à porta 90.</span><span class="sxs-lookup"><span data-stu-id="d3338-130">This command closes the **PSSessions** that are connected to port 90.</span></span>
<span data-ttu-id="d3338-131">Você pode usar esse formato de comando para identificar **PSSessions** por propriedades diferentes de *ComputerName* , *Name* , *InstanceId* e *ID* .</span><span class="sxs-lookup"><span data-stu-id="d3338-131">You can use this command format to identify **PSSessions** by properties other than *ComputerName* , *Name* , *InstanceID* , and *ID* .</span></span>

### <span data-ttu-id="d3338-132">Exemplo 5: fechar uma sessão com base na ID da instância</span><span class="sxs-lookup"><span data-stu-id="d3338-132">Example 5: Close a session based on instance ID</span></span>

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

<span data-ttu-id="d3338-133">Estes comandos mostram como fechar uma **PSSession** com base em sua ID de instância ou **RemoteRunspaceID** .</span><span class="sxs-lookup"><span data-stu-id="d3338-133">These commands show how to close a **PSSession** based on its instance ID, or **RemoteRunspaceID** .</span></span>

<span data-ttu-id="d3338-134">O primeiro comando usa o cmdlet **Get-PSSession** para obter as **PSSessions** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-134">The first command uses the **Get-PSSession** cmdlet to get the **PSSessions** in the current session.</span></span>
<span data-ttu-id="d3338-135">Ele usa um operador de pipeline (|) para enviar as **PSSessions** para o cmdlet Format-Table, que formata suas propriedades **ComputerName** e **InstanceId** em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="d3338-135">It uses a pipeline operator (|) to send the **PSSessions** to the Format-Table cmdlet, which formats their **ComputerName** and **InstanceID** properties in a table.</span></span>
<span data-ttu-id="d3338-136">O parâmetro *AutoSize* compacta as colunas para exibição.</span><span class="sxs-lookup"><span data-stu-id="d3338-136">The *AutoSize* parameter compresses the columns for display.</span></span>

<span data-ttu-id="d3338-137">Na exibição resultante, você pode identificar a **PSSession** a ser fechada e copiar e colar a *InstanceId* dessa **PSSession** no segundo comando.</span><span class="sxs-lookup"><span data-stu-id="d3338-137">From the resulting display, you can identify the **PSSession** to be closed, and copy and paste the *InstanceID* of that **PSSession** into the second command.</span></span>

<span data-ttu-id="d3338-138">O segundo comando usa o cmdlet **Remove-PSSession** para remover a *PSSession* com a ID de instância especificada.</span><span class="sxs-lookup"><span data-stu-id="d3338-138">The second command uses the **Remove-PSSession** cmdlet to remove the *PSSession* with the specified instance ID.</span></span>

### <span data-ttu-id="d3338-139">Exemplo 6: criar uma função que exclui todas as sessões na sessão atual</span><span class="sxs-lookup"><span data-stu-id="d3338-139">Example 6: Create a function that deletes all sessions in the current session</span></span>

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

<span data-ttu-id="d3338-140">Essa função exclui todas as **PSSessions** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-140">This function deletes all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="d3338-141">Depois de adicionar essa função ao seu perfil do PowerShell, para excluir todas as sessões, digite `EndPSS` .</span><span class="sxs-lookup"><span data-stu-id="d3338-141">After you add this function to your PowerShell profile, to delete all sessions, type `EndPSS`.</span></span>

## <span data-ttu-id="d3338-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3338-142">PARAMETERS</span></span>

### <span data-ttu-id="d3338-143">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d3338-143">-ComputerName</span></span>

<span data-ttu-id="d3338-144">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="d3338-144">Specifies an array of names of computers.</span></span>
<span data-ttu-id="d3338-145">Esse cmdlet fecha as **PSSessions** que estão conectadas aos computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="d3338-145">This cmdlet closes the **PSSessions** that are connected to the specified computers.</span></span>
<span data-ttu-id="d3338-146">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d3338-146">Wildcard characters are permitted.</span></span>

<span data-ttu-id="d3338-147">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="d3338-147">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span>
<span data-ttu-id="d3338-148">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="d3338-148">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d3338-149">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="d3338-149">-ContainerId</span></span>

<span data-ttu-id="d3338-150">Especifica uma matriz de IDs de contêineres.</span><span class="sxs-lookup"><span data-stu-id="d3338-150">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="d3338-151">Esse cmdlet Remove sessões para cada um dos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="d3338-151">This cmdlet removes sessions for each of the specified containers.</span></span> <span data-ttu-id="d3338-152">Use o `docker ps` comando para obter uma lista de IDs de contêiner.</span><span class="sxs-lookup"><span data-stu-id="d3338-152">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="d3338-153">Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="d3338-153">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-154">-Id</span><span class="sxs-lookup"><span data-stu-id="d3338-154">-Id</span></span>

<span data-ttu-id="d3338-155">Especifica uma matriz de IDs de sessões.</span><span class="sxs-lookup"><span data-stu-id="d3338-155">Specifies an array of IDs of sessions.</span></span>
<span data-ttu-id="d3338-156">Esse cmdlet fecha as *PSSessions* com as IDs especificadas.</span><span class="sxs-lookup"><span data-stu-id="d3338-156">This cmdlet closes the *PSSessions* with the specified IDs.</span></span>
<span data-ttu-id="d3338-157">Digite uma ou mais IDs, separadas por vírgulas, ou use o operador de intervalo (..) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="d3338-157">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="d3338-158">Uma ID é um inteiro que identifica exclusivamente a **PSSession** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-158">An ID is an integer that uniquely identifies the **PSSession** in the current session.</span></span>
<span data-ttu-id="d3338-159">É mais fácil lembrar e digitar do que a *InstanceId* , mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-159">It is easier to remember and type than the *InstanceId* , but it is unique only in the current session.</span></span>
<span data-ttu-id="d3338-160">Para localizar a ID de uma **PSSession** , execute o cmdlet Get-PSSession sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d3338-160">To find the ID of a **PSSession** , run the Get-PSSession cmdlet without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-161">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="d3338-161">-InstanceId</span></span>

<span data-ttu-id="d3338-162">Especifica uma matriz de IDs de instância.</span><span class="sxs-lookup"><span data-stu-id="d3338-162">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="d3338-163">Esse cmdlet fecha as **PSSessions** que têm as IDs de instância especificadas.</span><span class="sxs-lookup"><span data-stu-id="d3338-163">This cmdlet closes the **PSSessions** that have the specified instance IDs.</span></span>

<span data-ttu-id="d3338-164">A ID da instância é um GUID que identifica exclusivamente uma **PSSession** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-164">The instance ID is a GUID that uniquely identifies a **PSSession** in the current session.</span></span>
<span data-ttu-id="d3338-165">A ID da instância é exclusiva, mesmo quando você tem várias sessões em execução em um único computador.</span><span class="sxs-lookup"><span data-stu-id="d3338-165">The instance ID is unique, even when you have multiple sessions running on a single computer.</span></span>

<span data-ttu-id="d3338-166">A ID da instância é armazenada na propriedade **InstanceId** do objeto que representa uma **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3338-166">The instance ID is stored in the **InstanceID** property of the object that represents a **PSSession** .</span></span>
<span data-ttu-id="d3338-167">Para localizar a **InstanceId** das **PSSessions** na sessão atual, digite `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .</span><span class="sxs-lookup"><span data-stu-id="d3338-167">To find the **InstanceID** of the **PSSessions** in the current session, type `Get-PSSession | Format-Table Name, ComputerName, InstanceId`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-168">-Name</span><span class="sxs-lookup"><span data-stu-id="d3338-168">-Name</span></span>

<span data-ttu-id="d3338-169">Especifica uma matriz de nomes amigáveis de sessões.</span><span class="sxs-lookup"><span data-stu-id="d3338-169">Specifies an array of friendly names of sessions.</span></span>
<span data-ttu-id="d3338-170">Esse cmdlet fecha as **PSSessions** que têm os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="d3338-170">This cmdlet closes the **PSSessions** that have the specified friendly names.</span></span>
<span data-ttu-id="d3338-171">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d3338-171">Wildcard characters are permitted.</span></span>

<span data-ttu-id="d3338-172">Como o nome amigável de uma **PSSession** pode não ser exclusivo, ao usar o parâmetro *Name* , considere também usar o parâmetro *WhatIf* ou *Confirm* no comando **Remove-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3338-172">Because the friendly name of a **PSSession** might not be unique, when you use the *Name* parameter, consider also using the *WhatIf* or *Confirm* parameter in the **Remove-PSSession** command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d3338-173">-Sessão</span><span class="sxs-lookup"><span data-stu-id="d3338-173">-Session</span></span>

<span data-ttu-id="d3338-174">Especifica os objetos de sessão de **PSSessions** a serem fechados.</span><span class="sxs-lookup"><span data-stu-id="d3338-174">Specifies the session objects of the **PSSessions** to close.</span></span>
<span data-ttu-id="d3338-175">Insira uma variável que contenha **PSSessions** ou um comando que cria ou obtém as **PSSessions** , como um comando New-PSSession ou **Get-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3338-175">Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions** , such as a New-PSSession or **Get-PSSession** command.</span></span>
<span data-ttu-id="d3338-176">Você também pode canalizar um ou mais objetos de sessão para **Remove-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3338-176">You can also pipe one or more session objects to **Remove-PSSession** .</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-177">-VMId</span><span class="sxs-lookup"><span data-stu-id="d3338-177">-VMId</span></span>

<span data-ttu-id="d3338-178">Especifica uma matriz de ID de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d3338-178">Specifies an array of ID of virtual machines.</span></span>
<span data-ttu-id="d3338-179">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="d3338-179">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="d3338-180">Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d3338-180">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-181">-VMName</span><span class="sxs-lookup"><span data-stu-id="d3338-181">-VMName</span></span>

<span data-ttu-id="d3338-182">Especifica uma matriz de nomes de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d3338-182">Specifies an array of names of virtual machines.</span></span>
<span data-ttu-id="d3338-183">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="d3338-183">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="d3338-184">Para ver as máquinas virtuais que estão disponíveis para você, use o cmdlet **Get-VM** .</span><span class="sxs-lookup"><span data-stu-id="d3338-184">To see the virtual machines that are available to you, use the **Get-VM** cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3338-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d3338-185">-Confirm</span></span>

<span data-ttu-id="d3338-186">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3338-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d3338-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d3338-187">-WhatIf</span></span>

<span data-ttu-id="d3338-188">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d3338-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d3338-189">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d3338-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d3338-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3338-190">CommonParameters</span></span>

<span data-ttu-id="d3338-191">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3338-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3338-192">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3338-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3338-193">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d3338-193">INPUTS</span></span>

### <span data-ttu-id="d3338-194">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-194">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="d3338-195">É possível canalizar um objeto de sessão para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3338-195">You can pipe a session object to this cmdlet.</span></span>

## <span data-ttu-id="d3338-196">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d3338-196">OUTPUTS</span></span>

### <span data-ttu-id="d3338-197">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d3338-197">None</span></span>

<span data-ttu-id="d3338-198">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="d3338-198">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="d3338-199">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d3338-199">NOTES</span></span>

* <span data-ttu-id="d3338-200">O parâmetro *ID* é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d3338-200">The *Id* parameter is mandatory.</span></span> <span data-ttu-id="d3338-201">Para excluir todas as **PSSessions** na sessão atual, digite `Get-PSSession | Remove-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="d3338-201">To delete all the **PSSessions** in the current session, type `Get-PSSession | Remove-PSSession`.</span></span>
* <span data-ttu-id="d3338-202">Uma **PSSession** usa uma conexão persistente com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3338-202">A **PSSession** uses a persistent connection to a remote computer.</span></span> <span data-ttu-id="d3338-203">Crie uma **PSSession** para executar uma série de comandos que compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="d3338-203">Create a **PSSession** to run a series of commands that share data.</span></span> <span data-ttu-id="d3338-204">Para obter mais informações, digite `Get-Help about_PSSessions`.</span><span class="sxs-lookup"><span data-stu-id="d3338-204">For more information, type `Get-Help about_PSSessions`.</span></span>
* <span data-ttu-id="d3338-205">As **PSSessions** são específicas para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d3338-205">**PSSessions** are specific to the current session.</span></span> <span data-ttu-id="d3338-206">Quando você encerra uma sessão, as **PSSessions** que você criou nessa sessão são fechadas forçosamente.</span><span class="sxs-lookup"><span data-stu-id="d3338-206">When you end a session, the **PSSessions** that you created in that session are forcibly closed.</span></span>

## <span data-ttu-id="d3338-207">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d3338-207">RELATED LINKS</span></span>

[<span data-ttu-id="d3338-208">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-208">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="d3338-209">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-209">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="d3338-210">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-210">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d3338-211">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-211">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d3338-212">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-212">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="d3338-213">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d3338-213">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="d3338-214">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-214">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d3338-215">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3338-215">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="d3338-216">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d3338-216">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="d3338-217">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d3338-217">about_Remote</span></span>](About/about_Remote.md)
