---
title: Estendendo objetos de saída | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a252e0ec-d456-42d7-bd49-d6b8bc57f388
caps.latest.revision: 11
ms.openlocfilehash: 12a826363221b8a7ce06245c787a7bd0529e42f8
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83690906"
---
# <a name="extending-output-objects"></a>Estender os objetos de saída

Você pode estender os objetos de .NET Framework que são retornados por cmdlets, funções e scripts usando arquivos de tipos (. ps1xml). Os arquivos de tipos são arquivos baseados em XML que permitem adicionar propriedades e métodos a objetos existentes. Por exemplo, o Windows PowerShell fornece o arquivo Types. ps1xml, que adiciona elementos a vários objetos de .NET Framework existentes. O arquivo Types. ps1xml está localizado no diretório de instalação do Windows PowerShell ( `$pshome` ). Você pode criar seu próprio arquivo de tipos para estender ainda mais esses objetos ou para estender outros objetos. Quando você estende um objeto usando um arquivo de tipos, qualquer instância do objeto é estendida com os novos elementos.

## <a name="extending-the-systemarray-object"></a>Estendendo o objeto System. array

O exemplo a seguir mostra como o Windows PowerShell estende o objeto [System. array](/dotnet/api/System.Array) no arquivo Types. ps1xml. Por padrão, os objetos [System. array](/dotnet/api/System.Array) têm uma `Length` propriedade que lista o número de objetos na matriz. No entanto, como o nome "Length" não descreve claramente a propriedade, o Windows PowerShell adiciona a `Count` Propriedade Alias, que exibe o mesmo valor que a `Length` propriedade. O XML a seguir adiciona a `Count` propriedade ao tipo [System. array](/dotnet/api/System.Array) .

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>

```

Para ver essa nova propriedade de alias, use um comando [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) em qualquer matriz, conforme mostrado no exemplo a seguir.

```powershell
Get-Member -InputObject (1,2,3,4)
```

O comando retorna os seguintes resultados.

```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```

Você pode usar a `Count` propriedade ou a `Length` propriedade para determinar quantos objetos estão em uma matriz. Por exemplo:

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a>Arquivos de tipos personalizados

Para criar um arquivo de tipos personalizados, comece copiando um arquivo de tipos existente. O novo arquivo pode ter qualquer nome, mas deve ter uma extensão de nome de arquivo. ps1xml. Ao copiar o arquivo, você pode colocá-lo em qualquer diretório que seja acessível ao Windows PowerShell, mas é útil colocá-los no diretório de instalação do Windows PowerShell ( `$pshome` ) ou em um subdiretório do diretório de instalação.

Para adicionar seus próprios tipos estendidos ao arquivo, adicione um elemento de tipos para cada objeto que você deseja estender. Os tópicos a seguir fornecem exemplos.

- Para obter mais informações sobre a adição de propriedades e conjuntos de propriedades, consulte [Propriedades estendidas](./extending-properties-for-objects.md)

- Para obter mais informações sobre como adicionar métodos, consulte [métodos estendidos](./defining-default-methods-for-objects.md).

- Para obter mais informações sobre como adicionar conjuntos de membros, consulte [conjuntos de membros estendidos](./defining-default-member-sets-for-objects.md).

Depois de definir seus próprios tipos estendidos, use um dos seguintes métodos para disponibilizar seus objetos estendidos:

- Para tornar o arquivo de tipos estendidos disponível para a sessão atual, use o cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) para adicionar o novo arquivo. Se você quiser que seus tipos tenham precedência sobre os tipos que são definidos em outros tipos de arquivos (incluindo o arquivo Types. ps1xml), use o `PrependData` parâmetro do cmdlet [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) .
- Para disponibilizar o arquivo de tipos estendidos para todas as sessões futuras, adicione o arquivo de tipos a um módulo, exporte a sessão atual ou adicione o comando [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) ao seu perfil do Windows PowerShell.

## <a name="signing-types-files"></a>Arquivos de tipos de assinatura

Os arquivos de tipos devem ser assinados digitalmente para evitar a violação, pois o XML pode incluir blocos de script. Para obter mais informações sobre como adicionar assinaturas digitais, consulte [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)

## <a name="see-also"></a>Consulte Também

[Definindo propriedades padrão para objetos](./extending-properties-for-objects.md)

[Definir os métodos padrão para objetos](./defining-default-methods-for-objects.md)

[Definir os conjuntos de membro padrão para objetos](./defining-default-member-sets-for-objects.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
