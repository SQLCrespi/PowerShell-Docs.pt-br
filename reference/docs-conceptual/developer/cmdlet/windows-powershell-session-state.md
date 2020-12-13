---
ms.date: 09/13/2016
ms.topic: reference
title: Estado de sessão do Windows PowerShell
description: Estado de sessão do Windows PowerShell
ms.openlocfilehash: 51de92f1f392f708cf49c7ccb4a6808fd628076c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668126"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="327a4-103">Estado de sessão do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="327a4-103">Windows PowerShell Session State</span></span>

<span data-ttu-id="327a4-104">Estado da sessão refere-se à configuração atual de uma sessão ou módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327a4-104">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="327a4-105">Uma sessão do Windows PowerShell é o ambiente operacional usado interativamente pelo usuário de linha de comando ou por meio de programação por um aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="327a4-105">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="327a4-106">O estado de sessão de uma sessão é conhecido como o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="327a4-106">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="327a4-107">Da perspectiva do desenvolvedor, uma sessão do Windows PowerShell refere-se ao tempo entre quando um aplicativo host abre um runspace do Windows PowerShell e quando fecha o runspace.</span><span class="sxs-lookup"><span data-stu-id="327a4-107">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="327a4-108">Examinamos de outra forma, a sessão é o tempo de vida de uma instância do mecanismo do Windows PowerShell que é invocado enquanto o runspace existe.</span><span class="sxs-lookup"><span data-stu-id="327a4-108">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="327a4-109">Estado de sessão do módulo</span><span class="sxs-lookup"><span data-stu-id="327a4-109">Module Session State</span></span>

<span data-ttu-id="327a4-110">Os Estados de sessão de módulo são criados sempre que o módulo ou um de seus módulos aninhados é importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="327a4-110">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="327a4-111">Quando um módulo exporta um elemento, como um cmdlet, uma função ou um script, uma referência a esse elemento é adicionada ao estado de sessão global da sessão.</span><span class="sxs-lookup"><span data-stu-id="327a4-111">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="327a4-112">No entanto, quando o elemento é executado, ele é executado dentro do estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="327a4-112">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="327a4-113">Session-State dados</span><span class="sxs-lookup"><span data-stu-id="327a4-113">Session-State Data</span></span>

<span data-ttu-id="327a4-114">Os dados de estado da sessão podem ser públicos ou privados.</span><span class="sxs-lookup"><span data-stu-id="327a4-114">Session state data can be public or private.</span></span> <span data-ttu-id="327a4-115">Os dados públicos estão disponíveis para chamadas de fora do estado da sessão enquanto dados privados estão disponíveis somente para chamadas de dentro do estado da sessão.</span><span class="sxs-lookup"><span data-stu-id="327a4-115">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="327a4-116">Por exemplo, um módulo pode ter uma função particular que pode ser chamada somente pelo módulo ou apenas internamente por um elemento público que tenha sido exportado.</span><span class="sxs-lookup"><span data-stu-id="327a4-116">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="327a4-117">Isso é semelhante aos membros públicos e privados de um tipo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="327a4-117">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="327a4-118">Os dados de estado da sessão são armazenados pela instância atual do mecanismo de execução no contexto da sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327a4-118">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="327a4-119">Os dados de estado da sessão consistem nos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="327a4-119">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="327a4-120">Informações de caminho</span><span class="sxs-lookup"><span data-stu-id="327a4-120">Path information</span></span>

- <span data-ttu-id="327a4-121">Informações da unidade</span><span class="sxs-lookup"><span data-stu-id="327a4-121">Drive information</span></span>

- <span data-ttu-id="327a4-122">Informações do provedor do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="327a4-122">Windows PowerShell provider information</span></span>

- <span data-ttu-id="327a4-123">Informações sobre os módulos importados e referências aos elementos do módulo (como, por exemplo, cmdlets, funções e scripts) que são exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="327a4-123">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="327a4-124">Essas informações e essas referências são apenas para o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="327a4-124">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="327a4-125">Informações da variável de estado da sessão</span><span class="sxs-lookup"><span data-stu-id="327a4-125">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="327a4-126">Acessando dados Session-State dentro de cmdlets</span><span class="sxs-lookup"><span data-stu-id="327a4-126">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="327a4-127">Os cmdlets podem acessar dados de estado de sessão indiretamente por meio da propriedade [System. Management. Automation. PSCmdlet. SessionState \*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) da classe cmdlet ou diretamente por meio da classe [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) .</span><span class="sxs-lookup"><span data-stu-id="327a4-127">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="327a4-128">A classe [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) fornece propriedades que podem ser usadas para investigar diferentes tipos de dados de estado de sessão.</span><span class="sxs-lookup"><span data-stu-id="327a4-128">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="327a4-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="327a4-129">See Also</span></span>

[<span data-ttu-id="327a4-130">System. Management. Automation. PSCmdlet. SessionState</span><span class="sxs-lookup"><span data-stu-id="327a4-130">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="327a4-131">System. Management. Automation. SessionState? Displayproperty = FullName</span><span class="sxs-lookup"><span data-stu-id="327a4-131">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="327a4-132">Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="327a4-132">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

<span data-ttu-id="327a4-133">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="327a4-133">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

[<span data-ttu-id="327a4-134">SDK do Shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="327a4-134">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
