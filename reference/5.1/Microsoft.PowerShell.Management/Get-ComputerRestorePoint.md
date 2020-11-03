---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194186"
---
# <span data-ttu-id="c168b-103">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="c168b-103">Get-ComputerRestorePoint</span></span>

## <span data-ttu-id="c168b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c168b-104">SYNOPSIS</span></span>
<span data-ttu-id="c168b-105">Obtém os pontos de restauração no computador local.</span><span class="sxs-lookup"><span data-stu-id="c168b-105">Gets the restore points on the local computer.</span></span>

## <span data-ttu-id="c168b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c168b-106">SYNTAX</span></span>

### <span data-ttu-id="c168b-107">ID (padrão)</span><span class="sxs-lookup"><span data-stu-id="c168b-107">ID (Default)</span></span>

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="c168b-108">LastStatus</span><span class="sxs-lookup"><span data-stu-id="c168b-108">LastStatus</span></span>

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## <span data-ttu-id="c168b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c168b-109">DESCRIPTION</span></span>

<span data-ttu-id="c168b-110">O `Get-ComputerRestorePoint` cmdlet obtém os pontos de restauração do sistema do computador local.</span><span class="sxs-lookup"><span data-stu-id="c168b-110">The `Get-ComputerRestorePoint` cmdlet gets the local computer's system restore points.</span></span> <span data-ttu-id="c168b-111">E ele pode exibir o status da tentativa mais recente de restaurar o computador.</span><span class="sxs-lookup"><span data-stu-id="c168b-111">And, it can display the status of the most recent attempt to restore the computer.</span></span>

<span data-ttu-id="c168b-112">Você pode usar as informações do `Get-ComputerRestorePoint` para selecionar um ponto de restauração.</span><span class="sxs-lookup"><span data-stu-id="c168b-112">You can use the information from `Get-ComputerRestorePoint` to select a restore point.</span></span> <span data-ttu-id="c168b-113">Por exemplo, use um número de sequência para identificar um ponto de restauração para o `Restore-Computer` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c168b-113">For example, use a sequence number to identify a restore point for the `Restore-Computer` cmdlet.</span></span>

<span data-ttu-id="c168b-114">Os pontos de restauração do sistema e o `Get-ComputerRestorePoint` cmdlet têm suporte apenas em sistemas operacionais cliente, como o Windows 10, o Windows 7, o Windows Vista e o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="c168b-114">System restore points and the `Get-ComputerRestorePoint` cmdlet are supported only on client operating systems such as Windows 10, Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="c168b-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c168b-115">EXAMPLES</span></span>

### <span data-ttu-id="c168b-116">Exemplo 1: obter todos os pontos de restauração do sistema</span><span class="sxs-lookup"><span data-stu-id="c168b-116">Example 1: Get all system restore points</span></span>

<span data-ttu-id="c168b-117">Neste exemplo, `Get-ComputerRestorePoint` Obtém todos os pontos de restauração do sistema do computador local.</span><span class="sxs-lookup"><span data-stu-id="c168b-117">In this example, `Get-ComputerRestorePoint` gets all the local computer's system restore points.</span></span>

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### <span data-ttu-id="c168b-118">Exemplo 2: obter números de sequência específicos</span><span class="sxs-lookup"><span data-stu-id="c168b-118">Example 2: Get specific sequence numbers</span></span>

<span data-ttu-id="c168b-119">Este exemplo obtém pontos de restauração do sistema para números de sequência específicos.</span><span class="sxs-lookup"><span data-stu-id="c168b-119">This example gets system restore points for specific sequence numbers.</span></span>

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

<span data-ttu-id="c168b-120">`Get-ComputerRestorePoint` usa o parâmetro **RestorePoint** para especificar uma matriz separada por vírgulas de números de sequência.</span><span class="sxs-lookup"><span data-stu-id="c168b-120">`Get-ComputerRestorePoint` uses the **RestorePoint** parameter to specify a comma-separated array of sequence numbers.</span></span>

### <span data-ttu-id="c168b-121">Exemplo 3: exibir o status de uma restauração do sistema</span><span class="sxs-lookup"><span data-stu-id="c168b-121">Example 3: Display the status of a system restore</span></span>

<span data-ttu-id="c168b-122">Este exemplo exibe o status da restauração mais recente do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="c168b-122">This example displays the status of the most recent system restore on the local computer.</span></span>

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

<span data-ttu-id="c168b-123">`Get-ComputerRestorePoint` usa o parâmetro **LastStatus** para exibir o resultado da restauração mais recente do sistema.</span><span class="sxs-lookup"><span data-stu-id="c168b-123">`Get-ComputerRestorePoint` uses the **LastStatus** parameter to display the result of the most recent system restore.</span></span>

### <span data-ttu-id="c168b-124">Exemplo 4: usar uma expressão para converter o CreationTime</span><span class="sxs-lookup"><span data-stu-id="c168b-124">Example 4: Use an expression to convert the CreationTime</span></span>

<span data-ttu-id="c168b-125">`Get-ComputerRestorePoint` gera o **CreationTime** como uma cadeia de caracteres de data e hora Instrumentação de gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c168b-125">`Get-ComputerRestorePoint` outputs the **CreationTime** as a Windows Management Instrumentation (WMI) date and time string.</span></span>

<span data-ttu-id="c168b-126">Neste exemplo, uma variável armazena uma expressão que converte a cadeia de caracteres **CreationTime** em um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="c168b-126">In this example, a variable stores an expression that converts the **CreationTime** string to a **DateTime** object.</span></span> <span data-ttu-id="c168b-127">Para exibir as cadeias de caracteres **CreationTime** antes que elas sejam convertidas, use um comando como `((Get-ComputerRestorePoint).CreationTime)` .</span><span class="sxs-lookup"><span data-stu-id="c168b-127">To view **CreationTime** strings before they're converted, use a command such as `((Get-ComputerRestorePoint).CreationTime)`.</span></span> <span data-ttu-id="c168b-128">Para obter mais informações sobre a cadeia de caracteres de data e hora do WMI, consulte [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span><span class="sxs-lookup"><span data-stu-id="c168b-128">For more information about the WMI date and time string, see [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span></span>

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

<span data-ttu-id="c168b-129">A `$date` variável armazena uma tabela de hash com a expressão que usa o método **ConvertToDateTime** .</span><span class="sxs-lookup"><span data-stu-id="c168b-129">The `$date` variable stores a hash table with the expression that uses the **ConvertToDateTime** method.</span></span> <span data-ttu-id="c168b-130">A expressão converte o valor da propriedade **CreationTime** de uma cadeia de caracteres WMI em um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="c168b-130">The expression converts the **CreationTime** property's value from a WMI string to a **DateTime** object.</span></span>

<span data-ttu-id="c168b-131">`Get-ComputerRestorePoint` envia os objetos do ponto de restauração do sistema para baixo no pipeline.</span><span class="sxs-lookup"><span data-stu-id="c168b-131">`Get-ComputerRestorePoint` sends the system restore point objects down the pipeline.</span></span> <span data-ttu-id="c168b-132">`Select-Object` usa o parâmetro **Property** para especificar as propriedades a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="c168b-132">`Select-Object` uses the **Property** parameter to specify the properties to display.</span></span> <span data-ttu-id="c168b-133">Para cada objeto no pipeline, a expressão em `$date` converte o **CreationTime** e gera o resultado na propriedade **Date** .</span><span class="sxs-lookup"><span data-stu-id="c168b-133">For each object in the pipeline, the expression in `$date` converts the **CreationTime** and outputs the result in the **Date** property.</span></span>

### <span data-ttu-id="c168b-134">Exemplo 5: usar uma propriedade para obter um número de sequência</span><span class="sxs-lookup"><span data-stu-id="c168b-134">Example 5: Use a property to get a sequence number</span></span>

<span data-ttu-id="c168b-135">Este exemplo obtém um número de sequência usando a propriedade **SequenceNumber** e um índice de matriz.</span><span class="sxs-lookup"><span data-stu-id="c168b-135">This example gets a sequence number by using the **SequenceNumber** property and an array index.</span></span> <span data-ttu-id="c168b-136">A saída contém apenas o número de sequência.</span><span class="sxs-lookup"><span data-stu-id="c168b-136">The output only contains the sequence number.</span></span>

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

<span data-ttu-id="c168b-137">`Get-ComputerRestorePoint` usa a propriedade **SequenceNumber** com um índice de matriz.</span><span class="sxs-lookup"><span data-stu-id="c168b-137">`Get-ComputerRestorePoint` uses the **SequenceNumber** property with an array index.</span></span> <span data-ttu-id="c168b-138">O índice de matriz `-1` Obtém o número de sequência mais recente na matriz.</span><span class="sxs-lookup"><span data-stu-id="c168b-138">The array index of `-1` gets the most recent sequence number in the array.</span></span>

## <span data-ttu-id="c168b-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c168b-139">PARAMETERS</span></span>

### <span data-ttu-id="c168b-140">-LastStatus</span><span class="sxs-lookup"><span data-stu-id="c168b-140">-LastStatus</span></span>

<span data-ttu-id="c168b-141">Indica que `Get-ComputerRestorePoint` Obtém o status da operação de restauração do sistema mais recente.</span><span class="sxs-lookup"><span data-stu-id="c168b-141">Indicates that `Get-ComputerRestorePoint` gets the status of the most recent system restore operation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c168b-142">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="c168b-142">-RestorePoint</span></span>

<span data-ttu-id="c168b-143">Especifica os números de sequência dos pontos de restauração do sistema.</span><span class="sxs-lookup"><span data-stu-id="c168b-143">Specifies the sequence numbers of the system restore points.</span></span> <span data-ttu-id="c168b-144">Você pode especificar um único número de sequência ou uma matriz separada por vírgulas de números de sequência.</span><span class="sxs-lookup"><span data-stu-id="c168b-144">You can specify either a single sequence number or a comma-separated array of sequence numbers.</span></span>

<span data-ttu-id="c168b-145">Se o parâmetro **RestorePoint** não for especificado, o `Get-ComputerRestorePoint` retornará todos os pontos de restauração do sistema do computador local.</span><span class="sxs-lookup"><span data-stu-id="c168b-145">If the **RestorePoint** parameter isn't specified, `Get-ComputerRestorePoint` returns all the local computer's system restore points.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c168b-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c168b-146">CommonParameters</span></span>

<span data-ttu-id="c168b-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c168b-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c168b-148">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c168b-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c168b-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c168b-149">INPUTS</span></span>

### <span data-ttu-id="c168b-150">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c168b-150">None</span></span>

<span data-ttu-id="c168b-151">Você não pode enviar objetos pelo pipeline para o `Get-ComputerRestorePoint` .</span><span class="sxs-lookup"><span data-stu-id="c168b-151">You can't send objects down the pipeline to `Get-ComputerRestorePoint`.</span></span>

## <span data-ttu-id="c168b-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c168b-152">OUTPUTS</span></span>

### <span data-ttu-id="c168b-153">System. Management. ManagementObject # root\default\SystemRestore ou String</span><span class="sxs-lookup"><span data-stu-id="c168b-153">System.Management.ManagementObject#root\default\SystemRestore or String</span></span>

<span data-ttu-id="c168b-154">`Get-ComputerRestorePoint` Retorna um objeto **SystemRestore** , que é uma instância da classe **SystemRestore** do Instrumentação de gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c168b-154">`Get-ComputerRestorePoint` returns a **SystemRestore** object, which is an instance of the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

<span data-ttu-id="c168b-155">Quando você usa o parâmetro **LastStatus** , o `Get-ComputerRestorePoint` retorna uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c168b-155">When you use the **LastStatus** parameter, `Get-ComputerRestorePoint` returns a string.</span></span>

## <span data-ttu-id="c168b-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c168b-156">NOTES</span></span>

<span data-ttu-id="c168b-157">Para executar um `Get-ComputerRestorePoint` comando no Windows Vista e em versões posteriores do Windows, abra o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="c168b-157">To run a `Get-ComputerRestorePoint` command on Windows Vista and later versions of Windows, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="c168b-158">`Get-ComputerRestorePoint` usa a classe WMI **SystemRestore** .</span><span class="sxs-lookup"><span data-stu-id="c168b-158">`Get-ComputerRestorePoint` uses the WMI **SystemRestore** class.</span></span>

## <span data-ttu-id="c168b-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c168b-159">RELATED LINKS</span></span>

[<span data-ttu-id="c168b-160">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c168b-160">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="c168b-161">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="c168b-161">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="c168b-162">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="c168b-162">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="c168b-163">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="c168b-163">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="c168b-164">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="c168b-164">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="c168b-165">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="c168b-165">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="c168b-166">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="c168b-166">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="c168b-167">SystemRestore</span><span class="sxs-lookup"><span data-stu-id="c168b-167">SystemRestore</span></span>](/windows/win32/sr/systemrestore)
