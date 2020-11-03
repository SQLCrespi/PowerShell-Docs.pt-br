---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 42a2b37144d9af188a7204500227fddf4827bdf9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194444"
---
# Update-Module

## SINOPSE
Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.

## SYNTAX

### Tudo

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Update-Module` cmdlet instala a versão mais recente de um módulo de uma galeria online. Você será solicitado a confirmar a atualização antes de ela ser instalada. As atualizações são instaladas somente para módulos que foram instalados no computador local com o `Install-Module` . `Update-Module` procura `$env:PSModulePath` módulos instalados.

`Update-Module` sem parâmetros especificados atualiza todos os módulos instalados. Para especificar um módulo a ser atualizado, use o parâmetro **Name** . Você pode atualizar para a versão específica de um módulo usando o parâmetro **RequiredVersion** .

Se um módulo instalado já for a versão mais recente, o módulo não será atualizado. Se o módulo não for encontrado em `$env:PSModulePath` , um erro será exibido.

Para exibir os módulos instalados, use `Get-InstalledModule` .

## EXEMPLOS

### Exemplo 1: atualizar todos os módulos

Este exemplo atualiza todos os módulos instalados para a versão mais recente em uma galeria online.

```powershell
Update-Module
```

### Exemplo 2: atualizar um módulo por nome

Este exemplo atualiza um módulo específico para a versão mais recente em uma galeria online.

```powershell
Update-Module -Name SpeculationControl
```

`Update-Module` usa o parâmetro **Name** para atualizar um módulo específico, **SpeculationControl** .

### Exemplo 3: exibir as execuções de Update-Module de hipóteses

Este exemplo faz um cenário de hipóteses para mostrar o que acontece se `Update-Module` for executado. O comando não é executado.

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

`Update-Module` usa o parâmetro **WhatIf** exibir o que aconteceria se `Update-Module` fosse executado.

### Exemplo 4: atualizar um módulo para uma versão especificada

Neste exemplo, um módulo é atualizado para uma versão específica. A versão deve existir na galeria online ou um erro é exibido.

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl** . O parâmetro **RequiredVersion** especifica a versão, **1.0.14** .

### Exemplo 5: atualizar um módulo sem confirmação

Este exemplo não solicita confirmação para atualizar o módulo para a versão mais recente de uma galeria online. Se o módulo já estiver instalado, o parâmetro **Force** reinstalará o módulo.

```powershell
Update-Module -Name SpeculationControl -Force
```

`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl** . O parâmetro **Force** atualiza o módulo sem solicitar a confirmação do usuário.

## PARAMETERS

### -AcceptLicense

Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.

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

### -AllowPrerelease

Permite que você atualize um módulo com o módulo mais recente marcado como um pré-lançamento.

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

### -Confirm

Solicita a confirmação antes de executar `Update-Module` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para atualizar um módulo.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Força uma atualização de cada módulo especificado sem solicitar confirmação. Se o módulo já estiver instalado, **Force** reinstalará o módulo.

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

Especifica a versão máxima de um único módulo a ser atualizado. Você não poderá adicionar esse parâmetro se estiver tentando atualizar vários módulos. Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de um ou mais módulos a serem atualizados. `Update-Module` pesquisa `$env:PSModulePath` os módulos a serem atualizados. Se nenhuma correspondência for encontrada em `$env:PSModulePath` para o nome do módulo especificado, ocorrerá um erro.

Caracteres curinga são aceitos em nomes de módulo. Se você adicionar caracteres curinga ao nome especificado e nenhuma correspondência for encontrada, nenhum erro ocorrerá.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential

Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata para a qual o módulo instalado existente será atualizado. A versão especificada por **RequiredVersion** deve existir na galeria online ou um erro é exibido. Se mais de um módulo for atualizado em um único comando, você não poderá usar **RequiredVersion** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Especifica o escopo de instalação do módulo. Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser** . Se o **escopo** não for especificado, a atualização será instalada no escopo **CurrentUser** .

O escopo **AllUsers** requer permissões elevadas e instala módulos em um local que pode ser acessado por todos os usuários do computador:

`$env:ProgramFiles\PowerShell\Modules`

O **CurrentUser** não requer permissões elevadas e instala módulos em um local acessível somente para o usuário atual do computador:

`$home\Documents\PowerShell\Modules`

Quando nenhum **escopo** é definido, o padrão é definido com base na versão do PowerShellGet.

- No PowerShellGet versões 2.0.0 e superiores, o padrão é **CurrentUser** , que não requer elevação para a instalação.
- Nas versões do PowerShellGet 1. x, o padrão é **AllUsers** , o que requer elevação para a instalação.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se `Update-Module` for executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

### System.String

### System. Management. Automation. PSCredential

### System.Uri

## SAÍDAS

### System.Object

## OBSERVAÇÕES

Para o PowerShell versão 6,0 e superior, o escopo de instalação padrão é sempre **CurrentUser** .
Atualizações de módulo para **CurrentUser** , `$home\Documents\PowerShell\Modules` , não precisam de permissões elevadas. As atualizações de módulo para **AllUsers** , `$env:ProgramFiles\PowerShell\Modules` , precisam de permissões elevadas.

`Update-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.

Se o módulo especificado com o parâmetro **Name** não tiver sido instalado usando o `Install-Module` , ocorrerá um erro.

Você só pode executar `Update-Module` em módulos que você instalou da galeria online executando `Install-Module` .

Se `Update-Module` as tentativas de atualizar os binários que estão em uso, `Update-Module` o retorna um erro que identifica os processos de problema. O usuário é informado para tentar novamente `Update-Module` depois que os processos são interrompidos.

## LINKS RELACIONADOS

[Find-Module](Find-Module.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Uninstall-Module](Uninstall-Module.md)
