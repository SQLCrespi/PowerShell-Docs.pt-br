---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194185"
---
# Get-ControlPanelItem

## SINOPSE
Obtém itens do painel de controle.

## SYNTAX

### Regularname (padrão)

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### Canônicaname

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-ControlPanelItem` cmdlet obtém itens do painel de controle no computador local. Você pode usá-lo para localizar os itens do painel de controle por nome, categoria ou descrição, mesmo em sistemas que não têm uma interface de usuário.

Esse cmdlet obtém apenas os itens do painel de controle que podem ser abertos no sistema. Em computadores que não têm o painel de controle ou o explorador de arquivos, esse cmdlet obtém apenas os itens do painel de controle que podem ser abertos sem esses componentes.

Este cmdlet foi introduzido no Windows PowerShell 3.0. Ele funciona apenas no Windows 8 e no Windows Server 2012 e mais recente.

## EXEMPLOS

### Exemplo 1: obter todos os itens do painel de controle

Este comando obtém todos os itens do Painel de controle no computador local.

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### Exemplo 2: obter itens do painel de controle por nome

Este exemplo obtém itens do painel de controle que têm programa ou aplicativo em seus nomes.

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### Exemplo 3: obter itens do painel de controle por categoria

Esse comando obtém todos os itens do painel de controle em categorias que têm segurança em seus nomes.

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### Exemplo 4: abrir um item do painel de controle

Este exemplo abre o item do painel de controle do firewall do Windows no computador local.

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

O `Get-ControlPanelItem` cmdlet obtém o item do painel de controle. O `Show-ControlPanelItem` cmdlet o abre.

### Exemplo 5: obter itens do painel de controle em um computador remoto

Este exemplo obtém o Criptografia de Unidade de Disco BitLocker item do painel de controle no computador remoto Server01.
O `Invoke-Command` cmdlet executa o `Get-ControlPanelItem` cmdlet remotamente.

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### Exemplo 6: Pesquisar as descrições dos itens do painel de controle

Este exemplo pesquisa a propriedade **Description** dos itens do painel de controle para obter apenas os que contêm o nome do **dispositivo** .

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

O `Get-ControlPanelItem` cmdlet obtém todos os itens do painel de controle. O `Where-Object` cmdlet filtra os itens pelo valor da propriedade **Description** .

## PARAMETERS

### -Canôniconame

Especifica, como uma matriz de cadeia de caracteres, os itens do painel de controle por seus nomes canônicos ou padrões de nome que esse cmdlet obtém. Caracteres curinga são permitidos. Se você inserir vários nomes, esse cmdlet obterá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador "or".

Por padrão, esse cmdlet obtém todos os itens do painel de controle no sistema.

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Categoria

Especifica, como uma matriz de cadeia de caracteres, as categorias dos itens do painel de controle nas categorias especificadas que esse cmdlet obtém. Digite um nome de categoria ou o padrão de nome. Caracteres curinga são permitidos. Se você inserir vários nomes, esse cmdlet obterá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador "or". Por padrão, esse cmdlet obtém todos os itens do painel de controle no sistema.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Especifica, como uma matriz de cadeia de caracteres, os nomes ou padrões de nome do painel de controle que esse cmdlet obtém.
Caracteres curinga são permitidos. Você também pode canalizar um nome ou padrão de nome para esse cmdlet.

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar um nome ou padrão de nome para esse cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. ControlPanelItem

Esse cmdlet obtém itens do painel de controle no computador local.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Show-ControlPanelItem](Show-ControlPanelItem.md)
