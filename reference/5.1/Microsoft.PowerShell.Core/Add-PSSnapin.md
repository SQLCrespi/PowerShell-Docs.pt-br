---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193347"
---
# <span data-ttu-id="01bdc-103">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="01bdc-103">Add-PSSnapin</span></span>

## <span data-ttu-id="01bdc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="01bdc-104">SYNOPSIS</span></span>
<span data-ttu-id="01bdc-105">Adiciona um ou mais snap-ins do Windows PowerShell à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="01bdc-105">Adds one or more Windows PowerShell snap-ins to the current session.</span></span>

## <span data-ttu-id="01bdc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01bdc-106">SYNTAX</span></span>

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="01bdc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01bdc-107">DESCRIPTION</span></span>

<span data-ttu-id="01bdc-108">O `Add-PSSnapin` cmdlet adiciona snap-ins do Windows PowerShell registrados à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="01bdc-108">The `Add-PSSnapin` cmdlet adds registered Windows PowerShell snap-ins to the current session.</span></span> <span data-ttu-id="01bdc-109">Depois que os snap-ins são adicionados, você pode usar os cmdlets e provedores compatíveis com os snap-ins da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="01bdc-109">After the snap-ins are added, you can use the cmdlets and providers that the snap-ins support in the current session.</span></span>

<span data-ttu-id="01bdc-110">Para adicionar o snap-in a todas as sessões futuras do Windows PowerShell, adicione um `Add-PSSnapin` comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01bdc-110">To add the snap-in to all future Windows PowerShell sessions, add an `Add-PSSnapin` command to your Windows PowerShell profile.</span></span> <span data-ttu-id="01bdc-111">Para obter mais informações, consulte [about_Profiles](about/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="01bdc-111">For more information, see [about_Profiles](about/about_Profiles.md).</span></span>

<span data-ttu-id="01bdc-112">A partir do Windows PowerShell 3.0, os comandos principais que estão incluídos no Windows PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="01bdc-112">Beginning in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="01bdc-113">A exceção é o **Microsoft.PowerShell.Core** , que é um snap-in (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="01bdc-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="01bdc-114">Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="01bdc-115">Os módulos são importados automaticamente no primeiro uso e você pode usar o cmdlet Import-Module para importá-los.</span><span class="sxs-lookup"><span data-stu-id="01bdc-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="01bdc-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="01bdc-116">EXAMPLES</span></span>

### <span data-ttu-id="01bdc-117">Exemplo 1: Adicionar Snap-ins</span><span class="sxs-lookup"><span data-stu-id="01bdc-117">Example 1: Add snap-ins</span></span>

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

<span data-ttu-id="01bdc-118">Este comando adiciona os snap-ins do Microsoft Exchange e o Active Directory para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="01bdc-118">This command adds the Microsoft Exchange and Active Directory snap-ins to the current session.</span></span>

### <span data-ttu-id="01bdc-119">Exemplo 2: adicionar todos os snap-ins registrados</span><span class="sxs-lookup"><span data-stu-id="01bdc-119">Example 2: Add all the registered snap-ins</span></span>

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

<span data-ttu-id="01bdc-120">Este comando adiciona todos os snap-ins registrados do Windows PowerShell à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-120">This command adds all of the registered Windows PowerShell snap-ins to the session.</span></span> <span data-ttu-id="01bdc-121">Ele usa o cmdlet Get-PSSnapin com o parâmetro **Registered** para obter objetos que representam cada um dos snap-ins registrados. O operador de pipeline (|) passa o resultado para `Add-PSSnapin` , que os adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-121">It uses the Get-PSSnapin cmdlet with the **Registered** parameter to get objects representing each of the registered snap-ins. The pipeline operator (|) passes the result to `Add-PSSnapin`, which adds them to the session.</span></span> <span data-ttu-id="01bdc-122">O parâmetro **PassThru** retorna objetos que representam cada um dos snap-ins adicionados.</span><span class="sxs-lookup"><span data-stu-id="01bdc-122">The **PassThru** parameter returns objects that represent each of the added snap-ins.</span></span>

### <span data-ttu-id="01bdc-123">Exemplo 3: registrar um snap-in e adicioná-lo</span><span class="sxs-lookup"><span data-stu-id="01bdc-123">Example 3: Register a snap-in and add it</span></span>

<span data-ttu-id="01bdc-124">O primeiro comando obtém snap-ins que foram adicionados à sessão atual que incluem os snap-ins instalados com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01bdc-124">The first command gets snap-ins that have been added to the current session that include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="01bdc-125">Neste exemplo, ManagementFeatures não é retornado.</span><span class="sxs-lookup"><span data-stu-id="01bdc-125">In this example, ManagementFeatures is not returned.</span></span> <span data-ttu-id="01bdc-126">Isso indica que não foi adicionado à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-126">This indicates that it has not been added to the session.</span></span>

<span data-ttu-id="01bdc-127">O segundo comando obtém snap-ins que foram registrados no seu sistema, o que inclui aqueles que já foram adicionados à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-127">The second command gets snap-ins that have been registered on your system, which includes those that have already been added to the session.</span></span> <span data-ttu-id="01bdc-128">Ele não inclui os snap-ins instalados com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01bdc-128">It does not include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="01bdc-129">Nesse caso, o comando não retorna nenhum snap-in. Isso indica que o snap-in ManagementFeatures não foi registrado no sistema.</span><span class="sxs-lookup"><span data-stu-id="01bdc-129">In this case, the command does not return any snap-ins. This indicates that the ManagementFeatures snapin has not been registered on the system.</span></span>

<span data-ttu-id="01bdc-130">O terceiro comando cria um alias, InstallUtil, para o caminho da ferramenta InstallUtil no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01bdc-130">The third command creates an alias, installutil, for the path of the InstallUtil tool in .NET Framework.</span></span>

<span data-ttu-id="01bdc-131">O quarto comando usa a ferramenta InstallUtil para registrar o snap-in.</span><span class="sxs-lookup"><span data-stu-id="01bdc-131">The fourth command uses the InstallUtil tool to register the snap-in.</span></span> <span data-ttu-id="01bdc-132">O comando especifica o caminho do ManagementCmdlets.dll, o nome do arquivo ou do módulo do snap-in do.</span><span class="sxs-lookup"><span data-stu-id="01bdc-132">The command specifies the path of ManagementCmdlets.dll, the filename or module name of the snap-in.</span></span>

<span data-ttu-id="01bdc-133">O quinto comando é o mesmo que o segundo comando.</span><span class="sxs-lookup"><span data-stu-id="01bdc-133">The fifth command is the same as the second command.</span></span> <span data-ttu-id="01bdc-134">Dessa vez, você vai usá-lo para verificar se o snap-in ManagementCmdlets está registrado.</span><span class="sxs-lookup"><span data-stu-id="01bdc-134">This time, you use it to verify that the ManagementCmdlets snap-in is registered.</span></span>

<span data-ttu-id="01bdc-135">O sexto comando usa o `Add-PSSnapin` cmdlet para adicionar o snap-in ManagementFeatures à sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-135">The sixth command uses the `Add-PSSnapin` cmdlet to add the ManagementFeatures snap-in to the session.</span></span> <span data-ttu-id="01bdc-136">Especifica o nome do snap-in, ManagementFeatures, não o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="01bdc-136">It specifies the name of the snap-in, ManagementFeatures, not the file name.</span></span>

<span data-ttu-id="01bdc-137">Para verificar se o snap-in foi adicionado à sessão, o sétimo comando usa o parâmetro **Module** do cmdlet Get-Command.</span><span class="sxs-lookup"><span data-stu-id="01bdc-137">To verify that the snap-in is added to the session, the seventh command uses the **Module** parameter of the Get-Command cmdlet.</span></span> <span data-ttu-id="01bdc-138">Ele exibe os itens que foram adicionados à sessão por um snap-in ou módulo.</span><span class="sxs-lookup"><span data-stu-id="01bdc-138">It displays the items that were added to the session by a snap-in or module.</span></span>

<span data-ttu-id="01bdc-139">Você também pode usar a propriedade **PSSnapin** do objeto que o `Get-Command` cmdlet retorna para localizar o snap-in ou o módulo no qual um cmdlet foi originado.</span><span class="sxs-lookup"><span data-stu-id="01bdc-139">You can also use the **PSSnapin** property of the object that the `Get-Command` cmdlet returns to find the snap-in or module in which a cmdlet originated.</span></span> <span data-ttu-id="01bdc-140">O oitavo comando usa a notação de ponto para localizar o valor da propriedade PSSnapin do cmdlet Set-Alias.</span><span class="sxs-lookup"><span data-stu-id="01bdc-140">The eighth command uses dot notation to find the value of the PSSnapin property of the Set-Alias cmdlet.</span></span>

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

<span data-ttu-id="01bdc-141">Este exemplo demonstra o processo de registrar um snap-in no seu sistema e, em seguida, adicioná-lo à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="01bdc-141">This example demonstrates the process of registering a snap-in on your system and then adding it to your session.</span></span> <span data-ttu-id="01bdc-142">Ele usa ManagementFeatures, um snap-in fictício implementado em um arquivo chamado ManagementCmdlets.dll.</span><span class="sxs-lookup"><span data-stu-id="01bdc-142">It uses ManagementFeatures, a fictitious snap-in implemented in a file that is named ManagementCmdlets.dll.</span></span>

## <span data-ttu-id="01bdc-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01bdc-143">PARAMETERS</span></span>

### <span data-ttu-id="01bdc-144">-Name</span><span class="sxs-lookup"><span data-stu-id="01bdc-144">-Name</span></span>

<span data-ttu-id="01bdc-145">Especifica o nome do snap-in do.</span><span class="sxs-lookup"><span data-stu-id="01bdc-145">Specifies the name of the snap-in.</span></span> <span data-ttu-id="01bdc-146">Esse é o nome, não o AssemblyName ou ModuleName.</span><span class="sxs-lookup"><span data-stu-id="01bdc-146">This is the Name, not the AssemblyName or ModuleName.</span></span> <span data-ttu-id="01bdc-147">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="01bdc-147">Wildcards are permitted.</span></span>

<span data-ttu-id="01bdc-148">Para localizar os nomes dos snap-ins registrados em seu sistema, digite `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="01bdc-148">To find the names of the registered snap-ins on your system, type `Get-PSSnapin -Registered`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="01bdc-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="01bdc-149">-PassThru</span></span>

<span data-ttu-id="01bdc-150">Indica que esse cmdlet retorna um objeto que representa cada snap-in adicionado.</span><span class="sxs-lookup"><span data-stu-id="01bdc-150">Indicates that this cmdlet returns an object that represents each added snap-in.</span></span> <span data-ttu-id="01bdc-151">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="01bdc-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="01bdc-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="01bdc-152">CommonParameters</span></span>

<span data-ttu-id="01bdc-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01bdc-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01bdc-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01bdc-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01bdc-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="01bdc-155">INPUTS</span></span>

### <span data-ttu-id="01bdc-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="01bdc-156">None</span></span>
<span data-ttu-id="01bdc-157">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01bdc-157">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="01bdc-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="01bdc-158">OUTPUTS</span></span>

### <span data-ttu-id="01bdc-159">Nenhum ou System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="01bdc-159">None or System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="01bdc-160">Esse cmdlet retorna um objeto PSSnapInInfo que representa o snap-in se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="01bdc-160">This cmdlet returns a PSSnapInInfo object that represents the snap-in if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="01bdc-161">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="01bdc-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="01bdc-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="01bdc-162">NOTES</span></span>

* <span data-ttu-id="01bdc-163">A partir do Windows PowerShell 3.0, os comandos principais que são instalados com o Windows PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="01bdc-163">Beginning in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="01bdc-164">No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do Windows PowerShell, os comandos principais são empacotados em snap-ins (PSSnapins).</span><span class="sxs-lookup"><span data-stu-id="01bdc-164">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins (PSSnapins).</span></span> <span data-ttu-id="01bdc-165">A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in.</span><span class="sxs-lookup"><span data-stu-id="01bdc-165">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="01bdc-166">Além disso, as sessões remotas, como as iniciadas pelo cmdlet New-PSSession, são sessões de estilo antigo que incluem snap-ins de núcleo.</span><span class="sxs-lookup"><span data-stu-id="01bdc-166">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="01bdc-167">Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte o [método CREATEDEFAULT2](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="01bdc-167">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

* <span data-ttu-id="01bdc-168">Para obter mais informações sobre snap-ins, consulte [about_Pssnapins](About/about_PSSnapins.md) e [como criar um snap-in do Windows PowerShell](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span><span class="sxs-lookup"><span data-stu-id="01bdc-168">For more information about snap-ins, see [about_PSSnapins](About/about_PSSnapins.md) and [How to Create a Windows PowerShell Snap-in](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span></span>
* <span data-ttu-id="01bdc-169">`Add-PSSnapin` Adiciona o snap-in somente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="01bdc-169">`Add-PSSnapin` adds the snap-in only to the current session.</span></span> <span data-ttu-id="01bdc-170">Para adicionar o snap-in para todas as sessões do Windows PowerShell, adicione-o ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01bdc-170">To add the snap-in to all Windows PowerShell sessions, add it to your Windows PowerShell profile.</span></span> <span data-ttu-id="01bdc-171">Para obter mais informações, consulte about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="01bdc-171">For more information, see about_Profiles.</span></span>
* <span data-ttu-id="01bdc-172">Você pode adicionar qualquer snap-in que tenha sido registrado usando o utilitário de instalação do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01bdc-172">You can add any snap-in that has been registered using the Microsoft .NET Framework install utility.</span></span> <span data-ttu-id="01bdc-173">Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="01bdc-173">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>
* <span data-ttu-id="01bdc-174">Para obter uma lista de snap-ins registrados no seu computador, digite `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="01bdc-174">To get a list of snap-ins that are registered on your computer, type `Get-PSSnapin -Registered`.</span></span>
* <span data-ttu-id="01bdc-175">Antes de adicionar um snap-in, `Add-PSSnapin` o verifica a versão do snap-in para verificar se ele é compatível com a versão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01bdc-175">Before adding a snap-in, `Add-PSSnapin` checks the version of the snap-in to verify that it is compatible with the current version of Windows PowerShell.</span></span> <span data-ttu-id="01bdc-176">Se o snap-in falha na verificação de versão, o Windows PowerShell relata um erro.</span><span class="sxs-lookup"><span data-stu-id="01bdc-176">If the snap-in fails the version check, Windows PowerShell reports an error.</span></span>

## <span data-ttu-id="01bdc-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="01bdc-177">RELATED LINKS</span></span>

[<span data-ttu-id="01bdc-178">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="01bdc-178">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="01bdc-179">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="01bdc-179">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
