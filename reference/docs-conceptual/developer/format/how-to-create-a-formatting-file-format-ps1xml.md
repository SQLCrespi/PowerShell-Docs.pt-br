---
title: Como criar um arquivo de formatação (.format.ps1XML) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: abdbd4e15b0c4cb1dafcde087d24ed5792c86c3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781249"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Como criar um arquivo de formatação (.format.ps1xml)

Este tópico descreve como criar um arquivo de formatação (.format.ps1XML).

> [!NOTE]
> Você também pode criar um arquivo de formatação fazendo uma cópia de um dos arquivos fornecidos pelo Windows PowerShell. Se você fizer uma cópia de um arquivo existente, exclua a assinatura digital existente e adicione sua própria assinatura ao novo arquivo.

### <a name="to-create-a-formatps1xml-file"></a>Para criar um arquivo XML .format.ps1.

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
