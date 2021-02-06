---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 3b2c789225a1d76391015c39e3fc919ba65f0a1b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596591"
---
# <span data-ttu-id="40b25-102">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="40b25-102">Get-PSReadLineOption</span></span>

## <span data-ttu-id="40b25-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="40b25-103">SYNOPSIS</span></span>
<span data-ttu-id="40b25-104">Obtém valores para as opções que podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="40b25-104">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="40b25-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40b25-105">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="40b25-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40b25-106">DESCRIPTION</span></span>

<span data-ttu-id="40b25-107">O `Get-PSReadLineOption` cmdlet retorna o estado atual das configurações que podem ser configuradas usando o `Set-PSReadLineOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40b25-107">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="40b25-108">Você pode usar o objeto retornado para alterar as opções de **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="40b25-108">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="40b25-109">Isso fornece uma maneira ligeiramente mais simples de definir opções de coloração de sintaxe para vários tipos de tokens.</span><span class="sxs-lookup"><span data-stu-id="40b25-109">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="40b25-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="40b25-110">EXAMPLES</span></span>

### <span data-ttu-id="40b25-111">Exemplo 1: obter opções e seus valores</span><span class="sxs-lookup"><span data-stu-id="40b25-111">Example 1: Get options and their values</span></span>

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    : System.Func`2[System.String,System.Object]
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "`e[93m"
CommentColor                           : "`e[32m"
ContinuationPromptColor                : "`e[97m"
DefaultTokenColor                      : "`e[97m"
EmphasisColor                          : "`e[96m"
ErrorColor                             : "`e[91m"
KeywordColor                           : "`e[92m"
MemberColor                            : "`e[97m"
NumberColor                            : "`e[97m"
OperatorColor                          : "`e[90m"
ParameterColor                         : "`e[90m"
SelectionColor                         : "`e[30;107m"
StringColor                            : "`e[36m"
TypeColor                              : "`e[37m"
VariableColor                          : "`e[92m"
```

<span data-ttu-id="40b25-112">Esse comando retorna a lista de opções de PSReadLine disponíveis e seus valores atuais.</span><span class="sxs-lookup"><span data-stu-id="40b25-112">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="40b25-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40b25-113">PARAMETERS</span></span>

### <span data-ttu-id="40b25-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40b25-114">CommonParameters</span></span>

<span data-ttu-id="40b25-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40b25-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40b25-116">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40b25-116">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40b25-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="40b25-117">INPUTS</span></span>

### <span data-ttu-id="40b25-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="40b25-118">None</span></span>

<span data-ttu-id="40b25-119">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40b25-119">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="40b25-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="40b25-120">OUTPUTS</span></span>

### <span data-ttu-id="40b25-121">Microsoft. PowerShell. PSConsoleReadLineOptions</span><span class="sxs-lookup"><span data-stu-id="40b25-121">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="40b25-122">Uma instância das opções atuais.</span><span class="sxs-lookup"><span data-stu-id="40b25-122">An instance of the current options.</span></span> <span data-ttu-id="40b25-123">A alteração dos valores de propriedade desse objeto atualiza as configurações no PSReadLine diretamente sem invocar `Set-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="40b25-123">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="40b25-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="40b25-124">NOTES</span></span>

## <span data-ttu-id="40b25-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="40b25-125">RELATED LINKS</span></span>

[<span data-ttu-id="40b25-126">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="40b25-126">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="40b25-127">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="40b25-127">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="40b25-128">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="40b25-128">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="40b25-129">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="40b25-129">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
