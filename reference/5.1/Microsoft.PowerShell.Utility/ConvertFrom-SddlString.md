---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: dbb6263c628c08876f64335b420f76d5ecc8f59b
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344364"
---
# <span data-ttu-id="8ed20-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="8ed20-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="8ed20-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8ed20-104">SYNOPSIS</span></span>
<span data-ttu-id="8ed20-105">Converte uma cadeia de caracteres SDDL em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ed20-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="8ed20-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ed20-106">SYNTAX</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <Object>] [<CommonParameters>]
```

## <span data-ttu-id="8ed20-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ed20-107">DESCRIPTION</span></span>

<span data-ttu-id="8ed20-108">O `ConvertFrom-SddlString` cmdlet converte uma cadeia de caracteres de linguagem de definição de descritor de segurança em um objeto **PSCustomObject** personalizado com as seguintes propriedades: Owner, Group, DiscretionaryAcl, SystemAcl e RawDescriptor.</span><span class="sxs-lookup"><span data-stu-id="8ed20-108">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="8ed20-109">As propriedades Owner, Group, DiscretionaryAcl e SystemAcl contêm uma representação de texto legível dos direitos de acesso especificados em uma cadeia de caracteres SDDL.</span><span class="sxs-lookup"><span data-stu-id="8ed20-109">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="8ed20-110">Esse cmdlet foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="8ed20-110">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="8ed20-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8ed20-111">EXAMPLES</span></span>

### <span data-ttu-id="8ed20-112">Exemplo 1: converter o SDDL de direitos de acesso do sistema de arquivos em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="8ed20-112">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="8ed20-113">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a pasta C:\Windows e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="8ed20-113">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="8ed20-114">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="8ed20-114">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="8ed20-115">Exemplo 2: converter o SDDL de direitos de acesso do registro em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="8ed20-115">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="8ed20-116">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="8ed20-116">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="8ed20-117">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="8ed20-117">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="8ed20-118">Ele usa o `-Type` parâmetro para especificar que a cadeia de caracteres SDDL representa um descritor de segurança do registro.</span><span class="sxs-lookup"><span data-stu-id="8ed20-118">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="8ed20-119">Exemplo 3: converter o SDDL de direitos de acesso do registro em um PSCustomObject usando ConvertFrom-SddlString com e sem o `-Type` parâmetro</span><span class="sxs-lookup"><span data-stu-id="8ed20-119">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="8ed20-120">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="8ed20-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="8ed20-121">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="8ed20-121">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="8ed20-122">Ele não usa o `-Type` parâmetro, portanto, os direitos de acesso mostrados são para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8ed20-122">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="8ed20-123">O terceiro comando usa o `ConvertFrom-SddlString` cmdlet com o `-Type` parâmetro, de modo que os direitos de acesso retornados são para o registro.</span><span class="sxs-lookup"><span data-stu-id="8ed20-123">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

### <span data-ttu-id="8ed20-124">Exemplo 4: converter Active Directory SDDL de direitos de acesso para um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="8ed20-124">Example 4: Convert Active Directory access rights SDDL to a PSCustomObject</span></span>

```powershell
$user = [ADSI]"LDAP://CN=username,CN=Users,DC=domain,DC=com"
ConvertFrom-SddlString $user.psbase.ObjectSecurity.Sddl -Type ActiveDirectoryRights
```

<span data-ttu-id="8ed20-125">O primeiro comando usa Active Directory ADSI (interfaces de serviço) para obter o objeto de usuário e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="8ed20-125">The first command uses Active Directory Service Interfaces (ADSI) to get the user object and saves it in the variable.</span></span>

<span data-ttu-id="8ed20-126">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="8ed20-126">The second command uses the `ConvertFrom-SddlString` cmdlet to get text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="8ed20-127">Ele usa o `-Type` parâmetro para especificar que a cadeia de caracteres SDDL representa um descritor de segurança Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ed20-127">It uses the `-Type` parameter to specify that SDDL string represents an Active Directory security descriptor.</span></span>

## <span data-ttu-id="8ed20-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ed20-128">PARAMETERS</span></span>

### <span data-ttu-id="8ed20-129">-SDDL</span><span class="sxs-lookup"><span data-stu-id="8ed20-129">-Sddl</span></span>

<span data-ttu-id="8ed20-130">Especifica a cadeia de caracteres que representa o descritor de segurança na sintaxe SDDL.</span><span class="sxs-lookup"><span data-stu-id="8ed20-130">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8ed20-131">-Type</span><span class="sxs-lookup"><span data-stu-id="8ed20-131">-Type</span></span>

<span data-ttu-id="8ed20-132">Especifica o tipo de direitos que a cadeia de caracteres SDDL representa.</span><span class="sxs-lookup"><span data-stu-id="8ed20-132">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="8ed20-133">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="8ed20-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8ed20-134">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-134">FileSystemRights</span></span>
- <span data-ttu-id="8ed20-135">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-135">RegistryRights</span></span>
- <span data-ttu-id="8ed20-136">ActiveDirectoryRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-136">ActiveDirectoryRights</span></span>
- <span data-ttu-id="8ed20-137">MutexRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-137">MutexRights</span></span>
- <span data-ttu-id="8ed20-138">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-138">SemaphoreRights</span></span>
- <span data-ttu-id="8ed20-139">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-139">CryptoKeyRights</span></span>
- <span data-ttu-id="8ed20-140">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="8ed20-140">EventWaitHandleRights</span></span>

<span data-ttu-id="8ed20-141">Por padrão, o cmdlet usa direitos de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8ed20-141">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="8ed20-142">Não há suporte para CryptoKeyRights e ActiveDirectoryRights no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="8ed20-142">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8ed20-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8ed20-143">CommonParameters</span></span>

<span data-ttu-id="8ed20-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ed20-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ed20-145">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ed20-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ed20-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8ed20-146">INPUTS</span></span>

### <span data-ttu-id="8ed20-147">System.String</span><span class="sxs-lookup"><span data-stu-id="8ed20-147">System.String</span></span>

<span data-ttu-id="8ed20-148">É possível canalizar uma cadeia de caracteres SDDL para `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="8ed20-148">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="8ed20-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8ed20-149">OUTPUTS</span></span>

## <span data-ttu-id="8ed20-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8ed20-150">NOTES</span></span>

## <span data-ttu-id="8ed20-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8ed20-151">RELATED LINKS</span></span>

[<span data-ttu-id="8ed20-152">Linguagem de definição do descritor de segurança</span><span class="sxs-lookup"><span data-stu-id="8ed20-152">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
