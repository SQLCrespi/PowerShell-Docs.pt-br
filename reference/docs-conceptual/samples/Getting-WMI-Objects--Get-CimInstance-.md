---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Obter objetos WMI (Get-CimInstance)
ms.openlocfilehash: 4ff47844fd367a49f554c7c05c491bdddf28eabc
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "77002646"
---
# <a name="getting-wmi-objects-get-ciminstance"></a>Obter objetos WMI (Get-CimInstance)

## <a name="getting-wmi-objects-get-ciminstance"></a>Obter objetos WMI (Get-CimInstance)

O WMI (Instrumentação de Gerenciamento do Windows) é uma das principais tecnologias para a administração do sistema, pois ela expõe uma grande variedade de informações de maneira uniforme. Devido às inúmeras possibilidades oferecidas pelo WMI, o cmdlet do PowerShell usado para acessar objetos WMI, `Get-CimInstance`, é um dos mais úteis para fazer o trabalho duro. Vamos discutir como usar CimCmdlets para acessar objetos WMI e como usar objetos WMI para fazer coisas específicas.

### <a name="listing-wmi-classes"></a>Listar classes WMI

O primeiro problema que a maioria dos usuários do WMI encontram é tentar descobrir o que pode ser feito com o WMI. As classes WMI descrevem os recursos que podem ser gerenciados. Há centenas de classes WMI, algumas das quais contêm dezenas de propriedades.

`Get-CimClass` cuida desse problema possibilitando que o WMI possa ser descoberto. Você pode obter uma lista das classes WMI disponíveis no computador local digitando:

```powershell
Get-CimClass -Namespace root/CIMV2 |
  Where-Object CimClassName -like Win32* |
    Select-Object CimClassName
```

```Output
CimClassName
------------
Win32_DeviceChangeEvent
Win32_SystemConfigurationChangeEvent
Win32_VolumeChangeEvent
Win32_SystemTrace
Win32_ProcessTrace
Win32_ProcessStartTrace
Win32_ProcessStopTrace
Win32_ThreadTrace
Win32_ThreadStartTrace
Win32_ThreadStopTrace
...
```

Você pode recuperar as mesmas informações de um computador remoto por meio do parâmetro **ComputerName** especificando um nome do computador ou endereço IP:

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

A listagem de classe retornada por computadores remotos pode variar por sistema operacional específico que o computador está executando e as extensões WMI específicas adicionadas por aplicativos instalados.

> [!NOTE]
> Quando usar cmdlets do CIM para se conectar a um computador remoto, o computador remoto deverá estar executando o WMI, e a conta usada deverá estar no grupo de administradores locais no computador remoto.
> O sistema remoto não precisa ter o PowerShell instalado. Isso permite administrar sistemas operacionais que não executam o PowerShell, mas que têm o WMI disponível.

### <a name="displaying-wmi-class-details"></a>Exibir detalhes da classe WMI

Se você já souber o nome de uma classe WMI, poderá usá-la para obter informações imediatamente. Por exemplo, uma das classes WMI geralmente usadas para recuperar informações sobre um computador é **Win32_OperatingSystem**.

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

Embora mostremos todos os parâmetros, o comando pode ser expresso de forma mais sucinta.
O parâmetro **ComputerName** não é necessário ao se conectar ao sistema local. Vamos mostrá-lo para demonstrar o caso mais geral e lembrá-lo sobre o parâmetro. O **Namespace** usa `root/CIMV2` como padrão e também pode ser omitido. Por fim, a maioria dos cmdlets permitem omitir o nome dos parâmetros comuns. Com `Get-CimInstance`, se nenhum nome for especificado para o primeiro parâmetro, o PowerShell o tratará como o parâmetro **Class**. Isso significa que o último comando pode ter sido emitido digitando:

```powershell
Get-CimInstance Win32_OperatingSystem
```

A classe **Win32_OperatingSystem** tem muitos mais propriedades do que as exibidas aqui. Você pode usar Get-Member para ver todas as propriedades. As propriedades de uma classe WMI ficam automaticamente disponíveis assim como outras propriedades de objeto:

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Get-Member -MemberType Property
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_OperatingSystem
Name                                      MemberType Definition
----                                      ---------- ----------
BootDevice                                Property   string BootDevice {get;}
BuildNumber                               Property   string BuildNumber {get;}
BuildType                                 Property   string BuildType {get;}
Caption                                   Property   string Caption {get;}
CodeSet                                   Property   string CodeSet {get;}
CountryCode                               Property   string CountryCode {get;}
CreationClassName                         Property   string CreationClassName {get;}
CSCreationClassName                       Property   string CSCreationClassName {get;}
CSDVersion                                Property   string CSDVersion {get;}
CSName                                    Property   string CSName {get;}
CurrentTimeZone                           Property   short CurrentTimeZone {get;}
DataExecutionPrevention_32BitApplications Property   bool DataExecutionPrevention_32BitApplications {get;}
DataExecutionPrevention_Available         Property   bool DataExecutionPrevention_Available {get;}
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a>Exibindo propriedades não padrão com cmdlets Format

Se quiser ver as informações contidas na classe **Win32_OperatingSystem** que não são exibidas por padrão, você poderá exibi-las usando os cmdlets **Format**. Por exemplo, se você deseja exibir dados de memória disponível, digite:

```powershell
Get-CimInstance -Class Win32_OperatingSystem |
  Format-Table -Property TotalVirtualMemorySize, TotalVisibleMemorySize,
    FreePhysicalMemory, FreeVirtualMemory, FreeSpaceInPagingFiles
```

```Output
TotalVirtualMemorySize TotalVisibleMemorySize FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------------- ------------------ ----------------- ----------------------
              33449088               16671872            6451868          18424496               16285032
```

> [!NOTE]
> Os curingas funcionam com nomes de propriedade em `Format-Table`, portanto, o elemento final do pipeline pode ser reduzido para `Format-Table -Property Total*Memory*, Free*`

Os dados da memória podem ficar mais legíveis se você formatá-los como uma lista digitando:

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Format-List Total*Memory*, Free*
```

```Output
TotalVirtualMemorySize : 33449088
TotalVisibleMemorySize : 16671872
FreePhysicalMemory     : 6524456
FreeSpaceInPagingFiles : 16285808
FreeVirtualMemory      : 18393668
Name                   : Microsoft Windows 10 Pro|C:\WINDOWS|\Device\Harddisk0\Partition2
```
