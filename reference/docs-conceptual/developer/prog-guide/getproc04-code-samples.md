---
title: Exemplos de código do GetProc04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 67081528ebe14fbb082091c1b9500de82069b48f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360315"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="94179-102">Exemplos de código GetProc04</span><span class="sxs-lookup"><span data-stu-id="94179-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="94179-103">Aqui estão os exemplos de código para o cmdlet de exemplo GetProc04.</span><span class="sxs-lookup"><span data-stu-id="94179-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="94179-104">Este é o exemplo de cmdlet `Get-Process` descrito em [adicionando relatórios de erros não finalizados ao seu cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="94179-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="94179-105">Esse cmdlet `Get-Process` chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) sempre que uma exceção de operação inválida é lançada durante a recuperação de informações do processo.</span><span class="sxs-lookup"><span data-stu-id="94179-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="94179-106">Você pode baixar o C# arquivo de origem (getprov04.cs) para este cmdlet Get-proc usando o kit de desenvolvimento de software do Microsoft Windows para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="94179-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="94179-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="94179-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="94179-108">Os arquivos de origem baixados estão disponíveis no diretório de **exemplos do \<PowerShell >** .</span><span class="sxs-lookup"><span data-stu-id="94179-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="94179-109">Para obter o código de exemplo completo, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="94179-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="94179-110">Language</span><span class="sxs-lookup"><span data-stu-id="94179-110">Language</span></span>|<span data-ttu-id="94179-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="94179-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="94179-112">C#</span><span class="sxs-lookup"><span data-stu-id="94179-112">C#</span></span>|[<span data-ttu-id="94179-113">Código deC#exemplo GetProc04 ()</span><span class="sxs-lookup"><span data-stu-id="94179-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="94179-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="94179-114">VB.NET</span></span>|[<span data-ttu-id="94179-115">Código de exemplo do GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="94179-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="94179-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94179-116">See Also</span></span>

[<span data-ttu-id="94179-117">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94179-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="94179-118">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94179-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)