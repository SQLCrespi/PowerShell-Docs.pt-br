---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 19a7020059f0a647d8460cfc9fb7f27a22605760
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890123"
---
# Get-PackageProvider

## SINOPSE
Retorna uma lista de provedores de pacote que estão conectados a Gerenciamento de Pacotes.

## SYNTAX

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-packageprovider** retorna uma lista de provedores de pacote que estão conectados a gerenciamento de pacotes.
Exemplos desses provedores incluem PSModule, NuGet e Chocolatey.
Você pode filtrar os resultados com base em todos ou em parte de um ou mais nomes de provedor.

## EXEMPLOS

### Exemplo 1: obter todos os provedores de pacote carregados no momento

```
PS C:\> Get-PackageProvider
```

Esse comando obtém uma lista de todos os provedores de pacote carregados no computador local.

### Exemplo 2: obter todos os provedores de pacote disponíveis

```
PS C:\> Get-PackageProvider -ListAvailable
```

Esse comando obtém uma lista de todos os provedores de pacote que estão disponíveis no computador local.

### Exemplo 3: obter dinamicamente um provedor de pacote

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

Esse comando instala automaticamente o provedor de Chocolatey se o seu computador não tiver o provedor de Chocolatey instalado.

## PARAMETERS

### -Force

Indica que esse cmdlet força todas as outras ações com esse cmdlet que podem ser forçadas.
Em **Get-packageprovider**, isso significa que o parâmetro *Force* age da mesma forma que o parâmetro *ForceBootstrap* .

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

### -ListAvailable

Obtém todos os provedores instalados.
**Get-packageprovider** Obtém o provedor em caminhos listados na variável de ambiente **PSModulePath** , bem como as pastas de assembly do provedor de pacote:

**$env:P rogramFiles\PackageManagement\ProviderAssemblies * * * * $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**

Sem esse parâmetro, **Get-packageprovider** obtém somente os provedores carregados na sessão atual.

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

### -Name

Especifica um ou mais nomes de provedor ou nomes de provedor parciais.
Separe vários nomes de provedor com vírgulas.
Os valores válidos para esse parâmetro incluem nomes de provedores que você instalou com pacotes; O PackageManagement é fornecido com um conjunto de provedores padrão, incluindo os provedores **PSModule** e **MSI** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### Packageprovider []

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

