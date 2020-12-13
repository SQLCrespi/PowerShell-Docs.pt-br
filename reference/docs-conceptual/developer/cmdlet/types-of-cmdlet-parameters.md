---
ms.date: 09/13/2016
ms.topic: reference
title: Tipos de parâmetros de cmdlet
description: Tipos de parâmetros de cmdlet
ms.openlocfilehash: 8daaa3c778396e06a826de3b93e0610c51160fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660482"
---
# <a name="types-of-cmdlet-parameters"></a>Tipos de parâmetros de cmdlet

Este tópico descreve os diferentes tipos de parâmetros que você pode declarar em cmdlets. Os parâmetros de cmdlet podem ser posicionais, nomeados, obrigatórios, opcionais ou parâmetros de switch.

## <a name="positional-and-named-parameters"></a>Parâmetros posicionais e nomeados

Todos os parâmetros de cmdlet são parâmetros nomeados ou posicionais. Um parâmetro nomeado requer que você digite o nome do parâmetro e o argumento ao chamar o cmdlet. Um parâmetro posicional requer apenas que você digite os argumentos em ordem relativa. Em seguida, o sistema mapeia o primeiro argumento sem nome para o primeiro parâmetro posicional. O sistema mapeia o segundo argumento sem nome para o segundo parâmetro sem nome e assim por diante. Por padrão, todos os parâmetros de cmdlet são parâmetros nomeados.

Para definir um parâmetro nomeado, omita a `Position` palavra-chave na declaração de atributo de **parâmetro** , conforme mostrado na declaração de parâmetro a seguir.

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Para definir um parâmetro posicional, adicione a `Position` palavra-chave na declaração de atributo de parâmetro e, em seguida, especifique uma posição. No exemplo a seguir, o `UserName` parâmetro é declarado como um parâmetro posicional com a posição 0. Isso significa que o primeiro argumento da chamada será associado automaticamente a esse parâmetro.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> Um bom design de cmdlet recomenda que os parâmetros mais usados sejam declarados como parâmetros posicionais para que o usuário não precise inserir o nome do parâmetro quando o cmdlet for executado.

Os parâmetros posicionais e nomeados aceitam argumentos únicos ou vários argumentos separados por vírgulas. Vários argumentos são permitidos somente se o parâmetro aceita uma coleção, como uma matriz de cadeias de caracteres. Você pode misturar os parâmetros posicionais e nomeados no mesmo cmdlet. Nesse caso, o sistema recupera os argumentos nomeados primeiro e, em seguida, tenta mapear os argumentos não nomeados restantes para os parâmetros posicionais.

Os comandos a seguir mostram as diferentes maneiras pelas quais você pode especificar argumentos únicos e múltiplos para os parâmetros do `Get-Command` cmdlet. Observe que nos dois últimos exemplos, **-Name** não precisa ser especificado porque o `Name` parâmetro é definido como um parâmetro posicional.

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>Parâmetros obrigatórios e opcionais

Você também pode definir parâmetros de cmdlet como parâmetros obrigatórios ou opcionais. (Um parâmetro obrigatório deve ser especificado antes de o tempo de execução do Windows PowerShell invocar o cmdlet.)  Por padrão, os parâmetros são definidos como opcionais.

Para definir um parâmetro obrigatório, adicione a `Mandatory` palavra-chave na declaração de atributo de parâmetro e defina-a `true` como, conforme mostrado na declaração de parâmetro a seguir.

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Para definir um parâmetro opcional, omita a `Mandatory` palavra-chave na declaração de atributo de **parâmetro** , conforme mostrado na declaração de parâmetro a seguir.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>Parâmetros de comutação

O Windows PowerShell fornece um tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) que permite que você defina um parâmetro cujo valor é definido automaticamente como `false` se o parâmetro não for especificado quando o cmdlet for chamado. Sempre que possível, use parâmetros de opção no lugar de parâmetros boolianos.

Considere o exemplo a seguir. Por padrão, vários cmdlets do Windows PowerShell não passam um objeto de saída para baixo no pipeline. No entanto, esses cmdlets têm um `PassThru` parâmetro de opção que substitui o comportamento padrão. Se o `PassThru` parâmetro for especificado quando esses cmdlets forem chamados, o cmdlet retornará um objeto de saída para o pipeline.

Se você precisar que o parâmetro tenha um valor padrão `true` quando o parâmetro não for especificado na chamada, considere reverter a noção do parâmetro. Por exemplo, em vez de definir o atributo de parâmetro como um valor booliano de `true` , declare a propriedade como o tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) e, em seguida, defina o valor padrão do parâmetro como `false` .

Para definir um parâmetro de opção, declare a propriedade como o tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) , conforme mostrado no exemplo a seguir.

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

Para fazer com que o cmdlet atue no parâmetro quando ele for especificado, use a seguinte estrutura dentro de um dos métodos de processamento de entrada.

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
