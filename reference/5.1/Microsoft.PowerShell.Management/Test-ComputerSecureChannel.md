---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193902"
---
# Test-ComputerSecureChannel

## SINOPSE
Testa e repara o canal seguro entre o computador local e seu domínio.

## SYNTAX

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Test-ComputerSecureChannel** verifica se o canal entre o computador local e seu domínio está funcionando corretamente verificando o status de suas relações de confiança.
Se uma conexão falhar, você poderá usar o parâmetro de *reparo* para tentar restaurá-lo.

**Test-ComputerSecureChannel** retornará $true se o canal estiver funcionando corretamente e $false se não estiver.
Esse resultado permite a você usar o cmdlet em instruções condicionais presentes em funções e scripts.
Para obter resultados de teste mais detalhados, use o parâmetro *Verbose* .

Esse cmdlet funciona de modo muito similar ao NetDom.exe.
O NetDom e o **Test-ComputerSecureChannel** usam o serviço **Netlogon** para executar as ações.

## EXEMPLOS

### Exemplo 1: testar um canal entre o computador local e seu domínio

```
PS C:\> Test-ComputerSecureChannel
True
```

Esse comando testa o canal entre o computador local e o domínio ao qual ele está associado.

### Exemplo 2: testar um canal entre o computador local e um controlador de domínio

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

Este comando especifica um controlador de domínio preferencial para o teste.

### Exemplo 3: redefinir o canal entre o computador local e seu domínio

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

Esse comando redefine o canal entre o computador local e seu domínio.

### Exemplo 4: exibir informações detalhadas sobre o teste

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

Esse comando usa o parâmetro comum *detalhado* para solicitar mensagens detalhadas sobre a operação.
Para obter mais informações sobre o *modo detalhado* , consulte about_Commonparameters.

### Exemplo 5: testar uma conexão antes de executar um script

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

Este exemplo mostra como usar **Test-ComputerSecureChannel** para testar uma conexão antes de executar um script que requer a conexão.

O primeiro comando usa o cmdlet Set-Alias para criar um alias para o nome do cmdlet.
Isso economiza espaço e evita erros de digitação.

A instrução **If** verifica o valor que **Test-ComputerSecureChannel** retorna antes de executar um script.

## PARAMETERS

### -Credential
Especifica uma conta de usuário que tem permissão para executar esta ação.
Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um que o cmdlet Get-Credential retorna.
Por padrão, o cmdlet usa as credenciais do usuário atual.

O parâmetro *Credential* é projetado para uso em comandos que usam o parâmetro *Repair* para reparar o canal entre o computador e o domínio.

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

### -Reparar
Indica que esse cmdlet Remove e, em seguida, recria o canal estabelecido pelo serviço NetLogon.
Use este parâmetro para tentar restaurar uma conexão que falhou no teste.

Para usar este parâmetro, o usuário atual precisa ser membro do grupo Administradores no computador local.

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

### -Server
Especifica o controlador de domínio para executar o comando.
Se esse parâmetro não for especificado, esse cmdlet selecionará um controlador de domínio padrão para a operação.

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

### System.Boolean
Esse cmdlet retornará $True se a conexão estiver funcionando corretamente e $False se não estiver.

## OBSERVAÇÕES

* Para executar um comando **Test-ComputerSecureChannel** no Windows Vista e versões posteriores do sistema operacional Windows, abra o Windows PowerShell usando a opção Executar como administrador.
* O **Test-ComputerSecureChannel** é implementado usando a função **I_NetLogonControl2** , que controla vários aspectos do serviço Netlogon.

## LINKS RELACIONADOS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
