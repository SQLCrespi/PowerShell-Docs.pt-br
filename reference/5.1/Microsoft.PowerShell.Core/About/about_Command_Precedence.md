---
description: Descreve como o PowerShell determina qual comando executar.
keywords: powershell, cmdlet
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: 288c01af2d66aca786cf1b97ad844dd91cac45ca
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196036"
---
# <a name="about-command-precedence"></a>Sobre a precedência de comando

## <a name="short-description"></a>Descrição breve
Descreve como o PowerShell determina qual comando executar.

## <a name="long-description"></a>Descrição longa

Precedência de comando descreve como o PowerShell determina qual comando deve ser executado quando uma sessão contém mais de um comando com o mesmo nome. Os comandos dentro de uma sessão podem ser ocultados ou substituídos por comandos com o mesmo nome. Este artigo mostra como executar comandos ocultos e como evitar conflitos de nome de comando.

## <a name="command-precedence"></a>Precedência de comando

Quando uma sessão do PowerShell inclui mais de um comando que tem o mesmo nome, o PowerShell determina qual comando deve ser executado usando as regras a seguir.

Se você especificar o caminho para um comando, o PowerShell executará o comando no local especificado pelo caminho.

Por exemplo, o comando a seguir executa o script FindDocs.ps1 no diretório "C: \\ TechDocs":

```
C:\TechDocs\FindDocs.ps1
```

Como um recurso de segurança, o PowerShell não executa comandos executáveis (nativos), incluindo scripts do PowerShell, a menos que o comando esteja localizado em um caminho listado na variável de ambiente PATH `$env:path` ou a menos que você especifique o caminho para o arquivo de script.

Para executar um script que está no diretório atual, especifique o caminho completo ou digite um ponto `.\` para representar o diretório atual.

Por exemplo, para executar o arquivo de FindDocs.ps1 no diretório atual, digite:

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a>Usando curingas na execução

Você pode usar curingas na execução do comando. O uso de caracteres curinga também é conhecido como *mascaramento* .

O PowerShell executa um arquivo que tem uma correspondência de curinga, antes de uma correspondência literal.

Por exemplo, considere um diretório com os seguintes arquivos:

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

Ambos os arquivos de script têm o mesmo conteúdo: `$MyInvocation.MyCommand.Path` .
Esse comando exibe o nome do script que é invocado.

Quando você executa `[a1].ps1` o, o arquivo `a.ps1` é executado, embora o arquivo `[a1].ps1` seja uma correspondência literal.

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

Agora, vamos excluir o `a.ps1` arquivo e tentar executá-lo novamente.

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

Você pode ver na saída que `[a1].ps1` é executada desta vez porque a correspondência literal é a única correspondência de arquivo para esse padrão de curinga.

Para obter mais informações sobre como o PowerShell usa curingas, consulte [about_Wildcards](about_Wildcards.md).

> [!NOTE]
> Para limitar a pesquisa a um caminho relativo, você deve prefixar o nome do script com o `.\` caminho. Isso limita a pesquisa de comandos para arquivos nesse caminho relativo. Sem esse prefixo, outra sintaxe do PowerShell pode entrar em conflito e há algumas garantias de que o arquivo será encontrado.

Se você não especificar um caminho, o PowerShell usará a seguinte ordem de precedência quando executar comandos para todos os itens carregados na sessão atual:

  1. Alias
  2. Função
  3. Cmdlet
  4. Arquivos executáveis externos (programas e scripts não PowerShell)

Portanto, se você digitar "Help", o PowerShell primeiro procura um alias chamado `help` , depois uma função chamada `Help` e, finalmente, um cmdlet chamado `Help` . Ele executa o primeiro `help` item que encontra.

Por exemplo, se sua sessão contiver um cmdlet e uma função, ambos nomeados `Get-Map` , quando você digitar `Get-Map` , o PowerShell executará a função.

> [!NOTE]
> Isso se aplica somente a comandos carregados. Se houver um `build` executável e um alias `build` para uma função com o nome de `Invoke-Build` dentro de um módulo que não é carregado na sessão atual, o PowerShell executará o `build` executável em vez disso. Ele não carregará os módulos automaticamente se encontrar o executável externo nesse caso. Só quando nenhum executável externo é encontrado, um alias, uma função ou um cmdlet com o nome fornecido é invocado, disparando assim o carregamento automático de seu módulo.

Quando a sessão contém itens do mesmo tipo que têm o mesmo nome, o PowerShell executa o item mais recente.

Por exemplo, se você importar outro `Get-Date` cmdlet de um módulo, ao digitar `Get-Date` , o PowerShell executará a versão importada no nativo.

## <a name="hidden-and-replaced-items"></a>Itens ocultos e substituídos

Como resultado dessas regras, os itens podem ser substituídos ou ocultados por itens com o mesmo nome.

Os itens serão "ocultos" ou "sombreados" se você ainda puder acessar o item original, como qualificando o nome do item com um módulo ou nome de snap-in.

Por exemplo, se você importar uma função que tem o mesmo nome de um cmdlet na sessão, o cmdlet será oculto (mas não substituído) porque foi importado de um snap-in ou módulo.

Os itens são "substituídos" ou "sobrescritos" se você não puder mais acessar o item original.

Por exemplo, se você importar uma variável que tem o mesmo nome de uma variável na sessão, a variável original será substituída e não estará mais acessível.
Você não pode qualificar uma variável com um nome de módulo.

Além disso, se você digitar uma função na linha de comando e, em seguida, importar uma função com o mesmo nome, a função original será substituída e não estará mais acessível.

### <a name="finding-hidden-commands"></a>Localizando comandos ocultos

O parâmetro **All** do cmdlet [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) Obtém todos os comandos com o nome especificado, mesmo se eles estiverem ocultos ou substituídos. A partir do PowerShell 3,0, por padrão, `Get-Command` obtém somente os comandos que são executados quando você digita o nome do comando.

Nos exemplos a seguir, a sessão inclui uma `Get-Date` função e um cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) .

O comando a seguir obtém o `Get-Date` comando que é executado quando você digita `Get-Date` .

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

O comando a seguir usa o parâmetro **All** para obter todos os `Get-Date` comandos.

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a>Executando comandos ocultos

Você pode executar comandos específicos especificando propriedades de item que distinguem o comando de outros comandos que podem ter o mesmo nome. Você pode usar esse método para executar qualquer comando, mas ele é especialmente útil para executar comandos ocultos.

#### <a name="qualified-names"></a>Nomes qualificados

O uso do nome qualificado por módulo de um cmdlet permite que você execute comandos ocultos por um item com o mesmo nome. Por exemplo, você pode executar o `Get-Date` cmdlet qualificando-o com seu nome de módulo **Microsoft. PowerShell. Utility** .

Use esse método preferido ao escrever scripts que você pretende distribuir. Você não pode prever quais comandos podem estar presentes na sessão em que o script é executado.

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

Para executar um `New-Map` comando que foi adicionado pelo `MapFunctions` módulo, use o nome qualificado do módulo:

```powershell
MapFunctions\New-Map
```

Para localizar o módulo do qual um comando foi importado, use a propriedade **ModuleName** de comandos.

```
(Get-Command <command-name>).ModuleName
```

Por exemplo, para localizar a origem do `Get-Date` cmdlet, digite:

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> Você não pode qualificar variáveis ou aliases.

#### <a name="call-operator"></a>Operador de chamada

Você também pode usar o `Call` operador `&` para executar comandos ocultos, combinando-o com uma chamada para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (o alias é "dir") `Get-Command` ou [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).

O operador de chamada executa cadeias de caracteres e blocos de script em um escopo filho. Para obter mais informações, consulte [about_Operators](about_Operators.md).

Por exemplo, se você tiver uma função chamada `Map` que é ocultada por um alias chamado `Map` , use o comando a seguir para executar a função.

```powershell
&(Get-Command -Name Map -CommandType Function)
```

ou

```powershell
&(dir Function:\map)
```

Você também pode salvar o comando oculto em uma variável para facilitar a execução.

Por exemplo, o comando a seguir salva a `Map` função na `$myMap` variável e, em seguida, usa o `Call` operador para executá-la.

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a>Itens substituídos

Um item "substituído" é aquele que você não pode mais acessar. Você pode substituir itens Importando itens de mesmo nome de um módulo ou snap-in.

Por exemplo, se você digitar uma `Get-Map` função em sua sessão e importar uma função chamada `Get-Map` , ela substituirá a função original. Você não pode recuperá-lo na sessão atual.

Variáveis e aliases não podem ser ocultados porque você não pode usar um operador de chamada ou um nome qualificado para executá-los. Quando você importa variáveis e aliases de um módulo ou snap-in, eles substituem variáveis na sessão com o mesmo nome.

### <a name="avoiding-name-conflicts"></a>Evitando conflitos de nome

A melhor maneira de gerenciar conflitos de nome de comando é impedi-los. Ao nomear seus comandos, use um nome exclusivo. Por exemplo, adicione as iniciais ou o acrônimo de nome da empresa aos substantivos em seus comandos.

Além disso, quando você importa comandos para a sessão de um módulo do PowerShell ou de outra sessão, use o `Prefix` parâmetro do [módulo importar/](xref:Microsoft.PowerShell.Core.Import-Module) ou

Cmdlet [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) para adicionar um prefixo aos substantivos nos nomes de comandos.

Por exemplo, o comando a seguir evita qualquer conflito com os `Get-Date` `Set-Date` cmdlets e que acompanham o PowerShell quando você importa o `DateFunctions` módulo.

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

Para obter mais informações, consulte `Import-Module` e `Import-PSSession` abaixo.

## <a name="see-also"></a>Confira também

- [about_Path_Syntax](about_Path_Syntax.md)
- [about_Aliases](about_Aliases.md)
- [about_Functions](about_Functions.md)
- [Alias-Provider](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [Function-Provider](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
- [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)
