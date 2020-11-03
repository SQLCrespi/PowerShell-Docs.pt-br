---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: 17b7c534036c1146f38c9b2b16f987d90e0cb503
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193286"
---
# Get-PSDrive

## SINOPSE
Obtém as unidades na sessão atual.

## SYNTAX

### Nome (padrão)

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### Valor literal

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-PSDrive` cmdlet obtém as unidades na sessão atual. Você pode obter uma determinada unidade ou todas as unidades existentes na sessão.

Esse cmdlet obtém os seguintes tipos de unidades:

- Unidades lógicas do Windows no computador, incluindo unidades mapeadas para compartilhamentos de rede.
- Unidades expostas por provedores do PowerShell (como o certificado:, função: e alias: unidades) e as unidades HKLM: e HKCU: que são expostas pelo provedor de registro do Windows PowerShell.
- Unidades temporárias especificadas pela sessão e unidades de rede mapeadas persistentes que você cria usando o cmdlet New-PSDrive.

A partir do Windows PowerShell 3,0, o parâmetro **Persist** do `New-PSDrive` cmdlet pode criar unidades de rede mapeadas que são salvas no computador local e estão disponíveis em outras sessões. Para obter mais informações, consulte New-PSDrive.

Também, a partir do Windows PowerShell 3.0, quando uma unidade externa é conectada ao computador, o Windows PowerShell adiciona automaticamente um PSDrive ao sistema de arquivos que representa a nova unidade.
Não é necessário reiniciar o Windows PowerShell. Da mesma forma, quando uma unidade externa é desconectada do computador, o Windows PowerShell exclui automaticamente o PSDrive que representa a unidade removida.

## EXEMPLOS

### Exemplo 1: obter unidades na sessão atual

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

Esse comando obtém as unidades na sessão atual.

A saída mostra o disco rígido (C:), unidade de CD-ROM (D:) e as unidades expostas pelos provedores do Windows PowerShell (alias:, CERT:, env:, function:, HKCU:, HKLM: e Variable:).

### Exemplo 2: obter uma unidade no computador

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

Esse comando obtém a unidade D: no computador. Observe que a letra da unidade no comando não é seguida por dois pontos.

### Exemplo 3: obter todas as unidades com suporte no provedor do sistema de arquivos do Windows PowerShell

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

Esse comando obtém todas as unidades suportadas pelo provedor FileSystem do Windows PowerShell. Isso inclui unidades fixas, partições lógicas, unidades de rede mapeadas e unidades temporárias que você cria usando o cmdlet New-PSDrive.

### Exemplo 4: verificar se uma unidade está em uso como um nome de unidade do Windows PowerShell

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

Este comando verifica se a unidade X já está em uso como um nome de unidade do Windows PowerShell.
Se não estiver, o comando usará o `New-PSDrive` cmdlet para criar uma unidade temporária que é mapeada para a chave do Registro HKLM: \ Software.

### Exemplo 5: comparar os tipos de unidades do sistema de arquivos

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

Este exemplo compara os tipos de unidades do sistema de arquivos que são exibidos pelo `Get-PSDrive` para os exibidos usando outros métodos. Este exemplo demonstra diferentes maneiras de exibir unidades no Windows PowerShell e mostra que as unidades específicas da sessão criadas usando o cmdlet New-PSDrive são acessíveis somente no Windows PowerShell.

O primeiro comando usa `Get-PSDrive` para obter todas as unidades do sistema de arquivos na sessão. Isso inclui as unidades fixas (C: e D:), uma unidade de rede mapeada (G:) que foi criado usando o parâmetro **Persist** de `New-PSDrive` e uma unidade do PowerShell (T:) que foi criado usando `New-PSDrive` sem o parâmetro **Persist** .

O comando **net use** exibe as unidades de rede mapeadas do Windows, neste caso, exibe apenas a unidade G. Ele não exibe a unidade X: que foi criada pelo `New-PSDrive` . Ele mostra que a unidade G: também está mapeada para o \\ \\ GratefulDead de música \\ .

O terceiro comando usa o método **GetDrives** da classe **System.IO.DriveInfo** do Microsoft .NET Framework. Esse comando obtém as unidades do sistema de arquivos do Windows, incluindo a unidade G:, mas não obtém as unidades criadas pelo `New-PSDrive` .

O quarto comando usa o `Get-CimInstance` cmdlet para obter as instâncias da classe **Win32_LogicalDisk** . Ele retorna as unidades A:, C:, D:, E:, e G:, mas não as unidades criadas pelo `New-PSDrive` .

O último comando usa o `Get-CimInstance` cmdlet para exibir as instâncias da classe **Win32_NetworkConnection** . Como **net use** , ele retorna apenas a unidade persistente G: criada pelo `New-PSDrive` .

## PARAMETERS

### -LiteralName

Especifica o nome da unidade.

O valor de **LiteralName** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o nome inclui caracteres de escape, coloque-o entre aspas simples. As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica, como uma matriz de cadeia de caracteres, o nome ou nome das unidades que esse cmdlet obtém na operação.
Digite o nome ou a letra da unidade sem dois-pontos (:).

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Especifica, como uma matriz de cadeia de caracteres, o provedor do Windows PowerShell. Esse cmdlet obtém apenas as unidades suportadas por este provedor. Digite o nome de um provedor, como FileSystem, Registry ou Certificate.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Especifica o escopo no qual este cmdlet obtém as unidades.

Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai). "Local" é o padrão.

Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### System.Management.Automation.PSDriveInfo

Esse cmdlet retorna objetos que representam as unidades na sessão.

## OBSERVAÇÕES

* Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, use o `Get-PSProvider` cmdlet. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
* Unidades de rede mapeadas que são criadas usando o parâmetro **Persist** do cmdlet New-PSDrive são específicas para uma conta de usuário. Unidades de rede mapeadas que você cria em sessões iniciadas com a opção Executar como administrador ou com as credenciais de outro usuário não são visíveis em sessões que são iniciadas sem credenciais explícitas ou com as credenciais do usuário atual.

## LINKS RELACIONADOS

[New-PSDrive](New-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)

[Get-PSProvider](Get-PSProvider.md)

