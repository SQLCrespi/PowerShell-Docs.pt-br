---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: f24988833faaf56395b95e08430bbcc9fb6d2746
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193059"
---
# New-Item

## SINOPSE
Cria um novo item.

## SYNTAX

### caminhoset (padrão)

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### nome do

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `New-Item` cmdlet cria um novo item e define seu valor. Os tipos de itens que podem ser criados dependem do local do item. Por exemplo, no sistema de arquivos, o `New-Item` cria arquivos e pastas. No registro, o `New-Item` cria chaves e entradas do registro.

`New-Item` também pode definir o valor dos itens que ele cria. Por exemplo, quando ele cria um novo arquivo, o `New-Item` pode adicionar conteúdo inicial ao arquivo.

## EXEMPLOS

### Exemplo 1: criar um arquivo no diretório atual

Esse comando cria um arquivo de texto chamado "testfile1.txt" no diretório atual. O ponto ('. ') no valor do parâmetro **path** indica o diretório atual. O texto entre aspas que segue o parâmetro de **valor** é adicionado ao arquivo como conteúdo.

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### Exemplo 2: criar um diretório

Esse comando cria um diretório chamado "LogFiles" na `C:` unidade. O parâmetro **ItemType** especifica que o novo item é um diretório, não um arquivo ou outro objeto do sistema de arquivos.

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### Exemplo 3: criar um perfil

Esse comando cria um perfil do PowerShell no caminho especificado pela `$profile` variável.

Você pode usar perfis para personalizar o PowerShell. `$profile` é uma variável automática (interna) que armazena o caminho e o nome de arquivo do perfil "CurrentUser/CurrentHost". Por padrão, o perfil não existe, mesmo que o PowerShell armazene um caminho e um nome de arquivo para ele.

Nesse comando, a `$profile` variável representa o caminho do arquivo. O parâmetro **ItemType** especifica que o comando cria um arquivo. O parâmetro **Force** permite criar um arquivo no caminho do perfil, mesmo quando os diretórios no caminho não existem.

Depois de criar um perfil, você pode inserir aliases, funções e scripts no perfil para personalizar o Shell.

Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) e [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### Exemplo 4: criar um diretório em um diretório diferente

Este exemplo cria um novo diretório de scripts no diretório "C:\PS-Test".

O nome do novo item de diretório, "scripts", é incluído no valor do parâmetro **path** , em vez de ser especificado no valor de **Name** . Conforme indicado pela sintaxe, ambos os formatos de comando são válidos.

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### Exemplo 5: criar vários arquivos

Este exemplo cria arquivos em dois diretórios diferentes. Como o **caminho** usa várias cadeias de caracteres, você pode usá-lo para criar vários itens.

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### Exemplo 6: usar curingas para criar arquivos em vários diretórios

O `New-Item` cmdlet dá suporte a curingas no parâmetro **Path** . O comando a seguir cria um `temp.txt` arquivo em todos os diretórios especificados pelos curingas no parâmetro **Path** .

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

O `Get-ChildItem` cmdlet mostra três diretórios sob o `C:\Temp` diretório. Usando curingas o `New-Item` cmdlet cria um `temp.txt` arquivo em todos os diretórios no diretório atual. O `New-Item` cmdlet gera os itens que você criou, que é canalizado para `Select-Object` para verificar os caminhos dos arquivos recém-criados.

### Exemplo 7: criar um link simbólico para um arquivo ou pasta

Este exemplo cria um link simbólico para o arquivo de Notice.txt na pasta atual.

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

Neste exemplo, **target** é um alias para o parâmetro **Value** . O destino do link simbólico pode ser um caminho relativo. Antes do PowerShell v 6.2, o destino deve ser um caminho totalmente qualificado.

> [!CAUTION]
> Se você estiver criando um **SymbolicLink** para uma pasta no Windows, deverá usar um caminho totalmente qualificado. Se você usar um caminho relativo, o link será criado como um link de tipo de arquivo em vez de um link de tipo de diretório.

### Exemplo 8: usar o parâmetro-Force para tentar recriar pastas

Este exemplo cria uma pasta com um arquivo dentro de. Em seguida, o tenta criar a mesma pasta usando `-Force` . Ele não substituirá a pasta, mas simplesmente retornará o objeto de pasta existente com o arquivo criado intacto.

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### Exemplo 9: usar o parâmetro-Force para substituir os arquivos existentes

Este exemplo cria um arquivo com um valor e, em seguida, recria o arquivo usando `-Force` . Isso substitui o arquivo existente e perderá seu conteúdo como você pode ver pela propriedade Length

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> Ao usar `New-Item` com a `-Force` opção para criar chaves do registro, o comando se comportará da mesma forma que ao substituir um arquivo. Se a chave do registro já existir, a chave e todos os valores e propriedades serão substituídos por uma chave do registro vazia.

## PARAMETERS

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell. Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use `Invoke-Command` .

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

### -Force

Força este cmdlet a criar um item que grava em um item somente leitura existente. A implementação varia de provedor para provedor. Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.

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

### -ItemType

Especifica o tipo de provedor especificado do novo item. Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.

Se o local estiver em uma `FileSystem` unidade, os seguintes valores serão permitidos:

- Arquivo
- Diretório
- SymbolicLink
- Junção
- Real

> [!NOTE]
> A criação de um `SymbolicLink` tipo no Windows requer elevação como administrador. No entanto, o Windows 10 (Build 14972 ou mais recente) com o modo de desenvolvedor habilitado não requer mais a elevação da criação de links simbólicos.

Em uma `Certificate` unidade, esses são os valores que você pode especificar:

- Provedor Certificate
- Certificado
- Repositório
- StoreLocation

Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica o nome do novo item. Você pode especificar o nome do novo item no valor do parâmetro **Name** ou **Path** e pode especificar o caminho do novo item no **nome** ou no valor do **caminho** . Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho do local do novo item. O padrão é o local atual quando o **caminho** é omitido. Você pode especificar o nome do novo item no **nome** ou incluí-lo no **caminho** . Os nomes de itens passados usando o parâmetro **Name** são criados em relação ao valor do parâmetro **Path** .

Para esse cmdlet, o parâmetro **path** funciona como o parâmetro **LiteralPath** de outros cmdlets.
Os caracteres curinga não são interpretados. Todos os caracteres são passados para o provedor do local. O provedor pode não dar suporte a todos os caracteres. Por exemplo, você não pode criar um nome de arquivo que contenha um caractere de asterisco ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Especifica o valor do novo item. Você também pode canalizar um valor para `New-Item` .

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Object

É possível canalizar um valor para o novo item para esse cmdlet.

## SAÍDAS

### System.Object

Esse cmdlet retorna o item que ele cria.

## OBSERVAÇÕES

`New-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
