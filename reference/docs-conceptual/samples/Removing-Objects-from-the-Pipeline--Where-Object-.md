---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Removendo objetos do pipeline Where-Object
ms.openlocfilehash: 370e7745341b70c0794352a690d5750d21f53ac2
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737178"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a>Removendo objetos do pipeline (Where-Object)

No PowerShell, você muitas vezes gera e passa mais objetos para um pipeline do que deseja. É possível especificar as propriedades de determinados objetos para exibição usando os cmdlets `Format-*`, mas isso não ajuda em problemas de remoção de objetos inteiros da exibição. Talvez você queira filtrar objetos antes do final de um pipeline para poder executar ações em apenas um subconjunto dos objetos gerados inicialmente.

O PowerShell inclui um cmdlet `Where-Object` que permite testar cada objeto no pipeline e apenas passá-lo pelo pipeline caso ele atenda a determinada condição de teste. Objetos que não passarem no teste são removidos do pipeline. Forneça a condição de teste como o valor do parâmetro **FilterScript**.

## <a name="performing-simple-tests-with-where-object"></a>Executando testes simples com Where-Object

O valor de **FilterScript** é um *bloco de script* – um ou mais comandos do PowerShell entre chaves (`{}`) – que é avaliado como verdadeiro ou falso. Esses blocos de script podem ser muito simples, mas criá-los requer conhecimento sobre outro conceito do PowerShell, os operadores de comparação. Um operador de comparação compara os itens que aparecem em cada lado dela. Os operadores de comparação começam com um caractere de hífen (`-`) e são seguidos por um nome. Operadores de comparação básicos funcionam em praticamente qualquer tipo de objeto. Os operadores de comparação mais avançados podem funcionar apenas em texto ou matrizes.

> [!NOTE]
> Por padrão, ao trabalhar com texto, os operadores de comparação do PowerShell não diferenciam maiúsculas de minúsculas.

Devido a considerações de análise, símbolos como `<`,`>` e `=` não são usados como operadores de comparação. Em vez disso, os operadores de comparação são compostos por letras. Os operadores de comparação básicos estão listados na tabela a seguir.

| Operador de Comparação |                  Significado                   |    Exemplo (returna true)    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| -eq                 | é igual a                                | 1 -eq 1                      |
| -ne                 | Não é igual a                            | 1 -ne 2                      |
| -lt                 | É menor que                               | 1 -lt 2                      |
| -le                 | É menor ou igual a                   | 1 -le 2                      |
| -gt                 | É maior que                            | 2 -gt 1                      |
| -ge                 | É maior ou igual a                | 2 -ge 1                      |
| -like               | É como (curinga de comparação para texto)     | "file.doc" -like "f*.do?"    |
| -notlike            | Não é como (curinga de comparação para texto) | "file.doc" -notlike "p*.doc" |
| -contains           | Contém                                   | 1,2,3 -contains 1            |
| -notcontains        | Não contém                           | 1,2,3 -notcontains 4         |

Os blocos de script de `Where-Object` usam a variável especial `$_` para fazer referência ao objeto atual no pipeline. Veja um exemplo de como isso funciona. Se você tiver uma lista de números e quiser retornar apenas os inferiores a três, poderá usar `Where-Object` para filtrar os números digitando:

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a>Filtragem com base nas propriedades de objeto

Como `$_` se refere ao objeto atual no pipeline, podemos acessar suas propriedades para nossos testes.

Por exemplo, podemos ver a classe **Win32_SystemDriver** no WMI. Pode haver centenas de drivers do sistema em um determinado sistema, mas você pode só estar interessado em um determinado conjunto de drivers do sistema, como aqueles que estão sendo executados. Para a classe **Win32_SystemDriver**, a propriedade relevante é **State**. Você pode filtrar os drivers do sistema selecionando apenas aqueles em execução digitando:

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

Isso ainda produz uma longa lista. Você pode filtrar para escolher apenas os drivers definidos para iniciar automaticamente testando também o valor de **StartMode**:

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
...
```

Isso nos fornece muitas informações que já não precisamos mais porque sabemos que os drivers estão sendo executados.
Na verdade, a única informação que é provavelmente precisamos neste ponto é o nome e o nome de exibição. O comando a seguir inclui somente essas duas propriedades, resultando em uma saída muito mais simples:

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

Há dois elementos `Where-Object` no comando acima, mas eles podem ser expressados em um único elemento `Where-Object` usando o operador lógico `-and`, desta forma:

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

Os operadores lógicos padrão são listados na tabela a seguir.

| Operador Lógico |                 Significado                  |  Exemplo (returna true)  |
| ---------------- | ---------------------------------------- | ------------------------ |
| -and             | E lógico; verdadeiro se ambos os lados forem verdadeiros | (1 -eq 1) -and (2 -eq 2) |
| -or              | Ou lógico; verdadeiro se um dos lados for verdadeiro  | (1 -eq 1) -or (1 -eq 2)  |
| -not             | Não lógico; inverte o verdadeiro e o falso     | -not (1 -eq 2)           |
| \!               | Não lógico; inverte o verdadeiro e o falso     | \!(1 -eq 2)              |
