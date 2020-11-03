---
description: Ambiente
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Environment
ms.openlocfilehash: ae98e0e8c7d1c4a7e6e975b34e4c6e18b104c01b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196304"
---
# <a name="environment-provider"></a>Provedor de ambiente

## <a name="provider-name"></a>Nome do provedor
Ambiente

## <a name="drives"></a>Unidades

`Env:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso a variáveis de ambiente do Windows.

## <a name="detailed-description"></a>Descrição detalhada

O provedor de **ambiente** do PowerShell permite que você obtenha, adicione, altere, apague e exclua variáveis de ambiente e valores no PowerShell.

Variáveis de **ambiente** são variáveis nomeadas dinamicamente que descrevem o ambiente no qual seus programas são executados. O Windows e o PowerShell usam variáveis de ambiente para armazenar informações persistentes que afetam a execução do sistema e do processo. Ao contrário das variáveis do PowerShell, as variáveis de ambiente não estão sujeitas a restrições de escopo.

A unidade de **ambiente** é um namespace simples que contém as variáveis de ambiente específicas para a sessão do usuário atual. As variáveis de ambiente não têm nenhum item filho.

O provedor de **ambiente** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

Cada variável de ambiente é uma instância da classe [System. Collections. DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) . O nome da variável é a chave do dicionário. O valor da variável de ambiente é o valor do dicionário.

## <a name="navigating-the-environment-drive"></a>Navegando pela unidade do ambiente

O provedor de **ambiente** expõe seu armazenamento de dados na `Env:` unidade. Para trabalhar com variáveis de ambiente, altere seu local para a `Env:` unidade ( `Set-Location Env:` ) ou trabalhe de outra unidade do PowerShell. Para fazer referência a uma variável de ambiente de outro local, use o `Env:` nome da unidade no caminho.

```powershell
Set-Location Env:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor de **ambiente** de qualquer outra unidade do PowerShell. Para fazer referência a uma variável de ambiente de outro local, use o nome da unidade `Env:` no caminho.

O provedor de **ambiente** também expõe variáveis de ambiente usando um prefixo variável de `$env:` .  O comando a seguir exibe o conteúdo da variável de ambiente **ProgramFiles** . O `$env:` prefixo da variável pode ser usado em qualquer unidade do PowerShell.

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

Você também pode alterar o valor de uma variável de ambiente usando o `$env:` prefixo da variável.  Todas as alterações feitas somente pertencem à sessão atual do PowerShell enquanto estiverem ativas.

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-environment-variables"></a>Obtendo variáveis de ambiente

Esse comando lista todas as variáveis de ambiente na sessão atual.

```powershell
Get-Item -Path Env:
```

Você pode usar esse comando em qualquer unidade do PowerShell.

O provedor de ambiente não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a>Obter uma variável de ambiente selecionada

Esse comando obtém a `WINDIR` variável de ambiente.

```powershell
Get-ChildItem -Path Env:windir
```

Você também pode usar o formato de prefixo de variável também.

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a>Criar uma variável de ambiente

Esse comando cria a `USERMODE` variável de ambiente com um valor de "não administrador". O `-Path` valor do parâmetro cria o novo item na `Env:` unidade. A nova variável de ambiente só pode ser usada na sessão atual do PowerShell enquanto estiver ativa.

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a>Alterando uma variável de ambiente

### <a name="rename-an-environment-variable"></a>Renomear uma variável de ambiente

Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `USERMODE` variável de ambiente que você criou para `USERROLE` . Não altere o nome de uma variável de ambiente que usa o sistema. Embora essas alterações afetem apenas a sessão atual, elas podem fazer com que o sistema ou um programa seja operado de forma incorreta.

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a>Alterar uma variável de ambiente

Esse comando usa o `Set-Item` cmdlet para alterar o valor da `USERROLE` variável de ambiente para "administrador".

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a>Copiar uma variável de ambiente

Esse comando copia o valor da `USERROLE` variável de ambiente para a `USERROLE2` variável de ambiente.

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a>Remover uma variável de ambiente

Esse comando exclui a `USERROLE2` variável de ambiente da sessão atual.

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a>Remover uma variável de ambiente com Clear-Item

Esse comando exclui a `USERROLE` variável de ambiente limpando seu valor.

```powershell
Clear-Item -Path Env:USERROLE
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
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a>Confira também

[about_Providers](../About/about_Providers.md)
