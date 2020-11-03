---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194185"
---
# <span data-ttu-id="a41ef-103">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a41ef-103">Get-ControlPanelItem</span></span>

## <span data-ttu-id="a41ef-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a41ef-104">SYNOPSIS</span></span>
<span data-ttu-id="a41ef-105">Obtém itens do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="a41ef-105">Gets control panel items.</span></span>

## <span data-ttu-id="a41ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a41ef-106">SYNTAX</span></span>

### <span data-ttu-id="a41ef-107">Regularname (padrão)</span><span class="sxs-lookup"><span data-stu-id="a41ef-107">RegularName (Default)</span></span>

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a41ef-108">Canônicaname</span><span class="sxs-lookup"><span data-stu-id="a41ef-108">CanonicalName</span></span>

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a41ef-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a41ef-109">DESCRIPTION</span></span>

<span data-ttu-id="a41ef-110">O `Get-ControlPanelItem` cmdlet obtém itens do painel de controle no computador local.</span><span class="sxs-lookup"><span data-stu-id="a41ef-110">The `Get-ControlPanelItem` cmdlet gets control panel items on the local computer.</span></span> <span data-ttu-id="a41ef-111">Você pode usá-lo para localizar os itens do painel de controle por nome, categoria ou descrição, mesmo em sistemas que não têm uma interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="a41ef-111">You can use it to find control panel items by name, category, or description, even on systems that do not have a user interface.</span></span>

<span data-ttu-id="a41ef-112">Esse cmdlet obtém apenas os itens do painel de controle que podem ser abertos no sistema.</span><span class="sxs-lookup"><span data-stu-id="a41ef-112">This cmdlet gets only the control panel items that can be opened on the system.</span></span> <span data-ttu-id="a41ef-113">Em computadores que não têm o painel de controle ou o explorador de arquivos, esse cmdlet obtém apenas os itens do painel de controle que podem ser abertos sem esses componentes.</span><span class="sxs-lookup"><span data-stu-id="a41ef-113">On computers that do not have Control Panel or File Explorer, this cmdlet gets only control panel items that can open without these components.</span></span>

<span data-ttu-id="a41ef-114">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a41ef-114">This cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="a41ef-115">Ele funciona apenas no Windows 8 e no Windows Server 2012 e mais recente.</span><span class="sxs-lookup"><span data-stu-id="a41ef-115">It works only on Windows 8 and Windows Server 2012 and newer.</span></span>

## <span data-ttu-id="a41ef-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a41ef-116">EXAMPLES</span></span>

### <span data-ttu-id="a41ef-117">Exemplo 1: obter todos os itens do painel de controle</span><span class="sxs-lookup"><span data-stu-id="a41ef-117">Example 1: Get all control panel items</span></span>

<span data-ttu-id="a41ef-118">Este comando obtém todos os itens do Painel de controle no computador local.</span><span class="sxs-lookup"><span data-stu-id="a41ef-118">This command gets all control panel items on the local computer.</span></span>

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### <span data-ttu-id="a41ef-119">Exemplo 2: obter itens do painel de controle por nome</span><span class="sxs-lookup"><span data-stu-id="a41ef-119">Example 2: Get control panel items by name</span></span>

<span data-ttu-id="a41ef-120">Este exemplo obtém itens do painel de controle que têm programa ou aplicativo em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="a41ef-120">This example gets control panel items that have Program or App in their names.</span></span>

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### <span data-ttu-id="a41ef-121">Exemplo 3: obter itens do painel de controle por categoria</span><span class="sxs-lookup"><span data-stu-id="a41ef-121">Example 3: Get control panel items by category</span></span>

<span data-ttu-id="a41ef-122">Esse comando obtém todos os itens do painel de controle em categorias que têm segurança em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="a41ef-122">This command gets all control panel items in categories that have Security in their names.</span></span>

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### <span data-ttu-id="a41ef-123">Exemplo 4: abrir um item do painel de controle</span><span class="sxs-lookup"><span data-stu-id="a41ef-123">Example 4: Open a control panel item</span></span>

<span data-ttu-id="a41ef-124">Este exemplo abre o item do painel de controle do firewall do Windows no computador local.</span><span class="sxs-lookup"><span data-stu-id="a41ef-124">This example opens the Windows Firewall control panel item on the local computer.</span></span>

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="a41ef-125">O `Get-ControlPanelItem` cmdlet obtém o item do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="a41ef-125">The `Get-ControlPanelItem` cmdlet gets the control panel item.</span></span> <span data-ttu-id="a41ef-126">O `Show-ControlPanelItem` cmdlet o abre.</span><span class="sxs-lookup"><span data-stu-id="a41ef-126">The `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="a41ef-127">Exemplo 5: obter itens do painel de controle em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="a41ef-127">Example 5: Get control panel items on a remote computer</span></span>

<span data-ttu-id="a41ef-128">Este exemplo obtém o Criptografia de Unidade de Disco BitLocker item do painel de controle no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="a41ef-128">This example gets the BitLocker Drive Encryption control panel item on the Server01 remote computer.</span></span>
<span data-ttu-id="a41ef-129">O `Invoke-Command` cmdlet executa o `Get-ControlPanelItem` cmdlet remotamente.</span><span class="sxs-lookup"><span data-stu-id="a41ef-129">The `Invoke-Command` cmdlet runs the `Get-ControlPanelItem` cmdlet remotely.</span></span>

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### <span data-ttu-id="a41ef-130">Exemplo 6: Pesquisar as descrições dos itens do painel de controle</span><span class="sxs-lookup"><span data-stu-id="a41ef-130">Example 6: Search the descriptions of control panel items</span></span>

<span data-ttu-id="a41ef-131">Este exemplo pesquisa a propriedade **Description** dos itens do painel de controle para obter apenas os que contêm o nome do **dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="a41ef-131">This example searches the **Description** property of the control panel items to get only those that contain the name **Device** .</span></span>

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

<span data-ttu-id="a41ef-132">O `Get-ControlPanelItem` cmdlet obtém todos os itens do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="a41ef-132">The `Get-ControlPanelItem` cmdlet gets all control panel items.</span></span> <span data-ttu-id="a41ef-133">O `Where-Object` cmdlet filtra os itens pelo valor da propriedade **Description** .</span><span class="sxs-lookup"><span data-stu-id="a41ef-133">The `Where-Object` cmdlet filters the items by the value of the **Description** property.</span></span>

## <span data-ttu-id="a41ef-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a41ef-134">PARAMETERS</span></span>

### <span data-ttu-id="a41ef-135">-Canôniconame</span><span class="sxs-lookup"><span data-stu-id="a41ef-135">-CanonicalName</span></span>

<span data-ttu-id="a41ef-136">Especifica, como uma matriz de cadeia de caracteres, os itens do painel de controle por seus nomes canônicos ou padrões de nome que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="a41ef-136">Specifies, as a string array, the control panel items by their canonical names or name patterns that this cmdlet gets.</span></span> <span data-ttu-id="a41ef-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a41ef-137">Wildcards are permitted.</span></span> <span data-ttu-id="a41ef-138">Se você inserir vários nomes, esse cmdlet obterá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador "or".</span><span class="sxs-lookup"><span data-stu-id="a41ef-138">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span>

<span data-ttu-id="a41ef-139">Por padrão, esse cmdlet obtém todos os itens do painel de controle no sistema.</span><span class="sxs-lookup"><span data-stu-id="a41ef-139">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a41ef-140">-Categoria</span><span class="sxs-lookup"><span data-stu-id="a41ef-140">-Category</span></span>

<span data-ttu-id="a41ef-141">Especifica, como uma matriz de cadeia de caracteres, as categorias dos itens do painel de controle nas categorias especificadas que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="a41ef-141">Specifies, as a string array, the categories of the control panel items in the specified categories that this cmdlet gets.</span></span> <span data-ttu-id="a41ef-142">Digite um nome de categoria ou o padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="a41ef-142">Enter a category name or name pattern.</span></span> <span data-ttu-id="a41ef-143">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a41ef-143">Wildcards are permitted.</span></span> <span data-ttu-id="a41ef-144">Se você inserir vários nomes, esse cmdlet obterá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador "or".</span><span class="sxs-lookup"><span data-stu-id="a41ef-144">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span> <span data-ttu-id="a41ef-145">Por padrão, esse cmdlet obtém todos os itens do painel de controle no sistema.</span><span class="sxs-lookup"><span data-stu-id="a41ef-145">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a41ef-146">-Name</span><span class="sxs-lookup"><span data-stu-id="a41ef-146">-Name</span></span>

<span data-ttu-id="a41ef-147">Especifica, como uma matriz de cadeia de caracteres, os nomes ou padrões de nome do painel de controle que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="a41ef-147">Specifies, as a string array, the names or name patterns of the control panel that this cmdlet gets.</span></span>
<span data-ttu-id="a41ef-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a41ef-148">Wildcards are permitted.</span></span> <span data-ttu-id="a41ef-149">Você também pode canalizar um nome ou padrão de nome para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a41ef-149">You can also pipe a name or name pattern to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a41ef-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a41ef-150">CommonParameters</span></span>

<span data-ttu-id="a41ef-151">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a41ef-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a41ef-152">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a41ef-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a41ef-153">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a41ef-153">INPUTS</span></span>

### <span data-ttu-id="a41ef-154">System.String</span><span class="sxs-lookup"><span data-stu-id="a41ef-154">System.String</span></span>

<span data-ttu-id="a41ef-155">É possível canalizar um nome ou padrão de nome para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a41ef-155">You can pipe a name or name pattern to this cmdlet.</span></span>

## <span data-ttu-id="a41ef-156">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a41ef-156">OUTPUTS</span></span>

### <span data-ttu-id="a41ef-157">Microsoft. PowerShell. Commands. ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a41ef-157">Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="a41ef-158">Esse cmdlet obtém itens do painel de controle no computador local.</span><span class="sxs-lookup"><span data-stu-id="a41ef-158">This cmdlet gets control panel items on the local computer.</span></span>

## <span data-ttu-id="a41ef-159">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a41ef-159">NOTES</span></span>

## <span data-ttu-id="a41ef-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a41ef-160">RELATED LINKS</span></span>

[<span data-ttu-id="a41ef-161">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a41ef-161">Show-ControlPanelItem</span></span>](Show-ControlPanelItem.md)
