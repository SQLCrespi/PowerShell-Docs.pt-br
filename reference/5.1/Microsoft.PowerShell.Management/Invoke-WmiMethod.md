---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "93194832"
---
# Invoke-WmiMethod

## SINOPSE
Chama os métodos WMI.

## SYNTAX

### classe (padrão)

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### objeto

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### caminho

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Consulta

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-WmiMethod` cmdlet chama os métodos de objetos Instrumentação de gerenciamento do Windows (WMI).

Novos cmdlets de modelo CIM (CIM), introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI. Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão CIM, que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores Windows e aqueles que executam outros sistemas operacionais. Em vez de usar `Invoke-WmiMethod` , considere o uso [de Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).

## EXEMPLOS

### Exemplo 1: listar a ordem necessária de objetos WMI

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

Esse comando lista a ordem dos objetos exigida. Invocar o WMI no PowerShell 3.0 difere de métodos alternativos e requer que os valores de objeto sejam inseridos em uma ordem específica.

### Exemplo 2: iniciar uma instância de um aplicativo

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

Esse comando inicia uma instância do bloco de notas chamando o `Create` método da classe **Win32_Process** .

A propriedade **ReturnValue** é populada com um 0 e a propriedade **ProcessId** é populada com um inteiro (o próximo número de ID do processo) se o comando for concluído.

### Exemplo 3: renomear um arquivo

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

Este comando renomeia um arquivo. Ele usa o parâmetro **path** para fazer referência a uma instância da classe **CIM_Datafile** . Em seguida, ele aplica o método Rename àquela instância específica.

A propriedade **ReturnValue** será populada com um 0 se o comando for concluído.

### Exemplo 4: passando uma matriz de valores usando `-ArgumentList`

Um exemplo que usa uma matriz de objetos `$binSD` seguida por um `$null` valor.

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## PARAMETERS

### -ArgumentList

Especifica os parâmetros a passar para o método chamado. O valor desse parâmetro deve ser uma matriz de objetos e deve aparecer na ordem exigida pelo método chamado. O `Invoke-CimCommand` cmdlet não tem essas limitações.

Para determinar a ordem na qual listar esses objetos, execute o `GetMethodParameters()` método na classe WMI, conforme ilustrado no exemplo 1, próximo ao final deste tópico.

> [!IMPORTANT]
> Se o primeiro valor é uma matriz que contém mais de um elemento, um segundo valor de $null é necessário. Caso contrário, o comando gera um erro, como "Não é possível converter o objeto do tipo 'System.Byte' para o tipo 'System. Array'.". Consulte o exemplo 4 acima.

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Indica que esse cmdlet executa o comando como um trabalho em segundo plano. Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.

Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando. É possível continuar a trabalhar na sessão enquanto o trabalho é concluído. Se `Invoke-WmiMethod` é usado em um computador remoto, o trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local. Para gerenciar o trabalho, use os cmdlets que contêm o substantivo Job (os cmdlets Job). Para obter os resultados do trabalho, use o cmdlet Receive-Job.

Para utilizar esse parâmetro com computadores remotos, os computadores local e remoto precisam ser configurados para acesso remoto. Além disso, você deve iniciar o Windows PowerShell usando a opção Executar como administrador no Windows Vista e versões posteriores do Windows. Para obter mais informações, consulte about_Remote_Requirements.

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

Especifica o nível de autenticação a ser usado com a conexão WMI. Os valores aceitáveis para esse parâmetro são:

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

Especifica a autoridade a ser usada para autenticar a conexão WMI. Você pode especificar a autenticação NTLM (Windows NT LAN Manager) ou Kerberos padrão. Para usar o NTLM, defina a configuração da autoridade como ntlmdomain: \<DomainName\>, em que \<DomainName\> identifica um nome de domínio válido do NTLM. Para usar o Kerberos, especifique kerberos: \<DomainName\ServerName\>. Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.

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

Especifica a classe WMI que contém um método estático para realização de chamadas.

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

Especifica, como uma matriz de cadeia de caracteres, os computadores em que esse cmdlet executa o comando. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores. Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell. Você pode usar o parâmetro **ComputerName** , mesmo que seu computador não esteja configurado para executar comandos remotos.

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

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual. Digite um nome de usuário, como `User01` , `Domain01\User01` ou `User@Contoso.com` . Ou insira um objeto **PSCredential** , como um objeto que é retornado pelo cmdlet Get-Credential. Quando você digitar um nome de usuário, uma senha será solicitada.

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

Indica que esse cmdlet habilita todos os privilégios do usuário atual antes que o comando faça a chamada WMI.

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

Especifica o nível de representação a ser usado. Os valores aceitáveis para esse parâmetro são:

- 0: padrão (lê o registro local para o nível de representação padrão, que geralmente é definido como "3: Impersonate".)
- 1: anônimo (oculta as credenciais do chamador).
- 2: identificar (permite que os objetos consultem as credenciais do chamador).
- 3: representar (permite que os objetos usem as credenciais do chamador.)
- 4: delegate (permite que os objetos permitam que outros objetos usem as credenciais do chamador.)

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

Especifica um objeto **ManagementObject** a ser usado como entrada. Quando esse parâmetro é usado, todos os outros parâmetros, exceto os parâmetros **Flag** e **Argument** , são ignorados.

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

Especifica o local preferido para objetos WMI. Especifique o valor do parâmetro **locale** como uma matriz no `MS_<LCID>` formato na ordem preferida.

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

### -Name

Especifica o nome do método a ser invocado. Este parâmetro é obrigatório e não pode ser nulo ou vazio.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Quando usado com o parâmetro **Class** , esse parâmetro especifica o namespace do repositório WMI em que a classe WMI ou o objeto referenciado está localizado.

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

Especifica o caminho do objeto WMI de uma classe WMI, ou então especifica o caminho do objeto WMI de uma instância de uma classe WMI. A classe ou a instância especificada deve conter o método especificado no parâmetro **Name** .

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

### -ThrottleLimit

Especifica um valor de limitação para o número de operações WMI que podem ser executadas simultaneamente.
Esse parâmetro é usado junto com o parâmetro **AsJob** . O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.

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

### Nenhum

Esse cmdlet não aceita nenhuma entrada.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[Get-WmiObject](Get-WmiObject.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)
