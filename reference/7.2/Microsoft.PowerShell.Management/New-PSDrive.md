---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 54b65a636fe05ed82d4f022b5bb8cbf8acaf7bab
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603332"
---
# <span data-ttu-id="1bbc0-102">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1bbc0-102">New-PSDrive</span></span>

## <span data-ttu-id="1bbc0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1bbc0-103">SYNOPSIS</span></span>
<span data-ttu-id="1bbc0-104">Cria unidades de rede mapeadas temporárias e persistentes.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-104">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="1bbc0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1bbc0-105">SYNTAX</span></span>

### <span data-ttu-id="1bbc0-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="1bbc0-106">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="1bbc0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1bbc0-107">DESCRIPTION</span></span>

<span data-ttu-id="1bbc0-108">O `New-PSDrive` cmdlet cria unidades temporárias e persistentes que são mapeadas para ou associadas a um local em um armazenamento de dados, como uma unidade de rede, um diretório no computador local ou uma chave do registro, e unidades de rede persistentes mapeadas do Windows que estão associadas a um local do sistema de arquivos em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-108">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="1bbc0-109">As unidades temporárias existem somente na sessão atual do PowerShell e nas sessões que você cria na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-109">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="1bbc0-110">Eles podem ter qualquer nome que seja válido no PowerShell e possam ser mapeados para qualquer recurso local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-110">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="1bbc0-111">Você pode usar unidades temporárias do PowerShell para acessar dados no armazenamento de dados associado, assim como faria com qualquer unidade de rede mapeada.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-111">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="1bbc0-112">Você pode alterar os locais na unidade usando o `Set-Location` e acessar o conteúdo da unidade usando o `Get-Item` ou o `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-112">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="1bbc0-113">Como as unidades temporárias são conhecidas apenas pelo PowerShell, você não pode acessá-las usando o explorador de arquivos, Instrumentação de Gerenciamento do Windows (WMI), Component Object Model (COM), Microsoft .NET estrutura ou com ferramentas como **net use**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-113">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use**.</span></span>

<span data-ttu-id="1bbc0-114">Os seguintes recursos foram adicionados ao `New-PSDrive` no PowerShell 3,0:</span><span class="sxs-lookup"><span data-stu-id="1bbc0-114">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="1bbc0-115">Unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-115">Mapped network drives.</span></span> <span data-ttu-id="1bbc0-116">Você pode usar o parâmetro **Persist** de `New-PSDrive` para criar unidades de rede mapeada do Windows.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-116">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="1bbc0-117">Diferentemente das unidades temporárias do PowerShell, as unidades de rede mapeadas do Windows não são específicas da sessão.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-117">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="1bbc0-118">Eles são salvos no Windows e podem ser gerenciados usando ferramentas padrão do Windows, como o explorador de arquivos e o **net use**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-118">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use**.</span></span> <span data-ttu-id="1bbc0-119">Unidades de rede mapeadas devem ter um nome de letra da unidade e estar conectadas a um local de sistema de arquivos remoto.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-119">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="1bbc0-120">Quando o seu comando tem o escopo definido localmente, nenhum ponto de fornecimento, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual o comando está em execução.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-120">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="1bbc0-121">Se você estiver executando `New-PSDrive` dentro de um script e quiser que a unidade persista indefinidamente, você deverá criar o código de origem do script.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-121">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="1bbc0-122">Para obter melhores resultados, para forçar uma nova unidade a persistir indefinidamente, adicione o parâmetro **Scope** ao comando e defina seu valor como **global**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-122">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global**.</span></span> <span data-ttu-id="1bbc0-123">Para obter mais informações sobre o fornecimento de pontos, consulte [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-123">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="1bbc0-124">Unidades externas.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-124">External drives.</span></span> <span data-ttu-id="1bbc0-125">Quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um **PSDrive** ao sistema de arquivos que representa a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-125">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="1bbc0-126">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-126">You don't have to restart PowerShell.</span></span> <span data-ttu-id="1bbc0-127">Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o **PSDrive** que representa a unidade removida.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-127">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="1bbc0-128">Credenciais para caminhos UNC (Convenção de nomenclatura universal).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-128">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="1bbc0-129">Quando o valor do parâmetro **raiz** é um caminho UNC, como `\\Server\Share` , a credencial especificada no valor do parâmetro **Credential** é usada para criar o **PSDrive**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-129">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive**.</span></span> <span data-ttu-id="1bbc0-130">Caso contrário, a **credencial** não será eficaz quando você estiver criando novas unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-130">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="1bbc0-131">Alguns exemplos de código usam nivelamento para reduzir o tamanho da linha e melhorar a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-131">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="1bbc0-132">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-132">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="1bbc0-133">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1bbc0-133">EXAMPLES</span></span>

### <span data-ttu-id="1bbc0-134">Exemplo 1: criar uma unidade temporária mapeada para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="1bbc0-134">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="1bbc0-135">Este exemplo cria uma unidade temporária do PowerShell mapeada para um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-135">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="1bbc0-136">`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `Public` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-136">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="1bbc0-137">O parâmetro **raiz** especifica o caminho UNC do compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-137">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="1bbc0-138">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="1bbc0-138">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="1bbc0-139">Exemplo 2: criar uma unidade temporária mapeada para um diretório local</span><span class="sxs-lookup"><span data-stu-id="1bbc0-139">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="1bbc0-140">Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a um diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-140">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

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

<span data-ttu-id="1bbc0-141">Nivelamento cria as chaves de parâmetro e valores.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-141">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="1bbc0-142">O parâmetro **Name** especifica o nome da unidade, **mydocs**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-142">The **Name** parameter specifies the drive name, **MyDocs**.</span></span> <span data-ttu-id="1bbc0-143">O parâmetro **PSProvider** especifica o provedor do PowerShell `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-143">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="1bbc0-144">**Raiz** especifica o diretório do computador local.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-144">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="1bbc0-145">O parâmetro **Description** descreve a finalidade da unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-145">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="1bbc0-146">`New-PSDrive` usa os parâmetros splatted para criar a `MyDocs` unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-146">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="1bbc0-147">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="1bbc0-147">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="1bbc0-148">Exemplo 3: criar uma unidade temporária para uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="1bbc0-148">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="1bbc0-149">Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-149">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="1bbc0-150">Ele cria uma unidade chamada MyCompany que é mapeada para a `HKLM:\Software\MyCompany` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-150">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="1bbc0-151">`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `MyCompany` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `Registry` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-151">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="1bbc0-152">O parâmetro **raiz** especifica o local do registro.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-152">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="1bbc0-153">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="1bbc0-153">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="1bbc0-154">Exemplo 4: criar uma unidade de rede mapeada persistente usando credenciais</span><span class="sxs-lookup"><span data-stu-id="1bbc0-154">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="1bbc0-155">Este exemplo mapeia uma unidade de rede que é autenticada com as credenciais de uma conta de serviço de domínio.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-155">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="1bbc0-156">Para obter mais informações sobre o objeto **PSCredential** que armazena as credenciais e como as senhas são armazenadas como uma **SecureString**, consulte a descrição do parâmetro de **credencial** .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-156">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString**, see the **Credential** parameter's description.</span></span>

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
> <span data-ttu-id="1bbc0-157">Lembre-se de que, se você usar o trecho acima em um script, defina o valor do parâmetro de **escopo** como "global" para garantir que a unidade persiste fora do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-157">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="1bbc0-158">A `$cred` variável armazena um objeto **PSCredential** que contém as credenciais da conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-158">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="1bbc0-159">`Get-Credential` solicita que você insira a senha que está armazenada em uma **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-159">`Get-Credential` prompts you to enter the password that's stored in a **SecureString**.</span></span>

<span data-ttu-id="1bbc0-160">`New-PSDrive` cria a unidade de rede mapeada usando vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-160">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="1bbc0-161">**Nome** especifica a `S` letra da unidade que o Windows aceita.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-161">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="1bbc0-162">e **root** define `\\Server01\Scripts` como o local em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-162">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="1bbc0-163">**Persistir** cria uma unidade de rede mapeada do Windows que é salva no computador local.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-163">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="1bbc0-164">**PSProvider** especifica o `FileSystem` provedor.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-164">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="1bbc0-165">A **credencial** usa a `$cred` variável para obter as credenciais da conta de serviço para autenticação.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-165">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="1bbc0-166">A unidade mapeada pode ser exibida no computador local em sessões do PowerShell, explorador de arquivos e com ferramentas como **net use**.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-166">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use**.</span></span> <span data-ttu-id="1bbc0-167">Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="1bbc0-167">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="1bbc0-168">Exemplo 5: criar unidades persistentes e temporárias</span><span class="sxs-lookup"><span data-stu-id="1bbc0-168">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="1bbc0-169">Este exemplo mostra a diferença entre uma unidade de rede mapeada persistente e uma unidade temporária do PowerShell que é mapeada para o mesmo compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-169">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="1bbc0-170">Se você fechar a sessão do PowerShell e, em seguida, abrir uma nova sessão, o temporário `PSDrive:` não estará disponível, mas a `X:` unidade persistente estará disponível.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-170">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="1bbc0-171">Ao decidir qual método usar para mapear unidades de rede, considere como você usará a unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-171">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="1bbc0-172">Por exemplo, se precisa ser persistente e se a unidade precisa estar visível para outros recursos do Windows.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-172">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

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

## <span data-ttu-id="1bbc0-173">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1bbc0-173">PARAMETERS</span></span>

### <span data-ttu-id="1bbc0-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1bbc0-174">-Confirm</span></span>

<span data-ttu-id="1bbc0-175">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-175">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1bbc0-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="1bbc0-176">-Credential</span></span>

<span data-ttu-id="1bbc0-177">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-177">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="1bbc0-178">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-178">The default is the current user.</span></span>

<span data-ttu-id="1bbc0-179">Desde o PowerShell 3,0, quando o valor do parâmetro **raiz** é um caminho UNC, você pode usar credenciais para criar unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-179">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="1bbc0-180">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-180">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1bbc0-181">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-181">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="1bbc0-182">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-182">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1bbc0-183">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-183">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="1bbc0-184">-Description</span><span class="sxs-lookup"><span data-stu-id="1bbc0-184">-Description</span></span>

<span data-ttu-id="1bbc0-185">Especifica uma breve descrição em texto da unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-185">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="1bbc0-186">Digite qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-186">Type any string.</span></span>

<span data-ttu-id="1bbc0-187">Para ver as descrições de todas as unidades de sessão, `Get-PSDrive | Format-Table Name, Description` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-187">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="1bbc0-188">Para ver a descrição de uma unidade específica, digite `(Get-PSDrive <DriveName>).Description` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-188">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

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

### <span data-ttu-id="1bbc0-189">-Name</span><span class="sxs-lookup"><span data-stu-id="1bbc0-189">-Name</span></span>

<span data-ttu-id="1bbc0-190">Especifica um nome para a nova unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-190">Specifies a name for the new drive.</span></span> <span data-ttu-id="1bbc0-191">Para unidades de rede mapeadas persistentes, use uma letra de unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-191">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="1bbc0-192">Para unidades temporárias do PowerShell, você não está limitado a letras de unidade, use qualquer cadeia de caracteres válida.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-192">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

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

### <span data-ttu-id="1bbc0-193">-Persistir</span><span class="sxs-lookup"><span data-stu-id="1bbc0-193">-Persist</span></span>

<span data-ttu-id="1bbc0-194">Indica que esse cmdlet cria uma unidade de rede mapeada do Windows.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-194">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="1bbc0-195">O parâmetro **Persist** só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-195">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="1bbc0-196">Unidades de rede mapeadas são salvos no Windows no computador local.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-196">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="1bbc0-197">Eles são persistentes, não específicos da sessão e podem ser exibidos e gerenciados no explorador de arquivos e em outras ferramentas.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-197">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="1bbc0-198">Quando você faz o escopo do comando localmente, sem o fato de a Sourcing, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual você executa o comando.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-198">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="1bbc0-199">Se você executar `New-PSDrive` dentro de um script e quiser que a nova unidade persista indefinidamente, você deverá criar o código-fonte do script.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-199">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="1bbc0-200">Para obter melhores resultados, para forçar uma nova unidade a persistir, especifique **global** como o valor do parâmetro de **escopo** e inclua **Persist** no comando.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-200">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="1bbc0-201">O nome da unidade deve ser uma letra, como `D` ou `E` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-201">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="1bbc0-202">O valor do parâmetro **raiz** deve ser um caminho UNC de um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-202">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="1bbc0-203">O valor do parâmetro **PSProvider** deve ser `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-203">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="1bbc0-204">Para desconectar uma unidade de rede mapeada do Windows, use o `Remove-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-204">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="1bbc0-205">Quando você desconecta uma unidade de rede mapeada do Windows, o mapeamento é excluído permanentemente do computador, não apenas da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-205">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="1bbc0-206">Unidades de rede mapeadas são específicas para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-206">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="1bbc0-207">Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-207">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

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

### <span data-ttu-id="1bbc0-208">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="1bbc0-208">-PSProvider</span></span>

<span data-ttu-id="1bbc0-209">Especifica o provedor do PowerShell que oferece suporte a unidades desse tipo.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-209">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="1bbc0-210">Por exemplo, se a unidade estiver associada a um compartilhamento de rede ou diretório de sistema de arquivos, o provedor do PowerShell será `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-210">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="1bbc0-211">Se a unidade estiver associada a uma chave do registro, o provedor será `Registry` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-211">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="1bbc0-212">Unidades temporárias do PowerShell podem ser associadas a qualquer provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-212">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="1bbc0-213">Unidades de rede mapeadas podem ser associadas somente ao `FileSystem` provedor.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-213">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="1bbc0-214">Para ver uma lista dos provedores em sua sessão do PowerShell, use o `Get-PSProvider` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-214">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

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

### <span data-ttu-id="1bbc0-215">-Raiz</span><span class="sxs-lookup"><span data-stu-id="1bbc0-215">-Root</span></span>

<span data-ttu-id="1bbc0-216">Especifica o local do repositório de dados para o qual uma unidade do PowerShell é mapeada.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-216">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="1bbc0-217">Por exemplo, especifique um compartilhamento de rede, como `\\Server01\Public` um diretório local, como `C:\Program Files` , ou uma chave do registro, como `HKLM:\Software\Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-217">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="1bbc0-218">As unidades temporárias do PowerShell podem ser associadas a um local local ou remoto em qualquer unidade de provedor com suporte.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-218">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="1bbc0-219">Unidades de rede mapeadas podem ser associadas somente a um local de sistema de arquivos em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-219">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

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

### <span data-ttu-id="1bbc0-220">-Escopo</span><span class="sxs-lookup"><span data-stu-id="1bbc0-220">-Scope</span></span>

<span data-ttu-id="1bbc0-221">Especifica um escopo para a unidade.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-221">Specifies a scope for the drive.</span></span> <span data-ttu-id="1bbc0-222">Os valores aceitáveis para esse parâmetro são: **global**, **local** e **script**, ou um número relativo ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-222">The acceptable values for this parameter are: **Global**, **Local**, and **Script**, or a number relative to the current scope.</span></span> <span data-ttu-id="1bbc0-223">O número de escopos é 0 com o número de escopos.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-223">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="1bbc0-224">O número de escopo atual é 0 e seu pai é 1.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-224">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="1bbc0-225">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-225">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="1bbc0-226">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1bbc0-226">-WhatIf</span></span>

<span data-ttu-id="1bbc0-227">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-227">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1bbc0-228">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-228">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="1bbc0-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1bbc0-229">CommonParameters</span></span>

<span data-ttu-id="1bbc0-230">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-230">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1bbc0-231">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1bbc0-232">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1bbc0-232">INPUTS</span></span>

### <span data-ttu-id="1bbc0-233">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1bbc0-233">None</span></span>

<span data-ttu-id="1bbc0-234">Não é possível pipeline de entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-234">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="1bbc0-235">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1bbc0-235">OUTPUTS</span></span>

### <span data-ttu-id="1bbc0-236">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="1bbc0-236">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="1bbc0-237">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1bbc0-237">NOTES</span></span>

<span data-ttu-id="1bbc0-238">`New-PSDrive` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-238">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1bbc0-239">Para listar os provedores disponíveis em sua sessão, use `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="1bbc0-239">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="1bbc0-240">Para obter mais informações sobre provedores, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="1bbc0-240">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="1bbc0-241">Unidades de rede mapeadas são específicas para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-241">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="1bbc0-242">Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="1bbc0-242">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="1bbc0-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1bbc0-243">RELATED LINKS</span></span>

[<span data-ttu-id="1bbc0-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1bbc0-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="1bbc0-245">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="1bbc0-245">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="1bbc0-246">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1bbc0-246">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="1bbc0-247">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1bbc0-247">Remove-PSDrive</span></span>](Remove-PSDrive.md)

