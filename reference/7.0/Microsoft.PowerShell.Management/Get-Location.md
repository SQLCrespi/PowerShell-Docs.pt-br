---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 235c775e2da4188213f4eb35612c469947b5e2fc
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "93195220"
---
# Get-Location

## SINOPSE
Obtém informações sobre o local de trabalho atual ou uma pilha de locais.

## SYNTAX

### Local (padrão)

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [<CommonParameters>]
```

### Pilha

```
Get-Location [-Stack] [-StackName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Location` cmdlet obtém um objeto que representa o diretório atual, assim como o comando de pasta de trabalho de impressão (pwd).

Quando você se move entre as unidades do PowerShell, o PowerShell retém seu local em cada unidade. Você pode usar este cmdlet para localizar seu local em cada unidade.

Você pode usar este cmdlet para obter o diretório atual em tempo de execução e usá-lo em funções e scripts, como em uma função que exibe o diretório atual no prompt do PowerShell.

Você também pode usar este cmdlet para exibir os locais em uma pilha de local. Para obter mais informações, consulte as observações e as descrições dos parâmetros **Stack** e **StackName** .

## EXEMPLOS

### Exemplo 1: exibir o local da unidade atual

Esse comando exibe o local na unidade atual do PowerShell.

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

Por exemplo, se você estiver no `Windows` diretório da `C:` unidade, ele exibirá o caminho para esse diretório.

### Exemplo 2: exibir seu local atual para unidades diferentes

Este exemplo demonstra o uso do `Get-Location` para exibir seu local atual em diferentes unidades do PowerShell. `Set-Location` é usado para alterar o local para vários caminhos diferentes em PSDrives diferentes.

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### Exemplo 3: obter locais usando pilhas

Este exemplo mostra como usar os parâmetros **Stack** e **StackName** de `Get-Location` para listar os locais na pilha de local atual e as pilhas de local alternativas.

O `Push-Location` cmdlet é usado para alterar em três locais diferentes. O terceiro envio por push usa um nome de pilha diferente. O parâmetro **Stack** de `Get-Location` exibe o conteúdo da pilha padrão. O parâmetro **StackName** de `Get-Location` exibe o conteúdo da pilha chamada `Stack2` .

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### Exemplo 4: personalizar o prompt do PowerShell

Este exemplo mostra como personalizar o prompt do PowerShell.

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

A função que define o prompt inclui um `Get-Location` comando, que é executado sempre que o prompt é exibido no console do.

O formato do prompt padrão do PowerShell é definido por uma função especial chamada `prompt` . Você pode alterar o prompt no console criando uma nova função chamada `prompt` .

Para ver a função de prompt atual, digite o seguinte comando: `Get-Content Function:\prompt`

## PARAMETERS

### -PSDrive

Obtém o local atual na unidade do PowerShell especificada.

Por exemplo, se você estiver na `Cert:` unidade, poderá usar esse parâmetro para localizar o local atual na `C:` unidade.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Obtém o local atual na unidade com suporte pelo provedor do PowerShell especificado.
Se o provedor especificado oferecer suporte a mais de uma unidade, esse cmdlet retornará o local na unidade acessada mais recentemente.

Por exemplo, se você estiver na `C:` unidade, poderá usar esse parâmetro para localizar o local atual nas unidades do provedor de **registro** do PowerShell.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pilha

Indica que esse cmdlet exibe os locais adicionados à pilha do local atual. Você pode adicionar locais a pilhas usando o `Push-Location` cmdlet.

Para exibir os locais em uma pilha de local diferente, use o parâmetro **StackName** . Para obter informações sobre as pilhas de locais, consulte as [observações](#notes).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StackName

Especifica, como uma matriz de cadeia de caracteres, as pilhas de locais nomeadas. Insira um ou mais nomes de pilha de locais.

Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** . Para tornar uma pilha de localização a pilha de locais atual, use o `Set-Location` cmdlet.

Esse cmdlet não pode exibir os locais na pilha padrão sem nome, a menos que seja a pilha atual.

```yaml
Type: System.String[]
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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. PathInfo ou System. Management. Automation. PathInfoStack

Se você usar os parâmetros **Stack** ou **StackName** , esse cmdlet retornará um objeto **PathInfoStack** . Caso contrário, ele retorna um objeto **PathInfo** .

## OBSERVAÇÕES

O PowerShell dá suporte a vários Runspaces por processo. Cada runspace tem seu próprio _diretório atual_ .
Isso não é o mesmo que `[System.Environment]::CurrentDirectory` . Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.
O `Get-Location` cmdlet retorna o diretório atual do runspace do PowerShell atual.

Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

As maneiras como os parâmetros **PSProvider** , **PSDrive** , **Stack** e **StackName** interagem dependem do provedor. Algumas combinações resultarão em erros, como especificar uma unidade e um provedor que não expõe essa unidade. Se nenhum parâmetro for especificado, esse cmdlet retornará o objeto **PathInfo** para o provedor que contém o local de trabalho atual.

Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente está acessível. Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa. O PowerShell permite que você armazene locais de provedores em pilhas de locais. O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas. Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual. Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.

Para gerenciar as pilhas de locais, use os `*-Location` cmdlets do PowerShell, da seguinte maneira.

- Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.

- Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.

- Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet. Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.

- Para criar uma nova pilha de locais, use o parâmetro **StackName** do `Push-Location` cmdlet.
  Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.

- Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.

A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.
Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar este cmdlet para exibir os locais na pilha sem nome. Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$null` ou uma cadeia de caracteres vazia ( `""` ).

## LINKS RELACIONADOS

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)
