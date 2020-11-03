---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: ba17b526de91e470149e90913814ecfac0f75392
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193261"
---
# Set-Variable

## SINOPSE
Define o valor de uma variável.
Cria a variável se uma com o nome solicitado não existir.

## SYNTAX

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Set-Variable** atribui um valor a uma variável especificada ou altera o valor atual.
Se a variável não existir, o cmdlet a criará.

## EXEMPLOS

### Exemplo 1: definir uma variável e obter seu valor

```
PS C:\> Set-Variable -Name "desc" -Value "A description"
PS C:\> Get-Variable -Name "desc"
```

Esses comandos definem o valor da variável DESC como uma descrição e, em seguida, obtém o valor da variável.

### Exemplo 2: definir uma variável global, somente leitura

```
PS C:\> Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru | Format-List -Property *
```

Este comando cria uma variável global, somente leitura, que contém todos os processos do sistema e, em seguida, exibe todas as propriedades da variável.

O comando usa o cmdlet **Set-Variable** para criar a variável.
Ele usa o parâmetro *PassThru* para criar um objeto que representa a nova variável e usa o operador de pipeline (|) para passar o objeto para o cmdlet Format-List.
Ele usa o parâmetro de *Propriedade* de Format-List com um valor de todos (*) para exibir todas as propriedades da variável recém-criada.

O valor "(Get-Process)" é colocado entre parênteses para garantir que seja executado antes de ser armazenado na variável.
Caso contrário, a variável contém as palavras "Get-Process".

### Exemplo 3: entender as variáveis públicas versus privadas

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26 

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

 PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

Este comando mostra como alterar a visibilidade de uma variável para particular.
Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.

A saída de exemplo mostra a diferença de comportamento de variáveis públicas e privadas.

## PARAMETERS

### -Description

Especifica a descrição da variável.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Especifica uma matriz de itens que esse cmdlet exclui da operação.
O valor deste parâmetro qualifica o parâmetro *Path* .
Insira um elemento ou padrão de caminho, como `*.txt` .
Caracteres curinga são permitidos.

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

### -Force

Permite que você crie uma variável com o mesmo nome de uma variável somente leitura existente, ou altere o valor de uma variável somente leitura.

Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de ReadOnly ou Constant.
Para obter mais informações, consulte o parâmetro *Option* .

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

### -Incluir

Especifica uma matriz de itens que esse cmdlet inclui na operação.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um nome ou padrão de nome, como `c*` .
Caracteres curinga são permitidos.

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

Especifica o nome da variável.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opção

Especifica o valor da propriedade **Options** da variável.

Os valores válidos são:

- Nenhum: não define opções. ("None" é o padrão.)
- ReadOnly: pode ser excluído. Não pode ser alterado, exceto pelo uso do parâmetro Force.
- Constante: não pode ser excluída ou alterada. "Constant" é válido somente quando você estiver criando uma variável. Você não pode alterar as opções de uma variável existente para "Constant".
- Particular: a variável está disponível somente no escopo atual.
- Escopo: a variável é copiada para todos os novos escopos criados.

Para ver a propriedade **Options** de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -Autosize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Retorna um objeto que representa a nova variável.
Por padrão, este cmdlet não gera saída.

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

### -Escopo

Especifica o escopo da variável. Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Privados
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).

Local é o padrão.

Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica o valor da variável.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Visibilidade

Determina se a variável é visível fora da sessão na qual ela foi criada.
Esse parâmetro é voltado para uso em scripts e comandos que serão entregues a outros usuários.

Os valores válidos são:

- Público: a variável está visível. ("Public" é o padrão.)
- Particular: a variável não é visível.

Quando uma variável é privada, ele não aparece nas listas de variáveis como aquelas retornadas por Get-Variable ou em exibições da unidade Variable:.
Comandos para ler ou alterar o valor de uma variável privada retornam um erro.
No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Object

É possível canalizar um objeto que representa o valor da variável para **Set-Variable** .

## SAÍDAS

### Nenhum ou System. Management. Automation. PSVariable

Quando você usa o parâmetro *PassThru* , o **Set-Variable** gera um objeto **System. Management. Automation. PSVariable** que representa a variável nova ou alterada.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

