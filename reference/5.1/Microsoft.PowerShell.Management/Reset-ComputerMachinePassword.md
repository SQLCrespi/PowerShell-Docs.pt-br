---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193938"
---
# Reset-ComputerMachinePassword

## SINOPSE
Redefine a senha da conta da máquina para o computador.

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Reset-ComputerMachinePassword** altera a senha da conta de computador que os computadores usam para se autenticar nos controladores de domínio no domínio.
Você pode usá-lo para redefinir a senha do computador local.

## EXEMPLOS

### Exemplo 1: redefinir a senha para o computador local

```
PS C:\> Reset-ComputerMachinePassword
```

Esse comando redefine a senha do computador local.
O comando é executado com as credenciais do usuário atual.

### Exemplo 2: redefinir a senha para o computador local usando um controlador de domínio especificado

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

Esse comando redefine a senha do computador local usando o controlador de domínio DC01.
Ele usa o parâmetro *Credential* para especificar uma conta de usuário que tenha permissão para redefinir uma senha de computador no domínio.

### Exemplo 3: redefinir a senha em um computador remoto

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

Esse comando usa o cmdlet Invoke-Command para executar um comando **Reset-ComputerMachinePassword** no computador remoto Server01.

Para obter mais informações sobre comandos remotos no Windows PowerShell, consulte about_Remote e **Invoke-Command** .

## PARAMETERS

### -Credential
Especifica uma conta de usuário que tem permissão para executar esta ação.
O padrão é o usuário atual.

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo cmdlet Get-Credential.
Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -Server
Especifica o nome de um controlador de domínio a ser usado quando esse cmdlet definir a senha da conta do computador.

Esse parâmetro é opcional.
Se você omitir esse parâmetro, um controlador de domínio é escolhido para atender ao comando.

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
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

## LINKS RELACIONADOS
