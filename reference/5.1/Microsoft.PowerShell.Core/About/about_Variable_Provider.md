---
description: Variável
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Variable
ms.openlocfilehash: ff3d457e8d057329544cf1265720fc041a804973
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196140"
---
# <a name="variable-provider"></a>Provedor de variáveis

## <a name="provider-name"></a>Nome do provedor

Variável

## <a name="drives"></a>Unidades

`Variable:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso às variáveis do PowerShell e aos seus valores.

## <a name="detailed-description"></a>Descrição detalhada

O provedor de **variáveis** do PowerShell permite que você obtenha, adicione, altere, apague e exclua variáveis do PowerShell no console atual.

O provedor de **variáveis** do PowerShell dá suporte às variáveis que o PowerShell cria, incluindo as variáveis automáticas, as variáveis de preferência e as variáveis que você cria.

A unidade **variável** é um namespace simples que contém apenas os objetos de variável. As variáveis não possuem itens filho.

O provedor de **variáveis** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

O PowerShell também inclui um conjunto de cmdlets projetados especialmente para exibir e alterar variáveis. Quando você usa cmdlets **variáveis** , não é necessário especificar a `Variable:` unidade no nome. Este artigo não aborda o trabalho com cmdlets **variáveis** .

- [Get-Variable](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [New-Variable](xref:Microsoft.PowerShell.Utility.New-Variable)
- [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> Você também pode usar o analisador de expressão do PowerShell para criar, exibir e alterar os valores de variáveis sem usar os cmdlets. Ao trabalhar com variáveis diretamente, use um sinal de cifrão ( `$` ) para identificar o nome como uma variável e o operador de atribuição ( `=` ) para estabelecer e alterar seu valor. Por exemplo, `$p = Get-Process` cria a `p` variável e armazena os resultados de um `Get-Process` comando nela.

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

As variáveis podem ser um dos vários tipos diferentes. A maioria das variáveis será instâncias da `PSVariable` classe. Outras variáveis e seus tipos são listados abaixo.

- A `?` variável é uma instância da `QuestionMarkVariable` classe.
- A `null` variável é uma instância da `NullVariable` classe.
- As variáveis de contagem máxima são instâncias da `SessionStateCapacityVariable` classe.
- `LocalVariable` as instâncias contêm informações sobre a execução atual, como:
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a>Navegando pelas unidades variáveis

O provedor **variável** expõe seu armazenamento de dados na `Variable:` unidade. Para trabalhar com variáveis, você pode alterar seu local para a `Variable:` unidade ( `Set-Location Variable:` ) ou pode trabalhar em qualquer outra unidade do PowerShell. Para fazer referência a uma variável de outro local, use o nome da unidade ( `Variable:` ) no caminho.

```powershell
Set-Location Variable:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor de **variáveis** de qualquer outra unidade do PowerShell. Para fazer referência a uma variável de outro local, use o nome da unidade `Variable:` no caminho.

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-value-of-variables"></a>Exibindo o valor de variáveis

### <a name="get-all-variables-in-the-current-session"></a>Obter todas as variáveis na sessão atual

Esse comando obtém a lista de todas as variáveis e seus valores na sessão atual. Você pode usar esse comando em qualquer unidade do PowerShell.

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a>Obter uma variável usando seu caminho de provedor

Esse comando recupera um valor de variáveis usando seu caminho de provedor prefixado pelo cifrão ( `$` ). Isso tem o mesmo efeito que a prefixação do nome das variáveis com o cifrão ( `$` ).

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a>Obter variáveis usando curingas

Esse comando obtém as variáveis com nomes que começam com "max". Você pode usar esse comando em qualquer unidade do PowerShell.

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a>Obter o valor do? variável

Esse comando usa o `-LiteralPath` parâmetro de [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) para obter o valor da `?` variável de dentro da `Variable:` unidade. O `?` é um caractere curinga em caminhos, mas `Get-ChildItem` não tenta resolver nenhum caractere curinga nos valores do `-LiteralPath` parâmetro.

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a>Obter variáveis ReadOnly e constantes

Esse comando obtém as variáveis que têm os valores de `ReadOnly` ou `Constant` para suas propriedades de **Opções** .

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a>Criando variáveis

### <a name="create-a-new-variable"></a>Criar uma nova variável

Esse comando cria a `services` variável e armazena os resultados de um `Get-Service` comando nela. Como o local atual está na `Variable:` unidade, o valor do `-Path` parâmetro é um ponto ( `.` ), que representa o local atual.

Os parênteses em volta do `Get-Service` comando garantem que o comando seja executado antes de a variável ser criada. Sem os parênteses, o valor da nova variável é uma cadeia de caracteres "Get-Service".

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a>Criar uma variável usando um caminho absoluto

Esse comando cria uma `services` variável e armazena o resultado de um `Get-Service` comando nela.

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 Para criar uma variável sem um valor, omita o operador de atribuição.

## <a name="changing-variables"></a>Alterando variáveis

### <a name="rename-a-variable"></a>Renomear uma variável

Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `a` variável para `processes` .

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a>Alterar o valor de uma variável

Esse comando usa o `Set-Item` cmdlet para alterar o valor da `ErrorActionPreference` variável para "Stop".

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a>Copiar uma variável

Esse comando usa o `Copy-Item` cmdlet para copiar a `processes` variável para `old_processes` . Isso cria uma nova variável chamada `old_processes` que tem o mesmo valor que a `processes` variável.

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a>Excluir uma variável

Esse comando exclui a `serv` variável da sessão atual. Você pode usar esse comando em qualquer unidade do PowerShell.

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a>Excluir variáveis usando o parâmetro-Force

Esse comando exclui todas as variáveis da sessão atual, exceto pelas variáveis cuja propriedade **Options** tem um valor de `Constant` . Sem o `-Force` parâmetro, o comando não exclui variáveis cuja propriedade **Options** tem um valor de `ReadOnly` .

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a>Definindo o valor de uma variável como NULL

Esse comando usa o `Clear-Item` cmdlet para alterar o valor da `processes` variável para NULL.

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a>Usando o pipeline

Os cmdlets do provedor aceitam a entrada do pipeline. Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.
Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.

## <a name="getting-help"></a>Obtendo ajuda

A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.

Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a>Confira também

[about_Variables](../About/about_Variables.md)

[about_Automatic_Variables](../About/about_Automatic_Variables.md)

[about_Providers](../About/about_Providers.md)
