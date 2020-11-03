---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 2851305f40c9805ae3f0fcc2a25a82a57a78cd23
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "93195117"
---
# Update-Help

## SINOPSE
Baixa e instala os arquivos de ajuda mais recentes em seu computador.

## SYNTAX

### Caminho (padrão)

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LiteralPath

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Update-Help` cmdlet baixa os arquivos de ajuda mais recentes para os módulos do PowerShell e os instala em seu computador. Você não precisa reiniciar o PowerShell para que a alteração seja efetiva. Você pode usar o `Get-Help` cmdlet para exibir os novos arquivos de ajuda imediatamente.

`Update-Help` verifica a versão dos arquivos de ajuda em seu computador. Se você não tiver arquivos de ajuda para um módulo ou se os arquivos de ajuda estiverem desatualizados, `Update-Help` o baixará os arquivos de ajuda mais recentes. Os arquivos de ajuda podem ser baixados e instalados da Internet ou de um compartilhamento de arquivos.

Sem parâmetros, `Update-Help` o atualiza os arquivos de ajuda para os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável. Os módulos instalados, mas não carregados na sessão atual, estão incluídos. Os módulos do PowerShell são armazenados em um local listado na `$env:PSModulePath` variável de ambiente. Para obter mais informações, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).

Você pode usar o parâmetro **Module** para atualizar os arquivos de ajuda de um módulo específico. Use o parâmetro **UICulture** para baixar arquivos de ajuda em vários idiomas e localidades.

Você também pode usar `Update-Help` o em computadores que não estão conectados à Internet. Primeiro, use o `Save-Help` cmdlet para baixar arquivos de ajuda da Internet e salvá-los em uma pasta compartilhada que seja acessível ao sistema não conectado à Internet. Em seguida, use o parâmetro **SourcePath** do `Update-Help` para baixar os arquivos de ajuda atualizados do compartilhado e instale-os no computador.

Você pode automatizar as atualizações da ajuda adicionando o `Update-Help` cmdlet ao seu perfil do PowerShell. Por padrão, o `Update-Help` é executado apenas uma vez por dia em cada computador. Para substituir o limite de uma vez por dia, use o parâmetro **Force** .

O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0.

> [!IMPORTANT]
> `Update-Help` requer privilégios administrativos no PowerShell 6,0 e abaixo.
> O PowerShell 6,1 e superior definem o **escopo** padrão como `CurrentUser` .
> Antes do PowerShell 6,1, o parâmetro de **escopo** não estava disponível.
>
> Você deve ser um membro do grupo Administradores no computador para atualizar os arquivos de ajuda para os módulos do PowerShell Core.
>
> Para baixar ou atualizar os arquivos de ajuda para os módulos no diretório de instalação do PowerShell ( `$PSHOME\Modules` ), incluindo os módulos do PowerShell Core, inicie o PowerShell usando a opção **Executar como administrador** .
> Por exemplo: `Start-Process pwsh.exe -Verb RunAs`.

## EXEMPLOS

### Exemplo 1: atualizar arquivos de ajuda para todos os módulos

O `Update-Help` cmdlet atualiza os arquivos de ajuda para os módulos instalados que dão suporte à ajuda atualizável. O idioma da cultura da interface do usuário é definido no sistema operacional.

```powershell
Update-Help
```

### Exemplo 2: atualizar os arquivos de ajuda para os módulos especificados

O `Update-Help` cmdlet atualiza os arquivos de ajuda somente para nomes de módulo que começam com **Microsoft. PowerShell** .

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### Exemplo 3: atualizar arquivos de ajuda para idiomas diferentes

O `Update-Help` cmdlet atualiza os arquivos de ajuda japoneses (ja-JP) e inglês (en-US) para todos os módulos.

Se um módulo não fornecer arquivos de ajuda para uma cultura de interface do usuário especificada, uma mensagem de erro será exibida para a cultura do módulo e da interface do usuário. Neste exemplo, a mensagem de erro indica que os arquivos de ajuda do **ja-JP** não foram encontrados para o módulo **Microsoft. PowerShell. Utility** .

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### Exemplo 4: atualizar arquivos de ajuda em vários computadores a partir de um compartilhamento de arquivos

Neste exemplo, os arquivos de ajuda atualizados são baixados da Internet e salvos em um compartilhamento de arquivos. São necessárias credenciais de usuário que têm permissões para acessar o compartilhamento de arquivos e instalar atualizações. Quando um compartilhamento de arquivos é usado, é possível atualizar computadores que estão atrás de firewalls ou que não estão conectados à Internet.

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

O `Save-Help` comando baixa os arquivos de ajuda mais recentes para todos os módulos que dão suporte à ajuda atualizável.
O parâmetro **DestinationPath** salva os arquivos no `\\Server01\Share\PSHelp` compartilhamento de arquivos. O parâmetro **Credential** especifica um usuário que tem permissão para acessar o compartilhamento de arquivos.

O `Invoke-Command` cmdlet executa comandos remotos `Update-Help` em vários computadores. O parâmetro **ComputerName** Obtém uma lista de computadores remotos do arquivo **Servers.txt** . O parâmetro **scriptblock** executa o `Update-Help` comando e usa o parâmetro **SourcePath** para especificar o compartilhamento de arquivos que contém os arquivos de ajuda atualizados. O parâmetro **Credential** especifica um usuário que pode acessar o compartilhamento de arquivos e executar o `Update-Help` comando remoto.

### Exemplo 5: obter uma lista de arquivos de ajuda atualizados

O `Update-Help` cmdlet atualiza a ajuda para um módulo especificado. O cmdlet usa o parâmetro comum **detalhado** para exibir a lista de arquivos de ajuda que foram atualizados. Você pode usar o modo **detalhado** para exibir a saída de todos os arquivos de ajuda ou arquivos de ajuda para um módulo específico.

Sem o parâmetro **Verbose** , o `Update-Help` não exibe os resultados do comando. A saída de parâmetro **detalhado** é útil para verificar se os arquivos de ajuda foram atualizados ou se a versão mais recente está instalada.

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### Exemplo 6: localizar módulos que dão suporte à ajuda atualizável

Este exemplo lista os módulos que oferecem suporte à ajuda atualizável. O comando usa a propriedade **HelpInfoUri** do módulo para identificar os módulos que oferecem suporte à ajuda atualizável. A propriedade **HelpInfoUri** contém um endereço que é redirecionado quando o `Update-Help` cmdlet é executado.

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### Exemplo 7: Arquivos de ajuda atualizados do inventário

Neste exemplo, o script `Get-UpdateHelpVersion.ps1` cria um inventário dos arquivos de ajuda atualizáveis para cada módulo e seus números de versão.

O script identifica os módulos que dão suporte à ajuda atualizável usando a propriedade **HelpInfoUri** dos módulos. Para módulos que dão suporte à ajuda atualizável, o script procura e analisa o arquivo de informações de ajuda (* helpinfo.xml) para localizar o número de versão mais recente.

O script usa a classe **PSCustomObject** e uma tabela de hash para criar um objeto de saída personalizado.

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## PARAMETERS

### -Credential

Especifica as credenciais de um usuário que tem permissão para acessar o local do sistema de arquivos especificado por **SourcePath** . Esse parâmetro é válido somente quando o parâmetro **SourcePath** ou **LiteralPath** é usado no comando.

O parâmetro **Credential** permite que você execute `Update-Help` comandos com o parâmetro **SourcePath** em computadores remotos. Ao fornecer credenciais explícitas, você pode executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador sem encontrar um erro de acesso negado ou usar a autenticação CredSSP para delegar credenciais.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet não segue a limitação de uma vez por dia, ignora a verificação de versão e baixa os arquivos que excedem o limite de 1 GB.

Sem esse parâmetro, o `Update-Help` é executado apenas uma vez em cada período de 24 horas. Os downloads são limitados a 1 GB de conteúdo descompactado por módulo e os arquivos de ajuda são instalados apenas quando são mais recentes do que os arquivos existentes no computador.

O limite de uma vez por dia protege os servidores que hospedam os arquivos de ajuda e torna prático para você adicionar um `Update-Help` comando ao seu perfil do PowerShell sem incorrer no custo de recursos de conexões ou downloads repetidos.

Para atualizar a Ajuda para um módulo em várias culturas de interface do usuário sem o parâmetro **Force** , incluem todas as culturas de interface do usuário no mesmo comando, como:

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### -FullyQualifiedModule

Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .
Esses módulos são descritos na seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado no formato:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

ou

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.

Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Especifica a pasta para arquivos de ajuda atualizados em vez de baixá-los da Internet. Use esse parâmetro ou **SourcePath** se você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda para um diretório.

Você pode canalizar um objeto de diretório, como dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .

Ao contrário do valor de **SourcePath** , o valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Módulo

Atualizações de Ajuda para os módulos especificados. Insira um ou mais nomes de módulo ou padrões de nome em uma lista separada por vírgulas ou especifique um arquivo que liste um nome de módulo em cada linha. Caracteres curinga são permitidos. Você pode canalizar módulos do `Get-Module` cmdlet para o `Update-Help` cmdlet.

Os módulos que você especificar devem ser instalados no computador, mas não precisam ser importados para a sessão atual. Você pode especificar qualquer módulo na sessão ou qualquer módulo que esteja instalado em um local listado na variável de `$env:PSModulePath` ambiente.

Um valor de `*` (All) tenta atualizar a ajuda para todos os módulos instalados no computador.
Módulos que não dão suporte à ajuda atualizável estão incluídos. Esse valor pode gerar erros quando o comando encontra módulos que não dão suporte à ajuda atualizável. Em vez disso, execute `Update-Help` sem parâmetros.

O parâmetro **Module** do `Update-Help` cmdlet não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo. Para atualizar a ajuda para um módulo que não está em um `$env:PSModulePath` local, importe o módulo para a sessão atual antes de executar o `Update-Help` comando.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Recurse

Executa uma pesquisa recursiva de arquivos de ajuda no diretório especificado. Esse parâmetro é válido somente quando o comando usa o parâmetro **SourcePath** .

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

### -Escopo

Especifica o escopo do sistema em que a ajuda é atualizada. As atualizações no escopo **AllUsers** exigem privilégios administrativos em sistemas Windows. O `-Scope` parâmetro foi introduzido na versão 6,1 do PowerShell Core.

**CurrentUser** é o escopo padrão para arquivos de ajuda no PowerShell 6,1 e superior. **AllUsers** pode ser especificado para instalar ou atualizar a ajuda para todos os usuários. Em privilégios de sistemas UNIX `sudo` são necessários para atualizar a ajuda para todos os usuários. Por exemplo: `sudo pwsh -c Update-Help`

Os valores aceitáveis são:

- CurrentUser
- AllUsers

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePath

Especifica uma pasta do sistema de arquivos em que o `Update-Help` Obtém arquivos de ajuda atualizados, em vez de baixá-los da Internet. Insira o caminho de uma pasta. Não especifique um nome de arquivo ou uma extensão de nome de arquivo. Você pode canalizar uma pasta, como uma dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .

Por padrão, o `Update-Help` baixa arquivos de ajuda atualizados da Internet. Use **SourcePath** quando você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda atualizados para um diretório.

Para especificar um valor padrão para **SourcePath** , vá para **política de grupo** , **configuração do computador** e **defina o caminho de origem padrão para Update-Help** . Essa configuração de Política de Grupo impede que os usuários usem `Update-Help` o para baixar arquivos de ajuda da Internet.
Confira mais informações em [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Especifica os valores de cultura da interface do usuário que o `Update-Help` usa para obter arquivos de ajuda atualizados. Insira um ou mais códigos de idioma, como **es-es** , uma variável que contém objetos de cultura ou um comando que obtém objetos de cultura, como um `Get-Culture` `Get-UICulture` comando ou. Os caracteres curinga não são permitidos e você não pode enviar um código de idioma parcial, como **de** .

Por padrão, `Update-Help` o Obtém os arquivos de ajuda na cultura da interface do usuário definida para o sistema operacional. Se você especificar o parâmetro **UICulture** , o `Update-Help` procurará ajuda apenas para a cultura da interface do usuário especificada.

> [!NOTE]
> O Ubuntu 18, 4 alterou a configuração de localidade padrão para `C.UTF.8` , que não é uma cultura de interface do usuário reconhecida. `Update-Help` falha silenciosa ao baixar a ajuda, a menos que você use esse parâmetro com uma localidade com suporte como `en-US` . Isso pode ocorrer em qualquer plataforma que usa um valor sem suporte.

Os comandos que utilizam o parâmetro **UICulture** têm êxito somente quando o módulo fornece arquivos de ajuda para a cultura da interface do usuário especificado. Se o comando falhar porque a cultura da interface do usuário especificada não tem suporte, será exibida uma mensagem de erro.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

Indica que `Update-Help` o executa o comando, incluindo o download da Internet, usando as credenciais do usuário atual. Por padrão, o comando é executado sem credenciais explícitas.

Esse parâmetro é eficaz somente quando o download da Web usa o NTLM (NT LAN Manager), Negotiate ou autenticação baseada em Kerberos.

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

### System. IO. DirectoryInfo

É possível canalizar um caminho de diretório para `Update-Help` .

### System. Management. Automation. PSModuleInfo

É possível canalizar um objeto de módulo do `Get-Module` cmdlet para `Update-Help` .

## SAÍDAS

### Nenhum

`Update-Help` não gera nenhuma saída.

## OBSERVAÇÕES

Para atualizar a ajuda para os módulos do PowerShell Core, que contêm os comandos instalados com o PowerShell ou qualquer módulo no `$PSHOME\Modules` diretório, inicie o PowerShell com a opção de **Executar como administrador** .

Somente os membros do grupo Administradores no computador podem atualizar a ajuda para os módulos do PowerShell Core, os comandos que são instalados junto com o PowerShell e para os módulos na `$PSHOME\Modules` pasta. Se você não tiver permissão para atualizar os arquivos de ajuda, poderá ler os arquivos de ajuda online. Por exemplo, `Get-Help Update-Help -Online`.

Os módulos são a menor unidade da ajuda atualizável. Você não pode atualizar a ajuda para um cmdlet específico. Para localizar o módulo que contém um cmdlet específico, use a propriedade **ModuleName** do `Get-Command` cmdlet, por exemplo, `(Get-Command Update-Help).ModuleName` .

Como os arquivos de ajuda são instalados no diretório do módulo, o `Update-Help` cmdlet pode instalar o arquivo de ajuda atualizado somente para os módulos que estão instalados no computador. No entanto, o `Save-Help` cmdlet pode salvar ajuda para módulos que não estão instalados no computador.

Se `Update-Help` o não conseguir encontrar arquivos de ajuda atualizados para um módulo ou não conseguir encontrar ajuda atualizada no idioma especificado, ele continuará silenciosamente sem exibir uma mensagem de erro. Para ver os detalhes de status e o andamento, use o parâmetro **Verbose** .

O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0. Ele não funciona em versões anteriores do PowerShell. Em computadores que têm o Windows PowerShell 2,0 e o Windows PowerShell 3,0, use o `Update-Help` cmdlet em uma sessão do Windows powershell 3,0 para baixar e atualizar os arquivos de ajuda. Os arquivos de ajuda estão disponíveis para o Windows PowerShell 2,0 e o Windows PowerShell 3,0.

Os `Update-Help` `Save-Help` cmdlets e usam as seguintes portas para baixar arquivos de ajuda: porta 80 para http e porta 443 para https.

`Update-Help` dá suporte a todos os módulos e os snap-ins do PowerShell Core. Ele não dá suporte a nenhum outro snap-ins.

Para atualizar a ajuda de um módulo em um local que não está listado na `$env:PSModulePath` variável de ambiente, importe o módulo para a sessão atual e, em seguida, execute um `Update-Help` comando. Execute `Update-Help` sem parâmetros ou use o parâmetro **Module** para especificar o nome do módulo. O parâmetro **Module** dos `Update-Help` `Save-Help` cmdlets e não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.

Qualquer módulo pode dar suporte a Ajuda atualizável. Para obter instruções para dar suporte à ajuda atualizável nos módulos que você cria, consulte [dando suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).

`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).

## LINKS RELACIONADOS

[Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Get-UICulture](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[Start-Job](Start-Job.md)

[Save-Help](Save-Help.md)
