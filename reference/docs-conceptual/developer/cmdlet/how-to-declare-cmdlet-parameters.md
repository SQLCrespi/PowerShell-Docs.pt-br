---
ms.date: 09/13/2016
ms.topic: reference
title: Como declarar parâmetros de cmdlet
description: Como declarar parâmetros de cmdlet
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667089"
---
# <a name="how-to-declare-cmdlet-parameters"></a>Como declarar parâmetros de cmdlet

Esses exemplos mostram como declarar parâmetros nomeados, posicionais, obrigatórios, opcionais e de comutação. Esses exemplos também mostram como definir um alias de parâmetro.

## <a name="how-to-declare-a-named-parameter"></a>Como declarar um parâmetro nomeado

- Defina uma propriedade pública, conforme mostrado no código a seguir. Quando você adicionar o atributo de parâmetro, omita a `Position` palavra-chave do atributo.

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-positional-parameter"></a>Como declarar um parâmetro posicional

- Defina uma propriedade pública, conforme mostrado no código a seguir. Ao adicionar o atributo de parâmetro, defina a `Position` palavra-chave como a posição do argumento. Um valor de 0 indica a primeira posição.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-mandatory-parameter"></a>Como declarar um parâmetro obrigatório

- Defina uma propriedade pública, conforme mostrado no código a seguir. Ao adicionar o atributo de parâmetro, defina a `Mandatory` palavra-chave como `true` .

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

## <a name="how-to-declare-an-optional-parameter"></a>Como declarar um parâmetro opcional

- Defina uma propriedade pública, conforme mostrado no código a seguir. Quando você adicionar o atributo de parâmetro, omita a `Mandatory` palavra-chave.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>Como declarar um parâmetro de opção

- Defina uma propriedade pública como tipo [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)e, em seguida, declare o atributo Parameter.

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

Para obter mais informações sobre o atributo de parâmetro, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-parameter-with-aliases"></a>Como declarar um parâmetro com aliases

- Defina uma propriedade pública, conforme mostrado no código a seguir. Adicione um atributo de alias que liste os aliases para o parâmetro. Neste exemplo, três aliases são definidos para o mesmo parâmetro. O primeiro alias fornece um atalho. O segundo e o terceiro aliases fornecem nomes que você pode usar para cenários diferentes.

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre o atributo Alias, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md)

[Declaração de atributo de alias](./alias-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
