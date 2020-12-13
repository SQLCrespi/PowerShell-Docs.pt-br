---
ms.date: 09/13/2016
ms.topic: reference
title: Exibição ampla (Básica)
description: Exibição ampla (Básica)
ms.openlocfilehash: bfc647da9b78fcd22aac83cf330e466b6759471c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667684"
---
# <a name="wide-view-basic"></a>Exibição ampla (Básica)

Este exemplo mostra como implementar uma exibição ampla básica que exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) retornados pelo `Get-Service` cmdlet. Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).

### <a name="to-load-this-formatting-file"></a>Para carregar este arquivo de formatação

1. Copie o XML da seção de exemplo deste tópico em um arquivo de texto.

2. Salve o arquivo de texto. Certifique-se de adicionar a `format.ps1xml` extensão ao arquivo para identificá-lo como um arquivo de formatação.

3. Abra o Windows PowerShell e execute o seguinte comando para carregar o arquivo de formatação na sessão atual: `Update-formatdata -prependpath PathToFormattingFile` .

   > [!WARNING]
   > Esse arquivo de formatação define a exibição de um objeto que já está definido por um arquivo de formatação do Windows PowerShell. Você deve usar o `prependPath` parâmetro ao executar o cmdlet e não pode carregar esse arquivo de formatação como um módulo.

## <a name="demonstrates"></a>Demonstra

Esse arquivo de formatação demonstra os seguintes elementos XML:

- O elemento [Name](./name-element-for-view-format.md) para a exibição.

- O elemento [ViewSelectedBy](./viewselectedby-element-format.md) que define quais objetos são exibidos pela exibição.

- O elemento [WideItem](./wideitem-element-for-widecontrol-format.md) que define qual propriedade é exibida pela exibição.

## <a name="example"></a>Exemplo

O XML a seguir define uma exibição ampla que exibe o valor da propriedade [System. ServiceProcess. ServiceController. ServiceName](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) .

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado.

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a>Consulte Também

[Exemplos de arquivos de formatação](./examples-of-formatting-files.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
