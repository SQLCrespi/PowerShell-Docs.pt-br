---
description: FileSystem
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem Provider
ms.openlocfilehash: 3b37f6e4eb53ef7291c30cbc9820caf83641a9bb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196207"
---
# <a name="filesystem-provider"></a>FileSystem Provider

## <a name="provider-name"></a>Nome do provedor

FileSystem

## <a name="drives"></a>Unidades

`C:`, `D:` ...

## <a name="capabilities"></a>Funcionalidades

**Filtrar** , **ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso a arquivos e diretórios.

## <a name="detailed-description"></a>Descrição detalhada

O provedor do **sistema de arquivos** do PowerShell permite que você obtenha, adicione, altere, apague e exclua arquivos e diretórios no PowerShell.

As unidades do **sistema de arquivos** são um namespace hierárquico que contém os diretórios e arquivos em seu computador. Uma unidade de **sistema de arquivos** pode ser uma unidade lógica ou físicos, um diretório ou um compartilhamento de rede mapeado.

O provedor **FileSystem** oferece suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

Os arquivos são instâncias da classe [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) .  Os diretórios são instâncias da classe [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) .

## <a name="navigating-the-filesystem-drives"></a>Navegando pelas unidades do sistema de arquivos

O provedor **FileSystem** expõe seus armazenamentos de dados mapeando quaisquer unidades lógicas no computador como unidades do PowerShell. Para trabalhar com uma unidade de **sistema de arquivos** , você pode alterar seu local para uma unidade utoridades o nome da unidade seguido por dois-pontos ( `:` ).

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor **FileSystem** de qualquer outra unidade do PowerShell. Para fazer referência a um arquivo ou diretório de outro local, use o nome da unidade ( `C:` , `D:` ,...) no caminho.

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-files-and-directories"></a>Obtendo arquivos e diretórios

O `Get-ChildItem` cmdlet retorna todos os arquivos e diretórios no local atual. Você pode especificar um caminho diferente para pesquisar e usar parâmetros internos para filtrar e controlar a profundidade da recursão.

```powershell
Get-ChildItem
```

Para ler mais sobre o uso de cmdlet, consulte [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).

## <a name="copying-files-and-directories"></a>Copiando arquivos e diretórios

O `Copy-Item` cmdlet copia arquivos e diretórios para um local que você especificar.
Os parâmetros estão disponíveis para filtrar e recurse, semelhante a `Get-ChildItem` .

O comando a seguir copia todos os arquivos e diretórios no caminho "C:\temp" \" para a pasta "C:\Windows\Temp".

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

`Copy-Item` substitui os arquivos no diretório de destino sem solicitar confirmação.

Esse comando copia o `a.txt` arquivo do `C:\a` diretório para o `C:\a\bb` diretório.

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

Copia todos os diretórios e arquivos no `C:\a` diretório para o `C:\c` diretório. Se qualquer um dos diretórios para copiar já existir no diretório de destino, o comando falhará a menos que você especifique o parâmetro Force.

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

Para obter mais informações, consulte [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).

## <a name="moving-files-and-directories"></a>Movendo arquivos e diretórios

Esse comando move o `c.txt` arquivo no `C:\a` diretório para o `C:\a\aa` diretório:

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

O comando não substituirá automaticamente um arquivo existente que tenha o mesmo nome. Para forçar o cmdlet a substituir um arquivo existente, especifique o parâmetro Force.

Você não pode mover um diretório quando aquele diretório é o local atual. Ao usar `Move-Item` o para mover o diretório no local atual, você verá esse erro.

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a>Gerenciando conteúdo do arquivo

### <a name="get-the-content-of-a-file"></a>Obter o conteúdo de um arquivo

Esse comando obtém o conteúdo do arquivo "Test.txt" e os exibe no console do.

```powershell
Get-Content -Path Test.txt
```

Você pode canalizar o conteúdo do arquivo para outro cmdlet. Por exemplo, o comando a seguir lê o conteúdo do `Test.txt` arquivo e, em seguida, fornece-os como entrada para o cmdlet [ConvertTo-HTML](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) :

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

Você também pode recuperar o conteúdo de um arquivo prefixando seu caminho de provedor com o cifrão ( `$` ). O caminho deve ser colocado entre chaves devido a restrições de nomenclatura de variáveis. Para obter mais informações, consulte [about_Variables](about_Variables.md).

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a>Adicionar conteúdo a um arquivo

Esse comando acrescenta a cadeia de caracteres "conteúdo do teste" ao `Test.txt` arquivo:

```powershell
Add-Content -Path test.txt -Value "test content"
```

O conteúdo existente no `Test.txt` arquivo não é excluído.

### <a name="replace-the-content-of-a-file"></a>Substituir o conteúdo de um arquivo

Esse comando substitui o conteúdo do `Test.txt` arquivo pela cadeia de caracteres "conteúdo do teste":

```powershell
Set-Content -Path test.txt -Value "test content"
```

Ele substitui o conteúdo de `Test.txt` . Você pode usar o parâmetro **Value** do cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para adicionar conteúdo a um arquivo ao criá-lo.

### <a name="loop-through-the-contents-of-a-file"></a>Executar um loop no conteúdo de um arquivo

Por padrão, o `Get-Content` cmdlet usa o caractere de final de linha como seu delimitador, portanto, ele obtém um arquivo como uma coleção de cadeias de caracteres, com cada linha como uma cadeia de caracteres no arquivo.

Você pode usar o `-Delimiter` parâmetro para especificar um delimitador alternativo. Se você defini-lo para os caracteres que indicam o final de uma seção ou o início da próxima seção, você pode dividir o arquivo em partes lógicas.

O primeiro comando obtém o `Employees.txt` arquivo e o divide em seções, cada um dos quais termina com as palavras "fim do registro do funcionário" e salva-o na `$e` variável.

O segundo comando usa a notação de matriz para obter o primeiro item na coleção no `$e` . Ele usa um índice de 0, porque as matrizes do PowerShell são baseadas em zero.

Para obter mais informações sobre o `Get-Content` cmdlet, consulte o tópico da ajuda para o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).

Para obter mais informações sobre matrizes, consulte [about_Arrays](../About/about_Arrays.md).

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a>Gerenciando descritores de segurança

### <a name="view-the-acl-for-a-file"></a>Exibir a ACL para um arquivo

Esse comando retorna um objeto [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) :

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

Para obter mais informações sobre esse objeto, redirecione o comando para o cmdlet [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) . Ou então, consulte "classe[FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) " na biblioteca do MSDN (Microsoft Developer Network).

### <a name="modify-the-acl-for-a-file"></a>Modificar a ACL de um arquivo

### <a name="create-and-set-an-acl-for-a-file"></a>Criar e definir uma ACL para um arquivo

## <a name="creating-files-and-directories"></a>Criando arquivos e diretórios

### <a name="create-a-directory"></a>Criar um diretório

Este comando cria o `logfiles` diretório na `C` unidade:

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

O PowerShell também inclui uma `mkdir` função (alias `md` ) que usa o cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para criar um novo diretório.

### <a name="create-a-file"></a>Criar um arquivo

Esse comando cria o `log2.txt` arquivo no `C:\logfiles` diretório e, em seguida, adiciona a cadeia de caracteres "log de teste" ao arquivo:

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a>Crie um arquivo com conteúdo

Cria um arquivo chamado `log2.txt` no `C:\logfiles` diretório e adiciona a cadeia de caracteres "log de teste" ao arquivo.

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a>Renomeando arquivos e diretórios

### <a name="rename-a-file"></a>Renomear um arquivo

Esse comando renomeia o `a.txt` arquivo no `C:\a` diretório para `b.txt` :

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a>Renomear um diretório

Esse comando renomeia o `C:\a\cc` diretório para `C:\a\dd` :

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a>Excluindo arquivos e diretórios

### <a name="delete-a-file"></a>Excluir um arquivo

Este comando exclui o `Test.txt` arquivo no diretório atual:

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a>Excluir arquivos usando curingas

Este comando exclui todos os arquivos no diretório atual que têm a `.xml` extensão de nome de arquivo:

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a>Iniciando um programa invocando um arquivo associado

### <a name="invoke-a-file"></a>Invocar um arquivo

O primeiro comando usa o cmdlet [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) para obter informações sobre serviços locais.

Ele canaliza as informações para o cmdlet [Export-CSV](xref:Microsoft.PowerShell.Utility.Export-Csv) e, em seguida, armazena essas informações no `Services.csv` arquivo.

O segundo comando usa [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) para abrir o `services.csv` arquivo no programa associado à `.csv` extensão:

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a>Obtendo arquivos e pastas com atributos especificados

### <a name="get-system-files"></a>Obter arquivos do sistema

Esse comando obtém arquivos do sistema no diretório atual e em seus subdiretórios.

Ele usa o `-File` parâmetro para obter apenas os arquivos (não os diretórios) e o `-System` parâmetro para obter apenas os itens com o atributo "System".

Ele usa o `-Recurse` parâmetro para obter os itens no diretório atual e em todos os subdiretórios.

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a>Obter arquivos ocultos

Esse comando obtém todos os arquivos, inclusive arquivos ocultos, no diretório atual.

Ele usa o parâmetro **Attributes** com dois valores, `!Directory+Hidden` , que obtém arquivos ocultos e `!Directory` , que obtém todos os outros arquivos.

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

`dir -att !d,!d+h` é o equivalente deste comando.

### <a name="get-compressed-and-encrypted-files"></a>Obter arquivos compactados e criptografados

Esse comando obtém os arquivos no diretório atual que são compactados ou criptografados.

Ele usa o `-Attributes` parâmetro com dois valores, `Compressed` e `Encrypted` . Os valores são separados por uma vírgula `,` que representa o operador "or".

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a>Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\>

Especifica a codificação do arquivo. O padrão é ASCII.

- **ASCII** : usa a codificação para o conjunto de caracteres ASCII (7 bits).
- **BigEndianUnicode** : codifica em formato UTF-16 usando a ordem de bytes big-endian.
- **String** : usa o tipo de codificação para uma cadeia de caracteres.
- **Unicode** : codifica no formato UTF-16 usando a ordem de byte little-endian.
- **UTF7** : codifica em formato UTF-7.
- **UTF8** : codifica no formato UTF-8.
- **UTF8BOM** : codifica em formato UTF-8 com marca de ordem de byte (bom)
- **UF8NOBOM** : codifica em formato UTF-8 sem marca de ordem de byte (bom)
- **UTF32** : codifica no formato UTF-32.
- **Padrão** : codifica na página de código padrão instalada.
- **OEM** : usa a codificação padrão para MS-dos e programas de console.
- **Desconhecido** : o tipo de codificação é desconhecido ou inválido. Os dados podem ser tratados como binários.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a>Delimiter \<System.String\>

Especifica o delimitador que o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) usa para dividir o arquivo em objetos enquanto ele lê.

O padrão é `\n` , o caractere de fim de linha.

Ao ler um arquivo de texto, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna uma coleção de objetos String, cada um dos quais termina com o caractere delimitador.

A inserção de um delimitador que não existe no arquivo, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna o arquivo inteiro como um objeto único e não delimitado.

Você pode usar esse parâmetro para dividir um arquivo grande em arquivos menores, especificando um separador de arquivo, como "Final de exemplo," como o delimitador. O delimitador é preservado (não descartado) e se torna o último item em cada seção do arquivo.

> [!NOTE]
> Atualmente, quando o valor do `-Delimiter` parâmetro é uma cadeia de caracteres vazia, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) não retorna nada.
> Este é um problema conhecido. Para forçar o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) a retornar o arquivo inteiro como uma única cadeia de caracteres não delimitada, insira um valor que não existe no arquivo.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a>Wait \<System.Management.Automation.SwitchParameter\>

Aguarda o conteúdo a ser anexado ao arquivo. Se o conteúdo será anexado, ele retorna o conteúdo anexado. Se o conteúdo tiver sido alterado, ele retornará o arquivo inteiro.

Ao aguardar, o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) verifica o arquivo uma vez por segundo até você interrompê-lo, por exemplo, pressionando CTRL + C.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a>Attributes \<FlagsExpression\>

Obtém os arquivos e pastas com os atributos especificados. Esse parâmetro dá suporte a todos os atributos e permite que você especifique combinações complexas de atributos.

O `-Attributes` parâmetro foi introduzido no Windows PowerShell 3,0.

O `-Attributes` parâmetro oferece suporte aos seguintes atributos:

- **Arquivar**
- **Compactado**
- **Dispositivo**
- **Diretório**
- **Criptografado**
- **Oculto**
- **Normal**
- **NotContentIndexed**
- **Está**
- **ReadOnly (somente-leitura)**
- **ReparsePoint**
- **Escassfile**
- **Sistema**
- **Temporário**

Para obter uma descrição desses atributos, consulte a enumeração [FileAttributes](/dotnet/api/system.io.fileattributes) .

Use os seguintes operadores para combinar atributos.

- `!` -Não
- `+` -E
- `,` -OU

Nenhum espaço é permitido entre o operador e seus atributos. No entanto, os espaços são permitidos antes de vírgulas.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a>Directory \<System.Management.Automation.SwitchParameter\>

Obtém os diretórios (pastas).

O `-Directory` parâmetro foi introduzido no Windows PowerShell 3,0.

Para obter apenas os diretórios, use o `-Directory` parâmetro e omita o `-File` parâmetro. Para excluir diretórios, use o `-File` parâmetro e omita o `-Directory` parâmetro ou use o `-Attributes` parâmetro.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a>File \<System.Management.Automation.SwitchParameter\>

Obtém arquivos.

O `-File` parâmetro foi introduzido no Windows PowerShell 3,0.

Para obter apenas arquivos, use o `-File` parâmetro e omita o `-Directory` parâmetro. Para excluir arquivos, use o `-Directory` parâmetro e omita o `-File` parâmetro ou use o `-Attributes` parâmetro.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a>Hidden \<System.Management.Automation.SwitchParameter\>

Obtém somente arquivos ocultos e diretórios (pastas). Por padrão, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) obtém somente itens não ocultos.

O `-Hidden` parâmetro foi introduzido no Windows PowerShell 3,0.

Para obter apenas itens ocultos, use o `-Hidden` parâmetro, `h` seus `ah` aliases ou o valor **oculto** do `-Attributes` parâmetro. Para excluir itens ocultos, omita o `-Hidden` parâmetro ou use o `-Attributes` parâmetro.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a>ReadOnly \<System.Management.Automation.SwitchParameter\>

Obtém somente arquivos somente leitura e diretórios (pastas).

O `-ReadOnly` parâmetro foi introduzido no Windows PowerShell 3,0.

Para obter somente itens somente leitura, use o `-ReadOnly` parâmetro, seu `ar` alias ou o valor **ReadOnly** do `-Attributes` parâmetro. Para excluir itens somente leitura, use o `-Attributes` parâmetro.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a>System \<System.Management.Automation.SwitchParameter\>

Obtém somente os arquivos do sistema e diretórios (pastas).

O `-System` parâmetro foi introduzido no Windows PowerShell 3,0.

Para obter apenas arquivos e pastas do sistema, use o `-System` parâmetro, seu `as` alias ou o valor do **sistema** do `-Attributes` parâmetro. Para excluir arquivos e pastas do sistema, use o `-Attributes` parâmetro.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a>NewerThan \<System.DateTime\>

Retorna `$True` quando o `LastWriteTime` valor de um arquivo é maior que a data especificada. Caso contrário, retornará `$False`.

Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a>OlderThan \<System.DateTime\>

Retorna `$True` quando o `LastWriteTime` valor de um arquivo é menor que a data especificada. Caso contrário, retornará `$False`.

Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a>Stream \<System.String\>

Gerencia o fluxo de dados alternados. Insira o nome do fluxo. Curingas são permitidos somente em [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) para e os comandos [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) em uma unidade do sistema de arquivos.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a>Raw \<SwitchParameter\>

Ignora os caracteres de nova linha. Retorna o conteúdo como um único item.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a>ItemType \<String\>

Esse parâmetro permite especificar o Tye do item a ser criado com `New-Item`

Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.

Em uma `FileSystem` unidade, os seguintes valores são permitidos:

- Arquivo
- Diretório
- SymbolicLink
- Junção
- Real

### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

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
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a>Confira também

[about_Providers](../About/about_Providers.md)
