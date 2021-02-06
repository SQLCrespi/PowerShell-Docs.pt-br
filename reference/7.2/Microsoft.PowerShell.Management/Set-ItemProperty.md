---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 18383dc2b1e018e56864e412dfe75eca2b578a08
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598440"
---
# Set-ItemProperty

## SINOPSE
Cria ou altera o valor de uma propriedade de um item.

## SYNTAX

### propertyValuePathSet (padrão)

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertyPSObjectPathSet

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertyValueLiteralPathSet

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertyPSObjectLiteralPathSet

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## DESCRIPTION

O `Set-ItemProperty` cmdlet altera o valor da Propriedade do item especificado.
Você pode usar o cmdlet para estabelecer ou alterar as propriedades de itens.
Por exemplo, você pode usar `Set-ItemProperty` para definir o valor da propriedade **IsReadOnly** de um objeto de arquivo como `$True` .

Você também usa `Set-ItemProperty` para criar e alterar dados e valores de registro.
Por exemplo, você pode adicionar uma nova entrada de registro a uma chave e estabelecer ou alterar seu valor.

## EXEMPLOS

### Exemplo 1: definir uma propriedade de um arquivo

Esse comando define o valor da propriedade **IsReadOnly** do arquivo "final.doc" como "true".
Ele usa o **caminho** para especificar o arquivo, o **nome** para especificar o nome da propriedade e o parâmetro de **valor** para especificar o novo valor.

O arquivo é um objeto **System. IO. FileInfo** e **IsReadOnly** é apenas uma de suas propriedades.
Para ver todas as propriedades, digite `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .

A `$true` variável automática representa um valor de "true".
Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### Exemplo 2: criar uma entrada e um valor de registro

Este exemplo mostra como usar `Set-ItemProperty` o para criar uma nova entrada de registro e atribuir um valor à entrada. Ele cria a entrada "NoOfEmployees" na chave "ContosoCompany" na `HKLM\Software` chave e define seu valor como 823.

Como as entradas do registro são consideradas propriedades das chaves do registro, que são itens, você usa `Set-ItemProperty` para criar entradas do registro e para estabelecer e alterar seus valores.

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

O primeiro comando cria a entrada do registro.
Ele usa o **caminho** para especificar o caminho da `HKLM:` unidade e a chave "software\mycompany".
O comando usa **nome** para especificar o nome e o **valor** da entrada para especificar um valor.

O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.
Se você usar os `Get-Item` `Get-ChildItem` cmdlets ou, as entradas não aparecerão porque são propriedades de uma chave, não itens ou itens filho.

O terceiro comando altera o valor da entrada **NoOfEmployees** para 824.

Você também pode usar o `New-ItemProperty` cmdlet para criar a entrada do registro e seu valor e, em seguida, usar `Set-ItemProperty` para alterar o valor.

Para obter mais informações sobre a `HKLM:` unidade, digite `Get-Help Get-PSDrive` .
Para obter mais informações sobre como usar o PowerShell para gerenciar o registro, digite `Get-Help Registry` .

### Exemplo 3: modificar um item usando o pipeline

Estes comandos mostram como usar um operador de pipeline ( `|` ) para enviar um item para o `Set-ItemProperty` .

A primeira parte do comando usa `Get-ChildItem` para obter um objeto que representa o arquivo "Weekly.txt". O comando usa um operador de pipeline para o qual enviar o objeto de arquivo `Set-ItemProperty` .
O `Set-ItemProperty` comando usa os parâmetros **Name** e **Value** para especificar a propriedade e seu novo valor.

Esse comando é equivalente a usar o parâmetro **InputObject** para especificar o objeto que `Get-ChildItem` obtém.

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## PARAMETERS

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

Força o cmdlet a definir uma propriedade em itens que, de outra forma, não podem ser acessados pelo usuário.
A implementação varia de provedor para provedor.
Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -InputObject

Especifica o objeto que tem as propriedades que esse cmdlet altera.
Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica um caminho para um ou mais locais. O valor de **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica o nome da propriedade.

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa a propriedade do item.
Por padrão, este cmdlet não gera saída.

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

Especifica o caminho dos itens com a propriedade a ser modificada.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Type

**Type** é um parâmetro dinâmico que o provedor do registro adiciona ao `Set-ItemProperty` cmdlet.
Esse parâmetro só funciona nas unidades do registro.

Especifica o tipo de propriedade que este cmdlet adiciona.
Os valores aceitáveis para esse parâmetro são:

- **Cadeia de caracteres**: especifica uma cadeia de caracteres terminada em nulo. Equivalente a **REG_SZ**.
- **ExpandString**: especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado. Equivalente a **REG_EXPAND_SZ**.
- **Binary**: especifica dados binários em qualquer formulário. Equivalente a **REG_BINARY**.
- **DWORD**: especifica um número binário de 32 bits. Equivalente a **REG_DWORD**.
- **Multistring**: especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.
  Equivalente a **REG_MULTI_SZ**.
- **QWORD**: especifica um número binário de 64 bits. Equivalente a **REG_QWORD**.
- **Desconhecido**: indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST**.

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Especifica o valor da propriedade.

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System. Management. Automation. PSObject

Você pode canalizar objetos para este cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PSCustomObject

Esse cmdlet gera um objeto **PSCustomObject** que representa o item que foi alterado e seu novo valor de propriedade, se você especificar o parâmetro **PassThru** .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

`Set-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

