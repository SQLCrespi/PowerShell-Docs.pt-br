---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: c29a938fc73b8b69ea1bbf96f12f5d42d16f79bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194749"
---
# Get-ChildItem

## SINOPSE

Obtém os itens e os itens filhos de um ou mais locais especificados.

## SYNTAX

### Itens (padrão)

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### LiteralItems

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## DESCRIPTION

O `Get-ChildItem` cmdlet obtém os itens em um ou mais locais especificados. Se o item for um contêiner, ele obtém os itens dentro do contêiner, conhecidos como itens filho. Você pode usar o parâmetro **recurse** para obter itens em todos os contêineres filho e usar o parâmetro **Depth** para limitar o número de níveis para recurse.

`Get-ChildItem` não exibe diretórios vazios. Quando um `Get-ChildItem` comando inclui os parâmetros **Depth** ou **recurse** , os diretórios vazios não são incluídos na saída.

Os locais são expostos aos `Get-ChildItem` provedores do PowerShell. Um local pode ser um diretório do sistema de arquivos, hive do registro ou um repositório de certificados. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## EXEMPLOS

### Exemplo 1: obter itens filho de um diretório do sistema de arquivos

Este exemplo obtém os itens filho de um diretório do sistema de arquivos. Os nomes de filename e de subdiretório são exibidos. Para locais vazios, o comando não retorna nenhuma saída e retorna ao prompt do PowerShell.

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test` .
`Get-ChildItem` exibe os arquivos e diretórios no console do PowerShell.

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

Por padrão `Get-ChildItem` , lista o modo **(atributos** ), **LastWriteTime** , tamanho do arquivo ( **comprimento** ) e o **nome** do item. As letras na propriedade **modo** podem ser interpretadas da seguinte maneira:

- `l` criar
- `d` active
- `a` operação
- `r` (somente leitura)
- `h` oculto
- `s` (sistema).

Para obter mais informações sobre os sinalizadores de modo, consulte [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).

### Exemplo 2: obter nomes de item filho em um diretório

Este exemplo lista somente os nomes de itens em um diretório.

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test` . O parâmetro **Name** retorna somente os nomes de arquivo ou diretório do caminho especificado.

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### Exemplo 3: obter itens filho no diretório e nos subdiretórios atuais

Este exemplo exibe os arquivos **. txt** que estão localizados no diretório atual e seus subdiretórios.

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar `C:\Test\*.txt` . O **caminho** usa o curinga asterisco ( `*` ) para especificar todos os arquivos com a extensão de nome de arquivo `.txt` . O parâmetro **recurse** pesquisa o diretório **Path** em seus subdiretórios, conforme mostrado no **diretório:** cabeçalhos. O parâmetro **Force** exibe arquivos ocultos, como `hiddenfile.txt` que têm um modo de **h** .

### Exemplo 4: obter itens filho usando o parâmetro include

Neste exemplo `Get-ChildItem` , usa o parâmetro **include** para localizar itens específicos do diretório especificado pelo parâmetro **Path** .

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório **C:\test** . O parâmetro **path** inclui um curinga asterisco ( `*` ) à direita para especificar o conteúdo do diretório.
O parâmetro **include** usa um curinga asterisco ( `*` ) para especificar todos os arquivos com a extensão de nome de arquivo **. txt** .

Quando o parâmetro **include** é usado, o parâmetro **Path** precisa de um curinga asterisco ( `*` ) à direita para especificar o conteúdo do diretório. Por exemplo, `-Path C:\Test\*`.

- Se o parâmetro **recurse** for adicionado ao comando, o asterisco à direita ( `*` ) no parâmetro **Path** será opcional. O parâmetro **recurse** Obtém os itens do diretório **Path** e seus subdiretórios. Por exemplo, `-Path C:\Test\ -Recurse -Include *.txt`
- Se um asterisco à direita ( `*` ) não estiver incluído no parâmetro **Path** , o comando não retornará nenhuma saída e retornará ao prompt do PowerShell. Por exemplo, `-Path C:\Test\`.

### Exemplo 5: obter itens filhos usando o parâmetro Exclude

A saída do exemplo mostra o conteúdo do diretório **C:\Test\Logs** . A saída é uma referência para os outros comandos que usam os parâmetros **Exclude** e **recurse** .

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test\Logs` .
O parâmetro **Exclude** usa o curinga asterisco ( `*` ) para especificar os arquivos ou diretórios que começam com **um** ou **um** são excluídos da saída.

Quando o parâmetro **Exclude** é usado, um asterisco à direita ( `*` ) no parâmetro **Path** é opcional. Por exemplo, `-Path C:\Test\Logs` ou `-Path C:\Test\Logs\*`.

- Se um asterisco à direita ( `*` ) não estiver incluído no parâmetro **Path** , o conteúdo do parâmetro **Path** será exibido. As exceções são nomes de filename ou subdiretórios que correspondem ao valor do parâmetro **Exclude** .
- Se um asterisco à direita ( `*` ) estiver incluído no parâmetro **Path** , o comando recursivamente nos subdiretórios do parâmetro **Path** . As exceções são nomes de filename ou subdiretórios que correspondem ao valor do parâmetro **Exclude** .
- Se o parâmetro **recurse** for adicionado ao comando, a saída de recursão será a mesma se o parâmetro **Path** incluir um asterisco à direita ( `*` ).

### Exemplo 6: obter as chaves do registro de um hive do registro

Este exemplo obtém todas as chaves do registro de `HKEY_LOCAL_MACHINE\HARDWARE` .

`Get-ChildItem` usa o parâmetro **path** para especificar a chave do registro `HKLM:\HARDWARE` . O caminho do hive e o nível superior das chaves do registro são exibidos no console do PowerShell.

Para obter mais informações, consulte [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

O primeiro comando mostra o conteúdo da `HKLM:\HARDWARE` chave do registro. O parâmetro **Exclude** informa `Get-ChildItem` para não retornar nenhuma subchave que comece com `D*` . Atualmente, o parâmetro **Exclude** só funciona em subchaves, não em Propriedades de item.

### Exemplo 7: obter todos os certificados com autoridade de assinatura de código

Este exemplo obtém cada certificado na unidade de **certificado** do PowerShell: que tem autoridade de assinatura de código.

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o **CERT:** Provider. O parâmetro **recurse** pesquisa o diretório especificado por **Path** e seus subdiretórios. O parâmetro **CodeSigningCert** obtém somente os certificados que têm autoridade de assinatura de código.

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

Para obter mais informações sobre o provedor de certificado e a unidade CERT:, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Exemplo 8: obter itens usando o parâmetro Depth

Este exemplo exibe os itens em um diretório e seus subdiretórios. O parâmetro **Depth** determina o número de níveis de subdiretório a serem incluídos na recursão. Diretórios vazios são excluídos da saída.

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar **C:\Parent** . O parâmetro **Depth** especifica dois níveis de recursão. `Get-ChildItem` exibe o conteúdo do diretório especificado pelo parâmetro **path** e os dois níveis de subdiretórios.

### Exemplo 9: obtendo informações de vínculo físico

No PowerShell 6,2, uma exibição alternativa foi adicionada para obter informações de link físico.

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

### Exemplo 9: saída para o recurso experimental PSUnixFileStat

No PowerShell 7 em sistemas UNIX, o recurso experimental **PSUnixFileStat** fornece saída do tipo UNIX:

```powershell
PS> Get-ChildItem /etc/r*
```

```Output
    Directory: /etc

UnixMode   User Group    LastWriteTime Size Name
--------   ---- -----    ------------- ---- ----
drwxr-xr-x root wheel  9/30/2019 19:19  128 racoon
-rw-r--r-- root wheel  9/26/2019 18:20 1560 rc.common
-rw-r--r-- root wheel  7/31/2017 17:30 1560 rc.common~previous
-rw-r--r-- root wheel  9/27/2019 20:34 5264 rc.netboot
lrwxr-xr-x root wheel  11/8/2019 15:35   22 resolv.conf -> /private/var/run/resolv.conf
-rw-r--r-- root wheel 10/23/2019 17:41    0 rmtab
-rw-r--r-- root wheel 10/23/2019 17:41 1735 rpc
-rw-r--r-- root wheel  7/25/2017 18:37 1735 rpc~previous
-rw-r--r-- root wheel 10/23/2019 18:42  891 rtadvd.conf
-rw-r--r-- root wheel  8/24/2017 21:54  891 rtadvd.conf~previous
```

As novas propriedades que agora fazem parte da saída são:

- **Unixmode** são as permissões de arquivo, conforme representado em um sistema UNIX
- O **usuário** é o proprietário do arquivo
- O **grupo** é o proprietário do grupo
- **Tamanho** é o tamanho do arquivo ou diretório, conforme representado em um sistema UNIX

## Parâmetros

### -Atributos

Obtém os arquivos e pastas com os atributos especificados. Esse parâmetro dá suporte a todos os atributos e permite que você especifique combinações complexas de atributos.

Por exemplo, para obter arquivos de fora do sistema (não diretórios) que sejam criptografados ou compactados, digite:

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

Para localizar arquivos e pastas com atributos comumente usados, use o parâmetro **Attributes** . Ou, o **diretório** de parâmetros, **arquivo** , **oculto** , **ReadOnly** e **System** .

O parâmetro **Attributes** dá suporte às seguintes propriedades:

- **Arquivar**
- **Compactado**
- **Dispositivo**
- **Diretório**
- **Criptografado**
- **Oculto**
- **IntegrityStream**
- **Normal**
- **NoScrubData**
- **NotContentIndexed**
- **Está**
- **ReadOnly (somente-leitura)**
- **ReparsePoint**
- **Escassfile**
- **Sistema**
- **Temporário**

Para obter uma descrição desses atributos, consulte a [enumeração FileAttributes](/dotnet/api/system.io.fileattributes).

Para combinar atributos, use os seguintes operadores:

- `!` VÁLIDO
- `+` E
- `,` OR

Não use espaços entre um operador e seu atributo. Os espaços são aceitos após vírgulas.

Para atributos comuns, use as seguintes abreviações:

- `D` Active
- `H` Oculto
- `R` (Somente leitura)
- `S` Sistema

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profundidade

Esse parâmetro foi adicionado no PowerShell 5,0 e permite que você controle a profundidade da recursão. Por padrão, `Get-ChildItem` o exibe o conteúdo do diretório pai. O parâmetro **Depth** determina o número de níveis de subdiretório que são incluídos na recursão e exibe o conteúdo.

Por exemplo, `Depth 2` inclui o diretório do parâmetro de **caminho** , o primeiro nível de subdiretórios e o segundo nível de subdiretórios. Por padrão, os nomes do diretório e os nomes de FileName são incluídos na saída.

> [!NOTE]
> Em um computador Windows do PowerShell ou **cmd.exe** , você pode exibir uma exibição gráfica de uma estrutura de diretório com o comando **Tree.com** .

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Directory

Para obter uma lista de diretórios, use o parâmetro **Directory** ou o parâmetro **Attributes** com a propriedade **Directory** . Você pode usar o parâmetro **recurse** com o **diretório** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, uma propriedade ou propriedade que esse cmdlet exclui da operação.
O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `*.txt` ou `A*` . Caracteres curinga são aceitos.

Um asterisco à direita ( `*` ) no parâmetro **Path** é opcional. Por exemplo, `-Path C:\Test\Logs` ou `-Path C:\Test\Logs\*`. Se um asterisco à direita ( `*` ) for incluído, o comando recursivamente nos subdiretórios do parâmetro de **caminho** . Sem o asterisco ( `*` ), o conteúdo do parâmetro **Path** é exibido. Mais detalhes são incluídos no exemplo 5 e na seção observações.

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

### -File

Para obter uma lista de arquivos, use o parâmetro **File** . Você pode usar o parâmetro **recurse** com o **arquivo** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Especifica um filtro para qualificar o parâmetro **path** . O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros. Os filtros são mais eficientes do que outros parâmetros. O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados. A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos. A API só dá suporte a `*` `?` caracteres curinga e.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -FollowSymlink

Por padrão, o `Get-ChildItem` cmdlet exibe links simbólicos para diretórios encontrados durante a recursão, mas não os recursiva. Use o parâmetro **FollowSymlink** para pesquisar os diretórios direcionados a esses links simbólicos. O **FollowSymlink** é um parâmetro dinâmico e só tem suporte no provedor **FileSystem** .

Esse parâmetro foi introduzido no PowerShell 6,0.

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

### -Force

Permite que o cmdlet obtenha itens que, de outra forma, não podem ser acessados pelo usuário, como arquivos ocultos ou do sistema. O parâmetro **Force** não substitui as restrições de segurança. A implementação varia entre os provedores. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hidden

Para obter apenas itens ocultos, use o parâmetro **Hidden** ou o parâmetro **Attributes** com a propriedade **Hidden** . Por padrão, o `Get-ChildItem` não exibe itens ocultos. Use o parâmetro **Force** para obter itens ocultos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `"*.txt"` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

### -LiteralPath

Especifica um caminho para um ou mais locais. O valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Obtém somente os nomes dos itens no local. A saída é um objeto de cadeia de caracteres que pode ser enviado ao pipeline para outros comandos. Caracteres curinga são permitidos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Especifica um caminho para um ou mais locais. Caracteres curinga são aceitos. O local padrão é o diretório atual ( `.` ).

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ReadOnly

Para obter somente itens somente leitura, use o parâmetro **ReadOnly** ou a propriedade **ReadOnly** do parâmetro **Attributes** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Obtém os itens nos locais especificados e em todos os itens filhos dos locais.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -System

Obtém somente os arquivos e diretórios do sistema. Para obter apenas arquivos e pastas do sistema, use o parâmetro do **sistema** ou a propriedade do **sistema** de parâmetros de **atributos** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ChildItem` .

## SAÍDAS

### System.Object

O tipo de objeto que `Get-ChildItem` retorna é determinado pelos objetos no caminho da unidade do provedor.

### System.String

Se você usar o parâmetro **Name** , `Get-ChildItem` o retornará os nomes de objeto como cadeias de caracteres.

## OBSERVAÇÕES

- `Get-ChildItem` pode ser executado usando qualquer um dos aliases internos, `ls` , `dir` , e `gci` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Get-ChildItem` não obtém itens ocultos por padrão. Para obter itens ocultos, use o parâmetro **Force** .
- O `Get-ChildItem` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .
  Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Alias](../Microsoft.PowerShell.Utility/Get-Alias.md)

[Get-Item](Get-Item.md)

[Get-Location](Get-Location.md)

[Get-Process](Get-Process.md)

[Get-PSProvider](Get-PSProvider.md)

[Split-Path](Split-Path.md)

