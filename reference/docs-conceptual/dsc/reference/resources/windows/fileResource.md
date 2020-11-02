---
ms.date: 07/16/2020
ms.topic: reference
title: Recursos File de DSC
description: Recursos File de DSC
ms.openlocfilehash: b62b9b80beb1f433715b32b41445dd0a8bb19d84
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142932"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="cae9b-103">Recursos File de DSC</span><span class="sxs-lookup"><span data-stu-id="cae9b-103">DSC File Resource</span></span>

> <span data-ttu-id="cae9b-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="cae9b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="cae9b-105">O recurso **File** no DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para gerenciar arquivos e pastas no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-105">The **File** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="cae9b-106">O **DestinationPath** e o **SourcePath** devem ser acessíveis pelo nó de destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-106">**DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="cae9b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cae9b-107">Syntax</span></span>

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="cae9b-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="cae9b-108">Properties</span></span>

|<span data-ttu-id="cae9b-109">Propriedade</span><span class="sxs-lookup"><span data-stu-id="cae9b-109">Property</span></span> |<span data-ttu-id="cae9b-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="cae9b-110">Description</span></span> |
|---|---|
|<span data-ttu-id="cae9b-111">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="cae9b-111">DestinationPath</span></span> |<span data-ttu-id="cae9b-112">O local, no nó de destino, que você quer que seja **Present** ou **Absent** com **Ensure** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-112">The location, on the target node, you want to ensure is **Present** or **Absent** with **Ensure** .</span></span> |
|<span data-ttu-id="cae9b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cae9b-113">Attributes</span></span> |<span data-ttu-id="cae9b-114">O estado desejado dos atributos para o arquivo ou diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-114">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="cae9b-115">Os valores válidos são _Archive_ , _Hidden_ , _ReadOnly_ e _System_ .</span><span class="sxs-lookup"><span data-stu-id="cae9b-115">Valid values are _Archive_ , _Hidden_ , _ReadOnly_ , and _System_ .</span></span> |
|<span data-ttu-id="cae9b-116">Checksum (soma de verificação)</span><span class="sxs-lookup"><span data-stu-id="cae9b-116">Checksum</span></span> |<span data-ttu-id="cae9b-117">O tipo de soma de verificação a usar para determinar se dois arquivos são iguais.</span><span class="sxs-lookup"><span data-stu-id="cae9b-117">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="cae9b-118">Os valores válidos incluem: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-118">Valid values include: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span></span> |
|<span data-ttu-id="cae9b-119">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="cae9b-119">Contents</span></span> |<span data-ttu-id="cae9b-120">Válido apenas quando usado com o **Type** **File** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-120">Only valid when used with **Type** **File** .</span></span> <span data-ttu-id="cae9b-121">Indica se o conteúdo a **Ensure** está **Present** ou **Absent** no arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-121">Indicates the contents to **Ensure** are **Present** or **Absent** from the targeted file.</span></span> |
|<span data-ttu-id="cae9b-122">Credencial</span><span class="sxs-lookup"><span data-stu-id="cae9b-122">Credential</span></span> |<span data-ttu-id="cae9b-123">As credenciais necessárias para acessar recursos, como arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="cae9b-123">The credentials that are required to access resources, such as source files.</span></span> |
|<span data-ttu-id="cae9b-124">Force</span><span class="sxs-lookup"><span data-stu-id="cae9b-124">Force</span></span> |<span data-ttu-id="cae9b-125">Substitui as operações de acesso que resultariam em erro (como substituir um arquivo ou excluir um diretório que não esteja vazio).</span><span class="sxs-lookup"><span data-stu-id="cae9b-125">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span> <span data-ttu-id="cae9b-126">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="cae9b-126">Default value is `$false`.</span></span> |
|<span data-ttu-id="cae9b-127">Recurse</span><span class="sxs-lookup"><span data-stu-id="cae9b-127">Recurse</span></span> |<span data-ttu-id="cae9b-128">Válido apenas quando usado com o **Type** **Directory** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-128">Only valid when used with **Type** **Directory** .</span></span> <span data-ttu-id="cae9b-129">Executa a operação de estado recursivamente para todo o conteúdo do diretório, subdiretórios e conteúdo de subdiretório.</span><span class="sxs-lookup"><span data-stu-id="cae9b-129">Performs the state operation recursively to all directory content, subdirectories, and subdirectory content.</span></span> <span data-ttu-id="cae9b-130">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="cae9b-130">Default value is `$false`.</span></span> |
|<span data-ttu-id="cae9b-131">SourcePath</span><span class="sxs-lookup"><span data-stu-id="cae9b-131">SourcePath</span></span> |<span data-ttu-id="cae9b-132">O caminho do qual o recurso de arquivo ou pasta deve ser copiado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-132">The path from which to copy the file or folder resource.</span></span> |
|<span data-ttu-id="cae9b-133">Type</span><span class="sxs-lookup"><span data-stu-id="cae9b-133">Type</span></span> |<span data-ttu-id="cae9b-134">O tipo de recurso que está sendo configurado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-134">The type of resource being configured.</span></span> <span data-ttu-id="cae9b-135">Os valores válidos são **Directory** e **File** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-135">Valid values are **Directory** and **File** .</span></span> <span data-ttu-id="cae9b-136">O valor padrão é **File** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-136">Default value is **File** .</span></span> |
|<span data-ttu-id="cae9b-137">MatchSource</span><span class="sxs-lookup"><span data-stu-id="cae9b-137">MatchSource</span></span> |<span data-ttu-id="cae9b-138">Determina se o recurso deve monitorar novos arquivos adicionados ao diretório de origem após a cópia inicial.</span><span class="sxs-lookup"><span data-stu-id="cae9b-138">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="cae9b-139">Um valor `$true` indica que, após a cópia inicial, os novos arquivos de origem devem ser copiados para o destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-139">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="cae9b-140">Se for definido como `$false`, o recurso armazena em cache o conteúdo do diretório de origem e ignora todos os arquivos adicionados após a cópia inicial.</span><span class="sxs-lookup"><span data-stu-id="cae9b-140">If set to `$false`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span> <span data-ttu-id="cae9b-141">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="cae9b-141">Default value is `$false`.</span></span> |

> [!WARNING]
> <span data-ttu-id="cae9b-142">Se você não especificar um valor para **Credential** ou **PSRunAsCredential** , o recurso usará a conta de computador do nó de destino para acessar o **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-142">If you do not specify a value for **Credential** or **PSRunAsCredential** , the resource will use the computer account of the target node to access the **SourcePath** .</span></span> <span data-ttu-id="cae9b-143">Quando o **SourcePath** é um compartilhamento UNC, isso pode resultar em um erro "Acesso negado".</span><span class="sxs-lookup"><span data-stu-id="cae9b-143">When the **SourcePath** is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="cae9b-144">Verifique se suas permissões estão definidas adequadamente ou use as propriedades **Credential** ou **PSRunAsCredential** para especificar a conta que deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="cae9b-144">Please ensure your permissions are set accordingly, or use the **Credential** or **PSRunAsCredential** properties to specify the account that should be used.</span></span>

## <a name="common-properties"></a><span data-ttu-id="cae9b-145">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="cae9b-145">Common properties</span></span>

|<span data-ttu-id="cae9b-146">Propriedade</span><span class="sxs-lookup"><span data-stu-id="cae9b-146">Property</span></span> |<span data-ttu-id="cae9b-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="cae9b-147">Description</span></span> |
|---|---|
|<span data-ttu-id="cae9b-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="cae9b-148">DependsOn</span></span> |<span data-ttu-id="cae9b-149">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="cae9b-150">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="cae9b-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="cae9b-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="cae9b-151">Ensure</span></span> |<span data-ttu-id="cae9b-152">Determina se o arquivo e **Contents** em **Destination** devem existir ou não.</span><span class="sxs-lookup"><span data-stu-id="cae9b-152">Determines whether the file and **Contents** at the **Destination** should exist or not.</span></span> <span data-ttu-id="cae9b-153">Defina essa propriedade como **Present** para garantir que o arquivo exista.</span><span class="sxs-lookup"><span data-stu-id="cae9b-153">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="cae9b-154">Defina-a como **Absent** para garantir que não exista.</span><span class="sxs-lookup"><span data-stu-id="cae9b-154">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="cae9b-155">O valor padrão é **Present** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-155">The default value is **Present** .</span></span> |
|<span data-ttu-id="cae9b-156">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="cae9b-156">PsDscRunAsCredential</span></span> |<span data-ttu-id="cae9b-157">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="cae9b-157">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="cae9b-158">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="cae9b-158">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="cae9b-159">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="cae9b-159">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="cae9b-160">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="cae9b-160">Additional information</span></span>

- <span data-ttu-id="cae9b-161">Ao especificar apenas um **DestinationPath** , o recurso garante que o caminho existe caso seja **Present** ou se não existe caso seja **Absent** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-161">When you only specify a **DestinationPath** , the resource ensures that the path exists if **Present** or does not exist if **Absent** .</span></span>
- <span data-ttu-id="cae9b-162">Quando você especifica um **SourcePath** e um **DestinationPath** com um valor **Type** do **Diretório** , o recurso copia o diretório de origem para o caminho de destino.</span><span class="sxs-lookup"><span data-stu-id="cae9b-162">When you specify a **SourcePath** and a **DestinationPath** with a **Type** value of **Directory** , the resource copies source directory to the destination path.</span></span> <span data-ttu-id="cae9b-163">As propriedades **Recurse** , **Force** e **MatchSource** alteram o tipo de operação de cópia executada, embora **Credential** determine qual conta usar para acessar o diretório de origem.</span><span class="sxs-lookup"><span data-stu-id="cae9b-163">The properties **Recurse** , **Force** , and **MatchSource** change the type of copy operation performed, while **Credential** determines which account to use to access the source directory.</span></span>
- <span data-ttu-id="cae9b-164">Se você não definir a propriedade **Recurse** como `$true` ao copiar um diretório, nenhum dos conteúdos do diretório existente será copiado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-164">If you do not set the **Recurse** property to `$true` when copying a directory, none of the contents of the existing directory will be copied.</span></span> <span data-ttu-id="cae9b-165">Somente o diretório especificado será copiado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-165">Only the directory specified will be copied.</span></span>
- <span data-ttu-id="cae9b-166">Se você tiver especificado um valor de **ReadOnly** para a propriedade **Attributes** junto com um **DestinationPath** , **Ensure** **Present** criarão o caminho especificado, enquanto **Contents** definirá o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="cae9b-166">If you specified a value of **ReadOnly** for the **Attributes** property alongside a **DestinationPath** , **Ensure** **Present** would create the path specified, while **Contents** would set the contents of the file.</span></span> <span data-ttu-id="cae9b-167">Uma configuração **Ensure** **Absent** ignoraria a propriedade **Attributes** completamente e removeria qualquer arquivo no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="cae9b-167">An **Ensure** **Absent** setting would ignore the **Attributes** property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="cae9b-168">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cae9b-168">Example</span></span>

<span data-ttu-id="cae9b-169">O exemplo a seguir copia um diretório e seus subdiretórios de um servidor de pull para um nó de destino usando o recurso de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cae9b-169">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="cae9b-170">Se a operação for bem-sucedida, o recurso de Log gravará uma mensagem de confirmação no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="cae9b-170">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="cae9b-171">O diretório de origem é um caminho UNC (`\\PullServer\DemoSource`) compartilhado do servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="cae9b-171">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="cae9b-172">A propriedade **Recurse** garante que todos os subdiretórios também sejam copiados.</span><span class="sxs-lookup"><span data-stu-id="cae9b-172">The **Recurse** property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cae9b-173">O LCM no nó de destino é executado no contexto da conta do sistema local por padrão.</span><span class="sxs-lookup"><span data-stu-id="cae9b-173">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="cae9b-174">Para conceder acesso ao **SourcePath** , dê à conta do computador do nó de destino as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="cae9b-174">To grant access to the **SourcePath** , give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="cae9b-175">**Credential** e **PSDSCRunAsCredential** alteram o contexto que o LCM usa para acessar o **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-175">The **Credential** and **PSDSCRunAsCredential** both change the context the LCM uses to access the **SourcePath** .</span></span> <span data-ttu-id="cae9b-176">Você ainda precisa conceder acesso à conta a ser usada para acessar o **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="cae9b-176">You still need to grant access to the account that will be used to access the **SourcePath** .</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

<span data-ttu-id="cae9b-177">Para saber mais sobre como usar **Credentials** no DSC, confira [Executar como usuário](../../../configurations/runAsUser.md) ou [Configurar credenciais de dados](../../../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="cae9b-177">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>
