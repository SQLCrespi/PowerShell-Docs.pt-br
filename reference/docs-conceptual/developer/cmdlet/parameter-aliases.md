---
title: Aliases de parâmetro | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e320eeb4d2ab91acf2116fdc817a50e93c82aead
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781980"
---
# <a name="parameter-aliases"></a>Aliases de parâmetro

Parâmetros de cmdlet também podem ter aliases. Você pode usar os aliases em vez dos nomes de parâmetro ao digitar ou especificar o parâmetro em um comando.

## <a name="benefits-of-using-aliases"></a>Benefícios do uso de aliases

A adição de aliases a parâmetros oferece os seguintes benefícios.

- Você pode fornecer um atalho para que o usuário não precise usar o nome completo do parâmetro quando o cmdlet for chamado. Por exemplo, você pode usar o alias "CN" em vez do nome do parâmetro "computername".

- Você pode definir vários aliases se desejar fornecer nomes diferentes para o mesmo parâmetro. Talvez você queira definir vários aliases se precisar trabalhar com vários grupos de usuários que se referem aos mesmos dados de diferentes maneiras.

- Você pode fornecer compatibilidade com versões anteriores para scripts existentes se o nome de um parâmetro for alterado.

- Usando o atributo alias junto com o atributo ValueFromPipelineByName, você pode definir um parâmetro que permite que o cmdlet se vincule a diferentes tipos de objeto. Por exemplo, digamos que você tivesse dois objetos de tipos diferentes e o primeiro objeto tinha uma propriedade de gravador e o segundo objeto tinha uma propriedade de editor. Se o cmdlet tivesse um parâmetro que tinha aliases de gravador e editor e o cmdlet aceitou a entrada de pipeline com base em nomes de propriedade, seu cmdlet poderá se associar a ambos os objetos usando os dois aliases de parâmetro.

Para obter mais informações sobre aliases que podem ser usados com parâmetros específicos, consulte [nomes de parâmetro comuns](./common-parameter-names.md).

## <a name="defining-parameter-aliases"></a>Definindo aliases de parâmetro

Para definir um alias para um parâmetro, declare o atributo Alias, conforme mostrado na declaração de parâmetro a seguir. Neste exemplo, vários aliases são definidos para o mesmo parâmetro. (Para obter mais informações, consulte[How to declare cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)

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

## <a name="see-also"></a>Consulte Também

[Nomes de parâmetro comuns](./common-parameter-names.md)

[Como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
