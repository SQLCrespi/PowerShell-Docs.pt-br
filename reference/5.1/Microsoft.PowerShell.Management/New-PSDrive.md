---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: df5f335780ad04b2d833180c30cc46a06f85d850
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193968"
---
# <span data-ttu-id="fdf2a-103">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf2a-103">New-PSDrive</span></span>

## <span data-ttu-id="fdf2a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fdf2a-104">SYNOPSIS</span></span>
<span data-ttu-id="fdf2a-105">Cria unidades de rede mapeadas temporárias e persistentes.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-105">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="fdf2a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdf2a-106">SYNTAX</span></span>

### <span data-ttu-id="fdf2a-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="fdf2a-107">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="fdf2a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fdf2a-108">DESCRIPTION</span></span>

<span data-ttu-id="fdf2a-109">O `New-PSDrive` cmdlet cria unidades temporárias e persistentes que são mapeadas para ou associadas a um local em um armazenamento de dados, como uma unidade de rede, um diretório no computador local ou uma chave do registro, e unidades de rede persistentes mapeadas do Windows que estão associadas a um local do sistema de arquivos em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-109">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="fdf2a-110">As unidades temporárias existem somente na sessão atual do PowerShell e nas sessões que você cria na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-110">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="fdf2a-111">Eles podem ter qualquer nome que seja válido no PowerShell e possam ser mapeados para qualquer recurso local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-111">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="fdf2a-112">Você pode usar unidades temporárias do PowerShell para acessar dados no armazenamento de dados associado, assim como faria com qualquer unidade de rede mapeada.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-112">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="fdf2a-113">Você pode alterar os locais na unidade usando o `Set-Location` e acessar o conteúdo da unidade usando o `Get-Item` ou o `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-113">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="fdf2a-114">Como as unidades temporárias são conhecidas apenas pelo PowerShell, você não pode acessá-las usando o explorador de arquivos, Instrumentação de Gerenciamento do Windows (WMI), Component Object Model (COM), Microsoft .NET estrutura ou com ferramentas como **net use** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-114">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use** .</span></span>

<span data-ttu-id="fdf2a-115">Os seguintes recursos foram adicionados ao `New-PSDrive` no PowerShell 3,0:</span><span class="sxs-lookup"><span data-stu-id="fdf2a-115">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="fdf2a-116">Unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-116">Mapped network drives.</span></span> <span data-ttu-id="fdf2a-117">Você pode usar o parâmetro **Persist** de `New-PSDrive` para criar unidades de rede mapeada do Windows.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-117">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="fdf2a-118">Diferentemente das unidades temporárias do PowerShell, as unidades de rede mapeadas do Windows não são específicas da sessão.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-118">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="fdf2a-119">Eles são salvos no Windows e podem ser gerenciados usando ferramentas padrão do Windows, como o explorador de arquivos e o **net use** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-119">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use** .</span></span> <span data-ttu-id="fdf2a-120">Unidades de rede mapeadas devem ter um nome de letra da unidade e estar conectadas a um local de sistema de arquivos remoto.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-120">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="fdf2a-121">Quando o seu comando tem o escopo definido localmente, nenhum ponto de fornecimento, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual o comando está em execução.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-121">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="fdf2a-122">Se você estiver executando `New-PSDrive` dentro de um script e quiser que a unidade persista indefinidamente, você deverá criar o código de origem do script.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-122">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="fdf2a-123">Para obter melhores resultados, para forçar uma nova unidade a persistir indefinidamente, adicione o parâmetro **Scope** ao comando e defina seu valor como **global** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-123">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global** .</span></span> <span data-ttu-id="fdf2a-124">Para obter mais informações sobre o fornecimento de pontos, consulte [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-124">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="fdf2a-125">Unidades externas.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-125">External drives.</span></span> <span data-ttu-id="fdf2a-126">Quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um **PSDrive** ao sistema de arquivos que representa a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-126">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="fdf2a-127">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-127">You don't have to restart PowerShell.</span></span> <span data-ttu-id="fdf2a-128">Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o **PSDrive** que representa a unidade removida.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-128">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="fdf2a-129">Credenciais para caminhos UNC (Convenção de nomenclatura universal).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-129">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="fdf2a-130">Quando o valor do parâmetro **raiz** é um caminho UNC, como `\\Server\Share` , a credencial especificada no valor do parâmetro **Credential** é usada para criar o **PSDrive** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-130">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive** .</span></span> <span data-ttu-id="fdf2a-131">Caso contrário, a **credencial** não será eficaz quando você estiver criando novas unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-131">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="fdf2a-132">Alguns exemplos de código usam nivelamento para reduzir o tamanho da linha e melhorar a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-132">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="fdf2a-133">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-133">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="fdf2a-134">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fdf2a-134">EXAMPLES</span></span>

### <span data-ttu-id="fdf2a-135">Exemplo 1: criar uma unidade temporária mapeada para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="fdf2a-135">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="fdf2a-136">Este exemplo cria uma unidade temporária do PowerShell mapeada para um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-136">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="fdf2a-137">`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `Public` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-137">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="fdf2a-138">O parâmetro **raiz** especifica o caminho UNC do compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-138">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="fdf2a-139">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="fdf2a-139">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="fdf2a-140">Exemplo 2: criar uma unidade temporária mapeada para um diretório local</span><span class="sxs-lookup"><span data-stu-id="fdf2a-140">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="fdf2a-141">Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a um diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-141">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

<span data-ttu-id="fdf2a-142">Nivelamento cria as chaves de parâmetro e valores.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-142">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="fdf2a-143">O parâmetro **Name** especifica o nome da unidade, **mydocs** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-143">The **Name** parameter specifies the drive name, **MyDocs** .</span></span> <span data-ttu-id="fdf2a-144">O parâmetro **PSProvider** especifica o provedor do PowerShell `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-144">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="fdf2a-145">**Raiz** especifica o diretório do computador local.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-145">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="fdf2a-146">O parâmetro **Description** descreve a finalidade da unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-146">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="fdf2a-147">`New-PSDrive` usa os parâmetros splatted para criar a `MyDocs` unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-147">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="fdf2a-148">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="fdf2a-148">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="fdf2a-149">Exemplo 3: criar uma unidade temporária para uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="fdf2a-149">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="fdf2a-150">Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-150">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="fdf2a-151">Ele cria uma unidade chamada MyCompany que é mapeada para a `HKLM:\Software\MyCompany` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-151">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="fdf2a-152">`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `MyCompany` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `Registry` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-152">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="fdf2a-153">O parâmetro **raiz** especifica o local do registro.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-153">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="fdf2a-154">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="fdf2a-154">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="fdf2a-155">Exemplo 4: criar uma unidade de rede mapeada persistente usando credenciais</span><span class="sxs-lookup"><span data-stu-id="fdf2a-155">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="fdf2a-156">Este exemplo mapeia uma unidade de rede que é autenticada com as credenciais de uma conta de serviço de domínio.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-156">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="fdf2a-157">Para obter mais informações sobre o objeto **PSCredential** que armazena as credenciais e como as senhas são armazenadas como uma **SecureString** , consulte a descrição do parâmetro de **credencial** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-157">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString** , see the **Credential** parameter's description.</span></span>

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> <span data-ttu-id="fdf2a-158">Lembre-se de que, se você usar o trecho acima em um script, defina o valor do parâmetro de **escopo** como "global" para garantir que a unidade persiste fora do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-158">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="fdf2a-159">A `$cred` variável armazena um objeto **PSCredential** que contém as credenciais da conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-159">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="fdf2a-160">`Get-Credential` solicita que você insira a senha que está armazenada em uma **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-160">`Get-Credential` prompts you to enter the password that's stored in a **SecureString** .</span></span>

<span data-ttu-id="fdf2a-161">`New-PSDrive` cria a unidade de rede mapeada usando vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-161">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="fdf2a-162">**Nome** especifica a `S` letra da unidade que o Windows aceita.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-162">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="fdf2a-163">e **root** define `\\Server01\Scripts` como o local em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-163">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="fdf2a-164">**Persistir** cria uma unidade de rede mapeada do Windows que é salva no computador local.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-164">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="fdf2a-165">**PSProvider** especifica o `FileSystem` provedor.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-165">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="fdf2a-166">A **credencial** usa a `$cred` variável para obter as credenciais da conta de serviço para autenticação.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-166">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="fdf2a-167">A unidade mapeada pode ser exibida no computador local em sessões do PowerShell, explorador de arquivos e com ferramentas como **net use** .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-167">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use** .</span></span> <span data-ttu-id="fdf2a-168">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="fdf2a-168">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="fdf2a-169">Exemplo 5: criar unidades persistentes e temporárias</span><span class="sxs-lookup"><span data-stu-id="fdf2a-169">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="fdf2a-170">Este exemplo mostra a diferença entre uma unidade de rede mapeada persistente e uma unidade temporária do PowerShell que é mapeada para o mesmo compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-170">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="fdf2a-171">Se você fechar a sessão do PowerShell e, em seguida, abrir uma nova sessão, o temporário `PSDrive:` não estará disponível, mas a `X:` unidade persistente estará disponível.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-171">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="fdf2a-172">Ao decidir qual método usar para mapear unidades de rede, considere como você usará a unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-172">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="fdf2a-173">Por exemplo, se precisa ser persistente e se a unidade precisa estar visível para outros recursos do Windows.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-173">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## <span data-ttu-id="fdf2a-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdf2a-174">PARAMETERS</span></span>

### <span data-ttu-id="fdf2a-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fdf2a-175">-Confirm</span></span>

<span data-ttu-id="fdf2a-176">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-176">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fdf2a-177">-Credential</span><span class="sxs-lookup"><span data-stu-id="fdf2a-177">-Credential</span></span>

<span data-ttu-id="fdf2a-178">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-178">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="fdf2a-179">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-179">The default is the current user.</span></span>

<span data-ttu-id="fdf2a-180">Desde o PowerShell 3,0, quando o valor do parâmetro **raiz** é um caminho UNC, você pode usar credenciais para criar unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-180">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="fdf2a-181">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-181">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="fdf2a-182">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-182">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="fdf2a-183">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-183">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="fdf2a-184">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-184">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-185">-Description</span><span class="sxs-lookup"><span data-stu-id="fdf2a-185">-Description</span></span>

<span data-ttu-id="fdf2a-186">Especifica uma breve descrição em texto da unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-186">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="fdf2a-187">Digite qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-187">Type any string.</span></span>

<span data-ttu-id="fdf2a-188">Para ver as descrições de todas as unidades de sessão, `Get-PSDrive | Format-Table Name, Description` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-188">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="fdf2a-189">Para ver a descrição de uma unidade específica, digite `(Get-PSDrive <DriveName>).Description` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-189">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

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

### <span data-ttu-id="fdf2a-190">-Name</span><span class="sxs-lookup"><span data-stu-id="fdf2a-190">-Name</span></span>

<span data-ttu-id="fdf2a-191">Especifica um nome para a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-191">Specifies a name for the new drive.</span></span> <span data-ttu-id="fdf2a-192">Para unidades de rede mapeadas persistentes, use uma letra de unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-192">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="fdf2a-193">Para unidades temporárias do PowerShell, você não está limitado a letras de unidade, use qualquer cadeia de caracteres válida.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-193">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-194">-Persistir</span><span class="sxs-lookup"><span data-stu-id="fdf2a-194">-Persist</span></span>

<span data-ttu-id="fdf2a-195">Indica que esse cmdlet cria uma unidade de rede mapeada do Windows.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-195">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="fdf2a-196">O parâmetro **Persist** só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-196">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="fdf2a-197">Unidades de rede mapeadas são salvos no Windows no computador local.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-197">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="fdf2a-198">Eles são persistentes, não específicos da sessão e podem ser exibidos e gerenciados no explorador de arquivos e em outras ferramentas.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-198">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="fdf2a-199">Quando você faz o escopo do comando localmente, sem o fato de a Sourcing, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual você executa o comando.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-199">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="fdf2a-200">Se você executar `New-PSDrive` dentro de um script e quiser que a nova unidade persista indefinidamente, você deverá criar o código-fonte do script.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-200">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="fdf2a-201">Para obter melhores resultados, para forçar uma nova unidade a persistir, especifique **global** como o valor do parâmetro de **escopo** e inclua **Persist** no comando.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-201">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="fdf2a-202">O nome da unidade deve ser uma letra, como `D` ou `E` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-202">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="fdf2a-203">O valor do parâmetro **raiz** deve ser um caminho UNC de um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-203">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="fdf2a-204">O valor do parâmetro **PSProvider** deve ser `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-204">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="fdf2a-205">Para desconectar uma unidade de rede mapeada do Windows, use o `Remove-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-205">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="fdf2a-206">Quando você desconecta uma unidade de rede mapeada do Windows, o mapeamento é excluído permanentemente do computador, não apenas da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-206">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="fdf2a-207">Unidades de rede mapeadas são específicas para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-207">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="fdf2a-208">Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-208">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-209">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="fdf2a-209">-PSProvider</span></span>

<span data-ttu-id="fdf2a-210">Especifica o provedor do PowerShell que oferece suporte a unidades desse tipo.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-210">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="fdf2a-211">Por exemplo, se a unidade estiver associada a um compartilhamento de rede ou diretório de sistema de arquivos, o provedor do PowerShell será `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-211">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="fdf2a-212">Se a unidade estiver associada a uma chave do registro, o provedor será `Registry` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-212">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="fdf2a-213">Unidades temporárias do PowerShell podem ser associadas a qualquer provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-213">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="fdf2a-214">Unidades de rede mapeadas podem ser associadas somente ao `FileSystem` provedor.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-214">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="fdf2a-215">Para ver uma lista dos provedores em sua sessão do PowerShell, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-215">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-216">-Raiz</span><span class="sxs-lookup"><span data-stu-id="fdf2a-216">-Root</span></span>

<span data-ttu-id="fdf2a-217">Especifica o local do repositório de dados para o qual uma unidade do PowerShell é mapeada.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-217">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="fdf2a-218">Por exemplo, especifique um compartilhamento de rede, como `\\Server01\Public` um diretório local, como `C:\Program Files` , ou uma chave do registro, como `HKLM:\Software\Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-218">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="fdf2a-219">As unidades temporárias do PowerShell podem ser associadas a um local local ou remoto em qualquer unidade de provedor com suporte.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-219">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="fdf2a-220">Unidades de rede mapeadas podem ser associadas somente a um local de sistema de arquivos em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-220">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-221">-Escopo</span><span class="sxs-lookup"><span data-stu-id="fdf2a-221">-Scope</span></span>

<span data-ttu-id="fdf2a-222">Especifica um escopo para a unidade.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-222">Specifies a scope for the drive.</span></span> <span data-ttu-id="fdf2a-223">Os valores aceitáveis para esse parâmetro são: **global** , **local** e **script** , ou um número relativo ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-223">The acceptable values for this parameter are: **Global** , **Local** , and **Script** , or a number relative to the current scope.</span></span> <span data-ttu-id="fdf2a-224">O número de escopos é 0 com o número de escopos.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-224">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="fdf2a-225">O número de escopo atual é 0 e seu pai é 1.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-225">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="fdf2a-226">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-226">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf2a-227">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="fdf2a-227">-UseTransaction</span></span>

<span data-ttu-id="fdf2a-228">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-228">Includes the command in the active transaction.</span></span> <span data-ttu-id="fdf2a-229">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-229">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="fdf2a-230">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-230">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="fdf2a-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fdf2a-231">-WhatIf</span></span>

<span data-ttu-id="fdf2a-232">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-232">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fdf2a-233">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-233">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fdf2a-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fdf2a-234">CommonParameters</span></span>

<span data-ttu-id="fdf2a-235">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-235">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="fdf2a-236">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdf2a-237">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fdf2a-237">INPUTS</span></span>

### <span data-ttu-id="fdf2a-238">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fdf2a-238">None</span></span>

<span data-ttu-id="fdf2a-239">Não é possível pipeline de entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-239">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="fdf2a-240">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fdf2a-240">OUTPUTS</span></span>

### <span data-ttu-id="fdf2a-241">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="fdf2a-241">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="fdf2a-242">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fdf2a-242">NOTES</span></span>

<span data-ttu-id="fdf2a-243">`New-PSDrive` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-243">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="fdf2a-244">Para listar os provedores disponíveis em sua sessão, use `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="fdf2a-244">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="fdf2a-245">Para obter mais informações sobre provedores, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="fdf2a-245">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="fdf2a-246">Unidades de rede mapeadas são específicas para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-246">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="fdf2a-247">Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="fdf2a-247">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="fdf2a-248">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fdf2a-248">RELATED LINKS</span></span>

[<span data-ttu-id="fdf2a-249">about_Providers</span><span class="sxs-lookup"><span data-stu-id="fdf2a-249">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="fdf2a-250">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="fdf2a-250">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="fdf2a-251">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf2a-251">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="fdf2a-252">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf2a-252">Remove-PSDrive</span></span>](Remove-PSDrive.md)
