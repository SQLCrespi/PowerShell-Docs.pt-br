---
description: Descreve como criar e usar um perfil do PowerShell.
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: 7604b8058a731939524769b6e1469b072a7eb2fe
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196176"
---
# <a name="about-profiles"></a><span data-ttu-id="f4112-103">Sobre perfis</span><span class="sxs-lookup"><span data-stu-id="f4112-103">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="f4112-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f4112-104">Short Description</span></span>
<span data-ttu-id="f4112-105">Descreve como criar e usar um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-105">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="f4112-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f4112-106">Long Description</span></span>

<span data-ttu-id="f4112-107">Você pode criar um perfil do PowerShell para personalizar seu ambiente e adicionar elementos específicos da sessão para cada sessão do PowerShell que você iniciar.</span><span class="sxs-lookup"><span data-stu-id="f4112-107">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="f4112-108">Um perfil do PowerShell é um script executado quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="f4112-108">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="f4112-109">Você pode usar o perfil como um script de logon para personalizar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4112-109">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="f4112-110">Você pode adicionar comandos, aliases, funções, variáveis, snap-ins, módulos e unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-110">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="f4112-111">Você também pode adicionar outros elementos específicos da sessão ao seu perfil para que eles estejam disponíveis em cada sessão sem a necessidade de importá-los ou recriá-los.</span><span class="sxs-lookup"><span data-stu-id="f4112-111">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="f4112-112">O PowerShell dá suporte a vários perfis para usuários e programas de host.</span><span class="sxs-lookup"><span data-stu-id="f4112-112">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="f4112-113">No entanto, ele não cria os perfis para você.</span><span class="sxs-lookup"><span data-stu-id="f4112-113">However, it does not create the profiles for you.</span></span> <span data-ttu-id="f4112-114">Este tópico descreve os perfis e descreve como criar e manter perfis no seu computador.</span><span class="sxs-lookup"><span data-stu-id="f4112-114">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="f4112-115">Ele explica como usar o parâmetro **NoProfile** do console do PowerShell (PowerShell.exe) para iniciar o PowerShell sem nenhum perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-115">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="f4112-116">E explica o efeito da política de execução do PowerShell em perfis.</span><span class="sxs-lookup"><span data-stu-id="f4112-116">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="f4112-117">Os arquivos de perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-117">The Profile Files</span></span>

<span data-ttu-id="f4112-118">O PowerShell dá suporte a vários arquivos de perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-118">PowerShell supports several profile files.</span></span> <span data-ttu-id="f4112-119">Além disso, os programas de host do PowerShell podem dar suporte a seus próprios perfis específicos de host.</span><span class="sxs-lookup"><span data-stu-id="f4112-119">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="f4112-120">Por exemplo, o console do PowerShell dá suporte aos seguintes arquivos de perfil básicos.</span><span class="sxs-lookup"><span data-stu-id="f4112-120">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="f4112-121">Os perfis são listados em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="f4112-121">The profiles are listed in precedence order.</span></span> <span data-ttu-id="f4112-122">O primeiro perfil tem a precedência mais alta.</span><span class="sxs-lookup"><span data-stu-id="f4112-122">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="f4112-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4112-123">Description</span></span>               | <span data-ttu-id="f4112-124">Caminho</span><span class="sxs-lookup"><span data-stu-id="f4112-124">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="f4112-125">Todos os usuários, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="f4112-125">All Users, All Hosts</span></span>      |<span data-ttu-id="f4112-126">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-126">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="f4112-127">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-127">All Users, Current Host</span></span>   |<span data-ttu-id="f4112-128">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-128">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="f4112-129">Usuário atual, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="f4112-129">Current User, All Hosts</span></span>   |<span data-ttu-id="f4112-130">$Home \\ [meus] documentos do \\ PowerShell \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-130">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="f4112-131">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-131">Current user, Current Host</span></span>|<span data-ttu-id="f4112-132">$Home \\ [My] Documents \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4112-132">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="f4112-133">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-133">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="f4112-134">Os caminhos de perfil incluem as seguintes variáveis:</span><span class="sxs-lookup"><span data-stu-id="f4112-134">The profile paths include the following variables:</span></span>

- <span data-ttu-id="f4112-135">A `$PSHOME` variável, que armazena o diretório de instalação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4112-135">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="f4112-136">A `$Home` variável, que armazena o diretório base do usuário atual</span><span class="sxs-lookup"><span data-stu-id="f4112-136">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="f4112-137">Além disso, outros programas que hospedam o PowerShell podem dar suporte a seus próprios perfis.</span><span class="sxs-lookup"><span data-stu-id="f4112-137">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="f4112-138">Por exemplo, Visual Studio Code dá suporte aos seguintes perfis específicos de host.</span><span class="sxs-lookup"><span data-stu-id="f4112-138">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="f4112-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4112-139">Description</span></span>               | <span data-ttu-id="f4112-140">Caminho</span><span class="sxs-lookup"><span data-stu-id="f4112-140">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="f4112-141">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-141">All users, Current Host</span></span>   |<span data-ttu-id="f4112-142">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-142">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="f4112-143">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-143">Current user, Current Host</span></span>|<span data-ttu-id="f4112-144">$Home \\ [My] Documents \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4112-144">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="f4112-145">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="f4112-145">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="f4112-146">Na ajuda do PowerShell, o perfil "CurrentUser, host atual" é o perfil mais conhecido como "seu perfil do PowerShell".</span><span class="sxs-lookup"><span data-stu-id="f4112-146">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="f4112-147">A variável $PROFILE</span><span class="sxs-lookup"><span data-stu-id="f4112-147">The $PROFILE variable</span></span>

<span data-ttu-id="f4112-148">A `$PROFILE` variável automática armazena os caminhos para os perfis do PowerShell que estão disponíveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f4112-148">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="f4112-149">Para exibir um caminho de perfil, exiba o valor da `$PROFILE` variável.</span><span class="sxs-lookup"><span data-stu-id="f4112-149">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="f4112-150">Você também pode usar a `$PROFILE` variável em um comando para representar um caminho.</span><span class="sxs-lookup"><span data-stu-id="f4112-150">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="f4112-151">A `$PROFILE` variável armazena o caminho para o perfil "usuário atual, host atual".</span><span class="sxs-lookup"><span data-stu-id="f4112-151">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="f4112-152">Os outros perfis são salvos nas propriedades de observação da `$PROFILE` variável.</span><span class="sxs-lookup"><span data-stu-id="f4112-152">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="f4112-153">Por exemplo, a `$PROFILE` variável tem os seguintes valores no console do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-153">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="f4112-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4112-154">Description</span></span>                |<span data-ttu-id="f4112-155">Nome</span><span class="sxs-lookup"><span data-stu-id="f4112-155">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="f4112-156">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-156">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="f4112-157">Usuário atual, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-157">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="f4112-158">Usuário atual, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="f4112-158">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="f4112-159">Todos os usuários, host atual</span><span class="sxs-lookup"><span data-stu-id="f4112-159">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="f4112-160">Todos os usuários, todos os hosts</span><span class="sxs-lookup"><span data-stu-id="f4112-160">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="f4112-161">Como os valores da `$PROFILE` variável são alterados para cada usuário e em cada aplicativo host, certifique-se de exibir os valores das variáveis de perfil em cada aplicativo host do PowerShell que você usa.</span><span class="sxs-lookup"><span data-stu-id="f4112-161">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="f4112-162">Para ver os valores atuais da `$PROFILE` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="f4112-162">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="f4112-163">Você pode usar a `$PROFILE` variável em muitos comandos.</span><span class="sxs-lookup"><span data-stu-id="f4112-163">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="f4112-164">Por exemplo, o comando a seguir abre o perfil "usuário atual, host atual" no bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="f4112-164">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="f4112-165">O comando a seguir determina se um perfil "todos os usuários, todos os hosts" foi criado no computador local:</span><span class="sxs-lookup"><span data-stu-id="f4112-165">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="f4112-166">Como criar um perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-166">How to create a profile</span></span>

<span data-ttu-id="f4112-167">Para criar um perfil do PowerShell, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="f4112-167">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="f4112-168">Por exemplo, para criar um perfil para o usuário atual no aplicativo host do PowerShell atual, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4112-168">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="f4112-169">Nesse comando, a `If` instrução impede que você substitua um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="f4112-169">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="f4112-170">Substitua o valor do \<profile-path\> espaço reservado pelo caminho para o arquivo de perfil que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="f4112-170">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="f4112-171">Para criar perfis de "todos os usuários" no Windows Vista e versões posteriores do Windows, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="f4112-171">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="f4112-172">Como editar um perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-172">How to edit a profile</span></span>

<span data-ttu-id="f4112-173">Você pode abrir qualquer perfil do PowerShell em um editor de texto, como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="f4112-173">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="f4112-174">Para abrir o perfil do usuário atual no aplicativo host do PowerShell atual no bloco de notas, digite:</span><span class="sxs-lookup"><span data-stu-id="f4112-174">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="f4112-175">Para abrir outros perfis, especifique o nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-175">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="f4112-176">Por exemplo, para abrir o perfil para todos os usuários de todos os aplicativos host, digite:</span><span class="sxs-lookup"><span data-stu-id="f4112-176">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="f4112-177">Para aplicar as alterações, salve o arquivo de perfil e reinicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-177">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="f4112-178">Como escolher um perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-178">How to choose a profile</span></span>

<span data-ttu-id="f4112-179">Se você usar vários aplicativos host, coloque os itens que você usa em todos os aplicativos host em seu `$PROFILE.CurrentUserAllHosts` perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-179">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="f4112-180">Coloque os itens que são específicos de um aplicativo host, como um comando que define a cor do plano de fundo de um aplicativo host, em um perfil específico para esse aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="f4112-180">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="f4112-181">Se você for um administrador que está Personalizando o PowerShell para muitos usuários, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="f4112-181">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="f4112-182">Armazenar os itens comuns no `$PROFILE.AllUsersAllHosts` perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-182">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="f4112-183">Armazenar itens que são específicos a um aplicativo host em `$PROFILE.AllUsersCurrentHost` perfis que são específicos para o aplicativo host</span><span class="sxs-lookup"><span data-stu-id="f4112-183">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="f4112-184">Armazenar itens para usuários específicos nos perfis específicos do usuário</span><span class="sxs-lookup"><span data-stu-id="f4112-184">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="f4112-185">Certifique-se de verificar a documentação do aplicativo host para qualquer implementação especial de perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-185">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="f4112-186">Como usar um perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-186">How to use a profile</span></span>

<span data-ttu-id="f4112-187">Muitos dos itens que você cria no PowerShell e a maioria dos comandos que você executa afetam apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f4112-187">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="f4112-188">Quando você encerra a sessão, os itens são excluídos.</span><span class="sxs-lookup"><span data-stu-id="f4112-188">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="f4112-189">Os comandos e itens específicos da sessão incluem variáveis, variáveis de preferência, aliases, funções, comandos (exceto para [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)) e módulos do PowerShell que você adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="f4112-189">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="f4112-190">Para salvar esses itens e torná-los disponíveis em todas as sessões futuras, adicione-os a um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-190">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="f4112-191">Outro uso comum para perfis é salvar funções, aliases e variáveis usadas com frequência.</span><span class="sxs-lookup"><span data-stu-id="f4112-191">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="f4112-192">Ao salvar os itens em um perfil, você pode usá-los em qualquer sessão aplicável, sem recriá-los.</span><span class="sxs-lookup"><span data-stu-id="f4112-192">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="f4112-193">Como iniciar um perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-193">How to start a profile</span></span>

<span data-ttu-id="f4112-194">Quando você abre o arquivo de perfil, ele fica em branco.</span><span class="sxs-lookup"><span data-stu-id="f4112-194">When you open the profile file, it is blank.</span></span> <span data-ttu-id="f4112-195">No entanto, você pode preenchê-lo com as variáveis, os aliases e os comandos que você usa com frequência.</span><span class="sxs-lookup"><span data-stu-id="f4112-195">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="f4112-196">Aqui estão algumas sugestões para você começar.</span><span class="sxs-lookup"><span data-stu-id="f4112-196">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="f4112-197">Adicionar comandos que facilitam a abertura do seu perfil</span><span class="sxs-lookup"><span data-stu-id="f4112-197">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="f4112-198">Isso é especialmente útil se você usar um perfil diferente do perfil "usuário atual, host atual".</span><span class="sxs-lookup"><span data-stu-id="f4112-198">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="f4112-199">Por exemplo, adicione o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4112-199">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="f4112-200">Adicionar uma função que lista os aliases para qualquer cmdlet</span><span class="sxs-lookup"><span data-stu-id="f4112-200">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="f4112-201">Personalizar o console</span><span class="sxs-lookup"><span data-stu-id="f4112-201">Customize your console</span></span>

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

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="f4112-202">Adicionar um prompt personalizado do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4112-202">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="f4112-203">Para obter mais informações sobre o prompt do PowerShell, consulte [about_Prompts](about_Prompts.md).</span><span class="sxs-lookup"><span data-stu-id="f4112-203">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="f4112-204">O parâmetro NoProfile</span><span class="sxs-lookup"><span data-stu-id="f4112-204">The NoProfile parameter</span></span>

<span data-ttu-id="f4112-205">Para iniciar o PowerShell sem perfis, use o parâmetro **NoProfile** de **PowerShell.exe**, o programa que inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-205">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe**, the program that starts PowerShell.</span></span>

<span data-ttu-id="f4112-206">Para começar, abra um programa que possa iniciar o PowerShell, como Cmd.exe ou próprio PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4112-206">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="f4112-207">Você também pode usar a caixa de diálogo Executar no Windows.</span><span class="sxs-lookup"><span data-stu-id="f4112-207">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="f4112-208">Tipo:</span><span class="sxs-lookup"><span data-stu-id="f4112-208">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="f4112-209">Para obter uma lista completa dos parâmetros de PowerShell.exe, digite:</span><span class="sxs-lookup"><span data-stu-id="f4112-209">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="f4112-210">Perfis e política de execução</span><span class="sxs-lookup"><span data-stu-id="f4112-210">Profiles and Execution Policy</span></span>

<span data-ttu-id="f4112-211">A política de execução do PowerShell determina, em parte, se você pode executar scripts e carregar arquivos de configuração, incluindo os perfis.</span><span class="sxs-lookup"><span data-stu-id="f4112-211">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="f4112-212">A política de execução **restrita** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="f4112-212">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="f4112-213">Ele impede a execução de todos os scripts, incluindo os perfis.</span><span class="sxs-lookup"><span data-stu-id="f4112-213">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="f4112-214">Se você usar a política "Restricted", o perfil não é executado e seu conteúdo não é aplicado.</span><span class="sxs-lookup"><span data-stu-id="f4112-214">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="f4112-215">Um `Set-ExecutionPolicy` comando define e altera sua política de execução.</span><span class="sxs-lookup"><span data-stu-id="f4112-215">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="f4112-216">É um dos poucos comandos que se aplica em todas as sessões do PowerShell porque o valor é salvo no registro.</span><span class="sxs-lookup"><span data-stu-id="f4112-216">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="f4112-217">Você não precisa defini-lo ao abrir o console do e não precisa armazenar um `Set-ExecutionPolicy` comando em seu perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-217">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="f4112-218">Perfis e sessões remotas</span><span class="sxs-lookup"><span data-stu-id="f4112-218">Profiles and remote sessions</span></span>

<span data-ttu-id="f4112-219">Os perfis do PowerShell não são executados automaticamente em sessões remotas, portanto, os comandos que os perfis adicionam não estão presentes na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="f4112-219">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="f4112-220">Além disso, a `$PROFILE` variável automática não é populada em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="f4112-220">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="f4112-221">Para executar um perfil em uma sessão, use o cmdlet [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="f4112-221">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="f4112-222">Por exemplo, o comando a seguir executa o perfil "usuário atual, host atual" do computador local na sessão em `$s` .</span><span class="sxs-lookup"><span data-stu-id="f4112-222">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="f4112-223">O comando a seguir executa o perfil "usuário atual, host atual" do computador remoto na sessão no `$s` .</span><span class="sxs-lookup"><span data-stu-id="f4112-223">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="f4112-224">Como a `$PROFILE` variável não é populada, o comando usa o caminho explícito para o perfil.</span><span class="sxs-lookup"><span data-stu-id="f4112-224">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="f4112-225">Usamos o operador de fornecimento de ponto para que o perfil seja executado no escopo atual no computador remoto e não em seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="f4112-225">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="f4112-226">Depois de executar esse comando, os comandos que o perfil adiciona à sessão estão disponíveis no `$s` .</span><span class="sxs-lookup"><span data-stu-id="f4112-226">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4112-227">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4112-227">See Also</span></span>

[<span data-ttu-id="f4112-228">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="f4112-228">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="f4112-229">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f4112-229">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f4112-230">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="f4112-230">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="f4112-231">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="f4112-231">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="f4112-232">about_Signing</span><span class="sxs-lookup"><span data-stu-id="f4112-232">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="f4112-233">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f4112-233">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="f4112-234">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="f4112-234">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="f4112-235">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f4112-235">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

