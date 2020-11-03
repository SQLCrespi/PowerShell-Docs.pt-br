---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193938"
---
# <span data-ttu-id="64b8f-103">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="64b8f-103">Reset-ComputerMachinePassword</span></span>

## <span data-ttu-id="64b8f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="64b8f-104">SYNOPSIS</span></span>
<span data-ttu-id="64b8f-105">Redefine a senha da conta da máquina para o computador.</span><span class="sxs-lookup"><span data-stu-id="64b8f-105">Resets the machine account password for the computer.</span></span>

## <span data-ttu-id="64b8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64b8f-106">SYNTAX</span></span>

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="64b8f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="64b8f-107">DESCRIPTION</span></span>
<span data-ttu-id="64b8f-108">O cmdlet **Reset-ComputerMachinePassword** altera a senha da conta de computador que os computadores usam para se autenticar nos controladores de domínio no domínio.</span><span class="sxs-lookup"><span data-stu-id="64b8f-108">The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.</span></span>
<span data-ttu-id="64b8f-109">Você pode usá-lo para redefinir a senha do computador local.</span><span class="sxs-lookup"><span data-stu-id="64b8f-109">You can use it to reset the password of the local computer.</span></span>

## <span data-ttu-id="64b8f-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="64b8f-110">EXAMPLES</span></span>

### <span data-ttu-id="64b8f-111">Exemplo 1: redefinir a senha para o computador local</span><span class="sxs-lookup"><span data-stu-id="64b8f-111">Example 1: Reset the password for the local computer</span></span>

```
PS C:\> Reset-ComputerMachinePassword
```

<span data-ttu-id="64b8f-112">Esse comando redefine a senha do computador local.</span><span class="sxs-lookup"><span data-stu-id="64b8f-112">This command resets the computer password for the local computer.</span></span>
<span data-ttu-id="64b8f-113">O comando é executado com as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="64b8f-113">The command runs with the credentials of the current user.</span></span>

### <span data-ttu-id="64b8f-114">Exemplo 2: redefinir a senha para o computador local usando um controlador de domínio especificado</span><span class="sxs-lookup"><span data-stu-id="64b8f-114">Example 2: Reset the password for the local computer by using a specified domain controller</span></span>

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

<span data-ttu-id="64b8f-115">Esse comando redefine a senha do computador local usando o controlador de domínio DC01.</span><span class="sxs-lookup"><span data-stu-id="64b8f-115">This command resets the computer password of the local computer by using the DC01 domain controller.</span></span>
<span data-ttu-id="64b8f-116">Ele usa o parâmetro *Credential* para especificar uma conta de usuário que tenha permissão para redefinir uma senha de computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="64b8f-116">It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.</span></span>

### <span data-ttu-id="64b8f-117">Exemplo 3: redefinir a senha em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="64b8f-117">Example 3: Reset the password on a remote computer</span></span>

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

<span data-ttu-id="64b8f-118">Esse comando usa o cmdlet Invoke-Command para executar um comando **Reset-ComputerMachinePassword** no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="64b8f-118">This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.</span></span>

<span data-ttu-id="64b8f-119">Para obter mais informações sobre comandos remotos no Windows PowerShell, consulte about_Remote e **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="64b8f-119">For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command** .</span></span>

## <span data-ttu-id="64b8f-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64b8f-120">PARAMETERS</span></span>

### <span data-ttu-id="64b8f-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="64b8f-121">-Credential</span></span>
<span data-ttu-id="64b8f-122">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="64b8f-122">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="64b8f-123">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="64b8f-123">The default is the current user.</span></span>

<span data-ttu-id="64b8f-124">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="64b8f-124">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="64b8f-125">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="64b8f-125">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="64b8f-126">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="64b8f-126">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b8f-127">-Server</span><span class="sxs-lookup"><span data-stu-id="64b8f-127">-Server</span></span>
<span data-ttu-id="64b8f-128">Especifica o nome de um controlador de domínio a ser usado quando esse cmdlet definir a senha da conta do computador.</span><span class="sxs-lookup"><span data-stu-id="64b8f-128">Specifies the name of a domain controller to use when this cmdlet sets the computer account password.</span></span>

<span data-ttu-id="64b8f-129">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="64b8f-129">This parameter is optional.</span></span>
<span data-ttu-id="64b8f-130">Se você omitir esse parâmetro, um controlador de domínio é escolhido para atender ao comando.</span><span class="sxs-lookup"><span data-stu-id="64b8f-130">If you omit this parameter, a domain controller is chosen to service the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64b8f-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="64b8f-131">-Confirm</span></span>
<span data-ttu-id="64b8f-132">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64b8f-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="64b8f-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="64b8f-133">-WhatIf</span></span>
<span data-ttu-id="64b8f-134">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="64b8f-134">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="64b8f-135">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="64b8f-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="64b8f-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="64b8f-136">CommonParameters</span></span>
<span data-ttu-id="64b8f-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="64b8f-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64b8f-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="64b8f-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64b8f-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="64b8f-139">INPUTS</span></span>

### <span data-ttu-id="64b8f-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="64b8f-140">None</span></span>
<span data-ttu-id="64b8f-141">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64b8f-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="64b8f-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="64b8f-142">OUTPUTS</span></span>

### <span data-ttu-id="64b8f-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="64b8f-143">None</span></span>
<span data-ttu-id="64b8f-144">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="64b8f-144">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="64b8f-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="64b8f-145">NOTES</span></span>

## <span data-ttu-id="64b8f-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="64b8f-146">RELATED LINKS</span></span>

## <span data-ttu-id="64b8f-147">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="64b8f-147">RELATED LINKS</span></span>
