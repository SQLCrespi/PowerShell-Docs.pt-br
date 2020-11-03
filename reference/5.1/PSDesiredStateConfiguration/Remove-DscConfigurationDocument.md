---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194141"
---
# Remove-DscConfigurationDocument

## SINOPSE
Remove um documento de configuração do repositório de configuração DSC.

## SYNTAX

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O `Remove-DscConfigurationDocument` cmdlet Remove um documento de configuração (arquivo. MOF) do repositório de configuração de DSC (configuração de estado desejado) do Windows PowerShell.
Durante a configuração, o `Start-DscConfiguration` cmdlet copia um arquivo. MOF para uma pasta no computador de destino.
Esse cmdlet Remove esse documento de configuração e faz uma limpeza adicional.

Esse cmdlet está disponível somente como parte do [pacote cumulativo de atualizações de novembro de 2014 para Windows RT 8,1, Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) da biblioteca suporte da Microsoft.

## EXEMPLOS

### Exemplo 1: remover o documento de configuração atual

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.
O comando solicita uma senha.
Para obter mais informações, digite `Get-Help New-CimSession`.

O segundo comando Remove o documento de configuração atual do computador especificado no **CimSession** armazenado em $Session.

## PARAMETERS

### -AsJob
Indica que esse cmdlet executa o comando como um trabalho em segundo plano.

Se você especificar o parâmetro *AsJob* , o comando retornará um objeto que representa o trabalho e, em seguida, exibirá o prompt de comando.
Você pode continuar a trabalhar na sessão até que o trabalho seja concluído.
O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.
Para gerenciar o trabalho, use os cmdlets Job.
Para obter os resultados do trabalho, use o cmdlet Receive-Job.

Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e no Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o Windows PowerShell com a opção Executar como administrador.
Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

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

### -CimSession
Executa o cmdlet em uma sessão remota ou em um computador remoto.
Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet **New-CimSession** ou **Get-CimSession** .

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indica que esse cmdlet interrompe o trabalho de configuração em execução antes de remover o documento de configuração.
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

### -Estágio
Especifica qual documento de configuração remover.
Você pode especificar vários documentos.
Os valores aceitáveis para esse parâmetro são:

- Atual.
Remova o documento de configuração que descreve o estado atual do sistema.
- Pendente.
Remova o documento de configuração que descreve o estado pendente do sistema.
- Anterior.
Remova o documento de configuração que descreve o estado anterior do sistema.

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
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

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)
