---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 277dd2678b54c9e708d09f6ca27d82ab9afd4c1c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347611"
---
# <span data-ttu-id="28f42-103">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="28f42-103">Get-HotFix</span></span>

## <span data-ttu-id="28f42-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="28f42-104">SYNOPSIS</span></span>
<span data-ttu-id="28f42-105">Obtém os hotfixes instalados em computadores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="28f42-105">Gets the hotfixes that are installed on local or remote computers.</span></span>

## <span data-ttu-id="28f42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28f42-106">SYNTAX</span></span>

### <span data-ttu-id="28f42-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="28f42-107">Default (Default)</span></span>

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### <span data-ttu-id="28f42-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="28f42-108">Description</span></span>

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## <span data-ttu-id="28f42-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28f42-109">DESCRIPTION</span></span>

<span data-ttu-id="28f42-110">O `Get-Hotfix` cmdlet obtém hotfixes ou atualizações que estão instalados no computador local ou em computadores remotos especificados.</span><span class="sxs-lookup"><span data-stu-id="28f42-110">The `Get-Hotfix` cmdlet gets hotfixes, or updates, that are installed on the local computer or specified remote computers.</span></span> <span data-ttu-id="28f42-111">As atualizações podem ser instaladas por Windows Update, Microsoft Update, Windows Server Update Services ou instalados manualmente.</span><span class="sxs-lookup"><span data-stu-id="28f42-111">The updates can be installed by Windows Update, Microsoft Update, Windows Server Update Services, or manually installed.</span></span>

## <span data-ttu-id="28f42-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="28f42-112">EXAMPLES</span></span>

### <span data-ttu-id="28f42-113">Exemplo 1: obter todos os hotfixes no computador local</span><span class="sxs-lookup"><span data-stu-id="28f42-113">Example 1: Get all hotfixes on the local computer</span></span>

<span data-ttu-id="28f42-114">O `Get-Hotfix` cmdlet obtém todos os hotfixes instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="28f42-114">The `Get-Hotfix` cmdlet gets all hotfixes installed on the local computer.</span></span>

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### <span data-ttu-id="28f42-115">Exemplo 2: obter hotfixes de vários computadores filtrados por uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28f42-115">Example 2: Get hotfixes from multiple computers filtered by a string</span></span>

<span data-ttu-id="28f42-116">O `Get-Hotfix` comando usa parâmetros para obter hotfixes instalados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="28f42-116">The `Get-Hotfix` command uses parameters to get hotfixes installed on remote computers.</span></span> <span data-ttu-id="28f42-117">Os resultados são filtrados por uma cadeia de caracteres de descrição especificada.</span><span class="sxs-lookup"><span data-stu-id="28f42-117">The results are filtered by a specified description string.</span></span>

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

<span data-ttu-id="28f42-118">`Get-Hotfix` filtra a saída com o parâmetro **Description** e a **segurança** de cadeia de caracteres que inclui o curinga asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="28f42-118">`Get-Hotfix` filters the output with the **Description** parameter and the string **Security** that includes the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="28f42-119">O parâmetro **ComputerName** inclui uma cadeia de caracteres separada por vírgulas de nomes de computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="28f42-119">The **ComputerName** parameter includes a comma-separated string of remote computer names.</span></span> <span data-ttu-id="28f42-120">O parâmetro **Credential** especifica uma conta de usuário que tem permissão para acessar os computadores remotos e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="28f42-120">The **Credential** parameter specifies a user account that has permission to access the remote computers and run commands.</span></span>

### <span data-ttu-id="28f42-121">Exemplo 3: verificar se uma atualização está instalada e gravar nomes de computador em um arquivo</span><span class="sxs-lookup"><span data-stu-id="28f42-121">Example 3: Verify if an update is installed and write computer names to a file</span></span>

<span data-ttu-id="28f42-122">Os comandos neste exemplo verificam se uma atualização específica está instalada.</span><span class="sxs-lookup"><span data-stu-id="28f42-122">The commands in this example verify whether a particular update installed.</span></span> <span data-ttu-id="28f42-123">Se a atualização não estiver instalada, o nome do computador será gravado em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f42-123">If the update isn't installed, the computer name is written to a text file.</span></span>

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

<span data-ttu-id="28f42-124">A `$A` variável contém nomes de computador que foram obtidos por `Get-Content` meio de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f42-124">The `$A` variable contains computer names that were obtained by `Get-Content` from a text file.</span></span> <span data-ttu-id="28f42-125">Os objetos no `$A` são enviados para o pipeline para `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="28f42-125">The objects in `$A` are sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="28f42-126">Uma `if` instrução usa o `Get-Hotfix` cmdlet com o parâmetro **ID** e um número de ID específico para cada nome de computador.</span><span class="sxs-lookup"><span data-stu-id="28f42-126">An `if` statement uses the `Get-Hotfix` cmdlet with the **Id** parameter and a specific Id number for each computer name.</span></span> <span data-ttu-id="28f42-127">Se um computador não tiver a ID de hotfix especificada instalada, o `Add-Content` cmdlet gravará o nome do computador em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="28f42-127">If a computer doesn't have the specified hotfix Id installed, the `Add-Content` cmdlet writes the computer name to a file.</span></span>

### <span data-ttu-id="28f42-128">Exemplo 4: obter o hotfix mais recente no computador local</span><span class="sxs-lookup"><span data-stu-id="28f42-128">Example 4: Get the most recent hotfix on the local computer</span></span>

<span data-ttu-id="28f42-129">Este exemplo obtém o hotfix mais recente instalado em um computador.</span><span class="sxs-lookup"><span data-stu-id="28f42-129">This example gets the most recent hotfix installed on a computer.</span></span>

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

<span data-ttu-id="28f42-130">`Get-Hotfix` envia os objetos por meio do pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28f42-130">`Get-Hotfix` sends the objects down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="28f42-131">`Sort-Object` classifica os objetos por ordem crescente e usa o parâmetro **Property** para avaliar cada data de **instalação** .</span><span class="sxs-lookup"><span data-stu-id="28f42-131">`Sort-Object` sorts objects by ascending order and uses the **Property** parameter to evaluate each **InstalledOn** date.</span></span> <span data-ttu-id="28f42-132">A notação de matriz `[-1]` seleciona o hotfix instalado mais recente.</span><span class="sxs-lookup"><span data-stu-id="28f42-132">The array notation `[-1]` selects the most recent installed hotfix.</span></span>

## <span data-ttu-id="28f42-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28f42-133">PARAMETERS</span></span>

### <span data-ttu-id="28f42-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="28f42-134">-ComputerName</span></span>

<span data-ttu-id="28f42-135">Especifica um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="28f42-135">Specifies a remote computer.</span></span> <span data-ttu-id="28f42-136">Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="28f42-136">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>

<span data-ttu-id="28f42-137">Quando o parâmetro **ComputerName** não é especificado, o `Get-Hotfix` é executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="28f42-137">When the **ComputerName** parameter isn't specified, `Get-Hotfix` runs on the local computer.</span></span>

<span data-ttu-id="28f42-138">O parâmetro **ComputerName** não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28f42-138">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="28f42-139">Se o computador não estiver configurado para executar comandos remotos, use o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="28f42-139">If your computer isn't configured to run remote commands, use the **ComputerName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="28f42-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="28f42-140">-Credential</span></span>

<span data-ttu-id="28f42-141">Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="28f42-141">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="28f42-142">O padrão é o usuário atual</span><span class="sxs-lookup"><span data-stu-id="28f42-142">The default is the current user</span></span>

<span data-ttu-id="28f42-143">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28f42-143">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="28f42-144">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="28f42-144">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="28f42-145">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="28f42-145">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="28f42-146">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="28f42-146">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28f42-147">-Description</span><span class="sxs-lookup"><span data-stu-id="28f42-147">-Description</span></span>

<span data-ttu-id="28f42-148">`Get-HotFix` usa o parâmetro **Description** para especificar os tipos de hotfix.</span><span class="sxs-lookup"><span data-stu-id="28f42-148">`Get-HotFix` uses the **Description** parameter to specify hotfix types.</span></span> <span data-ttu-id="28f42-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="28f42-149">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="28f42-150">-Id</span><span class="sxs-lookup"><span data-stu-id="28f42-150">-Id</span></span>

<span data-ttu-id="28f42-151">Filtra os `Get-HotFix` resultados de IDs de hotfix específicos.</span><span class="sxs-lookup"><span data-stu-id="28f42-151">Filters the `Get-HotFix` results for specific hotfix Ids.</span></span> <span data-ttu-id="28f42-152">Caracteres curinga não são aceitos.</span><span class="sxs-lookup"><span data-stu-id="28f42-152">Wildcards aren't accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28f42-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28f42-153">CommonParameters</span></span>

<span data-ttu-id="28f42-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28f42-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28f42-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28f42-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28f42-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="28f42-156">INPUTS</span></span>

### <span data-ttu-id="28f42-157">String</span><span class="sxs-lookup"><span data-stu-id="28f42-157">String</span></span>

<span data-ttu-id="28f42-158">É possível canalizar um ou mais nomes de computador para Get-HotFix.</span><span class="sxs-lookup"><span data-stu-id="28f42-158">You can pipe one or more computer names to Get-HotFix.</span></span>

## <span data-ttu-id="28f42-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="28f42-159">OUTPUTS</span></span>

### <span data-ttu-id="28f42-160">System. Management. ManagementObject # root\CIMV2\ Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="28f42-160">System.Management.ManagementObject#root\CIMV2\Win32_QuickFixEngineering</span></span>

<span data-ttu-id="28f42-161">`Get-HotFix` retorna objetos que representam os hotfixes no computador.</span><span class="sxs-lookup"><span data-stu-id="28f42-161">`Get-HotFix` returns objects that represent the hotfixes on the computer.</span></span>

## <span data-ttu-id="28f42-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="28f42-162">NOTES</span></span>

<span data-ttu-id="28f42-163">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="28f42-163">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="28f42-164">A **Win32_QuickFixEngineering** [classe WMI](/windows/desktop/WmiSdk/retrieving-a-class) Win32_QuickFixEngineering representa uma atualização pequena em todo o sistema, normalmente conhecida como atualização de QFE (Quick-Fix Engineering), aplicada ao sistema operacional atual.</span><span class="sxs-lookup"><span data-stu-id="28f42-164">The **Win32_QuickFixEngineering** [WMI class](/windows/desktop/WmiSdk/retrieving-a-class) represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the current operating system.</span></span> <span data-ttu-id="28f42-165">Essa classe retorna apenas as atualizações fornecidas pela CBS (serviço baseado em componente).</span><span class="sxs-lookup"><span data-stu-id="28f42-165">This class returns only the updates supplied by Component Based Servicing (CBS).</span></span> <span data-ttu-id="28f42-166">Essas atualizações não estão listadas no registro.</span><span class="sxs-lookup"><span data-stu-id="28f42-166">These updates are not listed in the registry.</span></span> <span data-ttu-id="28f42-167">As atualizações fornecidas pelo Microsoft Windows Installer (MSI) ou pelo site do [Windows Update](https://update.microsoft.com) não são retornadas pelo **Win32_QuickFixEngineering**.</span><span class="sxs-lookup"><span data-stu-id="28f42-167">Updates supplied by Microsoft Windows Installer (MSI) or the [Windows Update](https://update.microsoft.com) site are not returned by **Win32_QuickFixEngineering**.</span></span> <span data-ttu-id="28f42-168">Para obter mais informações, consulte [classe Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span><span class="sxs-lookup"><span data-stu-id="28f42-168">For more information, see [Win32_QuickFixEngineering class](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span></span>

<span data-ttu-id="28f42-169">A `Get-HotFix` saída pode variar em sistemas operacionais diferentes.</span><span class="sxs-lookup"><span data-stu-id="28f42-169">The `Get-HotFix` output might vary on different operating systems.</span></span>

## <span data-ttu-id="28f42-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="28f42-170">RELATED LINKS</span></span>

[<span data-ttu-id="28f42-171">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="28f42-171">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="28f42-172">Add-Content</span><span class="sxs-lookup"><span data-stu-id="28f42-172">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="28f42-173">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="28f42-173">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="28f42-174">Classe Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="28f42-174">Win32_QuickFixEngineering class</span></span>](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
