---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 7ec2c3025f62a64cd24298c0749d40fa5eff4904
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346081"
---
# <span data-ttu-id="6497a-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="6497a-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="6497a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6497a-104">SYNOPSIS</span></span>
<span data-ttu-id="6497a-105">Converte uma cadeia de caracteres SDDL em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="6497a-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="6497a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6497a-106">SYNTAX</span></span>

### <span data-ttu-id="6497a-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="6497a-107">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="6497a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6497a-108">DESCRIPTION</span></span>

<span data-ttu-id="6497a-109">O `ConvertFrom-SddlString` cmdlet converte uma cadeia de caracteres de linguagem de definição de descritor de segurança em um objeto **PSCustomObject** personalizado com as seguintes propriedades: Owner, Group, DiscretionaryAcl, SystemAcl e RawDescriptor.</span><span class="sxs-lookup"><span data-stu-id="6497a-109">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="6497a-110">As propriedades Owner, Group, DiscretionaryAcl e SystemAcl contêm uma representação de texto legível dos direitos de acesso especificados em uma cadeia de caracteres SDDL.</span><span class="sxs-lookup"><span data-stu-id="6497a-110">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="6497a-111">Esse cmdlet foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="6497a-111">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="6497a-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6497a-112">EXAMPLES</span></span>

### <span data-ttu-id="6497a-113">Exemplo 1: converter o SDDL de direitos de acesso do sistema de arquivos em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="6497a-113">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="6497a-114">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a pasta C:\Windows e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="6497a-114">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="6497a-115">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="6497a-115">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="6497a-116">Exemplo 2: converter o SDDL de direitos de acesso do registro em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="6497a-116">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="6497a-117">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="6497a-117">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="6497a-118">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="6497a-118">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="6497a-119">Ele usa o `-Type` parâmetro para especificar que a cadeia de caracteres SDDL representa um descritor de segurança do registro.</span><span class="sxs-lookup"><span data-stu-id="6497a-119">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="6497a-120">Exemplo 3: converter o SDDL de direitos de acesso do registro em um PSCustomObject usando ConvertFrom-SddlString com e sem o `-Type` parâmetro</span><span class="sxs-lookup"><span data-stu-id="6497a-120">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="6497a-121">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="6497a-121">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="6497a-122">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="6497a-122">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="6497a-123">Ele não usa o `-Type` parâmetro, portanto, os direitos de acesso mostrados são para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6497a-123">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="6497a-124">O terceiro comando usa o `ConvertFrom-SddlString` cmdlet com o `-Type` parâmetro, de modo que os direitos de acesso retornados são para o registro.</span><span class="sxs-lookup"><span data-stu-id="6497a-124">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="6497a-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6497a-125">PARAMETERS</span></span>

### <span data-ttu-id="6497a-126">-SDDL</span><span class="sxs-lookup"><span data-stu-id="6497a-126">-Sddl</span></span>

<span data-ttu-id="6497a-127">Especifica a cadeia de caracteres que representa o descritor de segurança na sintaxe SDDL.</span><span class="sxs-lookup"><span data-stu-id="6497a-127">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

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

### <span data-ttu-id="6497a-128">-Type</span><span class="sxs-lookup"><span data-stu-id="6497a-128">-Type</span></span>

<span data-ttu-id="6497a-129">Especifica o tipo de direitos que a cadeia de caracteres SDDL representa.</span><span class="sxs-lookup"><span data-stu-id="6497a-129">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="6497a-130">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="6497a-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6497a-131">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="6497a-131">FileSystemRights</span></span>
- <span data-ttu-id="6497a-132">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="6497a-132">RegistryRights</span></span>
- <span data-ttu-id="6497a-133">ActiveDirectoryRights</span><span class="sxs-lookup"><span data-stu-id="6497a-133">ActiveDirectoryRights</span></span>
- <span data-ttu-id="6497a-134">MutexRights</span><span class="sxs-lookup"><span data-stu-id="6497a-134">MutexRights</span></span>
- <span data-ttu-id="6497a-135">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="6497a-135">SemaphoreRights</span></span>
- <span data-ttu-id="6497a-136">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="6497a-136">CryptoKeyRights</span></span>
- <span data-ttu-id="6497a-137">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="6497a-137">EventWaitHandleRights</span></span>

<span data-ttu-id="6497a-138">Por padrão, o cmdlet usa direitos de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6497a-138">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="6497a-139">Não há suporte para CryptoKeyRights e ActiveDirectoryRights no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6497a-139">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6497a-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6497a-140">CommonParameters</span></span>

<span data-ttu-id="6497a-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6497a-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6497a-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6497a-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6497a-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6497a-143">INPUTS</span></span>

### <span data-ttu-id="6497a-144">System.String</span><span class="sxs-lookup"><span data-stu-id="6497a-144">System.String</span></span>

<span data-ttu-id="6497a-145">É possível canalizar uma cadeia de caracteres SDDL para `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="6497a-145">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="6497a-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6497a-146">OUTPUTS</span></span>

## <span data-ttu-id="6497a-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6497a-147">NOTES</span></span>

<span data-ttu-id="6497a-148">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="6497a-148">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="6497a-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6497a-149">RELATED LINKS</span></span>

[<span data-ttu-id="6497a-150">Linguagem de definição do descritor de segurança</span><span class="sxs-lookup"><span data-stu-id="6497a-150">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
