---
title: Como criar um arquivo de formatação (. Format. ps1xml) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363615"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Como criar um arquivo de formatação (.format.ps1xml)

Este tópico descreve como criar um arquivo de formatação (. Format. ps1xml).

> [!NOTE]
> Você também pode criar um arquivo de formatação fazendo uma cópia de um dos arquivos fornecidos pelo Windows PowerShell. Se você fizer uma cópia de um arquivo existente, exclua a assinatura digital existente e adicione sua própria assinatura ao novo arquivo.

### <a name="to-create-a-formatps1xml-file"></a>Para criar um arquivo. Format. ps1xml.

1. Crie um arquivo de texto (. txt) usando um editor de texto como o bloco de notas.

2. Copie as linhas a seguir no arquivo de formatação.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - As marcas \<Configuration > \</Configuration > definem o nó raiz `Configuration`. Todas as marcas XML adicionais serão incluídas nesse nó.

   - As <ViewDefinitions></ViewDefinitions> marcas definem o nó `ViewDefinitions`. Todas as exibições são definidas neste nó.

3. Salve o arquivo na pasta de instalação do Windows PowerShell, na pasta do módulo ou em uma subpasta da pasta do módulo. Use o seguinte formato de nome ao salvar o arquivo: `MyFile.format.ps1xml`. Os arquivos de formatação devem usar a extensão `.format.ps1xml`.

   Agora você está pronto para adicionar exibições ao arquivo de formatação. Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação. Você pode adicionar uma única exibição para cada objeto, várias exibições para o mesmo objeto ou uma única exibição usada por vários objetos.

## <a name="see-also"></a>Consulte Também

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
