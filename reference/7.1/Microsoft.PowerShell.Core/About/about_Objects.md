---
description: Fornece informações essenciais sobre objetos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: b8b642288927af7151bdf6d60d251d45c9f8ca34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196357"
---
# <a name="about-objects"></a>Sobre objetos

## <a name="short-description"></a>Descrição breve
Fornece informações essenciais sobre objetos no PowerShell.

## <a name="long-description"></a>Descrição longa

Cada ação executada no PowerShell ocorre dentro do contexto de objetos. À medida que os dados são movidos de um comando para o outro, ele é movido como um ou mais objetos identificáveis. Um objeto, então, é uma coleção de dados que representa um item. Um objeto é composto de três tipos de dados: o tipo Objects, seus métodos e suas propriedades.

## <a name="types-methods-and-properties"></a>Tipos, métodos e propriedades

O tipo de objeto informa que tipo de objeto é. Por exemplo, um objeto que representa um arquivo é um objeto FileInfo.

Os métodos de objeto são ações que você pode executar no objeto.
Por exemplo, os objetos FileInfo têm um método CopyTo que você pode usar para copiar o arquivo.

As propriedades do objeto armazenam informações sobre o objeto. Por exemplo, os objetos FileInfo têm uma Propriedade LastWriteTime que armazena a data e a hora em que o arquivo foi acessado mais recentemente.

Ao trabalhar com objetos, você pode usar seus métodos e propriedades em comandos para executar ações e gerenciar dados.

## <a name="objects-in-pipelines"></a>Objetos em pipelines

Quando os comandos são combinados em um pipeline, eles passam informações entre si como objetos. Quando o primeiro comando é executado, ele envia um ou mais objetos por meio do pipeline para o segundo comando. O segundo comando recebe os objetos do primeiro comando, processa os objetos e, em seguida, passa os objetos novos ou revisados para o próximo comando no pipeline.
Isso continuará até que todos os comandos no pipeline sejam executados.

O exemplo a seguir demonstra como os objetos são passados de um comando para o seguinte:

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

O primeiro comando `Get-ChildItem C:` retorna um objeto de arquivo ou diretório para cada item no diretório raiz do sistema de arquivos. Os objetos de arquivo e diretório são passados para o pipeline para o segundo comando.

O segundo comando `where { $_.PsIsContainer -eq $false }` usa a propriedade PsIsContainer de todos os objetos do sistema de arquivos para selecionar apenas os arquivos, que têm um valor de false ( \$ false) em sua propriedade PsIsContainer. As pastas, que são contêineres e, portanto, têm um valor de true ( \$ true) em sua propriedade PsIsContainer, não são selecionadas.

O segundo comando passa apenas os objetos File para o terceiro comando `Format-List` , que exibe os objetos de arquivo em uma lista.

## <a name="see-also"></a>Consulte Também

[about_Methods](about_Methods.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

