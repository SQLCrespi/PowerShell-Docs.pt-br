---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: baf06c34511217f23d876843007525b9ce17f35b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596795"
---
# <span data-ttu-id="f845c-102">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="f845c-102">Get-PfxCertificate</span></span>

## <span data-ttu-id="f845c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f845c-103">SYNOPSIS</span></span>
<span data-ttu-id="f845c-104">Obtém informações sobre os arquivos de certificado PFX no computador.</span><span class="sxs-lookup"><span data-stu-id="f845c-104">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="f845c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f845c-105">SYNTAX</span></span>

### <span data-ttu-id="f845c-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="f845c-106">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="f845c-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f845c-107">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="f845c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f845c-108">DESCRIPTION</span></span>

<span data-ttu-id="f845c-109">O `Get-PfxCertificate` cmdlet obtém um objeto que representa cada arquivo de certificado pfx especificado.</span><span class="sxs-lookup"><span data-stu-id="f845c-109">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="f845c-110">Um arquivo PFX inclui o certificado e uma chave privada.</span><span class="sxs-lookup"><span data-stu-id="f845c-110">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="f845c-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f845c-111">EXAMPLES</span></span>

### <span data-ttu-id="f845c-112">Exemplo 1: obter um certificado PFX</span><span class="sxs-lookup"><span data-stu-id="f845c-112">Example 1: Get a PFX certificate</span></span>

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

<span data-ttu-id="f845c-113">Esse comando obtém informações sobre o arquivo de certificado. pfx de teste no sistema.</span><span class="sxs-lookup"><span data-stu-id="f845c-113">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="f845c-114">Exemplo 2: obter um certificado PFX de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="f845c-114">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="f845c-115">Esse comando obtém um arquivo de certificado PFX do computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="f845c-115">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="f845c-116">Ele usa `Invoke-Command` para executar um `Get-PfxCertificate` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="f845c-116">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="f845c-117">Quando o arquivo de certificado PFX não está protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.</span><span class="sxs-lookup"><span data-stu-id="f845c-117">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="f845c-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f845c-118">PARAMETERS</span></span>

### <span data-ttu-id="f845c-119">-FilePath</span><span class="sxs-lookup"><span data-stu-id="f845c-119">-FilePath</span></span>

<span data-ttu-id="f845c-120">Especifica o caminho completo para o arquivo PFX do arquivo protegido.</span><span class="sxs-lookup"><span data-stu-id="f845c-120">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="f845c-121">Se você especificar um valor para esse parâmetro, não será necessário digitar `-FilePath` na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f845c-121">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

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

### <span data-ttu-id="f845c-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f845c-122">-LiteralPath</span></span>

<span data-ttu-id="f845c-123">O caminho completo para o arquivo PFX do arquivo protegido.</span><span class="sxs-lookup"><span data-stu-id="f845c-123">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="f845c-124">Ao contrário de **FilePath**, o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="f845c-124">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f845c-125">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="f845c-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f845c-126">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="f845c-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f845c-127">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="f845c-127">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="f845c-128">-NoPromptForPassword</span><span class="sxs-lookup"><span data-stu-id="f845c-128">-NoPromptForPassword</span></span>

<span data-ttu-id="f845c-129">Suprime a solicitação de uma senha.</span><span class="sxs-lookup"><span data-stu-id="f845c-129">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="f845c-130">-Password</span><span class="sxs-lookup"><span data-stu-id="f845c-130">-Password</span></span>

<span data-ttu-id="f845c-131">Especifica uma senha necessária para acessar um `.pfx` arquivo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f845c-131">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="f845c-132">Esse parâmetro foi introduzido no PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="f845c-132">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="f845c-133">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="f845c-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="f845c-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f845c-134">CommonParameters</span></span>

<span data-ttu-id="f845c-135">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f845c-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f845c-136">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f845c-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f845c-137">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f845c-137">INPUTS</span></span>

### <span data-ttu-id="f845c-138">System.String</span><span class="sxs-lookup"><span data-stu-id="f845c-138">System.String</span></span>

<span data-ttu-id="f845c-139">É possível canalizar uma cadeia de caracteres que contém um caminho de arquivo para `Get-PfxCertificate` .</span><span class="sxs-lookup"><span data-stu-id="f845c-139">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="f845c-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f845c-140">OUTPUTS</span></span>

### <span data-ttu-id="f845c-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="f845c-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="f845c-142">`Get-PfxCertificate` Retorna um objeto para cada certificado que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="f845c-142">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="f845c-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f845c-143">NOTES</span></span>

<span data-ttu-id="f845c-144">Ao usar o `Invoke-Command` cmdlet para executar um `Get-PfxCertificate` comando remotamente, e o arquivo de certificado pfx não é protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.</span><span class="sxs-lookup"><span data-stu-id="f845c-144">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="f845c-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f845c-145">RELATED LINKS</span></span>

[<span data-ttu-id="f845c-146">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="f845c-146">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="f845c-147">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="f845c-147">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

