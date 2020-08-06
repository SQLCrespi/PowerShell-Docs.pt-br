---
title: Modo de exibição de lista (GroupBy) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7956d13e196454a3f6da185e9be74f9d3cb8ef63
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773395"
---
# <a name="list-view-groupby"></a>Exibição de lista (GroupBy)

Este exemplo mostra como implementar um modo de exibição de lista que separa as linhas da lista em grupos. Esta exibição de lista exibe as propriedades do [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) retornados pelo cmdlet [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) . Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).

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

- O elemento [GroupBy](./viewselectedby-element-format.md) que define como um novo grupo de objetos é exibido.

- O elemento [ListControl](./listcontrol-element-format.md) que define qual propriedade é exibida pela exibição.

- O elemento [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) que define o que é exibido em uma linha da exibição de lista.

- O elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) que define qual propriedade é exibida.

## <a name="example"></a>Exemplo

O XML a seguir define um modo de exibição de lista que inicia um novo grupo sempre que o valor da propriedade [System. ServiceProcess. ServiceController. status](/dotnet/api/System.ServiceProcess.ServiceController.Status) é alterado. Quando cada grupo é iniciado, é exibido um rótulo personalizado que inclui o novo valor da propriedade.

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
      <ListControl>
        <ListEntries>
          <ListEntry>
            <ListItems>
              <ListItem>
                <PropertyName>Name</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>DisplayName</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>ServiceType</PropertyName>
              </ListItem>
            </ListItems>
          </ListEntry>
        </ListEntries>
      </ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

O exemplo a seguir mostra como o Windows PowerShell exibe o [System. ServiceProcess. ServiceController? Objetos displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) depois que esse arquivo de formato é carregado. As linhas em branco adicionadas antes e depois do rótulo do grupo são automaticamente adicionadas pelo Windows PowerShell.

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>Consulte Também

[Exemplos de arquivos de formatação](./examples-of-formatting-files.md)

[Escrever um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
