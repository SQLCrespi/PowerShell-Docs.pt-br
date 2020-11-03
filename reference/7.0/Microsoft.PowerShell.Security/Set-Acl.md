---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: 3c8f26884ac0eda1ece799bbd49a7863b6d2239c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193124"
---
# <span data-ttu-id="f703a-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="f703a-103">Set-Acl</span></span>

## <span data-ttu-id="f703a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f703a-104">SYNOPSIS</span></span>
<span data-ttu-id="f703a-105">Altera o descritor de segurança de um item especificado, como um arquivo ou chave do registro.</span><span class="sxs-lookup"><span data-stu-id="f703a-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="f703a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f703a-106">SYNTAX</span></span>

### <span data-ttu-id="f703a-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="f703a-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f703a-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="f703a-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f703a-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f703a-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f703a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f703a-110">DESCRIPTION</span></span>

<span data-ttu-id="f703a-111">O `Set-Acl` cmdlet altera o descritor de segurança de um item especificado, como um arquivo ou uma chave do registro, para corresponder aos valores em um descritor de segurança fornecido por você.</span><span class="sxs-lookup"><span data-stu-id="f703a-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="f703a-112">Para usar `Set-Acl` , use o **caminho** ou o parâmetro **InputObject** para identificar o item cujo descritor de segurança você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="f703a-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="f703a-113">Em seguida, use os parâmetros **AclObject** ou **SecurityDescriptor** para fornecer um descritor de segurança com os valores que deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="f703a-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="f703a-114">`Set-Acl` aplica o descritor de segurança fornecido.</span><span class="sxs-lookup"><span data-stu-id="f703a-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="f703a-115">Ele usa o valor do parâmetro **AclObject** como um modelo e altera os valores no descritor de segurança do item para que correspondam aos valores do parâmetro **AclObject** .</span><span class="sxs-lookup"><span data-stu-id="f703a-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="f703a-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f703a-116">EXAMPLES</span></span>

### <span data-ttu-id="f703a-117">Exemplo 1: copiar um descritor de segurança de um arquivo para outro</span><span class="sxs-lookup"><span data-stu-id="f703a-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="f703a-118">Esse comando copia os valores do descritor de segurança do arquivo Dog.txt para o descritor de segurança do arquivo Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="f703a-119">Quando os comandos forem concluídos, os descritores de segurança dos arquivos Dog.txt e Cat.txt serão idênticos.</span><span class="sxs-lookup"><span data-stu-id="f703a-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="f703a-120">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="f703a-121">O operador de atribuição ( `=` ) armazena o descritor de segurança no valor da variável $DogACL.</span><span class="sxs-lookup"><span data-stu-id="f703a-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="f703a-122">O segundo comando usa `Set-Acl` para alterar os valores na ACL de Cat.txt para os valores em `$DogACL` .</span><span class="sxs-lookup"><span data-stu-id="f703a-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="f703a-123">O valor do parâmetro **Path** é o caminho para o arquivo Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="f703a-124">O valor do parâmetro **AclObject** é a ACL de modelo, nesse caso, a acl de Dog.txt como salva na `$DogACL` variável.</span><span class="sxs-lookup"><span data-stu-id="f703a-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="f703a-125">Exemplo 2: usar o operador de pipeline para passar um descritor</span><span class="sxs-lookup"><span data-stu-id="f703a-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="f703a-126">Esse comando é quase o mesmo que o comando no exemplo anterior, exceto pelo fato de que ele usa um operador de pipeline ( `|` ) para enviar o descritor de segurança de um `Get-Acl` comando para um `Set-Acl` comando.</span><span class="sxs-lookup"><span data-stu-id="f703a-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="f703a-127">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="f703a-128">O operador de pipeline ( `|` ) passa um objeto que representa o descritor de segurança Dog.txt para o `Set-Acl` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f703a-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="f703a-129">O segundo comando usa `Set-Acl` para aplicar o descritor de segurança do Dog.txt ao Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="f703a-130">Quando o comando for concluído, as ACLs dos arquivos Dog.txt e Cat.txt serão idênticas.</span><span class="sxs-lookup"><span data-stu-id="f703a-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="f703a-131">Exemplo 3: aplicar um descritor de segurança a vários arquivos</span><span class="sxs-lookup"><span data-stu-id="f703a-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="f703a-132">Esses comandos aplicam os descritores de segurança no arquivo de File0.txt a todos os arquivos de texto no `C:\Temp` diretório e em todos os seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="f703a-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="f703a-133">O primeiro comando obtém o descritor de segurança do arquivo de File0.txt no diretório atual e usa o operador de atribuição ( `=` ) para armazená-lo na `$NewACL` variável.</span><span class="sxs-lookup"><span data-stu-id="f703a-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="f703a-134">O primeiro comando no pipeline usa o cmdlet Get-ChildItem para obter todos os arquivos de texto no `C:\Temp` diretório.</span><span class="sxs-lookup"><span data-stu-id="f703a-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="f703a-135">O parâmetro **recurse** estende o comando para todos os subdiretórios de `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="f703a-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="f703a-136">O parâmetro **include** limita os arquivos recuperados para aqueles com a `.txt` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f703a-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="f703a-137">O parâmetro **Force** obtém arquivos ocultos, que do contrário, seriam excluídos.</span><span class="sxs-lookup"><span data-stu-id="f703a-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="f703a-138">(Não é possível usar `c:\temp\*.txt` o, porque o parâmetro **recurse** funciona em diretórios, não em arquivos.)</span><span class="sxs-lookup"><span data-stu-id="f703a-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="f703a-139">O operador de pipeline ( `|` ) envia os objetos que representam os arquivos recuperados para o `Set-Acl` cmdlet, que aplica o descritor de segurança no parâmetro **AclObject** a todos os arquivos no pipeline.</span><span class="sxs-lookup"><span data-stu-id="f703a-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="f703a-140">Na prática, é melhor usar o parâmetro **WhatIf** com todos os `Set-Acl` comandos que podem afetar mais de um item.</span><span class="sxs-lookup"><span data-stu-id="f703a-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="f703a-141">Nesse caso, o segundo comando no pipeline seria `Set-Acl -AclObject $NewAcl -WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="f703a-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="f703a-142">Esse comando lista os arquivos que seriam afetados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="f703a-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="f703a-143">Depois de examinar o resultado, você pode executar o comando novamente sem o parâmetro **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="f703a-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="f703a-144">Exemplo 4: desabilitar a herança e preservar as regras de acesso herdadas</span><span class="sxs-lookup"><span data-stu-id="f703a-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="f703a-145">Esses comandos desativarão a herança de acesso das pastas pai, enquanto ainda preservam as regras de acesso herdadas existentes.</span><span class="sxs-lookup"><span data-stu-id="f703a-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="f703a-146">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="f703a-147">Em seguida, as variáveis são criadas para converter as regras de acesso herdadas para regras de acesso explícitas.</span><span class="sxs-lookup"><span data-stu-id="f703a-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="f703a-148">Para proteger as regras de acesso associadas a ela da herança, defina a `$isProtected` variável como `$true` . para permitir a herança, defina `$isProtected` como `$false` .</span><span class="sxs-lookup"><span data-stu-id="f703a-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="f703a-149">Para obter mais informações, consulte [definir a proteção da regra de acesso](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span><span class="sxs-lookup"><span data-stu-id="f703a-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="f703a-150">A `$preserveInheritance` variável definida como `$true` para preservar as regras de acesso herdadas; false para remover as regras de acesso herdadas.</span><span class="sxs-lookup"><span data-stu-id="f703a-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="f703a-151">Em seguida, a proteção da regra de acesso é atualizada usando o método **SetAccessRuleProtection ()** .</span><span class="sxs-lookup"><span data-stu-id="f703a-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="f703a-152">O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="f703a-153">Quando o comando for concluído, as ACLs do Dog.txt que foram herdadas da pasta pets serão aplicadas diretamente ao Dog.txt, e as novas políticas de acesso adicionadas aos animais de estimação não alterarão o acesso ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="f703a-154">Exemplo 5: conceder aos administradores controle total do arquivo</span><span class="sxs-lookup"><span data-stu-id="f703a-154">Example 5: Grant Administrators Full Control of the file</span></span>

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

<span data-ttu-id="f703a-155">Esse comando concederá ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="f703a-156">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="f703a-157">As variáveis seguintes são criadas para conceder ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="f703a-158">A `$identity` variável definida como o nome de uma [conta de usuário](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span><span class="sxs-lookup"><span data-stu-id="f703a-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span>
<span data-ttu-id="f703a-159">A `$fileSystemRights` variável definida como FullControl e pode ser qualquer um dos valores de [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) que especifica o tipo de operação associado à regra de acesso.</span><span class="sxs-lookup"><span data-stu-id="f703a-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="f703a-160">A `$type` variável definida como "Allow" especifica se a operação deve ser permitida ou negada.</span><span class="sxs-lookup"><span data-stu-id="f703a-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="f703a-161">A `$fileSystemAccessRuleArgumentList` variável é uma lista de argumentos que deve ser passada ao fazer o novo objeto **FileSystemAccessRule** .</span><span class="sxs-lookup"><span data-stu-id="f703a-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="f703a-162">Em seguida, um novo objeto **FileSystemAccessRule** é criado e o objeto **FileSystemAccessRule** é passado para o método **SetAccessRule ()** , adiciona a nova regra de acesso.</span><span class="sxs-lookup"><span data-stu-id="f703a-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="f703a-163">O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span>
<span data-ttu-id="f703a-164">Quando o comando for concluído, o grupo **BUILTIN\Administradores** terá controle total da Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="f703a-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="f703a-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f703a-165">PARAMETERS</span></span>

### <span data-ttu-id="f703a-166">-AclObject</span><span class="sxs-lookup"><span data-stu-id="f703a-166">-AclObject</span></span>

<span data-ttu-id="f703a-167">Especifica uma ACL com os valores de propriedade desejados.</span><span class="sxs-lookup"><span data-stu-id="f703a-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="f703a-168">`Set-Acl` altera a ACL do item especificado pelo **caminho** ou o parâmetro **InputObject** para corresponder aos valores no objeto de segurança especificado.</span><span class="sxs-lookup"><span data-stu-id="f703a-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="f703a-169">Você pode salvar a saída de um `Get-Acl` comando em uma variável e, em seguida, usar o parâmetro **AclObject** para passar a variável ou digitar um `Get-Acl` comando.</span><span class="sxs-lookup"><span data-stu-id="f703a-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

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

### <span data-ttu-id="f703a-170">-ClearCentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f703a-170">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="f703a-171">Remove a política de acesso central do item especificado.</span><span class="sxs-lookup"><span data-stu-id="f703a-171">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="f703a-172">A partir do Windows Server 2012, os administradores podem usar Active Directory e Política de Grupo para definir políticas de acesso central para usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="f703a-172">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="f703a-173">Para obter mais informações, consulte [controle de acesso dinâmico: visão geral do cenário](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="f703a-173">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="f703a-174">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f703a-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f703a-175">-Excluir</span><span class="sxs-lookup"><span data-stu-id="f703a-175">-Exclude</span></span>

<span data-ttu-id="f703a-176">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="f703a-176">Omits the specified items.</span></span> <span data-ttu-id="f703a-177">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="f703a-177">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f703a-178">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="f703a-178">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f703a-179">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f703a-179">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f703a-180">-Filter</span><span class="sxs-lookup"><span data-stu-id="f703a-180">-Filter</span></span>

<span data-ttu-id="f703a-181">Especifica um filtro no formato ou linguagem do provedor.</span><span class="sxs-lookup"><span data-stu-id="f703a-181">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="f703a-182">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="f703a-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f703a-183">A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="f703a-183">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="f703a-184">Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao recuperar os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="f703a-184">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="f703a-185">-Incluir</span><span class="sxs-lookup"><span data-stu-id="f703a-185">-Include</span></span>

<span data-ttu-id="f703a-186">Altera somente os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="f703a-186">Changes only the specified items.</span></span> <span data-ttu-id="f703a-187">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="f703a-187">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="f703a-188">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="f703a-188">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f703a-189">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f703a-189">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="f703a-190">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f703a-190">-InputObject</span></span>

<span data-ttu-id="f703a-191">Altera o descritor de segurança do objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="f703a-191">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="f703a-192">Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.</span><span class="sxs-lookup"><span data-stu-id="f703a-192">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="f703a-193">Não é possível canalizar o objeto a ser alterado para `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="f703a-193">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="f703a-194">Em vez disso, use o parâmetro **InputObject** explicitamente no comando.</span><span class="sxs-lookup"><span data-stu-id="f703a-194">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="f703a-195">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f703a-195">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f703a-196">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f703a-196">-LiteralPath</span></span>

<span data-ttu-id="f703a-197">Altera o descritor de segurança do item especificado.</span><span class="sxs-lookup"><span data-stu-id="f703a-197">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="f703a-198">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="f703a-198">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f703a-199">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="f703a-199">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f703a-200">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="f703a-200">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="f703a-201">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="f703a-201">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="f703a-202">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f703a-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f703a-203">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f703a-203">-Passthru</span></span>

<span data-ttu-id="f703a-204">Retorna um objeto que representa o descritor de segurança que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="f703a-204">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="f703a-205">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f703a-205">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f703a-206">-Path</span><span class="sxs-lookup"><span data-stu-id="f703a-206">-Path</span></span>

<span data-ttu-id="f703a-207">Altera o descritor de segurança do item especificado.</span><span class="sxs-lookup"><span data-stu-id="f703a-207">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="f703a-208">Digite o caminho para um item, como um caminho para um arquivo ou chave de registro.</span><span class="sxs-lookup"><span data-stu-id="f703a-208">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="f703a-209">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f703a-209">Wildcards are permitted.</span></span>

<span data-ttu-id="f703a-210">Se você passar um objeto de segurança para `Set-Acl` (usando os parâmetros **AclObject** ou **SecurityDescriptor** ou passando um objeto de segurança de Get-Acl para `Set-Acl` ), e omitir o parâmetro **Path** (nome e valor), `Set-Acl` o usará o caminho incluído no objeto de segurança.</span><span class="sxs-lookup"><span data-stu-id="f703a-210">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

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

### <span data-ttu-id="f703a-211">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f703a-211">-Confirm</span></span>

<span data-ttu-id="f703a-212">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f703a-212">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f703a-213">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f703a-213">-WhatIf</span></span>

<span data-ttu-id="f703a-214">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f703a-214">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f703a-215">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f703a-215">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f703a-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f703a-216">CommonParameters</span></span>

<span data-ttu-id="f703a-217">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f703a-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f703a-218">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f703a-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f703a-219">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f703a-219">INPUTS</span></span>

### <span data-ttu-id="f703a-220">System. Security. AccessControl. ObjectSecurity, System. Security. AccessControl. CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="f703a-220">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="f703a-221">É possível canalizar um objeto ACL ou um descritor de segurança para o `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="f703a-221">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="f703a-222">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f703a-222">OUTPUTS</span></span>

### <span data-ttu-id="f703a-223">System. Security. AccessControl. FileSecurity</span><span class="sxs-lookup"><span data-stu-id="f703a-223">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="f703a-224">Por padrão, `Set-Acl` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f703a-224">By default, `Set-Acl` does not generate any output.</span></span>
<span data-ttu-id="f703a-225">No entanto, se usar o parâmetro **Passthru** , ele gera um objeto de segurança.</span><span class="sxs-lookup"><span data-stu-id="f703a-225">However, if you use the **Passthru** parameter, it generates a security object.</span></span>
<span data-ttu-id="f703a-226">O tipo do objeto de segurança depende do tipo do item.</span><span class="sxs-lookup"><span data-stu-id="f703a-226">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="f703a-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f703a-227">NOTES</span></span>

 <span data-ttu-id="f703a-228">O `Set-Acl` cmdlet é suportado pelo sistema de arquivos do PowerShell e pelos provedores de registro.</span><span class="sxs-lookup"><span data-stu-id="f703a-228">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="f703a-229">Dessa forma, você pode usá-lo para alterar os descritores de segurança dos arquivos, diretórios e chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="f703a-229">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="f703a-230">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f703a-230">RELATED LINKS</span></span>

[<span data-ttu-id="f703a-231">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="f703a-231">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="f703a-232">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="f703a-232">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="f703a-233">ObjectSecurity.SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="f703a-233">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="f703a-234">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="f703a-234">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
