---
description: Descreve como criar e usar um perfil do PowerShell.
keywords: powershell, cmdlet
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: d0457cf485528f675840161383aa24d0f63781fb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195675"
---
# <a name="about-profiles"></a><span data-ttu-id="a4abb-104">Sobre perfis</span><span class="sxs-lookup"><span data-stu-id="a4abb-104">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="a4abb-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a4abb-105">Short Description</span></span>
<span data-ttu-id="a4abb-106">Descreve como criar e usar um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-106">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="a4abb-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a4abb-107">Long Description</span></span>

<span data-ttu-id="a4abb-108">Você pode criar um perfil do PowerShell para personalizar seu ambiente e adicionar elementos específicos da sessão para cada sessão do PowerShell que você iniciar.</span><span class="sxs-lookup"><span data-stu-id="a4abb-108">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="a4abb-109">Um perfil do PowerShell é um script executado quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a4abb-109">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="a4abb-110">Você pode usar o perfil como um script de logon para personalizar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="a4abb-110">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="a4abb-111">Você pode adicionar comandos, aliases, funções, variáveis, snap-ins, módulos e unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-111">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="a4abb-112">Você também pode adicionar outros elementos específicos da sessão ao seu perfil para que eles estejam disponíveis em cada sessão sem a necessidade de importá-los ou recriá-los.</span><span class="sxs-lookup"><span data-stu-id="a4abb-112">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="a4abb-113">O PowerShell dá suporte a vários perfis para usuários e programas de host.</span><span class="sxs-lookup"><span data-stu-id="a4abb-113">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="a4abb-114">No entanto, ele não cria os perfis para você.</span><span class="sxs-lookup"><span data-stu-id="a4abb-114">However, it does not create the profiles for you.</span></span> <span data-ttu-id="a4abb-115">Este tópico descreve os perfis e descreve como criar e manter perfis no seu computador.</span><span class="sxs-lookup"><span data-stu-id="a4abb-115">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="a4abb-116">Ele explica como usar o parâmetro **NoProfile** do console do PowerShell (PowerShell.exe) para iniciar o PowerShell sem nenhum perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-116">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="a4abb-117">E explica o efeito da política de execução do PowerShell em perfis.</span><span class="sxs-lookup"><span data-stu-id="a4abb-117">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="a4abb-118">Os arquivos de perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-118">The Profile Files</span></span>

<span data-ttu-id="a4abb-119">O PowerShell dá suporte a vários arquivos de perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-119">PowerShell supports several profile files.</span></span> <span data-ttu-id="a4abb-120">Além disso, os programas de host do PowerShell podem dar suporte a seus próprios perfis específicos de host.</span><span class="sxs-lookup"><span data-stu-id="a4abb-120">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="a4abb-121">Por exemplo, o console do PowerShell dá suporte aos seguintes arquivos de perfil básicos.</span><span class="sxs-lookup"><span data-stu-id="a4abb-121">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="a4abb-122">Os perfis são listados em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="a4abb-122">The profiles are listed in precedence order.</span></span> <span data-ttu-id="a4abb-123">O primeiro perfil tem a precedência mais alta.</span><span class="sxs-lookup"><span data-stu-id="a4abb-123">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="a4abb-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4abb-124">Description</span></span>               | <span data-ttu-id="a4abb-125">Caminho</span><span class="sxs-lookup"><span data-stu-id="a4abb-125">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="a4abb-126">Todos os usuários, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="a4abb-126">All Users, All Hosts</span></span>      |<span data-ttu-id="a4abb-127">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-127">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="a4abb-128">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-128">All Users, Current Host</span></span>   |<span data-ttu-id="a4abb-129">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-129">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="a4abb-130">Usuário atual, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="a4abb-130">Current User, All Hosts</span></span>   |<span data-ttu-id="a4abb-131">$Home \\ [meus] documentos do \\ PowerShell \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-131">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="a4abb-132">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-132">Current user, Current Host</span></span>|<span data-ttu-id="a4abb-133">$Home \\ [My] Documents \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4abb-133">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="a4abb-134">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-134">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="a4abb-135">Os caminhos de perfil incluem as seguintes variáveis:</span><span class="sxs-lookup"><span data-stu-id="a4abb-135">The profile paths include the following variables:</span></span>

- <span data-ttu-id="a4abb-136">A `$PSHOME` variável, que armazena o diretório de instalação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4abb-136">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="a4abb-137">A `$Home` variável, que armazena o diretório base do usuário atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-137">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="a4abb-138">Além disso, outros programas que hospedam o PowerShell podem dar suporte a seus próprios perfis.</span><span class="sxs-lookup"><span data-stu-id="a4abb-138">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="a4abb-139">Por exemplo, Visual Studio Code dá suporte aos seguintes perfis específicos de host.</span><span class="sxs-lookup"><span data-stu-id="a4abb-139">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="a4abb-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4abb-140">Description</span></span>               | <span data-ttu-id="a4abb-141">Caminho</span><span class="sxs-lookup"><span data-stu-id="a4abb-141">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="a4abb-142">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-142">All users, Current Host</span></span>   |<span data-ttu-id="a4abb-143">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-143">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="a4abb-144">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-144">Current user, Current Host</span></span>|<span data-ttu-id="a4abb-145">$Home \\ [My] Documents \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4abb-145">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="a4abb-146">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="a4abb-146">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="a4abb-147">Na ajuda do PowerShell, o perfil "CurrentUser, host atual" é o perfil mais conhecido como "seu perfil do PowerShell".</span><span class="sxs-lookup"><span data-stu-id="a4abb-147">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="a4abb-148">A variável $PROFILE</span><span class="sxs-lookup"><span data-stu-id="a4abb-148">The $PROFILE variable</span></span>

<span data-ttu-id="a4abb-149">A `$PROFILE` variável automática armazena os caminhos para os perfis do PowerShell que estão disponíveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a4abb-149">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="a4abb-150">Para exibir um caminho de perfil, exiba o valor da `$PROFILE` variável.</span><span class="sxs-lookup"><span data-stu-id="a4abb-150">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="a4abb-151">Você também pode usar a `$PROFILE` variável em um comando para representar um caminho.</span><span class="sxs-lookup"><span data-stu-id="a4abb-151">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="a4abb-152">A `$PROFILE` variável armazena o caminho para o perfil "usuário atual, host atual".</span><span class="sxs-lookup"><span data-stu-id="a4abb-152">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="a4abb-153">Os outros perfis são salvos nas propriedades de observação da `$PROFILE` variável.</span><span class="sxs-lookup"><span data-stu-id="a4abb-153">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="a4abb-154">Por exemplo, a `$PROFILE` variável tem os seguintes valores no console do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-154">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="a4abb-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4abb-155">Description</span></span>                |<span data-ttu-id="a4abb-156">Name</span><span class="sxs-lookup"><span data-stu-id="a4abb-156">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="a4abb-157">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-157">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="a4abb-158">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-158">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="a4abb-159">Usuário atual, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="a4abb-159">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="a4abb-160">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="a4abb-160">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="a4abb-161">Todos os usuários, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="a4abb-161">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="a4abb-162">Como os valores da `$PROFILE` variável são alterados para cada usuário e em cada aplicativo host, certifique-se de exibir os valores das variáveis de perfil em cada aplicativo host do PowerShell que você usa.</span><span class="sxs-lookup"><span data-stu-id="a4abb-162">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="a4abb-163">Para ver os valores atuais da `$PROFILE` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="a4abb-163">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="a4abb-164">Você pode usar a `$PROFILE` variável em muitos comandos.</span><span class="sxs-lookup"><span data-stu-id="a4abb-164">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="a4abb-165">Por exemplo, o comando a seguir abre o perfil "usuário atual, host atual" no bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="a4abb-165">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="a4abb-166">O comando a seguir determina se um perfil "todos os usuários, todos os hosts" foi criado no computador local:</span><span class="sxs-lookup"><span data-stu-id="a4abb-166">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="a4abb-167">Como criar um perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-167">How to create a profile</span></span>

<span data-ttu-id="a4abb-168">Para criar um perfil do PowerShell, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="a4abb-168">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="a4abb-169">Por exemplo, para criar um perfil para o usuário atual no aplicativo host do PowerShell atual, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a4abb-169">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="a4abb-170">Nesse comando, a `If` instrução impede que você substitua um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="a4abb-170">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="a4abb-171">Substitua o valor do \<profile-path\> espaço reservado pelo caminho para o arquivo de perfil que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="a4abb-171">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="a4abb-172">Para criar perfis de "todos os usuários" no Windows Vista e versões posteriores do Windows, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="a4abb-172">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="a4abb-173">Como editar um perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-173">How to edit a profile</span></span>

<span data-ttu-id="a4abb-174">Você pode abrir qualquer perfil do PowerShell em um editor de texto, como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="a4abb-174">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="a4abb-175">Para abrir o perfil do usuário atual no aplicativo host do PowerShell atual no bloco de notas, digite:</span><span class="sxs-lookup"><span data-stu-id="a4abb-175">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="a4abb-176">Para abrir outros perfis, especifique o nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-176">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="a4abb-177">Por exemplo, para abrir o perfil para todos os usuários de todos os aplicativos host, digite:</span><span class="sxs-lookup"><span data-stu-id="a4abb-177">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="a4abb-178">Para aplicar as alterações, salve o arquivo de perfil e reinicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-178">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="a4abb-179">Como escolher um perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-179">How to choose a profile</span></span>

<span data-ttu-id="a4abb-180">Se você usar vários aplicativos host, coloque os itens que você usa em todos os aplicativos host em seu `$PROFILE.CurrentUserAllHosts` perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-180">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="a4abb-181">Coloque os itens que são específicos de um aplicativo host, como um comando que define a cor do plano de fundo de um aplicativo host, em um perfil específico para esse aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="a4abb-181">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="a4abb-182">Se você for um administrador que está Personalizando o PowerShell para muitos usuários, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="a4abb-182">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="a4abb-183">Armazenar os itens comuns no `$PROFILE.AllUsersAllHosts` perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-183">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="a4abb-184">Armazenar itens que são específicos a um aplicativo host em `$PROFILE.AllUsersCurrentHost` perfis que são específicos para o aplicativo host</span><span class="sxs-lookup"><span data-stu-id="a4abb-184">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="a4abb-185">Armazenar itens para usuários específicos nos perfis específicos do usuário</span><span class="sxs-lookup"><span data-stu-id="a4abb-185">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="a4abb-186">Certifique-se de verificar a documentação do aplicativo host para qualquer implementação especial de perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-186">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="a4abb-187">Como usar um perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-187">How to use a profile</span></span>

<span data-ttu-id="a4abb-188">Muitos dos itens que você cria no PowerShell e a maioria dos comandos que você executa afetam apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a4abb-188">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="a4abb-189">Quando você encerra a sessão, os itens são excluídos.</span><span class="sxs-lookup"><span data-stu-id="a4abb-189">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="a4abb-190">Os comandos e itens específicos da sessão incluem variáveis, variáveis de preferência, aliases, funções, comandos (exceto para [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)) e módulos do PowerShell que você adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="a4abb-190">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="a4abb-191">Para salvar esses itens e torná-los disponíveis em todas as sessões futuras, adicione-os a um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-191">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="a4abb-192">Outro uso comum para perfis é salvar funções, aliases e variáveis usadas com frequência.</span><span class="sxs-lookup"><span data-stu-id="a4abb-192">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="a4abb-193">Ao salvar os itens em um perfil, você pode usá-los em qualquer sessão aplicável, sem recriá-los.</span><span class="sxs-lookup"><span data-stu-id="a4abb-193">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="a4abb-194">Como iniciar um perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-194">How to start a profile</span></span>

<span data-ttu-id="a4abb-195">Quando você abre o arquivo de perfil, ele fica em branco.</span><span class="sxs-lookup"><span data-stu-id="a4abb-195">When you open the profile file, it is blank.</span></span> <span data-ttu-id="a4abb-196">No entanto, você pode preenchê-lo com as variáveis, os aliases e os comandos que você usa com frequência.</span><span class="sxs-lookup"><span data-stu-id="a4abb-196">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="a4abb-197">Aqui estão algumas sugestões para você começar.</span><span class="sxs-lookup"><span data-stu-id="a4abb-197">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="a4abb-198">Adicionar comandos que facilitam a abertura do seu perfil</span><span class="sxs-lookup"><span data-stu-id="a4abb-198">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="a4abb-199">Isso é especialmente útil se você usar um perfil diferente do perfil "usuário atual, host atual".</span><span class="sxs-lookup"><span data-stu-id="a4abb-199">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="a4abb-200">Por exemplo, adicione o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a4abb-200">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="a4abb-201">Adicionar uma função que lista os aliases para qualquer cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4abb-201">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="a4abb-202">Personalizar o console</span><span class="sxs-lookup"><span data-stu-id="a4abb-202">Customize your console</span></span>

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="a4abb-203">Adicionar um prompt personalizado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4abb-203">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="a4abb-204">Para obter mais informações sobre o prompt do PowerShell, consulte [about_Prompts](about_Prompts.md).</span><span class="sxs-lookup"><span data-stu-id="a4abb-204">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="a4abb-205">O parâmetro NoProfile</span><span class="sxs-lookup"><span data-stu-id="a4abb-205">The NoProfile parameter</span></span>

<span data-ttu-id="a4abb-206">Para iniciar o PowerShell sem perfis, use o parâmetro **NoProfile** de **PowerShell.exe** , o programa que inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-206">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe** , the program that starts PowerShell.</span></span>

<span data-ttu-id="a4abb-207">Para começar, abra um programa que possa iniciar o PowerShell, como Cmd.exe ou próprio PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4abb-207">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="a4abb-208">Você também pode usar a caixa de diálogo Executar no Windows.</span><span class="sxs-lookup"><span data-stu-id="a4abb-208">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="a4abb-209">Tipo:</span><span class="sxs-lookup"><span data-stu-id="a4abb-209">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="a4abb-210">Para obter uma lista completa dos parâmetros de PowerShell.exe, digite:</span><span class="sxs-lookup"><span data-stu-id="a4abb-210">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="a4abb-211">Perfis e política de execução</span><span class="sxs-lookup"><span data-stu-id="a4abb-211">Profiles and Execution Policy</span></span>

<span data-ttu-id="a4abb-212">A política de execução do PowerShell determina, em parte, se você pode executar scripts e carregar arquivos de configuração, incluindo os perfis.</span><span class="sxs-lookup"><span data-stu-id="a4abb-212">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="a4abb-213">A política de execução **restrita** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="a4abb-213">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="a4abb-214">Ele impede a execução de todos os scripts, incluindo os perfis.</span><span class="sxs-lookup"><span data-stu-id="a4abb-214">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="a4abb-215">Se você usar a política "Restricted", o perfil não é executado e seu conteúdo não é aplicado.</span><span class="sxs-lookup"><span data-stu-id="a4abb-215">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="a4abb-216">Um `Set-ExecutionPolicy` comando define e altera sua política de execução.</span><span class="sxs-lookup"><span data-stu-id="a4abb-216">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="a4abb-217">É um dos poucos comandos que se aplica em todas as sessões do PowerShell porque o valor é salvo no registro.</span><span class="sxs-lookup"><span data-stu-id="a4abb-217">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="a4abb-218">Você não precisa defini-lo ao abrir o console do e não precisa armazenar um `Set-ExecutionPolicy` comando em seu perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-218">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="a4abb-219">Perfis e sessões remotas</span><span class="sxs-lookup"><span data-stu-id="a4abb-219">Profiles and remote sessions</span></span>

<span data-ttu-id="a4abb-220">Os perfis do PowerShell não são executados automaticamente em sessões remotas, portanto, os comandos que os perfis adicionam não estão presentes na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="a4abb-220">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="a4abb-221">Além disso, a `$PROFILE` variável automática não é populada em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="a4abb-221">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="a4abb-222">Para executar um perfil em uma sessão, use o cmdlet [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="a4abb-222">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="a4abb-223">Por exemplo, o comando a seguir executa o perfil "usuário atual, host atual" do computador local na sessão em `$s` .</span><span class="sxs-lookup"><span data-stu-id="a4abb-223">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="a4abb-224">O comando a seguir executa o perfil "usuário atual, host atual" do computador remoto na sessão no `$s` .</span><span class="sxs-lookup"><span data-stu-id="a4abb-224">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="a4abb-225">Como a `$PROFILE` variável não é populada, o comando usa o caminho explícito para o perfil.</span><span class="sxs-lookup"><span data-stu-id="a4abb-225">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="a4abb-226">Usamos o operador de fornecimento de ponto para que o perfil seja executado no escopo atual no computador remoto e não em seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="a4abb-226">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="a4abb-227">Depois de executar esse comando, os comandos que o perfil adiciona à sessão estão disponíveis no `$s` .</span><span class="sxs-lookup"><span data-stu-id="a4abb-227">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4abb-228">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4abb-228">See Also</span></span>

[<span data-ttu-id="a4abb-229">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="a4abb-229">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="a4abb-230">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a4abb-230">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a4abb-231">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="a4abb-231">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="a4abb-232">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="a4abb-232">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="a4abb-233">about_Signing</span><span class="sxs-lookup"><span data-stu-id="a4abb-233">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="a4abb-234">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a4abb-234">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="a4abb-235">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a4abb-235">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="a4abb-236">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a4abb-236">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)
