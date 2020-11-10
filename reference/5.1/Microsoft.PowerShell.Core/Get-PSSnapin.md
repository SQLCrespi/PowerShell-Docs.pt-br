---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 156cadecd87910e3c3312e84929b16709770641d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388664"
---
# <span data-ttu-id="122b5-103">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="122b5-103">Get-PSSnapin</span></span>

## <span data-ttu-id="122b5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="122b5-104">SYNOPSIS</span></span>
<span data-ttu-id="122b5-105">Obtém os snap-ins do Windows PowerShell presentes no computador.</span><span class="sxs-lookup"><span data-stu-id="122b5-105">Gets the Windows PowerShell snap-ins on the computer.</span></span>

## <span data-ttu-id="122b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="122b5-106">SYNTAX</span></span>

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## <span data-ttu-id="122b5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="122b5-107">DESCRIPTION</span></span>

<span data-ttu-id="122b5-108">O `Get-PSSnapin` cmdlet obtém os snap-ins do Windows PowerShell que foram adicionados à sessão atual ou que foram registrados no sistema.</span><span class="sxs-lookup"><span data-stu-id="122b5-108">The `Get-PSSnapin` cmdlet gets the Windows PowerShell snap-ins that have been added to the current session or that have been registered on the system.</span></span> <span data-ttu-id="122b5-109">Esse cmdlet lista os snap-ins na ordem em que são detectados.</span><span class="sxs-lookup"><span data-stu-id="122b5-109">This cmdlet lists the snap-ins in the order in which they are detected.</span></span>

<span data-ttu-id="122b5-110">`Get-PSSnapin` Obtém apenas snap-ins registrados. Para registrar um snap-in do Windows PowerShell, use a ferramenta InstallUtil incluída com o Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="122b5-110">`Get-PSSnapin` gets only registered snap-ins. To register a Windows PowerShell snap-in, use the InstallUtil tool included with the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="122b5-111">Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="122b5-111">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="122b5-112">A partir do Windows PowerShell 3,0, os comandos principais incluídos no Windows PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="122b5-112">Starting in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="122b5-113">A exceção é o **Microsoft.PowerShell.Core** , que é um snap-in (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="122b5-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="122b5-114">Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="122b5-115">Os módulos são importados automaticamente no primeiro uso e você pode usar o `Import-Module` cmdlet para importá-los.</span><span class="sxs-lookup"><span data-stu-id="122b5-115">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>

## <span data-ttu-id="122b5-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="122b5-116">EXAMPLES</span></span>

### <span data-ttu-id="122b5-117">Exemplo 1: obter snap-ins que estão carregados no momento</span><span class="sxs-lookup"><span data-stu-id="122b5-117">Example 1: Get snap-ins that are currently loaded</span></span>

```
PS C:\> Get-PSSnapIn
```

<span data-ttu-id="122b5-118">Esse comando obtém os snap-ins do Windows PowerShell que estão atualmente carregados na sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-118">This command gets the Windows PowerShell snap-ins that are currently loaded in the session.</span></span> <span data-ttu-id="122b5-119">Isso inclui os snap-ins instalados com o Windows PowerShell e aqueles que foram adicionados à sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-119">This includes the snap-ins that are installed with Windows PowerShell and those that have been added to the session.</span></span>

### <span data-ttu-id="122b5-120">Exemplo 2: obter snap-ins que foram registrados</span><span class="sxs-lookup"><span data-stu-id="122b5-120">Example 2: Get snap-ins that have been registered</span></span>

```
PS C:\> get-PSSnapIn -Registered
```

<span data-ttu-id="122b5-121">Esse comando obtém os snap-ins do Windows PowerShell que foram registrados no computador, incluindo aqueles que já foram adicionados à sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-121">This command gets the Windows PowerShell snap-ins that have been registered on the computer, including those that have already been added to the session.</span></span> <span data-ttu-id="122b5-122">A saída não inclui snap-ins que são instalados com o Windows PowerShell ou do snap-ins de bibliotecas de vínculo dinâmico (DLLs) do Windows PowerShell que ainda não foram registrados no sistema.</span><span class="sxs-lookup"><span data-stu-id="122b5-122">The output does not include snap-ins that are installed with Windows PowerShell or Windows PowerShell snap-in dynamic-link libraries (DLLs) that have not yet been registered on the system.</span></span>

### <span data-ttu-id="122b5-123">Exemplo 3: obter snap-ins atuais que correspondem a uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="122b5-123">Example 3: Get current snap-ins that match a string</span></span>

```
PS C:\> Get-PSSnapIn -Name smp*
```

<span data-ttu-id="122b5-124">Esse comando obtém os snap-ins do Windows PowerShell na sessão atual que têm nomes que começam com SMP.</span><span class="sxs-lookup"><span data-stu-id="122b5-124">This command gets the Windows PowerShell snap-ins in the current session that have names that begin with smp.</span></span>

## <span data-ttu-id="122b5-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="122b5-125">PARAMETERS</span></span>

### <span data-ttu-id="122b5-126">-Name</span><span class="sxs-lookup"><span data-stu-id="122b5-126">-Name</span></span>

<span data-ttu-id="122b5-127">Especifica uma matriz de nomes de snap-in.</span><span class="sxs-lookup"><span data-stu-id="122b5-127">Specifies an array of snap-in names.</span></span> <span data-ttu-id="122b5-128">Esse cmdlet obtém apenas os snap-ins do Windows PowerShell especificados. Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="122b5-128">This cmdlet gets only the specified Windows PowerShell snap-ins. Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="122b5-129">-Registrado</span><span class="sxs-lookup"><span data-stu-id="122b5-129">-Registered</span></span>

<span data-ttu-id="122b5-130">Indica que esse cmdlet obtém os snap-ins do Windows PowerShell que foram registrados no sistema, mesmo que ainda não tenham sido adicionados à sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-130">Indicates that this cmdlet gets the Windows PowerShell snap-ins that have been registered on the system even if they have not yet been added to the session.</span></span>

<span data-ttu-id="122b5-131">Os snap-ins instalados com o Windows PowerShell não aparecem nessa lista.</span><span class="sxs-lookup"><span data-stu-id="122b5-131">The snap-ins that are installed with Windows PowerShell do not appear in this list.</span></span>

<span data-ttu-id="122b5-132">Sem esse parâmetro, `Get-PSSnapin` o Obtém os snap-ins do Windows PowerShell que foram adicionados à sessão.</span><span class="sxs-lookup"><span data-stu-id="122b5-132">Without this parameter, `Get-PSSnapin` gets the Windows PowerShell snap-ins that have been added to the session.</span></span>

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

### <span data-ttu-id="122b5-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="122b5-133">CommonParameters</span></span>

<span data-ttu-id="122b5-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="122b5-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="122b5-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="122b5-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="122b5-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="122b5-136">INPUTS</span></span>

### <span data-ttu-id="122b5-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="122b5-137">None</span></span>
<span data-ttu-id="122b5-138">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="122b5-138">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="122b5-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="122b5-139">OUTPUTS</span></span>

### <span data-ttu-id="122b5-140">System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="122b5-140">System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="122b5-141">`Get-PSSnapin` Retorna um objeto para cada snap-in que obtém.</span><span class="sxs-lookup"><span data-stu-id="122b5-141">`Get-PSSnapin` returns an object for each snap-in that it gets.</span></span>

## <span data-ttu-id="122b5-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="122b5-142">NOTES</span></span>

<span data-ttu-id="122b5-143">A partir do Windows PowerShell 3,0, os comandos principais instalados com o Windows PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="122b5-143">Starting in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="122b5-144">No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do Windows PowerShell, os comandos principais são empacotados em snap-ins ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="122b5-144">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins ( **PSSnapin** ).</span></span> <span data-ttu-id="122b5-145">A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in.</span><span class="sxs-lookup"><span data-stu-id="122b5-145">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="122b5-146">Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.</span><span class="sxs-lookup"><span data-stu-id="122b5-146">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

 <span data-ttu-id="122b5-147">Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).</span><span class="sxs-lookup"><span data-stu-id="122b5-147">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).</span></span>

## <span data-ttu-id="122b5-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="122b5-148">RELATED LINKS</span></span>

[<span data-ttu-id="122b5-149">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="122b5-149">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="122b5-150">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="122b5-150">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
