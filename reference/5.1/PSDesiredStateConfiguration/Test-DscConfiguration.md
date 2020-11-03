---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193710"
---
# Test-DscConfiguration

## SINOPSE
Testa se a configuração real nos nós corresponde à configuração desejada.

## SYNTAX

### ComputerNameSet (padrão)

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### ComputerNameAndPathSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### ComputerNameAndReferenceConfigurationSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionAndPathSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### CimSessionAndReferenceConfigurationSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Test-DscConfiguration** testa se a configuração real nos nós corresponde à configuração desejada.
Especifique os computadores para os quais você deseja testar as configurações usando nomes de computador ou sessões de modelo CIM (CIM).
Se você não especificar um computador de destino, o cmdlet testará a configuração do computador local.

Se as configurações desejadas e reais corresponderem, o cmdlet retornará um valor de cadeia de caracteres de ' true '.
Caso contrário, ele retornará um valor de cadeia de caracteres de ' false '.

## EXEMPLOS

### Exemplo 1: testar a configuração do computador local

```
PS C:\> Test-DscConfiguration
```

Esse comando testa a configuração do computador local.

### Exemplo 2: testar a configuração de um computador especificado

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

Esse exemplo testa a configuração de um computador especificado por uma sessão CIM.
O exemplo cria uma sessão CIM para um computador denominado Server01 para uso com o cmdlet.
Como alternativa, crie uma matriz de sessões CIM para aplicar o cmdlet a vários computadores especificados.

O primeiro comando cria uma sessão CIM usando o cmdlet **New-CimSession** e, em seguida, armazena o objeto **CimSession** na variável $Session.
O comando solicita uma senha.
Para obter mais informações, digite `Get-Help New-CimSession`.

O segundo comando testa a configuração dos computadores identificados pelos objetos **CimSession** armazenados na variável $Session, nesse caso, o computador denominado Server01.

### Exemplo 3: testar configurações com resultados detalhados

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

Esse comando testa as configurações de um conjunto de computadores especificado pelo parâmetro *ComputerName* e retorna informações detalhadas que incluem o estado geral, os recursos que estão no estado desejado, os recursos que não estão no estado desejado e no nome do computador.

### Exemplo 4: testar as configurações especificadas em uma pasta

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

Esse comando testa as configurações definidas em uma pasta especificada pelo parâmetro *path* .
As configurações são testadas em relação a um conjunto de computadores, cada um identificado pelo nome de arquivo do arquivo de configuração.

### Exemplo 5: testar as configurações especificadas em um arquivo

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

Esse comando testa uma configuração definida em um arquivo em relação a um conjunto de computadores especificado pelo parâmetro *ComputerName* .

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
Insira um nome de computador ou um objeto de sessão, como a saída de um cmdlet [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) ou [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
O padrão é a sessão atual do computador local.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Especifica uma matriz de nomes de computador em que esse cmdlet testa a configuração.
O cmdlet testa o documento de configuração no local especificado pelo parâmetro *path* para esses computadores.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
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
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
Indica que esse cmdlet retorna um resultado detalhado da comparação do documento de configuração com o estado desejado dos nós.
O resultado inclui informações como o estado geral, os recursos que estão no estado desejado, os recursos que não estão no estado desejado e o nome do computador.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Especifica o caminho de uma pasta que contém arquivos de documento de configuração.
O cmdlet testa a configuração em relação ao estado desejado dos computadores especificados pelo parâmetro *ComputerName* ou *CimSession* .

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceConfiguration
Especifica o caminho do arquivo de documento de configuração.
Esse cmdlet testa a configuração em relação ao estado real dos computadores especificados pelo parâmetro *ComputerName* ou *CimSession* .

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Visão geral da Desired State Configuration do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)
