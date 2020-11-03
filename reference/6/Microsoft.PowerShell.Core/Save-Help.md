---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 4b7e74d7b83dbf5128b30e1bbf2c51d69c3a235a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194609"
---
# Save-Help

## SINOPSE
Baixa e salva os arquivos de ajuda mais recentes em um diretório de sistema de arquivos.

## SYNTAX

### Caminho (padrão)

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### LiteralPath

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Save-Help** baixa os arquivos mais recentes de ajuda para os módulos do PowerShell e os salva em um diretório que você especificar.
Esse recurso permite que você atualize os arquivos de ajuda em computadores que não têm acesso à Internet e torna mais fácil atualizar os arquivos de ajuda em vários computadores.

No Windows PowerShell 3,0, o **Save-Help** funcionava apenas para módulos que estão instalados no computador local.
Embora fosse possível importar um módulo de um computador remoto, ou obter uma referência a um objeto **PSModuleInfo** de um computador remoto usando a comunicação remota do PowerShell, a propriedade **HelpInfoUri** não foi preservada e **Save-Help** não funcionaria para a ajuda do módulo remoto.

No Windows PowerShell 4,0, a propriedade **HelpInfoUri** é preservada pela comunicação remota do PowerShell, o que permite que o **Save-Help** funcione para os módulos instalados em computadores remotos.
Também é possível salvar um objeto **PSModuleInfo** em disco ou mídia removível executando Export-Clixml em um computador que não tenha acesso à Internet, importar o objeto em um computador que tenha acesso à Internet e, em seguida, executar **Save-Help** no objeto **PSModuleInfo** .
A ajuda salva pode ser transportada para o computador remoto usando mídia de armazenamento removível, como uma unidade USB.
A ajuda pode ser instalada no computador remoto executando **Update-Help** .
Esse processo pode ser usado para instalar ajuda em computadores que não têm qualquer tipo de acesso à rede.

Para instalar arquivos de ajuda salvos, execute o cmdlet Update-Help.
Adicione seu parâmetro *SourcePath* para especificar a pasta na qual você salvou os arquivos de ajuda.

Sem parâmetros, um comando **Save-Help** baixa a ajuda mais recente para todos os módulos da sessão e para módulos instalados no computador em um local listado na variável de ambiente **PSModulePath** .
Esta ação ignora módulos que não dão suporte à ajuda atualizável sem aviso.

O cmdlet **Save-Help** verifica a versão de qualquer arquivo de ajuda na pasta de destino.
Se os arquivos de ajuda mais recentes estiverem disponíveis, esse cmdlet baixará os arquivos de ajuda mais recentes da Internet e os salvará na pasta.
O cmdlet **Save-Help** funciona exatamente como o cmdlet Update-Help, exceto que ele salva os arquivos de gabinete (. cab) baixados, em vez de extrair os arquivos de ajuda dos arquivos de gabinete e instalá-los no computador.

A ajuda salva para cada módulo consiste em um arquivo de informações de ajuda (HelpInfo XML) e um arquivo de gabinete (. cab) para os arquivos de ajuda de cada cultura da interface do usuário.
Você não precisa extrair os arquivos de ajuda do arquivo de gabinete.
O cmdlet **Update-Help** extrai os arquivos da ajuda, valida o XML para segurança e, em seguida, instala os arquivos de ajuda e o arquivo de informações da ajuda em uma subpasta específica do idioma da pasta do módulo.

Para salvar os arquivos de ajuda para os módulos na pasta de instalação do PowerShell ($pshome \Modules), inicie o PowerShell usando a opção Executar como administrador.
Você precisa ser um membro do grupo Administradores no computador para baixar os arquivos de ajuda para esses módulos.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: salvar a ajuda para o módulo DhcpServer

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

Este exemplo mostra três maneiras diferentes de usar **Save-Help** para salvar a ajuda para o módulo **DhcpServer** de um computador cliente conectado à Internet, sem instalar o módulo **dhcpserver** ou a função de servidor DHCP no computador local.

### Exemplo 2: instalar a ajuda para o módulo DhcpServer

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

Este exemplo mostra como instalar a ajuda que você salvou no exemplo 1 para o módulo **DhcpServer** em um computador que não tem acesso à Internet.

### Exemplo 3: salvar a ajuda para todos os módulos

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

Esse comando baixa os arquivos de ajuda mais recentes para todos os módulos na cultura da interface do usuário definidos para o Windows no computador local.
Ele salva os arquivos de ajuda na \\ \\ pasta Server01\Fileshare01

### Exemplo 4: salvar a ajuda para um módulo no computador

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

Esse comando baixa os arquivos de ajuda mais recentes para o módulo **ServerManager** e os salva na \\ \\ pasta Server01\Fileshare01

Quando um módulo é instalado no computador, você pode digitar o nome do módulo como o valor do parâmetro *Module* , ainda que o módulo não seja importado para a sessão atual.

O comando usa o parâmetro *Credential* para fornecer as credenciais de um usuário que tem permissão para gravar no compartilhamento de arquivos.

### Exemplo 5: salvar a ajuda para um módulo em um computador diferente

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

Esses comandos baixam os arquivos de ajuda mais recentes para o módulo **CustomSQL** e os salvam na \\ \\ pasta Server01\Fileshare01.

Como o módulo **CustomSQL** não está instalado no computador, a sequência inclui um comando Invoke-Command que obtém o objeto de módulo para o módulo CustomSQL do computador Server02 e, em seguida, canaliza o objeto de módulo para o cmdlet **Save-Help** .

Quando um módulo não está instalado no computador, **Save-Help** precisa do objeto de módulo, que inclui informações sobre o local dos arquivos de ajuda mais recentes.

### Exemplo 6: salvar a ajuda para um módulo em vários idiomas

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

Esse comando salva a ajuda para os módulos do PowerShell Core em quatro culturas de interface do usuário diferentes.
Os pacotes de idiomas dessas localidades não precisam ser instalados no computador.

**Save-Help** pode baixar arquivos de ajuda para módulos em diferentes culturas de interface do usuário somente quando o proprietário do módulo disponibiliza os arquivos traduzidos na Internet.

### Exemplo 7: salvar ajuda mais de uma vez por dia

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

Este comando salva ajuda para todos os módulos instalados no computador.
O comando especifica o parâmetro *Force* para substituir a regra que impede que o cmdlet **Save-Help** Baixe a ajuda mais de uma vez em cada período de 24 horas.

O parâmetro *Force* também substitui a restrição de 1 GB e evita a verificação da versão.
Portanto, você pode baixar arquivos mesmo que a versão não seja posterior à versão na pasta de destino.

O comando usa o cmdlet **Save-Help** para baixar e salvar os arquivos de ajuda na pasta especificada.
O parâmetro *Force* é necessário quando você precisa executar um comando **Save-Help** mais de uma vez por dia.

## PARAMETERS

### -Credential

Especifica uma credencial de usuário. Esse cmdlet executa o comando usando as credenciais de um usuário que tem permissão para acessar o local do sistema de arquivos especificado pelo parâmetro **DestinationPath** . Esse parâmetro é válido somente quando o parâmetro **DestinationPath** ou **LiteralPath** é usado no comando.

Esse parâmetro permite que você execute `Save-Help` comandos que usam o parâmetro **DestinationPath** em computadores remotos. Ao fornecer credenciais explícitas, você pode executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador sem encontrar um erro de acesso negado ou usar a autenticação CredSSP para delegar credenciais.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath

Especifica o caminho da pasta na qual os arquivos de ajuda são salvos.
Não especifique um nome de arquivo ou extensão de nome de arquivo.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet não segue a limitação de uma vez por dia, ignora a verificação de versão e baixa os arquivos que excedem o limite de 1 GB.

Sem esse parâmetro, somente um comando **Save-Help** para cada módulo é permitido em cada período de 24 horas, downloads são limitados a 1 GB de conteúdo não compactado por módulo e arquivos de ajuda para um módulo são instalados apenas quando eles são mais recentes que os arquivos no computador.

O limite de uma vez por dia protege os servidores que hospedam os arquivos de ajuda e torna prático para você adicionar um comando **Save-Help** ao seu perfil do PowerShell.

Para salvar a ajuda de um módulo em várias culturas de interface do usuário sem o parâmetro *Force* , inclua todas as culturas da interface do usuário no mesmo comando, como: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### -FullyQualifiedModule

Especifica os módulos com nomes que são especificados na forma de objetos ModuleSpecification.
Isso é descrito na seção comentários do [Construtor ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) na biblioteca MSDN.
Por exemplo, o parâmetro *FullyQualifiedModule* aceita um nome de módulo que é especificado no formato @ {ModuleName = "ModuleName"; ModuleVersion = "version_number"} ou @ {ModuleName = "ModuleName"; ModuleVersion = "version_number"; GUID = "GUID"}.
**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.

Você não pode especificar o parâmetro *FullyQualifiedModule* no mesmo comando que um parâmetro de *módulo* .

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

Especifica um caminho da pasta de destino.
Ao contrário do valor do parâmetro *DestinationPath* , o valor do parâmetro *LiteralPath* é usado exatamente como é digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Módulo

Especifica os módulos para os quais esse cmdlet baixa a ajuda.
Insira um ou mais nomes de módulo ou nome padrões em uma lista separada por vírgulas ou em um arquivo que tenha um nome de módulo em cada linha.
Caracteres curinga são permitidos.
Você também pode canalizar objetos de módulo do cmdlet Get-Module para **salvar-Help** .

Por padrão, **Save-Help** baixa ajuda para todos os módulos que suportam Ajuda Atualizável e estão instalados no computador local, em um local listado na variável de ambiente **PSModulePath** .

Para salvar a ajuda para módulos que não estão instalados no computador, execute um comando **Get-Module** em um computador remoto.
Então, redirecione os objetos de módulo resultantes para o cmdlet **Save-Help** ou envie os objetos de módulo como valor dos parâmetros *Module* ou *InputObject* .

Se o módulo especificado estiver instalado no computador, você pode inserir o nome do módulo ou um objeto de módulo.
Se o módulo não estiver instalado no computador, você deve inserir um objeto de módulo, como o retornado pelo cmdlet **Get-Module** .

O parâmetro *Module* do cmdlet **Save-Help** não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.
Para salvar a ajuda para um módulo que não está em um local **PSModulePath** , importe o módulo para a sessão atual antes de executar o comando **Save-Help** .

Um valor de "*" (All) tenta atualizar a ajuda para todos os módulos instalados no computador.
Isso inclui módulos que não dão suporte à ajuda atualizável.
Esse valor pode gerar erros quando o comando encontra módulos que não dão suporte à ajuda atualizável.

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UICulture

Especifica os valores de cultura da interface do usuário para os quais este cmdlet obtém arquivos de ajuda atualizados.
Insira um ou mais códigos de idioma, como es-ES, uma variável que contém objetos de cultura ou um comando que obtém objetos de cultura, como um Get-Culture ou Get-UICulture comando.

Caracteres curinga não são permitidos.
Não especifique um código de idioma parcial, como "de".

Por padrão, **Save-Help** Obtém arquivos de ajuda no conjunto de cultura da interface do usuário para Windows ou sua cultura de fallback.
Se você especificar o parâmetro *UICulture* , **Save-Help** procurará ajuda apenas para a cultura da interface do usuário especificada, não em qualquer cultura de fallback.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

Indica que esse cmdlet executa o comando, incluindo o download da Web, com as credenciais do usuário atual.
Por padrão, o comando é executado sem credenciais explícitas.

Esse parâmetro é válido somente quando o download da Web usa autenticação NTLM, de negociação ou baseada em Kerberos.

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

### -Escopo

Esse parâmetro não faz nada nesse cmdlet.

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSModuleInfo

É possível canalizar um objeto de módulo do cmdlet **Get-Module** para o parâmetro *Module* de **Save-Help** .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para salvar a ajuda para os módulos na pasta $pshome \Modules, inicie o PowerShell usando a opção Executar como administrador. Somente os membros do grupo Administradores no computador podem baixar a ajuda para os módulos na pasta $pshome \Modules.
* A ajuda salva para cada módulo consiste em um arquivo de informações de ajuda (HelpInfo XML) e um arquivo de gabinete (. cab) para os arquivos de ajuda de cada cultura da interface do usuário. Você não precisa extrair os arquivos de ajuda do arquivo de gabinete. O cmdlet Update-Help extrai os arquivos da ajuda, valida o XML e, em seguida, instala os arquivos de ajuda e o arquivo de informações da ajuda em uma subpasta específica do idioma da pasta do módulo.
* O cmdlet **Save-Help** pode salvar ajuda para módulos que não estão instalados no computador. No entanto, como os arquivos de ajuda são instalados na pasta do módulo, o cmdlet **Update-Help** pode instalar o arquivo de ajuda atualizado somente para os módulos que estão instalados no computador.
* Se **Save-Help** não puder encontrar os arquivos de ajuda atualizados para um módulo ou se não for possível encontrar arquivos de ajuda atualizados no idioma especificado, ele continua silenciosamente, sem exibir uma mensagem de erro. Para ver quais arquivos foram salvos pelo comando, especifique o parâmetro *Verbose* .
* Os módulos são a menor unidade da ajuda atualizável. Não é possível salvar a ajuda para um cmdlet específico, somente para todos os cmdlets no módulo. Para localizar o módulo que contém um cmdlet específico, use a propriedade **ModuleName** junto com o cmdlet Get-Command, por exemplo, `(Get-Command \<cmdlet-name\>).ModuleName`
* **Save-Help** dá suporte a todos os módulos e aos snap-ins do PowerShell Core. Ele não dá suporte a nenhum outro snap-ins.
* Os cmdlets **Update-Help** e **Save-Help** usam as seguintes portas para baixar arquivos de ajuda: porta 80 para http e porta 443 para https.
* Os cmdlets **Update-Help** e **Save-Help** não são suportados no Ambiente de Pré-instalação do Windows (Windows PE).

## LINKS RELACIONADOS

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Update-Help](Update-Help.md)
