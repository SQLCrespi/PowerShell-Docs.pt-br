---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 075071f83e8443d186dcc99e13fa102504dc23af
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345520"
---
# <span data-ttu-id="7039b-103">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-103">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="7039b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7039b-104">SYNOPSIS</span></span>
<span data-ttu-id="7039b-105">Desabilita as configurações de sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="7039b-105">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="7039b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7039b-106">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="7039b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7039b-107">DESCRIPTION</span></span>

<span data-ttu-id="7039b-108">O `Disable-PSSessionConfiguration` cmdlet desabilita as configurações de sessão no computador local, o que impede que todos os usuários usem as configurações de sessão para criar sessões gerenciadas pelo usuário ( **PSSessions** ) no computador local.</span><span class="sxs-lookup"><span data-stu-id="7039b-108">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions ( **PSSessions** ) on the local computer.</span></span> <span data-ttu-id="7039b-109">Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7039b-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="7039b-110">A partir do PowerShell 3,0, o `Disable-PSSessionConfiguration` cmdlet define a configuração **habilitada** da configuração de sessão ( `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ) como false.</span><span class="sxs-lookup"><span data-stu-id="7039b-110">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="7039b-111">No PowerShell 2,0, o `Disable-PSSessionConfiguration` cmdlet adiciona uma entrada de **Deny_All** ao descritor de segurança de uma ou mais configurações de sessão registradas.</span><span class="sxs-lookup"><span data-stu-id="7039b-111">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="7039b-112">Sem parâmetros, `Disable-PSSessionConfiguration` desabilita a configuração do **Microsoft. PowerShell** , a configuração padrão usada para sessões.</span><span class="sxs-lookup"><span data-stu-id="7039b-112">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="7039b-113">A menos que o usuário especifique uma configuração diferente, tanto os usuários locais e remotos são efetivamente impedidos de criar quaisquer sessões que se conectem ao computador.</span><span class="sxs-lookup"><span data-stu-id="7039b-113">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="7039b-114">Para desabilitar todas as configurações de sessão no computador, use `Disable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="7039b-114">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="7039b-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7039b-115">EXAMPLES</span></span>

### <span data-ttu-id="7039b-116">Exemplo 1: desabilitar a configuração padrão</span><span class="sxs-lookup"><span data-stu-id="7039b-116">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="7039b-117">Este exemplo desabilita a configuração de sessão do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7039b-117">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="7039b-118">Exemplo 2: desabilitar todas as configurações de sessão registradas</span><span class="sxs-lookup"><span data-stu-id="7039b-118">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="7039b-119">Este exemplo desabilita todas as configurações de sessão registradas no computador.</span><span class="sxs-lookup"><span data-stu-id="7039b-119">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="7039b-120">Exemplo 3: desabilitar as configurações de sessão por nome</span><span class="sxs-lookup"><span data-stu-id="7039b-120">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="7039b-121">Este exemplo desabilita todas as configurações de sessão que têm nomes que começam com a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7039b-121">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="7039b-122">O parâmetro **Force** suprime todos os prompts do usuário do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7039b-122">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="7039b-123">Exemplo 4: desabilitar as configurações de sessão usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="7039b-123">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="7039b-124">Este exemplo desabilita as configurações de sessão **MaintenanceShell** e **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="7039b-124">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="7039b-125">O operador de pipeline (|) envia os resultados de um `Get-PSSessionConfiguration` para `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="7039b-125">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="7039b-126">Exemplo 5: efeitos da desabilitação de uma configuração de sessão</span><span class="sxs-lookup"><span data-stu-id="7039b-126">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="7039b-127">Este exemplo mostra as permissões antes e depois `Disable-PSSessionConfiguration` da execução e o efeito de desabilitar uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="7039b-127">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> <span data-ttu-id="7039b-128">Desabilitar a configuração não impede que você altere a configuração usando o `Set-PSSessionConfiguration` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7039b-128">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="7039b-129">Ele só impede o uso da configuração.</span><span class="sxs-lookup"><span data-stu-id="7039b-129">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="7039b-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7039b-130">PARAMETERS</span></span>

### <span data-ttu-id="7039b-131">-Force</span><span class="sxs-lookup"><span data-stu-id="7039b-131">-Force</span></span>

<span data-ttu-id="7039b-132">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="7039b-132">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7039b-133">-Name</span><span class="sxs-lookup"><span data-stu-id="7039b-133">-Name</span></span>

<span data-ttu-id="7039b-134">Especifica uma matriz de nomes de configurações de sessão a serem desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="7039b-134">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="7039b-135">Insira um ou mais nomes de configuração.</span><span class="sxs-lookup"><span data-stu-id="7039b-135">Enter one or more configuration names.</span></span> <span data-ttu-id="7039b-136">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7039b-136">Wildcard characters are permitted.</span></span> <span data-ttu-id="7039b-137">Você também pode canalizar uma cadeia de caracteres que contém um nome de configuração ou um objeto de configuração de sessão para `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="7039b-137">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="7039b-138">Se você omitir esse parâmetro, `Disable-PSSessionConfiguration` o desabilitará a configuração de sessão do Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7039b-138">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="7039b-139">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="7039b-139">-NoServiceRestart</span></span>

<span data-ttu-id="7039b-140">Usado para impedir a reinicialização do serviço WSMan.</span><span class="sxs-lookup"><span data-stu-id="7039b-140">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="7039b-141">Não é necessário reiniciar o serviço para desabilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="7039b-141">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="7039b-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7039b-142">-Confirm</span></span>

<span data-ttu-id="7039b-143">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7039b-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7039b-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7039b-144">-WhatIf</span></span>

<span data-ttu-id="7039b-145">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7039b-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7039b-146">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7039b-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7039b-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7039b-147">CommonParameters</span></span>

<span data-ttu-id="7039b-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7039b-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7039b-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7039b-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7039b-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7039b-150">INPUTS</span></span>

### <span data-ttu-id="7039b-151">Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="7039b-151">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="7039b-152">É possível canalizar um objeto de configuração de sessão ou uma cadeia de caracteres que contém o nome de uma configuração de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7039b-152">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="7039b-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7039b-153">OUTPUTS</span></span>

### <span data-ttu-id="7039b-154">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7039b-154">None</span></span>

<span data-ttu-id="7039b-155">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="7039b-155">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="7039b-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7039b-156">NOTES</span></span>

<span data-ttu-id="7039b-157">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="7039b-157">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="7039b-158">Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="7039b-158">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="7039b-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7039b-159">RELATED LINKS</span></span>

[<span data-ttu-id="7039b-160">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-160">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="7039b-161">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-161">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="7039b-162">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="7039b-162">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="7039b-163">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-163">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="7039b-164">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-164">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="7039b-165">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="7039b-165">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="7039b-166">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7039b-166">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="7039b-167">Provedor WSMan</span><span class="sxs-lookup"><span data-stu-id="7039b-167">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="7039b-168">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="7039b-168">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="7039b-169">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="7039b-169">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
