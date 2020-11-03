---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193917"
---
# <span data-ttu-id="453e0-103">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="453e0-103">Show-ControlPanelItem</span></span>

## <span data-ttu-id="453e0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="453e0-104">SYNOPSIS</span></span>
<span data-ttu-id="453e0-105">Abre itens do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="453e0-105">Opens control panel items.</span></span>

## <span data-ttu-id="453e0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="453e0-106">SYNTAX</span></span>

### <span data-ttu-id="453e0-107">Regularname (padrão)</span><span class="sxs-lookup"><span data-stu-id="453e0-107">RegularName (Default)</span></span>

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="453e0-108">Canônicaname</span><span class="sxs-lookup"><span data-stu-id="453e0-108">CanonicalName</span></span>

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="453e0-109">ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="453e0-109">ControlPanelItem</span></span>

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## <span data-ttu-id="453e0-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="453e0-110">DESCRIPTION</span></span>

<span data-ttu-id="453e0-111">O `Show-ControlPanelItem` cmdlet abre itens do painel de controle no computador local.</span><span class="sxs-lookup"><span data-stu-id="453e0-111">The `Show-ControlPanelItem` cmdlet opens control panel items on the local computer.</span></span> <span data-ttu-id="453e0-112">Você pode usá-lo para abrir itens do painel de controle por nome, categoria ou descrição, mesmo em sistemas que não têm uma interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="453e0-112">You can use it to open control panel items by name, category, or description, even on systems that do not have a user interface.</span></span> <span data-ttu-id="453e0-113">Você pode canalizar itens do painel de controle do `Get-ControlPanelItem` cmdlet para `Show-ControlPanelItem` .</span><span class="sxs-lookup"><span data-stu-id="453e0-113">You can pipe control panel items from the `Get-ControlPanelItem` cmdlet to `Show-ControlPanelItem`.</span></span>

<span data-ttu-id="453e0-114">`Show-ControlPanelItem` pesquisa somente os itens do painel de controle que podem ser abertos no sistema.</span><span class="sxs-lookup"><span data-stu-id="453e0-114">`Show-ControlPanelItem` searches only control panel items that can be opened on the system.</span></span> <span data-ttu-id="453e0-115">Em computadores que não têm o **painel de controle** ou o **Explorador de arquivos** , o `Show-ControlPanelItem` pesquisa somente os itens do painel de controle que podem ser abertos sem esses componentes.</span><span class="sxs-lookup"><span data-stu-id="453e0-115">On computers that do not have **Control Panel** or **File Explorer** , `Show-ControlPanelItem` searches only control panel items that can open without these components.</span></span>

<span data-ttu-id="453e0-116">Esse cmdlet foi introduzido no Windows PowerShell 3,0 e funciona no Windows 8, no Windows Server 2012 e em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="453e0-116">This cmdlet was introduced in Windows PowerShell 3.0 and works on Windows 8, Windows Server 2012, and higher versions.</span></span>

## <span data-ttu-id="453e0-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="453e0-117">EXAMPLES</span></span>

### <span data-ttu-id="453e0-118">Exemplo 1: mostrar um item do painel de controle</span><span class="sxs-lookup"><span data-stu-id="453e0-118">Example 1: Show a control panel item</span></span>

<span data-ttu-id="453e0-119">Este exemplo inicia o item do painel de controle de **reprodução automática** .</span><span class="sxs-lookup"><span data-stu-id="453e0-119">This example launches the **AutoPlay** control panel item.</span></span>

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### <span data-ttu-id="453e0-120">Exemplo 2: canalizar um item do painel de controle para este cmdlet</span><span class="sxs-lookup"><span data-stu-id="453e0-120">Example 2: Pipe a control panel item to this cmdlet</span></span>

<span data-ttu-id="453e0-121">Este exemplo abre o item do painel de controle do **Windows Defender firewall** no computador local.</span><span class="sxs-lookup"><span data-stu-id="453e0-121">This example opens the **Windows Defender Firewall** control panel item on the local computer.</span></span>
<span data-ttu-id="453e0-122">O nome do item do painel de controle do firewall do Windows foi alterado nas versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="453e0-122">The name of the Windows Firewall control panel item has changed over the versions of Windows.</span></span> <span data-ttu-id="453e0-123">Este exemplo usa um padrão curinga para localizar o item do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="453e0-123">This example uses a wildcard pattern to find the control panel item.</span></span>

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="453e0-124">`Get-ControlPanelItem` Obtém o item do painel de controle e o `Show-ControlPanelItem` cmdlet o abre.</span><span class="sxs-lookup"><span data-stu-id="453e0-124">`Get-ControlPanelItem` gets the control panel item and the `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="453e0-125">Exemplo 3: usar um nome de arquivo para abrir um item do painel de controle</span><span class="sxs-lookup"><span data-stu-id="453e0-125">Example 3: Use a file name to open a control panel item</span></span>

<span data-ttu-id="453e0-126">Este exemplo abre o item do painel de controle **programas e recursos** usando seu nome de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="453e0-126">This example opens the **Programs and Features** control panel item by using its application name.</span></span>

```powershell
appwiz.cpl
```

<span data-ttu-id="453e0-127">Esse método é uma alternativa ao uso de um `Show-ControlPanelItem` comando.</span><span class="sxs-lookup"><span data-stu-id="453e0-127">This method is an alternative to using a `Show-ControlPanelItem` command.</span></span>

> [!NOTE]
> <span data-ttu-id="453e0-128">No PowerShell, você pode omitir a extensão de arquivo. cpl para arquivos do painel de controle porque ele está incluído no valor da `$env:PathExt` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="453e0-128">In PowerShell, you can omit the .cpl file extension for control panel files because it's included in the value of the `$env:PathExt` environment variable.</span></span>

## <span data-ttu-id="453e0-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="453e0-129">PARAMETERS</span></span>

### <span data-ttu-id="453e0-130">-Canôniconame</span><span class="sxs-lookup"><span data-stu-id="453e0-130">-CanonicalName</span></span>

<span data-ttu-id="453e0-131">Especifica itens do painel de controle usando os nomes canônicos ou padrões de nome especificados.</span><span class="sxs-lookup"><span data-stu-id="453e0-131">Specifies control panel items by using the specified canonical names or name patterns.</span></span> <span data-ttu-id="453e0-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="453e0-132">Wildcard characters are permitted.</span></span> <span data-ttu-id="453e0-133">Se você inserir vários nomes, esse cmdlet abrirá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador **or** .</span><span class="sxs-lookup"><span data-stu-id="453e0-133">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

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

### <span data-ttu-id="453e0-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="453e0-134">-InputObject</span></span>

<span data-ttu-id="453e0-135">Especifica os itens do painel de controle a serem abertos por meio do envio de objetos de item do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="453e0-135">Specifies control panel items to open by submitting control panel item objects.</span></span> <span data-ttu-id="453e0-136">Insira uma variável que contenha objetos de item do painel de controle ou digite um comando ou uma expressão que obtenha objetos de item do painel de controle, como `Get-ControlPanelItem` .</span><span class="sxs-lookup"><span data-stu-id="453e0-136">Enter a variable that contains control panel item objects, or type a command or expression that gets control panel item objects, such as `Get-ControlPanelItem`.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="453e0-137">-Name</span><span class="sxs-lookup"><span data-stu-id="453e0-137">-Name</span></span>

<span data-ttu-id="453e0-138">Especifica os nomes dos itens do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="453e0-138">Specifies names of control panel items.</span></span> <span data-ttu-id="453e0-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="453e0-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="453e0-140">Se você inserir vários nomes, esse cmdlet abrirá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador **or** .</span><span class="sxs-lookup"><span data-stu-id="453e0-140">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="453e0-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="453e0-141">CommonParameters</span></span>

<span data-ttu-id="453e0-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="453e0-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="453e0-143">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="453e0-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="453e0-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="453e0-144">INPUTS</span></span>

### <span data-ttu-id="453e0-145">System. String, Microsoft. PowerShell. Commands. ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="453e0-145">System.String, Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="453e0-146">É possível canalizar um nome ou objeto de item do painel de controle para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="453e0-146">You can pipe a name or control panel item object to this cmdlet.</span></span>

## <span data-ttu-id="453e0-147">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="453e0-147">OUTPUTS</span></span>

### <span data-ttu-id="453e0-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="453e0-148">None</span></span>

<span data-ttu-id="453e0-149">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="453e0-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="453e0-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="453e0-150">NOTES</span></span>

## <span data-ttu-id="453e0-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="453e0-151">RELATED LINKS</span></span>

[<span data-ttu-id="453e0-152">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="453e0-152">Get-ControlPanelItem</span></span>](Get-ControlPanelItem.md)
