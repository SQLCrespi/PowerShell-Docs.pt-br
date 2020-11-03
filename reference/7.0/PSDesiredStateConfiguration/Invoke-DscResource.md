---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 4703586008d9044ae68fd7375db65f0d0a9b9980
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "93195216"
---
# <span data-ttu-id="b5441-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="b5441-103">Invoke-DscResource</span></span>

## <span data-ttu-id="b5441-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b5441-104">SYNOPSIS</span></span>
<span data-ttu-id="b5441-105">Executa um método de um recurso de configuração de estado desejado (DSC) do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="b5441-105">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="b5441-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5441-106">SYNTAX</span></span>

```
Invoke-DscResource [[-Method] <Object>] [[-Name] <Object>] [[-Property] <Object>]
 [[-ModuleName] <Object>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="b5441-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5441-107">DESCRIPTION</span></span>

<span data-ttu-id="b5441-108">O cmdlet `Invoke-DscResource` executa um método de um recurso de DSC (Desired State Configuration) do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="b5441-108">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="b5441-109">Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="b5441-109">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="b5441-110">Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows ou o Linux usando recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="b5441-110">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="b5441-111">Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC está em execução com a depuração habilitada.</span><span class="sxs-lookup"><span data-stu-id="b5441-111">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="b5441-112">`Invoke-DscResource` é um recurso experimental no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="b5441-112">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="b5441-113">Para usar o cmdlet, você deve habilitá-lo usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5441-113">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="b5441-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b5441-114">EXAMPLES</span></span>

### <span data-ttu-id="b5441-115">Exemplo 1: invocar o método set de um recurso especificando suas propriedades obrigatórias</span><span class="sxs-lookup"><span data-stu-id="b5441-115">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="b5441-116">Este exemplo invoca o método **set** de um recurso chamado **WindowsProcess** e fornece as propriedades de **caminho** e **argumentos** obrigatórios para iniciar o processo do Windows especificado.</span><span class="sxs-lookup"><span data-stu-id="b5441-116">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="b5441-117">Exemplo 2: invocar o método de teste de um recurso para um módulo especificado</span><span class="sxs-lookup"><span data-stu-id="b5441-117">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="b5441-118">Este exemplo invoca o método de **teste** de um recurso chamado **WindowsProcess** , que está no módulo chamado **PSDesiredStateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b5441-118">This example invokes the **Test** method of a resource named **WindowsProcess** , which is in the module named **PSDesiredStateConfiguration** .</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="b5441-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5441-119">PARAMETERS</span></span>

### <span data-ttu-id="b5441-120">-Método</span><span class="sxs-lookup"><span data-stu-id="b5441-120">-Method</span></span>

<span data-ttu-id="b5441-121">Especifica o método do recurso que esse cmdlet invoca.</span><span class="sxs-lookup"><span data-stu-id="b5441-121">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="b5441-122">Os valores aceitáveis para esse parâmetro são: **Get** , **set** e **Test** .</span><span class="sxs-lookup"><span data-stu-id="b5441-122">The acceptable values for this parameter are: **Get** , **Set** , and **Test** .</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5441-123">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="b5441-123">-ModuleName</span></span>

<span data-ttu-id="b5441-124">Especifica o nome do módulo do qual este cmdlet invoca o recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="b5441-124">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5441-125">-Name</span><span class="sxs-lookup"><span data-stu-id="b5441-125">-Name</span></span>

<span data-ttu-id="b5441-126">Especifica o nome do recurso DSC a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="b5441-126">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5441-127">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="b5441-127">-Property</span></span>

<span data-ttu-id="b5441-128">Especifica o nome da propriedade de recurso e seu valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b5441-128">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5441-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5441-129">CommonParameters</span></span>

<span data-ttu-id="b5441-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5441-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5441-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5441-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5441-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b5441-132">INPUTS</span></span>

## <span data-ttu-id="b5441-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b5441-133">OUTPUTS</span></span>

### <span data-ttu-id="b5441-134">Microsoft. Management. Infrastructure. CimInstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="b5441-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="b5441-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b5441-135">NOTES</span></span>

- <span data-ttu-id="b5441-136">Anteriormente, os recursos do Windows PowerShell 5,1 eram executados no contexto do sistema, a menos que especificado com o contexto do usuário usando a chave **PsDscRunAsCredential** .</span><span class="sxs-lookup"><span data-stu-id="b5441-136">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential** .</span></span> <span data-ttu-id="b5441-137">No PowerShell 7,0, os recursos são executados no contexto do usuário e não há mais suporte para **PsDscRunAsCredential** .</span><span class="sxs-lookup"><span data-stu-id="b5441-137">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="b5441-138">As configurações anteriores que usam essa chave gerarão uma exceção.</span><span class="sxs-lookup"><span data-stu-id="b5441-138">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="b5441-139">A partir do PowerShell 7, o `Invoke-DscResource` não dá mais suporte à invocação de recursos de DSC do WMI.</span><span class="sxs-lookup"><span data-stu-id="b5441-139">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="b5441-140">Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b5441-140">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration** .</span></span>

## <span data-ttu-id="b5441-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b5441-141">RELATED LINKS</span></span>

[<span data-ttu-id="b5441-142">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5441-142">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="b5441-143">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="b5441-143">Get-DscResource</span></span>](Get-DscResource.md)
