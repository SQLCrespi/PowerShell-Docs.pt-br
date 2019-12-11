---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Selecionar partes de objetos com Select Object
ms.openlocfilehash: 4d4c89f0b5103e4701a3af3cd07fcd7c8f1c697f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030112"
---
# <a name="selecting-parts-of-objects-select-object"></a>Selecionar partes de objetos (Select-Object)

Você pode usar o cmdlet **Select-Object** para criar objetos do Windows PowerShell novos e personalizados que contêm as propriedades selecionadas dos objetos usados para criá-los. Digite o seguinte comando para criar um novo objeto que inclui apenas as propriedades Name e FreeSpace da classe WMI Win32_LogicalDisk:

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace

Name                                    FreeSpace
----                                    ---------
C:                                      50664845312
```

Não é possível ver o tipo de dados depois de emitir esse comando, mas, se você direcionar o resultado para Get-Member depois do Select-Object, verá que há um novo tipo de objeto, um PSCustomObject:

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace| Get-Member

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       System.Boolean Equals(Object obj)
GetHashCode Method       System.Int32 GetHashCode()
GetType     Method       System.Type GetType()
ToString    Method       System.String ToString()
FreeSpace   NoteProperty  FreeSpace=...
Name        NoteProperty System.String Name=C:
```

Select-Object tem muitos usos. Um deles é replicar dados que você pode modificar. Agora podemos manipular o problema que encontramos na seção anterior. Podemos atualizar o valor de FreeSpace em nossos objetos recém-criados e a saída incluirá o rótulo descritivo:

```
Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0; $_}
Name                                                                  FreeSpace
----                                                                  ---------
C:                                                                48317.7265625
```
