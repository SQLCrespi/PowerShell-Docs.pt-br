---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: d9adce420ff8904fa40c7689a8b2ab5a3b5e945f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347203"
---
# Get-Acl

## SINOPSE
Obtém o descritor de segurança para um recurso, como um arquivo ou chave do registro.

## SYNTAX

### ByPath (padrão)

```
Get-Acl [[-Path] <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [<CommonParameters>]
```

### ByInputObject

```
Get-Acl -InputObject <PSObject> [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Acl` cmdlet obtém objetos que representam o descritor de segurança de um arquivo ou recurso. O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso. A ACL especifica as permissões que os usuários e grupos de usuários têm para acessar o recurso.

A partir do Windows PowerShell 3,0, você pode usar o parâmetro **InputObject** de `Get-Acl` para obter o descritor de segurança de objetos que não têm um caminho.

## EXEMPLOS

### Exemplo 1-obter uma ACL para uma pasta

Este exemplo obtém o descritor de segurança do `C:\Windows` diretório.

```powershell
Get-Acl C:\Windows
```

### Exemplo 2-obter uma ACL para uma pasta usando curingas

Este exemplo obtém o caminho e o SDDL do PowerShell para todos os `.log` arquivos no `C:\Windows` diretório cujos nomes começam com `s` .

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

O comando usa o `Get-Acl` cmdlet para obter objetos que representam os descritores de segurança de cada arquivo de log. Ele usa um operador de pipeline ( `|` ) para enviar os resultados para o `Format-List` cmdlet. O comando usa o parâmetro **Property** de `Format-List` para exibir somente as propriedades **PSPath** e **SDDL** de cada objeto de descritor de segurança.

As listas geralmente são usadas no PowerShell, porque os valores longos aparecem truncados nas tabelas.

Os valores **SDDL** são importantes para administradores de sistema, porque eles são cadeias de caracteres de texto simples que contêm todas as informações no descritor de segurança. Assim, é fácil que ocorra com eles passar e armazenar, eles que podem ser analisados quando necessário.

### Exemplo 3-obter a contagem de entradas de auditoria para uma ACL

Este exemplo obtém os descritores de segurança dos `.log` arquivos no `C:\Windows` diretório cujos nomes começam com `s` .

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

Ele usa o parâmetro **Audit** para obter os registros de auditoria da SACL no descritor de segurança.
Em seguida, ele usa o `ForEach-Object` cmdlet para contar o número de registros de auditoria associados a cada arquivo. O resultado é uma lista de números que representam o número de registros de auditoria para cada arquivo de log.

### Exemplo 4-obter uma ACL para uma chave do registro

Este exemplo usa o `Get-Acl` cmdlet para obter o descritor de segurança da subchave de controle ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) do registro.

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

O parâmetro **path** especifica a subchave Control. O operador de pipeline ( `|` ) passa o descritor de segurança que `Get-Acl` Obtém o `Format-List` comando, que formata as propriedades do descritor de segurança como uma lista para que sejam fáceis de ler.

### Exemplo 5-obter uma ACL usando **InputObject**

Este exemplo usa o parâmetro **InputObject** de `Get-Acl` para obter o descritor de segurança de um objeto de subsistema de armazenamento.

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## PARAMETERS

### -Auditoria

Obtém os dados de auditoria para o descritor de segurança da lista de controle de acesso do sistema (SACL).

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

### -Excluir

Omite os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

Especifica um filtro no formato ou linguagem do provedor. O valor deste parâmetro qualifica o parâmetro **Path**. A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor. Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao obter os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

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

### -Incluir

Obtém somente os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

### -Path

Especifica o caminho para um recurso. `Get-Acl` Obtém o descritor de segurança do recurso indicado pelo caminho. Caracteres curinga são permitidos. Se você omitir o parâmetro **path** , `Get-Acl` obterá o descritor de segurança do diretório atual.

O nome do parâmetro ("Path") é opcional.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -InputObject

Obtém o descritor de segurança para o objeto especificado. Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.

Não é possível canalizar um objeto, que não seja um caminho, para `Get-Acl` . Em vez disso, use o parâmetro **InputObject** explicitamente no comando.

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para um recurso. Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Este parâmetro é introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-Acl` .

## SAÍDAS

### System. Security. AccessControl. FileSecurity, System. Security. AccessControl. DirectorySecurity, System. Security. AccessControl. RegistrySecurity

`Get-Acl` Retorna um objeto que representa as ACLs que ele obtém. O tipo de objeto depende do tipo da ACL.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Por padrão, `Get-Acl` o exibe o caminho do PowerShell para o recurso ( `<provider>::<resource-path>` ), o proprietário do recurso e "acesso", uma lista (matriz) das entradas de controle de acesso na DACL (lista de controle de acesso discricionário) do recurso. A lista de DACL é controlada pelo proprietário do recurso.

Quando você formata o resultado como uma lista, ( `Get-Acl | Format-List` ), além do caminho, do proprietário e da lista de acesso, o PowerShell exibe as propriedades e os valores de propriedade a seguir:

- **Grupo** : o grupo de segurança do proprietário.
- **Auditoria** : uma lista (matriz) de entradas na SACL (lista de controle de acesso) do sistema. A SACL especifica os tipos de tentativas de acesso para as quais o Windows gera registros de auditoria.
- **SDDL** : o descritor de segurança do recurso exibido em uma única cadeia de texto no formato de linguagem de definição do descritor de segurança. O PowerShell usa o método **GetSddlForm** de descritores de segurança para obter esses dados.

Como `Get-Acl` o é compatível com o sistema de arquivos e os provedores de registro, você pode usar `Get-Acl` o para exibir a ACL de objetos do sistema de arquivos, como arquivos e diretórios e objetos do registro, como chaves e entradas do registro.

## LINKS RELACIONADOS

[Set-Acl](Set-Acl.md)
