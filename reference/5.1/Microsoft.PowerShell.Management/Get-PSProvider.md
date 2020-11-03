---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194166"
---
# <span data-ttu-id="f3949-103">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f3949-103">Get-PSProvider</span></span>

## <span data-ttu-id="f3949-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f3949-104">SYNOPSIS</span></span>
<span data-ttu-id="f3949-105">Obtém informações sobre o provedor do Windows PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="f3949-105">Gets information about the specified Windows PowerShell provider.</span></span>

## <span data-ttu-id="f3949-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f3949-106">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f3949-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f3949-107">DESCRIPTION</span></span>
<span data-ttu-id="f3949-108">O cmdlet **Get-PSProvider** Obtém os provedores do Windows PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f3949-108">The **Get-PSProvider** cmdlet gets the Windows PowerShell providers in the current session.</span></span>
<span data-ttu-id="f3949-109">Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="f3949-109">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="f3949-110">Os provedores do Windows PowerShell permitem que você acesse uma variedade de fontes de dados, como se fossem unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f3949-110">Windows PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="f3949-111">Para obter informações sobre os provedores do Windows PowerShell, consulte about_Providers.</span><span class="sxs-lookup"><span data-stu-id="f3949-111">For information about Windows PowerShell providers, see about_Providers.</span></span>

## <span data-ttu-id="f3949-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f3949-112">EXAMPLES</span></span>

### <span data-ttu-id="f3949-113">Exemplo 1: exibir uma lista de todos os provedores disponíveis</span><span class="sxs-lookup"><span data-stu-id="f3949-113">Example 1: Display a list of all available providers</span></span>

```
PS C:\> Get-PSProvider
```

<span data-ttu-id="f3949-114">Este comando exibe uma lista de todos os provedores disponíveis do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3949-114">This command displays a list of all available Windows PowerShell providers.</span></span>

### <span data-ttu-id="f3949-115">Exemplo 2: exibir uma lista de todos os provedores do Windows PowerShell que começam com as letras especificadas</span><span class="sxs-lookup"><span data-stu-id="f3949-115">Example 2: Display a list of all Windows PowerShell providers that begin with specified letters</span></span>

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="f3949-116">Esse comando exibe uma lista de todos os provedores do Windows PowerShell com nomes que começam com a letra f ou r.</span><span class="sxs-lookup"><span data-stu-id="f3949-116">This command displays a list of all Windows PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="f3949-117">Exemplo 3: localizar snap-ins ou um módulo que adicionou provedores à sua sessão</span><span class="sxs-lookup"><span data-stu-id="f3949-117">Example 3: Find snap-ins or module that added providers to your session</span></span>

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="f3949-118">Estes comandos encontram os módulos ou snap-ins do Windows PowerShell que adicionaram provedores à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="f3949-118">These commands find the Windows PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="f3949-119">Todos os elementos do Windows PowerShell, incluindo provedores, são originadas em um snap-in ou em um módulo.</span><span class="sxs-lookup"><span data-stu-id="f3949-119">All Windows PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="f3949-120">Esses comandos usam as propriedades PSSnapin e Module do objeto **providerInfo** que o **Get-PSProvider** retorna.</span><span class="sxs-lookup"><span data-stu-id="f3949-120">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that **Get-PSProvider** returns.</span></span>
<span data-ttu-id="f3949-121">Os valores dessas propriedades contêm o nome do snap-in ou módulo que adiciona o provedor.</span><span class="sxs-lookup"><span data-stu-id="f3949-121">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="f3949-122">O primeiro comando obtém todos os provedores existentes na sessão e formata-os em uma tabela com os valores de suas propriedades Name (nome), Module (módulo) e PSSnapin.</span><span class="sxs-lookup"><span data-stu-id="f3949-122">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="f3949-123">O segundo comando usa o cmdlet Where-Object para obter os provedores que vêm do snap-in **Microsoft. PowerShell. Security** .</span><span class="sxs-lookup"><span data-stu-id="f3949-123">The second command uses the Where-Object cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="f3949-124">Exemplo 4: resolver o caminho da propriedade Home do provedor do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="f3949-124">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

<span data-ttu-id="f3949-125">Este exemplo mostra que o símbolo de til (~) representa o valor da propriedade Home (início) do provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="f3949-125">This example shows that the tilde symbol (~) represents the value of the Home property of the FileSystem provider.</span></span>
<span data-ttu-id="f3949-126">O valor da propriedade Home é opcional, mas para o provedor FileSystem, ele é definido como $env: HomeDrive \$ env: homepath ou $Home.</span><span class="sxs-lookup"><span data-stu-id="f3949-126">The Home property value is optional, but for the FileSystem provider, it is defined as $env:homedrive\$env:homepath or $home.</span></span>

## <span data-ttu-id="f3949-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f3949-127">PARAMETERS</span></span>

### <span data-ttu-id="f3949-128">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f3949-128">-PSProvider</span></span>
<span data-ttu-id="f3949-129">Especifica o nome ou os nomes dos provedores do Windows PowerShell sobre os quais esse cmdlet obtém informações.</span><span class="sxs-lookup"><span data-stu-id="f3949-129">Specifies the name or names of the Windows PowerShell providers about which this cmdlet gets information.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f3949-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f3949-130">CommonParameters</span></span>
<span data-ttu-id="f3949-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f3949-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f3949-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f3949-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f3949-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f3949-133">INPUTS</span></span>

### <span data-ttu-id="f3949-134">String[]</span><span class="sxs-lookup"><span data-stu-id="f3949-134">String[]</span></span>

<span data-ttu-id="f3949-135">É possível canalizar uma ou mais cadeias de caracteres de nome de provedor para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3949-135">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="f3949-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f3949-136">OUTPUTS</span></span>

### <span data-ttu-id="f3949-137">System. Management. Automation. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="f3949-137">System.Management.Automation.ProviderInfo</span></span>
<span data-ttu-id="f3949-138">Esse cmdlet retorna objetos que representam os provedores do Windows PowerShell na sessão.</span><span class="sxs-lookup"><span data-stu-id="f3949-138">This cmdlet returns objects that represent the Windows PowerShell providers in the session.</span></span>

## <span data-ttu-id="f3949-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f3949-139">NOTES</span></span>

## <span data-ttu-id="f3949-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f3949-140">RELATED LINKS</span></span>

## <span data-ttu-id="f3949-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f3949-141">RELATED LINKS</span></span>
