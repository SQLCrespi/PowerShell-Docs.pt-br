---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194164"
---
# Get-WmiObject

## SINOPSE
Obtém as instâncias de classes do Windows Management Instrumentation (WMI) ou obtém informações sobre as classes disponíveis.

## SYNTAX

### consulta (padrão)

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### list

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### WQLQuery

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### classe

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### caminho

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## DESCRIPTION

A partir do PowerShell 3,0, esse cmdlet foi substituído pelo `Get-CimInstance` .

O `Get-WmiObject` cmdlet obtém instâncias de classes WMI ou informações sobre as classes WMI disponíveis. Para especificar um computador remoto, use o parâmetro **ComputerName** . Se o parâmetro **List** for especificado, o cmdlet obtém informações sobre as classes WMI disponíveis em um namespace especificado. Se o parâmetro **Query** for especificado, o cmdlet executa uma instrução do WMI query language (WQL).

O `Get-WmiObject` cmdlet não usa a comunicação remota do Windows PowerShell para executar operações remotas.
Você pode usar o parâmetro **ComputerName** do `Get-WmiObject` cmdlet, mesmo que o computador não atenda aos requisitos da comunicação remota do Windows PowerShell ou não esteja configurado para comunicação remota no Windows PowerShell.

A partir do Windows PowerShell 3,0, a propriedade **__Server** do objeto que `Get-WmiObject` retorna tem um alias **PSComputerName** . Isso facilita incluir o nome do computador de origem na saída e nos relatórios.

## EXEMPLOS

### Exemplo 1: obter processos no computador local

Este exemplo obtém os processos no computador local.

```powershell
Get-WmiObject -Class Win32_Process
```

### Exemplo 2: Obtém serviços em um computador remoto

Este exemplo obtém os serviços em um computador remoto. O parâmetro **ComputerName** especifica o endereço IP de um computador remoto. Por padrão, a conta de usuário atual deve ser um membro do grupo **Administradores** no computador remoto.

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### Exemplo 3: obter as classes WMI no namespace raiz ou padrão do computador local

Este exemplo obtém as classes WMI no namespace raiz ou padrão do computador local.

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### Exemplo 4: obter um serviço nomeado em vários computadores

Este exemplo obtém o serviço WinRM nos computadores especificados pelo valor do parâmetro **ComputerName** .

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

Um operador de pipeline (|) envia a saída para o `Format-List` cmdlet, que adiciona a propriedade **PSComputerName** à saída padrão. **PSComputerName** é um alias da propriedade **__Server** dos objetos que `Get-WmiObject` retorna. Esse alias foi introduzido no PowerShell 3,0.

### Exemplo 5: parar um serviço em um computador remoto

Este exemplo interrompe o serviço WinRM em um computador remoto. `Get-WmiObject` Obtém a instância do objeto de serviço WinRM em Server01. Em seguida, ele invoca o método **StopService** da classe **Win32_Service** WMI nesse objeto.

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

Isso é equivalente a usar o `Stop-Service` cmdlet.

### Exemplo 6: obter o BIOS no computador local

Este exemplo obtém as informações do BIOS do computador local. O parâmetro **Property** do `Format-List` cmdlet é usado para exibir todas as propriedades do objeto retornado em uma lista. Por padrão, somente o subconjunto de propriedades definido no `Types.ps1xml` arquivo de configuração é exibido.

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### Exemplo 7: obter os serviços em um computador remoto

Este exemplo usa o parâmetro **Credential** do `Get-WmiObject` cmdlet para obter os serviços em um computador remoto. O valor do parâmetro **Credential** é um nome de conta de usuário. O usuário é solicitado para uma senha.

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> As credenciais não podem ser usadas ao direcionar o computador local.

## PARAMETERS

### -Emendado

Obtém ou define um valor que indica se os objetos que são retornados do WMI devem conter informações aperfeiçoadas. Normalmente, informações aperfeiçoadas são informações localizáveis, como descrições de objeto e propriedade, que são anexadas ao objeto WMI.

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

### -AsJob

Executa o comando como um trabalho em segundo plano. Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.

Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. Se `Get-WmiObject` é usado em um computador remoto, o trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local. Para gerenciar o trabalho, utilize os cmdlets que contêm os cmdlets Job. Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.

> [!NOTE]
> Para utilizar esse parâmetro com computadores remotos, os computadores local e remoto precisam ser configurados para acesso remoto. Além disso, você deve iniciar o Windows PowerShell usando a opção "Executar como administrador" no Windows Vista e versões posteriores do Windows. Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).

Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).

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

### -Autenticação

Especifica o nível de autenticação a ser usado com a conexão WMI.
Os valores válidos são:

- -1: inalterado
- 0: padrão
- 1: nenhum (nenhuma autenticação em executada.)
- 2: conectar (a autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.)
- 3: chamada (a autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação).
- 4: pacote (a autenticação é executada em todos os dados que são recebidos do cliente.)
- 5: PacketIntegrity (todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.)
- 6: PacketPrivacy (as propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados).

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autoridade

Especifica a autoridade a ser usada para autenticar a conexão WMI. É possível especificar uma autenticação padrão NTLM ou Kerberos. Para usar o NTLM, defina a configuração de autoridade como `ntlmdomain:<DomainName>` , onde `<DomainName>` identifica um nome de domínio NTLM válido. Para usar o Kerberos, especifique `kerberos:<DomainName>\<ServerName>` . Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.

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

### -Classe

Especifica o nome de uma classe WMI. Quando esse parâmetro é utilizado, o cmdlet recupera instâncias da classe WMI.

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica o computador de destino para a operação de gerenciamento. Insira um nome de domínio totalmente qualificado (FQDN), um nome NetBIOS ou um endereço IP. Quando o computador remoto está em um domínio diferente do computador local, o nome de domínio totalmente qualificado é necessário.

O padrão é o computador local. Para especificar o computador local, como em uma lista de nomes de computador, use "localhost", o nome do computador local ou um ponto (.).

Esse parâmetro não se baseia no Windows PowerShell remotamente, que usa o WS-Management. Você pode usar o parâmetro **ComputerName** de `Get-WmiObject` mesmo que o computador não esteja configurado para executar WS-Management comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual. Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou User@Contoso.com . Ou insira um objeto **PSCredential** , como um objeto que é retornado pelo `Get-Credential` cmdlet. Quando você digitar um nome de usuário, uma senha será solicitada. As credenciais não podem ser usadas ao direcionar o computador local.

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

### -DirectRead

Especifica se o acesso direto ao provedor WMI é solicitado para a classe especificada sem qualquer relação com a sua classe base ou suas classes derivadas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges

Habilita todos os privilégios do usuário atual antes do comando realizar a chamada WMI.

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

Especifica uma cláusula **Where** para usar como um filtro. Utiliza a sintaxe de linguagem de consulta WMI (WQL).

> [!IMPORTANT]
> Não inclua a palavra-chave **Where** no valor do parâmetro. Por exemplo, os seguintes comandos retornam somente os discos lógicos que têm um **DeviceID** de 'c:' e serviços com o nome 'WinRM' sem usar a palavra-chave **Where** .

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Representação

Especifica o nível de representação a ser usado.

Os valores aceitáveis para esse parâmetro são:

- 0: padrão. Lê o registro local para o nível de representação padrão. O padrão é geralmente definido como **Impersonate** .
- 1: anônimo. Oculta as credenciais do autor da chamada.
- 2: identificar. Permite que os objetos consultem as credenciais do autor da chamada.
- 3: representar. Permite que os objetos utilizem as credenciais do autor da chamada.
- 4: delegar. Autoriza que os objetos permitam que outros objetos utilizem as credenciais do autor da chamada.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lista

Obtém os nomes das classes WMI no namespace do repositório WMI especificados pelo parâmetro **Namespace** .

Se você especificar o parâmetro de **lista** , mas não o parâmetro **namespace** , `Get-WmiObject` o usará o namespace **Root\Cimv2** por padrão. Esse cmdlet não usa a entrada de registro de **namespace padrão** na `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` chave do registro para determinar o namespace padrão.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Localidade

Especifica o local preferido para objetos WMI.
Insira um valor no formato MS_\<LCID\>.

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

### -Namespace

Quando utilizado com o parâmetro **Class** , o parâmetro **Namespace** especifica o namespace do repositório WMI onde se encontra a classe WMI especificada. Quando utilizado com o parâmetro **List** , ele especifica o namespace do qual coletar informações de classe WMI.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Especifica as propriedades de classe WMI das quais esse cmdlet obtém informações. Digite os nomes das propriedades.

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Executa a instrução de linguagem de consulta WMI (WQL). Esse parâmetro não oferece suporte a consultas de evento.

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Pesquisa o namespace atual e todos os outros namespaces para o nome da classe que é especificada pelo parâmetro **Class** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de operações de WMI que podem ser executadas simultaneamente. Esse parâmetro é válido somente quando o parâmetro **AsJob** é usado no comando.

```yaml
Type: System.Int32
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

### Nenhum

Não é possível canalizar a entrada para `Get-WmiObject` .

## SAÍDAS

### PSObject ou System. Management. Automation. RemotingJob

Ao utilizar o parâmetro **AsJob** , o cmdlet retorna um objeto de trabalho. Caso contrário, o objeto que `Get-WmiObject` retorna depende do valor do parâmetro de **classe** .

## OBSERVAÇÕES

Para acessar informações de WMI em um computador remoto, o cmdlet deve ser executado em uma conta que seja membro do grupo Administradores locais no computador remoto. Ou, o controle de acesso padrão no namespace WMI do repositório remoto pode ser alterado para conceder direitos de acesso a outras contas.

Apenas algumas das propriedades de cada classe WMI são exibidas por padrão. O conjunto de propriedades que é exibido para cada classe WMI que é especificada no arquivo de configuração Types.ps1xml. Para obter todas as propriedades de um objeto WMI, use `Get-Member` os `Format-List` cmdlets ou.

## LINKS RELACIONADOS

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
