---
description: Combinando comandos em pipelines no PowerShell
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: 1be86d4ff65dfc36a85eac32814c76175157aa4d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196505"
---
# <a name="about-pipelines"></a>Sobre pipelines

## <a name="short-description"></a>Descrição breve

Combinando comandos em pipelines no PowerShell

## <a name="long-description"></a>Descrição longa

Um pipeline é uma série de comandos conectados por operadores de pipeline ( `|` ) (ASCII 124). Cada operador de pipeline envia os resultados do comando anterior para o próximo comando.

A saída do primeiro comando pode ser enviada para processamento como entrada para o segundo comando. E essa saída pode ser enviada para outro comando. O resultado é uma cadeia de comandos complexa ou um _pipeline_ composto por uma série de comandos simples.

Por exemplo,

```powershell
Command-1 | Command-2 | Command-3
```

Neste exemplo, os objetos que `Command-1` são emitidos são enviados para `Command-2` .
`Command-2` processa os objetos e os envia para o `Command-3` . `Command-3` processa os objetos e os envia por meio do pipeline. Como não há mais comandos no pipeline, os resultados são exibidos no console.

Em um pipeline, os comandos são processados na ordem da esquerda para a direita. O processamento é tratado como uma única operação e a saída é exibida à medida que é gerada.

Veja um exemplo simples. O comando a seguir obtém o processo do bloco de notas e o interrompe.

Por exemplo,

```powershell
Get-Process notepad | Stop-Process
```

O primeiro comando usa o `Get-Process` cmdlet para obter um objeto que representa o processo do bloco de notas. Ele usa um operador de pipeline ( `|` ) para enviar o objeto de processo para o `Stop-Process` cmdlet, o que interrompe o processo do bloco de notas. Observe que o `Stop-Process` comando não tem um parâmetro **Name** ou **ID** para especificar o processo, pois o processo especificado é enviado por meio do pipeline.

Este exemplo de pipeline Obtém os arquivos de texto no diretório atual, seleciona apenas os arquivos com mais de 10.000 bytes, classifica-os por comprimento e exibe o nome e o comprimento de cada arquivo em uma tabela.

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

Esse pipeline consiste em quatro comandos na ordem especificada. A ilustração a seguir mostra a saída de cada comando conforme passado para o próximo comando no pipeline.

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a>Usando pipelines

A maioria dos cmdlets do PowerShell foi projetada para dar suporte a pipelines. Na maioria dos casos, você pode _canalizar_ os resultados de um cmdlet **Get** para outro cmdlet do mesmo substantivo.
Por exemplo, você pode canalizar a saída do `Get-Service` cmdlet para os `Start-Service` `Stop-Service` cmdlets ou.

Este pipeline de exemplo inicia o serviço WMI no computador:

```powershell
Get-Service wmi | Start-Service
```

Para outro exemplo, você pode canalizar a saída de `Get-Item` ou `Get-ChildItem` dentro do provedor de registro do PowerShell para o `New-ItemProperty` cmdlet. Este exemplo adiciona uma nova entrada de registro, **NoOfEmployees** , com um valor de **8124** , à chave do registro **MyCompany** .

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

Muitos dos cmdlets do utilitário, como `Get-Member` ,, `Where-Object` , `Sort-Object` `Group-Object` e `Measure-Object` são usados quase exclusivamente em pipelines. É possível canalizar qualquer tipo de objeto para esses cmdlets. Este exemplo mostra como classificar todos os processos no computador pelo número de identificadores abertos em cada processo.

```powershell
Get-Process | Sort-Object -Property handles
```

Você pode canalizar objetos para os cmdlets de formatação, exportação e saída, como `Format-List` ,,, `Format-Table` `Export-Clixml` `Export-CSV` e `Out-File` .

Este exemplo mostra como usar o `Format-List` cmdlet para exibir uma lista de propriedades para um objeto de processo.

```powershell
Get-Process winlogon | Format-List -Property *
```

Com um pouco de prática, você descobrirá que a combinação de comandos simples em pipelines poupa tempo e digitação e torna o script mais eficiente.

## <a name="how-pipelines-work"></a>Como funcionam os pipelines

Esta seção explica como os objetos de entrada são associados a parâmetros de cmdlet e processados durante a execução do pipeline.

### <a name="accepts-pipeline-input"></a>Aceita entrada de pipeline

Para dar suporte ao pipeline, o cmdlet receptor deve ter um parâmetro que aceita entrada de pipeline. Use o `Get-Help` comando com as opções **Full** ou **Parameter** para determinar quais parâmetros de um cmdlet aceitam entrada de pipeline.

Por exemplo, para determinar qual dos parâmetros do `Start-Service` cmdlet aceita entrada de pipeline, digite:

```powershell
Get-Help Start-Service -Full
```

ou

```powershell
Get-Help Start-Service -Parameter *
```

A ajuda para o `Start-Service` cmdlet mostra que apenas os parâmetros **InputObject** e **Name** aceitam a entrada do pipeline.

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

Quando você envia objetos por meio do pipeline para o `Start-Service` , o PowerShell tenta associar os objetos aos parâmetros **InputObject** e **Name** .

### <a name="methods-of-accepting-pipeline-input"></a>Métodos de aceitação de entrada de pipeline

Os parâmetros de cmdlets podem aceitar a entrada de pipeline em uma das duas maneiras diferentes:

- **ByValue** : o parâmetro aceita valores que correspondem ao tipo .net esperado ou que podem ser convertidos nesse tipo.

  Por exemplo, o parâmetro **Name** de `Start-Service` aceita entrada de pipeline por valor. Ele pode aceitar objetos String ou objetos que podem ser convertidos em cadeias de caracteres.

- **ByPropertyName** : o parâmetro aceita a entrada somente quando o objeto de entrada tem uma propriedade de mesmo nome que o parâmetro.

  Por exemplo, o parâmetro Name de `Start-Service` pode aceitar objetos que têm uma propriedade **Name** . Para listar as propriedades de um objeto, redirecione-o para `Get-Member` .

Alguns parâmetros podem aceitar objetos pelo valor ou nome da propriedade, facilitando a entrada do pipeline.

### <a name="parameter-binding"></a>Associação de parâmetro

Quando você canaliza objetos de um comando para outro, o PowerShell tenta associar os objetos de pipe com um parâmetro do cmdlet de recebimento.

O componente de associação de parâmetro do PowerShell associa os objetos de entrada a parâmetros de cmdlet de acordo com os seguintes critérios:

- O parâmetro deve aceitar a entrada de um pipeline.
- O parâmetro deve aceitar o tipo de objeto que está sendo enviado ou um tipo que pode ser convertido para o tipo esperado.
- O parâmetro não foi usado no comando.

Por exemplo, o `Start-Service` cmdlet tem muitos parâmetros, mas apenas dois deles, **Name** e **InputObject** aceitam entrada de pipeline. O parâmetro **Name** usa cadeias de caracteres e o parâmetro **InputObject** usa objetos de serviço. Portanto, é possível redirecionar cadeias de caracteres, objetos de serviço e objetos com propriedades que podem ser convertidas em objetos de cadeia ou de serviço.

O PowerShell gerencia a associação de parâmetro com a maior eficiência possível. Você não pode sugerir ou forçar o PowerShell a se associar a um parâmetro específico. O comando falhará se o PowerShell não puder associar os objetos canalizados.

Para obter mais informações sobre como solucionar erros de associação, consulte [investigando erros de pipeline](#investigating-pipeline-errors) mais adiante neste artigo.

### <a name="one-at-a-time-processing"></a>Processamento One-at-time

Os objetos de tubulação a um comando são muito parecidos com o uso de um parâmetro do comando para enviar os objetos. Vejamos um exemplo de pipeline. Neste exemplo, usamos um pipeline para exibir uma tabela de objetos de serviço.

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

Funcionalmente, isso é como usar o parâmetro **InputObject** de `Format-Table` para enviar a coleção de objetos.

Por exemplo, podemos salvar a coleção de serviços em uma variável que é passada usando o parâmetro **InputObject** .

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

Ou podemos inserir o comando no parâmetro **InputObject** .

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

No entanto, há uma diferença importante. Quando você canaliza vários objetos para um comando, o PowerShell envia os objetos para o comando, um de cada vez. Quando você usa um parâmetro de comando, os objetos são enviados como um único objeto de matriz. Essa diferença secundária tem consequências significativas.

Ao executar um pipeline, o PowerShell enumera automaticamente qualquer tipo que implemente a `IEnumerable` interface e envia os membros por meio do pipeline, um de cada vez. A exceção é `[hashtable]` , que requer uma chamada para o `GetEnumerator()` método.

Nos exemplos a seguir, uma matriz e uma tabela de hash são canalizadas para o `Measure-Object` cmdlet para contar o número de objetos recebidos do pipeline. A matriz tem vários membros, e a tabela de hash tem vários pares de chave/valor. Somente a matriz é enumerada uma de cada vez.

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Da mesma forma, se você canalizar vários objetos de processo do `Get-Process` cmdlet para o `Get-Member` cmdlet, o PowerShell enviará cada objeto de processo, um de cada vez, para `Get-Member` . `Get-Member` exibe a classe .NET (tipo) dos objetos de processo e suas propriedades e métodos.

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> `Get-Member` elimina duplicatas, portanto, se os objetos forem todos do mesmo tipo, ele exibirá apenas um tipo de objeto.

No entanto, se você usar o parâmetro **InputObject** de `Get-Member` , `Get-Member` o receberá uma matriz de objetos **System. Diagnostics. Process** como uma única unidade. Ele exibe as propriedades de uma matriz de objetos. (Observe o símbolo da matriz ( `[]` ) após o nome do tipo **System. Object** .)

Por exemplo,

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

Esse resultado pode não ser o que você pretendia. Mas, depois de entender, você pode usá-lo. Por exemplo, todos os objetos de matriz têm uma propriedade **Count** . Você pode usá-lo para contar o número de processos em execução no computador.

Por exemplo,

```powershell
(Get-Process).count
```

É importante lembrar que os objetos enviados pelo pipeline são entregues um de cada vez.

## <a name="investigating-pipeline-errors"></a>Investigando erros de pipeline

Quando o PowerShell não pode associar os objetos de pipe com um parâmetro do cmdlet receptor, o comando falha.

No exemplo a seguir, tentamos mover uma entrada de registro de uma chave do registro para outra. O `Get-Item` cmdlet obtém o caminho de destino, que é então canalizado para o `Move-ItemProperty` cmdlet. O `Move-ItemProperty` comando especifica o caminho atual e o nome da entrada do registro a ser movida.

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

O comando falha e o PowerShell exibe a seguinte mensagem de erro:

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

Para investigar, use o `Trace-Command` cmdlet para rastrear o componente de associação de parâmetro do PowerShell. O exemplo a seguir rastreia a associação de parâmetro enquanto o pipeline está em execução. O parâmetro **PSHost** exibe os resultados do rastreamento no console e o parâmetro **FilePath** envia os resultados do rastreamento para o `debug.txt` arquivo para referência posterior.

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

Os resultados do rastreamento são longos, mas mostram os valores que estão sendo associados ao `Get-Item` cmdlet e, em seguida, os valores nomeados que estão sendo associados ao `Move-ItemProperty` cmdlet.

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

Por fim, ele mostra que a tentativa de associar o caminho ao **Destination** parâmetro de destino `Move-ItemProperty` falha.

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

Use o `Get-Help` cmdlet para exibir os atributos do parâmetro de **destino** .

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

Os resultados mostram que o **destino** faz apenas a entrada do pipeline "por nome da propriedade". Portanto, o objeto de pipe deve ter uma propriedade chamada **Destination** .

Use `Get-Member` para ver as propriedades do objeto proveniente de `Get-Item` .

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

A saída mostra que o item é um objeto **Microsoft. Win32. RegistryKey** que não tem uma propriedade de **destino** . Isso explica por que o comando falhou.

O parâmetro **path** aceita a entrada de pipeline por nome ou por valor.

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

Para corrigir o comando, devemos especificar o destino no `Move-ItemProperty` cmdlet e usar `Get-Item` para obter o **caminho** do item que desejamos mover.

Por exemplo,

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a>Continuação de linha intrínseca

Como já foi discutido, um pipeline é uma série de comandos conectados por operadores de pipeline ( `|` ), geralmente gravados em uma única linha. No entanto, para facilitar a leitura, o PowerShell permite dividir o pipeline em várias linhas.
Quando um operador de pipe é o último token na linha, o analisador do PowerShell une a linha seguinte ao comando atual para continuar a construção do pipeline.

Por exemplo, o seguinte pipeline de linha única:

```powershell
Command-1 | Command-2 | Command-3
```

pode ser escrito como:

```powershell
Command-1 |
  Command-2 |
    Command-3
```

Os espaços à esquerda nas linhas subsequentes não são significativos. O recuo melhora a legibilidade.

## <a name="see-also"></a>Consulte Também

[about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)

[about_Objects](about_objects.md)

[about_Parameters](about_parameters.md)

[about_Command_Syntax](about_command_syntax.md)

[about_ForEach](about_foreach.md)
