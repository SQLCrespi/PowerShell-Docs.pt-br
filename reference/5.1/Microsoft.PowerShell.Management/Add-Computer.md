---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388341"
---
# Add-Computer

## SINOPSE
Adicione o computador local para um domínio ou grupo de trabalho.

## SYNTAX

### Domínio (padrão)

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Grupo de trabalho

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Add-Computer` cmdlet adiciona o computador local ou os computadores remotos a um domínio ou grupo de trabalho, ou os move de um domínio para outro. Ele também cria uma conta de domínio caso o computador seja adicionado ao domínio sem uma conta.

Você pode usar os parâmetros desse cmdlet para especificar uma unidade organizacional (UO) e um controlador de domínio ou para realizar uma junção não segura.

Para obter os resultados do comando, utilize os parâmetros **Verbose** e **PassThru**.

## EXEMPLOS

### Exemplo 1: adicionar um computador local a um domínio e reiniciar o computador

```powershell
Add-Computer -DomainName Domain01 -Restart
```

Este comando adiciona o computador local ao domínio Domain01 e, em seguida, reinicia o computador para que as alterações entrem em vigor.

### Exemplo 2: adicionar um computador local a um grupo de trabalho

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

Este comando adiciona o computador local ao grupo de trabalho Workgroup-A.

### Exemplo 3: adicionar um computador local a um domínio

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

Este comando adiciona o computador local ao domínio Domain01 usando o controlador de domínio Domain01\DC01.

O comando usa os parâmetros **PassThru** e **Verbose** para obter informações detalhadas sobre os resultados do comando.

### Exemplo 4: adicionar um computador local a um domínio usando o parâmetro OUPath

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

Este comando adiciona o computador local ao domínio Domain02.
Ele usa o parâmetro OUPath para especificar a unidade organizacional das novas contas.

### Exemplo 5: adicionar um computador local a um domínio usando credenciais

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

Este comando adiciona o computador Server01 ao domínio Domain02. Ele usa o parâmetro **LocalCredential** para especificar uma conta de usuário com permissão para se conectar ao computador Server01. Ele usa o parâmetro **Credential** para especificar uma conta de usuário com permissão para adicionar computadores ao domínio. Ele usa o parâmetro **Restart** para reiniciar o computador após a conclusão da operação de junção e o parâmetro **Force** para suprimir mensagens de confirmação do usuário.

### Exemplo 6: mover um grupo de computadores para um novo domínio

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

Este comando move os computadores Server01 e Server02 e o computador local, de Domain01 para Domain02.

Ele usa o parâmetro **LocalCredential** para especificar uma conta de usuário com permissão para conectar-se a três computadores afetados. Ele usa o parâmetro **UnjoinDomainCredential** para especificar uma conta de usuário com permissão para sair dos computadores do domínio Domain01 e o parâmetro **Credential** para especificar uma conta de usuário com permissão para ingressar computadores ao domínio Domain02. Ele usa o parâmetro **Restart** reiniciar todos os três computadores após a conclusão da migração.

### Exemplo 7: mover um computador para um novo domínio e alterar o nome do computador

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

Este comando move o computador Server01 para o Domain02 e altera o nome do computador para Server044.

O comando usa as credenciais do usuário atual para se conectar ao computador Server01 e removê-lo do seu domínio atual. Ele usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para ingressar o computador no domínio Domain02.

### Exemplo 8: adicionar computadores listados em um arquivo a um novo domínio

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

Este comando adiciona os computadores listados no arquivo Servers.txt no domínio Domain02. Ele usa o parâmetro **Options** para especificar a opção **Win9xUpgrade**. O parâmetro **Restart** reinicia todos os computadores recentemente adicionados após a conclusão da operação de junção.

### Exemplo 9: adicionar um computador a um domínio usando credenciais de computador predefinidas

Esse primeiro comando deve ser executado por um administrador de um computador que já tenha ingressado no domínio `Domain03` :

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

Essa combinação de comandos cria uma nova conta de computador com um nome predefinido e uma senha de junção temporária em um domínio usando um computador ingressado no domínio existente. Em seguida, separadamente, um computador com o nome predefinido une o domínio usando apenas o nome do computador e a senha de junção temporária.
A senha predefinida é usada apenas para dar suporte à operação de junção e é substituída como parte dos procedimentos de conta de computador normal depois que o computador conclui a junção.

## PARAMETERS

### -ComputerName

Especifica os computadores a serem adicionados a um domínio ou grupo de trabalho.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um nome de domínio totalmente qualificado de cada um dos computadores remotos. Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou "localhost".

Esse parâmetro não depende da comunicação remota do Windows PowerShell. Você pode usar o parâmetro **ComputerName** de `Add-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tenha permissão para ingressar os computadores em um novo domínio.
O padrão é o usuário atual.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, uma senha será solicitada.

Para especificar uma conta de usuário que tenha permissão para remover o computador do seu domínio atual, utilize o parâmetro **UnjoinDomainCredential**. Para especificar uma conta de usuário que tenha permissão para conectar um computador remoto, use o parâmetro **LocalCredential**.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

Especifica o domínio ao qual os computadores são adicionados. Este parâmetro é necessário ao adicionar computadores a um domínio.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Suprime o aviso de confirmação de usuário. Sem esse parâmetro, `Add-Computer` o exige que você confirme a adição de cada computador.

Este parâmetro é introduzido no Windows PowerShell 3.0.

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

### -LocalCredential

Especifica uma conta de usuário que tenha permissão para conectar-se aos computadores que são especificados pelo parâmetro **ComputerName**. O padrão é o usuário atual.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, uma senha será solicitada.

Para especificar uma conta de usuário que tem permissão para adicionar computadores a um novo domínio, use o parâmetro **Credential**. Para especificar uma conta de usuário com permissão para remover os computadores dos seus domínios atuais, use o parâmetro **UnjoinDomainCredential**.

Este parâmetro é introduzido no Windows PowerShell 3.0.

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

### -NewName

Especifica um novo nome para o computador no novo domínio. Este parâmetro é válido somente quando um computador está sendo adicionado ou movido.

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opções

Especifica opções avançadas para a operação Adicionar ingresso no **computador** . Insira um ou mais valores em uma cadeia de caracteres separada por vírgulas.

Os valores aceitáveis para esse parâmetro são:

- **AccountCreate** : cria uma conta de domínio. O cmdlet **Add-Computer** cria automaticamente uma conta de domínio quando adiciona um computador a um domínio. Essa opção está incluída para fins de integridade.

- **Win9XUpgrade** : indica que a operação de junção faz parte de uma atualização do sistema operacional Windows.

- **UnsecuredJoin** : executa uma junção não segura. Para solicitar uma junção não segura, use o parâmetro *Unsecure* ou essa opção. Se você quiser passar uma senha de computador, deverá usar essa opção em combinação com a `PasswordPass` opção.

- **PasswordPass** : define a senha do computador para o valor do parâmetro *Credential* (DomainCredential) após a execução de uma junção não segura. Essa opção também indica que o valor do parâmetro *Credential* (DomainCredential) é uma senha de computador, não uma senha de usuário. Essa opção é válida somente quando a `UnsecuredJoin` opção é especificada. Ao usar essa opção, a credencial fornecida ao `-Credential` parâmetro *deve* ter um nome de usuário nulo.

- **JoinWithNewName** : renomeia o nome do computador no novo domínio para o nome especificado pelo parâmetro *NewName* . Quando você usa o parâmetro *NewName* , essa opção é definida automaticamente. Essa opção foi projetada para ser usada com o cmdlet Rename-Computer. Se você usar o cmdlet **Rename-Computer** para renomear o computador, mas não reiniciar o computador para que a alteração entre em vigor, poderá usar esse parâmetro para ingressar o computador em um domínio com seu novo nome.

- **JoinReadOnly** : usa uma conta de computador existente para ingressar o computador em um controlador de domínio somente leitura. A conta da máquina deve ser adicionada à lista de permissões para a política de replicação de senha e a senha da conta deve ser replicada para o controlador de domínio somente leitura antes da operação de junção.

- **InstallInvoke** : define os sinalizadores Create (0x2) e Delete (0x4) do parâmetro **FJoinOptions** do método **JoinDomainOrWorkgroup** . Para obter mais informações sobre o método **JoinDomainOrWorkgroup** , consulte [método JoinDomainOrWorkgroup da classe Win32_ComputerSystem](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).
  Para obter mais informações sobre essas opções, consulte [função NetJoinDomain](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OUPath

Especifica uma unidade organizacional (UO) para a conta de domínio. Digite o nome distinto completo da UO entre aspas. O valor padrão é o padrão da UO para objetos do computador no domínio.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

### -Restart

Reinicia os computadores que foram adicionados ao domínio ou grupo de trabalho. Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.

Este parâmetro é introduzido no Windows PowerShell 3.0.

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

### -Server

Especifica o nome de um controlador de domínio que adiciona o computador ao domínio. Digite o nome no formato DomainName\ComputerName. Por padrão, nenhum controlador de domínio é especificado.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnjoinDomainCredential

Especifica uma conta de usuário que tenha permissão para remover os computadores de seus domínios atuais. O padrão é o usuário atual.

Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, uma senha será solicitada.

Use esse parâmetro quando você estiver movendo computadores para um domínio diferente. Para especificar uma conta de usuário que tenha permissão para ingressar no novo domínio, use o parâmetro **Credential**. Para especificar uma conta de usuário que tenha permissão para conectar um computador remoto, use o parâmetro **LocalCredential**.

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sem segurança

Executa um ingresso não seguro no domínio especificado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

Especifica o nome de um grupo de trabalho para o qual os computadores são adicionados. O valor padrão é "WORKGROUP".

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar nomes de computador e novos nomes para o `Add-Computer` cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. ComputerChangeInfo

Quando você usa o parâmetro **PassThru** , `Add-Computer` retorna um objeto **ComputerChangeInfo** .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

- No Windows PowerShell 2,0, o **Server** parâmetro de servidor `Add-Computer` falha mesmo quando o servidor está presente. No Windows PowerShell 3.0, a implementação do parâmetro **Server** é alterada para que ele funcione de forma confiável.

## LINKS RELACIONADOS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
