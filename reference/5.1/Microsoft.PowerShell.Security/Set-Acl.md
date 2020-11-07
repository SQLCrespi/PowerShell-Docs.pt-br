---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: e2e2166bbe65256c67937be8da1a3e82944840e8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343225"
---
# <span data-ttu-id="a800e-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="a800e-103">Set-Acl</span></span>

## <span data-ttu-id="a800e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a800e-104">SYNOPSIS</span></span>
<span data-ttu-id="a800e-105">Altera o descritor de segurança de um item especificado, como um arquivo ou chave do registro.</span><span class="sxs-lookup"><span data-stu-id="a800e-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="a800e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a800e-106">SYNTAX</span></span>

### <span data-ttu-id="a800e-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="a800e-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>] [-ClearCentralAccessPolicy]
 [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a800e-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="a800e-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a800e-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="a800e-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>]
 [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="a800e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a800e-110">DESCRIPTION</span></span>

<span data-ttu-id="a800e-111">O `Set-Acl` cmdlet altera o descritor de segurança de um item especificado, como um arquivo ou uma chave do registro, para corresponder aos valores em um descritor de segurança fornecido por você.</span><span class="sxs-lookup"><span data-stu-id="a800e-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="a800e-112">Para usar `Set-Acl` , use o **caminho** ou o parâmetro **InputObject** para identificar o item cujo descritor de segurança você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="a800e-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="a800e-113">Em seguida, use os parâmetros **AclObject** ou **SecurityDescriptor** para fornecer um descritor de segurança com os valores que deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="a800e-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="a800e-114">`Set-Acl` aplica o descritor de segurança fornecido.</span><span class="sxs-lookup"><span data-stu-id="a800e-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="a800e-115">Ele usa o valor do parâmetro **AclObject** como um modelo e altera os valores no descritor de segurança do item para que correspondam aos valores do parâmetro **AclObject**.</span><span class="sxs-lookup"><span data-stu-id="a800e-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="a800e-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a800e-116">EXAMPLES</span></span>

### <span data-ttu-id="a800e-117">Exemplo 1: copiar um descritor de segurança de um arquivo para outro</span><span class="sxs-lookup"><span data-stu-id="a800e-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="a800e-118">Esse comando copia os valores do descritor de segurança do arquivo Dog.txt para o descritor de segurança do arquivo Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="a800e-119">Quando os comandos forem concluídos, os descritores de segurança dos arquivos Dog.txt e Cat.txt serão idênticos.</span><span class="sxs-lookup"><span data-stu-id="a800e-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="a800e-120">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="a800e-121">O operador de atribuição ( `=` ) armazena o descritor de segurança no valor da variável $DogACL.</span><span class="sxs-lookup"><span data-stu-id="a800e-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="a800e-122">O segundo comando usa `Set-Acl` para alterar os valores na ACL de Cat.txt para os valores em `$DogACL` .</span><span class="sxs-lookup"><span data-stu-id="a800e-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="a800e-123">O valor do parâmetro **Path** é o caminho para o arquivo Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="a800e-124">O valor do parâmetro **AclObject** é a ACL de modelo, nesse caso, a acl de Dog.txt como salva na `$DogACL` variável.</span><span class="sxs-lookup"><span data-stu-id="a800e-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="a800e-125">Exemplo 2: usar o operador de pipeline para passar um descritor</span><span class="sxs-lookup"><span data-stu-id="a800e-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="a800e-126">Esse comando é quase o mesmo que o comando no exemplo anterior, exceto pelo fato de que ele usa um operador de pipeline ( `|` ) para enviar o descritor de segurança de um `Get-Acl` comando para um `Set-Acl` comando.</span><span class="sxs-lookup"><span data-stu-id="a800e-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="a800e-127">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="a800e-128">O operador de pipeline ( `|` ) passa um objeto que representa o descritor de segurança Dog.txt para o `Set-Acl` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a800e-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="a800e-129">O segundo comando usa `Set-Acl` para aplicar o descritor de segurança do Dog.txt ao Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="a800e-130">Quando o comando for concluído, as ACLs dos arquivos Dog.txt e Cat.txt serão idênticas.</span><span class="sxs-lookup"><span data-stu-id="a800e-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="a800e-131">Exemplo 3: aplicar um descritor de segurança a vários arquivos</span><span class="sxs-lookup"><span data-stu-id="a800e-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="a800e-132">Esses comandos aplicam os descritores de segurança no arquivo de File0.txt a todos os arquivos de texto no `C:\Temp` diretório e em todos os seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="a800e-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="a800e-133">O primeiro comando obtém o descritor de segurança do arquivo de File0.txt no diretório atual e usa o operador de atribuição ( `=` ) para armazená-lo na `$NewACL` variável.</span><span class="sxs-lookup"><span data-stu-id="a800e-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="a800e-134">O primeiro comando no pipeline usa o cmdlet Get-ChildItem para obter todos os arquivos de texto no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="a800e-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="a800e-135">O parâmetro **recurse** estende o comando para todos os subdiretórios de `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="a800e-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="a800e-136">O parâmetro **include** limita os arquivos recuperados para aqueles com a `.txt` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a800e-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="a800e-137">O parâmetro **Force** obtém arquivos ocultos, que do contrário, seriam excluídos.</span><span class="sxs-lookup"><span data-stu-id="a800e-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="a800e-138">(Não é possível usar `c:\temp\*.txt` o, porque o parâmetro **recurse** funciona em diretórios, não em arquivos.)</span><span class="sxs-lookup"><span data-stu-id="a800e-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="a800e-139">O operador de pipeline ( `|` ) envia os objetos que representam os arquivos recuperados para o `Set-Acl` cmdlet, que aplica o descritor de segurança no parâmetro **AclObject** a todos os arquivos no pipeline.</span><span class="sxs-lookup"><span data-stu-id="a800e-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="a800e-140">Na prática, é melhor usar o parâmetro **WhatIf** com todos os `Set-Acl` comandos que podem afetar mais de um item.</span><span class="sxs-lookup"><span data-stu-id="a800e-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="a800e-141">Nesse caso, o segundo comando no pipeline seria `Set-Acl -AclObject $NewAcl -WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="a800e-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="a800e-142">Esse comando lista os arquivos que seriam afetados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="a800e-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="a800e-143">Depois de examinar o resultado, você pode executar o comando novamente sem o parâmetro **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="a800e-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="a800e-144">Exemplo 4: desabilitar a herança e preservar as regras de acesso herdadas</span><span class="sxs-lookup"><span data-stu-id="a800e-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="a800e-145">Esses comandos desativarão a herança de acesso das pastas pai, enquanto ainda preservam as regras de acesso herdadas existentes.</span><span class="sxs-lookup"><span data-stu-id="a800e-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="a800e-146">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="a800e-147">Em seguida, as variáveis são criadas para converter as regras de acesso herdadas para regras de acesso explícitas.</span><span class="sxs-lookup"><span data-stu-id="a800e-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="a800e-148">Para proteger as regras de acesso associadas a ela da herança, defina a `$isProtected` variável como `$true` . para permitir a herança, defina `$isProtected` como `$false` .</span><span class="sxs-lookup"><span data-stu-id="a800e-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="a800e-149">Para obter mais informações, consulte [definir a proteção da regra de acesso](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span><span class="sxs-lookup"><span data-stu-id="a800e-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="a800e-150">A `$preserveInheritance` variável definida como `$true` para preservar as regras de acesso herdadas; false para remover as regras de acesso herdadas.</span><span class="sxs-lookup"><span data-stu-id="a800e-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="a800e-151">Em seguida, a proteção da regra de acesso é atualizada usando o método **SetAccessRuleProtection ()** .</span><span class="sxs-lookup"><span data-stu-id="a800e-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="a800e-152">O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="a800e-153">Quando o comando for concluído, as ACLs do Dog.txt que foram herdadas da pasta pets serão aplicadas diretamente ao Dog.txt, e as novas políticas de acesso adicionadas aos animais de estimação não alterarão o acesso ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="a800e-154">Exemplo 5: conceder aos administradores controle total do arquivo</span><span class="sxs-lookup"><span data-stu-id="a800e-154">Example 5: Grant Administrators Full Control of the file</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="a800e-155">Esse comando concederá ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="a800e-156">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="a800e-157">As variáveis seguintes são criadas para conceder ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="a800e-158">A `$identity` variável definida como o nome de uma [conta de usuário](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span><span class="sxs-lookup"><span data-stu-id="a800e-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span> <span data-ttu-id="a800e-159">A `$fileSystemRights` variável definida como FullControl e pode ser qualquer um dos valores de [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) que especifica o tipo de operação associado à regra de acesso.</span><span class="sxs-lookup"><span data-stu-id="a800e-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="a800e-160">A `$type` variável definida como "Allow" especifica se a operação deve ser permitida ou negada.</span><span class="sxs-lookup"><span data-stu-id="a800e-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="a800e-161">A `$fileSystemAccessRuleArgumentList` variável é uma lista de argumentos que deve ser passada ao fazer o novo objeto **FileSystemAccessRule** .</span><span class="sxs-lookup"><span data-stu-id="a800e-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="a800e-162">Em seguida, um novo objeto **FileSystemAccessRule** é criado e o objeto **FileSystemAccessRule** é passado para o método **SetAccessRule ()** , adiciona a nova regra de acesso.</span><span class="sxs-lookup"><span data-stu-id="a800e-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="a800e-163">O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="a800e-164">Quando o comando for concluído, o grupo **BUILTIN\Administradores** terá controle total da Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="a800e-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="a800e-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a800e-165">PARAMETERS</span></span>

### <span data-ttu-id="a800e-166">-AclObject</span><span class="sxs-lookup"><span data-stu-id="a800e-166">-AclObject</span></span>

<span data-ttu-id="a800e-167">Especifica uma ACL com os valores de propriedade desejados.</span><span class="sxs-lookup"><span data-stu-id="a800e-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="a800e-168">`Set-Acl` altera a ACL do item especificado pelo **caminho** ou o parâmetro **InputObject** para corresponder aos valores no objeto de segurança especificado.</span><span class="sxs-lookup"><span data-stu-id="a800e-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="a800e-169">Você pode salvar a saída de um `Get-Acl` comando em uma variável e, em seguida, usar o parâmetro **AclObject** para passar a variável ou digitar um `Get-Acl` comando.</span><span class="sxs-lookup"><span data-stu-id="a800e-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a800e-170">-CentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a800e-170">-CentralAccessPolicy</span></span>

<span data-ttu-id="a800e-171">Estabelece ou altera a política de acesso central do item.</span><span class="sxs-lookup"><span data-stu-id="a800e-171">Establishes or changes the central access policy of the item.</span></span>
<span data-ttu-id="a800e-172">Insira a ID ou nome amigável do ponto de acesso para cliente de uma política de acesso central no computador.</span><span class="sxs-lookup"><span data-stu-id="a800e-172">Enter the CAP ID or friendly name of a central access policy on the computer.</span></span>

<span data-ttu-id="a800e-173">A partir do Windows Server 2012, os administradores podem usar Active Directory e Política de Grupo para definir políticas de acesso central para usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="a800e-173">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span>
<span data-ttu-id="a800e-174">Para obter mais informações, consulte [controle de acesso dinâmico: visão geral do cenário](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="a800e-174">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="a800e-175">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a800e-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a800e-176">-ClearCentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a800e-176">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="a800e-177">Remove a política de acesso central do item especificado.</span><span class="sxs-lookup"><span data-stu-id="a800e-177">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="a800e-178">A partir do Windows Server 2012, os administradores podem usar Active Directory e Política de Grupo para definir políticas de acesso central para usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="a800e-178">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="a800e-179">Para obter mais informações, consulte [controle de acesso dinâmico: visão geral do cenário](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="a800e-179">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="a800e-180">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a800e-180">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a800e-181">-Excluir</span><span class="sxs-lookup"><span data-stu-id="a800e-181">-Exclude</span></span>

<span data-ttu-id="a800e-182">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="a800e-182">Omits the specified items.</span></span> <span data-ttu-id="a800e-183">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a800e-183">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a800e-184">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a800e-184">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a800e-185">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a800e-185">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="a800e-186">-Filter</span><span class="sxs-lookup"><span data-stu-id="a800e-186">-Filter</span></span>

<span data-ttu-id="a800e-187">Especifica um filtro no formato ou linguagem do provedor.</span><span class="sxs-lookup"><span data-stu-id="a800e-187">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="a800e-188">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a800e-188">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a800e-189">A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="a800e-189">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="a800e-190">Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao recuperar os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="a800e-190">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a800e-191">-Incluir</span><span class="sxs-lookup"><span data-stu-id="a800e-191">-Include</span></span>

<span data-ttu-id="a800e-192">Altera somente os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="a800e-192">Changes only the specified items.</span></span> <span data-ttu-id="a800e-193">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a800e-193">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a800e-194">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a800e-194">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a800e-195">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a800e-195">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="a800e-196">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a800e-196">-InputObject</span></span>

<span data-ttu-id="a800e-197">Altera o descritor de segurança do objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="a800e-197">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="a800e-198">Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.</span><span class="sxs-lookup"><span data-stu-id="a800e-198">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="a800e-199">Não é possível canalizar o objeto a ser alterado para `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="a800e-199">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="a800e-200">Em vez disso, use o parâmetro **InputObject** explicitamente no comando.</span><span class="sxs-lookup"><span data-stu-id="a800e-200">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="a800e-201">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a800e-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a800e-202">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a800e-202">-LiteralPath</span></span>

<span data-ttu-id="a800e-203">Altera o descritor de segurança do item especificado.</span><span class="sxs-lookup"><span data-stu-id="a800e-203">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="a800e-204">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="a800e-204">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="a800e-205">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="a800e-205">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a800e-206">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="a800e-206">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="a800e-207">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="a800e-207">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a800e-208">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a800e-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a800e-209">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a800e-209">-Passthru</span></span>

<span data-ttu-id="a800e-210">Retorna um objeto que representa o descritor de segurança que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="a800e-210">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="a800e-211">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="a800e-211">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a800e-212">-Path</span><span class="sxs-lookup"><span data-stu-id="a800e-212">-Path</span></span>

<span data-ttu-id="a800e-213">Altera o descritor de segurança do item especificado.</span><span class="sxs-lookup"><span data-stu-id="a800e-213">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="a800e-214">Digite o caminho para um item, como um caminho para um arquivo ou chave de registro.</span><span class="sxs-lookup"><span data-stu-id="a800e-214">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="a800e-215">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a800e-215">Wildcards are permitted.</span></span>

<span data-ttu-id="a800e-216">Se você passar um objeto de segurança para `Set-Acl` (usando os parâmetros **AclObject** ou **SecurityDescriptor** ou passando um objeto de segurança de Get-Acl para `Set-Acl` ), e omitir o parâmetro **Path** (nome e valor), `Set-Acl` o usará o caminho incluído no objeto de segurança.</span><span class="sxs-lookup"><span data-stu-id="a800e-216">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a800e-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a800e-217">-Confirm</span></span>

<span data-ttu-id="a800e-218">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a800e-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a800e-219">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="a800e-219">-UseTransaction</span></span>

<span data-ttu-id="a800e-220">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="a800e-220">Includes the command in the active transaction.</span></span>
<span data-ttu-id="a800e-221">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="a800e-221">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="a800e-222">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="a800e-222">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="a800e-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a800e-223">-WhatIf</span></span>

<span data-ttu-id="a800e-224">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a800e-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a800e-225">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a800e-225">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a800e-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a800e-226">CommonParameters</span></span>

<span data-ttu-id="a800e-227">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a800e-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a800e-228">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a800e-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a800e-229">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a800e-229">INPUTS</span></span>

### <span data-ttu-id="a800e-230">System. Security. AccessControl. ObjectSecurity, System. Security. AccessControl. CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="a800e-230">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="a800e-231">É possível canalizar um objeto ACL ou um descritor de segurança para o `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="a800e-231">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="a800e-232">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a800e-232">OUTPUTS</span></span>

### <span data-ttu-id="a800e-233">System. Security. AccessControl. FileSecurity</span><span class="sxs-lookup"><span data-stu-id="a800e-233">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="a800e-234">Por padrão, `Set-Acl` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a800e-234">By default, `Set-Acl` does not generate any output.</span></span> <span data-ttu-id="a800e-235">No entanto, se usar o parâmetro **Passthru** , ele gera um objeto de segurança.</span><span class="sxs-lookup"><span data-stu-id="a800e-235">However, if you use the **Passthru** parameter, it generates a security object.</span></span> <span data-ttu-id="a800e-236">O tipo do objeto de segurança depende do tipo do item.</span><span class="sxs-lookup"><span data-stu-id="a800e-236">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="a800e-237">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a800e-237">NOTES</span></span>

<span data-ttu-id="a800e-238">O `Set-Acl` cmdlet é suportado pelo sistema de arquivos do PowerShell e pelos provedores de registro.</span><span class="sxs-lookup"><span data-stu-id="a800e-238">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="a800e-239">Dessa forma, você pode usá-lo para alterar os descritores de segurança dos arquivos, diretórios e chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="a800e-239">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="a800e-240">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a800e-240">RELATED LINKS</span></span>

[<span data-ttu-id="a800e-241">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="a800e-241">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="a800e-242">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="a800e-242">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="a800e-243">ObjectSecurity.SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="a800e-243">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="a800e-244">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="a800e-244">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
