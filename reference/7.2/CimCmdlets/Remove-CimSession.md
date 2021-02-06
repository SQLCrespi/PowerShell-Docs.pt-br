---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: a3ff2132c531df1ab19bf7149a55ea0df4a787a8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596168"
---
# <span data-ttu-id="94307-102">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="94307-102">Remove-CimSession</span></span>

## <span data-ttu-id="94307-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="94307-103">SYNOPSIS</span></span>
<span data-ttu-id="94307-104">Remove uma ou mais sessões CIM.</span><span class="sxs-lookup"><span data-stu-id="94307-104">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="94307-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94307-105">SYNTAX</span></span>

### <span data-ttu-id="94307-106">CimSessionSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="94307-106">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="94307-107">ComputerNameSet</span><span class="sxs-lookup"><span data-stu-id="94307-107">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="94307-108">SessionIdset</span><span class="sxs-lookup"><span data-stu-id="94307-108">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="94307-109">InstanceIdset</span><span class="sxs-lookup"><span data-stu-id="94307-109">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="94307-110">Nome do</span><span class="sxs-lookup"><span data-stu-id="94307-110">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="94307-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94307-111">DESCRIPTION</span></span>

<span data-ttu-id="94307-112">O `Remove-CimSession` cmdlet Remove um ou mais objetos de sessão CIM da sessão do PowerShell local.</span><span class="sxs-lookup"><span data-stu-id="94307-112">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="94307-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="94307-113">EXAMPLES</span></span>

### <span data-ttu-id="94307-114">Exemplo 1: remover todas as sessões CIM</span><span class="sxs-lookup"><span data-stu-id="94307-114">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="94307-115">Este exemplo recupera todas as sessões CIM disponíveis no computador local usando o cmdlet [Get-CimSession](Get-CimSession.md) e, em seguida, as remove usando o `Remove-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="94307-115">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="94307-116">Exemplo 2: remover uma sessão CIM específica</span><span class="sxs-lookup"><span data-stu-id="94307-116">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="94307-117">Este exemplo remove a sessão CIM que tem um valor de **ID** de 5.</span><span class="sxs-lookup"><span data-stu-id="94307-117">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="94307-118">Exemplo 3: mostrar a lista de sessões CIM a serem removidas usando o parâmetro WhatIf</span><span class="sxs-lookup"><span data-stu-id="94307-118">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="94307-119">Este exemplo usa o parâmetro comum **WhatIf** para especificar que a remoção não deve ser feita, mas apenas saída o que aconteceria se fosse feito.</span><span class="sxs-lookup"><span data-stu-id="94307-119">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="94307-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94307-120">PARAMETERS</span></span>

### <span data-ttu-id="94307-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="94307-121">-CimSession</span></span>

<span data-ttu-id="94307-122">Especifica os objetos de sessão das sessões CIM a serem fechadas.</span><span class="sxs-lookup"><span data-stu-id="94307-122">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="94307-123">Insira uma variável que contenha a sessão CIM ou um comando que cria ou obtém a sessão CIM, como os [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="94307-123">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="94307-124">Para obter mais informações, consulte [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="94307-124">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="94307-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="94307-125">-ComputerName</span></span>

<span data-ttu-id="94307-126">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="94307-126">Specifies an array of names of computers.</span></span> <span data-ttu-id="94307-127">Remove as sessões que se conectam aos computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="94307-127">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="94307-128">Você pode especificar um nome de domínio totalmente qualificado (FQDN) ou um nome NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="94307-128">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="94307-129">-Id</span><span class="sxs-lookup"><span data-stu-id="94307-129">-Id</span></span>

<span data-ttu-id="94307-130">Especifica a ID da sessão CIM a ser removida.</span><span class="sxs-lookup"><span data-stu-id="94307-130">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="94307-131">Especifique uma ou mais IDs separadas por vírgulas ou use o operador de intervalo ( `..` ) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="94307-131">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="94307-132">Uma **ID** é um inteiro que identifica exclusivamente a sessão CIM na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94307-132">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="94307-133">Para obter mais informações sobre o operador Range, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="94307-133">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="94307-134">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="94307-134">-InstanceId</span></span>

<span data-ttu-id="94307-135">Especifica a ID da instância da sessão CIM a ser removida.</span><span class="sxs-lookup"><span data-stu-id="94307-135">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="94307-136">**InstanceId** é um GUID (identificador global exclusivo) que identifica exclusivamente uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="94307-136">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="94307-137">A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94307-137">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="94307-138">A **InstanceId** é armazenada na propriedade **InstanceId** do objeto que representa uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="94307-138">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="94307-139">-Name</span><span class="sxs-lookup"><span data-stu-id="94307-139">-Name</span></span>

<span data-ttu-id="94307-140">Especifica o nome amigável da sessão CIM a ser removida.</span><span class="sxs-lookup"><span data-stu-id="94307-140">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="94307-141">Você pode usar caracteres curinga com esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94307-141">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="94307-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="94307-142">-Confirm</span></span>

<span data-ttu-id="94307-143">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94307-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="94307-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="94307-144">-WhatIf</span></span>

<span data-ttu-id="94307-145">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="94307-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="94307-146">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="94307-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="94307-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="94307-147">CommonParameters</span></span>

<span data-ttu-id="94307-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="94307-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94307-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="94307-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94307-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="94307-150">INPUTS</span></span>

### <span data-ttu-id="94307-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="94307-151">None</span></span>

<span data-ttu-id="94307-152">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="94307-152">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="94307-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="94307-153">OUTPUTS</span></span>

### <span data-ttu-id="94307-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="94307-154">System.Object</span></span>

<span data-ttu-id="94307-155">Esse cmdlet retorna um objeto que contém informações de sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="94307-155">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="94307-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="94307-156">NOTES</span></span>

## <span data-ttu-id="94307-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="94307-157">RELATED LINKS</span></span>

[<span data-ttu-id="94307-158">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="94307-158">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="94307-159">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="94307-159">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="94307-160">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="94307-160">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

