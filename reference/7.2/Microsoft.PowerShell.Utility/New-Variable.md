---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: 71bb70dac3436c5293b2a34ce52e54e751786a48
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072253"
---
# New-Variable

## Sinopse
Cria uma nova variável.

## Sintaxe

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Descrição

O `New-Variable` cmdlet cria uma nova variável no Windows PowerShell. Você pode atribuir um valor à variável ao criá-la ou atribuir ou alterar o valor depois que ela é criada.

Você pode usar os parâmetros de `New-Variable` para definir as propriedades da variável, definir o escopo de uma variável e determinar se as variáveis são públicas ou privadas.

Normalmente, você cria uma nova variável digitando o nome da variável e seu valor, como `$Var = 3` , mas você pode usar o `New-Variable` cmdlet para usar seus parâmetros.

## Exemplos

### Exemplo 1: criar uma variável

```
New-Variable days
```

Este comando cria uma nova variável chamada Days. Não é necessário digitar o parâmetro **Name** .

### Exemplo 2: criar uma variável e atribuir a ela um valor

```
New-Variable -Name "zipcode" -Value 98033
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

Este exemplo mostra como usar a `ReadOnly` opção de `New-Variable` para proteger uma variável de ser substituída.

O primeiro comando cria uma nova variável chamada Max e define seu valor como 256. Ele usa o parâmetro **Option** com um valor de `ReadOnly` .

O segundo comando tenta criar uma segunda variável com o mesmo nome. Esse comando retorna um erro, porque a opção somente leitura é definida na variável.

O terceiro comando usa o parâmetro **Force** para substituir a proteção somente leitura na variável.
Nesse caso, o comando para criar uma nova variável com o mesmo nome é bem-sucedido.

### Exemplo 4: atribuir várias opções a uma variável

```powershell
New-Variable -Name 'TestVariable' -Value 'Test Value' -Option AllScope,Constant
```

Este exemplo cria uma variável e atribui as `AllScope` `Constant` Opções e, portanto, a variável estará disponível no escopo atual e quaisquer novos escopos criados e não poderão ser alterados ou excluídos.

### Exemplo 5: criar uma variável privada

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

Esse comando demonstra o comportamento de uma variável privada em um módulo. O módulo contém o `Get-Counter` cmdlet, que tem uma variável particular chamada Counter. O comando usa o parâmetro **Visibility** com um valor de Private para criar a variável.

A amostra de saída mostra o comportamento de uma variável particular. O usuário que carregou o módulo não pode exibir ou alterar o valor da variável Counter, mas a variável Counter pode ser lida e alterada pelos comandos no módulo.

### Exemplo 6: criar uma variável com um espaço

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

Esse comando demonstra que as variáveis com espaços podem ser criadas. As variáveis podem ser acessadas usando o `Get-Variable` cmdlet ou diretamente delimitando uma variável com chaves.

## Parâmetros

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

Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` . Para obter mais informações, consulte o parâmetro **Option** .

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

- `None` -Não define opções. `None` é o padrão.
- `ReadOnly` -Pode ser excluído. Não pode ser alterado, exceto pelo uso do parâmetro **Force** .
- `Private` -A variável está disponível somente no escopo atual.
- `AllScope` -A variável é copiada para todos os novos escopos criados.
- `Constant` -Não pode ser excluído ou alterado. `Constant` é válido somente quando você está criando uma variável. Você não pode alterar as opções de uma variável existente para `Constant` .

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

Para ver a propriedade Options de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -AutoSize` .

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

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

Especifica o escopo da nova variável. Os valores aceitáveis para esse parâmetro são:

- `Global` -As variáveis criadas no escopo global são acessíveis em todos os lugares em um processo do PowerShell.
- `Local` -O escopo local refere-se ao escopo atual, que pode ser qualquer escopo, dependendo do contexto.
- `Script` -As variáveis criadas no escopo do script são acessíveis somente no arquivo de script ou no módulo em que são criadas.
- `Private` -As variáveis criadas no escopo privado não podem ser acessadas fora do escopo em que existem. Você pode usar o escopo privado para criar uma versão privada de um item com o mesmo nome em outro escopo.
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual, 1 é seu pai, 2 o pai do escopo pai e assim por diante). Números negativos não podem ser usados.

`Local` é o escopo padrão quando o parâmetro de escopo não é especificado.

Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

Determina se a variável é visível fora da sessão na qual ela foi criada. Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários. Os valores aceitáveis para esse parâmetro são:

- `Public` -A variável é visível. `Public` é o padrão.
- `Private` -A variável não é visível.

Quando uma variável é privada, ela não aparece em listas de variáveis, como aquelas retornadas por `Get-Variable` ou em exibições da `Variable:` unidade. Comandos para ler ou alterar o valor de uma variável privada retornam um erro. No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.

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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

## Entradas

### System.Object

É possível canalizar um valor para `New-Variable` .

## Saídas

### Nenhum ou System. Management. Automation. PSVariable

Quando você usa o parâmetro **PassThru** , o `New-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a nova variável. Caso contrário, este cmdlet não gera nenhuma saída.

## Observações

## Links Relacionados

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
