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
ms.openlocfilehash: 9e70fbeaef61d04e66f16d06519742ff2f679df6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564216"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Parâmetros dinâmicos de cmdlet do provedor

Os provedores podem definir parâmetros dinâmicos que são adicionados a um cmdlet de provedor quando o usuário especifica um determinado valor para um dos parâmetros estáticos do cmdlet. Por exemplo, um provedor pode adicionar diferentes parâmetros dinâmicos com base em qual caminho o usuário especifica ao chamar `Get-Item` os `Set-Item` cmdlets do provedor ou.

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

`Clear-Content`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do cmdlet Clear-Clear implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Clearcontentdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

`Clear-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Clear-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Clearitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

`Clear-ItemProperty`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Clear-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

`Copy-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Destination` parâmetros, e `Recurse` do `Copy-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

Cmdlet Get-ChildItems você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Recurse` parâmetros e do `Get-ChildItem` cmdlet implementando os métodos [System. Management. Automation. Provider. Containercmdletprovider. Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) e [System. Management. Automation. Provider. Containercmdletprovider. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) .

`Get-Content`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Get-Content` cmdlet implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentreaderdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) .

`Get-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Get-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

`Get-ItemProperty`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Name` parâmetros e do `Get-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

`Invoke-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Invoke-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

`Move-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Destination` parâmetros e do `Move-Item` cmdlet implementando o método [System. Management. Automation. Provider. Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) .

`New-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `ItemType` parâmetros, e `Value` do `New-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Newitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) .

`New-ItemProperty`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Name` parâmetros,, `PropertyType` e `Value` do `New-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Newpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

`New-PSDrive`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo objeto [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) retornado pelo `New-PSDrive` cmdlet implementando o método [System. Management. Automation. Provider. Drivecmdletprovider. Newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

`Remove-Item`Você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Recurse` parâmetros e do `Remove-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Removeitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

`Remove-ItemProperty`Você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Name` parâmetros e do `Remove-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Removepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

`Rename-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `NewName` parâmetros e do `Rename-Item` cmdlet implementando o método [System. Management. Automation. Provider. Containercmdletprovider. Renameitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

`Rename-ItemProperty`Você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Name` parâmetros, e `NewName` do `Rename-ItemProperty` cmdlet implementando o método [System. Management. Automation. Provider. Idynamicpropertycmdletprovider. Renamepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

`Set-Content`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Set-Content` cmdlet implementando o método [System. Management. Automation. Provider. Icontentcmdletprovider. Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) .

`Set-Item`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Value` parâmetros e do `Set-Item` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

`Set-ItemProperty`cmdlet você pode definir parâmetros dinâmicos que são disparados pelos `Path` `Value` parâmetros e do `Set-Item` cmdlet implementando o método [System. Management. Automation. Provider. Ipropertycmdletprovider. Setpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

`Test-Path`cmdlet você pode definir parâmetros dinâmicos que são disparados pelo `Path` parâmetro do `Test-Path` cmdlet implementando o método [System. Management. Automation. Provider. docmdletprovider. Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

## <a name="see-also"></a>Consulte Também

[Escrever um provedor do Windows PowerShell](./writing-a-windows-powershell-provider.md)
