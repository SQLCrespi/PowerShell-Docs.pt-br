---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: ea57ae0b3affcbe060b74c6cc21e6df6d50e50ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194604"
---
# Test-PSSessionConfigurationFile

## SINOPSE
Verifica as chaves e os valores em um arquivo de configuração de sessão.

## SYNTAX

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet verifica se um arquivo de configuração de sessão contém chaves válidas e se os valores são do tipo correto. Para valores enumerados, o cmdlet verifica se os valores especificados são válidos.

O cmdlet retornará `$True` se o arquivo passar por todos os testes e se não tiver `$False` . Para encontrar erros, use o parâmetro **Verbose** .

`Test-PSSessionConfigurationFile` Verifica os arquivos de configuração de sessão, como aqueles criados pelo `New-PSSessionConfigurationFile` cmdlet. Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md). Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Esse cmdlet foi introduzido no PowerShell 3,0.

## EXEMPLOS

### Exemplo 1: testar um arquivo de configuração de sessão

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### Exemplo 2: testar o arquivo de configuração de sessão de uma configuração de sessão

Neste exemplo, testamos o arquivo de configuração usado na configuração de sessão **restrita** .
O valor do parâmetro **path** é o resultado do `Get-PSSessionConfiguration` comando que obtém a configuração de sessão **restrita** . O caminho do arquivo de configuração de sessão é armazenado no valor da propriedade **ConfigFilePath** da configuração de sessão.

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### Exemplo 3: testar todos os arquivos de configuração de sessão

A função neste exemplo testa todos os arquivos de configuração de sessão no computador local. A função usa o `Get-PSSessionConfiguration` cmdlet para obter todas as configurações de sessão. O código dentro do `ForEach-Object` loop exibe o caminho do arquivo e testa cada uma das configurações de sessão.

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

A propriedade **ConfigFilePath** de uma configuração de sessão contém o caminho do arquivo de configuração de sessão que é usado na configuração da sessão, se houver.

Se o valor da propriedade **ConfigFilePath** estiver preenchido (é verdadeiro), o comando obtém (imprime) o valor da propriedade **ConfigFilePath** . Em seguida, ele usa o `Test-PSSessionConfigurationFile` cmdlet para testar o arquivo no valor **ConfigFilePath** . O parâmetro **Verbose** retorna o erro de arquivo quando o arquivo falha no teste.

## PARAMETERS

### -Path

Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC). Se você omitir o caminho, o padrão será a pasta atual. Há suporte para caracteres curinga, mas eles devem ser resolvidos para um único arquivo. Também é possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar um caminho de arquivo de configuração de sessão para `Test-PSSessionConfigurationFile` .

## SAÍDAS

### System.Boolean

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
