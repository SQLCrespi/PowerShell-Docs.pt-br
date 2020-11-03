---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: a48f2c5f62990258f14195eda934bbf4bbe589a1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193937"
---
# <span data-ttu-id="458ae-103">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-103">Resolve-Path</span></span>

## <span data-ttu-id="458ae-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="458ae-104">SYNOPSIS</span></span>
<span data-ttu-id="458ae-105">Resolve os caracteres curinga em um caminho e exibe o conteúdo do caminho.</span><span class="sxs-lookup"><span data-stu-id="458ae-105">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="458ae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="458ae-106">SYNTAX</span></span>

### <span data-ttu-id="458ae-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="458ae-107">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="458ae-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="458ae-108">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="458ae-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="458ae-109">DESCRIPTION</span></span>

<span data-ttu-id="458ae-110">O `Resolve-Path` cmdlet exibe os itens e contêineres que correspondem ao padrão curinga no local especificado.</span><span class="sxs-lookup"><span data-stu-id="458ae-110">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="458ae-111">A correspondência pode incluir arquivos, pastas, chaves do registro ou qualquer outro objeto acessível por meio de um provedor PSDrive.</span><span class="sxs-lookup"><span data-stu-id="458ae-111">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="458ae-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="458ae-112">EXAMPLES</span></span>

### <span data-ttu-id="458ae-113">Exemplo 1: resolver o caminho da pasta base</span><span class="sxs-lookup"><span data-stu-id="458ae-113">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="458ae-114">O caractere de til (~) é uma notação abreviada para a pasta base do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="458ae-114">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="458ae-115">Este exemplo mostra `Resolve-Path` o retorno do valor de caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="458ae-115">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="458ae-116">Exemplo 2: resolver o caminho da pasta do Windows</span><span class="sxs-lookup"><span data-stu-id="458ae-116">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="458ae-117">Quando executado da raiz da unidade C:, esse comando retorna o caminho da pasta do Windows na unidade C:.</span><span class="sxs-lookup"><span data-stu-id="458ae-117">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="458ae-118">Exemplo 3: obter todos os caminhos na pasta do Windows</span><span class="sxs-lookup"><span data-stu-id="458ae-118">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="458ae-119">Esse comando retorna todas as pastas na pasta C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="458ae-119">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="458ae-120">O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres de caminho para `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="458ae-120">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="458ae-121">Exemplo 4: resolver um caminho UNC</span><span class="sxs-lookup"><span data-stu-id="458ae-121">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="458ae-122">Esse comando resolve um caminho de convenção de nomenclatura Universal (UNC) e retorna os compartilhamentos no caminho.</span><span class="sxs-lookup"><span data-stu-id="458ae-122">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="458ae-123">Exemplo 5: obter caminhos relativos</span><span class="sxs-lookup"><span data-stu-id="458ae-123">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="458ae-124">Esse comando retorna os caminhos relativos para os diretórios na raiz da unidade C:.</span><span class="sxs-lookup"><span data-stu-id="458ae-124">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="458ae-125">Exemplo 6: resolver um caminho contendo colchetes</span><span class="sxs-lookup"><span data-stu-id="458ae-125">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="458ae-126">Este exemplo usa o parâmetro **LiteralPath** para resolver o caminho da \[ subpasta XML de teste \] .</span><span class="sxs-lookup"><span data-stu-id="458ae-126">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="458ae-127">O uso de **LiteralPath** faz com que os colchetes sejam tratados como caracteres normais em vez de uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="458ae-127">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="458ae-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="458ae-128">PARAMETERS</span></span>

### <span data-ttu-id="458ae-129">-Credential</span><span class="sxs-lookup"><span data-stu-id="458ae-129">-Credential</span></span>

<span data-ttu-id="458ae-130">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="458ae-130">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="458ae-131">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="458ae-131">The default is the current user.</span></span>

<span data-ttu-id="458ae-132">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou passe um objeto **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="458ae-132">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="458ae-133">Você pode criar um objeto **PSCredential** usando o `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="458ae-133">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="458ae-134">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="458ae-134">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="458ae-135">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="458ae-135">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="458ae-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="458ae-136">-LiteralPath</span></span>

<span data-ttu-id="458ae-137">Especifica os caminhos que serão resolvidos.</span><span class="sxs-lookup"><span data-stu-id="458ae-137">Specifies the path to be resolved.</span></span> <span data-ttu-id="458ae-138">O valor do parâmetro **LiteralPath** é usado exatamente como tipado.</span><span class="sxs-lookup"><span data-stu-id="458ae-138">The value of the **LiteralPath** parameter is used exactly as typed.</span></span> <span data-ttu-id="458ae-139">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="458ae-139">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="458ae-140">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="458ae-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="458ae-141">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="458ae-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="458ae-142">-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-142">-Path</span></span>

<span data-ttu-id="458ae-143">Especifica o caminho do PowerShell a ser resolvido.</span><span class="sxs-lookup"><span data-stu-id="458ae-143">Specifies the PowerShell path to resolve.</span></span> <span data-ttu-id="458ae-144">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="458ae-144">This parameter is required.</span></span> <span data-ttu-id="458ae-145">Também é possível canalizar uma cadeia de caracteres de caminho para `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="458ae-145">You can also pipe a path string to `Resolve-Path`.</span></span> <span data-ttu-id="458ae-146">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="458ae-146">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="458ae-147">-Relativo</span><span class="sxs-lookup"><span data-stu-id="458ae-147">-Relative</span></span>

<span data-ttu-id="458ae-148">Indica que esse cmdlet retorna um caminho relativo.</span><span class="sxs-lookup"><span data-stu-id="458ae-148">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="458ae-149">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="458ae-149">-UseTransaction</span></span>
<span data-ttu-id="458ae-150">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="458ae-150">Includes the command in the active transaction.</span></span>
<span data-ttu-id="458ae-151">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="458ae-151">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="458ae-152">Para obter mais informações, consulte about_transactions.</span><span class="sxs-lookup"><span data-stu-id="458ae-152">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="458ae-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="458ae-153">CommonParameters</span></span>

<span data-ttu-id="458ae-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="458ae-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="458ae-155">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="458ae-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="458ae-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="458ae-156">INPUTS</span></span>

### <span data-ttu-id="458ae-157">System.String</span><span class="sxs-lookup"><span data-stu-id="458ae-157">System.String</span></span>

<span data-ttu-id="458ae-158">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="458ae-158">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="458ae-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="458ae-159">OUTPUTS</span></span>

### <span data-ttu-id="458ae-160">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="458ae-160">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="458ae-161">Retorna um objeto **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="458ae-161">Returns a **PathInfo** object.</span></span> <span data-ttu-id="458ae-162">Retorna um valor de cadeia de caracteres para o caminho resolvido se você especificar o parâmetro **relativo** .</span><span class="sxs-lookup"><span data-stu-id="458ae-162">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="458ae-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="458ae-163">NOTES</span></span>

<span data-ttu-id="458ae-164">Os `*-Path` cmdlets funcionam com o sistema de arquivos, o registro e os provedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="458ae-164">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="458ae-165">`Resolve-Path` o foi projetado para funcionar com qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="458ae-165">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="458ae-166">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="458ae-166">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="458ae-167">Para obter mais informações, consulte [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="458ae-167">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="458ae-168">`Resolve-Path` resolve apenas os caminhos existentes.</span><span class="sxs-lookup"><span data-stu-id="458ae-168">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="458ae-169">Ele não pode ser usado para resolver um local que ainda não existe.</span><span class="sxs-lookup"><span data-stu-id="458ae-169">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="458ae-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="458ae-170">RELATED LINKS</span></span>

[<span data-ttu-id="458ae-171">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-171">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="458ae-172">Join-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-172">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="458ae-173">Split-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-173">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="458ae-174">Test-Path</span><span class="sxs-lookup"><span data-stu-id="458ae-174">Test-Path</span></span>](Test-Path.md)
