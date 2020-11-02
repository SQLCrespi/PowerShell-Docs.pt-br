---
ms.date: 07/17/2020
ms.topic: reference
title: Recurso nxScript de DSC para Linux
description: Recurso nxScript de DSC para Linux
ms.openlocfilehash: c92d7ac76323d39167512734ef743c299857c9a6
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648810"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="148a5-103">Recurso nxScript de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="148a5-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="148a5-104">O recurso **nxScript** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para executar scripts do Linux em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="148a5-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="148a5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="148a5-105">Syntax</span></span>

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="148a5-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="148a5-106">Properties</span></span>

|<span data-ttu-id="148a5-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="148a5-107">Property</span></span> |<span data-ttu-id="148a5-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="148a5-108">Description</span></span> |
|---|---|
|<span data-ttu-id="148a5-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="148a5-109">GetScript</span></span> |<span data-ttu-id="148a5-110">Fornece um script para retornar ao status atual do computador.</span><span class="sxs-lookup"><span data-stu-id="148a5-110">Provides a script to return current status of the machine.</span></span> <span data-ttu-id="148a5-111">Esse script é executado quando você invoca o script [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="148a5-111">This script runs when you invoke the [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="148a5-112">O script precisa começar com um shebang, como `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="148a5-112">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="148a5-113">SetScript</span><span class="sxs-lookup"><span data-stu-id="148a5-113">SetScript</span></span> |<span data-ttu-id="148a5-114">Fornece um script que coloca o computador no estado correto.</span><span class="sxs-lookup"><span data-stu-id="148a5-114">Provides a script that puts the machine in the correct state.</span></span> <span data-ttu-id="148a5-115">Quando você invoca o script [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer), o **TestScript** é executado primeiro.</span><span class="sxs-lookup"><span data-stu-id="148a5-115">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, the **TestScript** runs first.</span></span> <span data-ttu-id="148a5-116">Se o bloco **TestScript** gerar um código de saída diferente de 0, o bloco **SetScript** será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-116">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="148a5-117">Se o **TestScript** gerar um código de saída igual a 0, o **SetScript** não será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-117">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="148a5-118">O script precisa começar com um shebang, como `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="148a5-118">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="148a5-119">TestScript</span><span class="sxs-lookup"><span data-stu-id="148a5-119">TestScript</span></span> |<span data-ttu-id="148a5-120">Fornece um script que avalia se o nó está atualmente no estado correto.</span><span class="sxs-lookup"><span data-stu-id="148a5-120">Provides a script that evaluates whether the node is currently in the correct state.</span></span> <span data-ttu-id="148a5-121">Quando você invoca o script [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer), este script é executado primeiro.</span><span class="sxs-lookup"><span data-stu-id="148a5-121">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, this script runs.</span></span> <span data-ttu-id="148a5-122">Se gerar um código de saída diferente de 0, o **SetScript** será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-122">If it returns an exit code other than 0, the **SetScript** will run.</span></span> <span data-ttu-id="148a5-123">Se gerar um código de saída igual a 0, o **SetScript** não será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-123">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="148a5-124">O **TestScript** também é executado quando você invoca o script [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="148a5-124">The **TestScript** also runs when you invoke the [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="148a5-125">No entanto, nesse caso, o **SetScript** não será executado, não importa qual código de saída é gerado pelo **TestScript** .</span><span class="sxs-lookup"><span data-stu-id="148a5-125">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript** .</span></span> <span data-ttu-id="148a5-126">O **TestScript** deve ter o conteúdo e deverá gerar um código de saída igual a 0, se a configuração real corresponder à configuração atual de estado desejado, e um código de saída diferente de 0, se não corresponder.</span><span class="sxs-lookup"><span data-stu-id="148a5-126">The **TestScript** must contain content and must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="148a5-127">A configuração atual de estado desejado é a última configuração aplicada ao nó que está usando o DSC.</span><span class="sxs-lookup"><span data-stu-id="148a5-127">The current desired state configuration is the last configuration enacted on the node that is using DSC.</span></span> <span data-ttu-id="148a5-128">O script precisa começar com um shebang, como `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="148a5-128">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="148a5-129">Usuário</span><span class="sxs-lookup"><span data-stu-id="148a5-129">User</span></span> |<span data-ttu-id="148a5-130">O usuário com o qual o script será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-130">The user to run the script as.</span></span> |
|<span data-ttu-id="148a5-131">Agrupar</span><span class="sxs-lookup"><span data-stu-id="148a5-131">Group</span></span> |<span data-ttu-id="148a5-132">O grupo com o qual o script será executado.</span><span class="sxs-lookup"><span data-stu-id="148a5-132">The group to run the script as.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="148a5-133">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="148a5-133">Common properties</span></span>

|<span data-ttu-id="148a5-134">Propriedade</span><span class="sxs-lookup"><span data-stu-id="148a5-134">Property</span></span> |<span data-ttu-id="148a5-135">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="148a5-135">Description</span></span> |
|---|---|
|<span data-ttu-id="148a5-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="148a5-136">DependsOn</span></span> |<span data-ttu-id="148a5-137">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="148a5-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="148a5-138">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="148a5-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="example"></a><span data-ttu-id="148a5-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="148a5-139">Example</span></span>

<span data-ttu-id="148a5-140">O exemplo a seguir demonstra o uso do recurso **nxScript** para executar um gerenciamento de configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="148a5-140">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
