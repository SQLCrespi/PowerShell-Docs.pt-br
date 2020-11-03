---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: c2a9af56c395409fd08c3126d36126a171ff7ec7
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "93195123"
---
# Pop-Location

## SINOPSE
Altera o local atual para o local mais recentemente inserido na pilha.

## SYNTAX

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Pop-Location` cmdlet altera o local atual para o local mais recentemente enviado para a pilha usando o `Push-Location` cmdlet. Você pode mostrar um local da pilha padrão ou de uma pilha que você cria usando um `Push-Location` comando.

## EXEMPLOS

### Exemplo 1: alterar para o local mais recente

```
PS C:\> Pop-Location
```

Este comando altera o local para o local mais recentemente adicionado à pilha atual.

### Exemplo 2: alterar para o local mais recente em uma pilha nomeada

```
PS C:\> Pop-Location -StackName "Stack2"
```

Este comando altera o local para o local mais recentemente adicionado à pilha de local Stack2.

Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

### Exemplo 3: mover entre locais para provedores diferentes

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

Esses comandos usam os `Push-Location` `Pop-Location` cmdlets e para se mover entre os locais com suporte de diferentes provedores do PowerShell. Os comandos usam o `pushd` alias para `Push-Location` e o `popd` alias para `Pop-Location` .

O primeiro comando envia o local do sistema de arquivos atual para a pilha e move para a unidade HKLM suportada pelo provedor de registro do PowerShell.

O segundo comando envia o local do registro para a pilha e move para um local com suporte do provedor de certificados do PowerShell.

Os dois últimos comandos removem esses locais da pilha. O primeiro `popd` comando retorna à unidade do registro e o segundo comando retorna à unidade do sistema de arquivos.

## PARAMETERS

### -PassThru

Passa um objeto que representa o local para o pipeline. Por padrão, este cmdlet não gera saída.

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

### -StackName

Especifica a pilha do local de onde o local é exibido. Digite um nome de pilha de local.

Sem esse parâmetro, `Pop-Location` o exibe um local da pilha de locais atual. Por padrão, a pilha de local atual é a pilha de locais padrão sem nome que o PowerShell cria. Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet. Para obter mais informações sobre as pilhas de local, consulte as [observações](#notes).

`Pop-Location` Não é possível retirar um local da pilha padrão sem nome, a menos que seja a pilha de local atual.

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

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PathInfo

Esse cmdlet gera um objeto **System. Management. Automation. PathInfo** que representa o local, se você especificar o parâmetro **PassThru** . Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

O PowerShell dá suporte a vários Runspaces por processo. Cada runspace tem seu próprio _diretório atual_ .
Isso não é o mesmo que `[System.Environment]::CurrentDirectory` . Esse comportamento pode ser um problema ao chamar APIs .NET ou executar aplicativos nativos sem fornecer caminhos de diretório explícitos.

Mesmo que os cmdlets de local tenham definido o diretório atual de todo o processo, você não pode depender dele porque outro runspace pode alterá-lo a qualquer momento. Você deve usar os cmdlets de local para executar operações baseadas em caminho usando o diretório de trabalho atual específico para o runspace atual.

Uma pilha é uma lista de último a entrar, primeiro a sair na qual apenas o item adicionado mais recentemente pode ser acessado. Você adiciona itens a uma pilha na ordem em que as usará e as recupera para uso na ordem inversa. O PowerShell permite que você armazene locais de provedores em pilhas de locais.

O PowerShell cria uma pilha de local padrão sem nome e você pode criar várias pilhas de locais nomeadas. Se você não especificar um nome de pilha, o PowerShell usará a pilha de local atual. Por padrão, o local padrão sem nome é a pilha de local atual, mas você pode usar o `Set-Location` cmdlet para alterar a pilha de locais atual.

Para gerenciar as pilhas de locais, use os `*-Location` cmdlets do PowerShell, da seguinte maneira:

- Para adicionar um local a uma pilha de local, use o `Push-Location` cmdlet.

- Para obter um local de uma pilha de local, use o `Pop-Location` cmdlet.

- Para exibir os locais na pilha de locais atual, use o parâmetro **Stack** do `Get-Location` cmdlet.

- Para exibir os locais em uma pilha de local nomeada, use o parâmetro **StackName** do `Get-Location` cmdlet.

- Para criar uma nova pilha de locais, use o parâmetro **StackName** do `Push-Location` cmdlet. Se você especificar uma pilha que não existe, `Push-Location` o criará a pilha.

- Para tornar uma pilha de localização a pilha de locais atual, use o parâmetro **StackName** do `Set-Location` cmdlet.

A pilha de locais padrão sem nome é totalmente acessível somente quando é a pilha de locais atual.
Se você fizer uma pilha de local nomeada na pilha de locais atual, não poderá mais usar `Push-Location` os `Pop-Location` cmdlets ou para adicionar ou obter itens da pilha padrão ou usar o `Get-Location` cmdlet para exibir os locais na pilha sem nome. Para tornar a pilha sem nome a pilha atual, use o parâmetro **StackName** do `Set-Location` cmdlet com um valor de `$Null` ou uma cadeia de caracteres vazia ( `""` ).

Você também pode consultar `Pop-Location` por seu alias interno, `popd` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

`Pop-Location` o é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Get-Location](Get-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
