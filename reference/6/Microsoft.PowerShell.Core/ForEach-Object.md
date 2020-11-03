---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 5a1a53c2b312ef36c80ecfb2a771d2fee2ebea7f
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "93195306"
---
# ForEach-Object

## SINOPSE
Executa uma operação em cada item de uma coleção de objetos de entrada.

## SYNTAX

### ScriptBlockset (padrão)

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PropertyAndMethodSet

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `ForEach-Object` cmdlet executa uma operação em cada item em uma coleção de objetos de entrada. Os objetos de entrada podem ser canalizados para o cmdlet ou especificados usando o parâmetro **InputObject** .

A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `ForEach-Object` comando.

- **Bloco de script** . Você pode usar um bloco de script para especificar a operação. No bloco de script, use a `$_` variável para representar o objeto atual. O bloco de script é o valor do parâmetro **Process** . O bloco de script pode conter qualquer script do PowerShell.

  Por exemplo, o comando a seguir obtém o valor da propriedade **ProcessName** de cada processo no computador.

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` dá suporte `begin` aos `process` blocos, e `end` conforme descrito em [about_Functions](about/about_functions.md#piping-objects-to-functions).

  > [!NOTE]
  > Os blocos de script são executados no escopo do chamador. Portanto, os blocos têm acesso a variáveis nesse escopo e podem criar novas variáveis que persistem nesse escopo após a conclusão do cmdlet.

- **Instrução de operação** . Você também pode escrever uma instrução de operação, que é muito mais parecida com a linguagem natural. Você pode usar a instrução de operação para especificar um valor de propriedade ou chamar um método. Instruções de operação foram introduzidas no Windows PowerShell 3.0.

  Por exemplo, o comando a seguir também obtém o valor da propriedade **ProcessName** de cada processo no computador.

  `Get-Process | ForEach-Object ProcessName`

## EXEMPLOS

### Exemplo 1: dividir inteiros em uma matriz

Este exemplo usa uma matriz de três inteiros e divide cada um deles por 1024.

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### Exemplo 2: obter o comprimento de todos os arquivos em um diretório

Este exemplo processa os arquivos e diretórios no diretório de instalação do PowerShell `$PSHOME` .

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

Se o objeto não for um diretório, o bloco de script obterá o nome do arquivo, dividirá o valor de sua propriedade **Length** por 1024 e adicionará um espaço ("") para separá-lo da próxima entrada. O cmdlet usa a propriedade **PSISContainer** para determinar se um objeto é um diretório.

### Exemplo 3: operar nos eventos do sistema mais recentes

Este exemplo grava os 1000 eventos mais recentes do log de eventos do sistema em um arquivo de texto. A hora atual é exibida antes e depois do processamento dos eventos.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

`Get-EventLog` Obtém os 1000 eventos mais recentes do log de eventos do sistema e os armazena na `$Events` variável. `$Events` é então canalizado para o `ForEach-Object` cmdlet. O parâmetro **Begin** exibe a data e hora atuais. Em seguida, o parâmetro **process** usa o `Out-File` cmdlet para criar um arquivo de texto chamado events.txt e armazena a propriedade Message de cada um dos eventos nesse arquivo. Por fim, o parâmetro **End** é usado para exibir a data e hora após todo o processamento ter sido concluído.

### Exemplo 4: alterar o valor de uma chave do registro

Este exemplo altera o valor da entrada do registro **RemotePath** em todas as subchaves sob a `HKCU:\Network` chave para texto em maiúsculas.

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

Você pode usar esse formato para alterar a forma ou o conteúdo de um valor de entrada de registro.

Cada subchave da chave **Network** representa uma unidade de rede mapeada que será reconectada ao efetuar logon.
A entrada **RemotePath** contém o caminho UNC da unidade conectada. Por exemplo, se você mapear a unidade E: para `\\Server\Share` , haverá uma subchave **e** `HKCU:\Network` o valor da entrada do registro **RemotePath** na subchave **E** será `\\Server\Share` .

O comando usa o `Get-ItemProperty` cmdlet para obter todas as subchaves da chave de **rede** e o `Set-ItemProperty` cmdlet para alterar o valor da entrada do registro **RemotePath** em cada chave.
No `Set-ItemProperty` comando, o caminho é o valor da propriedade **PSPath** da chave do registro. Essa é uma propriedade do objeto Microsoft .NET Framework que representa a chave do registro, não uma entrada do registro. O comando usa o método **ToUpper ()** do valor **RemotePath** , que é uma cadeia de caracteres (REG_SZ).

Como o `Set-ItemProperty` está alterando a propriedade de cada chave, o `ForEach-Object` cmdlet é necessário para acessar a propriedade.

### Exemplo 5: usar a $Null variável automática

Este exemplo mostra o efeito de canalizar a `$Null` variável automática para o `ForEach-Object` cmdlet.

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

Como o PowerShell trata nulo como um espaço reservado explícito, o `ForEach-Object` cmdlet gera um valor para `$Null` , assim como faz para outros objetos que você canaliza para ele.

### Exemplo 6: obter valores de propriedade

Este exemplo obtém o valor da propriedade **path** de todos os módulos do PowerShell instalados usando o parâmetro **MemberName** do `ForEach-Object` cmdlet.

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

O segundo comando é equivalente ao primeiro. Ele usa o `Foreach` alias do `ForEach-Object` cmdlet e omite o nome do parâmetro **MemberName** , que é opcional.

O `ForEach-Object` cmdlet é muito útil para obter valores de propriedade, pois Obtém o valor sem alterar o tipo, diferentemente dos cmdlets **Format** ou do `Select-Object` cmdlet, que alteram o tipo de valor da propriedade.

### Exemplo 7: dividir nomes de módulo em nomes de componentes

Este exemplo mostra três maneiras de dividir dois nomes de módulo separados por ponto em seus nomes de componentes.

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

Os comandos chamam o método de cadeias de caracteres **Split** . Os três comandos usam uma sintaxe diferente, mas são equivalentes e intercambiáveis.

O primeiro comando usa a sintaxe tradicional, que inclui um bloco de script e o operador de objeto atual `$_` . Ele usa a sintaxe de ponto para especificar o método e parênteses para incluir o argumento delimitador.

O segundo comando usa o parâmetro **MemberName** para especificar o método **Split** e o parâmetro **ArgumentName** para identificar o ponto (".") como o delimitador de divisão.

O terceiro comando usa o alias **foreach** do `ForEach-Object` cmdlet e omite os nomes dos parâmetros **MemberName** e **ArgumentList** , que são opcionais.

### Exemplo 8: usando ForEach-Object com dois blocos de script

Neste exemplo, passamos dois blocos de script de posição. Todos os blocos de script são associados ao parâmetro de **processo** . No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** e **process** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### Exemplo 9: usando ForEach-Object com mais de dois blocos de script

Neste exemplo, passamos dois blocos de script de posição. Todos os blocos de script são associados ao parâmetro de **processo** . No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** , **process** e **end** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> O primeiro bloco de script é sempre mapeado para o `begin` bloco, o último bloco é mapeado para o `end` bloco e os blocos no between são todos mapeados para o `process` bloco.

### Exemplo 10: executar vários blocos de script para cada item de pipeline

Conforme mostrado no exemplo anterior, vários blocos de script passados usando o parâmetro **process** são mapeados para os parâmetros **begin** e **end** . Para evitar esse mapeamento, você deve fornecer valores explícitos para os parâmetros de **início** e **término** .

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

## PARAMETERS

### -ArgumentList

Especifica uma matriz de argumentos para uma chamada de método. Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Início

Especifica um bloco de script que é executado antes desse cmdlet processar qualquer objeto de entrada. Esse bloco de script só é executado uma vez para o pipeline inteiro. Para obter mais informações sobre o `begin` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fim

Especifica um bloco de script que é executado depois que esse cmdlet processa todos os objetos de entrada. Esse bloco de script só é executado uma vez para o pipeline inteiro. Para obter mais informações sobre o `end` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos de entrada. `ForEach-Object` executa o bloco de script ou a instrução de operação em cada objeto de entrada. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Quando você usa o parâmetro **InputObject** com `ForEach-Object` , em vez de direcionar os resultados de comando para `ForEach-Object` , o valor **InputObject** é tratado como um único objeto. Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .
Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `ForEach-Object` o para executar operações em uma coleção de objetos para os objetos que têm valores específicos nas propriedades definidas, use `ForEach-Object` no pipeline, conforme mostrado nos exemplos neste tópico.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberName

Especifica a propriedade a ser obtida ou o método a ser chamado.

Caracteres curinga são permitidos, mas só funcionam se a cadeia de caracteres resultante for resolvida para um valor exclusivo.
Se, por exemplo, você executar `Get-Process | ForEach -MemberName *Name` e houver mais de um membro com um nome que contenha o nome da cadeia de caracteres, como as propriedades **ProcessName** e **Name** , o comando falhará.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Processo

Especifica a operação que é executada em cada objeto de entrada. Esse bloco de script é executado para cada objeto no pipeline. Para obter mais informações sobre o `process` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).

Quando você fornece vários blocos de script para o parâmetro **process** , o primeiro bloco de script é sempre mapeado para o `begin` bloco. Se houver apenas dois blocos de script, o segundo bloco será mapeado para o `process` bloco. Se houver três ou mais blocos de script, o primeiro bloco de script será sempre mapeado para o `begin` bloco, o último bloco será mapeado para o `end` bloco e os blocos no between serão todos mapeados para o `process` bloco.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemainingScripts

Especifica todos os blocos de script que não são usados pelo parâmetro **process** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PSObject

Esse cmdlet retorna objetos que são determinados pela entrada.

## OBSERVAÇÕES

- O `ForEach-Object` cmdlet funciona de forma muito parecida com a instrução **foreach** , exceto que não é possível canalizar a entrada para uma instrução **foreach** . Para obter mais informações sobre a instrução **foreach** , consulte [about_Foreach](./About/about_Foreach.md).

- A partir do PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções. Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)

## LINKS RELACIONADOS

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
