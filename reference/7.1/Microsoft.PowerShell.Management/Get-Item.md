---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 25d07028430d6ad6719136bd484d39e116d81516
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194434"
---
# Get-Item

## SINOPSE
Obtém o item no local especificado.

## SYNTAX

### Caminho (padrão)

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### LiteralPath

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Item` cmdlet obtém o item no local especificado. Ele não obtém o conteúdo do item no local, a menos que você use um caractere curinga ( `*` ) para solicitar todo o conteúdo do item.

Esse cmdlet é usado pelos provedores do PowerShell para navegar por diferentes tipos de armazenamentos de dados.

## EXEMPLOS

### Exemplo 1: obter o diretório atual

Este exemplo obtém o diretório atual. O ponto ('. ') representa o item no local atual (não seu conteúdo).

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### Exemplo 2: obter todos os itens no diretório atual

Este exemplo obtém todos os itens no diretório atual. O caractere curinga ( `*` ) representa todo o conteúdo do item atual.

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### Exemplo 3: obter o diretório atual de uma unidade

Este exemplo obtém o diretório atual da `C:` unidade. O objeto recuperado representa somente o diretório, e não o seu conteúdo.

```powershell
Get-Item C:\
```

### Exemplo 4: obter itens na unidade especificada

Este exemplo obtém os itens na `C:` unidade. O caractere curinga ( `*` ) representa todos os itens no contêiner, não apenas o contêiner.

```powershell
Get-Item C:\*
```

No PowerShell, use um único asterisco ( `*` ) para obter o conteúdo, em vez do tradicional `*.*` . O formato é interpretado literalmente, portanto, não `*.*` recuperaria diretórios ou nomes de FileName sem um ponto.

### Exemplo 5: obter uma propriedade no diretório especificado

Este exemplo obtém a propriedade **LastAccessTime** do `C:\Windows` diretório. **LastAccessTime** é apenas uma propriedade dos diretórios do sistema de arquivos. Para ver todas as propriedades de um diretório, digite `(Get-Item <directory-name>) | Get-Member` .

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### Exemplo 6: mostrar o conteúdo de uma chave do registro

Este exemplo mostra o conteúdo da chave do registro **Microsoft. PowerShell** . Você pode usar esse cmdlet com o provedor de registro do PowerShell para obter chaves e subchaves do registro, mas você deve usar o `Get-ItemProperty` cmdlet para obter os valores e os dados do registro.

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### Exemplo 7: obter itens em um diretório que tem uma exclusão

Este exemplo obtém os itens no diretório do Windows com nomes que incluem um ponto ( `.` ), mas não comece com `w*` . Este exemplo só funciona quando o caminho inclui um caractere curinga ( `*` ) para especificar o conteúdo do item.

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### Exemplo 8: obtendo informações de hardlink

No PowerShell 6,2, uma exibição alternativa foi adicionada para obter informações de hardlink. Para obter as informações de hardlink, redirecione a saída para `Format-Table -View childrenWithHardlink`

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### Exemplo 9: saída para o recurso experimental PSUnixFileStat

No PowerShell 7 em sistemas UNIX, o recurso experimental **PSUnixFileStat** fornece saída do tipo UNIX:

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

As novas propriedades que agora fazem parte da saída são:

- **Unixmode** são as permissões de arquivo, conforme representado em um sistema UNIX
- O **usuário** é o proprietário do arquivo
- O **grupo** é o proprietário do grupo
- **Tamanho** é o tamanho do arquivo ou diretório, conforme representado em um sistema UNIX

## PARAMETERS

### -Fluxo

Obtém o fluxo de arquivos NTFS alternativo especificado do arquivo. Insira o nome do fluxo. Há suporte para caracteres curinga. Para obter todos os fluxos, use um asterisco ( `*` ). Esse parâmetro não é válido em pastas.

**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Item` cmdlet.
Esse parâmetro funciona somente em unidades de sistema de arquivos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.
> Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos. O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

### -Filter

Especifica um filtro para qualificar o parâmetro **path** . O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros. Os filtros são mais eficientes do que outros parâmetros. O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados. A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos. A API só dá suporte a `*` `?` caracteres curinga e.

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

### -Force

Indica que esse cmdlet obtém os itens que não podem ser acessados de outra forma, como itens ocultos.
A implementação varia de provedor para provedor. Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md). Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.

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

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho para um item. Esse cmdlet obtém o item no local especificado. Caracteres curinga são permitidos. Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.

Use um ponto ( `.` ) para especificar o local atual. Use o caractere curinga ( `*` ) para especificar todos os itens no local atual.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.

## SAÍDAS

### System.Object

Esse cmdlet retorna os objetos que ele obtém. O tipo é determinado pelo tipo de objetos no caminho.

## OBSERVAÇÕES

Esse cmdlet não tem um parâmetro **recurse** , pois ele obtém apenas um item, não seu conteúdo.
Para obter o conteúdo de um item recursivamente, use `Get-ChildItem` .

Para navegar pelo registro, use este cmdlet para obter chaves do registro e `Get-ItemProperty` para obter valores e dados do registro. Os valores do registro são considerados propriedade da chave do registro.
  
Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Get-PSProvider](Get-PSProvider.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

