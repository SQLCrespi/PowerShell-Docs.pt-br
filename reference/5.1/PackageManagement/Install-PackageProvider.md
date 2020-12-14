---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 8ab8a0fd505bca7cda5cef17a09baa9f7e571dd4
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892790"
---
# Install-PackageProvider

## SINOPSE
Instala um ou mais provedores de pacote de Gerenciamento de Pacotes.

## SYNTAX

### PackageBySearch (padrão)

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### PackageByInputObject

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Install-PackageProvider` cmdlet instala provedores de gerenciamento de pacotes correspondentes que estão disponíveis em fontes de pacote registradas com **PowerShellGet**. Por padrão, isso inclui módulos disponíveis no Windows Galeria do PowerShell com a marca **PackageManagement** . O provedor de Gerenciamento de Pacotes **PowerShellGet** é usado para localizar provedores nesses repositórios.

Esse cmdlet também instala os provedores de Gerenciamento de Pacotes correspondentes que estão disponíveis usando o aplicativo de inicialização Gerenciamento de Pacotes.

Esse cmdlet também instala os provedores de Gerenciamento de Pacotes correspondentes que estão disponíveis no repositório de blob do Azure Gerenciamento de Pacotes. Use o provedor de bootstrapper para localizá-los e instalá-los.

Para executar a primeira vez, o PackageManagement requer uma conexão com a Internet para baixar o provedor de pacote NuGet. No entanto, se o computador não tiver uma conexão com a Internet e você precisar usar o provedor NuGet ou PowerShellGet, você poderá baixá-los em outro computador e copiá-los para o computador de destino. Use as seguintes etapas para fazer isso:

1. Execute `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` para instalar o provedor de um computador com uma conexão com a Internet.
1. Após a instalação, você pode encontrar o provedor instalado no `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` ou no `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` .
1. Coloque a `<ProviderName>` pasta, que, nesse caso, é a pasta NuGet, no local correspondente no computador de destino. Se o computador de destino for um nano Server, você precisará executar `Install-PackageProvider` do nano Server para baixar os binários do NuGet corretos.
1. Reinicie o PowerShell para carregar automaticamente o provedor de pacotes. Como alternativa, execute `Get-PackageProvider -ListAvailable` para listar todos os provedores de pacote disponíveis no computador.
   Em seguida, use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` para importar o provedor para a sessão atual do Windows PowerShell.

## EXEMPLOS

### Exemplo 1: instalar um provedor de pacote do Galeria do PowerShell

Esse comando instala o provedor de pacote do do Galeria do PowerShell.

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### Exemplo 2: instalar uma versão especificada de um provedor de pacote

Este exemplo instala uma versão especificada do provedor de pacote NuGet.

O primeiro comando localiza todas as versões do provedor de pacote chamado NuGet.
O segundo comando instala uma versão especificada do provedor de pacote NuGet.

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### Exemplo 3: localizar um provedor e instalá-lo

Este exemplo usa `Find-PackageProvider` e o pipeline para pesquisar o provedor de registro e instalá-lo.

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### Exemplo 4: instalar um provedor na pasta de módulo do usuário atual

Esse comando instala um provedor de pacote para `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` que somente o usuário atual possa usá-lo.

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## PARAMETERS

### -Próprias versões

Indica que esse cmdlet instala todas as versões disponíveis do provedor de pacote. Por padrão, `Install-PackageProvider` o retorna apenas a versão mais alta disponível.

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

### -Credential

Especifica uma conta de usuário que tem permissão para instalar provedores de pacote.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet força todas as ações com este cmdlet que podem ser forçadas. Atualmente, isso significa que o parâmetro **Force** age da mesma forma que o parâmetro **ForceBootstrap** .

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

Indica que esse cmdlet instala automaticamente o provedor de pacote.

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

### -InputObject

Especifica um objeto **SoftwareIdentity** . Use o `Find-PackageProvider` cmdlet para obter um objeto **SoftwareIdentity** para o pipe `Install-PackageProvider` .

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima permitida do provedor de pacote que você deseja instalar. Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do provedor.

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Especifica a versão mínima permitida do provedor de pacote que você deseja instalar. Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do pacote que também atende a qualquer requisito especificado pelo parâmetro *MaximumVersion* .

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um ou mais nomes de módulo de provedor de pacote. Separe vários nomes de pacote com vírgulas.
Não há suporte para caracteres curinga.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata permitida do provedor de pacote que você deseja instalar. Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do provedor que também atende a qualquer versão máxima especificada pelo parâmetro **MaximumVersion** .

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Escopo

Especifica o escopo de instalação do provedor. Os valores aceitáveis para esse parâmetro são:

- **AllUsers** – instala provedores em um local que pode ser acessado por todos os usuários do computador.
  Por padrão, isso é **$env:P rogramfiles\packagemanagement\providerassemblies.**

- **CurrentUser** – instala provedores em um local onde eles só podem ser acessados pelo usuário atual. Por padrão, isso é **$env: LOCALAPPDATA\PackageManagement\ProviderAssemblies.**

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Especifica uma ou mais origens de pacote. Use o `Get-PackageSource` cmdlet para obter uma lista de fontes de pacote disponíveis.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### Microsoft. PackageManagement. Packaging. SoftwareIdentity

É possível canalizar um objeto **SoftwareIdentity** para esse cmdlet. Use `Find-PackageProvider` para obter um objeto **SoftwareIdentity** que pode ser canalizado no `Install-PackageProvider` .

## SAÍDAS

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)
