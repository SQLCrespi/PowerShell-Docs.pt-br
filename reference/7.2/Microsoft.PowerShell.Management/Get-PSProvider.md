---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 20820d2d194f41d43048c9617b63b9acb3fbb4f8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595575"
---
# <span data-ttu-id="48a25-102">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="48a25-102">Get-PSProvider</span></span>

## <span data-ttu-id="48a25-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="48a25-103">SYNOPSIS</span></span>
<span data-ttu-id="48a25-104">Obtém informações sobre o provedor do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="48a25-104">Gets information about the specified PowerShell provider.</span></span>

## <span data-ttu-id="48a25-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48a25-105">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="48a25-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48a25-106">DESCRIPTION</span></span>

<span data-ttu-id="48a25-107">O `Get-PSProvider` cmdlet obtém os provedores do PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="48a25-107">The `Get-PSProvider` cmdlet gets the PowerShell providers in the current session.</span></span>
<span data-ttu-id="48a25-108">Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="48a25-108">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="48a25-109">Os provedores do PowerShell permitem acessar uma variedade de armazenamentos de dados como se fossem unidades do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="48a25-109">PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="48a25-110">Para obter informações sobre provedores do PowerShell, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="48a25-110">For information about PowerShell providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="48a25-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="48a25-111">EXAMPLES</span></span>

### <span data-ttu-id="48a25-112">Exemplo 1: exibir uma lista de todos os provedores disponíveis</span><span class="sxs-lookup"><span data-stu-id="48a25-112">Example 1: Display a list of all available providers</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="48a25-113">Este comando exibe uma lista de todos os provedores do PowerShell disponíveis.</span><span class="sxs-lookup"><span data-stu-id="48a25-113">This command displays a list of all available PowerShell providers.</span></span>

### <span data-ttu-id="48a25-114">Exemplo 2: exibir uma lista de todos os provedores do PowerShell que começam com as letras especificadas</span><span class="sxs-lookup"><span data-stu-id="48a25-114">Example 2: Display a list of all PowerShell providers that begin with specified letters</span></span>

```powershell
Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="48a25-115">Esse comando exibe uma lista de todos os provedores do PowerShell com nomes que começam com a letra f ou r.</span><span class="sxs-lookup"><span data-stu-id="48a25-115">This command displays a list of all PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="48a25-116">Exemplo 3: localizar snap-ins ou um módulo que adicionou provedores à sua sessão</span><span class="sxs-lookup"><span data-stu-id="48a25-116">Example 3: Find snap-ins or module that added providers to your session</span></span>

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
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
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="48a25-117">Esses comandos localizam os snap-ins ou módulos do PowerShell que adicionaram provedores à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="48a25-117">These commands find the PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="48a25-118">Todos os elementos do PowerShell, incluindo provedores, se originam em um snap-in ou em um módulo.</span><span class="sxs-lookup"><span data-stu-id="48a25-118">All PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="48a25-119">Esses comandos usam as propriedades PSSnapin e Module do objeto **providerInfo** que `Get-PSProvider` retorna.</span><span class="sxs-lookup"><span data-stu-id="48a25-119">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that `Get-PSProvider` returns.</span></span>
<span data-ttu-id="48a25-120">Os valores dessas propriedades contêm o nome do snap-in ou módulo que adiciona o provedor.</span><span class="sxs-lookup"><span data-stu-id="48a25-120">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="48a25-121">O primeiro comando obtém todos os provedores existentes na sessão e formata-os em uma tabela com os valores de suas propriedades Name (nome), Module (módulo) e PSSnapin.</span><span class="sxs-lookup"><span data-stu-id="48a25-121">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="48a25-122">O segundo comando usa o `Where-Object` cmdlet para obter os provedores que vêm do snap-in **Microsoft. PowerShell. Security** .</span><span class="sxs-lookup"><span data-stu-id="48a25-122">The second command uses the `Where-Object` cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="48a25-123">Exemplo 4: resolver o caminho da propriedade Home do provedor do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="48a25-123">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

<span data-ttu-id="48a25-124">Este exemplo mostra que o símbolo de til (~) representa o valor da propriedade **Home** do provedor FileSystem.</span><span class="sxs-lookup"><span data-stu-id="48a25-124">This example shows that the tilde symbol (~) represents the value of the **Home** property of the FileSystem provider.</span></span>
<span data-ttu-id="48a25-125">O valor da propriedade **Home** é opcional, mas para o provedor **FileSystem** , ele é definido como `$env:homedrive\$env:homepath` ou `$home` .</span><span class="sxs-lookup"><span data-stu-id="48a25-125">The **Home** property value is optional, but for the **FileSystem** provider, it is defined as `$env:homedrive\$env:homepath` or `$home`.</span></span>

## <span data-ttu-id="48a25-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48a25-126">PARAMETERS</span></span>

### <span data-ttu-id="48a25-127">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="48a25-127">-PSProvider</span></span>

<span data-ttu-id="48a25-128">Especifica o nome ou os nomes dos provedores do PowerShell sobre os quais esse cmdlet obtém informações.</span><span class="sxs-lookup"><span data-stu-id="48a25-128">Specifies the name or names of the PowerShell providers about which this cmdlet gets information.</span></span>

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

### <span data-ttu-id="48a25-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="48a25-129">CommonParameters</span></span>

<span data-ttu-id="48a25-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="48a25-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48a25-131">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="48a25-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="48a25-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="48a25-132">INPUTS</span></span>

### <span data-ttu-id="48a25-133">String[]</span><span class="sxs-lookup"><span data-stu-id="48a25-133">String[]</span></span>

<span data-ttu-id="48a25-134">É possível canalizar uma ou mais cadeias de caracteres de nome de provedor para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48a25-134">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="48a25-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="48a25-135">OUTPUTS</span></span>

### <span data-ttu-id="48a25-136">System. Management. Automation. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="48a25-136">System.Management.Automation.ProviderInfo</span></span>

<span data-ttu-id="48a25-137">Esse cmdlet retorna objetos que representam os provedores do PowerShell na sessão.</span><span class="sxs-lookup"><span data-stu-id="48a25-137">This cmdlet returns objects that represent the PowerShell providers in the session.</span></span>

## <span data-ttu-id="48a25-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="48a25-138">NOTES</span></span>

## <span data-ttu-id="48a25-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="48a25-139">RELATED LINKS</span></span>

