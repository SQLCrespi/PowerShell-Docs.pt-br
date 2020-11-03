---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: e1432a8ae6826e7f2c47f35c9cc01df20edde85c
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "93195224"
---
# Set-Location

## SINOPSE
Define o local de trabalho atual em um local especificado.

## SYNTAX

### Caminho (padrão)

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### LiteralPath

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### Pilha

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Location` cmdlet define o local de trabalho para um local especificado. Esse local pode ser um diretório, um subdiretório, um local do registro ou qualquer caminho do provedor.

O PowerShell 6,2 adicionou suporte para `-` e `+` como valores para o parâmetro **Path** . O PowerShell mantém um histórico dos últimos 20 locais que podem ser acessados com o `-` e o `+` . Essa lista é independente da pilha de local que é acessada usando o parâmetro **StackName** .

## EXEMPLOS

### Exemplo 1: definir o local atual

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

Esse comando define o local atual como a raiz da `HKLM:` unidade.

### Exemplo 2: definir o local atual e exibir esse local

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

Esse comando define o local atual como a raiz da `Env:` unidade. Ele usa o parâmetro **PassThru** para direcionar o PowerShell para retornar um objeto **PathInfo** que representa o `Env:\` local.

### Exemplo 3: definir local para o local atual na unidade C:

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

O primeiro comando define o local para a raiz da `HKLM:` unidade no provedor de registro.
O segundo comando define o local para o local atual da `C:` unidade no provedor FileSystem.
Quando o nome da unidade é especificado no formulário `<DriveName>:` (sem barra invertida), o cmdlet define o local para o local atual no PSDrive.
Para obter o local atual no comando PSDrive use `Get-Location -PSDrive <DriveName>` .

### Exemplo 4: definir o local atual para uma pilha nomeada

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

O primeiro comando adiciona o local atual à pilha de caminhos.
O segundo comando torna o local dos caminhos empilhar a pilha do local atual.
O terceiro comando exibe os locais na pilha de locais atual.

Os `*-Location` cmdlets usam a pilha de local atual, a menos que uma pilha de local diferente seja especificada no comando. Para obter informações sobre as pilhas de locais, consulte as [observações](#notes).

### Exemplo 5: navegar no histórico de local usando `+` ou `-`

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

Usar o alias `cd -` ou `cd +` é uma maneira fácil de navegar pelo seu histórico de local enquanto estiver em seu terminal. Para obter mais informações sobre como navegar com `-` / `+` o, consulte o parâmetro **Path** .

## PARAMETERS

### -LiteralPath

Especifica um caminho do local. O valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto **PathInfo** que representa o local. Por padrão, este cmdlet não gera saída.

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

Especifique o caminho de um novo local de trabalho. Se nenhum caminho for fornecido, `Set-Location` o padrão será o diretório base do usuário atual. Quando caracteres curinga são usados, o cmdlet escolhe o primeiro caminho que corresponde ao padrão de curinga.

O PowerShell mantém um histórico dos últimos 20 locais que você definiu. Se o valor do parâmetro **path** for o `-` caractere, o novo local de trabalho será o local de trabalho anterior no histórico (se existir). Da mesma forma, se o valor for o `+` caractere, o novo local de trabalho será o próximo local de trabalho no histórico (se existir). Isso é semelhante a usar `Pop-Location` e, `Push-Location` exceto que o histórico é uma lista, não uma pilha, e é rastreado implicitamente, não controlado manualmente. Atualmente, não há como exibir a lista de histórico.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StackName

Especifica o nome da pilha de local existente que esse cmdlet cria a pilha de local atual. Digite um nome de pilha de local. Para indicar a pilha de local padrão sem nome, digite `$null` ou uma cadeia de caracteres vazia ( `""` ).

Os `*-Location` cmdlets atuam na pilha atual, a menos que você use o parâmetro **StackName** para especificar uma pilha diferente. Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

```yaml
Type: System.String
Parameter Sets: Stack
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

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PathInfo, System. Management. Automation. PathInfoStack

Esse cmdlet não gera nenhuma saída, a menos que você especifique o parâmetro **PassThru** . O uso de **PassThru** com **Path** ou **LiteralPath** gera um objeto **PathInfo** que representa o novo local. O uso de **PassThru** com **StackName** gera um objeto **PathInfoStack** que representa o novo contexto da pilha.

## OBSERVAÇÕES

O PowerShell dá suporte a vários Runspaces por processo. Cada runspace tem seu próprio _diretório atual_ .
Isso não é o mesmo que `[System.Environment]::CurrentDirectory` . Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.

Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento. Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.

O `Set-Location` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).

Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado. Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa. O PowerShell permite que você armazene locais de provedores em pilhas de locais. O PowerShell cria uma pilha de local padrão sem nome. Você pode criar várias pilhas de locais nomeadas. Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual. Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.

Para gerenciar as pilhas de locais, use os `*-Location` cmdlets, da seguinte maneira:

- Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.

- Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.

- Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet. Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** de `Get-Location` .

- Para criar uma nova pilha de locais, use o parâmetro **StackName** de `Push-Location` . Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.

- Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** de `Set-Location` .

A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.
Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome. Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).

## LINKS RELACIONADOS

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)
