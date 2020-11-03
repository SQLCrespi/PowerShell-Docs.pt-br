---
description: Alias
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Alias
ms.openlocfilehash: e5251b6e36da5e5c32d9e7c826766aa3dc38a9e0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195793"
---
# <a name="alias-provider"></a>Provedor de alias

## <a name="provider-name"></a>Nome do provedor
Alias

## <a name="drives"></a>Unidades

`Alias:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso aos aliases do PowerShell e aos valores que eles representam.

## <a name="detailed-description"></a>Descrição detalhada

O provedor de **alias** do PowerShell permite que você obtenha, adicione, altere, apague e exclua aliases no PowerShell.

Um alias é um nome alternativo para um cmdlet, função, arquivo executável, incluindo scripts. O PowerShell inclui um conjunto de aliases internos. Você pode adicionar seus próprios aliases à sessão atual e ao seu perfil do PowerShell.

A unidade de **alias** é um namespace simples que contém apenas os objetos de alias.
Os aliases não possuem itens filho.

O provedor de **alias** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

O PowerShell inclui um conjunto de cmdlets que são projetados para exibir e alterar aliases. Quando você usa cmdlets de **alias** , não é necessário especificar a `Alias:` unidade no nome. Este artigo não aborda o trabalho com cmdlets de **alias** .

- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

Cada alias é uma instância da classe [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) .

## <a name="navigating-the-alias-drive"></a>Navegando pela unidade de alias

O provedor de **alias** expõe seu armazenamento de dados na `Alias:` unidade. Para trabalhar com aliases, você pode alterar seu local para a `Alias:` unidade usando o seguinte comando:

```powershell
Set-Location Alias:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor de alias de qualquer outra unidade do PowerShell. Para fazer referência a um alias de outro local, use o `Alias:` nome da unidade no caminho.

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

### <a name="displaying-the-contents-of-the-alias-drive"></a>Exibindo o conteúdo da unidade Alias:

Esse comando obtém a lista de todos os aliases quando o local atual é a `Alias:` unidade. Ele usa um caractere curinga `*` para indicar todo o conteúdo do local atual.

```powershell
PS Alias:\> Get-Item -Path *
```

Na `Alias:` unidade, um ponto `.` , que representa o local atual e um caractere curinga `*` , que representa todos os itens no local atual, têm o mesmo efeito. Por exemplo, `Get-Item -Path .` ou `Get-Item \*` produzir o mesmo resultado.

O provedor de alias não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a>Obter um alias selecionado

Esse comando obtém o `ls` alias.
Como ele inclui o caminho, você pode usá-lo em qualquer unidade do PowerShell.

```powershell
Get-Item -Path Alias:ls
```

Se você estiver na `Alias:` unidade, poderá omitir o nome da unidade do caminho.

Você também pode recuperar a definição de um alias prefixando o caminho do provedor com o cifrão ( `$` ).

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a>Obter todos os aliases para um cmdlet específico

Esse comando obtém uma lista dos aliases associados ao `Get-ChildItem` cmdlet. Ele usa a propriedade de **definição** , que armazena o nome do cmdlet.

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a>Criando aliases

### <a name="create-an-alias-from-the-alias-drive"></a>Criar um alias da unidade Alias:

Este comando cria o `serv` alias para o `Get-Service` cmdlet. Como o local atual está na `Alias:` unidade, o `-Path` parâmetro não é necessário.

Esse comando também usa o `-Options` parâmetro dinâmico para definir a opção de **escopo** no alias. O `-Options` parâmetro estará disponível no `New-Item` cmdlet somente quando você estiver na `Alias:` unidade. O ponto ( `.` ) indica o diretório atual, que é a unidade de alias.

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a>Criar um alias com um caminho absoluto

Você pode criar um alias para qualquer item que chama um comando.
Este comando cria o `np` alias para `Notepad.exe` .

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a>Criar um alias para uma nova função

Você pode criar um alias para qualquer função. Você pode usar esse recurso para criar um alias que inclui um cmdlet e seus parâmetros.

O primeiro comando cria a `CD32` função, que altera o diretório atual para o `System32` diretório. O segundo comando cria o `go` alias para a `CD32` função.

Quando o comando for concluído, você poderá usar o `CD32` ou o `go` para invocar a função.

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a>Alterando aliases

### <a name="change-the-options-of-an-alias"></a>Alterar as opções de um alias

Você pode usar o `Set-Item` cmdlet com o `-Options` parâmetro dinâmico para alterar o valor da `-Options` propriedade de um alias.

Esse comando define as opções de **escopo** e **somente leitura** para o `dir` alias. O comando usa o `-Options` parâmetro dinâmico do `Set-Item` cmdlet. O `-Options` parâmetro está disponível em `Set-Item` quando você o usa com o **alias** ou o provedor de **funções** .

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a>Alterar um comando de aliases referenciado

Esse comando usa o `Set-Item` cmdlet para alterar o `gp` alias para que ele represente o `Get-Process` cmdlet em vez do `Get-ItemProperty` cmdlet.
O `-Force` parâmetro é necessário porque o valor da propriedade **Options** do `gp` alias é definido como `ReadOnly` . Como o comando é enviado de dentro da `Alias:` unidade, a unidade não é especificada no caminho.

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

A alteração afeta as quatro propriedades que definem a associação entre o alias e o comando. Para exibir o efeito da alteração, digite o seguinte comando:

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a>Renomear um alias

Esse comando usa o `Rename-Item` cmdlet para alterar o `popd` alias para `pop` .

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a>Copiando um alias

Esse comando copia o `pushd` alias para que um novo `push` alias seja criado para o `Push-Location` cmdlet.

Quando o novo alias é criado, sua propriedade **Description** tem um valor nulo.
E, sua propriedade **Option** tem um valor de `None` . Se o comando for emitido de dentro da `Alias:` unidade, você poderá omitir o nome da unidade do valor do `-Path` parâmetro.

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a>Excluindo um alias

Este comando exclui o `serv` alias da sessão atual.
Você pode usar esse comando em qualquer unidade do PowerShell.

```powershell
Remove-Item -Path Alias:serv
```

Esse comando exclui aliases que começam com "s".
Isso não exclui os aliases de somente leitura.

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a>Excluir aliases somente leitura

Esse comando exclui todos os aliases da sessão atual, exceto aqueles com um valor de `Constant` para a propriedade **Options** . O `-Force` parâmetro permite que o comando exclua aliases cuja propriedade **Options** tem um valor de `ReadOnly` .

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Opções [System. Management. Automation. ScopedItemOptions]

Determina o valor da propriedade **Options** de um alias.

- **Nenhum** : nenhuma opção. Esse valor é o padrão.
- **Constante** : o alias não pode ser excluído e suas propriedades não podem ser alteradas.
  A **constante** está disponível somente quando você cria um alias. Você não pode alterar a opção de um alias existente para **constante** .
- **Particular** : o alias é visível apenas no escopo atual, não nos escopos filho.
- **ReadOnly** : as propriedades do alias não podem ser alteradas, exceto usando o `-Force` parâmetro. Você pode usar `Remove-Item` para excluir o alias.
- **Escopo** : o alias é copiado para todos os novos escopos criados.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

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
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a>Confira também

[about_Aliases](../About/about_Aliases.md)

[about_Providers](../About/about_Providers.md)
