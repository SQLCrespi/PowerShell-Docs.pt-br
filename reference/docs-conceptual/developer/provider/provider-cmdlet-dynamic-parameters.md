---
title: Parâmetros dinâmicos do cmdlet do provedor | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f1069f7-8fa8-4622-9e2c-af29b0b961c2
caps.latest.revision: 6
ms.openlocfilehash: a50de014988336c473c565b506a73de1c864d7e0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359945"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Parâmetros dinâmicos de cmdlet do provedor

Os provedores podem definir parâmetros dinâmicos que são adicionados a um cmdlet de provedor quando o usuário especifica um determinado valor para um dos parâmetros estáticos do cmdlet. Por exemplo, um provedor pode adicionar diferentes parâmetros dinâmicos com base em qual caminho o usuário especifica quando chama os cmdlets de provedor `Get-Item` ou `Set-Item`.

## <a name="dynamic-parameter-methods"></a>Métodos de parâmetro dinâmico

Os parâmetros dinâmicos são definidos pela implementação de um dos métodos de parâmetro dinâmico, como os métodos [System. Management. Automation. Provider. docmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) e [System. Management. Automation. Provider. docmdletprovider. Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s. Esses métodos retornam um objeto que tem propriedades públicas que são decoradas com atributos semelhantes aos de cmdlets autônomos. Aqui está um exemplo de uma implementação do método [System. Management. Automation. Provider. createcmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) extraído do provedor de certificados:

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

Ao contrário dos parâmetros estáticos dos cmdlets do provedor, você pode especificar as características desses parâmetros da mesma maneira que os parâmetros são definidos em cmdlets autônomos. Aqui está um exemplo de uma classe de parâmetro dinâmico obtida do provedor de certificado:

```csharp
internal sealed class CertificateProviderDynamicParameters
{
  /// <summary>
  /// Dynamic parameter the controls whether we only return
  /// code signing certs.
  /// </summary>
  [Parameter()]
  public SwitchParameter CodeSigningCert
  {
    get
    {
      {
        return codeSigningCert;
      }
    }

    set
    {
      {
        codeSigningCert = value;
      }
    }
  }

    private SwitchParameter codeSigningCert = new SwitchParameter();
}
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Aqui está uma lista dos parâmetros estáticos que podem ser usados para adicionar parâmetros dinâmicos.

`Clear-Content` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet Clear-Clear implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Clearcontentdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

`Clear-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Clear-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. Clearitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

`Clear-ItemProperty` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Clear-ItemProperty` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

`Copy-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path`, `Destination`e `Recurse` do cmdlet `Copy-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

Cmdlet Get-ChildItems você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Recurse` do cmdlet `Get-ChildItem` implementando os métodos [System. Management. Automation. Provider. Containercmdletprovider. Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) e [System. Management. Automation. Provider. Containercmdletprovider. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) .

`Get-Content` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Get-Content` implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreaderdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) .

`Get-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Get-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

`Get-ItemProperty` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Name` do cmdlet `Get-ItemProperty` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

`Invoke-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Invoke-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

`Move-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Destination` do cmdlet `Move-Item` implementando o método [System. Management. Automation. Provider. Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) .

`New-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path`, `ItemType`e `Value` do cmdlet `New-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Newitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) .

`New-ItemProperty` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path`, `Name`, `PropertyType`e `Value` do cmdlet `New-ItemProperty` implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Newpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

`New-PSDrive` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo objeto [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) retornado pelo cmdlet `New-PSDrive` implementando o método [System. Management. Automation. Provider. Drivecmdletprovider. Newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

`Remove-Item` você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Recurse` do cmdlet `Remove-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Removeitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

`Remove-ItemProperty` você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Name` do cmdlet `Remove-ItemProperty` implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Removepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

`Rename-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `NewName` do cmdlet `Rename-Item` implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Renameitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

`Rename-ItemProperty` você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path`, `Name`e `NewName` do cmdlet `Rename-ItemProperty` implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Renamepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

`Set-Content` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Set-Content` implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) .

`Set-Item` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Value` do cmdlet `Set-Item` implementando o método [System. Management. Automation. Provider. docmdletprovider. Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

`Set-ItemProperty` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelos parâmetros `Path` e `Value` do cmdlet `Set-Item` implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Setpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

`Test-Path` cmdlet, você pode definir parâmetros dinâmicos que são disparados pelo parâmetro `Path` do cmdlet `Test-Path` implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

## <a name="see-also"></a>Consulte Também

[Escrevendo um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)