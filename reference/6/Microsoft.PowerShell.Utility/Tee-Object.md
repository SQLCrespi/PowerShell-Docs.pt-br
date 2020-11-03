---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 1f892ece313ddc0074afbeaf3f3243c0bb9f31d0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194369"
---
# <span data-ttu-id="4bd54-103">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-103">Tee-Object</span></span>

## <span data-ttu-id="4bd54-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4bd54-104">SYNOPSIS</span></span>
<span data-ttu-id="4bd54-105">Salva a saída do comando em um arquivo ou variável e a envia pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="4bd54-105">Saves command output in a file or variable and also sends it down the pipeline.</span></span>

## <span data-ttu-id="4bd54-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4bd54-106">SYNTAX</span></span>

### <span data-ttu-id="4bd54-107">Arquivo (padrão)</span><span class="sxs-lookup"><span data-stu-id="4bd54-107">File (Default)</span></span>

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### <span data-ttu-id="4bd54-108">Valor literal</span><span class="sxs-lookup"><span data-stu-id="4bd54-108">LiteralFile</span></span>

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### <span data-ttu-id="4bd54-109">Variável</span><span class="sxs-lookup"><span data-stu-id="4bd54-109">Variable</span></span>

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## <span data-ttu-id="4bd54-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4bd54-110">DESCRIPTION</span></span>

<span data-ttu-id="4bd54-111">O `Tee-Object` cmdlet redireciona a saída, ou seja, envia a saída de um comando em duas direções (como a letra T).</span><span class="sxs-lookup"><span data-stu-id="4bd54-111">The `Tee-Object` cmdlet redirects output, that is, it sends the output of a command in two directions (like the letter T).</span></span> <span data-ttu-id="4bd54-112">Ele armazena a saída em um arquivo ou variável e também a envia pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="4bd54-112">It stores the output in a file or variable and also sends it down the pipeline.</span></span> <span data-ttu-id="4bd54-113">Se `Tee-Object` for o último comando no pipeline, a saída do comando será exibida no prompt.</span><span class="sxs-lookup"><span data-stu-id="4bd54-113">If `Tee-Object` is the last command in the pipeline, the command output is displayed at the prompt.</span></span>

## <span data-ttu-id="4bd54-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4bd54-114">EXAMPLES</span></span>

### <span data-ttu-id="4bd54-115">Exemplo 1: processos de saída para um arquivo e para o console</span><span class="sxs-lookup"><span data-stu-id="4bd54-115">Example 1: Output processes to a file and to the console</span></span>

<span data-ttu-id="4bd54-116">Este exemplo obtém uma lista dos processos em execução no computador e envia o resultado para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="4bd54-116">This example gets a list of the processes running on the computer and sends the result to a file.</span></span>
<span data-ttu-id="4bd54-117">Como um segundo caminho não foi especificado, os processos também são exibidos no console.</span><span class="sxs-lookup"><span data-stu-id="4bd54-117">Because a second path is not specified, the processes are also displayed in the console.</span></span>

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### <span data-ttu-id="4bd54-118">Exemplo 2: processos de saída para uma variável e `Select-Object`</span><span class="sxs-lookup"><span data-stu-id="4bd54-118">Example 2: Output processes to a variable and `Select-Object`</span></span>

<span data-ttu-id="4bd54-119">Este exemplo obtém uma lista dos processos em execução no computador, salva-os na `$proc` variável e os canaliza para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="4bd54-119">This example gets a list of the processes running on the computer, saves them to the `$proc` variable, and pipes them to `Select-Object`.</span></span>

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

<span data-ttu-id="4bd54-120">O `Select-Object` cmdlet seleciona o **ProcessName** e **manipula** as propriedades.</span><span class="sxs-lookup"><span data-stu-id="4bd54-120">The `Select-Object` cmdlet selects the **ProcessName** and **Handles** properties.</span></span> <span data-ttu-id="4bd54-121">Observe que a `$proc` variável inclui as informações padrão retornadas por `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="4bd54-121">Note that the `$proc` variable includes the default information returned by `Get-Process`.</span></span>

### <span data-ttu-id="4bd54-122">Exemplo 3: arquivos do sistema de saída para dois arquivos de log</span><span class="sxs-lookup"><span data-stu-id="4bd54-122">Example 3: Output system files to two log files</span></span>

<span data-ttu-id="4bd54-123">Este exemplo salva uma lista de arquivos do sistema em dois arquivos de log, um arquivo cumulativo e um arquivo atual.</span><span class="sxs-lookup"><span data-stu-id="4bd54-123">This example saves a list of system files in a two log files, a cumulative file and a current file.</span></span>

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

<span data-ttu-id="4bd54-124">O comando usa o `Get-ChildItem` cmdlet para fazer uma pesquisa recursiva de arquivos do sistema na unidade D:.</span><span class="sxs-lookup"><span data-stu-id="4bd54-124">The command uses the `Get-ChildItem` cmdlet to do a recursive search for system files on the D: drive.</span></span> <span data-ttu-id="4bd54-125">Um operador de pipeline (|) envia a lista para `Tee-Object` , que acrescenta a lista ao arquivo de AllSystemFiles.txt e passa a lista para baixo do pipeline para o `Out-File` cmdlet, que salva a lista no arquivo de NewSystemFiles.txt.</span><span class="sxs-lookup"><span data-stu-id="4bd54-125">A pipeline operator (|) sends the list to `Tee-Object`, which appends the list to the AllSystemFiles.txt file and passes the list down the pipeline to the `Out-File` cmdlet, which saves the list in the NewSystemFiles.txt file.</span></span>

## <span data-ttu-id="4bd54-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4bd54-126">PARAMETERS</span></span>

### <span data-ttu-id="4bd54-127">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="4bd54-127">-Append</span></span>

<span data-ttu-id="4bd54-128">Indica que o cmdlet acrescenta a saída ao arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="4bd54-128">Indicates that the cmdlet appends the output to the specified file.</span></span> <span data-ttu-id="4bd54-129">Sem esse parâmetro, o novo conteúdo substitui todo o conteúdo existente no arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="4bd54-129">Without this parameter, the new content replaces any existing content in the file without warning.</span></span>

<span data-ttu-id="4bd54-130">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="4bd54-130">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4bd54-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="4bd54-131">-FilePath</span></span>

<span data-ttu-id="4bd54-132">Especifica um arquivo no qual esse cmdlet salva o objeto para caracteres curinga é permitido, mas deve ser resolvido para um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="4bd54-132">Specifies a file that this cmdlet saves the object to Wildcard characters are permitted, but must resolve to a single file.</span></span>

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4bd54-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4bd54-133">-InputObject</span></span>

<span data-ttu-id="4bd54-134">Especifica o objeto a ser salvo e exibido.</span><span class="sxs-lookup"><span data-stu-id="4bd54-134">Specifies the object to be saved and displayed.</span></span> <span data-ttu-id="4bd54-135">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="4bd54-135">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="4bd54-136">Também é possível canalizar um objeto para `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="4bd54-136">You can also pipe an object to `Tee-Object`.</span></span>

<span data-ttu-id="4bd54-137">Quando você usa o parâmetro **InputObject** com `Tee-Object` , em vez de direcionar os resultados do comando para `Tee-Object` , o valor **InputObject** é tratado como um único objeto, mesmo se o valor for uma coleção.</span><span class="sxs-lookup"><span data-stu-id="4bd54-137">When you use the **InputObject** parameter with `Tee-Object`, instead of piping command results to `Tee-Object`, the **InputObject** value is treated as a single object even if the value is a collection.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4bd54-138">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4bd54-138">-LiteralPath</span></span>

<span data-ttu-id="4bd54-139">Especifica um arquivo para o qual esse cmdlet salva o objeto.</span><span class="sxs-lookup"><span data-stu-id="4bd54-139">Specifies a file that this cmdlet saves the object to.</span></span> <span data-ttu-id="4bd54-140">Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="4bd54-140">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="4bd54-141">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="4bd54-141">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4bd54-142">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="4bd54-142">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4bd54-143">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="4bd54-143">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4bd54-144">-Variable</span><span class="sxs-lookup"><span data-stu-id="4bd54-144">-Variable</span></span>

<span data-ttu-id="4bd54-145">Especifica uma variável para a qual o cmdlet salva o objeto.</span><span class="sxs-lookup"><span data-stu-id="4bd54-145">Specifies a variable that the cmdlet saves the object to.</span></span> <span data-ttu-id="4bd54-146">Insira um nome de variável sem o sinal de dólar anterior ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="4bd54-146">Enter a variable name without the preceding dollar sign (`$`).</span></span>

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4bd54-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4bd54-147">CommonParameters</span></span>

<span data-ttu-id="4bd54-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4bd54-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4bd54-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4bd54-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4bd54-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4bd54-150">INPUTS</span></span>

### <span data-ttu-id="4bd54-151">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="4bd54-151">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4bd54-152">Você pode canalizar objetos para `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="4bd54-152">You can pipe objects to `Tee-Object`.</span></span>

## <span data-ttu-id="4bd54-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4bd54-153">OUTPUTS</span></span>

### <span data-ttu-id="4bd54-154">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="4bd54-154">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4bd54-155">`Tee-Object` Retorna o objeto que é redirecionado.</span><span class="sxs-lookup"><span data-stu-id="4bd54-155">`Tee-Object` returns the object that it redirects.</span></span>

## <span data-ttu-id="4bd54-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4bd54-156">NOTES</span></span>

<span data-ttu-id="4bd54-157">Você também pode usar o `Out-File` cmdlet ou o operador de redirecionamento, ambos salvando a saída em um arquivo, mas não o enviam pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="4bd54-157">You can also use the `Out-File` cmdlet or the redirection operator, both of which save the output in a file but do not send it down the pipeline.</span></span>

<span data-ttu-id="4bd54-158">A partir do PowerShell 6, o `Tee-Object` usa a codificação UTF-8 sem bom quando grava em arquivos.</span><span class="sxs-lookup"><span data-stu-id="4bd54-158">Beginning in PowerShell 6, `Tee-Object` uses BOM-less UTF-8 encoding when it writes to files.</span></span> <span data-ttu-id="4bd54-159">Se você precisar de uma codificação diferente, use o `Out-File` cmdlet com o parâmetro **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="4bd54-159">If you need a different encoding, use the `Out-File` cmdlet with the **Encoding** parameter.</span></span>

## <span data-ttu-id="4bd54-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4bd54-160">RELATED LINKS</span></span>

[<span data-ttu-id="4bd54-161">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-161">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="4bd54-162">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-162">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="4bd54-163">Group-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-163">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="4bd54-164">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-164">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="4bd54-165">New-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-165">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="4bd54-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-166">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="4bd54-167">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-167">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="4bd54-168">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4bd54-168">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="4bd54-169">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="4bd54-169">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)
