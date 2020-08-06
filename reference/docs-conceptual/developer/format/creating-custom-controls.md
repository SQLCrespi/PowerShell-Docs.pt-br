---
title: Criando controles personalizados | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c36fa9b778e01501a3c88f735cdefdfbb04411a0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786111"
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
