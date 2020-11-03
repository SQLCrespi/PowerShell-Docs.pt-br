---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: 7a37857d9a4fb9eb18869ef78dc0ac19dc26367f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194169"
---
# <span data-ttu-id="8f9be-103">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="8f9be-103">Get-PSDrive</span></span>

## <span data-ttu-id="8f9be-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8f9be-104">SYNOPSIS</span></span>
<span data-ttu-id="8f9be-105">Obtém as unidades na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8f9be-105">Gets drives in the current session.</span></span>

## <span data-ttu-id="8f9be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f9be-106">SYNTAX</span></span>

### <span data-ttu-id="8f9be-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="8f9be-107">Name (Default)</span></span>

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8f9be-108">Valor literal</span><span class="sxs-lookup"><span data-stu-id="8f9be-108">LiteralName</span></span>

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="8f9be-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f9be-109">DESCRIPTION</span></span>

<span data-ttu-id="8f9be-110">O `Get-PSDrive` cmdlet obtém as unidades na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8f9be-110">The `Get-PSDrive` cmdlet gets the drives in the current session.</span></span> <span data-ttu-id="8f9be-111">Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="8f9be-111">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="8f9be-112">Esse cmdlet obtém os seguintes tipos de unidades:</span><span class="sxs-lookup"><span data-stu-id="8f9be-112">This cmdlet gets the following types of drives:</span></span>

- <span data-ttu-id="8f9be-113">Unidades lógicas do Windows no computador, incluindo unidades mapeadas para compartilhamentos de rede.</span><span class="sxs-lookup"><span data-stu-id="8f9be-113">Windows logical drives on the computer, including drives mapped to network shares.</span></span>
- <span data-ttu-id="8f9be-114">Unidades expostas por provedores do PowerShell (como o certificado:, função: e alias: unidades) e as unidades HKLM: e HKCU: que são expostas pelo provedor de registro do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-114">Drives exposed by PowerShell providers (such as the Certificate:, Function:, and Alias: drives) and the HKLM: and HKCU: drives that are exposed by the Windows PowerShell Registry provider.</span></span>
- <span data-ttu-id="8f9be-115">Unidades temporárias especificadas pela sessão e unidades de rede mapeadas persistentes que você cria usando o cmdlet New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="8f9be-115">Session-specified temporary drives and persistent mapped network drives that you create by using the New-PSDrive cmdlet.</span></span>

<span data-ttu-id="8f9be-116">A partir do Windows PowerShell 3,0, o parâmetro **Persist** do `New-PSDrive` cmdlet pode criar unidades de rede mapeadas que são salvas no computador local e estão disponíveis em outras sessões.</span><span class="sxs-lookup"><span data-stu-id="8f9be-116">Beginning in Windows PowerShell 3.0, the **Persist** parameter of the `New-PSDrive` cmdlet can create mapped network drives that are saved on the local computer and are available in other sessions.</span></span> <span data-ttu-id="8f9be-117">Para obter mais informações, consulte New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="8f9be-117">For more information, see New-PSDrive.</span></span>

<span data-ttu-id="8f9be-118">Também, a partir do Windows PowerShell 3.0, quando uma unidade externa é conectada ao computador, o Windows PowerShell adiciona automaticamente um PSDrive ao sistema de arquivos que representa a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="8f9be-118">Also, beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, Windows PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="8f9be-119">Não é necessário reiniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-119">You do not need to restart Windows PowerShell.</span></span> <span data-ttu-id="8f9be-120">Da mesma forma, quando uma unidade externa é desconectada do computador, o Windows PowerShell exclui automaticamente o PSDrive que representa a unidade removida.</span><span class="sxs-lookup"><span data-stu-id="8f9be-120">Similarly, when an external drive is disconnected from the computer, Windows PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="8f9be-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8f9be-121">EXAMPLES</span></span>

### <span data-ttu-id="8f9be-122">Exemplo 1: obter unidades na sessão atual</span><span class="sxs-lookup"><span data-stu-id="8f9be-122">Example 1: Get drives in the current session</span></span>

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

<span data-ttu-id="8f9be-123">Esse comando obtém as unidades na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8f9be-123">This command gets the drives in the current session.</span></span>

<span data-ttu-id="8f9be-124">A saída mostra o disco rígido (C:), unidade de CD-ROM (D:) e as unidades expostas pelos provedores do Windows PowerShell (alias:, CERT:, env:, function:, HKCU:, HKLM: e Variable:).</span><span class="sxs-lookup"><span data-stu-id="8f9be-124">The output shows the hard drive (C:), CD-ROM drive (D:), and the drives exposed by the Windows PowerShell providers (Alias:, Cert:, Env:, Function:, HKCU:, HKLM:, and Variable:).</span></span>

### <span data-ttu-id="8f9be-125">Exemplo 2: obter uma unidade no computador</span><span class="sxs-lookup"><span data-stu-id="8f9be-125">Example 2: Get a drive on the computer</span></span>

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

<span data-ttu-id="8f9be-126">Esse comando obtém a unidade D: no computador.</span><span class="sxs-lookup"><span data-stu-id="8f9be-126">This command gets the D: drive on the computer.</span></span> <span data-ttu-id="8f9be-127">Observe que a letra da unidade no comando não é seguida por dois pontos.</span><span class="sxs-lookup"><span data-stu-id="8f9be-127">Note that the drive letter in the command is not followed by a colon.</span></span>

### <span data-ttu-id="8f9be-128">Exemplo 3: obter todas as unidades com suporte no provedor do sistema de arquivos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9be-128">Example 3: Get all the drives that are supported by the Windows PowerShell file system provider</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

<span data-ttu-id="8f9be-129">Esse comando obtém todas as unidades suportadas pelo provedor FileSystem do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-129">This command gets all of the drives that are supported by the Windows PowerShell FileSystem provider.</span></span> <span data-ttu-id="8f9be-130">Isso inclui unidades fixas, partições lógicas, unidades de rede mapeadas e unidades temporárias que você cria usando o cmdlet New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="8f9be-130">This includes fixed drives, logical partitions, mapped network drives, and temporary drives that you create by using the New-PSDrive cmdlet.</span></span>

### <span data-ttu-id="8f9be-131">Exemplo 4: verificar se uma unidade está em uso como um nome de unidade do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9be-131">Example 4: Check to see if a drive is in use as a Windows PowerShell drive name</span></span>

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

<span data-ttu-id="8f9be-132">Este comando verifica se a unidade X já está em uso como um nome de unidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-132">This command checks to see whether the X drive is already in use as a Windows PowerShell drive name.</span></span>
<span data-ttu-id="8f9be-133">Se não estiver, o comando usará o `New-PSDrive` cmdlet para criar uma unidade temporária que é mapeada para a chave do Registro HKLM: \ Software.</span><span class="sxs-lookup"><span data-stu-id="8f9be-133">If it is not, the command uses the `New-PSDrive` cmdlet to create a temporary drive that is mapped to the HKLM:\SOFTWARE registry key.</span></span>

### <span data-ttu-id="8f9be-134">Exemplo 5: comparar os tipos de unidades do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="8f9be-134">Example 5: Compare the types of files system drives</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

<span data-ttu-id="8f9be-135">Este exemplo compara os tipos de unidades do sistema de arquivos que são exibidos pelo `Get-PSDrive` para os exibidos usando outros métodos.</span><span class="sxs-lookup"><span data-stu-id="8f9be-135">This example compares the types of file system drives that are displayed by `Get-PSDrive` to those displayed by using other methods.</span></span> <span data-ttu-id="8f9be-136">Este exemplo demonstra diferentes maneiras de exibir unidades no Windows PowerShell e mostra que as unidades específicas da sessão criadas usando o cmdlet New-PSDrive são acessíveis somente no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-136">This example demonstrates different ways to display drives in Windows PowerShell, and it shows that session-specific drives created by using the New-PSDrive cmdlet are accessible only in Windows PowerShell.</span></span>

<span data-ttu-id="8f9be-137">O primeiro comando usa `Get-PSDrive` para obter todas as unidades do sistema de arquivos na sessão.</span><span class="sxs-lookup"><span data-stu-id="8f9be-137">The first command uses `Get-PSDrive` to get all of the file system drives in the session.</span></span> <span data-ttu-id="8f9be-138">Isso inclui as unidades fixas (C: e D:), uma unidade de rede mapeada (G:) que foi criado usando o parâmetro **Persist** de `New-PSDrive` e uma unidade do PowerShell (T:) que foi criado usando `New-PSDrive` sem o parâmetro **Persist** .</span><span class="sxs-lookup"><span data-stu-id="8f9be-138">This includes the fixed drives (C: and D:), a mapped network drive (G:) that was created by using the **Persist** parameter of `New-PSDrive`, and a PowerShell drive (T:) that was created by using `New-PSDrive` without the **Persist** parameter.</span></span>

<span data-ttu-id="8f9be-139">O comando **net use** exibe as unidades de rede mapeadas do Windows, neste caso, exibe apenas a unidade G.</span><span class="sxs-lookup"><span data-stu-id="8f9be-139">The **net use** command displays Windows mapped network drives, in this case it displays only the G drive.</span></span> <span data-ttu-id="8f9be-140">Ele não exibe a unidade X: que foi criada pelo `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="8f9be-140">It does not display the X: drive that was created by `New-PSDrive`.</span></span> <span data-ttu-id="8f9be-141">Ele mostra que a unidade G: também está mapeada para o \\ \\ GratefulDead de música \\ .</span><span class="sxs-lookup"><span data-stu-id="8f9be-141">It shows that the G: drive is also mapped to \\\\Music\\GratefulDead.</span></span>

<span data-ttu-id="8f9be-142">O terceiro comando usa o método **GetDrives** da classe **System.IO.DriveInfo** do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f9be-142">The third command uses the **GetDrives** method of the Microsoft .NET Framework **System.IO.DriveInfo** class.</span></span> <span data-ttu-id="8f9be-143">Esse comando obtém as unidades do sistema de arquivos do Windows, incluindo a unidade G:, mas não obtém as unidades criadas pelo `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="8f9be-143">This command gets the Windows file system drives, including drive G:, but it does not get the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="8f9be-144">O quarto comando usa o `Get-CimInstance` cmdlet para obter as instâncias da classe **Win32_LogicalDisk** .</span><span class="sxs-lookup"><span data-stu-id="8f9be-144">The fourth command uses the `Get-CimInstance` cmdlet to get the instances of the **Win32_LogicalDisk** class.</span></span> <span data-ttu-id="8f9be-145">Ele retorna as unidades A:, C:, D:, E:, e G:, mas não as unidades criadas pelo `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="8f9be-145">It returns the A:, C:, D:, E:, and G: drives, but not the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="8f9be-146">O último comando usa o `Get-CimInstance` cmdlet para exibir as instâncias da classe **Win32_NetworkConnection** .</span><span class="sxs-lookup"><span data-stu-id="8f9be-146">The last command uses the `Get-CimInstance` cmdlet to display the instances of the **Win32_NetworkConnection** class.</span></span> <span data-ttu-id="8f9be-147">Como **net use** , ele retorna apenas a unidade persistente G: criada pelo `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="8f9be-147">Like **net use** , it returns only the persistent G: drive created by `New-PSDrive`.</span></span>

## <span data-ttu-id="8f9be-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f9be-148">PARAMETERS</span></span>

### <span data-ttu-id="8f9be-149">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="8f9be-149">-LiteralName</span></span>

<span data-ttu-id="8f9be-150">Especifica o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="8f9be-150">Specifies the name of the drive.</span></span>

<span data-ttu-id="8f9be-151">O valor de **LiteralName** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="8f9be-151">The value of **LiteralName** is used exactly as it is typed.</span></span> <span data-ttu-id="8f9be-152">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="8f9be-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8f9be-153">Se o nome inclui caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8f9be-153">If the name includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8f9be-154">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="8f9be-154">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f9be-155">-Name</span><span class="sxs-lookup"><span data-stu-id="8f9be-155">-Name</span></span>

<span data-ttu-id="8f9be-156">Especifica, como uma matriz de cadeia de caracteres, o nome ou nome das unidades que esse cmdlet obtém na operação.</span><span class="sxs-lookup"><span data-stu-id="8f9be-156">Specifies, as a string array, the name or name of drives that this cmdlet gets in the operation.</span></span>
<span data-ttu-id="8f9be-157">Digite o nome ou a letra da unidade sem dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="8f9be-157">Type the drive name or letter without a colon (:).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f9be-158">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="8f9be-158">-PSProvider</span></span>

<span data-ttu-id="8f9be-159">Especifica, como uma matriz de cadeia de caracteres, o provedor do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f9be-159">Specifies, as a string array, the Windows PowerShell provider.</span></span> <span data-ttu-id="8f9be-160">Esse cmdlet obtém apenas as unidades suportadas por este provedor.</span><span class="sxs-lookup"><span data-stu-id="8f9be-160">This cmdlet gets only the drives supported by this provider.</span></span> <span data-ttu-id="8f9be-161">Digite o nome de um provedor, como FileSystem, Registry ou Certificate.</span><span class="sxs-lookup"><span data-stu-id="8f9be-161">Type the name of a provider, such as FileSystem, Registry, or Certificate.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f9be-162">-Escopo</span><span class="sxs-lookup"><span data-stu-id="8f9be-162">-Scope</span></span>

<span data-ttu-id="8f9be-163">Especifica o escopo no qual este cmdlet obtém as unidades.</span><span class="sxs-lookup"><span data-stu-id="8f9be-163">Specifies the scope in which this cmdlet gets the drives.</span></span>

<span data-ttu-id="8f9be-164">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="8f9be-164">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8f9be-165">Global</span><span class="sxs-lookup"><span data-stu-id="8f9be-165">Global</span></span>
- <span data-ttu-id="8f9be-166">Local</span><span class="sxs-lookup"><span data-stu-id="8f9be-166">Local</span></span>
- <span data-ttu-id="8f9be-167">script</span><span class="sxs-lookup"><span data-stu-id="8f9be-167">Script</span></span>
- <span data-ttu-id="8f9be-168">um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="8f9be-168">a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span> <span data-ttu-id="8f9be-169">"Local" é o padrão.</span><span class="sxs-lookup"><span data-stu-id="8f9be-169">"Local" is the default.</span></span>

<span data-ttu-id="8f9be-170">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="8f9be-170">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f9be-171">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8f9be-171">-UseTransaction</span></span>

<span data-ttu-id="8f9be-172">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="8f9be-172">Includes the command in the active transaction.</span></span> <span data-ttu-id="8f9be-173">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="8f9be-173">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="8f9be-174">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="8f9be-174">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f9be-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8f9be-175">CommonParameters</span></span>

<span data-ttu-id="8f9be-176">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f9be-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f9be-177">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f9be-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f9be-178">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8f9be-178">INPUTS</span></span>

### <span data-ttu-id="8f9be-179">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8f9be-179">None</span></span>

<span data-ttu-id="8f9be-180">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f9be-180">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8f9be-181">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8f9be-181">OUTPUTS</span></span>

### <span data-ttu-id="8f9be-182">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="8f9be-182">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="8f9be-183">Esse cmdlet retorna objetos que representam as unidades na sessão.</span><span class="sxs-lookup"><span data-stu-id="8f9be-183">This cmdlet returns objects that represent the drives in the session.</span></span>

## <span data-ttu-id="8f9be-184">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8f9be-184">NOTES</span></span>

* <span data-ttu-id="8f9be-185">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="8f9be-185">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8f9be-186">Para listar os provedores disponíveis em sua sessão, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f9be-186">To list the providers available in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="8f9be-187">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8f9be-187">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
* <span data-ttu-id="8f9be-188">Unidades de rede mapeadas que são criadas usando o parâmetro **Persist** do cmdlet New-PSDrive são específicas para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f9be-188">Mapped network drives that are created by using the **Persist** parameter of the New-PSDrive cmdlet are specific to a user account.</span></span> <span data-ttu-id="8f9be-189">Unidades de rede mapeadas que você cria em sessões iniciadas com a opção Executar como administrador ou com as credenciais de outro usuário não são visíveis em sessões que são iniciadas sem credenciais explícitas ou com as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8f9be-189">Mapped network drives that you create in sessions that are started with the Run as administrator option or with the credentials of another user are not visible in sessions that are started without explicit credentials or with the credentials of the current user.</span></span>

## <span data-ttu-id="8f9be-190">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8f9be-190">RELATED LINKS</span></span>

[<span data-ttu-id="8f9be-191">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="8f9be-191">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="8f9be-192">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="8f9be-192">Remove-PSDrive</span></span>](Remove-PSDrive.md)

[<span data-ttu-id="8f9be-193">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="8f9be-193">Get-PSProvider</span></span>](Get-PSProvider.md)
