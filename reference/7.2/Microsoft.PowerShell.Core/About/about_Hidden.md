---
description: Descreve a palavra-chave Hidden, que oculta membros de classe dos resultados de Get-Member padrão.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 8340a955b7cfa540baccde0da233d6d9cf0c5552
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603547"
---
# <a name="about_hidden"></a><span data-ttu-id="9aa93-103">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="9aa93-103">about_Hidden</span></span>

## <a name="short-description"></a><span data-ttu-id="9aa93-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9aa93-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9aa93-105">Descreve a palavra-chave Hidden, que oculta membros de classe dos resultados de Get-Member padrão.</span><span class="sxs-lookup"><span data-stu-id="9aa93-105">Describes the Hidden keyword, which hides class members from default Get-Member results.</span></span>

## <a name="long-description"></a><span data-ttu-id="9aa93-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9aa93-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="9aa93-107">Quando você usa a palavra-chave Hidden em um script, você oculta os membros de uma classe por padrão.</span><span class="sxs-lookup"><span data-stu-id="9aa93-107">When you use the Hidden keyword in a script, you hide the members of a class by default.</span></span> <span data-ttu-id="9aa93-108">A palavra-chave Hidden pode ocultar propriedades, métodos (incluindo construtores, eventos, propriedades de alias e outros tipos de membros, incluindo membros estáticos, dos resultados padrão do cmdlet Get-Member e dos resultados do IntelliSense e da conclusão da guia.</span><span class="sxs-lookup"><span data-stu-id="9aa93-108">The Hidden keyword can hide properties, methods (including constructors, events, alias properties, and other member types, including static members, from the default results of the Get-Member cmdlet, and from IntelliSense and tab completion results.</span></span> <span data-ttu-id="9aa93-109">Para exibir os membros que você ocultou com a palavra-chave Hidden, adicione o parâmetro-Force a um comando Get-Member.</span><span class="sxs-lookup"><span data-stu-id="9aa93-109">To display members that you have hidden with the Hidden keyword, add the -Force parameter to a Get-Member command.</span></span>

<span data-ttu-id="9aa93-110">Os membros ocultos não são exibidos usando o preenchimento com Tab ou o IntelliSense, a menos que a conclusão ocorra na classe que define o membro oculto.</span><span class="sxs-lookup"><span data-stu-id="9aa93-110">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="9aa93-111">Um novo atributo, System. Management. Automation. Hiddenattribute, foi adicionado, para que \# o código C possa ter a mesma semântica no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9aa93-111">A new attribute, System.Management.Automation.HiddenAttribute, has been added, so that C\# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="9aa93-112">A palavra-chave Hidden é útil para criar propriedades e métodos dentro de uma classe que você não necessariamente deseja que outros usuários da classe vejam ou possam editar prontamente.</span><span class="sxs-lookup"><span data-stu-id="9aa93-112">The Hidden keyword is useful for creating properties and methods within a class that you do not necessarily want other users of the class to see, or readily be able to edit.</span></span>

<span data-ttu-id="9aa93-113">A palavra-chave Hidden não tem nenhum efeito sobre como você pode exibir ou fazer alterações nos membros de uma classe.</span><span class="sxs-lookup"><span data-stu-id="9aa93-113">The Hidden keyword has no effect on how you can view or make changes to members of a class.</span></span> <span data-ttu-id="9aa93-114">Como todas as palavras-chave de idioma no PowerShell, Hidden não diferencia maiúsculas de minúsculas e os membros ocultos ainda são públicos.</span><span class="sxs-lookup"><span data-stu-id="9aa93-114">Like all language keywords in PowerShell, Hidden is not case-sensitive, and hidden members are still public.</span></span>

<span data-ttu-id="9aa93-115">Oculto, juntamente com classes personalizadas, foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="9aa93-115">Hidden, along with custom classes, was introduced in PowerShell 5.0.</span></span>

## <a name="example"></a><span data-ttu-id="9aa93-116">EXEMPLO</span><span class="sxs-lookup"><span data-stu-id="9aa93-116">EXAMPLE</span></span>

<span data-ttu-id="9aa93-117">O exemplo a seguir mostra como usar a palavra-chave Hidden em uma definição de classe.</span><span class="sxs-lookup"><span data-stu-id="9aa93-117">The following example shows how to use the Hidden keyword in a class definition.</span></span> <span data-ttu-id="9aa93-118">O método de classe carro, tem uma propriedade, corridas, que não precisa ser exibida ou alterada (ela simplesmente calcula o número de vezes que a unidade é chamada na classe carro, uma métrica que não é importante para os usuários da classe; considere, por exemplo, que, quando você estiver comprando um carro, não pergunte ao vendedor quantas unidades o carro foi tirado.</span><span class="sxs-lookup"><span data-stu-id="9aa93-118">The Car class method, Drive, has a property, rides, that does not need to be viewed or changed (it merely tallies the number of times that Drive is called on the Car class, a metric that is not important to users of the class; consider, for example, that when you are buying a car, you do not ask the seller on how many drives the car has been taken.</span></span>

<span data-ttu-id="9aa93-119">Como há pouca necessidade de que os usuários da classe alterem essa propriedade, podemos ocultar a propriedade de Get-Member e os resultados de conclusão automática usando a palavra-chave Hidden.</span><span class="sxs-lookup"><span data-stu-id="9aa93-119">Because there is little need for users of the class to change this property, we can hide the property from Get-Member and automatic completion results by using the Hidden keyword.</span></span>

<span data-ttu-id="9aa93-120">Adicione a palavra-chave Hidden inserindo-a na mesma linha de instrução que a propriedade e seu tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="9aa93-120">Add the Hidden keyword by entering it on the same statement line as the property and its data type.</span></span> <span data-ttu-id="9aa93-121">Embora a palavra-chave possa estar em qualquer ordem nessa linha, iniciar a instrução com a palavra-chave Hidden torna mais fácil para você identificar todos os membros que você ocultou posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9aa93-121">Although the keyword can be in any order on this line, starting the statement with the Hidden keyword makes it easier for you later to identify all members that you have hidden.</span></span>

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

<span data-ttu-id="9aa93-122">Agora, crie uma nova instância da classe carro e salve-a em uma variável, \$ TestCar.</span><span class="sxs-lookup"><span data-stu-id="9aa93-122">Now, create a new instance of the Car class, and save it in a variable, \$TestCar.</span></span>

```powershell
$TestCar = [Car]::new()
```

<span data-ttu-id="9aa93-123">Depois de criar a nova instância, redirecione o conteúdo da variável de $TestCar para get-member.</span><span class="sxs-lookup"><span data-stu-id="9aa93-123">After you create the new instance, pipe the contents of the $TestCar variable to Get-Member.</span></span> <span data-ttu-id="9aa93-124">Observe que a propriedade corridas não está entre os membros listados na Get-Member resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="9aa93-124">Observe that the rides property is not among the members listed in the Get-Member command results.</span></span>

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

<span data-ttu-id="9aa93-125">Agora, tente executar Get-Member novamente, mas desta vez, adicione o parâmetro-Force.</span><span class="sxs-lookup"><span data-stu-id="9aa93-125">Now, try running Get-Member again, but this time, add the -Force parameter.</span></span>
<span data-ttu-id="9aa93-126">Observe que os resultados contêm a propriedade corridas oculta, entre outros membros que estão ocultos por padrão.</span><span class="sxs-lookup"><span data-stu-id="9aa93-126">Note that the results contain the hidden rides property, among other members that are hidden by default.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9aa93-127">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9aa93-127">SEE ALSO</span></span>

[<span data-ttu-id="9aa93-128">about_Classes</span><span class="sxs-lookup"><span data-stu-id="9aa93-128">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="9aa93-129">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9aa93-129">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="9aa93-130">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="9aa93-130">about_Wildcards</span></span>](about_Wildcards.md)

[<span data-ttu-id="9aa93-131">Get-Member</span><span class="sxs-lookup"><span data-stu-id="9aa93-131">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

