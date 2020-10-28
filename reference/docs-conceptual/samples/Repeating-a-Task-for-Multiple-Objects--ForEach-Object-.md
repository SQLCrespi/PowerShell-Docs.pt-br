---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Repetir uma tarefa para vários objetos ForEach Object
description: O ForEach-Object permite que você repita um conjunto de comandos para cada objeto passado pelo pipeline.
ms.openlocfilehash: 7353be833dc8bf77dd18b7fc45bdd97e092ff6ef
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499942"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a>Repetir uma tarefa para vários objetos (ForEach-Object)

O cmdlet `ForEach-Object` usa blocos de script e o descritor `$_` do objeto de pipeline atual para permitir a execução de um comando em cada objeto no pipeline. Isso pode ser usado para executar algumas tarefas complicadas.

Uma situação em que isso pode ser útil é manipular dados para torná-los mais úteis. Por exemplo, a classe **Win32_LogicalDisk** do WMI pode ser usada para retornar informações de espaço livre para cada disco local. Contudo, os dados são retornados em bytes, o que dificulta a leitura:

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

Podemos converter o valor **FreeSpace** para megabytes dividindo cada valor por 1 MB. Você pode fazer isso em um bloco de script de `ForEach-Object` digitando:

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

Infelizmente, a saída agora é de dados sem nenhum rótulo associado. Como propriedades WMI como essa são somente leitura, não é possível converter diretamente o **FreeSpace** . Se você digitar:

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

Receberá uma mensagem de erro:

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

É possível reorganizar os dados usando algumas técnicas avançadas, mas uma abordagem mais simples é criar um objeto usando `Select-Object`.
