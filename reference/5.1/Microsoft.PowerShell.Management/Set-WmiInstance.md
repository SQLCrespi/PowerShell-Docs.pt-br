---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193919"
---
# Set-WmiInstance

## SINOPSE
Cria ou atualiza uma instância de uma classe existente do WMI (Instrumentação de Gerenciamento do Windows).

## SYNTAX

### classe (padrão)

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### objeto

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### caminho

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Consulta

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O `Set-WmiInstance` cmdlet cria ou atualiza uma instância de uma classe de instrumentação de gerenciamento do Windows (WMI) existente.
A instância criada ou atualizada é gravada no repositório do WMI.

Novos cmdlets do CIM, apresentados pelo Windows PowerShell 3.0, executam as mesmas tarefas que os cmdlets do WMI.
Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM).
Isso permite que os cmdlets usem as mesmas técnicas para gerenciar computadores baseados no Windows e aqueles que executam outros sistemas operacionais.
Em vez de usar `Set-WmiInstance` , considere usar os cmdlets [set-Ciminstance](/powershell/module/cimcmdlets/set-ciminstance) ou [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) .

## EXEMPLOS

### Exemplo 1: definir o nível de log do WMI

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

Esse comando define o nível de log do WMI como 2.
O comando passa a propriedade a ser definida e o valor, em conjunto, é considerado um par de valor, no parâmetro Argument.
O parâmetro usa uma tabela de hash que é definida pela construção @{propriedade = valor}.
As informações de classe que são retornadas refletem o novo valor.

### Exemplo 2: criar uma variável de ambiente e seu valor

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

Esse comando cria a variável de ambiente testvar que tem o valor testValue.
Ele faz isso criando uma nova instância da classe **Win32_Environment** WMI.
Esta operação requer credenciais apropriadas e você pode precisar reiniciar o Windows PowerShell para ver a nova variável de ambiente.

### Exemplo 3: definir o nível de log do WMI para vários computadores remotos

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

Esse comando define o nível de log do WMI como 2.
O comando passa a propriedade a ser definida e o valor, em conjunto, é considerado um par de valor, no parâmetro Argument.
O parâmetro usa uma tabela de hash que é definida pela construção @{propriedade = valor}.
As informações de classe retornadas refletem o novo valor.

## PARAMETERS

### -Arguments
Especifica o nome da propriedade a ser alterado e o novo valor para essa propriedade.
O nome e o valor devem ser um par de nome-valor.
O par nome-valor é passado na linha de comando como uma tabela de hash.
Por exemplo:

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Indica que este cmdket é executado como um trabalho em segundo plano.
Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.

Quando você especifica o parâmetro *AsJob* , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.
É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.
Se **Set-WmiInstance** for usado para um computador remoto, o trabalho será criado no computador local e os resultados de computadores remotos serão retornados automaticamente para o computador local.
Para gerenciar o trabalho, use os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ).
Para obter os resultados do trabalho, use o cmdlet Receive-Job.

Para usar esse parâmetro junto com computadores remotos, os computadores locais e remotos devem ser configurados para comunicação remota.
Além disso, você deve iniciar o Windows PowerShell usando a opção Executar como administrador no Windows Vista e versões posteriores do sistema operacional Windows.
Para obter mais informações, consulte about_Remote_Requirements.

Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte about_Jobs e about_Remote_Jobs.

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
Especifica o nível de autenticação que deve ser usado com a conexão WMI.
Os valores aceitáveis para esse parâmetro são:

- -1: inalterado.
- 0: padrão.
- 1: nenhum.
Nenhuma autenticação em executada.
- 2: conectar.
A autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.
- 3: chamar.
A autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação.
- 4: pacote.
A autenticação é executada em todos os dados que são recebidos do cliente.
- 5: PacketIntegrity.
Todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.
- 6: PacketPrivacy.
As propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autoridade
Especifica a autoridade a ser usada para autenticar a conexão WMI.
É possível especificar uma autenticação padrão NTLM ou Kerberos.
Para usar o NTLM, defina a configuração da autoridade como ntlmdomain: \<DomainName\>, em que \<DomainName\> identifica um nome de domínio válido do NTLM.
Para usar o Kerberos, especifique Kerberos: \<DomainName\> \\ \<ServerName\> .
Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Classe
Especifica o nome de uma classe WMI.

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Especifica o nome do computador no qual este cmdlet é executado.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro *ComputerName* , mesmo que seu computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Especifica uma conta de usuário que tem permissão para executar esta ação.
O padrão é o usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo cmdlet Get-Credential.
Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Não há suporte para esse parâmetro em nenhum provedor instalado com o parâmetro de nenhum provedor instalado com o Windows PowerShell.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges
Indica que esse cmdlet habilita todas as permissões do usuário atual antes do comando que faz a chamada WMI.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
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

- 0: padrão.
Lê o registro local para o nível de representação padrão, que geralmente é definido como 3: Impersonate.
- 1: anônimo.
Oculta as credenciais do autor da chamada.
- 2: identificar.
Permite que os objetos consultem as credenciais do autor da chamada.
- 3: representar.
Permite que os objetos utilizem as credenciais do autor da chamada.
- 4: delegar.
Autoriza que os objetos permitam que outros objetos utilizem as credenciais do autor da chamada.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica um objeto **ManagementObject** a ser usado como entrada.
Quando esse parâmetro é usado, todos os outros parâmetros, exceto o parâmetro *arguments* , são ignorados.

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Localidade
Especifica o local preferido para objetos WMI.
O parâmetro *locale* é especificado em uma matriz no formato MS_ \<LCID\> na ordem preferida.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Especifica o namespace do repositório WMI em que a classe WMI referenciada está localizada quando usada com o parâmetro de *classe* .

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Especifica um caminho de objeto WMI da instância que você deseja criar ou atualizar.

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PutType
Indica se a instância do WMI deve ser criada ou atualizada.
Os valores aceitáveis para esse parâmetro são:

- UpdateOnly.
Atualiza uma instância existente do WMI.
- Somente Create.
Cria uma nova instância do WMI.
- UpdateOrCreate.
Atualiza a instância do WMI se ela existir, ou cria uma nova instância caso não exista.

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.
Esse parâmetro é usado junto com o parâmetro *AsJob* .
O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

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
Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

### Nenhum
Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum
Esse cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)
