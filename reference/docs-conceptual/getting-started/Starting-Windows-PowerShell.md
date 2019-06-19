---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Iniciando o Windows PowerShell
ms.openlocfilehash: d2cb77027f404c5b008a902c5147d018dd741a67
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030445"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="e8a5e-103">Iniciando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8a5e-103">Starting Windows PowerShell</span></span>
<span data-ttu-id="e8a5e-104">O PowerShell é uma dll de mecanismo de script que é inserida em vários hosts.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-104">PowerShell is a scripting engine dll which is embedded into multiple hosts.</span></span>  <span data-ttu-id="e8a5e-105">Os hosts que você iniciará com mais frequência são a linha de comando interativa do PowerShell.exe e o Ambiente de Script Integrado do PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-105">The most common host you will start are the interactive command line PowerShell.exe and the Interactive Scripting Environment PowerShell_ISE.exe.</span></span>

<span data-ttu-id="e8a5e-106">Para iniciar o Windows PowerShell® no Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012 e Windows 8, consulte [Common Management Tasks and Navigation (Tarefas comuns de gerenciamento e navegação)](https://technet.microsoft.com/library/hh831491.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8a5e-106">To start Windows PowerShell® on Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation](https://technet.microsoft.com/library/hh831491.aspx).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="e8a5e-107">Como iniciar o Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="e8a5e-107">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="e8a5e-108">Esta seção explica como iniciar o Windows PowerShell e o ISE (Ambiente de Script Integrado) do Windows PowerShell no Windows® 7, Windows Server® 2008 R2 e Windows Server® 2008.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-108">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows® 7, Windows Server® 2008 R2, and Windows Server® 2008.</span></span> <span data-ttu-id="e8a5e-109">Também explica como habilitar o recurso opcional para o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server® 2008 R2 e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-109">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server® 2008 R2 and Windows Server® 2008.</span></span>

<span data-ttu-id="e8a5e-110">Use qualquer um dos seguintes métodos para iniciar a versão instalada do Windows PowerShell 3.0 ou o Windows PowerShell 4.0, quando aplicável.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-110">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="e8a5e-111">Do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="e8a5e-111">From the Start Menu</span></span>

- <span data-ttu-id="e8a5e-112">Clique em **Iniciar**, digite **PowerShell** e clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-112">Click **Start**, type **PowerShell**, and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="e8a5e-113">No menu **Iniciar**, clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique na pasta **Windows PowerShell** e clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-113">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="e8a5e-114">No prompt de comando</span><span class="sxs-lookup"><span data-stu-id="e8a5e-114">At the Command Prompt</span></span>

<span data-ttu-id="e8a5e-115">No Cmd.exe, Windows PowerShell ou ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="e8a5e-115">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="e8a5e-116">Você também pode usar os parâmetros do programa PowerShell.exe para personalizar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-116">You can also use the parameters of the PowerShell.exe program to customize the session.</span></span> <span data-ttu-id="e8a5e-117">Para obter mais informações, consulte [Ajuda de linha de comando do PowerShell.exe](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span><span class="sxs-lookup"><span data-stu-id="e8a5e-117">For more information, see [PowerShell.exe Command-Line Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="e8a5e-118">Com privilégios administrativos (“Executar como administrador”)</span><span class="sxs-lookup"><span data-stu-id="e8a5e-118">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="e8a5e-119">Clique em **Iniciar**, digite **PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-119">Click **Start**, type **PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="e8a5e-120">Como iniciar o ISE do Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="e8a5e-120">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="e8a5e-121">Use qualquer um dos seguintes métodos para iniciar o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-121">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="e8a5e-122">Do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="e8a5e-122">From the Start Menu</span></span>

- <span data-ttu-id="e8a5e-123">Clique em **Iniciar**, digite **ISE** e clique em **ISE do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-123">Click **Start**, type **ISE**, and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="e8a5e-124">No menu **Iniciar**, clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique na pasta **Windows PowerShell** e clique em **ISE do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-124">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="e8a5e-125">No prompt de comando</span><span class="sxs-lookup"><span data-stu-id="e8a5e-125">At the Command Prompt</span></span>

<span data-ttu-id="e8a5e-126">No Cmd.exe, Windows PowerShell ou ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="e8a5e-126">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="e8a5e-127">ou</span><span class="sxs-lookup"><span data-stu-id="e8a5e-127">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="e8a5e-128">Com privilégios administrativos (“Executar como administrador”)</span><span class="sxs-lookup"><span data-stu-id="e8a5e-128">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="e8a5e-129">Clique em **Iniciar**, digite **ISE**, clique com o botão direito do mouse em **ISE do Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-129">Click **Start**, type **ISE**, right-click **Windows PowerShell ISE**, and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="e8a5e-130">Como habilitar o ISE do Windows PowerShell em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="e8a5e-130">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="e8a5e-131">No Windows PowerShell 4.0 e Windows PowerShell 3.0, o ISE do Windows PowerShell é habilitado por padrão em todas as versões do Windows.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-131">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="e8a5e-132">Se ele ainda não estiver habilitado, o Windows Management Framework 4.0 ou Windows Management Framework 3.0 o habilitará.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-132">If it is not already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="e8a5e-133">No Windows PowerShell 2.0, o ISE do Windows PowerShell é habilitado por padrão no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-133">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="e8a5e-134">No entanto, no Windows Server 2008 R2 e Windows Server 2008, é um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-134">However, on Windows Server 2008 R2 and Windows Server 2008, it is an optional feature.</span></span>

<span data-ttu-id="e8a5e-135">Para habilitar o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server 2008 R2 ou Windows Server 2008, use o seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-135">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="e8a5e-136">Para habilitar o ISE (Ambiente de Script Integrado) do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8a5e-136">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="e8a5e-137">Inicie o Gerenciador do Servidor.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-137">Start Server Manager.</span></span>
2. <span data-ttu-id="e8a5e-138">Clique em **Recursos** e depois em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-138">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="e8a5e-139">Em Selecionar Recursos, clique em ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-139">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="e8a5e-140">Iniciando a versão de 32 bits do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8a5e-140">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="e8a5e-141">Quando você instala o Windows PowerShell em um computador de 64 bits, o **Windows PowerShell (x86)** , uma versão de 32 bits do Windows PowerShell é instalada com a versão de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-141">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)**, a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="e8a5e-142">Quando você executa o Windows PowerShell, a versão de 64 bits é executada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-142">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="e8a5e-143">No entanto, ocasionalmente pode ser necessário executar o **Windows PowerShell (x86)** , como quando você estiver usando um módulo que requer a versão de 32 bits ou quando você quiser se conectar remotamente a um computador de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-143">However, you might occasionally need to run **Windows PowerShell (x86)**, such as when you are using a module that requires the 32-bit version or when you are connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="e8a5e-144">Para iniciar uma versão de 32 bits do Windows PowerShell, use qualquer um dos procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-144">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-server-2012-r2"></a><span data-ttu-id="e8a5e-145">No Windows Server® 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e8a5e-145">In Windows Server® 2012 R2</span></span>

- <span data-ttu-id="e8a5e-146">Na tela **Iniciar**, clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-146">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="e8a5e-147">Clique no bloco **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-147">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="e8a5e-148">Em **Gerenciador do Servidor**, no menu **Ferramentas**, selecione **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-148">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-149">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-149">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-150">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="e8a5e-150">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-server-2012"></a><span data-ttu-id="e8a5e-151">No Windows Server® 2012</span><span class="sxs-lookup"><span data-stu-id="e8a5e-151">In Windows Server® 2012</span></span>

- <span data-ttu-id="e8a5e-152">Na tela **Iniciar**, digite **PowerShell** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-152">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-153">Em **Gerenciador do Servidor**, no menu **Ferramentas**, selecione **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-153">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-154">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-154">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-155">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="e8a5e-155">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-81"></a><span data-ttu-id="e8a5e-156">No Windows® 8.1</span><span class="sxs-lookup"><span data-stu-id="e8a5e-156">In Windows® 8.1</span></span>

- <span data-ttu-id="e8a5e-157">Na tela **Iniciar**, clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-157">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="e8a5e-158">Clique no bloco **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-158">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="e8a5e-159">Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://go.microsoft.com/fwlink/?LinkID=304145) para o Windows 8.1, você também poderá abrir o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-159">If you are running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span>
  <span data-ttu-id="e8a5e-160">Selecione **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-160">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-161">Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-161">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-162">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="e8a5e-162">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-8"></a><span data-ttu-id="e8a5e-163">No Windows® 8</span><span class="sxs-lookup"><span data-stu-id="e8a5e-163">In Windows® 8</span></span>

- <span data-ttu-id="e8a5e-164">Na tela **Iniciar**, mova o cursor para o canto superior direito, clique em **Configurações**, **Blocos** e mova o controle deslizante **Mostrar Ferramentas Administrativas** para Sim.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-164">On the **Start** screen, move the cursor to the upper right corner, click **Settings**, click **Tiles**, and then move the **Show Administrative Tools** slider to Yes.</span></span> <span data-ttu-id="e8a5e-165">Em seguida, digite **PowerShell** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-165">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-166">Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://www.microsoft.com/download/details.aspx?id=28972) para o Windows 8, você também poderá abrir o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="e8a5e-166">If you are running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="e8a5e-167">Selecione **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-167">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-168">Na tela **Iniciar** ou na área de trabalho, digite **PowerShell (x86)** e clique em **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="e8a5e-168">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="e8a5e-169">Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="e8a5e-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
