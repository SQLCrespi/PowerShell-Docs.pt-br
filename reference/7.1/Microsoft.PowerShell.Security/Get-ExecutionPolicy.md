---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: 347ffa733068d4e7f4896eb18358c7a852c88d0a
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347271"
---
# Get-ExecutionPolicy

## SINOPSE
Obtém as políticas de execução da sessão atual.

## SYNTAX

### Tudo

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## DESCRIPTION

Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` . Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.

A política de execução efetiva é determinada pelas políticas de execução definidas pelo `Set-ExecutionPolicy` e política de grupo configurações.

Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

## EXEMPLOS

### Exemplo 1: obter todas as políticas de execução

Esse comando exibe as políticas de execução para cada escopo na ordem de precedência.

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo.

### Exemplo 2: definir uma política de execução

Este exemplo mostra como definir uma política de execução para o computador local.

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** . O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine**. Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .

### Exemplo 3: obter a política de execução efetiva

Este exemplo mostra como exibir a política de execução efetiva para uma sessão do PowerShell.

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo. O `Get-ExecutionPolicy` cmdlet é executado sem um parâmetro para exibir a política de execução efetiva, **AllSigned**.

### Exemplo 4: desbloquear um script para executá-lo sem alterar a política de execução

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

O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** . A política é definida para o escopo padrão, **LocalMachine**.

O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.

O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual. O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.

Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado. O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.

Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned**.

O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual. O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.

## PARAMETERS

### -Lista

Obtém todos os valores da política de execução para a sessão listada em ordem de precedência. Por padrão, `Get-ExecutionPolicy` obtém apenas a política de execução efetiva.

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

Especifica o escopo que é afetado por uma política de execução.

A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:

- **MachinePolicy**. Definido por um Política de Grupo para todos os usuários do computador.
- **UserPolicy**. Definido por um Política de Grupo para o usuário atual do computador.
- **Processar**. Afeta apenas a sessão atual do PowerShell.
- **CurrentUser**. Afeta somente o usuário atual.
- **LocalMachine**. Escopo padrão que afeta todos os usuários do computador.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

`Get-ExecutionPolicy` Não aceita a entrada do pipeline.

## SAÍDAS

### Microsoft.PowerShell.ExecutionPolicy

O cmdlet sempre retorna **irrestrito** em plataformas Linux e MacOS.

## OBSERVAÇÕES

Uma política de execução faz parte da estratégia de segurança do PowerShell. As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts. E se os scripts devem ser assinados digitalmente antes de serem executados.

## LINKS RELACIONADOS

[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)
