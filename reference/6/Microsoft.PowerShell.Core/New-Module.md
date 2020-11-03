---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: d0c0388142092034b06a2185dadcaed2f19d9865
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194430"
---
# New-Module

## SINOPSE
Cria um novo módulo dinâmico que existe apenas na memória.

## SYNTAX

### ScriptBlock (padrão)

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Name

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

O `New-Module` cmdlet cria um módulo dinâmico a partir de um bloco de script. Os membros do módulo dinâmico, como funções e variáveis, ficam imediatamente disponíveis na sessão e permanecem disponíveis até que você feche a sessão.

Semelhante aos módulos estáticos, por padrão, os cmdlets e funções em um módulo dinâmico são exportadas e as variáveis e os aliases não são. No entanto, você pode usar o cmdlet Export-ModuleMember e os parâmetros de `New-Module` para substituir os padrões.

Você também pode usar o parâmetro **AsCustomObject** de `New-Module` para retornar o módulo dinâmico como um objeto personalizado. Os membros dos módulos, como funções, são implementados como métodos de script do objeto personalizado em vez de serem importadas para a sessão.

Módulos dinâmicos existem apenas na memória, não no disco. Assim como todos os módulos, os membros de módulos dinâmicos são executados em um escopo de módulo privado que é um filho do escopo global. Get-Module não obtém um módulo dinâmico, mas Get-Command pode obter os membros exportados.

Para disponibilizar um módulo dinâmico para `Get-Module` o, direcione um `New-Module` comando para Import-Module ou direcione o objeto de módulo que `New-Module` retorna para `Import-Module` . Essa ação adiciona o módulo dinâmico à `Get-Module` lista, mas não salva o módulo no disco nem o torna persistente.

## EXEMPLOS

### Exemplo 1: criar um módulo dinâmico

Este exemplo cria um novo módulo dinâmico com uma função chamada `Hello` . O comando retorna um objeto de módulo que representa o novo módulo dinâmico.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### Exemplo 2: trabalhando com módulos dinâmicos e Get-Module e Get-Command

Este exemplo demonstra que os módulos dinâmicos não são retornados pelo `Get-Module` cmdlet. Os membros que eles exportam são retornados pelo `Get-Command` cmdlet.

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### Exemplo 3: exportar uma variável para a sessão atual

Este exemplo usa o `Export-ModuleMember` cmdlet para exportar uma variável para a sessão atual.
Sem o `Export-ModuleMember` comando, apenas a função é exportada.

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

A saída mostra que a variável e a função foram exportadas para a sessão.

### Exemplo 4: tornar um módulo dinâmico disponível para Get-Module

Este exemplo demonstra que você pode disponibilizar um módulo dinâmico para `Get-Module` o ao canalizar o módulo dinâmico para o `Import-Module` .

`New-Module` Cria um objeto de módulo que é canalizado para o `Import-Module` cmdlet. O parâmetro **Name** de `New-Module` atribui um nome amigável ao módulo. Como `Import-Module` o não retorna nenhum objeto por padrão, não há nenhuma saída desse comando. `Get-Module` Se o **GreetingModule** foi importado para a sessão atual.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

O `Get-Command` cmdlet mostra a `Hello` função que o módulo dinâmico exporta.

### Exemplo 5: gerar um objeto personalizado que tem funções exportadas

Este exemplo mostra como usar o parâmetro **AsCustomObject** de `New-Module` para gerar um objeto personalizado que tem métodos de script que representam as funções exportadas.

O `New-Module` cmdlet cria um módulo dinâmico com duas funções `Hello` e `Goodbye` . O parâmetro **AsCustomObject** cria um objeto personalizado em vez do objeto **PSModuleInfo** que `New-Module` gera por padrão. Esse objeto personalizado é salvo na `$m` variável.
A `$m` variável parece não ter nenhum valor atribuído.

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

A tubulação `$m` ao `Get-Member` cmdlet exibe as propriedades e os métodos do objeto personalizado. A saída mostra que o objeto tem métodos de script que representam `Hello` as `Goodbye` funções e.
Por fim, chamamos esses métodos de script e exibimos os resultados.

### Exemplo 6: obter os resultados do bloco de script

Este exemplo usa o parâmetro **ReturnResult** para solicitar os resultados da execução do bloco de script em vez de solicitar um objeto de módulo. O bloco de script no novo módulo define a `SayHello` função e, em seguida, chama a função.

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## PARAMETERS

### -ArgumentList

Especifica uma matriz de argumentos que são valores de parâmetro que são passados para o bloco de script. Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsCustomObject

Indica que esse cmdlet retorna um objeto personalizado que representa o módulo dinâmico. Os membros do módulo são implementados como métodos de script do objeto personalizado, mas eles não são importados para a sessão. Você pode salvar o objeto personalizado em uma variável e usar a notação de ponto para invocar os membros.

Se o módulo tiver vários membros com o mesmo nome, como uma função e uma variável que são nomeados como, somente um membro com cada nome poderá ser acessado do objeto personalizado.

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

### -Cmdlet

Especifica uma matriz de cmdlets que esse cmdlet exporta do módulo para a sessão atual.
Digite uma lista separada por vírgulas dos cmdlets. Caracteres curinga são permitidos. Por padrão, todos os cmdlets no módulo são exportados.

Você não pode definir os cmdlets em um bloco de script, mas um módulo dinâmico pode incluir cmdlets se importar os cmdlets de um módulo binário.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Função

Especifica uma matriz de funções que esse cmdlet exporta do módulo para a sessão atual.
Digite uma lista separada por vírgulas de funções. Caracteres curinga são permitidos. Por padrão, todas as funções definidas em um módulo são exportadas.

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

Especifica um nome para o novo módulo. Também é possível direcionar um nome de computador para New-Module.

O valor padrão é um nome gerado automaticamente que começa com `__DynamicModule_` e é seguido por um GUID que especifica o caminho do módulo dinâmico.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReturnResult

Indica que esse cmdlet executa o bloco de script e retorna os resultados de bloco de script em vez de retornar um objeto de módulo.

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

### -ScriptBlock

Especifica o conteúdo do módulo dinâmico. Coloque o conteúdo entre chaves ( `{}` ) para criar um bloco de script. Este parâmetro é necessário.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar um nome de módulo para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSModuleInfo, System. Management. Automation. PSCustomObject ou None

Por padrão, esse cmdlet gera um objeto **PSModuleInfo** . Se você usar o parâmetro **AsCustomObject** , ele gerará um objeto **PSCustomObject** . Se você usar o parâmetro **ReturnResult** , ele retornará o resultado da avaliação do bloco de script no módulo dinâmico.

## OBSERVAÇÕES

Você também pode se referir `New-Module` por seu alias, `nmo` . Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).

## LINKS RELACIONADOS

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)
