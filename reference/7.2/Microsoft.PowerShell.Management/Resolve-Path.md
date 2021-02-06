---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 0481526aead285e3d5fb494218d1573e03216f2e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597007"
---
# <span data-ttu-id="3bbe5-102">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-102">Resolve-Path</span></span>

## <span data-ttu-id="3bbe5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3bbe5-103">SYNOPSIS</span></span>
<span data-ttu-id="3bbe5-104">Resolve os caracteres curinga em um caminho e exibe o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-104">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="3bbe5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3bbe5-105">SYNTAX</span></span>

### <span data-ttu-id="3bbe5-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="3bbe5-106">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="3bbe5-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3bbe5-107">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="3bbe5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3bbe5-108">DESCRIPTION</span></span>

<span data-ttu-id="3bbe5-109">O `Resolve-Path` cmdlet exibe os itens e contêineres que correspondem ao padrão curinga no local especificado.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-109">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="3bbe5-110">A correspondência pode incluir arquivos, pastas, chaves do registro ou qualquer outro objeto acessível por meio de um provedor PSDrive.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-110">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="3bbe5-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3bbe5-111">EXAMPLES</span></span>

### <span data-ttu-id="3bbe5-112">Exemplo 1: resolver o caminho da pasta base</span><span class="sxs-lookup"><span data-stu-id="3bbe5-112">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="3bbe5-113">O caractere de til (~) é uma notação abreviada para a pasta base do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-113">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="3bbe5-114">Este exemplo mostra `Resolve-Path` o retorno do valor de caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-114">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="3bbe5-115">Exemplo 2: resolver o caminho da pasta do Windows</span><span class="sxs-lookup"><span data-stu-id="3bbe5-115">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="3bbe5-116">Quando executado da raiz da unidade C:, esse comando retorna o caminho da pasta do Windows na unidade C:.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-116">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="3bbe5-117">Exemplo 3: obter todos os caminhos na pasta do Windows</span><span class="sxs-lookup"><span data-stu-id="3bbe5-117">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="3bbe5-118">Esse comando retorna todas as pastas na pasta C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-118">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="3bbe5-119">O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres de caminho para `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-119">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="3bbe5-120">Exemplo 4: resolver um caminho UNC</span><span class="sxs-lookup"><span data-stu-id="3bbe5-120">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="3bbe5-121">Esse comando resolve um caminho de convenção de nomenclatura Universal (UNC) e retorna os compartilhamentos no caminho.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-121">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="3bbe5-122">Exemplo 5: obter caminhos relativos</span><span class="sxs-lookup"><span data-stu-id="3bbe5-122">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="3bbe5-123">Esse comando retorna os caminhos relativos para os diretórios na raiz da unidade C:.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-123">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="3bbe5-124">Exemplo 6: resolver um caminho contendo colchetes</span><span class="sxs-lookup"><span data-stu-id="3bbe5-124">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="3bbe5-125">Este exemplo usa o parâmetro **LiteralPath** para resolver o caminho da \[ subpasta XML de teste \] .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-125">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="3bbe5-126">O uso de **LiteralPath** faz com que os colchetes sejam tratados como caracteres normais em vez de uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-126">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="3bbe5-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3bbe5-127">PARAMETERS</span></span>

### <span data-ttu-id="3bbe5-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="3bbe5-128">-Credential</span></span>

<span data-ttu-id="3bbe5-129">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-129">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="3bbe5-130">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-130">The default is the current user.</span></span>

<span data-ttu-id="3bbe5-131">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou passe um objeto **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-131">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="3bbe5-132">Você pode criar um objeto **PSCredential** usando o `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-132">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3bbe5-133">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-133">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="3bbe5-134">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-134">This parameter is not supported by any providers installed with PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3bbe5-135">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3bbe5-135">-LiteralPath</span></span>

<span data-ttu-id="3bbe5-136">Especifica os caminhos que serão resolvidos.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-136">Specifies the path to be resolved.</span></span>
<span data-ttu-id="3bbe5-137">O valor do parâmetro **LiteralPath** é usado exatamente como tipado.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-137">The value of the **LiteralPath** parameter is used exactly as typed.</span></span>
<span data-ttu-id="3bbe5-138">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-138">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="3bbe5-139">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-139">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="3bbe5-140">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3bbe5-141">-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-141">-Path</span></span>

<span data-ttu-id="3bbe5-142">Especifica o caminho do PowerShell a ser resolvido.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-142">Specifies the PowerShell path to resolve.</span></span>
<span data-ttu-id="3bbe5-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-143">This parameter is required.</span></span>
<span data-ttu-id="3bbe5-144">Também é possível canalizar uma cadeia de caracteres de caminho para `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-144">You can also pipe a path string to `Resolve-Path`.</span></span>
<span data-ttu-id="3bbe5-145">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-145">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3bbe5-146">-Relativo</span><span class="sxs-lookup"><span data-stu-id="3bbe5-146">-Relative</span></span>

<span data-ttu-id="3bbe5-147">Indica que esse cmdlet retorna um caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-147">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="3bbe5-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3bbe5-148">CommonParameters</span></span>

<span data-ttu-id="3bbe5-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3bbe5-150">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3bbe5-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3bbe5-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3bbe5-151">INPUTS</span></span>

### <span data-ttu-id="3bbe5-152">System.String</span><span class="sxs-lookup"><span data-stu-id="3bbe5-152">System.String</span></span>

<span data-ttu-id="3bbe5-153">É possível canalizar uma cadeia de caracteres que contém um caminho para este cmdlet</span><span class="sxs-lookup"><span data-stu-id="3bbe5-153">You can pipe a string that contains a path to this cmdlet</span></span>

## <span data-ttu-id="3bbe5-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3bbe5-154">OUTPUTS</span></span>

### <span data-ttu-id="3bbe5-155">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="3bbe5-155">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="3bbe5-156">Retorna um objeto **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-156">Returns a **PathInfo** object.</span></span> <span data-ttu-id="3bbe5-157">Retorna um valor de cadeia de caracteres para o caminho resolvido se você especificar o parâmetro **relativo** .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-157">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="3bbe5-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3bbe5-158">NOTES</span></span>

<span data-ttu-id="3bbe5-159">Os `*-Path` cmdlets funcionam com o sistema de arquivos, o registro e os provedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-159">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="3bbe5-160">`Resolve-Path` o foi projetado para funcionar com qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-160">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="3bbe5-161">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="3bbe5-161">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3bbe5-162">Para obter mais informações, consulte [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="3bbe5-162">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="3bbe5-163">`Resolve-Path` resolve apenas os caminhos existentes.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-163">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="3bbe5-164">Ele não pode ser usado para resolver um local que ainda não existe.</span><span class="sxs-lookup"><span data-stu-id="3bbe5-164">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="3bbe5-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3bbe5-165">RELATED LINKS</span></span>

[<span data-ttu-id="3bbe5-166">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-166">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="3bbe5-167">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-167">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="3bbe5-168">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-168">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="3bbe5-169">Test-Path</span><span class="sxs-lookup"><span data-stu-id="3bbe5-169">Test-Path</span></span>](Test-Path.md)

