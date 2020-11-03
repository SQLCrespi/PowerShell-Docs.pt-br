---
description: Função
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Function
ms.openlocfilehash: 0323433d5ab9114dd1bb21afc47b7fa7db3d6f8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195738"
---
# <a name="function-provider"></a>Provedor de funções

## <a name="provider-name"></a>Nome do provedor
Função

## <a name="drives"></a>Unidades

`Function:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso às funções definidas no PowerShell.

## <a name="detailed-description"></a>Descrição detalhada

O provedor de **funções** do PowerShell permite que você obtenha, adicione, altere, apague e exclua as funções e os filtros no PowerShell.

Uma função é um bloco nomeado de código que executa uma ação. Quando você digita o nome da função, o código na função é executado. Um filtro é um bloco de código nomeado que estabelece as condições para uma ação. Você pode digitar o nome do filtro no lugar da condição, como em um `Where-Object` comando.

A unidade de **função** é um namespace simples que contém apenas os objetos de função e de filtro. Nem funções nem filtros possuem itens filhos.

O provedor de **funções** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

Cada função é uma instância da classe [System. Management. Automation. FunctionInfo](/dotnet/api/system.management.automation.functioninfo) . Cada filtro é uma instância da classe [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) .

## <a name="navigating-the-function-drive"></a>Navegando pela unidade de função

O provedor de **funções** expõe seu armazenamento de dados na `Function:` unidade. Para trabalhar com funções, você pode alterar seu local para a `Function:` unidade ( `Set-Location Function:` ). Ou, você pode trabalhar de outra unidade do PowerShell. Para fazer referência a uma função de outro local, use o nome da unidade ( `Function:` ) no caminho.

```powershell
Set-Location Function:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor de **funções** de qualquer outra unidade do PowerShell. Para fazer referência a uma função de outro local, use o nome da unidade `Function:` no caminho.

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-functions"></a>Obtendo funções

Esse comando obtém a lista de todas as funções na sessão atual. Você pode usar esse comando em qualquer unidade do PowerShell.

```powershell
Get-ChildItem -Path Function:
```

O provedor de funções não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .

```powershell
Get-ChildItem -Path Function:
```

Você pode recuperar a definição de uma função acessando a propriedade **definição** , conforme mostrado abaixo.

```powershell
(Get-Item -Path function:more).Definition
```

Você também pode recuperar a definição de uma função usando seu caminho de provedor prefixado pelo cifrão ( `$` ).

```powershell
$function:more
```

### <a name="getting-selected-functions"></a>Obtendo funções selecionadas

Esse comando obtém a `man` função da `Function:` unidade. Ele usa o `Get-Item` cmdlet para obter a função. O operador de pipeline ( `|` ) envia o resultado para `Format-Table` . O `-Wrap` parâmetro direciona o texto que não cabe na linha para a próxima linha. O `-Autosize` parâmetro redimensiona as colunas da tabela para acomodar o texto.

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a>Trabalhando com caminhos de provedor de funções

Esses comandos obtêm a função chamada `c:` . O primeiro comando pode ser usado em qualquer unidade. O segundo comando é usado na `Function:` unidade. Como o nome termina com dois-pontos, que é a sintaxe para uma unidade, você deve qualificar o caminho com o nome da unidade. Dentro da `Function:` unidade, você pode usar qualquer um dos formatos. No segundo comando, o ponto ( `.` ) representa o local atual.

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a>Criando uma função

Esse comando usa o `New-Item` cmdlet para criar uma função chamada `Win32:` .
A expressão entre chaves é o bloco de script que é representado pelo nome da função.

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

Você também pode criar uma função digitando-a na linha de comando do PowerShell. Por exemplo, TPE `Function:Win32: {Set-Location C:\Windows\System32}` . Se você estiver na `Function:` unidade, poderá omitir o nome da unidade.

## <a name="deleting-a-function"></a>Excluindo uma função

Este comando exclui a `more:` função da sessão atual.

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a>Alterando uma função

Esse comando usa o `Set-Item` cmdlet para alterar a `prompt` função para que ela exiba a hora antes do caminho.

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a>Renomear uma função

Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `help` função para `gh` .

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a>Copiando uma função

Esse comando copia a `prompt` função para `oldPrompt` , criando efetivamente um novo nome para o bloco de script que está associado à função de prompt.
Você pode usar isso para salvar a função de prompt original se quiser alterá-la.
A propriedade **Options** da nova função tem um valor de `None` . Para alterar o valor da propriedade **Options** , use `Set-Item` .

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Opções < [System. Management. Automation. ScopedItemOptions] >

Determina o valor da propriedade **Options** de uma função.

- `None`: Nenhuma opção. `None` é o padrão.
- `Constant`: A função não pode ser excluída e suas propriedades não podem ser alteradas. `Constant` está disponível somente quando você está criando uma função.
  Você não pode alterar a opção de uma função existente para `Constant` .
- `Private`: A função é visível somente no escopo atual
- (não em escopos filho).
- `ReadOnly`: As propriedades da função não podem ser alteradas, exceto usando o `-Force` parâmetro. Você pode usar `Remove-Item` para excluir a função.
- `AllScope`: A função é copiada para todos os novos escopos criados.

### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

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
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a>Confira também

[about_Functions](../About/about_Functions.md)

[about_Providers](../About/about_Providers.md)
