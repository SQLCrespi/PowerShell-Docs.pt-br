---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: d3724c79f5864295c70d5addd46a8a133862d0ec
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193122"
---
# Set-ExecutionPolicy

## SINOPSE
Define as políticas de execução do PowerShell para computadores Windows.

## SYNTAX

### Tudo

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-ExecutionPolicy` cmdlet altera as políticas de execução do PowerShell para computadores Windows. Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

A partir do PowerShell 6,0 para computadores não Windows, a política de execução padrão é **irrestrita** e não pode ser alterada. O `Set-ExecutionPolicy` cmdlet está disponível, mas o PowerShell exibe uma mensagem de console que não tem suporte.

Uma política de execução faz parte da estratégia de segurança do PowerShell. As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts. E se os scripts devem ser assinados digitalmente antes de serem executados.

O `Set-ExecutionPolicy` escopo padrão do cmdlet é **LocalMachine** , o que afeta todos os que usam o computador. Para alterar a política de execução para **LocalMachine** , inicie o PowerShell com **Executar como administrador** .

Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` . Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.

## EXEMPLOS

### Exemplo 1: definir uma política de execução

Este exemplo mostra como definir a política de execução para o computador local.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** . O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** . Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .

### Exemplo 2: definir uma política de execução que está em conflito com um Política de Grupo

Esse comando tenta definir a política de execução do escopo de **LocalMachine** como **restrita** .
**LocalMachine** é mais restritiva, mas não é a política efetiva porque está em conflito com um política de grupo. A política **restrita** é gravada no hive do registro **HKEY_LOCAL_MACHINE** .

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **restrita** . O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .
O `Get-ChildItem` cmdlet usa o parâmetro **Path** com o provedor **HKLM** para especificar o local do registro.

### Exemplo 3: aplicar a política de execução de um computador remoto a um computador local

Esse comando obtém o objeto de política de execução de um computador remoto e define a política no computador local. `Get-ExecutionPolicy` envia um objeto **Microsoft.PowerShell.ExecutionPolicy** para baixo do pipeline. `Set-ExecutionPolicy` aceita a entrada de pipeline e não requer o parâmetro **ExecutionPolicy** .

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

O `Invoke-Command` cmdlet é executado no computador local e envia o **scriptblock** para o computador remoto. O parâmetro **ComputerName** especifica o computador remoto, **Server01** . O parâmetro **scriptblock** é executado `Get-ExecutionPolicy` no computador remoto. O `Get-ExecutionPolicy` objeto é enviado ao pipeline para o `Set-ExecutionPolicy` .
`Set-ExecutionPolicy` aplica a política de execução ao escopo padrão do computador local, **LocalMachine** .

### Exemplo 4: definir o escopo para uma política de execução

Este exemplo mostra como definir uma política de execução para um escopo especificado, **CurrentUser** . O escopo **CurrentUser** só afeta o usuário que define esse escopo.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** .
O parâmetro **Scope** especifica o **CurrentUser** . Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .

A política de execução efetiva para o usuário torna-se **AllSigned** .

### Exemplo 5: remover a política de execução para o usuário atual

Este exemplo mostra como usar a política de execução **indefinida** para remover uma política de execução para um escopo especificado.

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **indefinida** .
O parâmetro **Scope** especifica o **CurrentUser** . Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .

### Exemplo 6: definir a política de execução para a sessão atual do PowerShell

O escopo do **processo** afeta apenas a sessão atual do PowerShell. A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` e é excluída quando a sessão é fechada.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** . O parâmetro **Scope** especifica o **processo** de valor. Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .

### Exemplo 7: desbloquear um script para executá-lo sem alterar a política de execução

Este exemplo mostra como a política de execução **RemoteSigned** impede que você execute scripts não assinados.

Uma prática recomendada é ler o código do script e verificar se ele é seguro **antes** de usar o `Unblock-File` cmdlet. O `Unblock-File` cmdlet desbloqueia scripts para que eles possam ser executados, mas não altera a política de execução.

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** . A política é definida para o escopo padrão, **LocalMachine** .

O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.

O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual. O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.

Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado. O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.

Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned** .

O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual. O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.

## PARAMETERS

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

### -ExecutionPolicy

Especifica a política de execução. Se não houver nenhuma política de grupo e a diretiva de execução de cada escopo estiver definida como **indefinida** , a **restrição** se tornará a política efetiva para todos os usuários.

Os valores de política de execução aceitáveis são os seguintes:

- **AllSigned** . Requer que todos os scripts e arquivos de configuração sejam assinados por um fornecedor confiável, incluindo scripts gravados no computador local.
- **Bypass** . Nada está bloqueado e não há avisos ou prompts.
- **Default** . Define a política de execução padrão. **Restrito** para clientes Windows ou **RemoteSigned** para Windows Servers.
- **RemoteSigned** . Requer que todos os scripts e arquivos de configuração baixados da Internet sejam assinados por um fornecedor confiável. A política de execução padrão para computadores Windows Server.
- **Restrito** . Não carrega arquivos de configuração nem executa scripts. Os computadores cliente do Windows da política de execução padrão.
- **Indefinido** . Nenhuma política de execução está definida para o escopo. Remove uma política de execução atribuída de um escopo que não está definido por um Política de Grupo. Se a política de execução em todos os escopos for **indefinida** , a política de execução efetiva será **restrita** .
- **Irrestrito** . A partir do PowerShell 6,0, essa é a política de execução padrão para computadores não Windows e não pode ser alterada. Carrega todos os arquivos de configuração e executa todos os scripts. Se você executar um script não assinado que foi baixado da Internet, sua permissão será solicitada antes de ser executada.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force

Suprime todas as solicitações de confirmação. Tome cuidado com esse parâmetro para evitar resultados inesperados.

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

Especifica o escopo que é afetado por uma política de execução. O escopo padrão é **LocalMachine** .

A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:

- **MachinePolicy** . Definido por um Política de Grupo para todos os usuários do computador.
- **UserPolicy** . Definido por um Política de Grupo para o usuário atual do computador.
- **Processar** . Afeta apenas a sessão atual do PowerShell.
- **CurrentUser** . Afeta somente o usuário atual.
- **LocalMachine** . Escopo padrão que afeta todos os usuários do computador.

O escopo do **processo** afeta apenas a sessão atual do PowerShell. A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` , em vez de no registro. Quando a sessão do PowerShell é fechada, a variável e o valor são excluídos.

As políticas de execução para o escopo **CurrentUser** são gravadas no hive do registro **HKEY_LOCAL_USER** .

As políticas de execução para o escopo **LocalMachine** são gravadas no hive do registro **HKEY_LOCAL_MACHINE** .

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.PowerShell.ExecutionPolicy, System. String

É possível canalizar um objeto de política de execução ou uma cadeia de caracteres que contém o nome de uma política de execução para `Set-ExecutionPolicy` .

## SAÍDAS

### Nenhum

`Set-ExecutionPolicy` Não retorna nenhuma saída.

## OBSERVAÇÕES

`Set-ExecutionPolicy` Não altera os escopos **MachinePolicy** e **UserPolicy** porque eles são definidos por políticas de grupo.

`Set-ExecutionPolicy` não substitui um Política de Grupo, mesmo que a preferência do usuário seja mais restritiva do que a política.

Se a Política de Grupo **ativar a execução do script** estiver habilitada para o computador ou usuário, a preferência do usuário será salva, mas não será eficaz. O PowerShell exibe uma mensagem que explica o conflito.

## LINKS RELACIONADOS

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Unblock-File](../Microsoft.PowerShell.Utility/Unblock-File.md)
