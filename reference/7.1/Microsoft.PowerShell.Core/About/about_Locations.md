---
description: Descreve como acessar itens do local de trabalho no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 56af758f06e365eb070786e50d8f8309d8f608fd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195447"
---
# <a name="about_locations"></a>about_Locations

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como acessar itens do local de trabalho no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O local de trabalho atual é o local padrão para o qual os comandos apontam.
Em outras palavras, esse é o local que o PowerShell usa se você não fornecer um caminho explícito para o item ou o local que é afetado pelo comando. Na maioria dos casos, o local de trabalho atual é uma unidade acessada por meio do provedor de sistema de arquivos do PowerShell e, em alguns casos, um diretório nessa unidade.
Por exemplo, você pode definir seu local de trabalho atual para o seguinte local:

```powershell
C:\Program Files\Windows PowerShell
```

Como resultado, todos os comandos são processados desse local, a menos que outro caminho seja explicitamente fornecido.

O PowerShell mantém o local de trabalho atual para cada unidade, mesmo quando a unidade não é a unidade atual. Isso permite que você acesse itens do local de trabalho atual fazendo referência apenas à unidade de outro local.
Por exemplo, suponha que o local de trabalho atual seja C: \\ Windows. Agora, suponha que você use o seguinte comando para alterar o local de trabalho atual para a unidade HKLM:

```powershell
Set-Location HKLM:
```

Embora seu local atual agora seja a unidade do registro, você ainda pode acessar itens no diretório C: \\ Windows simplesmente usando a unidade c:, conforme mostrado no exemplo a seguir:

```powershell
Get-ChildItem C:
```

O PowerShell lembra que o seu local de trabalho atual para essa unidade é o diretório do Windows, então ele recupera os itens desse diretório. Os resultados seriam os mesmos se você executou o seguinte comando:

```powershell
Get-ChildItem C:\Windows
```

No PowerShell, você pode usar o comando Get-Location para determinar o local de trabalho atual e pode usar o comando Set-Location para definir o local de trabalho atual. Por exemplo, o comando a seguir define o local de trabalho atual como o diretório do Windows da unidade C::

```powershell
Set-Location c:\windows
```

Depois de definir o local de trabalho atual, você ainda pode acessar itens de outras unidades simplesmente incluindo o nome da unidade (seguido por dois-pontos) no comando, conforme mostrado no exemplo a seguir:

```powershell
Get-ChildItem HKLM:\software
```

O comando de exemplo recupera uma lista de itens no contêiner de software do hive do computador local HKEY no registro.

O PowerShell também permite que você use caracteres especiais para representar o local de trabalho atual e seu local pai. Para representar o local de trabalho atual, use um único período. Para representar o pai do local de trabalho atual, use dois pontos. Por exemplo, o seguinte especifica o subdiretório do sistema no local de trabalho atual:

```powershell
Get-ChildItem .\system
```

Se o local de trabalho atual for C: \\ Windows, esse comando retornará uma lista de todos os itens em c: \\ Windows \\ System. No entanto, se você usar dois pontos, o diretório pai do diretório de trabalho atual será usado, conforme mostrado no exemplo a seguir:

```powershell
Get-ChildItem ..\"program files"
```

Nesse caso, o PowerShell trata os dois períodos como a unidade C:, portanto, o comando recupera todos os itens no diretório C: \\ arquivos de programas.

Um caminho que começa com uma barra identifica um caminho da raiz da unidade atual. Por exemplo, se o local de trabalho atual for C: \\ arquivos de programas do \\ PowerShell, a raiz da unidade será c. Portanto, o comando a seguir lista todos os itens no diretório C: \\ Windows:

```powershell
Get-ChildItem \windows
```

Se você não especificar um caminho começando com um nome de unidade, barra ou ponto ao fornecer o nome de um contêiner ou item, presume-se que o contêiner ou item esteja localizado no local de trabalho atual. Por exemplo, se o local de trabalho atual for C: \\ Windows, o comando a seguir retornará todos os itens no diretório c: \\ Windows \\ System:

```powershell
Get-ChildItem system
```

Se você especificar um nome de arquivo em vez de um nome de diretório, o PowerShell retornará detalhes sobre esse arquivo (supondo que esse arquivo esteja localizado no local de trabalho atual).

## <a name="see-also"></a>CONSULTE TAMBÉM

[Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)

[about_Providers](about_Providers.md)

[about_Path_Syntax](about_Path_Syntax.md)

