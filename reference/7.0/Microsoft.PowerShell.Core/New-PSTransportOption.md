---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: b8493931e6390dfb6a3c4becb5a9f51d79df0574
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194957"
---
# <span data-ttu-id="b3c82-103">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="b3c82-103">New-PSTransportOption</span></span>

## <span data-ttu-id="b3c82-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b3c82-104">SYNOPSIS</span></span>
<span data-ttu-id="b3c82-105">Cria um objeto que contém opções avançadas para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-105">Creates an object that contains advanced options for a session configuration.</span></span>

## <span data-ttu-id="b3c82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3c82-106">SYNTAX</span></span>

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## <span data-ttu-id="b3c82-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3c82-107">DESCRIPTION</span></span>

<span data-ttu-id="b3c82-108">O cmdlet **New-PSTransportOption** cria um objeto que contém opções de transporte para configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-108">The **New-PSTransportOption** cmdlet creates an object that contains transport options for session configurations.</span></span>
<span data-ttu-id="b3c82-109">Você pode usar o objeto como o valor do parâmetro *TransportOption* de cmdlets que criam ou alteram uma configuração de sessão, como os cmdlets Register-PSSessionConfiguration e Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b3c82-109">You can use the object as the value of the *TransportOption* parameter of cmdlets that create or change a session configuration, such as the Register-PSSessionConfiguration and Set-PSSessionConfiguration cmdlets.</span></span>

<span data-ttu-id="b3c82-110">Você também pode alterar as configurações de opção de transporte editando os valores das propriedades de configuração de sessão na unidade WSMan:.</span><span class="sxs-lookup"><span data-stu-id="b3c82-110">You can also change the transport option settings by editing the values of the session configuration properties in the WSMan: drive.</span></span>
<span data-ttu-id="b3c82-111">Para obter mais informações, consulte provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="b3c82-111">For more information, see WSMan Provider.</span></span>

<span data-ttu-id="b3c82-112">As opções de configuração de sessão representam os valores de sessão definidos no lado do servidor ou a extremidade de recebimento de uma conexão remota.</span><span class="sxs-lookup"><span data-stu-id="b3c82-112">The session configuration options represent the session values set on the server-side, or receiving end of a remote connection.</span></span>
<span data-ttu-id="b3c82-113">O lado do cliente, ou o término do envio da conexão, pode definir valores de opção de sessão quando a sessão é criada ou quando o cliente se desconecta do ou se reconecta à sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-113">The client-side, or sending end of the connection, can set session option values when the session is created, or when the client disconnects from or reconnects to the session.</span></span>
<span data-ttu-id="b3c82-114">Salvo indicação em contrário, quando há conflito de valores na configuração, prevalecem os valores do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="b3c82-114">Unless stated otherwise, when the setting values conflict, the client-side values take precedence.</span></span>
<span data-ttu-id="b3c82-115">No entanto, os valores do lado do cliente não podem violar valores máximos e as cotas definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-115">However, the client-side values cannot violate maximum values and quotas set in the session configuration.</span></span>

<span data-ttu-id="b3c82-116">Sem parâmetros, **New-PSTransportOption** gera um objeto de opção de transporte que tem valores nulos para todas as opções.</span><span class="sxs-lookup"><span data-stu-id="b3c82-116">Without parameters, **New-PSTransportOption** generates a transport option object that has null values for all of the options.</span></span>
<span data-ttu-id="b3c82-117">Se um parâmetro for omitido, o objeto tem um valor nulo para a propriedade que representa o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b3c82-117">If you omit a parameter, the object has a null value for the property that the parameter represents.</span></span>
<span data-ttu-id="b3c82-118">Um valor nulo não afeta a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-118">A null value does not affect the session configuration.</span></span>

<span data-ttu-id="b3c82-119">Para obter mais informações sobre as opções de sessão, consulte New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="b3c82-119">For more information about session options, see New-PSSessionOption.</span></span>
<span data-ttu-id="b3c82-120">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="b3c82-120">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="b3c82-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b3c82-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b3c82-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b3c82-122">EXAMPLES</span></span>

### <span data-ttu-id="b3c82-123">Exemplo 1: gerar uma opção de transporte padrão</span><span class="sxs-lookup"><span data-stu-id="b3c82-123">Example 1: Generate a default transport option</span></span>

```powershell
New-PSTransportOption
```

```Output
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

<span data-ttu-id="b3c82-124">Esse comando executa o **New-PSTransportOption** sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b3c82-124">This command runs the **New-PSTransportOption** without parameters.</span></span>
<span data-ttu-id="b3c82-125">A saída mostra que o cmdlet gera um objeto de opção de transporte que tem valores nulos para todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="b3c82-125">The output shows that the cmdlet generates a transport option object that has null values for all properties.</span></span>

### <span data-ttu-id="b3c82-126">Exemplo 2: obter opções de configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="b3c82-126">Example 2: Get session configuration options</span></span>

<span data-ttu-id="b3c82-127">Este exemplo mostra como usar um objeto de opções de transporte para definir opções de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-127">This example shows how to use a transport options object to set session configuration options.</span></span>

```powershell
$t = New-PSTransportOption -MaxSessions 40
Register-PSSessionConfiguration -Name ITTasks -TransportOption $t
Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="b3c82-128">O primeiro comando usa o cmdlet **New-PSTransportOption** para criar um objeto de opções de transporte, salvo na variável $t.</span><span class="sxs-lookup"><span data-stu-id="b3c82-128">The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable.</span></span> <span data-ttu-id="b3c82-129">O comando usa o parâmetro *MaxSessions* para aumentar o número máximo de sessões para 40.</span><span class="sxs-lookup"><span data-stu-id="b3c82-129">The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.</span></span>

<span data-ttu-id="b3c82-130">O segundo comando usa o cmdlet **Register-PSSessionConfiguration** para criar a configuração de sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="b3c82-130">The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration.</span></span> <span data-ttu-id="b3c82-131">O comando usa o parâmetro *TransportOption* para especificar o objeto de opções de transporte na variável $t.</span><span class="sxs-lookup"><span data-stu-id="b3c82-131">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="b3c82-132">O terceiro comando usa o cmdlet Get-PSSessionConfiguration para obter as configurações de sessão ITTasks e o cmdlet Format-List para exibir todas as propriedades do objeto de configuração de sessão em uma lista.</span><span class="sxs-lookup"><span data-stu-id="b3c82-132">The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list.</span></span> <span data-ttu-id="b3c82-133">A saída mostra que o valor da propriedade **MaxShells** da configuração de sessão é 40.</span><span class="sxs-lookup"><span data-stu-id="b3c82-133">The output shows that the value of the **MaxShells** property of the session configuration is 40.</span></span>

### <span data-ttu-id="b3c82-134">Exemplo 3: definindo uma opção de transporte</span><span class="sxs-lookup"><span data-stu-id="b3c82-134">Example 3: Setting a transport option</span></span>

<span data-ttu-id="b3c82-135">Este comando mostra o efeito de definir uma opção de transporte em uma configuração de sessão nas sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-135">This command shows the effect of setting a transport option in a session configuration on the sessions that use the session configuration.</span></span>

```powershell
$t = New-PSTransportOption -IdleTimeoutSec 3600
Set-PSSessionConfiguration -Name ITTasks -TransportOption $t
$s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks
$s | Format-List -Property *
```

```Output
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

<span data-ttu-id="b3c82-136">O primeiro comando utiliza o cmdlet **New-PSTransportOption** para criar um objeto de opção de transporte.</span><span class="sxs-lookup"><span data-stu-id="b3c82-136">The first command uses the **New-PSTransportOption** cmdlet to create a transport option object.</span></span> <span data-ttu-id="b3c82-137">O comando usa o parâmetro *IdleTimeoutSec* para definir o valor da propriedade **IdleTimeoutSec** do objeto para uma hora (3.600 segundos).</span><span class="sxs-lookup"><span data-stu-id="b3c82-137">The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds).</span></span> <span data-ttu-id="b3c82-138">O comando salva o objeto de transporte na variável $t.</span><span class="sxs-lookup"><span data-stu-id="b3c82-138">The command saves the transport objects object in the $t variable.</span></span>

<span data-ttu-id="b3c82-139">O segundo comando usa o cmdlet Set-PSSessionConfiguration para alterar as opções de transporte da configuração de sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="b3c82-139">The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration.</span></span> <span data-ttu-id="b3c82-140">O comando usa o parâmetro *TransportOption* para especificar o objeto de opções de transporte na variável $t.</span><span class="sxs-lookup"><span data-stu-id="b3c82-140">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="b3c82-141">O terceiro comando usa o cmdlet New-PSSession para criar a sessão MyITTasks no computador local.</span><span class="sxs-lookup"><span data-stu-id="b3c82-141">The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer.</span></span> <span data-ttu-id="b3c82-142">O comando utiliza a propriedade **ConfigurationName** para especificar a configuração de sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="b3c82-142">The command uses the **ConfigurationName** property to specify the ITTasks session configuration.</span></span> <span data-ttu-id="b3c82-143">O comando salva a sessão na variável $s. Observe que o comando não usa o parâmetro *SessionOption* de **New-PSSession** para definir um tempo limite de ociosidade personalizado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-143">The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session.</span></span> <span data-ttu-id="b3c82-144">Se tiver feito isso, o valor de tempo limite ocioso definido na opção de sessão terá precedência sobre o tempo limite de ociosidade definido na configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-144">If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.</span></span>

<span data-ttu-id="b3c82-145">O quarto comando usa o cmdlet Format-List para exibir todas as propriedades da sessão na variável $s em uma lista.</span><span class="sxs-lookup"><span data-stu-id="b3c82-145">The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list.</span></span> <span data-ttu-id="b3c82-146">A saída mostra que a sessão tem um tempo limite de ociosidade de uma hora (360.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="b3c82-146">The output shows that the session has an idle time-out of one hour (360,000 milliseconds).</span></span>

## <span data-ttu-id="b3c82-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3c82-147">PARAMETERS</span></span>

### <span data-ttu-id="b3c82-148">-IdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="b3c82-148">-IdleTimeoutSec</span></span>

<span data-ttu-id="b3c82-149">Determina por quanto tempo cada sessão permanecerá aberta se o computador remoto não receber nenhuma comunicação do computador local.</span><span class="sxs-lookup"><span data-stu-id="b3c82-149">Determines how long each session stays open if the remote computer does not receive any communication from the local computer.</span></span>
<span data-ttu-id="b3c82-150">Isso inclui o sinal de pulsação.</span><span class="sxs-lookup"><span data-stu-id="b3c82-150">This includes the heartbeat signal.</span></span>
<span data-ttu-id="b3c82-151">Quando o intervalo expira, a sessão é fechada.</span><span class="sxs-lookup"><span data-stu-id="b3c82-151">When the interval expires, the session closes.</span></span>

<span data-ttu-id="b3c82-152">O valor de tempo limite ocioso é de importância significativa quando o usuário pretende desconectar e reconectar-se a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-152">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="b3c82-153">O usuário poderá se reconectar somente se a sessão não tiver expirado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-153">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="b3c82-154">O parâmetro *IdleTimeoutSec* corresponde à propriedade **IdleTimeoutMs** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-154">The *IdleTimeoutSec* parameter corresponds to the **IdleTimeoutMs** property of a session configuration.</span></span>

<span data-ttu-id="b3c82-155">Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="b3c82-155">Enter a value in seconds.</span></span>
<span data-ttu-id="b3c82-156">O valor padrão é 7200 (2 horas).</span><span class="sxs-lookup"><span data-stu-id="b3c82-156">The default value is 7200 (2 hours).</span></span>
<span data-ttu-id="b3c82-157">O valor mínimo é 60 (1 minuto).</span><span class="sxs-lookup"><span data-stu-id="b3c82-157">The minimum value is 60 (1 minute).</span></span>
<span data-ttu-id="b3c82-158">O máximo é o valor da propriedade **IdleTimeout** dos objetos shell na configuração do WSMan ( `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` ).</span><span class="sxs-lookup"><span data-stu-id="b3c82-158">The maximum is the value of the **IdleTimeout** property of Shell objects in the WSMan configuration (`WSMan:\\\<ComputerName\>\Shell\IdleTimeout`).</span></span>
<span data-ttu-id="b3c82-159">O valor padrão é 7200000 milissegundos (2 horas).</span><span class="sxs-lookup"><span data-stu-id="b3c82-159">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="b3c82-160">Se um valor de tempo limite ocioso for definido nas opções de sessão e na configuração de sessão, o valor definido nas opções de sessão terá precedência, mas não poderá exceder o valor da propriedade **MaxIdleTimeoutMs** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-160">If an idle time-out value is set in the session options and in the session configuration, value set in the session options takes precedence, but it cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span>
<span data-ttu-id="b3c82-161">Para definir o valor da propriedade **MaxIdleTimeoutMs** , use o parâmetro *MaxIdleTimeoutSec* .</span><span class="sxs-lookup"><span data-stu-id="b3c82-161">To set the value of the **MaxIdleTimeoutMs** property, use the *MaxIdleTimeoutSec* parameter.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-162">-MaxConcurrentCommandsPerSession</span><span class="sxs-lookup"><span data-stu-id="b3c82-162">-MaxConcurrentCommandsPerSession</span></span>

<span data-ttu-id="b3c82-163">Limita o número de comandos que podem ser executados ao mesmo tempo em cada sessão para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-163">Limits the number of commands that can run at the same time in each session to the specified value.</span></span>
<span data-ttu-id="b3c82-164">O valor padrão é 1000.</span><span class="sxs-lookup"><span data-stu-id="b3c82-164">The default value is 1000.</span></span>

<span data-ttu-id="b3c82-165">O parâmetro *MaxConcurrentCommandsPerSession* corresponde à propriedade **MaxConcurrentCommandsPerShell** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-165">The *MaxConcurrentCommandsPerSession* parameter corresponds to the **MaxConcurrentCommandsPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-166">-MaxConcurrentUsers</span><span class="sxs-lookup"><span data-stu-id="b3c82-166">-MaxConcurrentUsers</span></span>

<span data-ttu-id="b3c82-167">Limita o número de usuários que podem executar comandos ao mesmo tempo em cada sessão para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-167">Limits the number of users who can run commands at the same time in each session to the specified value.</span></span>
<span data-ttu-id="b3c82-168">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="b3c82-168">The default value is 5.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-169">-MaxIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="b3c82-169">-MaxIdleTimeoutSec</span></span>

<span data-ttu-id="b3c82-170">Limita o tempo limite de ociosidade definido para cada sessão ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-170">Limits the idle time-out set for each session to the specified value.</span></span>
<span data-ttu-id="b3c82-171">O valor padrão é \[ int \] :: MaxValue (aproximadamente 25 dias).</span><span class="sxs-lookup"><span data-stu-id="b3c82-171">The default value is \[Int\]::MaxValue (~25 days).</span></span>

<span data-ttu-id="b3c82-172">O valor de tempo limite ocioso é de importância significativa quando o usuário pretende desconectar e reconectar-se a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-172">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="b3c82-173">O usuário poderá se reconectar somente se a sessão não tiver expirado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-173">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="b3c82-174">O parâmetro *MaxIdleTimeoutSec* corresponde à propriedade **MaxIdleTimeoutMs** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-174">The *MaxIdleTimeoutSec* parameter corresponds to the **MaxIdleTimeoutMs** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-175">-MaxMemoryPerSessionMB</span><span class="sxs-lookup"><span data-stu-id="b3c82-175">-MaxMemoryPerSessionMB</span></span>

<span data-ttu-id="b3c82-176">Limita a memória usada por cada sessão para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-176">Limits the memory used by each session to the specified value.</span></span>
<span data-ttu-id="b3c82-177">Insira um valor em megabytes.</span><span class="sxs-lookup"><span data-stu-id="b3c82-177">Enter a value in megabytes.</span></span>
<span data-ttu-id="b3c82-178">O valor padrão é 1024 MB (1 GB).</span><span class="sxs-lookup"><span data-stu-id="b3c82-178">The default value is 1024 megabytes (1 GB).</span></span>

<span data-ttu-id="b3c82-179">O parâmetro *MaxMemoryPerSessionMB* corresponde à propriedade **MaxMemoryPerShellMB** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-179">The *MaxMemoryPerSessionMB* parameter corresponds to the **MaxMemoryPerShellMB** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-180">-MaxProcessesPerSession</span><span class="sxs-lookup"><span data-stu-id="b3c82-180">-MaxProcessesPerSession</span></span>

<span data-ttu-id="b3c82-181">Limita o número de processos em execução em cada sessão para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-181">Limits the number of processes running in each session to the specified value.</span></span>
<span data-ttu-id="b3c82-182">O valor padrão é 15.</span><span class="sxs-lookup"><span data-stu-id="b3c82-182">The default value is 15.</span></span>

<span data-ttu-id="b3c82-183">O parâmetro *MaxProcessesPerSession* corresponde à propriedade **MaxProcessesPerShell** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-183">The *MaxProcessesPerSession* parameter corresponds to the **MaxProcessesPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-184">-MaxSessions</span><span class="sxs-lookup"><span data-stu-id="b3c82-184">-MaxSessions</span></span>

<span data-ttu-id="b3c82-185">Especifica o número de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-185">Limits the number of sessions that use the session configuration.</span></span>
<span data-ttu-id="b3c82-186">O valor padrão é 25.</span><span class="sxs-lookup"><span data-stu-id="b3c82-186">The default value is 25.</span></span>

<span data-ttu-id="b3c82-187">O parâmetro *MaxSessions* corresponde à propriedade **MaxShells** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-187">The *MaxSessions* parameter corresponds to the **MaxShells** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-188">-MaxSessionsPerUser</span><span class="sxs-lookup"><span data-stu-id="b3c82-188">-MaxSessionsPerUser</span></span>

<span data-ttu-id="b3c82-189">Limita o número de sessões que usam a configuração de sessão e são executadas com as credenciais de um determinado usuário para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-189">Limits the number of sessions that use the session configuration and run with the credentials of a given user to the specified value.</span></span>
<span data-ttu-id="b3c82-190">O valor padrão é 25.</span><span class="sxs-lookup"><span data-stu-id="b3c82-190">The default value is 25.</span></span>

<span data-ttu-id="b3c82-191">Ao especificar esse valor, considere que muitos usuários podem estar usando as credenciais de um usuário executar como.</span><span class="sxs-lookup"><span data-stu-id="b3c82-191">When you specify this value, consider that many users might be using the credentials of a run as user.</span></span>

<span data-ttu-id="b3c82-192">O parâmetro *MaxSessionsPerUser* corresponde à propriedade **MaxShellsPerUser** de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c82-192">The *MaxSessionsPerUser* parameter corresponds to the **MaxShellsPerUser** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-193">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="b3c82-193">-OutputBufferingMode</span></span>

<span data-ttu-id="b3c82-194">Determina como a saída do comando é gerenciada em sessões desconectadas quando o buffer de saída fica cheio.</span><span class="sxs-lookup"><span data-stu-id="b3c82-194">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>
<span data-ttu-id="b3c82-195">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b3c82-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b3c82-196">Bloquear.</span><span class="sxs-lookup"><span data-stu-id="b3c82-196">Block.</span></span>
<span data-ttu-id="b3c82-197">Quando o buffer de saída está cheio, a execução é suspensa até que o buffer esteja limpo.</span><span class="sxs-lookup"><span data-stu-id="b3c82-197">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="b3c82-198">Drop.</span><span class="sxs-lookup"><span data-stu-id="b3c82-198">Drop.</span></span>
<span data-ttu-id="b3c82-199">Quando o buffer de saída está cheio, a execução continua.</span><span class="sxs-lookup"><span data-stu-id="b3c82-199">When the output buffer is full, execution continues.</span></span>
<span data-ttu-id="b3c82-200">Conforme uma nova saída é salva, a saída mais antiga é descartada.</span><span class="sxs-lookup"><span data-stu-id="b3c82-200">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="b3c82-201">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b3c82-201">None.</span></span>
<span data-ttu-id="b3c82-202">Nenhum modo de buffering de saída é especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-202">No output buffering mode is specified.</span></span>

<span data-ttu-id="b3c82-203">O valor padrão da propriedade **OutputBufferingMode** de sessões é Block.</span><span class="sxs-lookup"><span data-stu-id="b3c82-203">The default value of the **OutputBufferingMode** property of sessions is Block.</span></span>

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-204">-ProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="b3c82-204">-ProcessIdleTimeoutSec</span></span>

<span data-ttu-id="b3c82-205">Limita o tempo limite para cada processo de host para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b3c82-205">Limits the time-out for each host process to the specified value.</span></span>
<span data-ttu-id="b3c82-206">O valor padrão, 0, significa que não há nenhum valor de tempo limite para o processo.</span><span class="sxs-lookup"><span data-stu-id="b3c82-206">The default value, 0, means that there is no time-out value for the process.</span></span>

<span data-ttu-id="b3c82-207">Outras configurações de sessão têm valores de tempo limite por processo.</span><span class="sxs-lookup"><span data-stu-id="b3c82-207">Other session configurations have per-process time-out values.</span></span>
<span data-ttu-id="b3c82-208">Por exemplo, a configuração de sessão do **Microsoft. PowerShell. Workflow** tem um valor de tempo limite por processo de 28800 segundos (8 horas).</span><span class="sxs-lookup"><span data-stu-id="b3c82-208">For example, the **Microsoft.PowerShell.Workflow** session configuration has a per-process time-out value of 28800 seconds (8 hours).</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c82-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b3c82-209">CommonParameters</span></span>

<span data-ttu-id="b3c82-210">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b3c82-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3c82-211">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b3c82-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3c82-212">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b3c82-212">INPUTS</span></span>

### <span data-ttu-id="b3c82-213">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b3c82-213">None</span></span>

<span data-ttu-id="b3c82-214">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b3c82-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b3c82-215">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b3c82-215">OUTPUTS</span></span>

### <span data-ttu-id="b3c82-216">Microsoft. PowerShell. Commands. WSManConfigurationOption</span><span class="sxs-lookup"><span data-stu-id="b3c82-216">Microsoft.PowerShell.Commands.WSManConfigurationOption</span></span>

## <span data-ttu-id="b3c82-217">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b3c82-217">NOTES</span></span>

- <span data-ttu-id="b3c82-218">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="b3c82-218">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="b3c82-219">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="b3c82-219">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="b3c82-220">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b3c82-220">RELATED LINKS</span></span>

[<span data-ttu-id="b3c82-221">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b3c82-221">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="b3c82-222">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="b3c82-222">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="b3c82-223">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3c82-223">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="b3c82-224">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3c82-224">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)
