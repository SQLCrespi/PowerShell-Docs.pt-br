---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: a754b6530ecd8b3153d82327a246cbb387d53dd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193024"
---
# <span data-ttu-id="73f42-103">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="73f42-103">Disconnect-WSMan</span></span>

## <span data-ttu-id="73f42-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="73f42-104">SYNOPSIS</span></span>
<span data-ttu-id="73f42-105">Desconecta o cliente do serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="73f42-105">Disconnects the client from the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="73f42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73f42-106">SYNTAX</span></span>

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="73f42-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73f42-107">DESCRIPTION</span></span>
<span data-ttu-id="73f42-108">O cmdlet **Disconnect-WSMan** desconecta o cliente do serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="73f42-108">The **Disconnect-WSMan** cmdlet disconnects the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="73f42-109">Se você salvou a sessão de WS-Management em uma variável, o objeto de sessão permanecerá na variável, mas o estado da sessão de WS-Management será fechado.</span><span class="sxs-lookup"><span data-stu-id="73f42-109">If you saved the WS-Management session in a variable, the session object remains in the variable, but the state of the WS-Management session is Closed.</span></span>
<span data-ttu-id="73f42-110">Você pode usar este cmdlet dentro do contexto do provedor WSMan para desconectar o cliente do serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="73f42-110">You can use this cmdlet within the context of the WSMan provider to disconnect the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="73f42-111">No entanto, você também pode usar este cmdlet para desconectar o serviço do WinRM em computadores remotos antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="73f42-111">However, you can also use this cmdlet to disconnect from the WinRM service on remote computers before you change to the WSMan provider.</span></span>

<span data-ttu-id="73f42-112">Para obter mais informações sobre como se conectar ao serviço WinRM em um computador remoto, consulte Connect-WSMan.</span><span class="sxs-lookup"><span data-stu-id="73f42-112">For more information about how to connect to the WinRM service on a remote computer, see Connect-WSMan.</span></span>

## <span data-ttu-id="73f42-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="73f42-113">EXAMPLES</span></span>

### <span data-ttu-id="73f42-114">Exemplo 1: excluir uma conexão com um computador remoto</span><span class="sxs-lookup"><span data-stu-id="73f42-114">Example 1: Delete a connection to a remote computer</span></span>

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

<span data-ttu-id="73f42-115">Esse comando exclui a conexão com o computador remoto chamado Server01.</span><span class="sxs-lookup"><span data-stu-id="73f42-115">This command deletes the connection to the remote computer named server01.</span></span>

<span data-ttu-id="73f42-116">Este cmdlet geralmente é usado dentro do contexto do provedor WSMan para se desconectar de um computador remoto, neste caso, o computador server01.</span><span class="sxs-lookup"><span data-stu-id="73f42-116">This cmdlet is generally used within the context of the WSMan provider to disconnect from a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="73f42-117">No entanto, você também pode usar **Disconnect-WSMan** para remover conexões a computadores remotos antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="73f42-117">However, you can also use **Disconnect-WSMan** to remove connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="73f42-118">Essas conexões não aparecem na lista ComputerName.</span><span class="sxs-lookup"><span data-stu-id="73f42-118">Those connections do not appear in the ComputerName list.</span></span>

## <span data-ttu-id="73f42-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73f42-119">PARAMETERS</span></span>

### <span data-ttu-id="73f42-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="73f42-120">-ComputerName</span></span>
<span data-ttu-id="73f42-121">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="73f42-121">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="73f42-122">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="73f42-122">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="73f42-123">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="73f42-123">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="73f42-124">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="73f42-124">The local computer is the default.</span></span>
<span data-ttu-id="73f42-125">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="73f42-125">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="73f42-126">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="73f42-126">You can pipe a value for this parameter to the cmdlet.</span></span>

<span data-ttu-id="73f42-127">Não é possível desconectar do host local.</span><span class="sxs-lookup"><span data-stu-id="73f42-127">You cannot disconnect from the local host.</span></span>
<span data-ttu-id="73f42-128">Ou seja, não é possível desconectar a conexão padrão ao computador local.</span><span class="sxs-lookup"><span data-stu-id="73f42-128">That is, you cannot disconnect the default connection to the local computer.</span></span>
<span data-ttu-id="73f42-129">No entanto, se você criar uma conexão separada com o computador local, por exemplo, usando o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="73f42-129">However, if you create a separate connection to the local computer, for example, by using the computer name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73f42-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="73f42-130">CommonParameters</span></span>
<span data-ttu-id="73f42-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73f42-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73f42-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73f42-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="73f42-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="73f42-133">INPUTS</span></span>

### <span data-ttu-id="73f42-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="73f42-134">None</span></span>
<span data-ttu-id="73f42-135">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="73f42-135">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="73f42-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="73f42-136">OUTPUTS</span></span>

### <span data-ttu-id="73f42-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="73f42-137">None</span></span>
<span data-ttu-id="73f42-138">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="73f42-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="73f42-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="73f42-139">NOTES</span></span>

## <span data-ttu-id="73f42-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="73f42-140">RELATED LINKS</span></span>

[<span data-ttu-id="73f42-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="73f42-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="73f42-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="73f42-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="73f42-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="73f42-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="73f42-144">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="73f42-144">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="73f42-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="73f42-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="73f42-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="73f42-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="73f42-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="73f42-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="73f42-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="73f42-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="73f42-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="73f42-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="73f42-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="73f42-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="73f42-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="73f42-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="73f42-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="73f42-152">Test-WSMan</span></span>](Test-WSMan.md)
