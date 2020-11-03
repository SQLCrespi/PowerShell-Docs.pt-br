---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "93194838"
---
# Set-DscLocalConfigurationManager

## SINOPSE

Aplica as configurações de Configuration Manager local (LCM) a nós.

## SYNTAX

### ComputerNameSet (padrão)

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionSet

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-DscLocalConfigurationManager` cmdlet aplica as configurações do LCM, ou metaconfiguração, aos nós. Especifique computadores especificando nomes de computador ou por meio de sessões CIM (Modelo de Informações Comuns). Se você não especificar um computador de destino, o cmdlet aplicará as configurações ao computador local.

## EXEMPLOS

### Exemplo 1: aplicar as configurações do LCM

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

Esse comando aplica as configurações do LCM a partir dos `C:\DSC\Configurations\` nós de destino. Depois de receber as configurações, o LCM as processa.

> [!WARNING]
> Se houver vários meta MOFs para o mesmo computador armazenado na pasta especificada, somente o primeiro meta MOF será aplicado.

### Exemplo 2: aplicar as configurações do LCM usando uma sessão CIM

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

Este exemplo aplica as configurações do LCM a um computador e aplica as configurações. O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet. Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.

O primeiro comando cria uma sessão CIM usando o `New-CimSession` cmdlet e, em seguida, armazena o objeto **CimSession** na `$Session` variável. O comando solicita uma senha. Para obter mais informações, digite `Get-Help New-CimSession`.

O segundo comando aplica as configurações do LCM para o nó de destino do `C:\DSC\Configurations\` ao computador identificado pelos objetos **CimSession** armazenados na `$Session` variável. Neste exemplo, a `$Session` variável contém uma sessão CIM somente para o computador chamado Server01. O comando aplica as configurações. Depois de receber as configurações, o LCM as processa.

## PARAMETERS

### -CimSession

Executa o cmdlet em uma sessão remota ou em um computador remoto. Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) ou [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) .
O padrão é a sessão atual do computador local.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Especifica uma matriz de nomes de computador. Esse parâmetro restringe os computadores que têm documentos de metaconfiguração no parâmetro **path** para aqueles especificados na matriz.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential

Especifica um nome de usuário e uma senha, como um objeto **PSCredential** , para o computador de destino. Para obter um objeto **PSCredential** , use o cmdlet Get-Credential. Para obter mais informações, digite `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

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

### -Path

Especifica um caminho de arquivo de uma pasta que contém arquivos de definições de configuração. O cmdlet publica e aplica essas configurações de LCM a computadores que têm arquivos de configurações no caminho especificado. Cada nó de destino deve ter um arquivo de configurações do seguinte formato: `NetBIOS Name.meta.mof` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Especifica o número máximo de operações simultâneas que podem ser estabelecidas para executar o cmdlet. Se esse parâmetro for omitido ou um valor de `0` for inserido, o Windows PowerShell calculará um limite de aceleração ideal para o cmdlet com base no número de cmdlets CIM em execução no computador. O limite de aceleração aplica-se somente ao cmdlet atual, e não à sessão ou ao computador.

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

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/overview)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)
