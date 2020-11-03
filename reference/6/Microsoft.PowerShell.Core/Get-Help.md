---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 691709fe3f5e4908ab3203df73f636981adf560c
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "93195090"
---
# Get-Help

## SINOPSE
Exibe informações sobre os comandos e conceitos do PowerShell.

## SYNTAX

### AllUsersView (padrão)

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### DetailedView

```
Get-Help [[-Name] <String>] -Detailed [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Exemplos

```
Get-Help [[-Name] <String>] -Examples [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Parâmetros

```
Get-Help [[-Name] <String>] -Parameter <String[]> [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Online

```
Get-Help [[-Name] <String>] -Online [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Help` cmdlet exibe informações sobre os conceitos e comandos do PowerShell, incluindo cmdlets, funções, comandos de modelo CIM (CIM), fluxos de trabalho, provedores, aliases e scripts.

Para obter ajuda para um cmdlet do PowerShell, digite `Get-Help` seguido pelo nome do cmdlet, como: `Get-Help Get-Process` .

Os artigos de ajuda conceitual no PowerShell começam com **about_** , como **about_Comparison_Operators** . Para ver todos os artigos **about_** , digite `Get-Help about_*` . Para ver um artigo específico, digite `Get-Help about_<article-name>` , como `Get-Help about_Comparison_Operators` .

Para obter ajuda para um provedor do PowerShell, digite `Get-Help` seguido pelo nome do provedor. Por exemplo, para obter ajuda para o provedor de certificado, digite `Get-Help Certificate` .

Você também pode digitar `help` ou `man` , que exibe uma tela de texto de cada vez. Ou, `<cmdlet-name> -?` , que é idêntico a `Get-Help` , mas funciona apenas para cmdlets.

`Get-Help` Obtém o conteúdo da ajuda que ele exibe dos arquivos de ajuda no seu computador. Sem os arquivos de ajuda, o `Get-Help` exibe apenas informações básicas sobre os cmdlets. Alguns módulos do PowerShell incluem arquivos de ajuda. A partir do PowerShell 3,0, os módulos fornecidos com o sistema operacional Windows não incluem arquivos de ajuda. Para baixar ou atualizar os arquivos de ajuda para um módulo no PowerShell 3,0, use o `Update-Help` cmdlet.

Você também pode exibir os documentos de ajuda do PowerShell online no Microsoft Docs. Para obter a versão online de um arquivo de ajuda, use o parâmetro **online** , como: `Get-Help Get-Process -Online` . Para ler toda a documentação do PowerShell, consulte a [documentação](/powershell)do Microsoft docs PowerShell.

Se você digitar `Get-Help` seguido pelo nome exato de um artigo de ajuda ou por uma palavra exclusiva para um artigo de ajuda, `Get-Help` o exibirá o conteúdo do artigo. Se você especificar o nome exato de um alias de comando, `Get-Help` o exibirá a ajuda do comando original. Se você inserir um padrão de palavra ou palavra que aparece em vários títulos de artigos `Get-Help` da ajuda, o exibirá uma lista dos títulos correspondentes. Se você inserir qualquer texto que não apareça em títulos de artigos de ajuda, `Get-Help` o exibirá uma lista de artigos que incluem esse texto em seu conteúdo.

`Get-Help` pode obter artigos de ajuda para todos os idiomas e localidades com suporte. `Get-Help` o primeiro procura arquivos de ajuda na localidade definida para Windows, em seguida, na localidade pai, como **pt** para **pt-br** e, em seguida, em uma localidade de fallback. A partir do PowerShell 3,0, se o `Get-Help` não encontrar ajuda na localidade de fallback, ele procurará artigos de ajuda em inglês, **en-US** , antes de retornar uma mensagem de erro ou exibir a ajuda gerada automaticamente.

Para obter informações sobre os símbolos `Get-Help` exibidos no diagrama de sintaxe de comando, consulte [about_Command_Syntax](./About/about_Command_Syntax.md).
Para obter informações sobre atributos de parâmetro, como **Required** e **Position** , consulte [about_Parameters](./About/about_Parameters.md).

>[!NOTE]
> No PowerShell 3,0 e no PowerShell 4,0, `Get-Help` o **About** não consegue encontrar artigos em módulos, a menos que o módulo seja importado para a sessão atual. Este é um problema conhecido. Para obter **informações sobre** artigos em um módulo, importe o módulo usando o `Import-Module` cmdlet ou executando um cmdlet que está incluído no módulo.

## EXEMPLOS

### Exemplo 1: exibir informações básicas de ajuda sobre um cmdlet

Esses exemplos exibem informações básicas de ajuda sobre o `Format-Table` cmdlet.

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

`Get-Help <cmdlet-name>` é a sintaxe mais simples e padrão do `Get-Help` cmdlet. Você pode omitir o parâmetro **Name** .

A sintaxe `<cmdlet-name> -?` funciona apenas para cmdlets.

### Exemplo 2: exibir informações básicas uma página por vez

Esses exemplos exibem informações básicas de ajuda sobre o `Format-Table` cmdlet uma página por vez.

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

`help` é uma função que executa `Get-Help` o cmdlet internamente e exibe o resultado uma página por vez.

`man` é um alias para a `help` função.

`Get-Help Format-Table` envia o objeto para baixo do pipeline. `Out-Host -Paging` recebe a saída do pipeline e exibe uma página por vez. Para obter mais informações, consulte [Out-Host](Out-Host.md).

### Exemplo 3: exibir mais informações para um cmdlet

Esses exemplos exibem informações de ajuda mais detalhadas sobre o `Format-Table` cmdlet.

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

O parâmetro **detailed** exibe a exibição detalhada do artigo de ajuda que inclui descrições e exemplos de parâmetros.

O parâmetro **Full** exibe a exibição completa do artigo de ajuda que inclui descrições de parâmetro, exemplos, tipos de objeto de entrada e saída e observações adicionais.

Os parâmetros **detalhados** e **completos** são efetivos apenas para os comandos que têm arquivos de ajuda instalados no computador. Os parâmetros não são eficazes para os artigos de ajuda conceitual ( **about_** ).

### Exemplo 4: exibir as partes selecionadas de um cmdlet usando parâmetros

Esses exemplos exibem as partes selecionadas da `Format-Table` ajuda do cmdlet.

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

O parâmetro de **exemplos** exibe as seções **nome** e **Sinopse** do arquivo de ajuda e todos os exemplos. Você não pode especificar um número de exemplo porque o parâmetro de **exemplos** é um parâmetro de opção.

O parâmetro **Parameter** exibe apenas as descrições dos parâmetros especificados. Se você especificar apenas o `*` caractere curinga asterisco (), ele exibirá as descrições de todos os parâmetros.
Quando o **parâmetro** especifica um nome de parâmetro, como **GroupBy** , as informações sobre esse parâmetro são mostradas.

Esses parâmetros não são eficazes para os artigos de ajuda conceitual ( **about_** ).

### Exemplo 5: exibir a versão online da ajuda

Este exemplo exibe a versão online do artigo de ajuda para o `Format-Table` cmdlet no navegador da Web padrão.

```powershell
Get-Help Format-Table -Online
```

### Exemplo 6: exibir a ajuda sobre o sistema de ajuda

O `Get-Help` cmdlet sem parâmetros exibe informações sobre o sistema de ajuda do PowerShell.

```powershell
Get-Help
```

### Exemplo 7: Exibir artigos de ajuda disponíveis

Este exemplo exibe uma lista de todos os artigos de ajuda disponíveis no seu computador.

```powershell
Get-Help *
```

### Exemplo 8: exibir uma lista de artigos conceituais

Este exemplo exibe uma lista dos artigos conceituais incluídos na ajuda do PowerShell. Todos esses artigos começam com os caracteres **about_** . Para exibir um arquivo de ajuda específico, digite `Get-Help \<about_article-name\>` , por exemplo, `Get-Help about_Signing` .

Somente os artigos conceituais que têm arquivos de ajuda instalados no computador são exibidos. Para obter informações sobre como baixar e instalar arquivos de ajuda no PowerShell 3,0, consulte [Update-Help](Update-Help.md).

```powershell
Get-Help about_*
```

### Exemplo 9: Pesquisar uma palavra na ajuda do cmdlet

Este exemplo mostra como pesquisar uma palavra em um artigo de ajuda de cmdlet.

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

`Get-Help` usa o parâmetro **Full** para obter informações de ajuda para o `Add-Member` . O objeto **MamlCommandHelpInfo** é enviado pelo pipeline. `Out-String` usa o parâmetro **Stream** para converter o objeto em uma cadeia de caracteres. `Select-String` usa o parâmetro **Pattern** para pesquisar a cadeia de caracteres de **Clixml** .

### Exemplo 10: exibir uma lista de artigos que incluem uma palavra

Este exemplo exibe uma lista de artigos que incluem a palavra **Remoting** .

Quando você insere uma palavra que não aparece em nenhum título de artigo, `Get-Help` o exibe uma lista de artigos que incluem essa palavra.

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### Exemplo 11: exibir a ajuda específica do provedor

Este exemplo mostra duas maneiras de obter a ajuda específica do provedor para o `Get-Item` . Esses comandos obtêm ajuda que explica como usar o `Get-Item` cmdlet no nó **DataCollection** do provedor de SQL Server do PowerShell.

O primeiro exemplo usa o `Get-Help` parâmetro **Path** para especificar o caminho do provedor de SQL Server.
Como o caminho do provedor é especificado, você pode executar o comando de qualquer local de caminho.

O segundo exemplo usa `Set-Location` para navegar até o caminho do provedor de SQL Server. Nesse local, o parâmetro **path** não é necessário para `Get-Help` que o obtenha a ajuda específica do provedor.

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### Exemplo 12: exibir a ajuda para um script

Este exemplo obtém ajuda para o `MyScript.ps1 script` . Para obter informações sobre como escrever ajuda para suas funções e scripts, consulte [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## PARAMETERS

### -Categoria

Exibe ajuda apenas para itens na categoria especificada e seus aliases. Os artigos conceituais estão na categoria **HelpFile** .

Os valores aceitáveis para esse parâmetro são os seguintes:

- Alias
- Cmdlet
- Provedor
- Geral
- Perguntas frequentes
- Glossário
- HelpFile
- ScriptCommand
- Função
- Filtrar
- ExternalScript
- Tudo
- Defaulthelp
- Fluxo de trabalho
- DscResource
- Classe
- Configuração

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Componente

Exibe comandos com o valor do componente especificado, como o **Exchange** . Insira um nome de componente.
Caracteres curinga são permitidos. Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).

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

### -Detailed

Adiciona descrições de parâmetro e exemplos à exibição de ajuda básica. Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador. Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Examples

Exibe apenas o nome, sinopse e exemplos. Para exibir apenas os exemplos, digite `(Get-Help \<cmdlet-name\>).Examples` .

Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador. Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Exibe o artigo de ajuda inteiro de um cmdlet. **Completo** inclui descrições de parâmetro e atributos, exemplos, tipos de objeto de entrada e saída e observações adicionais.

Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador. Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Funcionalidade

Exibe ajuda para os itens com a funcionalidade especificada. Insira a funcionalidade. Caracteres curinga são permitidos. Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).

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

Obtém ajuda sobre o comando ou conceito especificado. Insira o nome de um cmdlet, uma função, um provedor, um script ou um fluxo de trabalho, como `Get-Member` um nome de artigo conceitual, como `about_Objects` , ou um alias, como `ls` . Caracteres curinga são permitidos em nomes de cmdlet e de provedor, mas você não pode usar caracteres curinga para localizar os nomes dos artigos de ajuda de função e de script.

Para obter ajuda para um script que não está localizado em um caminho listado na variável de `$env:Path` ambiente, digite o caminho e o nome do arquivo do script.

Se você inserir o nome exato de um artigo de ajuda, `Get-Help` o exibirá o conteúdo do artigo.

Se você inserir um padrão de palavra ou palavra que aparece em vários títulos de artigos `Get-Help` da ajuda, o exibirá uma lista dos títulos correspondentes.

Se você inserir qualquer texto que não corresponda a nenhum título de artigo `Get-Help` da ajuda, o exibirá uma lista de artigos que incluem esse texto em seu conteúdo.

Os nomes dos artigos conceituais, como `about_Objects` , devem ser inseridos em inglês, mesmo em versões do PowerShell que não estejam em inglês.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Online

Exibe a versão online de um artigo de ajuda no navegador padrão. Esse parâmetro é válido somente para artigos de ajuda de cmdlet, função, fluxo de trabalho e script. Você não pode usar o parâmetro **online** com `Get-Help` em uma sessão remota.

Para obter informações sobre como dar suporte a esse recurso nos artigos de ajuda que você escreve, consulte [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)e [suporte à ajuda online](/powershell/scripting/developer/module/supporting-online-help)e [como escrever ajuda para cmdlets do PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Parâmetros do 

Exibe apenas as descrições detalhadas dos parâmetros especificados. Caracteres curinga são permitidos. Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Obtém ajuda que explica como o cmdlet funciona no caminho do provedor especificado. Insira um caminho do provedor do PowerShell.

Esse parâmetro Obtém uma versão personalizada de um artigo de ajuda de cmdlet que explica como o cmdlet funciona no caminho do provedor do PowerShell especificado. Esse parâmetro é eficaz apenas para obter ajuda sobre um cmdlet de provedor e somente quando o provedor inclui uma versão personalizada do artigo de ajuda do cmdlet do provedor em seu arquivo de ajuda. Para usar este parâmetro, instale o arquivo de ajuda para o módulo que inclui o provedor.

Para ver a ajuda do cmdlet personalizado para um caminho do provedor, acesse o local do caminho do provedor e insira um `Get-Help` comando ou, em qualquer local do caminho, use o parâmetro **Path** de `Get-Help` para especificar o caminho do provedor. Você também pode encontrar a ajuda online do cmdlet na seção de ajuda do provedor dos artigos de ajuda.

Para obter mais informações sobre provedores do PowerShell, consulte [about_Providers](./About/about_Providers.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Função

Exibe a ajuda personalizada para a função de usuário especificada. Insira uma função. Caracteres curinga são permitidos.

Insira a função que o usuário desempenha em uma organização. Alguns cmdlets exibem texto diferente em seus arquivos de ajuda com base no valor deste parâmetro. Este parâmetro não tem nenhum efeito na ajuda para os cmdlets principais.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Você não pode enviar objetos pelo pipeline para o `Get-Help` .

## SAÍDAS

### ExtendedCmdletHelpInfo

Se você executar `Get-Help` em um comando que não tem um arquivo de ajuda, o `Get-Help` retornará um objeto **ExtendedCmdletHelpInfo** que representa a ajuda gerada automaticamente.

### System.String

Se você receber um artigo de ajuda conceitual, o `Get-Help` o retornará como uma cadeia de caracteres.

### MamlCommandHelpInfo

Se você receber um comando que tem um arquivo de ajuda, `Get-Help` o retornará um objeto **MamlCommandHelpInfo** .

## OBSERVAÇÕES

O PowerShell 3,0 não inclui arquivos de ajuda. Para baixar e instalar os arquivos de ajuda que o `Get-Help` lê, use o `Update-Help` cmdlet. Você pode usar o `Update-Help` cmdlet para baixar e instalar arquivos de ajuda para os comandos principais que acompanham o PowerShell e para quaisquer módulos que você instalar. Ele também pode ser usado para atualizar os arquivos de ajuda, de modo que a ajuda em seu computador nunca fique desatualizada.

Você também pode ler os artigos de ajuda sobre os comandos que acompanham o PowerShell online, começando em [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

`Get-Help` exibe a ajuda na localidade definida para o sistema operacional Windows ou no idioma de fallback para essa localidade. Se você não tiver arquivos de ajuda para a localidade primária ou de fallback, o `Get-Help` se comporta como se não houvesse arquivos de ajuda no computador. Para obter ajuda para uma localidade diferente, use **região** e **idioma** no painel de controle para alterar as configurações. No Windows 10, **configurações** , **hora & idioma** .

A exibição completa da ajuda inclui uma tabela de informações sobre os parâmetros. A tabela inclui os seguintes campos:

- **Obrigatório** . Indica se o parâmetro é obrigatório (verdadeiro) ou opcional (falso).

- **Posição** . Indica se o parâmetro é nomeado ou posicional (numérico). Parâmetros posicionais devem aparecer em um local especificado no comando.

- **Chamado** indica que o nome do parâmetro é necessário, mas que o parâmetro pode aparecer em qualquer lugar no comando.

- **Numeric** indica que o nome do parâmetro é opcional, mas quando o nome é omitido, o parâmetro deve estar no local especificado pelo número. Por exemplo, `2` indica que quando o nome do parâmetro é omitido, o parâmetro deve ser o segundo ou apenas o parâmetro não nomeado no comando. Quando o nome do parâmetro é usado, o parâmetro pode aparecer em qualquer lugar no comando.

- **Valor padrão** . O valor do parâmetro ou o comportamento padrão que o PowerShell usa se você não incluir o parâmetro no comando.

- Aceita a entrada do pipeline. Indica se você pode (true) ou não pode (falso) enviar objetos para o parâmetro por meio de um pipeline. **Por nome de propriedade** significa que o objeto de pipeline deve ter uma propriedade que tenha o mesmo nome que o nome do parâmetro.

- **Aceita caracteres curinga** . Indica se o valor de um parâmetro pode incluir caracteres curinga, como um asterisco ( `*` ) ou um ponto de interrogação ( `?` ).

## LINKS RELACIONADOS

[about_Command_Syntax](About/about_Command_Syntax.md)

[about_Comment_Based_Help](./About/about_Comment_Based_Help.md)

[Get-Command](Get-Command.md)

[Suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help)

[Update-Help](Update-Help.md)

[Escrever tópicos da ajuda baseados em comentário](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[Escrever tópicos de ajuda para cmdlets do PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)
