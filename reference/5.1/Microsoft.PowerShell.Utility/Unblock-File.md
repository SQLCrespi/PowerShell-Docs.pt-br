---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 57c8c6f2ceda124b3dc89c363c6cf942680781ca
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344500"
---
# <span data-ttu-id="be76e-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="be76e-103">Unblock-File</span></span>

## <span data-ttu-id="be76e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="be76e-104">SYNOPSIS</span></span>
<span data-ttu-id="be76e-105">Desbloqueia os arquivos que foram baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="be76e-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="be76e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="be76e-106">SYNTAX</span></span>

### <span data-ttu-id="be76e-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="be76e-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="be76e-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="be76e-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="be76e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="be76e-109">DESCRIPTION</span></span>

<span data-ttu-id="be76e-110">O `Unblock-File` cmdlet permite abrir arquivos que foram baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="be76e-110">The `Unblock-File` cmdlet lets you open files that were downloaded from the Internet.</span></span> <span data-ttu-id="be76e-111">Ele desbloqueia os arquivos de script do PowerShell que foram baixados da Internet para que você possa executá-los, mesmo quando a política de execução do PowerShell for **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="be76e-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="be76e-112">Por padrão, esses arquivos são bloqueados para proteger o computador contra arquivos não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="be76e-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="be76e-113">Antes de usar o `Unblock-File` cmdlet, examine o arquivo e sua origem e verifique se é seguro abrir.</span><span class="sxs-lookup"><span data-stu-id="be76e-113">Before using the `Unblock-File` cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="be76e-114">Internamente, o `Unblock-File` cmdlet Remove o fluxo de dados alternativo Zone. Identifier, que tem um valor de "3" para indicar que foi baixado da Internet.</span><span class="sxs-lookup"><span data-stu-id="be76e-114">Internally, the `Unblock-File` cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="be76e-115">Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="be76e-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="be76e-116">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="be76e-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="be76e-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="be76e-117">EXAMPLES</span></span>

### <span data-ttu-id="be76e-118">Exemplo 1: desbloquear um arquivo</span><span class="sxs-lookup"><span data-stu-id="be76e-118">Example 1: Unblock a file</span></span>

<span data-ttu-id="be76e-119">Esse comando desbloqueia o arquivo PowerShellTips.chm.</span><span class="sxs-lookup"><span data-stu-id="be76e-119">This command unblocks the PowerShellTips.chm file.</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### <span data-ttu-id="be76e-120">Exemplo 2: desbloquear vários arquivos</span><span class="sxs-lookup"><span data-stu-id="be76e-120">Example 2: Unblock multiple files</span></span>

<span data-ttu-id="be76e-121">Esse comando desbloqueia todos os arquivos no `C:\Downloads` diretório cujos nomes incluem "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="be76e-121">This command unblocks all of the files in the `C:\Downloads` directory whose names include "PowerShell".</span></span> <span data-ttu-id="be76e-122">Não execute um comando como esse até que tenha verificado se todos os arquivos são seguros.</span><span class="sxs-lookup"><span data-stu-id="be76e-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### <span data-ttu-id="be76e-123">Exemplo 3: localizar e desbloquear scripts</span><span class="sxs-lookup"><span data-stu-id="be76e-123">Example 3: Find and unblock scripts</span></span>

<span data-ttu-id="be76e-124">Este comando mostra como localizar e desbloquear scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be76e-124">This command shows how to find and unblock PowerShell scripts.</span></span>

<span data-ttu-id="be76e-125">O primeiro comando usa o parâmetro **Stream** do cmdlet *Get-Item* obter arquivos com o fluxo Zone. identificador.</span><span class="sxs-lookup"><span data-stu-id="be76e-125">The first command uses the **Stream** parameter of the *Get-Item* cmdlet get files with the Zone.Identifier stream.</span></span>

<span data-ttu-id="be76e-126">O segundo comando mostra o que acontece quando você executa um script bloqueado em uma sessão do PowerShell na qual a política de execução é **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="be76e-126">The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="be76e-127">A diretiva RemoteSigned impede a execução de scripts baixados da Internet, a menos que estejam assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="be76e-127">The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.</span></span>

<span data-ttu-id="be76e-128">O terceiro comando usa o `Unblock-File` cmdlet para desbloquear o script para que ele possa ser executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="be76e-128">The third command uses the `Unblock-File` cmdlet to unblock the script so it can run in the session.</span></span>

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## <span data-ttu-id="be76e-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="be76e-129">PARAMETERS</span></span>

### <span data-ttu-id="be76e-130">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="be76e-130">-LiteralPath</span></span>

<span data-ttu-id="be76e-131">Especifica os arquivos que serão desbloqueados.</span><span class="sxs-lookup"><span data-stu-id="be76e-131">Specifies the files to unblock.</span></span> <span data-ttu-id="be76e-132">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="be76e-132">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="be76e-133">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="be76e-133">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="be76e-134">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="be76e-134">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="be76e-135">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="be76e-135">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be76e-136">-Path</span><span class="sxs-lookup"><span data-stu-id="be76e-136">-Path</span></span>

<span data-ttu-id="be76e-137">Especifica os arquivos que serão desbloqueados.</span><span class="sxs-lookup"><span data-stu-id="be76e-137">Specifies the files to unblock.</span></span> <span data-ttu-id="be76e-138">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="be76e-138">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="be76e-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="be76e-139">-Confirm</span></span>

<span data-ttu-id="be76e-140">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="be76e-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="be76e-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="be76e-141">-WhatIf</span></span>

<span data-ttu-id="be76e-142">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="be76e-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="be76e-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="be76e-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="be76e-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="be76e-144">CommonParameters</span></span>

<span data-ttu-id="be76e-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="be76e-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be76e-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="be76e-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="be76e-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="be76e-147">INPUTS</span></span>

### <span data-ttu-id="be76e-148">System.String</span><span class="sxs-lookup"><span data-stu-id="be76e-148">System.String</span></span>

<span data-ttu-id="be76e-149">É possível canalizar um caminho de arquivo para `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="be76e-149">You can pipe a file path to `Unblock-File`.</span></span>

## <span data-ttu-id="be76e-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="be76e-150">OUTPUTS</span></span>

### <span data-ttu-id="be76e-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="be76e-151">None</span></span>

<span data-ttu-id="be76e-152">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="be76e-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="be76e-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="be76e-153">NOTES</span></span>

- <span data-ttu-id="be76e-154">O `Unblock-File` cmdlet funciona apenas em unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="be76e-154">The `Unblock-File` cmdlet works only in file system drives.</span></span>
- <span data-ttu-id="be76e-155">`Unblock-File` executa a mesma operação que o botão **desbloquear** na caixa de diálogo **Propriedades** no explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="be76e-155">`Unblock-File` performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
- <span data-ttu-id="be76e-156">Se você usar o `Unblock-File` cmdlet em um arquivo que não está bloqueado, o comando não terá nenhum efeito sobre o arquivo não bloqueado e o cmdlet não gerará erros.</span><span class="sxs-lookup"><span data-stu-id="be76e-156">If you use the `Unblock-File` cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="be76e-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="be76e-157">RELATED LINKS</span></span>

[<span data-ttu-id="be76e-158">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="be76e-158">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="be76e-159">Get-Item</span><span class="sxs-lookup"><span data-stu-id="be76e-159">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="be76e-160">Out-File</span><span class="sxs-lookup"><span data-stu-id="be76e-160">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="be76e-161">FileSystem Provider</span><span class="sxs-lookup"><span data-stu-id="be76e-161">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
