---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: 7bcf9073b31da8470fe2b542f90ae35c20dba36d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892463"
---
# Find-Command

## SINOPSE
Localiza comandos do PowerShell em módulos.

## SYNTAX

### Tudo

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Find-Command` cmdlet localiza comandos do PowerShell, como cmdlets, aliases, funções e fluxos de trabalho. `Find-Command` pesquisa módulos em repositórios registrados.

Para cada comando encontrado por `Find-Command` , um objeto **PSGetCommandInfo** é retornado. O objeto **PSGetCommandInfo** pode ser enviado ao pipeline para o `Install-Module` cmdlet.
`Install-Module` instala o módulo que contém o comando.

## EXEMPLOS

### Exemplo 1: localizar todos os comandos em um repositório especificado

O `Find-Command` cmdlet pesquisa um repositório registrado em busca de módulos.

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

`Find-Command` usa o parâmetro **Repository** para especificar o nome de um repositório registrado. Os objetos são enviados pelo pipeline. `Select-Object` recebe os objetos e usa o **primeiro** parâmetro para exibir os 10 primeiros resultados.

### Exemplo 2: localizar um comando por nome

`Find-Command` pode usar o nome de um comando para localizar o módulo em um repositório. É possível que exista um nome de comando em vários **modulenames**.

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

`Find-Command` usa o parâmetro **Repository** para pesquisar o **PSGallery**. O parâmetro **Name** especifica o comando **Get-TargetResource**.

### Exemplo 3: localizar comandos por nome e instalar o módulo

`Find-Command` pode localizar o comando e o módulo e, em seguida, enviar o objeto para `Install-Module` . Se um comando for incluído em vários módulos, use o `Find-Command` parâmetro **Module-Name** do cmdlets.
Caso contrário, os módulos podem ser instalados e você não deseja instalar.

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

`Find-Command` usa o parâmetro **Name** para especificar o comando **Get-TargetResource**. O parâmetro **Repository** pesquisa o **PSGallery**. O parâmetro **ModuleName** especifica o módulo que você deseja instalar, **SystemLocaleDsc**. O objeto é enviado ao pipeline para o `Install-Module` e o módulo é instalado. Após a conclusão da instalação, você pode usar `Get-InstalledModule` o para exibir os resultados.

### Exemplo 4: localizar um comando e salvar seu módulo

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

`Find-Command` usa os parâmetros **Name** e **Repository** para pesquisar o comando **Invoke-ScriptAnalyzer** no repositório **PSGallery** . O objeto é enviado ao pipeline para `Save-Module` . O parâmetro **path** determina o local para salvar o módulo. **Verbose** é um parâmetro opcional, mas exibe a saída de status no console do PowerShell. A saída detalhada é benéfica para solução de problemas.

## PARAMETERS

### -AllowPrerelease

Inclui módulos marcados como um pré-lançamento nos resultados.

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

### -Próprias versões

Indica que este cmdlet obtém todas as versões de um módulo.

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

### -Filter

Localiza módulos com base na sintaxe de pesquisa do provedor de **PackageManagement** . Por exemplo, especifique as palavras a serem pesquisadas nas propriedades **ModuleName** e **Description** .

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

### -MaximumVersion

Especifica a versão máxima do módulo a ser incluída nos resultados. Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

Especifica a versão mínima do módulo a ser incluída nos resultados. Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

### -ModuleName

Especifica o nome de um módulo para procurar por comandos. O padrão é todos os módulos.

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

Especifica o nome do comando a ser pesquisado em um repositório. Use vírgulas para separar uma matriz de nomes de comando.

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

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.

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

Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.

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

### -Repositório

Especifica o repositório para procurar por comandos. Use vírgulas para separar uma matriz de nomes de repositório. O padrão é todos os repositórios.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão do módulo a ser incluída nos resultados.

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

### -Tag

Especifica as marcas que categorizam os módulos em um repositório. Use vírgulas para separar uma matriz de marcas.

```yaml
Type: System.String[]
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

## SAÍDAS

### PSGetCommandInfo

`Find-Command` gera um objeto **PSGetCommandInfo** .

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Save-Module](Save-Module.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Desinstalar-módulo](Uninstall-Module.md)

