---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 15aca668be08324f17a2a737214ede309370adf1
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342120"
---
# Get-HotFix

## SINOPSE
Obtém os hotfixes instalados em computadores locais ou remotos.

## SYNTAX

### Padrão (padrão)

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### Descrição

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## DESCRIPTION

O `Get-Hotfix` cmdlet obtém hotfixes ou atualizações que estão instalados no computador local ou em computadores remotos especificados. As atualizações podem ser instaladas por Windows Update, Microsoft Update, Windows Server Update Services ou instalados manualmente.

## EXEMPLOS

### Exemplo 1: obter todos os hotfixes no computador local

O `Get-Hotfix` cmdlet obtém todos os hotfixes instalados no computador local.

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### Exemplo 2: obter hotfixes de vários computadores filtrados por uma cadeia de caracteres

O `Get-Hotfix` comando usa parâmetros para obter hotfixes instalados em computadores remotos. Os resultados são filtrados por uma cadeia de caracteres de descrição especificada.

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

`Get-Hotfix` filtra a saída com o parâmetro **Description** e a **segurança** de cadeia de caracteres que inclui o curinga asterisco ( `*` ). O parâmetro **ComputerName** inclui uma cadeia de caracteres separada por vírgulas de nomes de computadores remotos. O parâmetro **Credential** especifica uma conta de usuário que tem permissão para acessar os computadores remotos e executar comandos.

### Exemplo 3: verificar se uma atualização está instalada e gravar nomes de computador em um arquivo

Os comandos neste exemplo verificam se uma atualização específica está instalada. Se a atualização não estiver instalada, o nome do computador será gravado em um arquivo de texto.

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

A `$A` variável contém nomes de computador que foram obtidos por `Get-Content` meio de um arquivo de texto. Os objetos no `$A` são enviados para o pipeline para `ForEach-Object` . Uma `if` instrução usa o `Get-Hotfix` cmdlet com o parâmetro **ID** e um número de ID específico para cada nome de computador. Se um computador não tiver a ID de hotfix especificada instalada, o `Add-Content` cmdlet gravará o nome do computador em um arquivo.

### Exemplo 4: obter o hotfix mais recente no computador local

Este exemplo obtém o hotfix mais recente instalado em um computador.

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

`Get-Hotfix` envia os objetos por meio do pipeline para o `Sort-Object` cmdlet. `Sort-Object` classifica os objetos por ordem crescente e usa o parâmetro **Property** para avaliar cada data de **instalação** . A notação de matriz `[-1]` seleciona o hotfix instalado mais recente.

## PARAMETERS

### -ComputerName

Especifica um computador remoto. Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.

Quando o parâmetro **ComputerName** não é especificado, o `Get-Hotfix` é executado no computador local.

O parâmetro **ComputerName** não depende da comunicação remota do Windows PowerShell. Se o computador não estiver configurado para executar comandos remotos, use o parâmetro **ComputerName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos. O padrão é o usuário atual

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

`Get-HotFix` usa o parâmetro **Description** para especificar os tipos de hotfix. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id

Filtra os `Get-HotFix` resultados de IDs de hotfix específicos. Caracteres curinga não são aceitos.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### String

É possível canalizar um ou mais nomes de computador para Get-HotFix.

## SAÍDAS

### System. Management. ManagementObject # root\CIMV2\ Win32_QuickFixEngineering

`Get-HotFix` retorna objetos que representam os hotfixes no computador.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

A **Win32_QuickFixEngineering** [classe WMI](/windows/desktop/WmiSdk/retrieving-a-class) Win32_QuickFixEngineering representa uma atualização pequena em todo o sistema, normalmente conhecida como atualização de QFE (Quick-Fix Engineering), aplicada ao sistema operacional atual. Essa classe retorna apenas as atualizações fornecidas pela CBS (serviço baseado em componente). Essas atualizações não estão listadas no registro. As atualizações fornecidas pelo Microsoft Windows Installer (MSI) ou pelo site do [Windows Update](https://update.microsoft.com) não são retornadas pelo **Win32_QuickFixEngineering**. Para obter mais informações, consulte [classe Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).

A `Get-HotFix` saída pode variar em sistemas operacionais diferentes.

## LINKS RELACIONADOS

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Add-Content](Add-Content.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Classe Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
