---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: faf8bc399185da402bebb678b02927e0e5628662
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194333"
---
# New-Variable

## SINOPSE
Cria uma nova variável.

## SYNTAX

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **New-Variable** cria uma nova variável no PowerShell.
Você pode atribuir um valor à variável ao criá-la ou atribuir ou alterar o valor depois que ela é criada.

Você pode usar os parâmetros de **New-Variable** para definir as propriedades da variável, definir o escopo de uma variável e determinar se as variáveis são públicas ou privadas.

Normalmente, você cria uma nova variável digitando o nome da variável e seu valor, como `$Var = 3` , mas você pode usar o cmdlet **New-Variable** para usar seus parâmetros.

## EXEMPLOS

### Exemplo 1: criar uma variável

```
PS C:\> New-Variable days
```

Este comando cria uma nova variável chamada Days.
Não é necessário digitar o parâmetro *Name* .

### Exemplo 2: criar uma variável e atribuir a ela um valor

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

Esse comando cria uma variável chamada ZipCode e atribui a ela o valor 98033.

### Exemplo 3: criar uma variável com a opção ReadOnly

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

Este exemplo mostra como usar a opção ReadOnly de **New-Variable** para proteger uma variável de ser substituída.

O primeiro comando cria uma nova variável chamada Max e define seu valor como 256.
Ele usa o parâmetro *Option* com um valor de ReadOnly.

O segundo comando tenta criar uma segunda variável com o mesmo nome.
Esse comando retorna um erro, porque a opção somente leitura é definida na variável.

O terceiro comando usa o parâmetro *Force* para substituir a proteção somente leitura na variável.
Nesse caso, o comando para criar uma nova variável com o mesmo nome é bem-sucedido.

### Exemplo 4: criar uma variável privada

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

Esse comando demonstra o comportamento de uma variável privada em um módulo.
O módulo contém o cmdlet Get-Counter, que tem uma variável particular chamada Counter.
O comando usa o parâmetro *Visibility* com um valor de Private para criar a variável.

A amostra de saída mostra o comportamento de uma variável particular.
O usuário que carregou o módulo não pode exibir ou alterar o valor da variável Counter, mas a variável Counter pode ser lida e alterada pelos comandos no módulo.

### Exemplo 5: criar uma variável com um espaço

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

Esse comando demonstra que as variáveis com espaços podem ser criadas.
As variáveis podem ser acessadas usando o cmdlet **Get-Variable** ou diretamente delimitando uma variável com chaves.

## PARAMETERS

### -Description
Especifica uma descrição da variável.

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

### -Force
Indica que o cmdlet cria uma variável com o mesmo nome de uma variável somente leitura existente.

Por padrão, você pode substituir uma variável, a menos que ela tenha um valor de opção de ReadOnly ou Constant.
Para obter mais informações, consulte o parâmetro *Option* .

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

### -Name
Especifica um nome para a nova variável.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opção
Especifica o valor da propriedade **Options** da variável. Os valores aceitáveis para esse parâmetro são:

- nenhuma.
Não define nenhuma opção.
(Nenhum é o padrão.)
- Leitura.
Pode ser excluído.
Não pode ser alterado, exceto pelo uso do parâmetro *Force* .
- Privado.
A variável está disponível somente no escopo atual.
- AllScope.
A variável é copiada para quaisquer novos escopos criados.
- Constante.
Não pode ser excluído ou alterado.
A constante é válida somente quando você está criando uma variável.
Você não pode alterar as opções de uma variável existente para constante.

Para ver a propriedade **Options** de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -autosize` .

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
Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

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

### -Escopo
Especifica o escopo da nova variável.
Os valores aceitáveis para esse parâmetro são:

- Geral.
As variáveis criadas no escopo global são acessíveis em todos os lugares em um processo do PowerShell.
- Local.
O escopo local refere-se ao escopo atual, que pode ser qualquer escopo, dependendo do contexto.
- Script.
As variáveis criadas no escopo do script são acessíveis somente no arquivo de script ou no módulo em que são criadas.
- Privado.
As variáveis criadas no escopo privado não podem ser acessadas fora do escopo em que existem.
Você pode usar o escopo privado para criar uma versão privada de um item com o mesmo nome em outro escopo.
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual, 1 é seu pai, 2 o pai do escopo pai e assim por diante).
Números negativos não podem ser usados.

Local é o escopo padrão quando o parâmetro de escopo não é especificado.

Para obter mais informações, consulte about_Scopes.

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

### -Value
Especifica o valor inicial da variável.

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
Os valores aceitáveis para esse parâmetro são:

- Público.
A variável está visível.
(Público é o padrão.)
- Privado.
A variável não é visível.

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
Default value: None
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
É possível canalizar um valor para **nova variável** .

## SAÍDAS

### Nenhum ou System. Management. Automation. PSVariable
Quando você usa o parâmetro *PassThru* , **New-Variable** gera um objeto **System. Management. Automation. PSVariable** que representa a nova variável.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
