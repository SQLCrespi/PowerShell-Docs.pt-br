---
ms.date: 08/11/2020
keywords: DSC,powershell,configuração,instalação
title: Chamando métodos do recurso DSC diretamente
description: O cmdlet Invoke-DscResource pode ser usado para chamar as funções ou os métodos de um recurso de DSC. Ele pode ser usado por terceiros que queiram usar recursos de DSC ou como uma ferramenta útil ao desenvolver recursos.
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650996"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="35f29-105">Chamando métodos do recurso DSC diretamente</span><span class="sxs-lookup"><span data-stu-id="35f29-105">Calling DSC resource methods directly</span></span>

> <span data-ttu-id="35f29-106">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="35f29-106">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="35f29-107">Use o cmdlet [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) para chamar diretamente as funções ou os métodos de um recurso de DSC (as funções `Get-TargetResource`, `Set-TargetResource` e `Test-TargetResource` de um recurso baseado em MOF ou os métodos **Get** , **Set** e **Test** de um recurso baseado em classe).</span><span class="sxs-lookup"><span data-stu-id="35f29-107">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get** , **Set** , and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="35f29-108">Isso pode ser usado por terceiros que querem usar recursos DSC, ou como uma ferramenta útil ao desenvolver recursos.</span><span class="sxs-lookup"><span data-stu-id="35f29-108">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="35f29-109">No PowerShell 7.0+, `Invoke-DscResource` não é mais compatível com a invocação de recursos de DSC do WMI.</span><span class="sxs-lookup"><span data-stu-id="35f29-109">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="35f29-110">Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="35f29-110">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="35f29-111">Geralmente, esse cmdlet é usado em combinação com uma propriedade de metaconfiguração `refreshMode = 'Disabled'`, mas pode ser usado, independentemente do **refreshMode** para o qual está definido.</span><span class="sxs-lookup"><span data-stu-id="35f29-111">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="35f29-112">Ao chamar o cmdlet `Invoke-DscResource`, você especifica qual método ou função chamar usando o parâmetro **Method**.</span><span class="sxs-lookup"><span data-stu-id="35f29-112">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="35f29-113">Especifique as propriedades do recurso passando uma tabela de hash como o valor do parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="35f29-113">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="35f29-114">A seguir, exemplos de chamada direta aos métodos do recurso:</span><span class="sxs-lookup"><span data-stu-id="35f29-114">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="35f29-115">Certificar-se de que um arquivo está presente</span><span class="sxs-lookup"><span data-stu-id="35f29-115">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="35f29-116">Testar se um arquivo está presente</span><span class="sxs-lookup"><span data-stu-id="35f29-116">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="35f29-117">Obter o conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="35f29-117">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> <span data-ttu-id="35f29-118">não é permitido chamar diretamente métodos de recurso de composição.</span><span class="sxs-lookup"><span data-stu-id="35f29-118">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="35f29-119">Em vez disso, chame os métodos de recursos subjacentes que compõem o recurso de composição.</span><span class="sxs-lookup"><span data-stu-id="35f29-119">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="35f29-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35f29-120">See Also</span></span>

- [<span data-ttu-id="35f29-121">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="35f29-121">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="35f29-122">Escrevendo um recurso personalizado de DSC com classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="35f29-122">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="35f29-123">Depurando os recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="35f29-123">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
