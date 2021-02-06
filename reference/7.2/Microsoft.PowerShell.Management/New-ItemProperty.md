---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 59b7ea7f675d72dd90d970306c60107bd3f1de87
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596984"
---
# New-ItemProperty

## SINOPSE
Cria uma nova propriedade para um item e define seu valor.

## SYNTAX

### Caminho (padrão)

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `New-ItemProperty` cmdlet cria uma nova propriedade para um item especificado e define seu valor.
Normalmente, esse cmdlet é usado para criar novos valores de registro porque os valores do registro são propriedades de um item de chave do registro.

Esse cmdlet não adiciona propriedades a um objeto.

- Para adicionar uma propriedade a uma instância de um objeto, use o `Add-Member` cmdlet.
- Para adicionar uma propriedade a todos os objetos de um tipo específico, modifique o arquivo XML Types.ps1.

## EXEMPLOS

### Exemplo 1: adicionar uma entrada de registro

Esse comando adiciona uma nova entrada de registro, "NoOfEmployees", à chave "MyCompany" do "HKLM: \ Software Hive".

O primeiro comando usa o parâmetro **path** para especificar o caminho da chave do registro "myCompany".
Ele usa o parâmetro **Name** para especificar um nome para a entrada e o parâmetro **Value** para especificar seu valor.

O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### Exemplo 2: adicionar uma entrada de registro a uma chave

Este comando adiciona uma nova entrada de registro a uma chave do registro.
Para especificar a chave, ele usa um operador de pipeline ( `|` ) para enviar um objeto que representa a chave para `New-ItemProperty` .

A primeira parte do comando usa o `Get-Item` cmdlet para obter a chave do registro "myCompany".
O operador de pipeline envia os resultados do comando para `New-ItemProperty` , que adiciona a nova entrada de registro ("NoOfLocations") e seu valor (3) à chave "myCompany".

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

Esse comando funciona porque o recurso de vinculação de parâmetro do PowerShell associa o caminho do `RegistryKey` objeto que `Get-Item` retorna com o parâmetro **LiteralPath** de `New-ItemProperty` . Para obter mais informações, consulte [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).

### Exemplo 3: criar um valor de multistring no registro usando um Here-String

Este exemplo cria um valor de multistring usando uma cadeia de caracteres here.

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### Exemplo 4: criar um valor de cadeia de caracteres multistring no registro usando uma matriz

O exemplo mostra como usar uma matriz de valores para criar o `MultiString` valor.

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
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

Força o cmdlet a criar uma propriedade em um objeto que, de outra forma, não pode ser acessado pelo usuário.
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

### -Name

Especifica um nome para a nova propriedade.
Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica o caminho do item.
Caracteres curinga são permitidos.
Esse parâmetro identifica o item ao qual esse cmdlet adiciona a nova propriedade.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -PropertyType

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
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Especifica o valor da propriedade.
Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSCustomObject

`New-ItemProperty` Retorna um objeto personalizado que contém a nova propriedade.

## OBSERVAÇÕES

`New-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

