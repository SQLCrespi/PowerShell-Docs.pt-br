---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: c29115a65b46d38039d78b10eee293e6944cede5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193592"
---
# <span data-ttu-id="ae0d8-103">Get-Error</span><span class="sxs-lookup"><span data-stu-id="ae0d8-103">Get-Error</span></span>

## <span data-ttu-id="ae0d8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ae0d8-104">SYNOPSIS</span></span>

<span data-ttu-id="ae0d8-105">Obtém e exibe as mensagens de erro mais recentes da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-105">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="ae0d8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae0d8-106">SYNTAX</span></span>

### <span data-ttu-id="ae0d8-107">Mais recente (padrão)</span><span class="sxs-lookup"><span data-stu-id="ae0d8-107">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ae0d8-108">Erro</span><span class="sxs-lookup"><span data-stu-id="ae0d8-108">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="ae0d8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae0d8-109">DESCRIPTION</span></span>

<span data-ttu-id="ae0d8-110">O `Get-Error` cmdlet obtém um objeto **PSExtendedError** que representa os detalhes do erro atual do último erro que ocorreu na sessão.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-110">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="ae0d8-111">Você pode usar `Get-Error` para exibir um número especificado de erros que ocorreram na sessão atual usando o parâmetro **mais recente** .</span><span class="sxs-lookup"><span data-stu-id="ae0d8-111">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="ae0d8-112">O `Get-Error` cmdlet também recebe objetos de erro de uma coleção, como `$Error` , para exibir vários erros da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-112">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="ae0d8-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ae0d8-113">EXAMPLES</span></span>

### <span data-ttu-id="ae0d8-114">Exemplo 1: obter os detalhes de erro mais recentes</span><span class="sxs-lookup"><span data-stu-id="ae0d8-114">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="ae0d8-115">Neste exemplo, `Get-Error` exibe os detalhes do erro mais recente que ocorreu na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-115">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### <span data-ttu-id="ae0d8-116">Exemplo 2: obter o número especificado de mensagens de erro que ocorreram na sessão atual</span><span class="sxs-lookup"><span data-stu-id="ae0d8-116">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="ae0d8-117">Este exemplo mostra como usar `Get-Error` com o parâmetro **mais recente** .</span><span class="sxs-lookup"><span data-stu-id="ae0d8-117">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="ae0d8-118">Neste exemplo, o **mais recente** retorna os detalhes dos três erros mais recentes que ocorreram nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-118">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="ae0d8-119">Exemplo 3: Enviar uma coleção de erros para receber mensagens detalhadas</span><span class="sxs-lookup"><span data-stu-id="ae0d8-119">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="ae0d8-120">A `$Error` variável automática contém uma matriz de objetos de erro na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-120">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="ae0d8-121">A matriz de objetos pode ser canalizada para `Get-Error` receber mensagens de erro detalhadas.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-121">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="ae0d8-122">Neste exemplo, `$Error` é canalizado para o `Get-Error` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-122">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="ae0d8-123">o resultado é uma lista de mensagens de erro detalhadas, semelhante ao resultado do exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-123">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="ae0d8-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae0d8-124">PARAMETERS</span></span>

### <span data-ttu-id="ae0d8-125">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="ae0d8-125">-Newest</span></span>

<span data-ttu-id="ae0d8-126">Especifica o número de erros a serem exibidos que ocorreram na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-126">Specifies the number of errors to display that have occurred in the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae0d8-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ae0d8-127">-InputObject</span></span>

<span data-ttu-id="ae0d8-128">Esse parâmetro é usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-128">This parameter is used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ae0d8-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae0d8-129">CommonParameters</span></span>

<span data-ttu-id="ae0d8-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae0d8-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ae0d8-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ae0d8-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ae0d8-132">INPUTS</span></span>

### <span data-ttu-id="ae0d8-133">PSObject</span><span class="sxs-lookup"><span data-stu-id="ae0d8-133">PSObject</span></span>

<span data-ttu-id="ae0d8-134">Dá suporte à entrada de qualquer **PSObject** , mas os resultados variam, a menos que um objeto **ErrorRecord** ou de **exceção** seja fornecido.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-134">Supports input from any **PSObject** , but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="ae0d8-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ae0d8-135">OUTPUTS</span></span>

### <span data-ttu-id="ae0d8-136">System. Management. Automation. ErrorRecord # PSExtendedError</span><span class="sxs-lookup"><span data-stu-id="ae0d8-136">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="ae0d8-137">Saída em um objeto **PSExtendedError** .</span><span class="sxs-lookup"><span data-stu-id="ae0d8-137">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="ae0d8-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ae0d8-138">NOTES</span></span>

<span data-ttu-id="ae0d8-139">`Get-Error` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-139">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="ae0d8-140">Por exemplo, `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-140">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="ae0d8-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ae0d8-141">RELATED LINKS</span></span>

[<span data-ttu-id="ae0d8-142">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="ae0d8-142">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
