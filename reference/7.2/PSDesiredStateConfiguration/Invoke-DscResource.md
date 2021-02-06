---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 732db5a049a68e059db6062d2f6c3f850d579adc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595770"
---
# <span data-ttu-id="c658b-102">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="c658b-102">Invoke-DscResource</span></span>

## <span data-ttu-id="c658b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c658b-103">SYNOPSIS</span></span>
<span data-ttu-id="c658b-104">Executa um método de um recurso de configuração de estado desejado (DSC) do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="c658b-104">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="c658b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c658b-105">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="c658b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c658b-106">DESCRIPTION</span></span>

<span data-ttu-id="c658b-107">O cmdlet `Invoke-DscResource` executa um método de um recurso de DSC (Desired State Configuration) do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="c658b-107">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="c658b-108">Esse cmdlet invoca um recurso de DSC diretamente, sem criar um documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="c658b-108">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="c658b-109">Usando esse cmdlet, os produtos de gerenciamento de configuração podem gerenciar o Windows ou o Linux usando recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="c658b-109">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="c658b-110">Esse cmdlet também habilita a depuração de recursos quando o mecanismo de DSC está em execução com a depuração habilitada.</span><span class="sxs-lookup"><span data-stu-id="c658b-110">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="c658b-111">`Invoke-DscResource` é um recurso experimental no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="c658b-111">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="c658b-112">Para usar o cmdlet, você deve habilitá-lo usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="c658b-112">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="c658b-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c658b-113">EXAMPLES</span></span>

### <span data-ttu-id="c658b-114">Exemplo 1: invocar o método set de um recurso especificando suas propriedades obrigatórias</span><span class="sxs-lookup"><span data-stu-id="c658b-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="c658b-115">Este exemplo invoca o método **set** de um recurso chamado **WindowsProcess** e fornece as propriedades de **caminho** e **argumentos** obrigatórios para iniciar o processo do Windows especificado.</span><span class="sxs-lookup"><span data-stu-id="c658b-115">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="c658b-116">Exemplo 2: invocar o método de teste de um recurso para um módulo especificado</span><span class="sxs-lookup"><span data-stu-id="c658b-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="c658b-117">Este exemplo invoca o método de **teste** de um recurso chamado **WindowsProcess**, que está no módulo chamado **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c658b-117">This example invokes the **Test** method of a resource named **WindowsProcess**, which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="c658b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c658b-118">PARAMETERS</span></span>

### <span data-ttu-id="c658b-119">-Método</span><span class="sxs-lookup"><span data-stu-id="c658b-119">-Method</span></span>

<span data-ttu-id="c658b-120">Especifica o método do recurso que esse cmdlet invoca.</span><span class="sxs-lookup"><span data-stu-id="c658b-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="c658b-121">Os valores aceitáveis para esse parâmetro são: **Get**, **set** e **Test**.</span><span class="sxs-lookup"><span data-stu-id="c658b-121">The acceptable values for this parameter are: **Get**, **Set**, and **Test**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c658b-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="c658b-122">-ModuleName</span></span>

<span data-ttu-id="c658b-123">Especifica o nome do módulo do qual este cmdlet invoca o recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="c658b-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c658b-124">-Name</span><span class="sxs-lookup"><span data-stu-id="c658b-124">-Name</span></span>

<span data-ttu-id="c658b-125">Especifica o nome do recurso DSC a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="c658b-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c658b-126">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="c658b-126">-Property</span></span>

<span data-ttu-id="c658b-127">Especifica o nome da propriedade de recurso e seu valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c658b-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c658b-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c658b-128">CommonParameters</span></span>

<span data-ttu-id="c658b-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c658b-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c658b-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c658b-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c658b-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c658b-131">INPUTS</span></span>

### <span data-ttu-id="c658b-132">System.String</span><span class="sxs-lookup"><span data-stu-id="c658b-132">System.String</span></span>

### <span data-ttu-id="c658b-133">Microsoft. PowerShell. Commands. ModuleSpecification</span><span class="sxs-lookup"><span data-stu-id="c658b-133">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="c658b-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c658b-134">OUTPUTS</span></span>

### <span data-ttu-id="c658b-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="c658b-135">System.Object</span></span>

## <span data-ttu-id="c658b-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c658b-136">NOTES</span></span>

- <span data-ttu-id="c658b-137">Anteriormente, os recursos do Windows PowerShell 5,1 eram executados no contexto do sistema, a menos que especificado com o contexto do usuário usando a chave **PsDscRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="c658b-137">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="c658b-138">No PowerShell 7,0, os recursos são executados no contexto do usuário e não há mais suporte para **PsDscRunAsCredential** .</span><span class="sxs-lookup"><span data-stu-id="c658b-138">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="c658b-139">As configurações anteriores que usam essa chave gerarão uma exceção.</span><span class="sxs-lookup"><span data-stu-id="c658b-139">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="c658b-140">A partir do PowerShell 7, o `Invoke-DscResource` não dá mais suporte à invocação de recursos de DSC do WMI.</span><span class="sxs-lookup"><span data-stu-id="c658b-140">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="c658b-141">Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c658b-141">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="c658b-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c658b-142">RELATED LINKS</span></span>

[<span data-ttu-id="c658b-143">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c658b-143">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="c658b-144">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="c658b-144">Get-DscResource</span></span>](Get-DscResource.md)
