---
ms.date: 08/11/2020
keywords: DSC,powershell,configuração,instalação
title: Chamando métodos do recurso DSC diretamente
ms.openlocfilehash: 029a278c938e414820e172b85fac3cb3ad4b4afa
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162487"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="abac1-103">Chamando métodos do recurso DSC diretamente</span><span class="sxs-lookup"><span data-stu-id="abac1-103">Calling DSC resource methods directly</span></span>

><span data-ttu-id="abac1-104">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="abac1-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="abac1-105">Use o cmdlet [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) para chamar diretamente as funções ou os métodos de um recurso de DSC (as funções `Get-TargetResource`, `Set-TargetResource` e `Test-TargetResource` de um recurso baseado em MOF ou os métodos **Get**, **Set** e **Test** de um recurso baseado em classe).</span><span class="sxs-lookup"><span data-stu-id="abac1-105">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get**, **Set**, and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="abac1-106">Isso pode ser usado por terceiros que querem usar recursos DSC, ou como uma ferramenta útil ao desenvolver recursos.</span><span class="sxs-lookup"><span data-stu-id="abac1-106">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="abac1-107">No PowerShell 7.0+, `Invoke-DscResource` não é mais compatível com a invocação de recursos de DSC do WMI.</span><span class="sxs-lookup"><span data-stu-id="abac1-107">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="abac1-108">Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="abac1-108">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="abac1-109">Geralmente, esse cmdlet é usado em combinação com uma propriedade de metaconfiguração `refreshMode = 'Disabled'`, mas pode ser usado, independentemente do **refreshMode** para o qual está definido.</span><span class="sxs-lookup"><span data-stu-id="abac1-109">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="abac1-110">Ao chamar o cmdlet `Invoke-DscResource`, você especifica qual método ou função chamar usando o parâmetro **Method**.</span><span class="sxs-lookup"><span data-stu-id="abac1-110">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="abac1-111">Especifique as propriedades do recurso passando uma tabela de hash como o valor do parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="abac1-111">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="abac1-112">A seguir, exemplos de chamada direta aos métodos do recurso:</span><span class="sxs-lookup"><span data-stu-id="abac1-112">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="abac1-113">Certificar-se de que um arquivo está presente</span><span class="sxs-lookup"><span data-stu-id="abac1-113">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="abac1-114">Testar se um arquivo está presente</span><span class="sxs-lookup"><span data-stu-id="abac1-114">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="abac1-115">Obter o conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="abac1-115">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

>[!NOTE]
> <span data-ttu-id="abac1-116">não é permitido chamar diretamente métodos de recurso de composição.</span><span class="sxs-lookup"><span data-stu-id="abac1-116">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="abac1-117">Em vez disso, chame os métodos de recursos subjacentes que compõem o recurso de composição.</span><span class="sxs-lookup"><span data-stu-id="abac1-117">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="abac1-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="abac1-118">See Also</span></span>

- [<span data-ttu-id="abac1-119">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="abac1-119">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="abac1-120">Escrevendo um recurso personalizado de DSC com classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="abac1-120">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="abac1-121">Depurando os recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="abac1-121">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
