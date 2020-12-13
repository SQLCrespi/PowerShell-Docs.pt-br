---
ms.date: 09/13/2016
ms.topic: reference
title: Criar controles personalizados
description: Criar controles personalizados
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668041"
---
# <a name="creating-custom-controls"></a>Criar controles personalizados

Os controles personalizados são os componentes mais flexíveis de um arquivo de formatação. Ao contrário das exibições de tabela, lista e amplas que definem uma estrutura formal de dados, como uma tabela de dados, os controles personalizados permitem que você defina como uma parte de dados individual é exibida. Você pode definir um conjunto comum de controles personalizados que estão disponíveis para todas as exibições do arquivo de formatação, pode definir controles personalizados que estão disponíveis para uma exibição específica ou pode definir um conjunto de controles que estão disponíveis para um grupo de objetos.

## <a name="custom-control-example"></a>Exemplo de controle personalizado

O exemplo a seguir mostra um controle personalizado que é definido no arquivo XML de Certificates.Format.ps1. Esse controle personalizado é usado para separar os objetos [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) exibidos em uma exibição de tabela.

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

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
