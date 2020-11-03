---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193331"
---
# <span data-ttu-id="8511d-103">Export-Console</span><span class="sxs-lookup"><span data-stu-id="8511d-103">Export-Console</span></span>

## <span data-ttu-id="8511d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8511d-104">SYNOPSIS</span></span>
<span data-ttu-id="8511d-105">Exporta os nomes de snap-ins presentes na sessão atual para um arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="8511d-105">Exports the names of snap-ins in the current session to a console file.</span></span>

## <span data-ttu-id="8511d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8511d-106">SYNTAX</span></span>

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8511d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8511d-107">DESCRIPTION</span></span>
<span data-ttu-id="8511d-108">O cmdlet **Export-Console** exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para um arquivo de console do Windows PowerShell (. psc1).</span><span class="sxs-lookup"><span data-stu-id="8511d-108">The **Export-Console** cmdlet exports the names of the Windows PowerShell snap-ins in the current session to a Windows PowerShell console file (.psc1).</span></span>
<span data-ttu-id="8511d-109">Você pode usar este cmdlet para salvar os snap-ins para uso em futuras sessões.</span><span class="sxs-lookup"><span data-stu-id="8511d-109">You can use this cmdlet to save the snap-ins for use in future sessions.</span></span>

<span data-ttu-id="8511d-110">Para adicionar os snap-ins no arquivo de console. psc1 a uma sessão, inicie o Windows PowerShell (Powershell.exe) na linha de comando usando Cmd.exe ou outra sessão do Windows PowerShell e, em seguida, use o parâmetro *PSConsoleFile* de Powershell.exe para especificar o arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="8511d-110">To add the snap-ins in the .psc1 console file to a session, start Windows PowerShell (Powershell.exe) at the command line by using Cmd.exe or another Windows PowerShell session, and then use the *PSConsoleFile* parameter of Powershell.exe to specify the console file.</span></span>

<span data-ttu-id="8511d-111">Para obter mais informações sobre os snap-ins do Windows PowerShell, consulte about_PSSnapins.</span><span class="sxs-lookup"><span data-stu-id="8511d-111">For more information about Windows PowerShell snap-ins, see about_PSSnapins.</span></span>

## <span data-ttu-id="8511d-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8511d-112">EXAMPLES</span></span>

### <span data-ttu-id="8511d-113">Exemplo 1: exportar os nomes dos snap-ins na sessão atual</span><span class="sxs-lookup"><span data-stu-id="8511d-113">Example 1: Export the names of snap-ins in the current session</span></span>

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

<span data-ttu-id="8511d-114">Esse comando exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para o arquivo ConsoleS1. psc1 na pasta consoles da pasta de instalação do Windows PowerShell, $pshome.</span><span class="sxs-lookup"><span data-stu-id="8511d-114">This command exports the names of Windows PowerShell snap-ins in the current session to the ConsoleS1.psc1 file in the Consoles folder of the Windows PowerShell installation folder, $pshome.</span></span>

### <span data-ttu-id="8511d-115">Exemplo 2: exportar os nomes de snap-ins para o arquivo de console mais recente</span><span class="sxs-lookup"><span data-stu-id="8511d-115">Example 2: Export the names of snap-ins to the most recent console file</span></span>

```
PS C:\> Export-Console
```

<span data-ttu-id="8511d-116">Esse comando exporta os nomes dos snap-ins do Windows PowerShell da sessão atual para o arquivo de console do Windows PowerShell que foi usado mais recentemente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-116">This command exports the names of Windows PowerShell snap-ins from current session to the Windows PowerShell console file that was most recently used in the current session.</span></span>
<span data-ttu-id="8511d-117">Ele substitui o conteúdo do arquivo anterior.</span><span class="sxs-lookup"><span data-stu-id="8511d-117">It overwrites the previous file contents.</span></span>

<span data-ttu-id="8511d-118">Se não exportar um arquivo de console durante a sessão atual, será solicitado que você tenha permissão para continuar e, em seguida, o nome de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8511d-118">If you have not exported a console file during the current session, you are prompted for permission to continue and then prompted for a file name.</span></span>

### <span data-ttu-id="8511d-119">Exemplo 3: adicionar um snap-in e exportar os nomes dos snap-ins</span><span class="sxs-lookup"><span data-stu-id="8511d-119">Example 3: Add a snap-in and export the names of snap-ins</span></span>

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

<span data-ttu-id="8511d-120">Esses comandos adicionam o snap-in NewPSSnapin Windows PowerShell à sessão atual, exportam os nomes dos snap-ins do Windows PowerShell na sessão atual para um arquivo de console e, em seguida, iniciam uma sessão do Windows PowerShell com o arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="8511d-120">These commands add the NewPSSnapin Windows PowerShell snap-in to the current session, export the names of Windows PowerShell snap-ins in the current session to a console file, and then start a Windows PowerShell session with the console file.</span></span>

<span data-ttu-id="8511d-121">O primeiro comando usa o cmdlet **Add-PSSnapin** para adicionar o snap-in NewPSSnapin à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-121">The first command uses the **Add-PSSnapin** cmdlet to add the NewPSSnapin snap-in to the current session.</span></span>
<span data-ttu-id="8511d-122">Você só pode adicionar snap-ins do Windows PowerShell registrados no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="8511d-122">You can only add Windows PowerShell snap-ins that are registered on your system.</span></span>

<span data-ttu-id="8511d-123">O segundo comando exporta os nomes de snap-in do Windows PowerShell para o arquivo NewPSSnapinConsole.psc1.</span><span class="sxs-lookup"><span data-stu-id="8511d-123">The second command exports the Windows PowerShell snap-in names to the NewPSSnapinConsole.psc1 file.</span></span>

<span data-ttu-id="8511d-124">O terceiro comando inicia o Windows PowerShell com o arquivo NewPSSnapinConsole.psc1.</span><span class="sxs-lookup"><span data-stu-id="8511d-124">The third command starts Windows PowerShell with the NewPSSnapinConsole.psc1 file.</span></span>
<span data-ttu-id="8511d-125">Como o arquivo de console inclui o nome do snap-in do Windows PowerShell, os cmdlets e provedores do snap-in estão disponíveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-125">Because the console file includes the Windows PowerShell snap-in name, the cmdlets and providers in the snap-in are available in the current session.</span></span>

### <span data-ttu-id="8511d-126">Exemplo 4: exportar nomes de snap-ins para um local especificado</span><span class="sxs-lookup"><span data-stu-id="8511d-126">Example 4: Export names of snap-ins to a specified location</span></span>

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

<span data-ttu-id="8511d-127">Esse comando exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para o arquivo Console01.psc1 do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-127">This command exports the names of the Windows PowerShell snap-ins in the current session to the Console01.psc1 file in the current directory.</span></span>

<span data-ttu-id="8511d-128">O segundo comando exibe o conteúdo do arquivo Console01.psc1 no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="8511d-128">The second command displays the contents of the Console01.psc1 file in Notepad.</span></span>

### <span data-ttu-id="8511d-129">Exemplo 5: determinar o arquivo de console a ser atualizado</span><span class="sxs-lookup"><span data-stu-id="8511d-129">Example 5: Determine the console file to update</span></span>

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

<span data-ttu-id="8511d-130">Este exemplo mostra como usar a variável automática $ConsoleFileName para determinar o arquivo de console que será atualizado se você usar o **Export-Console** sem um valor de parâmetro de *caminho* .</span><span class="sxs-lookup"><span data-stu-id="8511d-130">This example shows how to use the $ConsoleFileName automatic variable to determine the console file that will be updated if you use **Export-Console** without a *Path* parameter value.</span></span>

<span data-ttu-id="8511d-131">O primeiro comando usa o parâmetro *PSConsoleFile* de PowerShell.exe para abrir o Windows PowerShell com o arquivo arquivo Console01. psc1.</span><span class="sxs-lookup"><span data-stu-id="8511d-131">The first command uses the *PSConsoleFile* parameter of PowerShell.exe to open Windows PowerShell with the Console01.psc1 file.</span></span>

<span data-ttu-id="8511d-132">O segundo comando usa o cmdlet **Add-PSSnapin** para adicionar o snap-in MySnapin do Windows PowerShell à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-132">The second command uses the **Add-PSSnapin** cmdlet to add the MySnapin Windows PowerShell snap-in to the current session.</span></span>

<span data-ttu-id="8511d-133">O terceiro comando usa o cmdlet **Export-Console** para exportar os nomes de todos os snap-ins do Windows PowerShell na sessão para o arquivo NewConsole. psc1.</span><span class="sxs-lookup"><span data-stu-id="8511d-133">The third command uses the **Export-Console** cmdlet to export the names of all the Windows PowerShell snap-ins in the session to the NewConsole.psc1 file.</span></span>

<span data-ttu-id="8511d-134">O quarto comando exibe a variável $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="8511d-134">The fourth command displays the $ConsoleFileName variable.</span></span>
<span data-ttu-id="8511d-135">Ele contém o arquivo de console usado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="8511d-135">It contains the most recently used console file.</span></span>
<span data-ttu-id="8511d-136">A amostra de saída mostra que o NewConsole.ps1 é o arquivo usado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="8511d-136">The sample output shows that NewConsole.ps1 is the most recently used file.</span></span>

<span data-ttu-id="8511d-137">O quinto comando adiciona SnapIn03 no console atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-137">The fifth command adds SnapIn03 to the current console.</span></span>

<span data-ttu-id="8511d-138">O sexto comando usa o cmdlet **Export-Console** sem um parâmetro *Path* .</span><span class="sxs-lookup"><span data-stu-id="8511d-138">The sixth command uses the **Export-Console** cmdlet without a *Path* parameter.</span></span>
<span data-ttu-id="8511d-139">Esse comando exporta os nomes de todos os snap-ins Windows PowerShell da sessão atual para o arquivo usado mais recentemente, NewConsole.psc1.</span><span class="sxs-lookup"><span data-stu-id="8511d-139">This command exports the names of all the Windows PowerShell snap-ins in the current session to the most recently used file, NewConsole.psc1.</span></span>

## <span data-ttu-id="8511d-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8511d-140">PARAMETERS</span></span>

### <span data-ttu-id="8511d-141">-Force</span><span class="sxs-lookup"><span data-stu-id="8511d-141">-Force</span></span>
<span data-ttu-id="8511d-142">Indica que esse cmdlet substitui os dados em um arquivo de console sem aviso, mesmo que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8511d-142">Indicates that this cmdlet overwrites the data in a console file without warning, even if the file has the read-only attribute.</span></span>
<span data-ttu-id="8511d-143">O atributo somente leitura é alterado e não é redefinido quando o comando é concluído.</span><span class="sxs-lookup"><span data-stu-id="8511d-143">The read-only attribute is changed and is not reset when the command finishes.</span></span>

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

### <span data-ttu-id="8511d-144">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="8511d-144">-NoClobber</span></span>
<span data-ttu-id="8511d-145">Indica que esse cmdlet não substitui um arquivo de console existente.</span><span class="sxs-lookup"><span data-stu-id="8511d-145">Indicates that this cmdlet does not overwrite  an existing console file.</span></span>
<span data-ttu-id="8511d-146">Por padrão, se um arquivo ocorrer no caminho especificado, o **Export-Console** substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="8511d-146">By default, if a file occurs in the specified path, **Export-Console** overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8511d-147">-Path</span><span class="sxs-lookup"><span data-stu-id="8511d-147">-Path</span></span>
<span data-ttu-id="8511d-148">Especifica um nome de arquivo e de caminho para o arquivo de console (\*.psc1).</span><span class="sxs-lookup"><span data-stu-id="8511d-148">Specifies a path and file name for the console file (\*.psc1).</span></span>
<span data-ttu-id="8511d-149">Insira um caminho e um nome opcionais.</span><span class="sxs-lookup"><span data-stu-id="8511d-149">Enter an optional path and name.</span></span>
<span data-ttu-id="8511d-150">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8511d-150">Wildcard characters are not permitted.</span></span>

<span data-ttu-id="8511d-151">Se você especificar apenas um nome de arquivo, o **Export-Console** criará um arquivo com esse nome e a extensão de nome de arquivo. psc1 no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-151">If you specify only a file name, **Export-Console** creates a file that has that name and the .psc1 file name extension in the current directory.</span></span>

<span data-ttu-id="8511d-152">Esse parâmetro é necessário, a menos que você tenha aberto o Windows PowerShell com o parâmetro *PSConsoleFile* ou exportou um arquivo de console durante a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8511d-152">This parameter is required unless you have opened Windows PowerShell with the *PSConsoleFile* parameter or exported a console file during the current session.</span></span>
<span data-ttu-id="8511d-153">Ele também é necessário quando você usa o parâmetro *NoClobber* para impedir que o arquivo de console atual seja substituído.</span><span class="sxs-lookup"><span data-stu-id="8511d-153">It is also required when you use the *NoClobber* parameter to prevent the current console file from being overwritten.</span></span>

<span data-ttu-id="8511d-154">Se você omitir esse parâmetro, o **Export-Console** substituirá o arquivo de console que foi usado mais recentemente nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="8511d-154">If you omit this parameter, **Export-Console** overwrites the console file that was used most recently in this session.</span></span>
<span data-ttu-id="8511d-155">O caminho do arquivo de console usado mais recentemente é armazenado no valor da variável automática $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="8511d-155">The path of the most recently used console file is stored in the value of the $ConsoleFileName automatic variable.</span></span>
<span data-ttu-id="8511d-156">Para obter mais informações, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="8511d-156">For more information, see about_Automatic_Variables.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8511d-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8511d-157">-Confirm</span></span>
<span data-ttu-id="8511d-158">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8511d-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8511d-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8511d-159">-WhatIf</span></span>
<span data-ttu-id="8511d-160">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8511d-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8511d-161">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8511d-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8511d-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8511d-162">CommonParameters</span></span>
<span data-ttu-id="8511d-163">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8511d-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8511d-164">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8511d-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8511d-165">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8511d-165">INPUTS</span></span>

### <span data-ttu-id="8511d-166">System.String</span><span class="sxs-lookup"><span data-stu-id="8511d-166">System.String</span></span>
<span data-ttu-id="8511d-167">É possível canalizar uma cadeia de caracteres de caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8511d-167">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="8511d-168">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8511d-168">OUTPUTS</span></span>

### <span data-ttu-id="8511d-169">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="8511d-169">System.IO.FileInfo</span></span>
<span data-ttu-id="8511d-170">Esse cmdlet cria um arquivo que contém os aliases exportados.</span><span class="sxs-lookup"><span data-stu-id="8511d-170">This cmdlet creates a file that contains the exported aliases.</span></span>

## <span data-ttu-id="8511d-171">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8511d-171">NOTES</span></span>

* <span data-ttu-id="8511d-172">Quando um arquivo de console (.psc1) é usado para iniciar a sessão, o nome do arquivo de console é armazenado automaticamente na variável automática $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="8511d-172">When a console file (.psc1) is used to start the session, the name of the console file is automatically stored in the $ConsoleFileName automatic variable.</span></span> <span data-ttu-id="8511d-173">O valor de $ConsoleFileName é atualizado quando você usa o parâmetro *Path* de **Export-Console** para especificar um novo arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="8511d-173">The value of $ConsoleFileName is updated when you use the *Path* parameter of **Export-Console** to specify a new console file.</span></span> <span data-ttu-id="8511d-174">Quando nenhum arquivo de console é usado, $ConsoleFileName não tem valor ($Null).</span><span class="sxs-lookup"><span data-stu-id="8511d-174">When no console file is used, $ConsoleFileName has no value ($Null).</span></span>

  <span data-ttu-id="8511d-175">Para usar um arquivo de console do Windows PowerShell em uma nova sessão, use a sintaxe a seguir para iniciar o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8511d-175">To use a Windows PowerShell console file in a new session, use the following syntax to start Windows PowerShell:</span></span>

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  <span data-ttu-id="8511d-176">Você também pode salvar os snap-ins do Windows PowerShell para futuras sessões, adicionando um comando Add-PSSnapin para seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8511d-176">You can also save Windows PowerShell snap-ins for future sessions by adding an Add-PSSnapin command to your Windows PowerShell profile.</span></span>
<span data-ttu-id="8511d-177">Para obter mais informações, consulte about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="8511d-177">For more information, see about_Profiles.</span></span>


## <span data-ttu-id="8511d-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8511d-178">RELATED LINKS</span></span>

[<span data-ttu-id="8511d-179">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="8511d-179">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="8511d-180">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="8511d-180">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="8511d-181">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="8511d-181">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
