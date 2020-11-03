---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194138"
---
# Start-DscConfiguration

## SINOPSE
Aplica configuração a nós.

## SYNTAX

### ComputerNameAndPathSet (padrão)

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimSessionAndPathSet

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Start-DscConfiguration** aplica configuração aos nós.
Quando usado com o parâmetro *UseExisting* , a configuração existente no computador de destino é aplicada.
Especifique os computadores aos quais você deseja aplicar a configuração especificando nomes de computador ou usando sessões de modelo CIM (CIM).

Por padrão, esse cmdlet cria um trabalho e retorna um objeto **Job** .
Para obter mais informações sobre trabalhos em segundo plano, digite `Get-Help about_Jobs` .
Para usar esse cmdlet interativamente, especifique o parâmetro *Wait* .

Especifique o parâmetro *Verbose* para ver os detalhes do que o cmdlet faz ao aplicar as definições de configuração.

## EXEMPLOS

### Exemplo 1: aplicar definições de configuração

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

Esse comando aplica as configurações de C:\DSC\Configurations\ a cada computador que tem as configurações nessa pasta.
O comando retorna objetos **Job** para cada nó de destino implantado.

### Exemplo 2: aplicar definições de configuração e aguardar a conclusão da configuração

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

Este comando aplica a configuração de C:\DSC\Configurations\ ao computador local.
O comando retorna objetos **Job** para cada nó de destino implantado, nesse caso, apenas o computador local.
Este exemplo especifica o parâmetro *Verbose* .
Portanto, o comando envia mensagens para o console conforme ele prossegue.
O comando inclui o parâmetro *Wait* .
Portanto, você não pode usar o console do até que o comando conclua todas as tarefas de configuração.

### Exemplo 3: aplicar definições de configuração usando uma sessão CIM

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

Este exemplo aplica configurações a um computador especificado.
O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.
Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.

O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.
O comando solicita uma senha.
Para obter mais informações, digite `Get-Help NewCimSession`.

O segundo comando aplica os parâmetros de configuração de C:\DSC\Configurations\ aos computadores identificados pelos objetos **CimSession** armazenados na variável $Session.
Neste exemplo, a variável $Session contém uma sessão CIM apenas para o computador denominado Server01.
O comando aplica a configuração.
O comando cria objetos **Job** para cada computador configurado.

## PARAMETERS

### -CimSession
Executa o cmdlet em uma sessão remota ou em um computador remoto.
Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
O padrão é a sessão atual do computador local.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Especifica uma matriz de nomes de computador.
Esse parâmetro restringe os computadores que têm documentos de configuração no parâmetro *path* para os especificados na matriz.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino.
Para obter um objeto **PSCredential** , use o cmdlet Get-Credential.
Para obter mais informações, digite `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Interrompe a operação de configuração atualmente em execução no computador de destino e inicia a nova operação de Start-Configuration.
Se a propriedade **RefreshMode** do Configuration Manager local for definida como **pull** , a especificação desse parâmetro o alterará para **Push** .

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

### -JobName
Especifica um nome amigável para um trabalho.
Se você especificar esse parâmetro, o cmdlet será executado como um trabalho e retorna um objeto **Job** .

Por padrão, o Windows PowerShell atribui o nome JobN onde N é um inteiro.

Se você especificar o parâmetro *Wait* , não especifique esse parâmetro.

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

### -Path
Especifica um caminho de arquivo de uma pasta que contém arquivos de definições de configuração.
Esse cmdlet publica e aplica essas definições de configuração a computadores que têm arquivos de configurações no caminho especificado.
Cada nó de destino deve ter um arquivo de configurações do seguinte formato: NetBIOS Name. mof.

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet.
Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador.
O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.

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

### -UseExisting
Indica que este cmdlet aplica a configuração existente.
A configuração pode existir no computador de destino por aplicação usando **Start-DscConfiguration** ou por publicação usando o cmdlet Publish-DscConfiguration.

Antes de especificar esse parâmetro para esse cmdlet, examine as informações em [novidades no Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Indica que o cmdlet bloqueia o console até que ele termine todas as tarefas de configuração.

Se você especificar esse parâmetro, não especifique o parâmetro *JobName* .

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

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/overview)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)
