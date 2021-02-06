---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: 0e531b3cc072b7cc1efe0ef06fb741326bf3a72b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598823"
---
# <span data-ttu-id="4207d-102">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="4207d-102">Get-CimSession</span></span>

## <span data-ttu-id="4207d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4207d-103">SYNOPSIS</span></span>
<span data-ttu-id="4207d-104">Obtém os objetos de sessão CIM da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4207d-104">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="4207d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4207d-105">SYNTAX</span></span>

### <span data-ttu-id="4207d-106">ComputerNameSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="4207d-106">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="4207d-107">SessionIdset</span><span class="sxs-lookup"><span data-stu-id="4207d-107">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="4207d-108">InstanceIdset</span><span class="sxs-lookup"><span data-stu-id="4207d-108">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="4207d-109">Nome do</span><span class="sxs-lookup"><span data-stu-id="4207d-109">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="4207d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4207d-110">DESCRIPTION</span></span>

<span data-ttu-id="4207d-111">Por padrão, o cmdlet obtém todas as sessões CIM criadas na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4207d-111">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="4207d-112">Você pode usar os parâmetros de `Get-CimSession` para obter as sessões que são para computadores específicos ou pode identificar sessões por seus nomes ou outros identificadores.</span><span class="sxs-lookup"><span data-stu-id="4207d-112">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="4207d-113">`Get-CimSession` Não Obtém as sessões CIM que foram criadas em outras sessões do PowerShell ou que foram criadas em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="4207d-113">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="4207d-114">Para obter mais informações sobre sessões CIM, consulte [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="4207d-114">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="4207d-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4207d-115">EXAMPLES</span></span>

### <span data-ttu-id="4207d-116">Exemplo 1: obter sessões CIM da sessão atual do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4207d-116">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="4207d-117">Este exemplo cria sessões CIM usando [New-CimSession](New-CimSession.md)e, em seguida, obtém as sessões CIM usando `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="4207d-117">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

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

### <span data-ttu-id="4207d-118">Exemplo 2: obter as sessões CIM para um computador específico</span><span class="sxs-lookup"><span data-stu-id="4207d-118">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="4207d-119">Este exemplo obtém as sessões CIM que estão conectadas ao computador chamado **Server02**.</span><span class="sxs-lookup"><span data-stu-id="4207d-119">This example gets the CIM sessions that are connected to the computer named **Server02**.</span></span>

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

### <span data-ttu-id="4207d-120">Exemplo 3: obter uma lista de sessões CIM e formatar a lista</span><span class="sxs-lookup"><span data-stu-id="4207d-120">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="4207d-121">Este exemplo obtém todas as sessões CIM na sessão atual do PowerShell e exibe uma tabela que contém apenas as propriedades **ComputerName** e **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="4207d-121">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="4207d-122">Exemplo 4: obter todas as sessões CIM que têm nomes específicos</span><span class="sxs-lookup"><span data-stu-id="4207d-122">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="4207d-123">Este exemplo obtém todas as sessões CIM que têm nomes que começam com o **serv**.</span><span class="sxs-lookup"><span data-stu-id="4207d-123">This example gets all CIM sessions that have names that begin with **serv**.</span></span>

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

### <span data-ttu-id="4207d-124">Exemplo 5: obter uma sessão CIM específica</span><span class="sxs-lookup"><span data-stu-id="4207d-124">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="4207d-125">Este exemplo obtém a sessão CIM que tem uma **ID** de 2.</span><span class="sxs-lookup"><span data-stu-id="4207d-125">This example gets the CIM session that has an **Id** of 2.</span></span>

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

## <span data-ttu-id="4207d-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4207d-126">PARAMETERS</span></span>

### <span data-ttu-id="4207d-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4207d-127">-ComputerName</span></span>

<span data-ttu-id="4207d-128">Especifica o nome do computador para o qual as sessões CIM serão conectadas.</span><span class="sxs-lookup"><span data-stu-id="4207d-128">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="4207d-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4207d-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4207d-130">-Id</span><span class="sxs-lookup"><span data-stu-id="4207d-130">-Id</span></span>

<span data-ttu-id="4207d-131">Especifica o identificador da sessão CIM a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="4207d-131">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="4207d-132">Para várias IDs, use vírgulas para separar as IDs ou use o operador de intervalo ( `..` ) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="4207d-132">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="4207d-133">Uma **ID** é um inteiro que identifica exclusivamente a sessão CIM dentro da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4207d-133">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="4207d-134">Para obter mais informações sobre o operador Range, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="4207d-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="4207d-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="4207d-135">-InstanceId</span></span>

<span data-ttu-id="4207d-136">Especifica as IDs de instância da sessão CIM a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="4207d-136">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="4207d-137">**InstanceId** é um GUID (identificador globalmente exclusivo) que identifica exclusivamente uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="4207d-137">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="4207d-138">A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4207d-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="4207d-139">A **InstanceId** é armazenada na propriedade **InstanceId** do objeto que representa uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="4207d-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="4207d-140">-Name</span><span class="sxs-lookup"><span data-stu-id="4207d-140">-Name</span></span>

<span data-ttu-id="4207d-141">Obtém uma ou mais sessões CIM que contêm os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="4207d-141">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="4207d-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4207d-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4207d-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4207d-143">CommonParameters</span></span>
<span data-ttu-id="4207d-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4207d-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4207d-145">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4207d-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4207d-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4207d-146">INPUTS</span></span>

### <span data-ttu-id="4207d-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4207d-147">None</span></span>

## <span data-ttu-id="4207d-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4207d-148">OUTPUTS</span></span>

### <span data-ttu-id="4207d-149">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="4207d-149">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="4207d-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4207d-150">NOTES</span></span>

## <span data-ttu-id="4207d-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4207d-151">RELATED LINKS</span></span>

[<span data-ttu-id="4207d-152">Format-Table</span><span class="sxs-lookup"><span data-stu-id="4207d-152">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="4207d-153">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="4207d-153">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="4207d-154">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="4207d-154">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="4207d-155">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="4207d-155">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

