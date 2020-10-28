---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Classificação de objetos
description: O cmdlet Sort-Object permite que você classifique uma coleção de objetos em uma ou mais propriedades.
ms.openlocfilehash: 836207adfc566003e9714e45920d9b4e24a677e9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501007"
---
# <a name="sorting-objects"></a><span data-ttu-id="daece-104">Classificação de objetos</span><span class="sxs-lookup"><span data-stu-id="daece-104">Sorting Objects</span></span>

<span data-ttu-id="daece-105">É possível organizar os dados exibidos para facilitar a verificação usando o cmdlet `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="daece-105">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="daece-106">`Sort-Object` usa o nome de uma ou mais propriedades para classificar e retorna os dados classificados pelos valores dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="daece-106">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="daece-107">Classificação básica</span><span class="sxs-lookup"><span data-stu-id="daece-107">Basic sorting</span></span>

<span data-ttu-id="daece-108">Pense no problema de listar os subdiretórios e os arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="daece-108">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="daece-109">Se quisermos classificar por **LastWriteTime** e depois por **Nome** , poderemos fazer isso digitando:</span><span class="sxs-lookup"><span data-stu-id="daece-109">If we want to sort by **LastWriteTime** and then by **Name** , we can do it by typing:</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

<span data-ttu-id="daece-110">Você também pode classificar os objetos na ordem inversa, especificando o parâmetro de opção **Descending** .</span><span class="sxs-lookup"><span data-stu-id="daece-110">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a><span data-ttu-id="daece-111">Usando tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="daece-111">Using hash tables</span></span>

<span data-ttu-id="daece-112">Você pode classificar diferentes propriedades em ordens diferentes usando tabelas de hash em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="daece-112">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="daece-113">Cada tabela de hash usa uma chave **Expression** para especificar o nome da propriedade como uma cadeia de caracteres e uma chave **Ascending** ou **Descending** para especificar a ordem de classificação por `$true` ou `$false`.</span><span class="sxs-lookup"><span data-stu-id="daece-113">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="daece-114">A chave **Expression** é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="daece-114">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="daece-115">A chave **Ascending** ou **Descending** é opcional.</span><span class="sxs-lookup"><span data-stu-id="daece-115">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="daece-116">O exemplo a seguir classifica os objetos em ordem decrescente por **LastWriteTime** e ordem crescente por **Name** .</span><span class="sxs-lookup"><span data-stu-id="daece-116">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

<span data-ttu-id="daece-117">Você também pode definir um scriptblock como a chave **Expression** .</span><span class="sxs-lookup"><span data-stu-id="daece-117">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="daece-118">Ao executar o cmdlet `Sort-Object`, o scriptblock é executado e o resultado é usado para classificação.</span><span class="sxs-lookup"><span data-stu-id="daece-118">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="daece-119">O exemplo a seguir classifica objetos em ordem decrescente pelo período de tempo entre **CreationTime** e **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="daece-119">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a><span data-ttu-id="daece-120">Dicas</span><span class="sxs-lookup"><span data-stu-id="daece-120">Tips</span></span>

<span data-ttu-id="daece-121">Você pode omitir o nome do parâmetro **Property** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="daece-121">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="daece-122">Além disso, é possível consultar `Sort-Object` por seu alias interno, `sort`:</span><span class="sxs-lookup"><span data-stu-id="daece-122">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="daece-123">As chaves nas tabelas de hash para a classificação podem ser abreviadas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="daece-123">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="daece-124">Neste exemplo, o **e** significa **Expression** , o **d** significa **Descending** e o **a** significa **Ascending** .</span><span class="sxs-lookup"><span data-stu-id="daece-124">In this example, the **e** stands for **Expression** , the **d** stands for **Descending** , and the **a** stands for **Ascending** .</span></span>

<span data-ttu-id="daece-125">Para melhorar a legibilidade, você pode colocar as tabelas de hash em uma variável separada:</span><span class="sxs-lookup"><span data-stu-id="daece-125">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
