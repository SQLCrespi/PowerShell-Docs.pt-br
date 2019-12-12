---
title: Criando controles personalizados | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363375"
---
# <a name="creating-custom-controls"></a>Criar controles personalizados

Os controles personalizados são os componentes mais flexíveis de um arquivo de formatação. Ao contrário das exibições de tabela, lista e amplas que definem uma estrutura formal de dados, como uma tabela de dados, os controles personalizados permitem que você defina como uma parte de dados individual é exibida. Você pode definir um conjunto comum de controles personalizados que estão disponíveis para todas as exibições do arquivo de formatação, pode definir controles personalizados que estão disponíveis para uma exibição específica ou pode definir um conjunto de controles que estão disponíveis para um grupo de objetos.

## <a name="custom-control-example"></a>Exemplo de controle personalizado

O exemplo a seguir mostra um controle personalizado que é definido no arquivo Certificates. Format. ps1xml. Esse controle personalizado é usado para separar os objetos [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) exibidos em uma exibição de tabela.

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a>Consulte Também

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
