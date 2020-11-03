---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 8b900f8e7ff2583e20d359fd3d15aee653b9c1d6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193534"
---
# Import-PackageProvider

## SINOPSE
Adiciona Gerenciamento de Pacotes provedores de pacote à sessão atual.

## SYNTAX

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

O `Import-PackageProvider` cmdlet adiciona um ou mais provedores de pacote à sessão atual.
O provedor que você importar deve estar instalado no computador local.

Para obter uma lista de provedores disponíveis, execute `Get-PackageProvider -ListAvailable` .
Observe que um nome de provedor de pacote pode ser diferente do nome do módulo.

Devido a motivos de segurança, o **PackageManagement** exige que os provedores baseados em C# contenham um `provider.manifest` . Para obter mais informações sobre como criar um provedor com `provider.manifest` injetado, consulte os `.csproj` arquivos de projeto em [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .

## EXEMPLOS

### Exemplo 1: importar um provedor de pacote do computador local

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

Esse comando importa o provedor do NuGet depois que ele tiver sido instalado no computador local.

### Exemplo 2: importar uma versão específica de um provedor de pacote

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

Esse comando localiza, instala e importa uma versão específica do provedor de pacotes NuGet.

## PARAMETERS

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.
Importa novamente um provedor de pacote.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceBootstrap

Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima permitida do provedor de pacote que você deseja importar. Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Especifica a versão mínima permitida do provedor de pacote que você deseja importar. Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais alta disponível do pacote que também atende a qualquer versão máxima especificada usando o parâmetro *MaximumVersion* .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um ou mais nomes de provedor de pacote. Caracteres curinga não são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata do provedor de pacote que você deseja importar. Se você não adicionar esse parâmetro, `Import-PackageProvider` o importará a versão mais recente disponível do provedor que também atende a qualquer versão máxima especificada usando o parâmetro **MaximumVersion** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PackageManagement. Implementation. Packageprovider

É possível canalizar um objeto **packageprovider** retornado por `Get-PackageProvider` into `Import-PackageProvider` .

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Get-PackageProvider](Get-PackageProvider.md)

