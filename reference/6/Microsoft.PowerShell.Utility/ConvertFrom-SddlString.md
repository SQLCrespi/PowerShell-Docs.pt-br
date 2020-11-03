---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 8552bec8029210553a8d4e51dcecb88948eb353e
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "93195282"
---
# <span data-ttu-id="18fa4-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="18fa4-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="18fa4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="18fa4-104">SYNOPSIS</span></span>
<span data-ttu-id="18fa4-105">Converte uma cadeia de caracteres SDDL em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="18fa4-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="18fa4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18fa4-106">SYNTAX</span></span>

### <span data-ttu-id="18fa4-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="18fa4-107">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="18fa4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18fa4-108">DESCRIPTION</span></span>

<span data-ttu-id="18fa4-109">O `ConvertFrom-SddlString` cmdlet converte uma cadeia de caracteres de linguagem de definição de descritor de segurança em um objeto **PSCustomObject** personalizado com as seguintes propriedades: Owner, Group, DiscretionaryAcl, SystemAcl e RawDescriptor.</span><span class="sxs-lookup"><span data-stu-id="18fa4-109">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="18fa4-110">As propriedades Owner, Group, DiscretionaryAcl e SystemAcl contêm uma representação de texto legível dos direitos de acesso especificados em uma cadeia de caracteres SDDL.</span><span class="sxs-lookup"><span data-stu-id="18fa4-110">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="18fa4-111">Esse cmdlet foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="18fa4-111">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="18fa4-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="18fa4-112">EXAMPLES</span></span>

### <span data-ttu-id="18fa4-113">Exemplo 1: converter o SDDL de direitos de acesso do sistema de arquivos em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="18fa4-113">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="18fa4-114">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a pasta C:\Windows e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="18fa4-114">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="18fa4-115">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="18fa4-115">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="18fa4-116">Exemplo 2: converter o SDDL de direitos de acesso do registro em um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="18fa4-116">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="18fa4-117">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="18fa4-117">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="18fa4-118">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="18fa4-118">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="18fa4-119">Ele usa o `-Type` parâmetro para especificar que a cadeia de caracteres SDDL representa um descritor de segurança do registro.</span><span class="sxs-lookup"><span data-stu-id="18fa4-119">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="18fa4-120">Exemplo 3: converter o SDDL de direitos de acesso do registro em um PSCustomObject usando ConvertFrom-SddlString com e sem o `-Type` parâmetro</span><span class="sxs-lookup"><span data-stu-id="18fa4-120">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="18fa4-121">O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.</span><span class="sxs-lookup"><span data-stu-id="18fa4-121">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="18fa4-122">O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="18fa4-122">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="18fa4-123">Ele não usa o `-Type` parâmetro, portanto, os direitos de acesso mostrados são para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18fa4-123">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="18fa4-124">O terceiro comando usa o `ConvertFrom-SddlString` cmdlet com o `-Type` parâmetro, de modo que os direitos de acesso retornados são para o registro.</span><span class="sxs-lookup"><span data-stu-id="18fa4-124">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="18fa4-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18fa4-125">PARAMETERS</span></span>

### <span data-ttu-id="18fa4-126">-SDDL</span><span class="sxs-lookup"><span data-stu-id="18fa4-126">-Sddl</span></span>

<span data-ttu-id="18fa4-127">Especifica a cadeia de caracteres que representa o descritor de segurança na sintaxe SDDL.</span><span class="sxs-lookup"><span data-stu-id="18fa4-127">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

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

### <span data-ttu-id="18fa4-128">-Type</span><span class="sxs-lookup"><span data-stu-id="18fa4-128">-Type</span></span>

<span data-ttu-id="18fa4-129">Especifica o tipo de direitos que a cadeia de caracteres SDDL representa.</span><span class="sxs-lookup"><span data-stu-id="18fa4-129">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="18fa4-130">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="18fa4-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="18fa4-131">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-131">FileSystemRights</span></span>
- <span data-ttu-id="18fa4-132">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-132">RegistryRights</span></span>
- <span data-ttu-id="18fa4-133">ActiveDirectoryRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-133">ActiveDirectoryRights</span></span>
- <span data-ttu-id="18fa4-134">MutexRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-134">MutexRights</span></span>
- <span data-ttu-id="18fa4-135">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-135">SemaphoreRights</span></span>
- <span data-ttu-id="18fa4-136">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-136">CryptoKeyRights</span></span>
- <span data-ttu-id="18fa4-137">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="18fa4-137">EventWaitHandleRights</span></span>

<span data-ttu-id="18fa4-138">Por padrão, o cmdlet usa direitos de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18fa4-138">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="18fa4-139">Não há suporte para CryptoKeyRights e ActiveDirectoryRights no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="18fa4-139">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

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

### <span data-ttu-id="18fa4-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="18fa4-140">CommonParameters</span></span>

<span data-ttu-id="18fa4-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="18fa4-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18fa4-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="18fa4-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18fa4-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="18fa4-143">INPUTS</span></span>

### <span data-ttu-id="18fa4-144">System.String</span><span class="sxs-lookup"><span data-stu-id="18fa4-144">System.String</span></span>

<span data-ttu-id="18fa4-145">É possível canalizar uma cadeia de caracteres SDDL para `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="18fa4-145">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="18fa4-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="18fa4-146">OUTPUTS</span></span>

## <span data-ttu-id="18fa4-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="18fa4-147">NOTES</span></span>

## <span data-ttu-id="18fa4-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="18fa4-148">RELATED LINKS</span></span>

[<span data-ttu-id="18fa4-149">Linguagem de definição do descritor de segurança</span><span class="sxs-lookup"><span data-stu-id="18fa4-149">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
