---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recursos File de DSC
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077323"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="2a2a0-103">Recursos File de DSC</span><span class="sxs-lookup"><span data-stu-id="2a2a0-103">DSC File Resource</span></span>

> <span data-ttu-id="2a2a0-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2a2a0-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="2a2a0-105">O recurso File na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar arquivos e pastas no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-105">The File resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="2a2a0-106">O **DestinationPath** e o **SourcePath** devem ser acessíveis pelo nó de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-106">The **DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a2a0-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2a2a0-107">Syntax</span></span>

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a><span data-ttu-id="2a2a0-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2a2a0-108">Properties</span></span>

|<span data-ttu-id="2a2a0-109">Propriedade</span><span class="sxs-lookup"><span data-stu-id="2a2a0-109">Property</span></span>       |<span data-ttu-id="2a2a0-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a2a0-110">Description</span></span>                                                                   |<span data-ttu-id="2a2a0-111">Necessária</span><span class="sxs-lookup"><span data-stu-id="2a2a0-111">Required</span></span>|<span data-ttu-id="2a2a0-112">Padrão</span><span class="sxs-lookup"><span data-stu-id="2a2a0-112">Default</span></span>|
|---------------|------------------------------------------------------------------------------|--------|-------|
|<span data-ttu-id="2a2a0-113">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="2a2a0-113">DestinationPath</span></span>|<span data-ttu-id="2a2a0-114">O local, no nó de destino, que você quer que seja `Present` ou `Absent`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-114">The location, on the target node, you want to ensure is `Present` or `Absent`.</span></span>|<span data-ttu-id="2a2a0-115">Sim</span><span class="sxs-lookup"><span data-stu-id="2a2a0-115">Yes</span></span>|<span data-ttu-id="2a2a0-116">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-116">No</span></span>|
|<span data-ttu-id="2a2a0-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a2a0-117">Attributes</span></span>     |<span data-ttu-id="2a2a0-118">O estado desejado dos atributos para o arquivo ou diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-118">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="2a2a0-119">Os valores válidos são **Archive**, **Hidden**, **ReadOnly** e **System**.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-119">Valid values are **Archive**, **Hidden**, **ReadOnly**, and **System**.</span></span>|<span data-ttu-id="2a2a0-120">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-120">No</span></span>|<span data-ttu-id="2a2a0-121">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-121">None</span></span>|
|<span data-ttu-id="2a2a0-122">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="2a2a0-122">Checksum</span></span>      |<span data-ttu-id="2a2a0-123">O tipo de soma de verificação a usar para determinar se dois arquivos são iguais.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-123">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="2a2a0-124">Os valores válidos incluem: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-124">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.</span></span>|<span data-ttu-id="2a2a0-125">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-125">No</span></span>|<span data-ttu-id="2a2a0-126">Apenas os nomes de arquivo ou de diretório são comparados.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-126">Only the file or directory name is compared.</span></span>|
|<span data-ttu-id="2a2a0-127">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="2a2a0-127">Contents</span></span>       |<span data-ttu-id="2a2a0-128">Válido apenas quando usado com o tipo `File`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-128">Only valid when used with `File` type.</span></span> <span data-ttu-id="2a2a0-129">Indica se o conteúdo a verificar está `Present` ou `Absent` no arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-129">Indicates the contents to Ensure are `Present` or `Absent` from the targeted file.</span></span> |<span data-ttu-id="2a2a0-130">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-130">No</span></span>|<span data-ttu-id="2a2a0-131">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-131">None</span></span>|
|<span data-ttu-id="2a2a0-132">Credential</span><span class="sxs-lookup"><span data-stu-id="2a2a0-132">Credential</span></span>     |<span data-ttu-id="2a2a0-133">As credenciais necessárias para acessar recursos, como arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-133">The credentials that are required to access resources, such as source files.</span></span>|<span data-ttu-id="2a2a0-134">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-134">No</span></span>|<span data-ttu-id="2a2a0-135">A conta do computador do nó de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-135">The target node's Computer Account.</span></span> <span data-ttu-id="2a2a0-136">(*veja a observação*)</span><span class="sxs-lookup"><span data-stu-id="2a2a0-136">(*see note*)</span></span>|
|<span data-ttu-id="2a2a0-137">Ensure</span><span class="sxs-lookup"><span data-stu-id="2a2a0-137">Ensure</span></span>         |<span data-ttu-id="2a2a0-138">O estado desejado do diretório ou arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-138">The desired state of the target file or directory.</span></span> |<span data-ttu-id="2a2a0-139">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-139">No</span></span>|<span data-ttu-id="2a2a0-140">**Presente**</span><span class="sxs-lookup"><span data-stu-id="2a2a0-140">**Present**</span></span>|
|<span data-ttu-id="2a2a0-141">Force</span><span class="sxs-lookup"><span data-stu-id="2a2a0-141">Force</span></span>          |<span data-ttu-id="2a2a0-142">Substitui as operações de acesso que resultariam em erro (como substituir um arquivo ou excluir um diretório que não esteja vazio).</span><span class="sxs-lookup"><span data-stu-id="2a2a0-142">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span>|<span data-ttu-id="2a2a0-143">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-143">No</span></span>|`$false`|
|<span data-ttu-id="2a2a0-144">Recurse</span><span class="sxs-lookup"><span data-stu-id="2a2a0-144">Recurse</span></span>        |<span data-ttu-id="2a2a0-145">Válido apenas quando usado com o tipo `Directory`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-145">Only valid when used with `Directory` type.</span></span> <span data-ttu-id="2a2a0-146">Executa recursivamente a operação de estado em todos os subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-146">Performs the state operation recursively to all subdirectories.</span></span>|<span data-ttu-id="2a2a0-147">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-147">No</span></span>|`$false`|
|<span data-ttu-id="2a2a0-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2a2a0-148">DependsOn</span></span>      |<span data-ttu-id="2a2a0-149">Define uma dependência no(s) recurso(s) especificado(s).</span><span class="sxs-lookup"><span data-stu-id="2a2a0-149">Sets a dependency on specified resource(s).</span></span> <span data-ttu-id="2a2a0-150">Este recurso só será executado após a execução bem-sucedida de todos os recursos dependentes.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-150">This resource will only execute after successful execution of any dependent resources.</span></span> <span data-ttu-id="2a2a0-151">Você pode especificar os recursos dependentes usando a sintaxe `"[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-151">You can specify dependent resources using the syntax `"[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="2a2a0-152">Consulte [about_DependsOn](../../../configurations/resource-depends-on.md)</span><span class="sxs-lookup"><span data-stu-id="2a2a0-152">See [about_DependsOn](../../../configurations/resource-depends-on.md)</span></span>|<span data-ttu-id="2a2a0-153">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-153">No</span></span>|<span data-ttu-id="2a2a0-154">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-154">None</span></span>|
|<span data-ttu-id="2a2a0-155">SourcePath</span><span class="sxs-lookup"><span data-stu-id="2a2a0-155">SourcePath</span></span>     |<span data-ttu-id="2a2a0-156">O caminho do qual o recurso de arquivo ou pasta deve ser copiado.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-156">The path from which to copy the file or folder resource.</span></span>|<span data-ttu-id="2a2a0-157">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-157">No</span></span>|<span data-ttu-id="2a2a0-158">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-158">None</span></span>|
|<span data-ttu-id="2a2a0-159">Tipo</span><span class="sxs-lookup"><span data-stu-id="2a2a0-159">Type</span></span>           |<span data-ttu-id="2a2a0-160">O tipo de recurso que está sendo configurado.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-160">The type of resource being configured.</span></span> <span data-ttu-id="2a2a0-161">Os valores válidos são `Directory` e `File`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-161">Valid values are `Directory` and `File`.</span></span>|<span data-ttu-id="2a2a0-162">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-162">No</span></span>|`File`|
|<span data-ttu-id="2a2a0-163">MatchSource</span><span class="sxs-lookup"><span data-stu-id="2a2a0-163">MatchSource</span></span>    |<span data-ttu-id="2a2a0-164">Determina se o recurso deve monitorar novos arquivos adicionados ao diretório de origem após a cópia inicial.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-164">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="2a2a0-165">Um valor `$true` indica que, após a cópia inicial, os novos arquivos de origem devem ser copiados para o destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-165">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="2a2a0-166">Se for definido como `$False`, o recurso armazena em cache o conteúdo do diretório de origem e ignora todos os arquivos adicionados após a cópia inicial.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-166">If set to `$False`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span>|<span data-ttu-id="2a2a0-167">Não</span><span class="sxs-lookup"><span data-stu-id="2a2a0-167">No</span></span>|`$false`|

> [!WARNING]
> <span data-ttu-id="2a2a0-168">Se você não especificar um valor para `Credential` ou `PSRunAsCredential` (PS V.5), o recurso usará a conta de computador do nó de destino para acessar o `SourcePath`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-168">If you do not specify a value for `Credential` or `PSRunAsCredential` (PS V.5), the resource will use the computer account of the target node to access the `SourcePath`.</span></span>  <span data-ttu-id="2a2a0-169">Quando o `SourcePath` é um compartilhamento UNC, isso pode resultar em um erro "Acesso negado".</span><span class="sxs-lookup"><span data-stu-id="2a2a0-169">When the `SourcePath` is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="2a2a0-170">Verifique se suas permissões estão definidas adequadamente ou use as propriedades `Credential` ou `PSRunAsCredential` para especificar a conta que deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-170">Please ensure your permissions are set accordingly, or use the `Credential` or `PSRunAsCredential` properties to specify the account that should be used.</span></span>

## <a name="present-vs-absent"></a><span data-ttu-id="2a2a0-171">Present versus Absent</span><span class="sxs-lookup"><span data-stu-id="2a2a0-171">Present vs. Absent</span></span>

<span data-ttu-id="2a2a0-172">Cada recurso DSC executa operações diferentes com base no valor especificado para a propriedade `Ensure`.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-172">Each DSC resource performs different operations based on the value you specify for the `Ensure` property.</span></span> <span data-ttu-id="2a2a0-173">Os valores especificados para as propriedades acima determinam a operação de estado executada.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-173">The values you specify for the above properties determines the state operation performed.</span></span>

### <a name="existence"></a><span data-ttu-id="2a2a0-174">Existência</span><span class="sxs-lookup"><span data-stu-id="2a2a0-174">Existence</span></span>

<span data-ttu-id="2a2a0-175">Ao especificar apenas um `DestinationPath`, o recurso garante que o caminho existe (`Present`) ou não existe (`Absent`).</span><span class="sxs-lookup"><span data-stu-id="2a2a0-175">When you only specify a `DestinationPath`, the resource ensures that the path exists (`Present`) or does not exist (`Absent`).</span></span>

### <a name="copy-operations"></a><span data-ttu-id="2a2a0-176">Operações de cópia</span><span class="sxs-lookup"><span data-stu-id="2a2a0-176">Copy Operations</span></span>

<span data-ttu-id="2a2a0-177">Quando você especifica um `SourcePath` e um `DestinationPath` com um valor `Type` do **Diretório**, o recurso copia o diretório de origem para o caminho de destino.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-177">When you specify a `SourcePath` and a `DestinationPath` with a `Type` value of **Directory**, the resource copies source directory to the destination path.</span></span> <span data-ttu-id="2a2a0-178">As propriedades `Recurse`, `Force` e `MatchSource` alteram o tipo de operação de cópia executada, embora `Credential` determine qual conta usar para acessar o diretório de origem.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-178">The properties `Recurse`, `Force`, and `MatchSource` change the type of copy operation performed, while `Credential` determines which account to use to access the source directory.</span></span>

### <a name="limitations"></a><span data-ttu-id="2a2a0-179">Limitações</span><span class="sxs-lookup"><span data-stu-id="2a2a0-179">Limitations</span></span>

<span data-ttu-id="2a2a0-180">Se você tiver especificado um valor `ReadOnly` para a propriedade `Attributes` com um `DestinationPath`, `Ensure = "Present"` criará o caminho especificado, enquanto `Contents` definirá o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-180">If you specified a value of `ReadOnly` for the `Attributes` property alongside a `DestinationPath`, `Ensure = "Present"` would create the path specified, while `Contents` would set the contents of the file.</span></span>  <span data-ttu-id="2a2a0-181">Uma operação de estado `Absent` ignoraria completamente a propriedade `Attributes` e removeria qualquer arquivo no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-181">An `Absent` state operation would ignore the `Attributes` property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="2a2a0-182">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2a2a0-182">Example</span></span>

<span data-ttu-id="2a2a0-183">O exemplo a seguir copia um diretório e seus subdiretórios de um servidor de pull para um nó de destino usando o recurso de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-183">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="2a2a0-184">Se a operação for bem-sucedida, o recurso de Log gravará uma mensagem de confirmação no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-184">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="2a2a0-185">O diretório de origem é um caminho UNC (`\\PullServer\DemoSource`) compartilhado do servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-185">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="2a2a0-186">A propriedade `Recurse` garante que todos os subdiretórios também sejam copiados.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-186">The `Recurse` property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a2a0-187">O LCM no nó de destino é executado no contexto da conta do sistema local por padrão.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-187">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="2a2a0-188">Para conceder acesso ao **SourcePath**, dê à conta do computador do nó de destino as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-188">To grant access to the **SourcePath**, give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="2a2a0-189">**Credential** e **PSDSCRunAsCredential** (v5) alteram o contexto que o LCM usa para acessar o **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-189">The **Credential** and **PSDSCRunAsCredential** (v5) both change the context the LCM uses to access the **SourcePath**.</span></span> <span data-ttu-id="2a2a0-190">Você ainda precisa conceder acesso à conta a ser usada para acessar o **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="2a2a0-190">You still need to grant access to the account that will be used to access the **SourcePath**.</span></span>

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

<span data-ttu-id="2a2a0-191">Para saber mais sobre como usar **Credentials** no DSC, confira [Executar como usuário](../../../configurations/runAsUser.md) ou [Configurar credenciais de dados](../../../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="2a2a0-191">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>
