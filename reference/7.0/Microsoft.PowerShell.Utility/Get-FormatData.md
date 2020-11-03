---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: 22cdfce0ca9e591dfc97a6ac7ef2c1e0f0ed37ab
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193014"
---
# <span data-ttu-id="a81a4-103">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="a81a4-103">Get-FormatData</span></span>

## <span data-ttu-id="a81a4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a81a4-104">SYNOPSIS</span></span>
<span data-ttu-id="a81a4-105">Obtém os dados de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a81a4-105">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="a81a4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a81a4-106">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="a81a4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a81a4-107">DESCRIPTION</span></span>

<span data-ttu-id="a81a4-108">O `Get-FormatData` cmdlet obtém os dados de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a81a4-108">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="a81a4-109">Os dados de formatação na sessão incluem a formatação de dados de `Format.ps1xml` arquivos de formatação, como aqueles no `$PSHOME` diretório, a formatação de dados para os módulos que você importa para a sessão e a formatação de dados para comandos que você importa para sua sessão usando o `Import-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a81a4-109">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="a81a4-110">Você pode usar este cmdlet para examinar os dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="a81a4-110">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="a81a4-111">Em seguida, você pode usar o `Export-FormatData` cmdlet para serializar os objetos, convertê-los em XML e salvá-los em `Format.ps1xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="a81a4-111">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="a81a4-112">Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="a81a4-112">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="a81a4-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a81a4-113">EXAMPLES</span></span>

### <span data-ttu-id="a81a4-114">Exemplo 1: obter todos os dados de formatação</span><span class="sxs-lookup"><span data-stu-id="a81a4-114">Example 1: Get all formatting data</span></span>

<span data-ttu-id="a81a4-115">Este exemplo obtém todos os dados de formatação na sessão.</span><span class="sxs-lookup"><span data-stu-id="a81a4-115">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1
```

> [!IMPORTANT]
> <span data-ttu-id="a81a4-116">Para garantir que as informações de formatação de tipo completas sejam retornadas, você deve sempre incluir o parâmetro **PowerShellVersion** com o valor `5.1` ao usar uma invocação local de `Get-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="a81a4-116">To ensure that the complete type formatting information is returned, you should always include the **PowerShellVersion** parameter with the value `5.1` when using a local invocation of `Get-FormatData`.</span></span> <span data-ttu-id="a81a4-117">Se o parâmetro e o valor forem omitidos, você não poderá obter todas as informações de tipo corretas.</span><span class="sxs-lookup"><span data-stu-id="a81a4-117">If the parameter and value are omitted, you may not get all the correct type information.</span></span>

### <span data-ttu-id="a81a4-118">Exemplo 2: obter dados de formatação por nome de tipo</span><span class="sxs-lookup"><span data-stu-id="a81a4-118">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="a81a4-119">Este exemplo obtém os itens de dados de formatação cujos nomes começam com `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="a81a4-119">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
```

### <span data-ttu-id="a81a4-120">Exemplo 3: examinar um objeto de dados de formatação</span><span class="sxs-lookup"><span data-stu-id="a81a4-120">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="a81a4-121">Este exemplo mostra como obter um objeto de dados de formatação e examinar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="a81a4-121">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### <span data-ttu-id="a81a4-122">Exemplo 4: obter dados de formatação e exportá-los</span><span class="sxs-lookup"><span data-stu-id="a81a4-122">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="a81a4-123">Este exemplo mostra como usar `Get-FormatData` e `Export-FormatData` para exportar os dados de formatação que são adicionados por um módulo.</span><span class="sxs-lookup"><span data-stu-id="a81a4-123">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData -PowerShellVersion 5.1
Import-Module bitstransfer
$B = Get-FormatData -PowerShellVersion 5.1
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

<span data-ttu-id="a81a4-124">Os primeiros quatro comandos usam os `Get-FormatData` `Import-Module` `Compare-Object` cmdlets, e para identificar o tipo de formato que o módulo **BitsTransfer** adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="a81a4-124">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="a81a4-125">O quinto comando usa o `Get-FormatData` cmdlet para obter o tipo de formato que o módulo **BitsTransfer** adiciona.</span><span class="sxs-lookup"><span data-stu-id="a81a4-125">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="a81a4-126">Ele usa um operador de pipeline ( `|` ) para enviar o objeto de tipo de formato para o `Export-FormatData` cmdlet, que o converte de volta em XML e o salva no `format.ps1xml` arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a81a4-126">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="a81a4-127">O comando final mostra um trecho do `format.ps1xml` conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a81a4-127">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="a81a4-128">Exemplo 5: obter dados de formatação com base na versão especificada do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a81a4-128">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="a81a4-129">Este exemplo mostra como usar o `Get-FormatData` para obter dados de formato para uma versão especificada do **TypeName** e do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a81a4-129">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="a81a4-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a81a4-130">PARAMETERS</span></span>

### <span data-ttu-id="a81a4-131">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="a81a4-131">-PowerShellVersion</span></span>

<span data-ttu-id="a81a4-132">Especifique a versão do PowerShell que esse cmdlet obtém para os dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="a81a4-132">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="a81a4-133">Insira um número de dois dígitos separado por um ponto.</span><span class="sxs-lookup"><span data-stu-id="a81a4-133">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="a81a4-134">Esse parâmetro foi adicionado no PowerShell 5,1 para melhorar a compatibilidade quando computadores remotos que executam versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a81a4-134">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a81a4-135">-TypeName</span><span class="sxs-lookup"><span data-stu-id="a81a4-135">-TypeName</span></span>

<span data-ttu-id="a81a4-136">Especifica os nomes de tipo que esse cmdlet obtém para os dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="a81a4-136">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="a81a4-137">Insira os nomes de tipo.</span><span class="sxs-lookup"><span data-stu-id="a81a4-137">Enter the type names.</span></span>
<span data-ttu-id="a81a4-138">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a81a4-138">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a81a4-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a81a4-139">CommonParameters</span></span>

<span data-ttu-id="a81a4-140">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a81a4-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a81a4-141">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a81a4-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a81a4-142">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a81a4-142">INPUTS</span></span>

### <span data-ttu-id="a81a4-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a81a4-143">None</span></span>

<span data-ttu-id="a81a4-144">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a81a4-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a81a4-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a81a4-145">OUTPUTS</span></span>

### <span data-ttu-id="a81a4-146">System. Management. Automation. ExtendedTypeDefinition</span><span class="sxs-lookup"><span data-stu-id="a81a4-146">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="a81a4-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a81a4-147">NOTES</span></span>

## <span data-ttu-id="a81a4-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a81a4-148">RELATED LINKS</span></span>

[<span data-ttu-id="a81a4-149">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="a81a4-149">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="a81a4-150">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="a81a4-150">Update-FormatData</span></span>](Update-FormatData.md)
