---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: 5e210a626c0b64884bb95807a51d712061276122
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "93195111"
---
# Install-Module

## SINOPSE
Baixa um ou mais módulos de um repositório e os instala no computador local.

## SYNTAX

### NameParameterSet (padrão)

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Install-Module` cmdlet obtém um ou mais módulos que atendem aos critérios especificados de um repositório online. O cmdlet verifica se os resultados da pesquisa são módulos válidos e copia as pastas do módulo para o local de instalação. Os módulos instalados não são importados automaticamente após a instalação.
Você pode filtrar qual módulo está instalado com base nas versões mínima, máxima e exata dos módulos especificados.

Se o módulo que está sendo instalado tiver o mesmo nome ou versão, ou contiver comandos em um módulo existente, as mensagens de aviso serão exibidas. Depois de confirmar que deseja instalar o módulo e substituir os avisos, use os `-Force` `-AllowClobber` parâmetros e. Dependendo das configurações do repositório, talvez seja necessário responder a um prompt para que a instalação do módulo continue.

Esses exemplos usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado. `Get-PSRepository` exibe os repositórios registrados. Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.

## EXEMPLOS

### Exemplo 1: localizar e instalar um módulo

Este exemplo localiza um módulo no repositório e instala o módulo.

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

O `Find-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . Por padrão, a versão mais recente do módulo é baixada do repositório. O objeto é enviado ao pipeline para o `Install-Module` cmdlet. `Install-Module` instala o módulo para todos os usuários no `$env:ProgramFiles\WindowsPowerShell\Modules` .

### Exemplo 2: instalar um módulo por nome

Neste exemplo, a versão mais recente do módulo **PowerShellGet** está instalada.

```powershell
Install-Module -Name PowerShellGet
```

O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . Por padrão, a versão mais recente do módulo é baixada do repositório e instalada.

### Exemplo 3: instalar um módulo usando sua versão mínima

Neste exemplo, a versão mínima do módulo **PowerShellGet** está instalada. O parâmetro **MinimumVersion** especifica a versão mais baixa do módulo que deve ser instalada. Se uma versão mais recente do módulo estiver disponível, essa versão será baixada e instalada para todos os usuários.

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . O parâmetro **MinimumVersion** especifica que a versão **2.0.1** é baixada do repositório e instalada. Como a versão **2.0.4** está disponível, essa versão é baixada e instalada para todos os usuários.

### Exemplo 4: instalar uma versão específica de um módulo

Neste exemplo, uma versão específica do módulo **PowerShellGet** está instalada.

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . O parâmetro **RequiredVersion** especifica que a versão **2.0.0** é baixada e instalada para todos os usuários.

### Exemplo 5: instalar um módulo somente para o usuário atual

Este exemplo baixa e instala a versão mais recente de um módulo, somente para o usuário atual.

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .
`Install-Module` baixa e instala a versão mais recente do **PowerShellGet** no diretório do usuário atual, `$home\Documents\WindowsPowerShell\Modules` .

## PARAMETERS

### -AcceptLicense

Para módulos que exigem uma licença, o **AcceptLicense** automaticamente aceita o contrato de licença durante a instalação. Para obter mais informações, consulte [módulos que exigem a aceitação da licença](/powershell/scripting/gallery/concepts/module-license-acceptance).

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

### -AllowClobber

Substitui mensagens de aviso sobre conflitos de instalação sobre comandos existentes em um computador.
Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados por um módulo.
**AllowClobber** e **Force** podem ser usados juntos em um `Install-Module` comando.

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

Permite que você instale um módulo marcado como um pré-lançamento.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar o `Install-Module` cmdlet.

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

Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.

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

Instala um módulo e substitui mensagens de aviso sobre conflitos de instalação de módulo. Se um módulo com o mesmo nome já existir no computador, **Force** permitirá que várias versões sejam instaladas. Se houver um módulo existente com o mesmo nome e versão, **Force** substitui essa versão. **Force** e **AllowClobber** podem ser usados juntos em um `Install-Module` comando.

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

Usado para entrada de pipeline.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima de um único módulo a ser instalado. A versão instalada deve ser menor ou igual a **MaximumVersion** . Se você quiser instalar vários módulos, não poderá usar **MaximumVersion** . **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Especifica a versão mínima de um único módulo a ser instalado. A versão instalada deve ser maior ou igual a **MinimumVersion** . Se houver uma versão mais recente do módulo disponível, a versão mais recente será instalada. Se você quiser instalar vários módulos, não poderá usar **MinimumVersion** .
**MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica os nomes exatos dos módulos a serem instalados na galeria online. Uma lista separada por vírgulas de nomes de módulo é aceita. O nome do módulo deve corresponder ao nome do módulo no repositório. Use `Find-Module` para obter uma lista de nomes de módulo.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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

Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .

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

Use o parâmetro **Repository** para especificar qual repositório é usado para baixar e instalar um módulo. Usado quando vários repositórios são registrados. Especifica o nome de um repositório registrado no `Install-Module` comando. Para registrar um repositório, use `Register-PSRepository` .
Para exibir repositórios registrados, use `Get-PSRepository` .

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata de um único módulo a ser instalado. Se não houver nenhuma correspondência no repositório para a versão especificada, será exibido um erro. Se você quiser instalar vários módulos, não poderá usar **RequiredVersion** . **RequiredVersion** não pode ser usado no mesmo `Install-Module` comando que **MinimumVersion** ou **MaximumVersion** .

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Especifica o escopo de instalação do módulo. Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser** .

O escopo **AllUsers** instala módulos em um local que pode ser acessado por todos os usuários do computador:

`$env:ProgramFiles\WindowsPowerShell\Modules`

O **CurrentUser** instala módulos em um local que é acessível somente para o usuário atual do computador. Por exemplo:

`$home\Documents\WindowsPowerShell\Modules`

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPublisherCheck

Permite que você instale uma versão mais recente de um módulo que já existe em seu computador. Por exemplo, quando um módulo existente é assinado digitalmente por um fornecedor confiável, mas a nova versão não é assinada digitalmente por um fornecedor confiável.

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

### -WhatIf

Mostra o que aconteceria se um `Install-Module` comando fosse executado. O cmdlet não é executado.

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

### PSRepositoryItemInfo

`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` .

### System.String[]

### System. Management. Automation. PSObject []

### System.String

### System. Management. Automation. PSCredential

### System.Uri

## SAÍDAS

### Microsoft. PowerShell. Commands. PSRepositoryItemInfo

Ao usar o parâmetro **PassThru** , o `Install-Module` gera um objeto **PSRepositoryItemInfo** para o módulo. Essas são as mesmas informações que você obtém do `Find-Module` cmdlet.

## OBSERVAÇÕES

`Install-Module` é executado no PowerShell 5,0 ou versões posteriores, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.

Como prática recomendada de segurança, avalie o código de um módulo antes de executar quaisquer cmdlets ou funções pela primeira vez. Para evitar a execução de módulos que contêm código mal-intencionado, os módulos instalados não são importados automaticamente após a instalação.

Se o nome do módulo especificado pelo parâmetro **Name** não existir no repositório, o `Install-Module` retornará um erro.

Para instalar vários módulos, use o parâmetro **Name** e especifique uma matriz separada por vírgulas de nomes de módulo. Se você especificar vários nomes de módulo, não poderá usar **MinimumVersion** , **MaximumVersion** ou **RequiredVersion** . `Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` . O pipeline é outra maneira de especificar vários módulos a serem instalados em um único comando.

Por padrão, os módulos para o escopo do **AllUsers** são instalados no `$env:ProgramFiles\WindowsPowerShell\Modules` . O padrão evita confusão quando você instala recursos de DSC (configuração de estado desejado) do PowerShell.

Uma instalação de módulo falha e não pode ser importada se não tiver um `.psm1` , `.psd1` ou `.dll` de mesmo nome dentro da pasta. Use o parâmetro **Force** para instalar o módulo.

Se a versão de um módulo existente corresponder ao nome especificado pelo parâmetro **Name** , e o parâmetro **MinimumVersion** ou **RequiredVersion** não for usado, o `Install-Module` continuará silenciosamente, mas não instalará o módulo.

Se a versão de um módulo existente for maior que o valor do parâmetro **MinimumVersion** ou igual ao valor do parâmetro **RequiredVersion** , `Install-Module` o continuará silenciosamente, mas não instalará o módulo.

Se o módulo existente não corresponder aos valores especificados pelos parâmetros **MinimumVersion** ou **RequiredVersion** , ocorrerá um erro no `Install-Module` comando. Por exemplo, se a versão do módulo instalado existente for menor do que o valor **MinimumVersion** ou não for igual ao valor **RequiredVersion** .

Uma instalação de módulo também instalará quaisquer módulos dependentes especificados conforme exigido pelo editor de módulo.
O Publicador especificará os módulos necessários e suas versões no manifesto do módulo.

## LINKS RELACIONADOS

[Find-Module](Find-Module.md)

[Get-PSRepository](Get-PSRepository.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Publish-Module](Publish-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[about_Module](../Microsoft.PowerShell.Core/About/about_Modules.md)
