---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplos de código GetProc04
description: Exemplos de código GetProc04
ms.openlocfilehash: db94eda2b3aa5fc88a3054df66f54628e1482f56
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659238"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="d2e49-103">Exemplos de código GetProc04</span><span class="sxs-lookup"><span data-stu-id="d2e49-103">GetProc04 Code Samples</span></span>

<span data-ttu-id="d2e49-104">Aqui estão os exemplos de código para o cmdlet de exemplo GetProc04.</span><span class="sxs-lookup"><span data-stu-id="d2e49-104">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="d2e49-105">Este é o `Get-Process` exemplo de cmdlet descrito em [adicionando relatórios de erros não finalizados ao seu cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="d2e49-105">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="d2e49-106">Esse `Get-Process` cmdlet chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) sempre que uma exceção de operação inválida é lançada durante a recuperação de informações do processo.</span><span class="sxs-lookup"><span data-stu-id="d2e49-106">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="d2e49-107">Você pode baixar o arquivo de origem C# (getprov04.cs) para este cmdlet Get-Proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e os componentes de tempo de execução do .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="d2e49-107">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d2e49-108">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d2e49-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="d2e49-109">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="d2e49-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="d2e49-110">Para obter o código de exemplo completo, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d2e49-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="d2e49-111">Idioma</span><span class="sxs-lookup"><span data-stu-id="d2e49-111">Language</span></span>|<span data-ttu-id="d2e49-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="d2e49-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="d2e49-113">C#</span><span class="sxs-lookup"><span data-stu-id="d2e49-113">C#</span></span>|[<span data-ttu-id="d2e49-114">Código de exemplo GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="d2e49-114">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="d2e49-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="d2e49-115">VB.NET</span></span>|[<span data-ttu-id="d2e49-116">Código de exemplo GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="d2e49-116">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="d2e49-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2e49-117">See Also</span></span>

[<span data-ttu-id="d2e49-118">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2e49-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d2e49-119">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2e49-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
