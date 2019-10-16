---
title: Modificando o caminho de instalação do PSModulePath | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360665"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="de990-102">Modificar o caminho de instalação PSModulePath</span><span class="sxs-lookup"><span data-stu-id="de990-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="de990-103">A variável de ambiente `PSModulePath` armazena os caminhos para os locais dos módulos que estão instalados no disco.</span><span class="sxs-lookup"><span data-stu-id="de990-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="de990-104">O Windows PowerShell usa essa variável para localizar módulos quando o usuário não especifica o caminho completo de um módulo.</span><span class="sxs-lookup"><span data-stu-id="de990-104">Windows PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="de990-105">Os caminhos nessa variável são pesquisados na ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="de990-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="de990-106">Quando o Windows PowerShell é iniciado, `PSModulePath` é criado como uma variável de ambiente do sistema com o seguinte valor padrão: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="de990-106">When Windows PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="de990-107">Para exibir a variável PSModulePath</span><span class="sxs-lookup"><span data-stu-id="de990-107">To view the PSModulePath variable</span></span>

<span data-ttu-id="de990-108">Para exibir os caminhos especificados na variável `PSModulePath`, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="de990-108">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="de990-109">Para adicionar locais à variável PSModulePath</span><span class="sxs-lookup"><span data-stu-id="de990-109">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="de990-110">Para adicionar caminhos a essa variável, use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="de990-110">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="de990-111">Para adicionar um valor temporário que está disponível somente para a sessão atual, execute o seguinte comando na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="de990-111">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- <span data-ttu-id="de990-112">Para adicionar um valor persistente que esteja disponível sempre que uma sessão for aberta, adicione o seguinte comando a um perfil do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="de990-112">To add a persistent value that is available whenever a session is opened, add the following command to a Windows PowerShell profile:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  <span data-ttu-id="de990-113">Para obter mais informações sobre perfis, consulte [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) na biblioteca do Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="de990-113">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) in the Microsoft TechNet library.</span></span>

- <span data-ttu-id="de990-114">Para adicionar uma variável persistente ao registro, crie uma nova variável de ambiente de usuário chamada `PSModulePath` usando o editor de variáveis de ambiente na caixa de diálogo **Propriedades do sistema** .</span><span class="sxs-lookup"><span data-stu-id="de990-114">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="de990-115">Para adicionar uma variável persistente usando um script, use o método **SetEnvironmentVariable não** na classe Environment.</span><span class="sxs-lookup"><span data-stu-id="de990-115">To add a persistent variable by using a script, use the **SetEnvironmentVariable** method on the Environment class.</span></span> <span data-ttu-id="de990-116">Por exemplo, o script a seguir adiciona o "C:\Arquivos de Files\Fabrikam\Module caminho ao valor da variável de ambiente PSModulePath para o computador.</span><span class="sxs-lookup"><span data-stu-id="de990-116">For example, the following script adds the "C:\Program Files\Fabrikam\Module path to the value of the PSModulePath environment variable for the computer.</span></span> <span data-ttu-id="de990-117">Para adicionar o caminho para a variável de ambiente PSModulePath do usuário, defina o destino como "usuário".</span><span class="sxs-lookup"><span data-stu-id="de990-117">To add the path to the user PSModulePath environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="de990-118">Para remover locais do PSModulePath</span><span class="sxs-lookup"><span data-stu-id="de990-118">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="de990-119">Você pode remover caminhos da variável usando métodos semelhantes: por exemplo, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` removerá o caminho **c:\ModulePath** da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="de990-119">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="de990-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de990-120">See Also</span></span>

[<span data-ttu-id="de990-121">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de990-121">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
