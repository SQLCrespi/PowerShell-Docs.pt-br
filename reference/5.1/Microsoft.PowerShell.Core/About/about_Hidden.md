---
description: Descreve a palavra-chave Hidden, que oculta membros de classe dos resultados de Get-Member padrão.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 641ebdc942186db90a23f4c784a0f1b3c295cae9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196576"
---
# <a name="about_hidden"></a>about_Hidden

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve a palavra-chave Hidden, que oculta membros de classe dos resultados de Get-Member padrão.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Quando você usa a palavra-chave Hidden em um script, você oculta os membros de uma classe por padrão. A palavra-chave Hidden pode ocultar propriedades, métodos (incluindo construtores, eventos, propriedades de alias e outros tipos de membros, incluindo membros estáticos, dos resultados padrão do cmdlet Get-Member e dos resultados do IntelliSense e da conclusão da guia. Para exibir os membros que você ocultou com a palavra-chave Hidden, adicione o parâmetro-Force a um comando Get-Member.

Os membros ocultos não são exibidos usando o preenchimento com Tab ou o IntelliSense, a menos que a conclusão ocorra na classe que define o membro oculto.

Um novo atributo, System. Management. Automation. Hiddenattribute, foi adicionado, para que \# o código C possa ter a mesma semântica no PowerShell.

A palavra-chave Hidden é útil para criar propriedades e métodos dentro de uma classe que você não necessariamente deseja que outros usuários da classe vejam ou possam editar prontamente.

A palavra-chave Hidden não tem nenhum efeito sobre como você pode exibir ou fazer alterações nos membros de uma classe. Como todas as palavras-chave de idioma no PowerShell, Hidden não diferencia maiúsculas de minúsculas e os membros ocultos ainda são públicos.

Oculto, juntamente com classes personalizadas, foi introduzido no PowerShell 5,0.

## <a name="example"></a>EXEMPLO

O exemplo a seguir mostra como usar a palavra-chave Hidden em uma definição de classe. O método de classe carro, tem uma propriedade, corridas, que não precisa ser exibida ou alterada (ela simplesmente calcula o número de vezes que a unidade é chamada na classe carro, uma métrica que não é importante para os usuários da classe; considere, por exemplo, que, quando você estiver comprando um carro, não pergunte ao vendedor quantas unidades o carro foi tirado.

Como há pouca necessidade de que os usuários da classe alterem essa propriedade, podemos ocultar a propriedade de Get-Member e os resultados de conclusão automática usando a palavra-chave Hidden.

Adicione a palavra-chave Hidden inserindo-a na mesma linha de instrução que a propriedade e seu tipo de dados. Embora a palavra-chave possa estar em qualquer ordem nessa linha, iniciar a instrução com a palavra-chave Hidden torna mais fácil para você identificar todos os membros que você ocultou posteriormente.

```powershell
class Car
{
   # Properties
   [String] $Color
   [String] $ModelYear
   [int] $Distance

   # Method
   [int] Drive ([int]$miles)
   {
      $this.Distance += $miles
      $this.rides++
      return $this.Distance
   }

   # Hidden property of the Drive method
    hidden [int] $rides = 0
}
```

Agora, crie uma nova instância da classe carro e salve-a em uma variável, \$ TestCar.

```powershell
$TestCar = [Car]::new()
```

Depois de criar a nova instância, redirecione o conteúdo da variável de $TestCar para get-member. Observe que a propriedade corridas não está entre os membros listados na Get-Member resultados do comando.

```output
PS C:\Windows\system32> $TestCar | Get-Member

   TypeName: Car

Name        MemberType Definition
----        ---------- ----------
Drive       Method     int Drive(int miles)
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
ToString    Method     string ToString()
Color       Property   string Color {get;set;}
Distance    Property   int Distance {get;set;}
ModelYear   Property   string ModelYear {get;set;}

```

Agora, tente executar Get-Member novamente, mas desta vez, adicione o parâmetro-Force.
Observe que os resultados contêm a propriedade corridas oculta, entre outros membros que estão ocultos por padrão.

```output
PS C:\Windows\system32> $TestCar | Get-Member -Force

   TypeName: Car

Name          MemberType   Definition
----          ----------   ----------
pstypenames   CodeProperty System.Collections.ObjectModel.Collection`1
psadapted     MemberSet    psadapted {Color, ModelYear, Distance,
psbase        MemberSet    psbase {Color, ModelYear, Distance,...
psextended    MemberSet    psextended {}
psobject      MemberSet    psobject {BaseObject, Members,...
Drive         Method       int Drive(int miles)
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
get_Color     Method       string get_Color()
get_Distance  Method       int get_Distance()
get_ModelYear Method       string get_ModelYear()
get_rides     Method       int get_rides()
set_Color     Method       void set_Color(string )
set_Distance  Method       void set_Distance(int )
set_ModelYear Method       void set_ModelYear(string )
set_rides     Method       void set_rides(int )
ToString      Method       string ToString()
Color         Property     string Color {get;set;}
Distance      Property     int Distance {get;set;}
ModelYear     Property     string ModelYear {get;set;}
rides         Property     int rides {get;set;}

```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Classes](about_Classes.md)

[about_Language_Keywords](about_Language_Keywords.md)

[about_Wildcards](about_Wildcards.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
