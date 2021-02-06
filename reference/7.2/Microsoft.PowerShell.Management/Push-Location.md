---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: eaa7622e29680de4228579f8b77a6c829a586bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596595"
---
# Push-Location

## SINOPSE
Adiciona o local atual no topo de uma pilha de local.

## SYNTAX

### Caminho (padrão)

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### LiteralPath

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Push-Location` cmdlet adiciona ("envia") o local atual em uma pilha de local. Se você especificar um caminho, `Push-Location` o enviará o local atual para uma pilha de local e, em seguida, alterará o local atual para o local especificado pelo caminho. Você pode usar o `Pop-Location` cmdlet para obter locais da pilha de locais.

Por padrão, o `Push-Location` cmdlet envia o local atual para a pilha de locais atual, mas você pode usar o parâmetro **StackName** para especificar uma pilha de local alternativa. Se a pilha não existir, a `Push-Location` criará.

Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

## EXEMPLOS

### Exemplo 1

Este exemplo envia por push o local atual para a pilha de locais padrão e, em seguida, altera o local para `C:\Windows` .

```
PS C:\> Push-Location C:\Windows
```

### Exemplo 2

Este exemplo envia por push o local atual para a pilha RegFunction e altera o local atual para o `HKLM:\Software\Policies` local.

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

Você pode usar os cmdlets de local em qualquer unidade do PowerShell (PSDrive).

### Exemplo 3

Esse comando envia o local atual para a pilha padrão. O local não é alterado.

```
PS C:\> Push-Location
```

### Exemplo 4-criar e usar uma pilha nomeada

Esses comandos mostram como criar e usar uma pilha local nomeada.

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

O primeiro comando envia o local atual para uma nova pilha chamada Stack2 e, em seguida, altera o local atual para o diretório base, representado no comando pelo símbolo de til ( `~` ), que quando usado em uma unidade do provedor FileSystem é equivalente a `$HOME` and `$env:USERPROFILE` .

Se Stack2 ainda não existir na sessão, o o `Push-Location` criará. O segundo comando usa o `Pop-Location` cmdlet para exibir o local original ( `C:\` ) da pilha Stack2. Sem o parâmetro **StackName** , `Pop-Location` seria exibido o local da pilha padrão sem nome.

Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

## PARAMETERS

### -LiteralPath

Especifica o caminho para o local de destino. Ao contrário do parâmetro **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Passa um objeto representando o local para o pipeline. Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Altera seu local no local especificado por esse caminho depois de adicionado (enviado) o local atual para o topo da pilha. Insira um caminho para qualquer local cujo provedor oferece suporte a esse cmdlet. Caracteres curinga são permitidos. O nome do parâmetro é opcional.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StackName

Especifica a pilha local à qual o local atual será adicionado. Digite um nome de pilha de local.
Se a pilha não existir, a `Push-Location` criará.

Sem esse parâmetro, `Push-Location` o adiciona o local à pilha de locais atual. Por padrão, a pilha de local atual é a pilha de locais padrão sem nome que o PowerShell cria.
Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet. Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

> [!NOTE]
> `Push-Location` Não é possível adicionar um local à pilha padrão sem nome, a menos que ela seja a pilha de local atual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho (mas não um caminho literal) para `Push-Location` .

## SAÍDAS

### Nenhum ou System. Management. Automation. PathInfo

Quando você usa o parâmetro **PassThru** , o `Push-Location` gera um objeto **System. Management. Automation. PathInfo** que representa o local. Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

O PowerShell dá suporte a vários Runspaces por processo. Cada runspace tem seu próprio _diretório atual_.
Isso não é o mesmo que `[System.Environment]::CurrentDirectory` . Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.

Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento. Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.

Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente está acessível.
Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa. O PowerShell permite que você armazene locais de provedores em pilhas de locais.

O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas. Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual. Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.

Para gerenciar as pilhas de locais, use os cmdlets de local do PowerShell, da seguinte maneira.

- Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.

- Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.

- Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.

- Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.

- Para criar uma nova pilha de locais, use o parâmetro StackName do `Push-Location` cmdlet. Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.

- Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro StackName do `Set-Location` cmdlet.

A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.
Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome. Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).

Você também pode consultar `Push-Location` por seu alias interno, `pushd` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

O `Push-Location` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
