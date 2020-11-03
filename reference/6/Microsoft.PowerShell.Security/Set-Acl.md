---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: 0f5757d7e9fb2615149fd08473685491bfccada7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194538"
---
# Set-Acl

## SINOPSE
Altera o descritor de segurança de um item especificado, como um arquivo ou chave do registro.

## SYNTAX

### ByPath (padrão)

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Acl` cmdlet altera o descritor de segurança de um item especificado, como um arquivo ou uma chave do registro, para corresponder aos valores em um descritor de segurança fornecido por você.

Para usar `Set-Acl` , use o **caminho** ou o parâmetro **InputObject** para identificar o item cujo descritor de segurança você deseja alterar. Em seguida, use os parâmetros **AclObject** ou **SecurityDescriptor** para fornecer um descritor de segurança com os valores que deseja aplicar. `Set-Acl` aplica o descritor de segurança fornecido. Ele usa o valor do parâmetro **AclObject** como um modelo e altera os valores no descritor de segurança do item para que correspondam aos valores do parâmetro **AclObject** .

## EXEMPLOS

### Exemplo 1: copiar um descritor de segurança de um arquivo para outro

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

Esse comando copia os valores do descritor de segurança do arquivo Dog.txt para o descritor de segurança do arquivo Cat.txt. Quando os comandos forem concluídos, os descritores de segurança dos arquivos Dog.txt e Cat.txt serão idênticos.

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.
O operador de atribuição ( `=` ) armazena o descritor de segurança no valor da variável $DogACL.

O segundo comando usa `Set-Acl` para alterar os valores na ACL de Cat.txt para os valores em `$DogACL` .

O valor do parâmetro **Path** é o caminho para o arquivo Cat.txt. O valor do parâmetro **AclObject** é a ACL de modelo, nesse caso, a acl de Dog.txt como salva na `$DogACL` variável.

### Exemplo 2: usar o operador de pipeline para passar um descritor

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

Esse comando é quase o mesmo que o comando no exemplo anterior, exceto pelo fato de que ele usa um operador de pipeline ( `|` ) para enviar o descritor de segurança de um `Get-Acl` comando para um `Set-Acl` comando.

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt. O operador de pipeline ( `|` ) passa um objeto que representa o descritor de segurança Dog.txt para o `Set-Acl` cmdlet.

O segundo comando usa `Set-Acl` para aplicar o descritor de segurança do Dog.txt ao Cat.txt.
Quando o comando for concluído, as ACLs dos arquivos Dog.txt e Cat.txt serão idênticas.

### Exemplo 3: aplicar um descritor de segurança a vários arquivos

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

Esses comandos aplicam os descritores de segurança no arquivo de File0.txt a todos os arquivos de texto no `C:\Temp` diretório e em todos os seus subdiretórios.

O primeiro comando obtém o descritor de segurança do arquivo de File0.txt no diretório atual e usa o operador de atribuição ( `=` ) para armazená-lo na `$NewACL` variável.

O primeiro comando no pipeline usa o cmdlet Get-ChildItem para obter todos os arquivos de texto no `C:\Temp` diretório. O parâmetro **recurse** estende o comando para todos os subdiretórios de `C:\temp` . O parâmetro **include** limita os arquivos recuperados para aqueles com a `.txt` extensão de nome de arquivo. O parâmetro **Force** obtém arquivos ocultos, que do contrário, seriam excluídos. (Não é possível usar `c:\temp\*.txt` o, porque o parâmetro **recurse** funciona em diretórios, não em arquivos.)

O operador de pipeline ( `|` ) envia os objetos que representam os arquivos recuperados para o `Set-Acl` cmdlet, que aplica o descritor de segurança no parâmetro **AclObject** a todos os arquivos no pipeline.

Na prática, é melhor usar o parâmetro **WhatIf** com todos os `Set-Acl` comandos que podem afetar mais de um item. Nesse caso, o segundo comando no pipeline seria `Set-Acl -AclObject $NewAcl -WhatIf` . Esse comando lista os arquivos que seriam afetados pelo comando. Depois de examinar o resultado, você pode executar o comando novamente sem o parâmetro **WhatIf** .

### Exemplo 4: desabilitar a herança e preservar as regras de acesso herdadas

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Esses comandos desativarão a herança de acesso das pastas pai, enquanto ainda preservam as regras de acesso herdadas existentes.

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.

Em seguida, as variáveis são criadas para converter as regras de acesso herdadas para regras de acesso explícitas. Para proteger as regras de acesso associadas a ela da herança, defina a `$isProtected` variável como `$true` . para permitir a herança, defina `$isProtected` como `$false` . Para obter mais informações, consulte [definir a proteção da regra de acesso](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).
A `$preserveInheritance` variável definida como `$true` para preservar as regras de acesso herdadas; false para remover as regras de acesso herdadas. Em seguida, a proteção da regra de acesso é atualizada usando o método **SetAccessRuleProtection ()** .

O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt. Quando o comando for concluído, as ACLs do Dog.txt que foram herdadas da pasta pets serão aplicadas diretamente ao Dog.txt, e as novas políticas de acesso adicionadas aos animais de estimação não alterarão o acesso ao Dog.txt.

### Exemplo 5: conceder aos administradores controle total do arquivo

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Esse comando concederá ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt.

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança do arquivo de Dog.txt.

As variáveis seguintes são criadas para conceder ao grupo **BUILTIN\Administradores** controle total do arquivo de Dog.txt. A `$identity` variável definida como o nome de uma [conta de usuário](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).
A `$fileSystemRights` variável definida como FullControl e pode ser qualquer um dos valores de [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) que especifica o tipo de operação associado à regra de acesso. A `$type` variável definida como "Allow" especifica se a operação deve ser permitida ou negada. A `$fileSystemAccessRuleArgumentList` variável é uma lista de argumentos que deve ser passada ao fazer o novo objeto **FileSystemAccessRule** . Em seguida, um novo objeto **FileSystemAccessRule** é criado e o objeto **FileSystemAccessRule** é passado para o método **SetAccessRule ()** , adiciona a nova regra de acesso.

O último comando usa `Set-Acl` para aplicar o descritor de segurança do ao Dog.txt.
Quando o comando for concluído, o grupo **BUILTIN\Administradores** terá controle total da Dog.txt.

## PARAMETERS

### -AclObject

Especifica uma ACL com os valores de propriedade desejados. `Set-Acl` altera a ACL do item especificado pelo **caminho** ou o parâmetro **InputObject** para corresponder aos valores no objeto de segurança especificado.

Você pode salvar a saída de um `Get-Acl` comando em uma variável e, em seguida, usar o parâmetro **AclObject** para passar a variável ou digitar um `Get-Acl` comando.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClearCentralAccessPolicy

Remove a política de acesso central do item especificado.

A partir do Windows Server 2012, os administradores podem usar Active Directory e Política de Grupo para definir políticas de acesso central para usuários e grupos. Para obter mais informações, consulte [controle de acesso dinâmico: visão geral do cenário](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excluir

Omite os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path** . Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

Especifica um filtro no formato ou linguagem do provedor. O valor deste parâmetro qualifica o parâmetro **Path** . A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor. Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao recuperar os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

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

Altera somente os itens especificados. O valor deste parâmetro qualifica o parâmetro **Path** .
Insira um elemento ou padrão de caminho, como `*.txt` . Caracteres curinga são permitidos.

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

### -InputObject

Altera o descritor de segurança do objeto especificado. Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.

Não é possível canalizar o objeto a ser alterado para `Set-Acl` . Em vez disso, use o parâmetro **InputObject** explicitamente no comando.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Altera o descritor de segurança do item especificado. Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples ( `'` ).
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o descritor de segurança que foi alterado. Por padrão, este cmdlet não gera saída.

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

### -Path

Altera o descritor de segurança do item especificado. Digite o caminho para um item, como um caminho para um arquivo ou chave de registro. Caracteres curinga são permitidos.

Se você passar um objeto de segurança para `Set-Acl` (usando os parâmetros **AclObject** ou **SecurityDescriptor** ou passando um objeto de segurança de Get-Acl para `Set-Acl` ), e omitir o parâmetro **Path** (nome e valor), `Set-Acl` o usará o caminho incluído no objeto de segurança.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Security. AccessControl. ObjectSecurity, System. Security. AccessControl. CommonSecurityDescriptor

É possível canalizar um objeto ACL ou um descritor de segurança para o `Set-Acl` .

## SAÍDAS

### System. Security. AccessControl. FileSecurity

Por padrão, `Set-Acl` o não gera nenhuma saída.
No entanto, se usar o parâmetro **Passthru** , ele gera um objeto de segurança.
O tipo do objeto de segurança depende do tipo do item.

## OBSERVAÇÕES

 O `Set-Acl` cmdlet é suportado pelo sistema de arquivos do PowerShell e pelos provedores de registro. Dessa forma, você pode usá-lo para alterar os descritores de segurança dos arquivos, diretórios e chaves do registro.

## LINKS RELACIONADOS

[Get-Acl](Get-Acl.md)

[FileSystemAccessRule](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[ObjectSecurity.SetAccessRuleProtection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights)
