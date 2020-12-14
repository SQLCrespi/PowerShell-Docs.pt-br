---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 300d3388c39a86cb732d50404ad7d8c28bd3034e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892184"
---
# Register-PSRepository

## SINOPSE
Registra um repositório do PowerShell.

## SYNTAX

### NameParameterSet (padrão)

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### PSGalleryParameterSet

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

O `Register-PSRepository` cmdlet registra o repositório padrão para módulos do PowerShell. Depois que um repositório é registrado, você pode referenciá-lo `Find-Module` dos `Install-Module` `Publish-Module` cmdlets, e. O repositório registrado torna-se o repositório padrão no `Find-Module` e no `Install-Module` .

Repositórios registrados são específicos ao usuário. Eles não são registrados em um contexto de todo o sistema.

Cada repositório registrado é associado a um provedor de pacote OneGet, que é especificado com o parâmetro **PackageManagementProvider** . Cada provedor de OneGet é projetado para interagir com um tipo específico de repositório. Por exemplo, o provedor de NuGet foi projetado para interagir com repositórios baseados em NuGet. Se um provedor OneGet não for especificado durante o registro, o PowerShellGet tentará encontrar um provedor OneGet que possa manipular o local de origem especificado.

## EXEMPLOS

### Exemplo 1: registrar um repositório

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

O primeiro comando é registrado `https://www.myget.org/F/powershellgetdemo/` como um repositório para o usuário atual. Depois que o myNuGetSource é registrado, você pode referenciá-lo explicitamente ao procurar, instalar e publicar módulos. Como o parâmetro **PackageManagementProvider** não está especificado, o repositório não está explicitamente associado a um provedor de pacotes OneGet, portanto, o PowerShellGet sonda os provedores de pacotes disponíveis e os associa ao provedor do NuGet.

O segundo comando obtém repositórios registrados e exibe os resultados.

## PARAMETERS

### -Credential

Especifica as credenciais de uma conta que tem direitos para registrar um repositório.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallationPolicy

Especifica a política de instalação. Os valores válidos são: confiável, não confiável. O valor padrão não é confiável.

A política de instalação de um repositório especifica o comportamento do PowerShell ao instalar por meio desse repositório. Ao instalar módulos de um repositório não confiável, será solicitada a confirmação do usuário.

Você pode definir o **InstallationPolicy** com o `Set-PSRepository` cmdlet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome do repositório a ser registrado. Você pode usar esse nome para especificar o repositório em cmdlets, como `Find-Module` e `Install-Module` .

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider

Especifica um provedor de pacote OneGet. Se você não especificar um valor para esse parâmetro, o PowerShellGet sondará os provedores de pacote disponíveis e associará esse repositório ao primeiro provedor de pacote que indica que ele pode lidar com o repositório.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
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

### -PublishLocation

Especifica o URI do local de publicação. Por exemplo, para repositórios baseados em NuGet, o local de publicação é semelhante a `https://someNuGetUrl.com/api/v2/Packages` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptPublishLocation

Especifica o local de publicação do script.

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptSourceLocation

Especifica o local de origem do script.

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceLocation

Especifica o URI para descobrir e instalar os módulos deste repositório. Um URI pode ser um feed de servidor do NuGet (situação mais comum), HTTP, HTTPS, FTP ou local do arquivo.

Por exemplo, para repositórios baseados em NuGet, o local de origem é semelhante a `https://someNuGetUrl.com/api/v2` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSCredential

### System.Uri

## SAÍDAS

### System.Object

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Get-PSRepository](Get-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
