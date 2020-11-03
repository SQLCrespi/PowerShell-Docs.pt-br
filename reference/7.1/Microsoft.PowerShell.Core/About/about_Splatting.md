---
description: Descreve como usar nivelamento para passar parâmetros para comandos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: a64cbbe5edd40bf4fc7f9b7347421988d225e666
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195830"
---
# <a name="about-splatting"></a>Sobre o nivelamento

## <a name="short-description"></a>Descrição breve

Descreve como usar nivelamento para passar parâmetros para comandos no PowerShell.

## <a name="long-description"></a>Descrição longa

Nivelamento é um método para passar uma coleção de valores de parâmetro para um comando como uma unidade. O PowerShell associa cada valor na coleção a um parâmetro de comando. Os valores de parâmetro Splatted são armazenados em variáveis nomeadas nivelamento, que se parecem com variáveis padrão, mas começam com um símbolo de arroba ( `@` ) em vez de um cifrão ( `$` ). O símbolo at informa ao PowerShell que você está passando uma coleção de valores, em vez de um único valor.

O nivelamento torna seus comandos mais curtos e fáceis de ler. Você pode reutilizar os valores de nivelamento em chamadas de comando diferentes e usar nivelamento para passar valores de parâmetro da `$PSBoundParameters` variável automática para outros scripts e funções.

A partir do Windows PowerShell 3,0, você também pode usar nivelamento para representar todos os parâmetros de um comando.

## <a name="syntax"></a>Syntax

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

Para fornecer valores de parâmetro para parâmetros posicionais, nos quais os nomes de parâmetro não são necessários, use a sintaxe de matriz. Para fornecer pares de nome de parâmetro e valor, use a sintaxe da tabela de hash. O valor de splatted pode aparecer em qualquer lugar na lista de parâmetros.

Quando nivelamento, você não precisa usar uma tabela de hash ou uma matriz para passar todos os parâmetros. Você pode passar alguns parâmetros usando nivelamento e passar outros por posição ou por nome de parâmetro. Além disso, você pode fragmentação vários objetos em um único comando para não passar mais de um valor para cada parâmetro.

A partir do PowerShell 7,1, você pode substituir um parâmetro splatted definindo explicitamente um parâmetro em um comando.

## <a name="splatting-with-hash-tables"></a>Nivelamento com tabelas de hash

Use uma tabela de hash para fragmentação pares de nome e valor do parâmetro. Você pode usar esse formato para todos os tipos de parâmetro, incluindo parâmetros posicionais e de switch.
Os parâmetros posicionais devem ser atribuídos por nome.

Os exemplos a seguir comparam dois `Copy-Item` comandos que copiam o arquivo de Test.txt para o arquivo de Test2.txt no mesmo diretório.

O primeiro exemplo usa o formato tradicional no qual os nomes de parâmetro são incluídos.

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

O segundo exemplo usa a tabela de hash nivelamento. O primeiro comando cria uma tabela de hash de pares parâmetro-nome e parâmetro-valor e o armazena na `$HashArguments` variável. O segundo comando usa a `$HashArguments` variável em um comando com nivelamento. O símbolo de arroba ( `@HashArguments` ) substitui o sinal de dólar ( `$HashArguments` ) no comando.

Para fornecer um valor para o parâmetro de opção **WhatIf** , use `$True` ou `$False` .

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> No primeiro comando, o símbolo de arroba ( `@` ) indica uma tabela de hash, não um valor splatted. A sintaxe para tabelas de hash no PowerShell é: `@{<name>=<value>; <name>=<value>; ...}`

## <a name="splatting-with-arrays"></a>Nivelamento com matrizes

Use uma matriz para fragmentação valores de parâmetros posicionais, que não exigem nomes de parâmetro. Os valores devem estar na ordem de número de posição na matriz.

Os exemplos a seguir comparam dois `Copy-Item` comandos que copiam o arquivo de Test.txt para o arquivo de Test2.txt no mesmo diretório.

O primeiro exemplo usa o formato tradicional no qual os nomes de parâmetro são omitidos. Os valores de parâmetro aparecem na ordem de posição no comando.

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

O segundo exemplo usa a matriz nivelamento. O primeiro comando cria uma matriz dos valores de parâmetro e armazena-o na `$ArrayArguments` variável. Os valores estão na ordem de posição na matriz. O segundo comando usa a `$ArrayArguments` variável em um comando em nivelamento. O símbolo de arroba ( `@ArrayArguments` ) substitui o sinal de dólar ( `$ArrayArguments` ) no comando.

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a>Usando o parâmetro ArgumentList

Vários cmdlets têm um parâmetro **ArgumentList** que é usado para passar valores de parâmetro para um bloco de script que é executado pelo cmdlet. O parâmetro **ArgumentList** usa uma matriz de valores que é passada para o bloco de script. O PowerShell está efetivamente usando array nivelamento para associar os valores aos parâmetros do bloco de script. Ao usar **ArgumentList** , se você precisar passar uma matriz como um único objeto associado a um único parâmetro, deverá encapsular a matriz como o único elemento de outra matriz.

O exemplo a seguir tem um bloco de script que usa um único parâmetro que é uma matriz de cadeias de caracteres.

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```
<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
Neste exemplo, somente o primeiro item em `$array` é passado para o bloco de script.

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

Neste exemplo, `$array` é encapsulado em uma matriz para que toda a matriz seja passada para o bloco de script como um único objeto.

```Output
Hello World!
```

## <a name="examples"></a>Exemplos

### <a name="example-1-reuse-splatted-parameters-in-different-commands"></a>Exemplo 1: reutilizar parâmetros splatted em comandos diferentes

Este exemplo mostra como reutilizar valores splatted em comandos diferentes. Os comandos neste exemplo usam o `Write-Host` cmdlet para gravar mensagens no console do programa host. Ele usa nivelamento para especificar as cores de primeiro e segundo plano.

Para alterar as cores de todos os comandos, basta alterar o valor da `$Colors` variável.

O primeiro comando cria uma tabela de hash de nomes e valores de parâmetro e armazena a tabela de hash na `$Colors` variável.

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

O segundo e o terceiro comandos usam a `$Colors` variável para nivelamento em um `Write-Host` comando. Para usar o `$Colors variable` , substitua o cifrão ( `$Colors` ) por um símbolo de arroba ( `@Colors` ).

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

### <a name="example-2-forward-parameters-using-psboundparameters"></a>Exemplo 2: encaminhar parâmetros usando $PSBoundParameters

Este exemplo mostra como encaminhar seus parâmetros para outros comandos usando nivelamento e a `$PSBoundParameters` variável automática.

A `$PSBoundParameters` variável automática é um objeto de dicionário (System. Collections. Generic. Dictionary) que contém todos os nomes de parâmetro e valores que são usados quando um script ou uma função é executada.

No exemplo a seguir, usamos a `$PSBoundParameters` variável para encaminhar os valores de parâmetros passados para um script ou função da `Test2` função para a `Test1` função. Ambas as chamadas para a `Test1` função de `Test2` usam nivelamento.

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

### <a name="example-3-override-splatted-parameters-with-explicitly-defined-parameters"></a>Exemplo 3: Substituir parâmetros splatted por parâmetros definidos explicitamente

Este exemplo mostra como substituir um parâmetro splatted usando parâmetros definidos explicitamente. Isso é útil quando você não deseja criar uma nova tabela de hash ou alterar um valor na tabela de hash que você está usando para fragmentação.

A `$commonParams` variável armazena os parâmetros para criar máquinas virtuais no `East US` local. A `$allVms` variável é uma lista de máquinas virtuais a serem criadas. Vamos fazer um loop pela lista e usar `$commonParams` para fragmentação os parâmetros para criar cada máquina virtual. No entanto, queremos `myVM2` ser criados em uma região diferente das outras máquinas virtuais. Em vez de ajustar a `$commonParams` Hashtable, você pode definir explicitamente o parâmetro **Location** no `New-AzVm` para substituir o valor da `Location` chave em `$commonParams` .

```powershell
$commonParams = @{
    ResourceGroupName = "myResourceGroup"
    Location = "East US"
    VirtualNetworkName = "myVnet"
    SubnetName = "mySubnet"
    SecurityGroupName = "myNetworkSecurityGroup"
    PublicIpAddressName = "myPublicIpAddress"
}

$allVms = @('myVM1','myVM2','myVM3',)

foreach ($vm in $allVms)
{
    if ($vm -eq 'myVM2')
    {
        New-AzVm @commonParams -Name $vm -Location "West US"
    }
    else
    {
        New-AzVm @commonParams -Name $vm
    }
}
```

## <a name="splatting-command-parameters"></a>Parâmetros do comando nivelamento

Você pode usar nivelamento para representar os parâmetros de um comando. Essa técnica é útil quando você está criando uma função de proxy, ou seja, uma função que chama outro comando. Esse recurso é introduzido no Windows PowerShell 3,0.

Para fragmentação os parâmetros de um comando, use `@Args` para representar os parâmetros de comando. Essa técnica é mais fácil do que enumerar parâmetros de comando e funciona sem revisão, mesmo que os parâmetros do comando chamado sejam alterados.

O recurso usa a `$Args` variável automática, que contém todos os valores de parâmetro não atribuídos.

Por exemplo, a função a seguir chama o `Get-Process` cmdlet. Nessa função, `@Args` representa todos os parâmetros do `Get-Process` cmdlet.

```powershell
function Get-MyProcess { Get-Process @Args }
```

Quando você usa a `Get-MyProcess` função, todos os parâmetros e valores de parâmetros não atribuídos são passados para `@Args` , conforme mostrado nos comandos a seguir.

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

Você pode usar `@Args` o em uma função que tenha parâmetros explicitamente declarados. Você pode usá-lo mais de uma vez em uma função, mas todos os parâmetros inseridos são passados para todas as instâncias do `@Args` , conforme mostrado no exemplo a seguir.

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a>Observações

Se você fizer uma função em uma função avançada usando os atributos **CmdletBinding** ou **parâmetro** , a `$args` variável automática não estará mais disponível na função. As funções avançadas exigem definição de parâmetro explícita.

A DSC (configuração de estado desejado) do PowerShell não foi projetada para usar nivelamento.
Você não pode usar nivelamento para passar valores para um recurso de DSC. Para obter mais informações, consulte o artigo Gael colas " [Getnivelamento DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).

## <a name="see-also"></a>Confira também

[about_Arrays](about_Arrays.md)

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Parameters](about_Parameters.md)
