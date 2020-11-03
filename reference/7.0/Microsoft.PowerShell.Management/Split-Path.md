---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: b0366e9d84826d84dcdc341a9e83e4ed7dc45059
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192969"
---
# Split-Path

## SINOPSE
Retorna a parte especificada de um caminho.

## SYNTAX

### Parentset (padrão)

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Folha de um

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### LeafBaseSet

```
Split-Path [-Path] <String[]> [-LeafBase] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Extensão do

```
Split-Path [-Path] <String[]> [-Extension] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Qualificador

```
Split-Path [-Path] <String[]> [[-Qualifier]] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Noqualifierset

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Isabsolutaset

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### LiteralPathSet

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Split-Path** retorna apenas a parte especificada de um caminho, como a pasta pai, uma subpasta ou um nome de arquivo.
Também pode obter itens que são referenciados pelo caminho de divisão e informar se o caminho é relativo ou absoluto.

Você pode usar esse cmdlet para obter ou enviar apenas uma parte selecionada de um caminho.

## EXEMPLOS

### Exemplo 1: obter o qualificador de um caminho

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

Esse comando retorna somente o qualificador do caminho.
O qualificador é a unidade.

### Exemplo 2: exibir nomes de arquivo

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

Esse comando exibe os arquivos que são referenciados pelo caminho de divisão.
Como esse caminho é dividido para o último item, também conhecido como folha, o comando exibe somente os nomes de arquivo.

O parâmetro *resolve* informa ao **Split-Path** para exibir os itens que o caminho de divisão referencia, em vez de exibir o caminho de divisão.

Assim como todos os comandos **de divisão-caminho** , esse comando retorna cadeias de caracteres.
Ele não retorna objetos **FileInfo** que representam os arquivos.

### Exemplo 3: obter o contêiner pai

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

Esse comando retorna apenas os contêineres pai do caminho.
Como não inclui nenhum parâmetro para especificar a divisão, **Split-Path** usa o padrão de localização de divisão, que é o *pai* .

### Exemplo 4: determina se um caminho é absoluto

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

Esse comando determina se o caminho é relativo ou absoluto.
Nesse caso, como o caminho é relativo à pasta atual, que é representada por um ponto (.), ela retorna $False.

### Exemplo 5: alterar o local para um caminho especificado

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

Esse comando altera o local para a pasta que contém o perfil do PowerShell.

O comando entre parênteses usa **Split-Path** para retornar apenas o pai do caminho armazenado na variável de $Profile interna.
O parâmetro *pai* é o parâmetro de local de divisão padrão.
Portanto, você pode omiti-lo do comando.
Os parênteses direcionam o PowerShell para executar o comando primeiro.
Essa é uma maneira útil de mover para uma pasta que tem um nome de caminho longo.

### Exemplo 6: dividir um caminho usando o pipeline

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

Este comando usa um operador de pipeline (|) para enviar um caminho para o **caminho de divisão** .
O caminho é colocado entre aspas para indicar que se trata de um único token.

## PARAMETERS

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.
> Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Extensão

Indica que esse cmdlet retorna apenas a extensão da folha.
Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna apenas `.log` .

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Isabsoluta

Indica que esse cmdlet retornará $True se o caminho for absoluto e $False se for relativo.
Um caminho absoluto tem um comprimento maior que zero e não usa um ponto (.) para indicar o caminho atual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Folha

Indica que esse cmdlet retorna apenas o último item ou contêiner no caminho.
Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna somente Pass1. log.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeafBase

Indica que esse cmdlet retorna apenas o nome base da folha.
Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna apenas `Pass1` .

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Especifica os caminhos que serão divididos.
Ao contrário de *Path* , o valor de *LiteralPath* é usado exatamente como digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoQualifier

Indica que esse cmdlet retorna o caminho sem o qualificador.
Para os provedores de sistema de arquivos ou registro, o qualificador é a unidade do caminho de provedor, como C: ou HKCU:.
Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna apenas \Test\Logs\Pass1.log.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pai

Indica que esse cmdlet retorna somente os contêineres pai do item ou do contêiner especificado pelo caminho.
Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna C:\Test\Logs.
O parâmetro *pai* é o parâmetro de local de divisão padrão.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica os caminhos que serão divididos.
Caracteres curinga são permitidos.
Se o caminho incluir espaços, coloque-os entre aspas.
Você também pode canalizar um caminho para esse cmdlet.

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Qualificador

Indica que esse cmdlet retorna apenas o qualificador do caminho especificado.
Para os provedores de sistema de arquivos ou registro, o qualificador é a unidade do caminho de provedor, como C: ou HKCU:.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Resolver

Indica que esse cmdlet exibe os itens que são referenciados pelo caminho dividido resultante em vez de exibir os elementos de caminho.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.

## SAÍDAS

### System. String, System. Boolean

**Split-Path** retorna cadeias de caracteres de texto.
Quando você especifica o parâmetro *resolve* , o **Split-Path** retorna uma cadeia de caracteres que descreve o local dos itens; Ele não retorna objetos que representam os itens, como um objeto **FileInfo** ou **RegistryKey** .

Quando você especifica o parâmetro *IsAbsolute* , o **Split-Path** retorna um valor **booliano** .

## OBSERVAÇÕES

* Os parâmetros de localização de divisão ( *qualificador* , *pai* , *extensão* , *folha* , *LeafBase* e *noqualificador* ) são exclusivos. Você pode usar somente uma opção em cada comando.

  Os cmdlets que contêm o substantivo de **caminho** (os cmdlets de **caminho** ) funcionam com nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar.
Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.
Use-os na forma como você usaria **dirname** , **Normpath** , **realpath** , **Join** ou outros manipuladores de caminho.

  Você pode usar os cmdlets de **caminho** junto com vários provedores.
Isso inclui o sistema de arquivos, o registro e os provedores de certificado.

  A **divisão de caminho** é projetada para trabalhar com os dados expostos por qualquer provedor.
Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .
Para obter mais informações, consulte about_Providers.

## LINKS RELACIONADOS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Test-Path](Test-Path.md)
