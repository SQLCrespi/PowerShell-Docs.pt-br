---
description: Descreve os formatos de nome de caminho completo e relativo no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_path_syntax?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Path_Syntax
ms.openlocfilehash: b58fdd62803bfb654c9c69acda390d63341aacd9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196111"
---
# <a name="about-path-syntax"></a>Sobre a sintaxe do caminho

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os formatos de nome de caminho completo e relativo no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Todos os itens em um armazenamento de dados acessível por meio de um provedor do PowerShell podem ser identificados exclusivamente por seus nomes de caminho. Um nome de caminho é uma combinação do nome do item, o contêiner e os sub-recipientes nos quais o item está localizado e a unidade do PowerShell por meio da qual os contêineres são acessados.

No PowerShell, os nomes de caminho são divididos em um dos dois tipos: totalmente qualificado e relativo. Um nome de caminho totalmente qualificado consiste em todos os elementos que compõem um caminho. A sintaxe a seguir mostra os elementos em um nome de caminho totalmente qualificado:

```powershell
[<provider>::]<drive>:[\<container>[\<subcontainer>...]]\<item>
```

O \<provider\> espaço reservado refere-se ao provedor do PowerShell por meio do qual você acessa o armazenamento de dados. Por exemplo, o provedor FileSystem permite que você acesse os arquivos e diretórios em seu computador. Esse elemento da sintaxe é opcional e nunca é necessário porque os nomes das unidades são exclusivos em todos os provedores.

O \<drive\> espaço reservado refere-se à unidade do PowerShell que é suportada por um provedor específico do PowerShell. No caso do provedor FileSystem, as unidades do PowerShell são mapeadas para as unidades do Windows que são configuradas no seu sistema. Por exemplo, se o sistema incluir uma unidade A: e uma unidade C:, o provedor FileSystem criará as mesmas unidades no PowerShell.

Depois de especificar a unidade, você deve especificar todos os contêineres e subcontêineres que contenham o item. Os contêineres devem ser especificados na ordem hierárquica em que existem no repositório de dados. Em outras palavras, você deve começar com o contêiner pai, depois o contêiner filho nesse contêiner pai e assim por diante. Além disso, cada contêiner deve ser precedido por uma barra invertida. (Observe que o PowerShell permite que você use barras invertidas para compatibilidade com outros PowerShell.)

Depois que o contêiner e os sub-recipientes tiverem sido especificados, você deverá fornecer o nome do item, precedido por uma barra invertida. Por exemplo, o nome de caminho totalmente qualificado para o arquivo de Shell.dll no diretório C: \\ Windows \\ System32 é o seguinte:

```powershell
C:\Windows\System32\Shell.dll
```

Nesse caso, a unidade por meio da qual os contêineres são acessados é a unidade C:, o contêiner de nível superior é o Windows, o subcontêiner é system32 (localizado dentro do contêiner do Windows) e o item é Shell.dll.

Em algumas situações, você não precisa especificar um nome de caminho totalmente qualificado e, em vez disso, pode usar um nome de caminho relativo. Um nome de caminho relativo é baseado no local de trabalho atual. O PowerShell permite que você identifique um item com base em sua localização relativa ao local de trabalho atual. Você pode especificar nomes de caminho relativos usando caracteres especiais. A tabela a seguir descreve cada um desses caracteres e fornece exemplos de nomes de caminho relativo e nomes de caminho totalmente qualificados. Os exemplos na tabela baseiam-se no diretório de trabalho atual que está sendo definido como C:\Windows.

|Símbolo|Descrição               |Caminho relativo    |Caminho completo          |
|------|--------------------------|-----------------|-------------------|
|.     |Local atual          |.\\ Sistema        |c: \\ \\ sistema Windows|
|..    |Pai do local atual|..\\ Arquivos de programas|c: \\ arquivos de programas  |
|\     |Unidade raiz do atual     |\\Arquivos de programas  |c: \\ arquivos de programas  |
|      |local                  |                 |                   |
|None|Nenhum caractere especial     |Sistema           |c: \\ \\ sistema Windows|

Ao usar um nome de caminho em um comando, você insere esse nome da mesma maneira se usa um nome de caminho totalmente qualificado ou um relativo. Por exemplo, suponha que seu diretório de trabalho atual seja C:\Windows. O comando a seguir Get-ChildItem recupera todos os itens no diretório C:\Techdocs:

```powershell
Get-ChildItem \techdocs
```

A barra invertida indica que a raiz da unidade do local de trabalho atual deve ser usada. Como o diretório de trabalho é C: \\ Windows, a unidade raiz é a unidade c:. Como o diretório techdocs está localizado fora da raiz, você precisa especificar apenas a barra invertida.

Você pode obter os mesmos resultados usando o seguinte comando:

```powershell
Get-ChildItem c:\techdocs
```

Independentemente de você usar um nome de caminho totalmente qualificado ou um nome de caminho relativo, um nome de caminho é importante não apenas porque ele localiza um item, mas também porque ele identifica exclusivamente o item, mesmo que esse item Compartilhe o mesmo nome de outro item em um contêiner diferente.

Por exemplo, suponha que você tenha dois arquivos chamados Results.txt.
O primeiro arquivo está em um diretório chamado C: \\ techdocs \\ Jan e o segundo arquivo está em um diretório chamado c: \\ techdocs \\ Fev. O nome do caminho para o primeiro arquivo (C: \\ techdocs \\ Jan \\Results.txt) e o nome do caminho para o segundo arquivo (c: \\ techdocs \\ fev \\Results.txt) permitem distinguir claramente os dois arquivos.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Locations](about_Locations.md)
