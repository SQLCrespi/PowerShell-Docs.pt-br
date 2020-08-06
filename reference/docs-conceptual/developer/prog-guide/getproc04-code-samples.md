---
title: Exemplos de código do GetProc04 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771950"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="cce66-102">Exemplos de código GetProc04</span><span class="sxs-lookup"><span data-stu-id="cce66-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="cce66-103">Aqui estão os exemplos de código para o cmdlet de exemplo GetProc04.</span><span class="sxs-lookup"><span data-stu-id="cce66-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="cce66-104">Este é o `Get-Process` exemplo de cmdlet descrito em [adicionando relatórios de erros não finalizados ao seu cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="cce66-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="cce66-105">Esse `Get-Process` cmdlet chama o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) sempre que uma exceção de operação inválida é lançada durante a recuperação de informações do processo.</span><span class="sxs-lookup"><span data-stu-id="cce66-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="cce66-106">Você pode baixar o arquivo de origem do C# (getprov04.cs) para este cmdlet Get-proc usando o Microsoft Windows Software Development Kit para Windows Vista e .NET Framework os componentes de tempo de execução do 3,0.</span><span class="sxs-lookup"><span data-stu-id="cce66-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="cce66-107">Para obter instruções de download, consulte [como instalar o Windows PowerShell e baixar o SDK do Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="cce66-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="cce66-108">Os arquivos de origem baixados estão disponíveis no **\<PowerShell Samples>** diretório.</span><span class="sxs-lookup"><span data-stu-id="cce66-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="cce66-109">Para obter o código de exemplo completo, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="cce66-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="cce66-110">Idioma</span><span class="sxs-lookup"><span data-stu-id="cce66-110">Language</span></span>|<span data-ttu-id="cce66-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="cce66-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="cce66-112">C#</span><span class="sxs-lookup"><span data-stu-id="cce66-112">C#</span></span>|[<span data-ttu-id="cce66-113">Código de exemplo GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="cce66-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="cce66-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="cce66-114">VB.NET</span></span>|[<span data-ttu-id="cce66-115">Código de exemplo GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="cce66-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="cce66-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cce66-116">See Also</span></span>

[<span data-ttu-id="cce66-117">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cce66-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="cce66-118">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cce66-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
