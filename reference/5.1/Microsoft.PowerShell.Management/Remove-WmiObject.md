---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193952"
---
# Remove-WmiObject

## SINOPSE
Exclui uma instância de uma classe existente do Windows Management Instrumentation (WMI).

## SYNTAX

### classe (padrão)

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### objeto

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### caminho

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Consulta

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### list

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Remove-WmiObject** exclui uma instância de uma classe de instrumentação de gerenciamento do Windows (WMI) existente.

## EXEMPLOS

### Exemplo 1: fechar todas as instâncias de um processo Win32

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

Este exemplo fecha todas as instâncias de Notepad.exe.

O primeiro comando inicia uma instância do bloco de notas.

O segundo comando usa o cmdlet Get-WmiObject para recuperar as instâncias do Win32_Process que correspondem a Notepad.exe e, em seguida, as armazena na variável $np.

O terceiro comando passa o objeto na variável $np para **Remove-WmiObject** , que exclui todas as instâncias de Notepad.exe.

### Exemplo 2: excluir uma pasta

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

Esse comando exclui a pasta C:\Test.

O primeiro comando usa **Get-WmiObject** para consultar a pasta C:\test e, em seguida, armazena o objeto na variável $a.

O segundo comando canaliza a variável $a para **Remove-WmiObject** , que exclui a pasta.

## PARAMETERS

### -AsJob
Indica que este cmdlet é executado como um trabalho em segundo plano.
Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.

Novos cmdlets do CIM, apresentados pelo Windows PowerShell 3.0, executam as mesmas tarefas que os cmdlets do WMI.
Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM), que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores que executam o sistema operacional Windows e aqueles que executam outros sistemas operacionais.
Em vez de usar **Remove-WmiObject** , considere usar o cmdlet Remove-CimInstance https://go.microsoft.com/fwlink/?LinkId=227964 .

Quando você usa o parâmetro *AsJob* , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.
É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.
Se **Remove-WmiObject** for usado em um computador remoto, o trabalho será criado no computador local e os resultados de computadores remotos serão retornados automaticamente para o computador local.
Para gerenciar o trabalho, use os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ).
Para obter os resultados do trabalho, use o cmdlet Receive-Job.

Para usar esse parâmetro para computadores remotos, os computadores locais e remotos devem ser configurados para comunicação remota.
Inicie o Windows PowerShell usando a opção Executar como administrador.
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
Especifica o nível de autenticação a ser usado para a conexão WMI.
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
Especifica o nome de uma classe WMI que este cmdlet exclui.

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
Quando esse parâmetro é utilizado, todos os outros parâmetros são ignorados.

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
O parâmetro *locale* é especificado como uma matriz no formato de MS_ \<LCID\> na ordem preferida.

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
Especifica o caminho do objeto WMI de uma classe WMI ou especifica o caminho do objeto WMI de uma instância de uma classe WMI para exclusão.

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

### System. Management. ManagementObject
É possível canalizar um objeto de gerenciamento para este cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. RemotingJob
Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro *AsJob* .
Caso contrário, ele não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Set-WmiInstance](Set-WmiInstance.md)
