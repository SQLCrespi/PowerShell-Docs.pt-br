---
title: Como criar o arquivo de ajuda do cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: cc77c0546de98e492c9724e051b9d72f1ebfdcb6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560161"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>Como criar o arquivo de ajuda do cmdlet

Esta seção descreve como criar um arquivo XML válido que contém conteúdo para tópicos de ajuda do cmdlet do Windows PowerShell. Esta seção discute como nomear o arquivo de ajuda, como adicionar os cabeçalhos XML apropriados e como adicionar nós que conterám as diferentes seções do conteúdo de ajuda do cmdlet.

> [!NOTE]
> Para obter uma exibição completa de um arquivo de ajuda, abra um dos arquivos dll-Help. xml localizados no diretório de instalação do Windows PowerShell. Por exemplo, o arquivo Microsoft. PowerShell. Commands. Management. dll-Help. xml contém conteúdo para vários cmdlets do Windows PowerShell.

### <a name="how-to-create-a-cmdlet-help-file"></a>Como criar um arquivo de ajuda de cmdlet

1. Crie um arquivo de texto e salve-o usando a codificação UTF8. O nome do arquivo deve ter o seguinte formato para que o Windows PowerShell possa detectá-lo como um arquivo de ajuda de cmdlet.

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. Adicione os cabeçalhos XML a seguir ao arquivo de texto. Lembre-se de que o arquivo será validado em relação ao esquema MAML (linguagem de modelagem de vários agentes). Atualmente, o Windows PowerShell não fornece nenhuma ferramenta para validar o arquivo.

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. Adicione um nó de comando ao arquivo de ajuda de cmdlet para cada cmdlet no assembly. Cada nó dentro do nó de comando se relaciona às diferentes seções do tópico de ajuda do cmdlet.

   A tabela a seguir lista o elemento XML para cada nó, seguido por uma descrição de cada nó.

   |Nó|Descrição|
   |----------|-----------------|
   |`<details>`|Adiciona conteúdo para as seções nome e Sinopse do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar o nome do cmdlet e Sinopse](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).|
   |`<maml:description>`|Adiciona o conteúdo da seção Descrição do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar a descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md).|
   |`<command:syntax>`|Adiciona o conteúdo da seção de sintaxe do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar sintaxe a um tópico de ajuda de cmdlet](./how-to-add-syntax-to-a-cmdlet-help-topic.md).|
   |`<command:parameters>`|Adiciona o conteúdo da seção de parâmetros do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar parâmetros a um tópico de ajuda de cmdlet](./how-to-add-parameter-information.md).|
   |`<command:inputTypes>`|Adiciona o conteúdo da seção entradas do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar tipos de entrada a um tópico de ajuda de cmdlet](./how-to-add-input-types-to-a-cmdlet-help-topic.md).|
   |`<command:returnValues>`|Adiciona o conteúdo da seção de saídas do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar valores de retorno a um tópico de ajuda de cmdlet](./how-to-add-return-values-to-a-cmdlet-help-topic.md).|
   |`<maml:alertset>`|Adiciona o conteúdo à seção observações do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar anotações a um tópico de ajuda do cmdlet](./how-to-add-notes-to-a-cmdlet-help-topic.md).|
   |`<command:examples>`|Adiciona o conteúdo para a seção exemplos do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar exemplos a um tópico de ajuda de cmdlet](./how-to-add-examples-to-a-cmdlet-help-topic.md).|
   |`<maml:relatedLinks>`|Adiciona o conteúdo da seção LINKS relacionados do tópico de ajuda do cmdlet. Para obter mais informações, consulte [como adicionar links relacionados a um tópico de ajuda de cmdlet](./how-to-add-related-links-to-a-cmdlet-help-topic.md).|

## <a name="example"></a>Exemplo

 Aqui está um exemplo de um nó de comando que inclui os nós das várias seções do tópico de ajuda do cmdlet.

```xml
<command:command
  xmlns:maml="https://schemas.microsoft.com/maml/2004/10"
  xmlns:command="https://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="https://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a>Consulte Também

 [Como adicionar o nome do cmdlet e Sinopse](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [Como adicionar a descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md)

 [Como adicionar sintaxe a um tópico de ajuda do cmdlet](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [Como adicionar parâmetros a um tópico de ajuda de cmdlet](./how-to-add-parameter-information.md)

 [Como adicionar tipos de entrada a um tópico de ajuda do cmdlet](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [Como adicionar valores retornados a um tópico de ajuda do cmdlet](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [Como adicionar anotações a um tópico de ajuda de cmdlet](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [Como adicionar exemplos a um tópico de ajuda do cmdlet](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [Como adicionar links relacionados a um tópico de ajuda do cmdlet](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [SDK do Windows PowerShell](../windows-powershell-reference.md)
