---
ms.date: 12/05/2019
keywords: powershell, cmdlet
title: Iniciando o Windows PowerShell
description: Este artigo explica as maneiras de iniciar várias versões do PowerShell.
ms.openlocfilehash: 47da7d85c9f7e6966a7f7e809c77979cd24cf129
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664027"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="dc1e7-104">Iniciando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc1e7-104">Starting Windows PowerShell</span></span>

<span data-ttu-id="dc1e7-105">O Windows PowerShell é uma `.DLL` de mecanismo de script que é inserida em vários hosts.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-105">Windows PowerShell is a scripting engine `.DLL` that's embedded into multiple hosts.</span></span> <span data-ttu-id="dc1e7-106">Os hosts mais comuns que você iniciará são a linha de comando interativa `powershell.exe` e o Ambiente de Script Integrado `powershell_ise.exe`.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-106">The most common hosts you'll start are the interactive command-line `powershell.exe` and the Interactive Scripting Environment `powershell_ise.exe`.</span></span>

<span data-ttu-id="dc1e7-107">Para iniciar o Windows PowerShell&reg; no Windows Server&reg; 2012 R2, no Windows&reg; 8.1, no Windows Server 2012 e no Windows 8, confira [Tarefas comuns de gerenciamento e navegação no Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="dc1e7-107">To start Windows PowerShell&reg; on Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span></span>

## <a name="powershell-core-has-renamed-binary"></a><span data-ttu-id="dc1e7-108">O PowerShell Core renomeou o binário</span><span class="sxs-lookup"><span data-stu-id="dc1e7-108">PowerShell Core has renamed binary</span></span>

<span data-ttu-id="dc1e7-109">O PowerShell Core, conhecido como PowerShell, é a versão 6 e posterior que é de software livre e usa o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-109">PowerShell Core, referred to as PowerShell, is version 6 and higher that's open source and uses .NET Core.</span></span> <span data-ttu-id="dc1e7-110">As versões compatíveis estão disponíveis no Windows, no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-110">Supported versions are available on Windows, macOS, and Linux.</span></span>

<span data-ttu-id="dc1e7-111">No PowerShell 6 em diante, o binário do PowerShell foi renomeado `pwsh.exe` para o Windows e `pwsh` para o macOS e o Linux.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-111">Beginning in PowerShell 6, the PowerShell binary was renamed `pwsh.exe` for Windows and `pwsh` for macOS and Linux.</span></span> <span data-ttu-id="dc1e7-112">Você pode iniciar as versões prévias do PowerShell usando `pwsh-preview`.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-112">You can start PowerShell preview versions using `pwsh-preview`.</span></span> <span data-ttu-id="dc1e7-113">Para obter mais informações, confira [Novidades do PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) e [Sobre o pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span><span class="sxs-lookup"><span data-stu-id="dc1e7-113">For more information, see [What's New in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) and [About pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span></span>

<span data-ttu-id="dc1e7-114">Para encontrar a referência de cmdlet e a documentação de instalação do PowerShell 7, use os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="dc1e7-114">To find cmdlet reference and installation documentation for PowerShell 7, use the following links:</span></span>

| <span data-ttu-id="dc1e7-115">Documento</span><span class="sxs-lookup"><span data-stu-id="dc1e7-115">Document</span></span> | <span data-ttu-id="dc1e7-116">Link</span><span class="sxs-lookup"><span data-stu-id="dc1e7-116">Link</span></span> |
| ----- | ----- |
| <span data-ttu-id="dc1e7-117">Referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc1e7-117">Cmdlet reference</span></span> | [<span data-ttu-id="dc1e7-118">Navegador do Módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc1e7-118">PowerShell Module Browser</span></span>](/powershell/module/) |
| <span data-ttu-id="dc1e7-119">Instalação do Windows</span><span class="sxs-lookup"><span data-stu-id="dc1e7-119">Windows installation</span></span> | [<span data-ttu-id="dc1e7-120">Instalar o PowerShell Core no Windows</span><span class="sxs-lookup"><span data-stu-id="dc1e7-120">Installing PowerShell Core on Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows) |
| <span data-ttu-id="dc1e7-121">Instalação do macOS</span><span class="sxs-lookup"><span data-stu-id="dc1e7-121">macOS installation</span></span> | [<span data-ttu-id="dc1e7-122">Instalar o PowerShell Core no macOS</span><span class="sxs-lookup"><span data-stu-id="dc1e7-122">Installing PowerShell Core on macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos) |
| <span data-ttu-id="dc1e7-123">Instalação do Linux</span><span class="sxs-lookup"><span data-stu-id="dc1e7-123">Linux installation</span></span> | [<span data-ttu-id="dc1e7-124">Instalar o PowerShell Core no Linux</span><span class="sxs-lookup"><span data-stu-id="dc1e7-124">Installing PowerShell Core on Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux) |

<span data-ttu-id="dc1e7-125">Para exibir o conteúdo de outras versões do PowerShell, confira [Como usar a documentação do PowerShell](../how-to-use-docs.md).</span><span class="sxs-lookup"><span data-stu-id="dc1e7-125">To view content for other PowerShell versions, see [How to use the PowerShell documentation](../how-to-use-docs.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="dc1e7-126">Como iniciar o Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="dc1e7-126">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="dc1e7-127">Esta seção explica como iniciar o Windows PowerShell e o ISE (Ambiente de Script Integrado) do Windows PowerShell no Windows&reg; 7, Windows Server&reg; 2008 R2 e Windows Server&reg; 2008.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-127">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows&reg; 7, Windows Server&reg; 2008 R2, and Windows Server&reg; 2008.</span></span> <span data-ttu-id="dc1e7-128">Também explica como habilitar o recurso opcional para o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server&reg; 2008 R2 e Windows Server&reg; 2008.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-128">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server&reg; 2008 R2 and Windows Server&reg; 2008.</span></span>

<span data-ttu-id="dc1e7-129">Use qualquer um dos seguintes métodos para iniciar a versão instalada do Windows PowerShell 3.0 ou o Windows PowerShell 4.0, quando aplicável.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-129">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="dc1e7-130">Do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="dc1e7-130">From the Start Menu</span></span>

- <span data-ttu-id="dc1e7-131">Clique em **Iniciar** , digite **PowerShell** e clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-131">Click **Start** , type **PowerShell** , and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="dc1e7-132">No menu **Iniciar** , clique em **Iniciar** , **Todos os Programas** , **Acessórios** , clique na pasta **Windows PowerShell** e clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-132">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="dc1e7-133">No prompt de comando</span><span class="sxs-lookup"><span data-stu-id="dc1e7-133">At the Command Prompt</span></span>

<span data-ttu-id="dc1e7-134">No **cmd.exe** , no Windows PowerShell ou no ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="dc1e7-134">In **cmd.exe** , Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="dc1e7-135">Use também os parâmetros do programa `powershell.exe` para personalizar a sessão.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-135">You can also use the parameters of the `powershell.exe` program to customize the session.</span></span> <span data-ttu-id="dc1e7-136">Para obter mais informações, consulte [Ajuda de linha de comando do PowerShell.exe](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span><span class="sxs-lookup"><span data-stu-id="dc1e7-136">For more information, see [PowerShell.exe Command-Line Help](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="dc1e7-137">Com privilégios administrativos (Executar como administrador)</span><span class="sxs-lookup"><span data-stu-id="dc1e7-137">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="dc1e7-138">Clique em **Iniciar** , digite **PowerShell** , clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-138">Click **Start** , type **PowerShell** , right-click **Windows PowerShell** , and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="dc1e7-139">Como iniciar o ISE do Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="dc1e7-139">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="dc1e7-140">Use qualquer um dos seguintes métodos para iniciar o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-140">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="dc1e7-141">Do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="dc1e7-141">From the Start Menu</span></span>

- <span data-ttu-id="dc1e7-142">Clique em **Iniciar** , digite **ISE** e clique em **ISE do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-142">Click **Start** , type **ISE** , and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="dc1e7-143">No menu **Iniciar** , clique em **Iniciar** , **Todos os Programas** , **Acessórios** , clique na pasta **Windows PowerShell** e clique em **ISE do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-143">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="dc1e7-144">No prompt de comando</span><span class="sxs-lookup"><span data-stu-id="dc1e7-144">At the Command Prompt</span></span>

<span data-ttu-id="dc1e7-145">No `cmd.exe`, Windows PowerShell ou ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="dc1e7-145">In `cmd.exe`, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="dc1e7-146">ou</span><span class="sxs-lookup"><span data-stu-id="dc1e7-146">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="dc1e7-147">Com privilégios administrativos (Executar como administrador)</span><span class="sxs-lookup"><span data-stu-id="dc1e7-147">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="dc1e7-148">Clique em **Iniciar** , digite **ISE** , clique com o botão direito do mouse em **ISE do Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-148">Click **Start** , type **ISE** , right-click **Windows PowerShell ISE** , and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="dc1e7-149">Como habilitar o ISE do Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="dc1e7-149">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="dc1e7-150">No Windows PowerShell 4.0 e Windows PowerShell 3.0, o ISE do Windows PowerShell é habilitado por padrão em todas as versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-150">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="dc1e7-151">Se ele ainda não estiver habilitado, o Windows Management Framework 4.0 ou o Windows Management Framework 3.0 o habilitará.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-151">If it isn't already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="dc1e7-152">No Windows PowerShell 2.0, o ISE do Windows PowerShell é habilitado por padrão no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-152">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="dc1e7-153">No entanto, no Windows Server 2008 R2 e no Windows Server 2008, esse é um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-153">However, on Windows Server 2008 R2 and Windows Server 2008, it's an optional feature.</span></span>

<span data-ttu-id="dc1e7-154">Para habilitar o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server 2008 R2 ou Windows Server 2008, use o seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-154">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="dc1e7-155">Para habilitar o ISE (Ambiente de Script Integrado) do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc1e7-155">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="dc1e7-156">Inicie o Gerenciador do Servidor.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-156">Start Server Manager.</span></span>
2. <span data-ttu-id="dc1e7-157">Clique em **Recursos** e depois em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-157">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="dc1e7-158">Em Selecionar Recursos, clique em ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-158">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="dc1e7-159">Iniciando a versão de 32 bits do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc1e7-159">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="dc1e7-160">Quando você instala o Windows PowerShell em um computador de 64 bits, o **Windows PowerShell (x86)** , uma versão de 32 bits do Windows PowerShell é instalada com a versão de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-160">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)** , a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="dc1e7-161">Quando você executa o Windows PowerShell, a versão de 64 bits é executada por padrão.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-161">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="dc1e7-162">No entanto, ocasionalmente poderá ser necessário executar o **Windows PowerShell (x86)** , como quando você estiver usando um módulo que exija a versão de 32 bits ou quando você estiver se conectando remotamente a um computador de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-162">However, you might occasionally need to run **Windows PowerShell (x86)** , such as when you're using a module that requires the 32-bit version or when you're connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="dc1e7-163">Para iniciar uma versão de 32 bits do Windows PowerShell, use qualquer um dos procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-163">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-serverreg-2012-r2"></a><span data-ttu-id="dc1e7-164">No Windows Server&reg; 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dc1e7-164">In Windows Server&reg; 2012 R2</span></span>

- <span data-ttu-id="dc1e7-165">Na tela **Iniciar** , clique em **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-165">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="dc1e7-166">Clique no bloco **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-166">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="dc1e7-167">Em **Gerenciador do Servidor** , no menu **Ferramentas** , selecione **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-167">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-168">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar** , digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="dc1e7-168">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-169">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="dc1e7-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-serverreg-2012"></a><span data-ttu-id="dc1e7-170">No Windows Server&reg; 2012</span><span class="sxs-lookup"><span data-stu-id="dc1e7-170">In Windows Server&reg; 2012</span></span>

- <span data-ttu-id="dc1e7-171">Na tela **Iniciar** , digite **PowerShell** e clique em **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-171">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-172">Em **Gerenciador do Servidor** , no menu **Ferramentas** , selecione **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-172">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-173">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar** , digite **PowerShell** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="dc1e7-173">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-174">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="dc1e7-174">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-81"></a><span data-ttu-id="dc1e7-175">No Windows&reg; 8.1</span><span class="sxs-lookup"><span data-stu-id="dc1e7-175">In Windows&reg; 8.1</span></span>

- <span data-ttu-id="dc1e7-176">Na tela **Iniciar** , clique em **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-176">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="dc1e7-177">Clique no bloco **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-177">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="dc1e7-178">Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://go.microsoft.com/fwlink/?LinkID=304145) para o Windows 8.1, abra também o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-178">If you're running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="dc1e7-179">Selecione **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-179">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-180">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar** , digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="dc1e7-180">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-181">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="dc1e7-181">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-8"></a><span data-ttu-id="dc1e7-182">No Windows&reg; 8</span><span class="sxs-lookup"><span data-stu-id="dc1e7-182">In Windows&reg; 8</span></span>

- <span data-ttu-id="dc1e7-183">Na tela **Iniciar** , mova o cursor para o canto superior direito, clique em **Configurações** , **Blocos** e, em seguida, mova o controle deslizante **Mostrar Ferramentas Administrativas** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-183">On the **Start** screen, move the cursor to the upper right corner, click **Settings** , click **Tiles** , and then move the **Show Administrative Tools** slider to **Yes**.</span></span> <span data-ttu-id="dc1e7-184">Em seguida, digite **PowerShell** e clique em **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-184">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-185">Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://www.microsoft.com/download/details.aspx?id=28972) para o Windows 8, abra também o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-185">If you're running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="dc1e7-186">Selecione **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-186">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-187">Na tela **Iniciar** ou na área de trabalho, digite **PowerShell (x86)** e clique em **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="dc1e7-187">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="dc1e7-188">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="dc1e7-188">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
