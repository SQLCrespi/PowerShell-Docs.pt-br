---
title: Comunicação remota do PowerShell por SSH
ms.date: 10/19/2020
description: Explica como configurar o protocolo SSH para comunicação remota do PowerShell.
ms.openlocfilehash: c3373ac30fd915d42e8c9fb7f1eae348a2aee7f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501330"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="b6759-103">Comunicação remota do PowerShell por SSH</span><span class="sxs-lookup"><span data-stu-id="b6759-103">PowerShell remoting over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="b6759-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b6759-104">Overview</span></span>

<span data-ttu-id="b6759-105">Normalmente, a comunicação remota do PowerShell usa WinRM para negociação de conexão e transporte de dados.</span><span class="sxs-lookup"><span data-stu-id="b6759-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="b6759-106">Agora, o SSH está disponível para plataformas Linux e Windows, e permite a verdadeira comunicação remota multiplataforma do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="b6759-107">O WinRM fornece um modelo de hospedagem robusto para sessões remotas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="b6759-108">No momento, a comunicação remota baseada em SSH não é compatível com a configuração de ponto de extremidade remoto e JEA (Just Enough Administration).</span><span class="sxs-lookup"><span data-stu-id="b6759-108">SSH-based remoting doesn't currently support remote endpoint configuration and Just Enough Administration (JEA).</span></span>

<span data-ttu-id="b6759-109">A comunicação remota do SSH permite fazer a comunicação remota de sessão básica do PowerShell entre máquinas Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="b6759-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux computers.</span></span> <span data-ttu-id="b6759-110">A comunicação remota do SSH cria um processo de hospedagem do PowerShell no computador de destino como um subsistema de SSH.</span><span class="sxs-lookup"><span data-stu-id="b6759-110">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="b6759-111">Eventualmente, implementaremos um modelo de hospedagem geral, semelhante ao WinRM, para dar suporte à configuração de ponto de extremidade e JEA.</span><span class="sxs-lookup"><span data-stu-id="b6759-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="b6759-112">Agora, os cmdlets `New-PSSession`, `Enter-PSSession` e `Invoke-Command` têm um novo parâmetro definido para dar suporte a essa nova conexão de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="b6759-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="b6759-113">Para criar uma sessão remota, especifique o computador de destino com o parâmetro **HostName** e forneça o nome de usuário com **UserName**.</span><span class="sxs-lookup"><span data-stu-id="b6759-113">To create a remote session, you specify the target computer with the **HostName** parameter and provide the user name with **UserName**.</span></span> <span data-ttu-id="b6759-114">Ao executar os cmdlets interativamente, você receberá uma solicitação de senha.</span><span class="sxs-lookup"><span data-stu-id="b6759-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="b6759-115">Você também pode usar a autenticação de chave SSH usando um arquivo de chave privada com o parâmetro **KeyFilePath**.</span><span class="sxs-lookup"><span data-stu-id="b6759-115">You can also use SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span> <span data-ttu-id="b6759-116">A criação de chaves para a autenticação SSH varia de acordo com a plataforma.</span><span class="sxs-lookup"><span data-stu-id="b6759-116">Creating keys for SSH authentication varies by platform.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="b6759-117">Informações gerais de configuração</span><span class="sxs-lookup"><span data-stu-id="b6759-117">General setup information</span></span>

<span data-ttu-id="b6759-118">PowerShell 6 ou superior, e o SSH deve ser instalado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="b6759-118">PowerShell 6 or higher, and SSH must be installed on all computers.</span></span> <span data-ttu-id="b6759-119">Instale o cliente SSH (`ssh.exe`) e o servidor (`sshd.exe`) para fazer a comunicação remota entre os computadores.</span><span class="sxs-lookup"><span data-stu-id="b6759-119">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the computers.</span></span> <span data-ttu-id="b6759-120">Agora o OpenSSH para Windows está disponível no build 1809 do Windows 10 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b6759-120">OpenSSH for Windows is now available in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="b6759-121">Para saber mais, confira [Gerenciar o Windows com OpenSSH](/windows-server/administration/openssh/openssh_overview).</span><span class="sxs-lookup"><span data-stu-id="b6759-121">For more information, see [Manage Windows with OpenSSH](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="b6759-122">No Linux, instale o SSH (incluindo sshd server) apropriado para a sua plataforma.</span><span class="sxs-lookup"><span data-stu-id="b6759-122">For Linux, install SSH, including sshd server, that's appropriate for your platform.</span></span> <span data-ttu-id="b6759-123">Também é preciso instalar o PowerShell no GitHub para obter o recurso de comunicação remota do SSH.</span><span class="sxs-lookup"><span data-stu-id="b6759-123">You also need to install PowerShell from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="b6759-124">O servidor SSH deve ser configurado para criar um subsistema de SSH para hospedar um processo do PowerShell no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b6759-124">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote computer.</span></span> <span data-ttu-id="b6759-125">É necessário habilitar a autenticação por **senha** ou **baseada em chave**.</span><span class="sxs-lookup"><span data-stu-id="b6759-125">And, you must enable **password** or **key-based** authentication.</span></span>

## <a name="set-up-on-a-windows-computer"></a><span data-ttu-id="b6759-126">Configurar em um computador com Windows</span><span class="sxs-lookup"><span data-stu-id="b6759-126">Set up on a Windows computer</span></span>

1. <span data-ttu-id="b6759-127">Instalar a versão mais recente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-127">Install the latest version of PowerShell.</span></span> <span data-ttu-id="b6759-128">Para obter mais informações, confira [Como instalar o PowerShell Core no Windows](../../install/installing-powershell-core-on-windows.md#msi).</span><span class="sxs-lookup"><span data-stu-id="b6759-128">For more information, see [Installing PowerShell Core on Windows](../../install/installing-powershell-core-on-windows.md#msi).</span></span>

   <span data-ttu-id="b6759-129">É possível confirmar se o PowerShell é compatível com a comunicação remota do SSH listando os conjuntos do parâmetro `New-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="b6759-129">You can confirm that PowerShell has SSH remoting support by listing the `New-PSSession` parameter sets.</span></span> <span data-ttu-id="b6759-130">Você observará que há nomes de conjunto de parâmetros que começam com **SSH**.</span><span class="sxs-lookup"><span data-stu-id="b6759-130">You'll notice there are parameter set names that begin with **SSH**.</span></span> <span data-ttu-id="b6759-131">Esses conjuntos de parâmetros incluem parâmetros **SSH**.</span><span class="sxs-lookup"><span data-stu-id="b6759-131">Those parameter sets include **SSH** parameters.</span></span>

   ```powershell
   (Get-Command New-PSSession).ParameterSets.Name
   ```

   ```Output
   Name
   ----
   SSHHost
   SSHHostHashParam
   ```

1. <span data-ttu-id="b6759-132">Instale o OpenSSH Win32 mais recente.</span><span class="sxs-lookup"><span data-stu-id="b6759-132">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="b6759-133">Para ver as instruções de instalação, confira [Introdução ao OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span><span class="sxs-lookup"><span data-stu-id="b6759-133">For installation instructions, see [Getting started with OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b6759-134">Se você quiser definir o PowerShell como o shell padrão para o OpenSSH, confira [Configurar o Windows para o OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span><span class="sxs-lookup"><span data-stu-id="b6759-134">If you want to set PowerShell as the default shell for OpenSSH, see [Configuring Windows for OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span></span>

1. <span data-ttu-id="b6759-135">Edite o arquivo `sshd_config` localizado em `$env:ProgramData\ssh`.</span><span class="sxs-lookup"><span data-stu-id="b6759-135">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   <span data-ttu-id="b6759-136">Verifique se a autenticação de senha está habilitada:</span><span class="sxs-lookup"><span data-stu-id="b6759-136">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="b6759-137">Crie o subsistema SSH que hospeda um processo do PowerShell no computador remoto:</span><span class="sxs-lookup"><span data-stu-id="b6759-137">Create the SSH subsystem that hosts a PowerShell process on the remote computer:</span></span>

   ```
   Subsystem powershell c:/progra~1/powershell/7/pwsh.exe -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="b6759-138">O local padrão do executável do PowerShell é `c:/progra~1/powershell/7/pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="b6759-138">The default location of the PowerShell executable is `c:/progra~1/powershell/7/pwsh.exe`.</span></span> <span data-ttu-id="b6759-139">O local pode variar dependendo de como você instalou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-139">The location can vary depending on how you installed PowerShell.</span></span>
   >
   > <span data-ttu-id="b6759-140">Você deve usar o nome curto 8.3 para qualquer caminho de arquivo que contenha espaços.</span><span class="sxs-lookup"><span data-stu-id="b6759-140">You must use the 8.3 short name for any file paths that contain spaces.</span></span> <span data-ttu-id="b6759-141">Há um bug no OpenSSH para Windows que impede que os espaços trabalhem em caminhos executáveis do subsistema.</span><span class="sxs-lookup"><span data-stu-id="b6759-141">There's a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="b6759-142">Para saber mais, confira este [problema do GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span><span class="sxs-lookup"><span data-stu-id="b6759-142">For more information, see this [GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>
   >
   > <span data-ttu-id="b6759-143">O nome curto 8.3 para a pasta `Program Files` no Windows geralmente é `Progra~1`.</span><span class="sxs-lookup"><span data-stu-id="b6759-143">The 8.3 short name for the `Program Files` folder in Windows is usually `Progra~1`.</span></span> <span data-ttu-id="b6759-144">No entanto, você pode usar o seguinte comando para garantir:</span><span class="sxs-lookup"><span data-stu-id="b6759-144">However, you can use the following command to make sure:</span></span>
   >
   > ```powershell
   > Get-CimInstance Win32_Directory -Filter 'Name="C:\\Program Files"' |
   >   Select-Object EightDotThreeFileName
   > ```
   >
   > ```Output
   > EightDotThreeFileName
   > ---------------------
   > c:\progra~1
   > ```

   <span data-ttu-id="b6759-145">Como alternativa, habilite a autenticação de chave:</span><span class="sxs-lookup"><span data-stu-id="b6759-145">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="b6759-146">Para saber mais, confira [Gerenciar chaves do OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).</span><span class="sxs-lookup"><span data-stu-id="b6759-146">For more information, see [Managing OpenSSH Keys](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

1. <span data-ttu-id="b6759-147">Reinicie o serviço **sshd**.</span><span class="sxs-lookup"><span data-stu-id="b6759-147">Restart the **sshd** service.</span></span>

   ```powershell
   Restart-Service sshd
   ```

1. <span data-ttu-id="b6759-148">Adicione o caminho no qual o OpenSSH está instalado à sua variável de ambiente Path.</span><span class="sxs-lookup"><span data-stu-id="b6759-148">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="b6759-149">Por exemplo, `C:\Program Files\OpenSSH\`.</span><span class="sxs-lookup"><span data-stu-id="b6759-149">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="b6759-150">Essa entrada permite que `ssh.exe` seja localizado.</span><span class="sxs-lookup"><span data-stu-id="b6759-150">This entry allows for the `ssh.exe` to be found.</span></span>

## <a name="set-up-on-an-ubuntu-1604-linux-computer"></a><span data-ttu-id="b6759-151">Configurar em um computador Linux Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="b6759-151">Set up on an Ubuntu 16.04 Linux computer</span></span>

1. <span data-ttu-id="b6759-152">Instale a versão mais recente do PowerShell, confira [Instalar o PowerShell Core no Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span><span class="sxs-lookup"><span data-stu-id="b6759-152">Install the latest version of PowerShell, see [Installing PowerShell Core on Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span></span>
1. <span data-ttu-id="b6759-153">Instale o [Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span><span class="sxs-lookup"><span data-stu-id="b6759-153">Install [Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

1. <span data-ttu-id="b6759-154">Edite o arquivo `sshd_config` no local `/etc/ssh`.</span><span class="sxs-lookup"><span data-stu-id="b6759-154">Edit the `sshd_config` file at location `/etc/ssh`.</span></span>

   <span data-ttu-id="b6759-155">Verifique se a autenticação de senha está habilitada:</span><span class="sxs-lookup"><span data-stu-id="b6759-155">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="b6759-156">Como alternativa, habilite a autenticação de chave:</span><span class="sxs-lookup"><span data-stu-id="b6759-156">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="b6759-157">Para obter mais informações sobre como criar chaves SSH no Ubuntu, confira a página de manual para [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).</span><span class="sxs-lookup"><span data-stu-id="b6759-157">For more information about creating SSH keys on Ubuntu, see the manpage for [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).</span></span>

   <span data-ttu-id="b6759-158">Adicione uma entrada do subsistema PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b6759-158">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="b6759-159">O local padrão do executável do PowerShell é `/usr/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="b6759-159">The default location of the PowerShell executable is `/usr/bin/pwsh`.</span></span> <span data-ttu-id="b6759-160">O local pode variar dependendo de como você instalou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-160">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="b6759-161">Como alternativa, habilite a autenticação de chave:</span><span class="sxs-lookup"><span data-stu-id="b6759-161">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="b6759-162">Reinicie o serviço **ssh**.</span><span class="sxs-lookup"><span data-stu-id="b6759-162">Restart the **ssh** service.</span></span>

   ```bash
   sudo service ssh restart
   ```

## <a name="set-up-on-a-macos-computer"></a><span data-ttu-id="b6759-163">Configurar em um computador macOS</span><span class="sxs-lookup"><span data-stu-id="b6759-163">Set up on a macOS computer</span></span>

1. <span data-ttu-id="b6759-164">Instalar a versão mais recente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-164">Install the latest version of PowerShell.</span></span> <span data-ttu-id="b6759-165">Para obter mais informações, confira [Como instalar o PowerShell Core no macOS](../../install/installing-powershell-core-on-macos.md).</span><span class="sxs-lookup"><span data-stu-id="b6759-165">For more information, [Installing PowerShell Core on macOS](../../install/installing-powershell-core-on-macos.md).</span></span>

   <span data-ttu-id="b6759-166">Verifique se a comunicação remota do SSH está habilitada, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b6759-166">Make sure SSH Remoting is enabled by following these steps:</span></span>

   1. <span data-ttu-id="b6759-167">Abra o `System Preferences`.</span><span class="sxs-lookup"><span data-stu-id="b6759-167">Open `System Preferences`.</span></span>
   1. <span data-ttu-id="b6759-168">Clique em `Sharing`.</span><span class="sxs-lookup"><span data-stu-id="b6759-168">Click on `Sharing`.</span></span>
   1. <span data-ttu-id="b6759-169">Verifique `Remote Login` para definir `Remote Login: On`.</span><span class="sxs-lookup"><span data-stu-id="b6759-169">Check `Remote Login` to set `Remote Login: On`.</span></span>
   1. <span data-ttu-id="b6759-170">Permita o acesso a usuários apropriados.</span><span class="sxs-lookup"><span data-stu-id="b6759-170">Allow access to the appropriate users.</span></span>

1. <span data-ttu-id="b6759-171">Edite o arquivo `sshd_config` no local `/private/etc/ssh/sshd_config`.</span><span class="sxs-lookup"><span data-stu-id="b6759-171">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`.</span></span>

   <span data-ttu-id="b6759-172">Abra um editor de texto, como o **nano**:</span><span class="sxs-lookup"><span data-stu-id="b6759-172">Use a text editor such as **nano**:</span></span>

   ```bash
   sudo nano /private/etc/ssh/sshd_config
   ```

   <span data-ttu-id="b6759-173">Verifique se a autenticação de senha está habilitada:</span><span class="sxs-lookup"><span data-stu-id="b6759-173">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="b6759-174">Adicione uma entrada do subsistema PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b6759-174">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="b6759-175">O local padrão do executável do PowerShell é `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="b6759-175">The default location of the PowerShell executable is `/usr/local/bin/pwsh`.</span></span> <span data-ttu-id="b6759-176">O local pode variar dependendo de como você instalou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-176">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="b6759-177">Como alternativa, habilite a autenticação de chave:</span><span class="sxs-lookup"><span data-stu-id="b6759-177">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="b6759-178">Reinicie o serviço **sshd**.</span><span class="sxs-lookup"><span data-stu-id="b6759-178">Restart the **sshd** service.</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="b6759-179">Autenticação</span><span class="sxs-lookup"><span data-stu-id="b6759-179">Authentication</span></span>

<span data-ttu-id="b6759-180">A comunicação remota do PowerShell por SSH depende da troca de autenticação entre o cliente do SSH e o serviço de SSH; ela própria não implementa nenhum esquema de autenticação.</span><span class="sxs-lookup"><span data-stu-id="b6759-180">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and doesn't implement any authentication schemes itself.</span></span> <span data-ttu-id="b6759-181">Isso significa que os esquemas de autenticação configurada, incluindo a autenticação multifator, são manipulados por SSH e são independentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-181">The result is that any configured authentication schemes including multi-factor authentication are handled by SSH and independent of PowerShell.</span></span> <span data-ttu-id="b6759-182">Por exemplo, é possível configurar o serviço SSH para exigir autenticação de chave pública, bem como uma senha única para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="b6759-182">For example, you can configure the SSH service to require public key authentication and a one-time password for added security.</span></span> <span data-ttu-id="b6759-183">A configuração da autenticação multifator está fora do escopo desta documentação.</span><span class="sxs-lookup"><span data-stu-id="b6759-183">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span> <span data-ttu-id="b6759-184">Consulte a documentação para o SSH sobre como configurar a autenticação multifator corretamente e validar seu trabalho fora do PowerShell antes de tentar usá-la com a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6759-184">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

> [!NOTE]
> <span data-ttu-id="b6759-185">Os usuários mantêm os mesmos privilégios em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="b6759-185">Users retain the same privileges in remote sessions.</span></span> <span data-ttu-id="b6759-186">Isso quer dizer que os administradores têm acesso a um shell elevado, e os usuários normais não terão.</span><span class="sxs-lookup"><span data-stu-id="b6759-186">Meaning, Administrators have access to an elevated shell, and normal users will not.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="b6759-187">Exemplo de comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6759-187">PowerShell remoting example</span></span>

<span data-ttu-id="b6759-188">A maneira mais fácil de testar a comunicação remota é experimentá-la em um único computador.</span><span class="sxs-lookup"><span data-stu-id="b6759-188">The easiest way to test remoting is to try it on a single computer.</span></span> <span data-ttu-id="b6759-189">Neste exemplo, criamos uma sessão remota para o mesmo computador com Linux.</span><span class="sxs-lookup"><span data-stu-id="b6759-189">In this example, we create a remote session back to the same Linux computer.</span></span> <span data-ttu-id="b6759-190">Estamos usando cmdlets do PowerShell de forma interativa para que possamos ver avisos do SSH para verificar o computador host, bem como solicitar uma senha.</span><span class="sxs-lookup"><span data-stu-id="b6759-190">We're using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="b6759-191">É possível fazer a mesma coisa em um computador com Windows para garantir o funcionamento da comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="b6759-191">You can do the same thing on a Windows computer to ensure remoting is working.</span></span> <span data-ttu-id="b6759-192">Em seguida, realize a comunicação remota entre os computadores alterando o nome do host.</span><span class="sxs-lookup"><span data-stu-id="b6759-192">Then, remote between computers by changing the host name.</span></span>

```powershell
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```Output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```Output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```Output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~16.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1
```

```powershell
#
# Linux to Windows
#
Enter-PSSession -HostName WinVM1 -UserName PTestName
```

```
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```Output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```Output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```Output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```Output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```Output
[WinVM2]: PS C:\Users\PSRemoteUser\Documents> $PSVersionTable

Name                           Value
----                           -----
PSEdition                      Core
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
SerializationVersion           1.1.0.1
BuildVersion                   3.0.0.0
CLRVersion
PSVersion                      6.0.0-alpha
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
GitCommitId                    v6.0.0-alpha.17


[WinVM2]: PS C:\Users\PSRemoteUser\Documents>
```

### <a name="limitations"></a><span data-ttu-id="b6759-193">Limitações</span><span class="sxs-lookup"><span data-stu-id="b6759-193">Limitations</span></span>

- <span data-ttu-id="b6759-194">O comando **sudo** não funciona em uma sessão remota para computador com Linux.</span><span class="sxs-lookup"><span data-stu-id="b6759-194">The **sudo** command doesn't work in a remote session to a Linux computer.</span></span>

- <span data-ttu-id="b6759-195">O PSRemoting no SSH não dá suporte a perfis e não tem acesso a `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="b6759-195">PSRemoting over SSH does not support Profiles and does not have access to `$PROFILE`.</span></span> <span data-ttu-id="b6759-196">Estando em uma sessão, você pode carregar um perfil executando dot source dele com o caminho de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="b6759-196">Once in a session, you can load a profile by dot sourcing the profile with the full filepath.</span></span> <span data-ttu-id="b6759-197">Isso não está relacionado aos perfis SSH.</span><span class="sxs-lookup"><span data-stu-id="b6759-197">This is not related to SSH profiles.</span></span> <span data-ttu-id="b6759-198">Você pode configurar o servidor SSH para usar o PowerShell como o shell padrão e carregar um perfil por meio do SSH.</span><span class="sxs-lookup"><span data-stu-id="b6759-198">You can configure the SSH server to use PowerShell as the default shell and to load a profile through SSH.</span></span> <span data-ttu-id="b6759-199">Confira a documentação do SSH para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b6759-199">See the SSH documentation for more information.</span></span>

- <span data-ttu-id="b6759-200">Antes do PowerShell 7.1, a comunicação remota por SSH não dava suporte a sessões remotas de segundo salto.</span><span class="sxs-lookup"><span data-stu-id="b6759-200">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="b6759-201">Essa funcionalidade estava limitada a sessões que usavam o WinRM.</span><span class="sxs-lookup"><span data-stu-id="b6759-201">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="b6759-202">O PowerShell 7.1 permite que `Enter-PSSession` e `Enter-PSHostProcess` funcionem em qualquer sessão remota interativa.</span><span class="sxs-lookup"><span data-stu-id="b6759-202">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6759-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6759-203">See also</span></span>

[<span data-ttu-id="b6759-204">Instalar o PowerShell Core no Linux</span><span class="sxs-lookup"><span data-stu-id="b6759-204">Installing PowerShell Core on Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[<span data-ttu-id="b6759-205">Instalar o PowerShell Core no macOS</span><span class="sxs-lookup"><span data-stu-id="b6759-205">Installing PowerShell Core on macOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="b6759-206">Instalar o PowerShell Core no Windows</span><span class="sxs-lookup"><span data-stu-id="b6759-206">Installing PowerShell Core on Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="b6759-207">Gerenciar o Windows com o OpenSSH</span><span class="sxs-lookup"><span data-stu-id="b6759-207">Manage Windows with OpenSSH</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="b6759-208">Gerenciar chaves do OpenSSH</span><span class="sxs-lookup"><span data-stu-id="b6759-208">Managing OpenSSH Keys</span></span>](/windows-server/administration/openssh/openssh_keymanagement)

[<span data-ttu-id="b6759-209">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="b6759-209">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
