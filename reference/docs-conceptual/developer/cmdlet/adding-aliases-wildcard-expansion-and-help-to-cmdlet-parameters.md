---
title: Adicionando aliases, expansão de curinga e ajuda para parâmetros de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: d210a852a90d94df2ab360dd86f0b83a396330e3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415647"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a>Adicionar aliases, expansão de curinga e ajuda a parâmetros de cmdlet

Esta seção descreve como adicionar aliases, expansão de curinga e mensagens de ajuda aos parâmetros do cmdlet Stop-proc (descrito em [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)).

Esse cmdlet Stop-proc tenta parar os processos recuperados usando o cmdlet Get-proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Definindo o cmdlet

A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet. Como você está escrevendo um cmdlet para alterar o sistema, ele deve ser nomeado de acordo. Como esse cmdlet interrompe os processos do sistema, ele usa o verbo "Stop", definido pela classe [System. Management. Automation. Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , com o substantivo "proc" para indicar o processo. Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).

O código a seguir é a definição de classe para esse cmdlet Stop-proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Definindo parâmetros para a modificação do sistema

Seu cmdlet precisa definir parâmetros que dão suporte a modificações do sistema e comentários do usuário. O cmdlet deve definir um parâmetro `Name` ou equivalente para que o cmdlet possa modificar o sistema por algum tipo de identificador. Além disso, o cmdlet deve definir os parâmetros `Force` e `PassThru`. Para obter mais informações sobre esses parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="defining-a-parameter-alias"></a>Definindo um alias de parâmetro

Um alias de parâmetro pode ser um nome alternativo ou um nome curto bem definido de 1 letra ou de duas letras para um parâmetro de cmdlet. Em ambos os casos, a meta de usar aliases é simplificar a entrada do usuário na linha de comando. O Windows PowerShell dá suporte a aliases de parâmetro por meio do atributo [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) , que usa a sintaxe de declaração [alias ()].

O código a seguir mostra como um alias é adicionado ao parâmetro `Name`.

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

Além de usar o atributo [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) , o tempo de execução do Windows PowerShell executa correspondência de nome parcial, mesmo que nenhum alias seja especificado. Por exemplo, se o cmdlet tiver um parâmetro `FileName` e esse for o único parâmetro que começa com `F`, o usuário poderá inserir `Filename`, `Filenam`, `File`, `Fi`ou `F` e ainda reconhecer a entrada como o parâmetro `FileName`.

## <a name="creating-help-for-parameters"></a>Criando ajuda para parâmetros

O Windows PowerShell permite que você crie ajuda para parâmetros de cmdlet. Faça isso para qualquer parâmetro usado para modificação do sistema e comentários do usuário. Para cada parâmetro para dar suporte à ajuda, você pode definir a palavra-chave do atributo `HelpMessage` na declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) . Essa palavra-chave define o texto a ser exibido para o usuário para obter assistência no uso do parâmetro. Você também pode definir a palavra-chave `HelpMessageBaseName` para identificar o nome de base de um recurso a ser usado para a mensagem. Se você definir essa palavra-chave, também deverá definir a palavra-chave `HelpMessageResourceId` para especificar o identificador de recurso.

O código a seguir desse cmdlet Stop-proc define a palavra-chave do atributo `HelpMessage` para o parâmetro `Name`.

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a>Substituindo um método de processamento de entrada

O cmdlet deve substituir um método de processamento de entrada, com mais frequência ele será [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). Ao modificar o sistema, o cmdlet deve chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) para permitir que o usuário forneça comentários antes que uma alteração seja feita. Para obter mais informações sobre esses métodos, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="supporting-wildcard-expansion"></a>Suporte à expansão de curinga

Para permitir a seleção de vários objetos, o cmdlet pode usar as classes [System. Management. Automation. Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) e [System. Management. Automation. curingaoptions](/dotnet/api/System.Management.Automation.WildcardOptions) para fornecer suporte à expansão de curinga para a entrada de parâmetro. Exemplos de padrões de curinga são LSA *, \*. txt e [a-c]\*. Use o caractere de aspas (') como um caractere de escape quando o padrão contiver um caractere que deve ser usado literalmente.

As expansões de curinga dos nomes de arquivo e caminho são exemplos de cenários comuns em que o cmdlet pode querer permitir suporte para entradas de caminho quando a seleção de vários objetos é necessária. Um caso comum está no sistema de arquivos, em que um usuário deseja ver todos os arquivos que residem na pasta atual.

Você deve precisar de um padrão de caractere curinga personalizado somente para a implementação, raramente. Nesse caso, o cmdlet deve dar suporte à especificação POSIX 1003,2, 3,13 completa para expansão de curinga ou o seguinte subconjunto simplificado:

- **Ponto de interrogação (?).** Corresponde a qualquer caractere no local especificado.

- **Asterisco (\*).** Corresponde a zero ou mais caracteres a partir do local especificado.

- **Colchete de abertura ([).** Apresenta uma expressão de colchete de padrão que pode conter caracteres ou um intervalo de caracteres. Se um intervalo for necessário, um hífen (-) será usado para indicar o intervalo.

- **Colchete de fechamento (]).** Termina uma expressão de colchete de padrão.

- **Caractere de escape de aspas traseiras (').** Indica que o próximo caractere deve ser levado literalmente. Lembre-se de que ao especificar o caractere de aspas invertidas na linha de comando (em vez de especificá-lo de forma programática), o caractere de escape de aspas traseiras deve ser especificado duas vezes.

> [!NOTE]
> Para obter mais informações sobre padrões de curinga, consulte [suportando curingas em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).

O código a seguir mostra como definir opções de curinga e definir o padrão de curinga usado para resolver o parâmetro de `Name` para esse cmdlet.

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

O código a seguir mostra como testar se o nome do processo corresponde ao padrão curinga definido. Observe que, nesse caso, se o nome do processo não corresponder ao padrão, o cmdlet continuará para obter o próximo nome do processo.

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a>Exemplo de Código

Para obter o C# código de exemplo completo, consulte [exemplo de StopProcessSample03](./stopprocesssample03-sample.md).

## <a name="define-object-types-and-formatting"></a>Definir tipos de objeto e formatação

O Windows PowerShell passa informações entre os cmdlets usando objetos .net. Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet. Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Criando o cmdlet

Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell. Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testando o cmdlet

Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando. Vamos testar o cmdlet Stop-proc de exemplo. Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Inicie o Windows PowerShell e use Stop-proc para interromper um processo usando o alias ProcessName para o parâmetro `Name`.

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

A seguinte saída aparece.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Faça a seguinte entrada na linha de comando. Como o parâmetro Name é obrigatório, você será solicitado a fazê-lo. Inserindo "!?" Abre o texto de ajuda associado ao parâmetro.

    ```powershell
    PS> stop-proc
    ```

A seguinte saída aparece.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- Agora, faça a seguinte entrada parar todos os processos que correspondam ao padrão curinga "* note\*". Você será solicitado antes de parar cada processo que corresponde ao padrão.

    ```powershell
    PS> stop-proc -Name *note*
    ```

A seguinte saída aparece.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

A seguinte saída aparece.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

A seguinte saída aparece.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>Consulte Também

[Criar um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md)

[Como criar um cmdlet do Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))

[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))

[Suporte a curingas em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
