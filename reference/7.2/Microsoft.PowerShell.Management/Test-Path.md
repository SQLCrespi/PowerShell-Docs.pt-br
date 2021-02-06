---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: a79f12739643a873703b39d9d07e8b7db01dfbb4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597209"
---
# Test-Path

## SINOPSE
Determina se todos os elementos de um caminho existem ou não.

## SYNTAX

### Caminho (padrão)

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### LiteralPath

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## DESCRIPTION

O `Test-Path` cmdlet determina se todos os elementos do caminho existem. Ele retornará `$True` se todos os elementos existirem e `$False` se algum estiver ausente. Ele também pode informar se a sintaxe do caminho é válida e se o caminho leva a um contêiner ou a um elemento de terminal ou folha. Se o `Path` for um espaço em branco uma cadeia de caracteres vazia, `$False` será retornado. Se `Path` for `$null` , matriz ou matriz `$null` vazia, um erro de não finalização será retornado.

## EXEMPLOS

### Exemplo 1: testar um caminho

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

Esse comando verifica se todos os elementos no caminho existem, ou seja, o diretório C:, o diretório Documents and Settings e o diretório DavidC Se algum estiver faltando, o cmdlet retornará `$False` .
Caso contrário, ele retornará `$True`.

### Exemplo 2: testar o caminho de um perfil

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

Esses comandos testam o caminho do perfil do PowerShell.

O primeiro comando determina se todos os elementos no caminho existem. O segundo comando determina se a sintaxe do caminho está correta. Nesse caso, o caminho é `$False` , mas a sintaxe está correta `$True` . Esses comandos usam `$profile` , a variável automática que aponta para o local do perfil, mesmo que o perfil não exista.

Para obter mais informações sobre variáveis automáticas, consulte about_Automatic_Variables.

### Exemplo 3: verificar se há arquivos além de um tipo especificado

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

Esse comando verifica se há arquivos no diretório prédios comerciais que não sejam arquivos. dwg.

O comando usa o parâmetro **path** para especificar o caminho. Como o caminho inclui um espaço, o caminho é colocado entre aspas. O asterisco no final do caminho indica o conteúdo do diretório Prédios comerciais. Com caminhos longos, como este, digite as primeiras letras do caminho e, em seguida, use a tecla TAB para concluir o caminho.

O comando especifica o parâmetro **Exclude** para especificar os arquivos que serão omitidos da avaliação.

Nesse caso, como o diretório contém apenas arquivos. dwg, o resultado é `$False` .

### Exemplo 4: verificar se há um arquivo

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

Esse comando verifica se o caminho armazenado na `$profile` variável leva a um arquivo. Nesse caso, como o perfil do PowerShell é um `.ps1` arquivo, o cmdlet retorna `$True` .

### Exemplo 5: verificar caminhos no registro

Esses comandos usam `Test-Path` com o provedor de registro do PowerShell.

O primeiro comando testa se o caminho do registro da chave do registro **Microsoft. PowerShell** está correto no sistema. Se o PowerShell for instalado corretamente, o cmdlet retornará `$True` .

> [!IMPORTANT]
> `Test-Path` Não funciona corretamente com todos os provedores do PowerShell. Por exemplo, você pode usar `Test-Path` o para testar o caminho de uma chave do registro, mas se você usá-la para testar o caminho de uma entrada do registro, ela sempre retornará `$False` , mesmo que a entrada do registro esteja presente.

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### Exemplo 6: testar se um arquivo é mais novo do que uma data especificada

Esse comando usa o parâmetro dinâmico **NewerThan** para determinar se o arquivo "PowerShell.exe" no computador é mais recente do que "13 de julho de 2009".

O parâmetro NewerThan funciona apenas em unidades de sistema de arquivos.

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### Exemplo 7: testar um caminho com NULL como o valor

O erro retornado para `null` , matriz `null` ou matriz vazia é um erro de não finalização. Ele pode ser suprimido usando `-ErrorAction SilentlyContinue` . O exemplo a seguir mostra todos os casos que retornam o `NullPathNotPermitted` erro.

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### Exemplo 8: testar um caminho com espaço em branco como o valor

Quando um espaço em branco ou uma cadeia de caracteres vazia é fornecido para o `-Path` parâmetro, ele retorna **false**.
O exemplo a seguir mostra o espaço em branco e a cadeia de caracteres vazia.

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## PARAMETERS

### -Credential

> [!NOTE]
> Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell. Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Excluir

Especifica os itens que esse cmdlet omite. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um padrão ou elemento de caminho, como "*.txt". Caracteres curinga são permitidos.

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

Especifica um filtro no formato ou idioma do provedor. O valor deste parâmetro qualifica o parâmetro **Path**. A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor. Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica quando recupera os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.

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

Especifica os caminhos que este cmdlet testa. O valor deste parâmetro qualifica o parâmetro **Path**. Insira um padrão ou elemento de caminho, como "*.txt". Caracteres curinga são permitidos.

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

### -IsValid

Indica que esse cmdlet testa a sintaxe do caminho, independentemente se os elementos do caminho existem. Esse cmdlet retornará `$True` se a sintaxe do caminho for válida e `$False` se não for.

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

### -LiteralPath

Especifica um caminho a ser testado. Ao contrário de **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres que poderiam ser interpretados pelo PowerShell como sequências de escape, você deverá colocar o caminho entre aspas simples para que eles não sejam interpretados.

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

### -NewerThan

Especifique uma hora como um objeto **DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OlderThan

Especifique uma hora como um objeto **DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica um caminho a ser testado. Caracteres curinga são permitidos. Se o caminho incluir espaços, coloque-os entre aspas.

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

### -PathType

Especifica o tipo do elemento final no caminho. Esse cmdlet retorna `$True` se o elemento for do tipo especificado e `$False` se não for. Os valores aceitáveis para esse parâmetro são:

- Contêiner.
  Um elemento que contém outros elementos, como um diretório ou chave do registro.
- Chapa.
  Um elemento que não contém outros elementos, como um arquivo.
- Outro.
  Pode ser tanto um contêiner quanto uma folha.

Indica se o elemento final no caminho é ou não de um tipo específico.

> [!CAUTION]
>
> Até o PowerShell versão 6.1.2, quando as opções **IsValid** e **PathType** são especificadas juntas, o `Test-Path` cmdlet ignora a opção **PathType** e valida o caminho sintático sem validar o tipo de caminho.
>
> De acordo com o [problema #8607](https://github.com/PowerShell/PowerShell/issues/8607), corrigir esse comportamento pode ser uma alteração significativa em uma versão futura, em que as opções **IsValid** e **PathType** pertencem a conjuntos de parâmetros separados e, portanto, não podem ser usadas em conjunto, evitando essa confusão.

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.

## SAÍDAS

### System.Boolean

O cmdlet retorna um valor **booliano** .

## OBSERVAÇÕES

Os cmdlets que contêm o substantivo de **caminho** (os cmdlets de **caminho** ) funcionam com nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar. Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.
Use-os como usaria **dirname**, **Normpath**, **realpath**, **Join** ou outros manipuladores de caminho.

O `Test-Path` é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` . Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## LINKS RELACIONADOS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)
