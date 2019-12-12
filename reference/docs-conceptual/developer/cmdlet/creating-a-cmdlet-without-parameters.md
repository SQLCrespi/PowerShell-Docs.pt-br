---
title: Criando um cmdlet sem parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: af41c2c9855310d047404114a07b27180a7aa8fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415678"
---
# <a name="creating-a-cmdlet-without-parameters"></a>Criar um cmdlet sem parâmetros

Esta seção descreve como criar um cmdlet que recupera informações do computador local sem o uso de parâmetros e, em seguida, grava as informações no pipeline. O cmdlet descrito aqui é um cmdlet Get-proc que recupera informações sobre os processos do computador local e, em seguida, exibe essas informações na linha de comando.

> [!NOTE]
> Lembre-se de que, ao escrever cmdlets, os assemblies de referência do Windows PowerShell® são baixados no disco (por padrão, em C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0). Eles não são instalados no GAC (cache de assembly global).

## <a name="naming-the-cmdlet"></a>Nomeando o cmdlet

Um nome de cmdlet consiste em um verbo que indica a ação que o cmdlet usa e um substantivo que indica os itens que o cmdlet atua. Como esse cmdlet Get-proc de exemplo recupera objetos de processo, ele usa o verbo "Get", definido pela enumeração [System. Management. Automation. Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) e o substantivo "proc" para indicar que o cmdlet funciona em itens de processo.

Ao nomear cmdlets, não use nenhum dos seguintes caracteres: #, () {} [] &-/\ $; : "' < > &#124; ? @ ` .

### <a name="choosing-a-noun"></a>Escolhendo um substantivo

Você deve escolher um substantivo específico. É melhor usar um substantivo singular prefixado com uma versão reduzida do nome do produto. Um exemplo de nome de cmdlet desse tipo é "`Get-SQLServer`".

### <a name="choosing-a-verb"></a>Escolhendo um verbo

Você deve usar um verbo do conjunto de nomes de verbo de cmdlet aprovados. Para obter mais informações sobre os verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

## <a name="defining-the-cmdlet-class"></a>Definindo a classe do cmdlet

Depois de escolher um nome de cmdlet, defina uma classe .NET para implementar o cmdlet. Aqui está a definição de classe para este cmdlet Get-proc de exemplo:

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

Observe que, antes da definição de classe, o atributo [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , com a sintaxe `[Cmdlet(verb, noun, ...)]`, é usado para identificar essa classe como um cmdlet. Esse é o único atributo necessário para todos os cmdlets e permite que o tempo de execução do Windows PowerShell os chame corretamente. Você pode definir palavras-chave de atributo para declarar ainda mais a classe, se necessário. Lembre-se de que a declaração de atributo para nossa classe GetProcCommand de exemplo declara apenas os nomes de substantivo e verbo para o cmdlet Get-proc.

> [!NOTE]
> Para todas as classes de atributo do Windows PowerShell, as palavras-chave que você pode definir correspondem às propriedades da classe de atributo.

Ao nomear a classe do cmdlet, é uma prática recomendada refletir o nome do cmdlet no nome da classe. Para fazer isso, use o formato "VerbNounCommand" e substitua "verbo" e "substantivo" pelo verbo e pelo substantivo usados no nome do cmdlet. Como é mostrado na definição de classe anterior, o cmdlet Get-proc de exemplo define uma classe chamada GetProcCommand, que deriva da classe base [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .

> [!IMPORTANT]
> Se você quiser definir um cmdlet que acesse o tempo de execução do Windows PowerShell diretamente, sua classe do .NET deverá derivar da classe base [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) . Para obter mais informações sobre essa classe, consulte [criando um cmdlet que define conjuntos de parâmetros](./adding-parameter-sets-to-a-cmdlet.md).

> [!NOTE]
> A classe de um cmdlet deve ser explicitamente marcada como pública. As classes que não estiverem marcadas como públicas usarão como padrão o interno e não serão encontradas pelo tempo de execução do Windows PowerShell.

O Windows PowerShell usa o namespace [Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) para suas classes de cmdlet. É recomendável posicionar suas classes de cmdlet em um namespace de comandos do seu namespace de API, por exemplo, XXX. PS. Commands.

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

A classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) fornece três métodos principais de processamento de entrada, pelo menos um dos quais seu cmdlet deve substituir. Para obter mais informações sobre como o Windows PowerShell processa registros, consulte [como o Windows PowerShell funciona](/previous-versions//ms714658(v=vs.85)).

Para todos os tipos de entrada, o tempo de execução do Windows PowerShell chama [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) para habilitar o processamento. Se o cmdlet precisar executar algum pré-processamento ou configuração, ele poderá fazer isso substituindo esse método.

> [!NOTE]
> O Windows PowerShell usa o termo "registro" para descrever o conjunto de valores de parâmetro fornecidos quando um cmdlet é chamado.

Se o cmdlet aceitar a entrada do pipeline, ele deverá substituir o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e, opcionalmente, o método [System. Management. Automation. cmdlet. endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Por exemplo, um cmdlet poderá substituir os dois métodos se ele reunir todas as entradas usando [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e, em seguida, operar na entrada como um elemento inteiro, em vez de um Element de cada vez, como o cmdlet `Sort-Object`.

Se o cmdlet não receber a entrada do pipeline, ele deverá substituir o método [System. Management. Automation. cmdlet. Endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Lembre-se de que esse método é usado frequentemente no lugar de [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) quando o cmdlet não pode operar em um elemento por vez, como é o caso de um cmdlet de classificação.

Como este cmdlet Get-proc de exemplo deve receber a entrada do pipeline, ele substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) e usa as implementações padrão para [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) e [System. Management. Automation. cmdlet. noprocessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing). A substituição [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) recupera os processos e os grava na linha de comando usando o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a>Coisas a serem lembradas sobre o processamento de entrada

- A fonte padrão de entrada é um objeto explícito (por exemplo, uma cadeia de caracteres) fornecido pelo usuário na linha de comando. Para obter mais informações, consulte [criando um cmdlet para processar a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md).

- Um método de processamento de entrada também pode receber entrada do objeto de saída de um cmdlet upstream no pipeline. Para obter mais informações, consulte [criando um cmdlet para processar a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md). Lembre-se de que o cmdlet pode receber entrada de uma combinação de fontes de linha de comando e de pipeline.

- O cmdlet downstream pode não retornar por muito tempo ou não deve ser retornado. Por esse motivo, o método de processamento de entrada em seu cmdlet não deve manter bloqueios durante chamadas para [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especialmente bloqueios para os quais o escopo se estende além da instância do cmdlet.

> [!IMPORTANT]
> Os cmdlets devem nunca chamar [System. console. WriteLine *](/dotnet/api/System.Console.WriteLine) ou seu equivalente.

- Seu cmdlet pode ter variáveis de objeto para limpeza quando termina o processamento (por exemplo, se abrir um identificador de arquivo no método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) e manter o identificador aberto para uso por [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)). É importante lembrar que o tempo de execução do Windows PowerShell nem sempre chama o método [System. Management. Automation. cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , que deve executar a limpeza de objeto.

Por exemplo, [System. Management. Automation. cmdlet. endprocesso](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) não poderá ser chamado se o cmdlet for cancelado no Midway ou se um erro de encerramento ocorrer em qualquer parte do cmdlet. Portanto, um cmdlet que exige a limpeza de objeto deve implementar o padrão [System. IDisposable](/dotnet/api/System.IDisposable) completo, incluindo o finalizador, para que o tempo de execução possa chamar o [System. Management. Automation. cmdlet. endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) e [System. IDisposable. Dispose *](/dotnet/api/System.IDisposable.Dispose) no final do processamento.

## <a name="code-sample"></a>Exemplo de Código

Para obter o C# código de exemplo completo, consulte [exemplo de GetProcessSample01](./getprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definindo tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .NET. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando. O código para nosso cmdlet Get-proc de exemplo é pequeno, mas ainda usa o tempo de execução do Windows PowerShell e um objeto .NET existente, o que é suficiente para torná-lo útil. Vamos testá-lo para entender melhor o que o Get-proc pode fazer e como sua saída pode ser usada. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

1. Inicie o Windows PowerShell e obtenha os processos atuais em execução no computador.

    ```powershell
    get-proc
    ```

    A seguinte saída aparece.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. Atribua uma variável aos resultados do cmdlet para facilitar a manipulação.

    ```powershell
    $p=get-proc
    ```

3. Obter o número de processos.

    ```powershell
    $p.length
    ```

    A seguinte saída aparece.

    ```output
    63
    ```

4. Recuperar um processo específico.

    ```powershell
    $p[6]
    ```

    A seguinte saída aparece.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. Obtenha a hora de início desse processo.

    ```powershell
    $p[6].starttime
    ```

    A seguinte saída aparece.

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. Obtenha os processos para os quais a contagem de identificador é maior que 500 e Classifique o resultado.

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    A seguinte saída aparece.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. Use o cmdlet `Get-Member` para listar as propriedades disponíveis para cada processo.

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    A seguinte saída aparece.

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a>Consulte Também

[Criando um cmdlet para processar a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md)

[Criando um cmdlet para processar a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md)

[Como criar um cmdlet do Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como funciona o Windows PowerShell](/previous-versions//ms714658(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[Referência do Windows PowerShell](../windows-powershell-reference.md)

[Exemplos de cmdlet](./cmdlet-samples.md)
