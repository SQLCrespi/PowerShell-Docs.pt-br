---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 7e4f4adf60a4f6386c646d92ada0003f239f05f4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596794"
---
# <span data-ttu-id="00d15-102">Get-Error</span><span class="sxs-lookup"><span data-stu-id="00d15-102">Get-Error</span></span>

## <span data-ttu-id="00d15-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="00d15-103">SYNOPSIS</span></span>

<span data-ttu-id="00d15-104">Obtém e exibe as mensagens de erro mais recentes da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="00d15-104">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="00d15-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00d15-105">SYNTAX</span></span>

### <span data-ttu-id="00d15-106">Mais recente (padrão)</span><span class="sxs-lookup"><span data-stu-id="00d15-106">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="00d15-107">Erro do</span><span class="sxs-lookup"><span data-stu-id="00d15-107">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="00d15-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00d15-108">DESCRIPTION</span></span>

<span data-ttu-id="00d15-109">O `Get-Error` cmdlet obtém um objeto **PSExtendedError** que representa os detalhes do erro atual do último erro que ocorreu na sessão.</span><span class="sxs-lookup"><span data-stu-id="00d15-109">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="00d15-110">Você pode usar `Get-Error` para exibir um número especificado de erros que ocorreram na sessão atual usando o parâmetro **mais recente** .</span><span class="sxs-lookup"><span data-stu-id="00d15-110">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="00d15-111">O `Get-Error` cmdlet também recebe objetos de erro de uma coleção, como `$Error` , para exibir vários erros da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="00d15-111">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="00d15-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="00d15-112">EXAMPLES</span></span>

### <span data-ttu-id="00d15-113">Exemplo 1: obter os detalhes de erro mais recentes</span><span class="sxs-lookup"><span data-stu-id="00d15-113">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="00d15-114">Neste exemplo, `Get-Error` exibe os detalhes do erro mais recente que ocorreu na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="00d15-114">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

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

### <span data-ttu-id="00d15-115">Exemplo 2: obter o número especificado de mensagens de erro que ocorreram na sessão atual</span><span class="sxs-lookup"><span data-stu-id="00d15-115">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="00d15-116">Este exemplo mostra como usar `Get-Error` com o parâmetro **mais recente** .</span><span class="sxs-lookup"><span data-stu-id="00d15-116">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="00d15-117">Neste exemplo, o **mais recente** retorna os detalhes dos três erros mais recentes que ocorreram nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="00d15-117">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="00d15-118">Exemplo 3: Enviar uma coleção de erros para receber mensagens detalhadas</span><span class="sxs-lookup"><span data-stu-id="00d15-118">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="00d15-119">A `$Error` variável automática contém uma matriz de objetos de erro na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="00d15-119">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="00d15-120">A matriz de objetos pode ser canalizada para `Get-Error` receber mensagens de erro detalhadas.</span><span class="sxs-lookup"><span data-stu-id="00d15-120">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="00d15-121">Neste exemplo, `$Error` é canalizado para o `Get-Error` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="00d15-121">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="00d15-122">o resultado é uma lista de mensagens de erro detalhadas, semelhante ao resultado do exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="00d15-122">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="00d15-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00d15-123">PARAMETERS</span></span>

### <span data-ttu-id="00d15-124">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="00d15-124">-Newest</span></span>

<span data-ttu-id="00d15-125">Especifica o número de erros a serem exibidos que ocorreram na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="00d15-125">Specifies the number of errors to display that have occurred in the current session.</span></span>

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

### <span data-ttu-id="00d15-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00d15-126">-InputObject</span></span>

<span data-ttu-id="00d15-127">Esse parâmetro é usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="00d15-127">This parameter is used for pipeline input.</span></span>

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

### <span data-ttu-id="00d15-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="00d15-128">CommonParameters</span></span>

<span data-ttu-id="00d15-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="00d15-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00d15-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="00d15-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00d15-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="00d15-131">INPUTS</span></span>

### <span data-ttu-id="00d15-132">PSObject</span><span class="sxs-lookup"><span data-stu-id="00d15-132">PSObject</span></span>

<span data-ttu-id="00d15-133">Dá suporte à entrada de qualquer **PSObject**, mas os resultados variam, a menos que um objeto **ErrorRecord** ou de **exceção** seja fornecido.</span><span class="sxs-lookup"><span data-stu-id="00d15-133">Supports input from any **PSObject**, but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="00d15-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="00d15-134">OUTPUTS</span></span>

### <span data-ttu-id="00d15-135">System. Management. Automation. ErrorRecord # PSExtendedError</span><span class="sxs-lookup"><span data-stu-id="00d15-135">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="00d15-136">Saída em um objeto **PSExtendedError** .</span><span class="sxs-lookup"><span data-stu-id="00d15-136">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="00d15-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="00d15-137">NOTES</span></span>

<span data-ttu-id="00d15-138">`Get-Error` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="00d15-138">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="00d15-139">Por exemplo, `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="00d15-139">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="00d15-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="00d15-140">RELATED LINKS</span></span>

[<span data-ttu-id="00d15-141">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="00d15-141">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
