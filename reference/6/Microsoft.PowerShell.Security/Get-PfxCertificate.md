---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 67bb56a50f452475ba12abb2fccaeeaf5785c8b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194541"
---
# <span data-ttu-id="3b72a-103">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="3b72a-103">Get-PfxCertificate</span></span>

## <span data-ttu-id="3b72a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3b72a-104">SYNOPSIS</span></span>
<span data-ttu-id="3b72a-105">Obtém informações sobre os arquivos de certificado PFX no computador.</span><span class="sxs-lookup"><span data-stu-id="3b72a-105">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="3b72a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b72a-106">SYNTAX</span></span>

### <span data-ttu-id="3b72a-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="3b72a-107">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="3b72a-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b72a-108">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="3b72a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b72a-109">DESCRIPTION</span></span>

<span data-ttu-id="3b72a-110">O `Get-PfxCertificate` cmdlet obtém um objeto que representa cada arquivo de certificado pfx especificado.</span><span class="sxs-lookup"><span data-stu-id="3b72a-110">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="3b72a-111">Um arquivo PFX inclui o certificado e uma chave privada.</span><span class="sxs-lookup"><span data-stu-id="3b72a-111">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="3b72a-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3b72a-112">EXAMPLES</span></span>

### <span data-ttu-id="3b72a-113">Exemplo 1: obter um certificado PFX</span><span class="sxs-lookup"><span data-stu-id="3b72a-113">Example 1: Get a PFX certificate</span></span>

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

<span data-ttu-id="3b72a-114">Esse comando obtém informações sobre o arquivo de certificado. pfx de teste no sistema.</span><span class="sxs-lookup"><span data-stu-id="3b72a-114">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="3b72a-115">Exemplo 2: obter um certificado PFX de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="3b72a-115">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="3b72a-116">Esse comando obtém um arquivo de certificado PFX do computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="3b72a-116">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="3b72a-117">Ele usa `Invoke-Command` para executar um `Get-PfxCertificate` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="3b72a-117">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="3b72a-118">Quando o arquivo de certificado PFX não está protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.</span><span class="sxs-lookup"><span data-stu-id="3b72a-118">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="3b72a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b72a-119">PARAMETERS</span></span>

### <span data-ttu-id="3b72a-120">-FilePath</span><span class="sxs-lookup"><span data-stu-id="3b72a-120">-FilePath</span></span>

<span data-ttu-id="3b72a-121">Especifica o caminho completo para o arquivo PFX do arquivo protegido.</span><span class="sxs-lookup"><span data-stu-id="3b72a-121">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="3b72a-122">Se você especificar um valor para esse parâmetro, não será necessário digitar `-FilePath` na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3b72a-122">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3b72a-123">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3b72a-123">-LiteralPath</span></span>

<span data-ttu-id="3b72a-124">O caminho completo para o arquivo PFX do arquivo protegido.</span><span class="sxs-lookup"><span data-stu-id="3b72a-124">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="3b72a-125">Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="3b72a-125">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="3b72a-126">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="3b72a-126">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3b72a-127">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3b72a-127">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3b72a-128">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="3b72a-128">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3b72a-129">-NoPromptForPassword</span><span class="sxs-lookup"><span data-stu-id="3b72a-129">-NoPromptForPassword</span></span>

<span data-ttu-id="3b72a-130">Suprime a solicitação de uma senha.</span><span class="sxs-lookup"><span data-stu-id="3b72a-130">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="3b72a-131">-Password</span><span class="sxs-lookup"><span data-stu-id="3b72a-131">-Password</span></span>

<span data-ttu-id="3b72a-132">Especifica uma senha necessária para acessar um `.pfx` arquivo de certificado.</span><span class="sxs-lookup"><span data-stu-id="3b72a-132">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="3b72a-133">Esse parâmetro foi introduzido no PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="3b72a-133">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="3b72a-134">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="3b72a-134">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b72a-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3b72a-135">CommonParameters</span></span>

<span data-ttu-id="3b72a-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b72a-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b72a-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b72a-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b72a-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3b72a-138">INPUTS</span></span>

### <span data-ttu-id="3b72a-139">System.String</span><span class="sxs-lookup"><span data-stu-id="3b72a-139">System.String</span></span>

<span data-ttu-id="3b72a-140">É possível canalizar uma cadeia de caracteres que contém um caminho de arquivo para `Get-PfxCertificate` .</span><span class="sxs-lookup"><span data-stu-id="3b72a-140">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="3b72a-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3b72a-141">OUTPUTS</span></span>

### <span data-ttu-id="3b72a-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="3b72a-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="3b72a-143">`Get-PfxCertificate` Retorna um objeto para cada certificado que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="3b72a-143">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="3b72a-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3b72a-144">NOTES</span></span>

<span data-ttu-id="3b72a-145">Ao usar o `Invoke-Command` cmdlet para executar um `Get-PfxCertificate` comando remotamente, e o arquivo de certificado pfx não é protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.</span><span class="sxs-lookup"><span data-stu-id="3b72a-145">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="3b72a-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3b72a-146">RELATED LINKS</span></span>

[<span data-ttu-id="3b72a-147">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="3b72a-147">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="3b72a-148">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="3b72a-148">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)
