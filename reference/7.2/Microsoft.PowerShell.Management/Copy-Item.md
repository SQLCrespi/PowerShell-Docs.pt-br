---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: ee2d8b8a3b736a59b5af4a81710a0d29dd2238d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597201"
---
# Copy-Item

## SINOPSE
Copia um item de um local para outro.

## SYNTAX

### Caminho (padrão)

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### LiteralPath

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## DESCRIPTION

O `Copy-Item` cmdlet copia um item de um local para outro local no mesmo namespace.
Por exemplo, ele pode copiar um arquivo para uma pasta, mas não pode copiar um arquivo para uma unidade de certificado.

Esse cmdlet não recorta nem exclui os itens que estão sendo copiados. Os itens específicos que o cmdlet pode copiar dependem do provedor do PowerShell que expõe o item. Por exemplo, ele pode copiar arquivos e diretórios em uma unidade do sistema de arquivos e chaves do registro e entradas na unidade do registro.

Esse cmdlet pode copiar e renomear itens no mesmo comando. Para renomear um item, insira o novo nome no valor do parâmetro de **destino** . Para renomear um item e não copiá-lo, use o `Rename-Item` cmdlet.

## EXEMPLOS

### Exemplo 1: copiar um arquivo para o diretório especificado

Este exemplo copia o `mar1604.log.txt` arquivo para o `C:\Presentation` diretório. O arquivo original não é excluído.

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### Exemplo 2: copiar o conteúdo do diretório para um diretório existente

Este exemplo copia o conteúdo do `C:\Logfiles` diretório para o diretório existente `C:\Drawings` . O `Logfiles` diretório não é copiado.

Se o `Logfiles` diretório contiver arquivos em subdiretórios, esses subdiretórios serão copiados com suas árvores de arquivo intactas. Por padrão, o parâmetro de **contêiner** é definido como **true**, o que preserva a estrutura de diretórios.

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> Se você precisar incluir o `Logfiles` diretório na cópia, remova o `\*` do **caminho**.
> Por exemplo:
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### Exemplo 3: copiar diretório e conteúdo para um novo diretório

Este exemplo copia o conteúdo do `C:\Logfiles` diretório de origem e cria um novo diretório de destino. O novo diretório de destino, `\Logs` é criado no `C:\Drawings` .

Para incluir o nome do diretório de origem, copie para um diretório de destino existente, conforme mostrado no **exemplo 2**. Ou, nomeie o novo diretório de destino com o mesmo diretório de origem.

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> Se o **caminho** incluir `\*` , todo o conteúdo do arquivo do diretório, incluindo as árvores de subdiretórios, será copiado para o novo diretório de destino. Por exemplo:
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### Exemplo 4: copiar um arquivo para o diretório especificado e renomear o arquivo

Este exemplo usa o `Copy-Item` cmdlet para copiar o `Get-Widget.ps1` script do `\\Server01\Share` diretório para o `\\Server12\ScriptArchive` diretório. Como parte da operação de cópia, o comando altera o nome do item de `Get-Widget.ps1` para `Get-Widget.ps1.txt` , para que ele possa ser anexado a mensagens de email.

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### Exemplo 5: copiar um arquivo para um computador remoto

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia `test.log` da `D:\Folder001` pasta para a `C:\Folder001_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável. O arquivo original não é excluído.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### Exemplo 6: copiar uma pasta para um computador remoto

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia a `D:\Folder002` pasta para o `C:\Folder002_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável. Todas as subpastas ou arquivos não são copiados sem usar a opção **recurse** .
A operação criará a `Folder002_Copy` pasta se ela ainda não existir.

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### Exemplo 7: copiar recursivamente todo o conteúdo de uma pasta para um computador remoto

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia todo o conteúdo da `D:\Folder003` pasta para o `C:\Folder003_Copy` diretório no computador remoto usando as informações de sessão armazenadas na `$Session` variável. As subpastas são copiadas com suas árvores de arquivo intactas. A operação criará a `Folder003_Copy` pasta se ela ainda não existir.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### Exemplo 8: copiar um arquivo para um computador remoto e, em seguida, renomear o arquivo

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia `scriptingexample.ps1` da `D:\Folder004` pasta para a `C:\Folder004_Copy` pasta no computador remoto usando as informações de sessão armazenadas na `$Session` variável. Como parte da operação de cópia, o comando altera o nome do item de `scriptingexample.ps1` para `scriptingexample_copy.ps1` , para que ele possa ser anexado a mensagens de email. O arquivo original não é excluído.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### Exemplo 9: copiar um arquivo remoto para o computador local

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia `test.log` do controle remoto `C:\MyRemoteData\` para a `D:\MyLocalData` pasta local usando as informações de sessão armazenadas na `$Session` variável. O arquivo original não é excluído.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Exemplo 10: copiar todo o conteúdo de uma pasta remota para o computador local

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData` usando as informações de sessão armazenadas na `$Session` variável. Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Exemplo 11: copiar recursivamente todo o conteúdo de uma pasta remota para o computador local

Uma sessão é criada para o computador remoto chamado **SERVER01** com a credencial de `Contoso\User01` e armazena os resultados na variável chamada `$Session` .

O `Copy-Item` cmdlet copia todo o conteúdo da pasta remota `C:\MyRemoteData\scripts` para a pasta local `D:\MyLocalData\scripts` usando as informações de sessão armazenadas na `$Session` variável. Como o parâmetro **recurse** é usado, a operação cria a pasta scripts, caso ela ainda não exista. Se a pasta scripts contiver arquivos em subpastas, essas subpastas serão copiadas com suas árvores de arquivo intactas.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### Exemplo 12: copiar arquivos recursivamente de uma árvore de pastas para a pasta atual

Este exemplo mostra como copiar arquivos de uma estrutura de pasta de vários níveis em uma única pasta simples.
Os três primeiros comandos mostram a estrutura de pastas existente e o conteúdo de dois arquivos, ambos os nomes `file3.txt` .

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

O `Copy-Item` cmdlet tem o parâmetro de **contêiner** definido como `$false` . Isso faz com que o conteúdo da pasta de origem seja copiado, mas não preserva a estrutura de pastas. Observe que os arquivos com o mesmo nome são substituídos na pasta de destino.

## PARAMETERS

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Contêiner

Indica que esse cmdlet preserva objetos de contêiner durante a operação de cópia. Por padrão, o parâmetro de **contêiner** é definido como **true**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
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

### -Destino

Especifica o caminho para o local de destino. O padrão é o diretório atual.

Para renomear o item que está sendo copiado, especifique um novo nome no valor do parâmetro de **destino** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Excluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos. O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

Especifica um filtro para qualificar o parâmetro **path** . O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros. Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

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

Indica que esse cmdlet copia itens que não podem ser alterados de outra forma, como copiar por um arquivo somente leitura ou alias.

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

### -FromSession

Especifica o objeto **PSSession** do qual um arquivo remoto está sendo copiado. Quando você usa esse parâmetro, os parâmetros **Path** e **LiteralPath** referem-se ao caminho local no computador remoto.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Incluir

Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `"*.txt"` . Caracteres curinga são permitidos. O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.

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

### -PassThru

Retorna um objeto que representa o item com o qual você está trabalhando. Por padrão, esse cmdlet não gera nenhuma saída.

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

### -Path

Especifica, como uma matriz de cadeia de caracteres, o caminho para os itens a serem copiados. Caracteres curinga são permitidos.

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

### -Recurse

Indica que esse cmdlet faz uma cópia recursiva.

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

### -Tosession

Especifica o objeto **PSSession** ao qual um arquivo remoto está sendo copiado. Quando você usa esse parâmetro, o parâmetro de **destino** refere-se ao caminho local no computador remoto.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.

## SAÍDAS

### Nenhum ou um objeto que representa o item copiado

Quando você usa o parâmetro **PassThru** , esse cmdlet retorna um objeto que representa o item copiado. Caso contrário, esse cmdlet não gerará nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Item](Clear-Item.md)

[Get-Item](Get-Item.md)

[Get-PSProvider](Get-PSProvider.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

