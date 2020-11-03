---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193917"
---
# Show-ControlPanelItem

## SINOPSE
Abre itens do painel de controle.

## SYNTAX

### Regularname (padrão)

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### Canônicaname

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### ControlPanelItem

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Show-ControlPanelItem` cmdlet abre itens do painel de controle no computador local. Você pode usá-lo para abrir itens do painel de controle por nome, categoria ou descrição, mesmo em sistemas que não têm uma interface do usuário. Você pode canalizar itens do painel de controle do `Get-ControlPanelItem` cmdlet para `Show-ControlPanelItem` .

`Show-ControlPanelItem` pesquisa somente os itens do painel de controle que podem ser abertos no sistema. Em computadores que não têm o **painel de controle** ou o **Explorador de arquivos** , o `Show-ControlPanelItem` pesquisa somente os itens do painel de controle que podem ser abertos sem esses componentes.

Esse cmdlet foi introduzido no Windows PowerShell 3,0 e funciona no Windows 8, no Windows Server 2012 e em versões posteriores.

## EXEMPLOS

### Exemplo 1: mostrar um item do painel de controle

Este exemplo inicia o item do painel de controle de **reprodução automática** .

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### Exemplo 2: canalizar um item do painel de controle para este cmdlet

Este exemplo abre o item do painel de controle do **Windows Defender firewall** no computador local.
O nome do item do painel de controle do firewall do Windows foi alterado nas versões do Windows. Este exemplo usa um padrão curinga para localizar o item do painel de controle.

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem` Obtém o item do painel de controle e o `Show-ControlPanelItem` cmdlet o abre.

### Exemplo 3: usar um nome de arquivo para abrir um item do painel de controle

Este exemplo abre o item do painel de controle **programas e recursos** usando seu nome de aplicativo.

```powershell
appwiz.cpl
```

Esse método é uma alternativa ao uso de um `Show-ControlPanelItem` comando.

> [!NOTE]
> No PowerShell, você pode omitir a extensão de arquivo. cpl para arquivos do painel de controle porque ele está incluído no valor da `$env:PathExt` variável de ambiente.

## PARAMETERS

### -Canôniconame

Especifica itens do painel de controle usando os nomes canônicos ou padrões de nome especificados. Caracteres curinga são permitidos. Se você inserir vários nomes, esse cmdlet abrirá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador **or** .

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

### -InputObject

Especifica os itens do painel de controle a serem abertos por meio do envio de objetos de item do painel de controle. Insira uma variável que contenha objetos de item do painel de controle ou digite um comando ou uma expressão que obtenha objetos de item do painel de controle, como `Get-ControlPanelItem` .

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes dos itens do painel de controle. Caracteres curinga são permitidos. Se você inserir vários nomes, esse cmdlet abrirá itens do painel de controle que correspondem a qualquer um dos nomes, como se os itens na lista de nomes fossem separados por um operador **or** .

```yaml
Type: System.String[]
Parameter Sets: RegularName
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

### System. String, Microsoft. PowerShell. Commands. ControlPanelItem

É possível canalizar um nome ou objeto de item do painel de controle para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-ControlPanelItem](Get-ControlPanelItem.md)
