---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: 45a1aacd855ba1a2479fc3bf4d2ce991a87ddb09
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194791"
---
# <span data-ttu-id="c0939-103">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="c0939-103">Get-CimSession</span></span>

## <span data-ttu-id="c0939-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c0939-104">SYNOPSIS</span></span>
<span data-ttu-id="c0939-105">Obtém os objetos de sessão CIM da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c0939-105">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="c0939-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0939-106">SYNTAX</span></span>

### <span data-ttu-id="c0939-107">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="c0939-107">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="c0939-108">SessionIdset</span><span class="sxs-lookup"><span data-stu-id="c0939-108">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="c0939-109">InstanceIdset</span><span class="sxs-lookup"><span data-stu-id="c0939-109">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="c0939-110">Nome do</span><span class="sxs-lookup"><span data-stu-id="c0939-110">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="c0939-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c0939-111">DESCRIPTION</span></span>

<span data-ttu-id="c0939-112">Por padrão, o cmdlet obtém todas as sessões CIM criadas na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0939-112">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="c0939-113">Você pode usar os parâmetros de `Get-CimSession` para obter as sessões que são para computadores específicos ou pode identificar sessões por seus nomes ou outros identificadores.</span><span class="sxs-lookup"><span data-stu-id="c0939-113">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="c0939-114">`Get-CimSession` Não Obtém as sessões CIM que foram criadas em outras sessões do PowerShell ou que foram criadas em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="c0939-114">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="c0939-115">Para obter mais informações sobre sessões CIM, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="c0939-115">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="c0939-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c0939-116">EXAMPLES</span></span>

### <span data-ttu-id="c0939-117">Exemplo 1: obter sessões CIM da sessão atual do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0939-117">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="c0939-118">Este exemplo cria sessões CIM usando [New-CimSession](New-CimSession.md)e, em seguida, obtém as sessões CIM usando `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="c0939-118">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="c0939-119">Exemplo 2: obter as sessões CIM para um computador específico</span><span class="sxs-lookup"><span data-stu-id="c0939-119">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="c0939-120">Este exemplo obtém as sessões CIM que estão conectadas ao computador chamado **Server02** .</span><span class="sxs-lookup"><span data-stu-id="c0939-120">This example gets the CIM sessions that are connected to the computer named **Server02** .</span></span>

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="c0939-121">Exemplo 3: obter uma lista de sessões CIM e formatar a lista</span><span class="sxs-lookup"><span data-stu-id="c0939-121">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="c0939-122">Este exemplo obtém todas as sessões CIM na sessão atual do PowerShell e exibe uma tabela que contém apenas as propriedades **ComputerName** e **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="c0939-122">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="c0939-123">Exemplo 4: obter todas as sessões CIM que têm nomes específicos</span><span class="sxs-lookup"><span data-stu-id="c0939-123">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="c0939-124">Este exemplo obtém todas as sessões CIM que têm nomes que começam com o **serv** .</span><span class="sxs-lookup"><span data-stu-id="c0939-124">This example gets all CIM sessions that have names that begin with **serv** .</span></span>

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="c0939-125">Exemplo 5: obter uma sessão CIM específica</span><span class="sxs-lookup"><span data-stu-id="c0939-125">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="c0939-126">Este exemplo obtém a sessão CIM que tem uma **ID** de 2.</span><span class="sxs-lookup"><span data-stu-id="c0939-126">This example gets the CIM session that has an **Id** of 2.</span></span>

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## <span data-ttu-id="c0939-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c0939-127">PARAMETERS</span></span>

### <span data-ttu-id="c0939-128">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c0939-128">-ComputerName</span></span>

<span data-ttu-id="c0939-129">Especifica o nome do computador para o qual as sessões CIM serão conectadas.</span><span class="sxs-lookup"><span data-stu-id="c0939-129">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="c0939-130">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c0939-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c0939-131">-Id</span><span class="sxs-lookup"><span data-stu-id="c0939-131">-Id</span></span>

<span data-ttu-id="c0939-132">Especifica o identificador da sessão CIM a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="c0939-132">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="c0939-133">Para várias IDs, use vírgulas para separar as IDs ou use o operador de intervalo ( `..` ) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="c0939-133">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="c0939-134">Uma **ID** é um inteiro que identifica exclusivamente a sessão CIM dentro da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0939-134">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="c0939-135">Para obter mais informações sobre o operador Range, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="c0939-135">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="c0939-136">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="c0939-136">-InstanceId</span></span>

<span data-ttu-id="c0939-137">Especifica as IDs de instância da sessão CIM a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="c0939-137">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="c0939-138">**InstanceId** é um GUID (identificador globalmente exclusivo) que identifica exclusivamente uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="c0939-138">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="c0939-139">A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0939-139">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="c0939-140">A **InstanceId** é armazenada na propriedade **InstanceId** do objeto que representa uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="c0939-140">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="c0939-141">-Name</span><span class="sxs-lookup"><span data-stu-id="c0939-141">-Name</span></span>

<span data-ttu-id="c0939-142">Obtém uma ou mais sessões CIM que contêm os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="c0939-142">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="c0939-143">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c0939-143">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c0939-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c0939-144">CommonParameters</span></span>
<span data-ttu-id="c0939-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c0939-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c0939-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c0939-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c0939-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c0939-147">INPUTS</span></span>

### <span data-ttu-id="c0939-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c0939-148">None</span></span>

## <span data-ttu-id="c0939-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c0939-149">OUTPUTS</span></span>

### <span data-ttu-id="c0939-150">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="c0939-150">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="c0939-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c0939-151">NOTES</span></span>

## <span data-ttu-id="c0939-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c0939-152">RELATED LINKS</span></span>

[<span data-ttu-id="c0939-153">Format-Table</span><span class="sxs-lookup"><span data-stu-id="c0939-153">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="c0939-154">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="c0939-154">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="c0939-155">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="c0939-155">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="c0939-156">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="c0939-156">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

