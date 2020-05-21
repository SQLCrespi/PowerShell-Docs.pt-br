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
ms.openlocfilehash: 7a578dd63a53562f992b2970573258b8676e2a52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692278"
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

   - As `<Configuration></Configuration>` marcas definem o `Configuration` nó raiz. Todas as marcas XML adicionais serão incluídas nesse nó.

   - As `<ViewDefinitions></ViewDefinitions>` marcas definem o `ViewDefinitions` nó. Todas as exibições são definidas neste nó.

3. Salve o arquivo na pasta de instalação do Windows PowerShell, na pasta do módulo ou em uma subpasta da pasta do módulo. Use o seguinte formato de nome ao salvar o arquivo: `MyFile.format.ps1xml` . Os arquivos de formatação devem usar a `.format.ps1xml` extensão.

   Agora você está pronto para adicionar exibições ao arquivo de formatação. Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação. Você pode adicionar uma única exibição para cada objeto, várias exibições para o mesmo objeto ou uma única exibição usada por vários objetos.

## <a name="see-also"></a>Consulte Também

[Escrevendo um arquivo de tipos e formatação do Windows PowerShell](./writing-a-powershell-formatting-file.md)
