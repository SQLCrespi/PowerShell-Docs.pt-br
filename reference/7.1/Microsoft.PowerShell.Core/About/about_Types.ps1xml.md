---
description: Explica como usar `Types.ps1xml` arquivos para estender os tipos de objetos que são usados no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 66c319a6f1e84fb2d7aeea60433a2ddea9fb4616
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195917"
---
# <a name="about-typesps1xml"></a>Sobre o Types.ps1XML

## <a name="short-description"></a>Descrição breve
Explica como usar `Types.ps1xml` arquivos para estender os tipos de objetos que são usados no PowerShell.

## <a name="long-description"></a>Descrição longa

Os dados de tipo estendido definem propriedades e métodos adicionais ("Membros") de tipos de objeto no PowerShell. Há duas técnicas para adicionar dados de tipo estendido a uma sessão do PowerShell.

- `Types.ps1xml` arquivo: um arquivo XML que define dados de tipo estendido.
- `Update-TypeData`: Um cmdlet que recarrega `Types.ps1xml` arquivos e define dados estendidos para tipos na sessão atual.

Este tópico descreve `Types.ps1xml` os arquivos do. Para obter mais informações sobre como usar o `Update-TypeData` cmdlet para adicionar dados de tipo estendido dinâmico à sessão atual [, consulte Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).

## <a name="about-extended-type-data"></a>Sobre os dados de tipo estendido

Os dados de tipo estendido definem propriedades e métodos adicionais ("Membros") de tipos de objeto no PowerShell. Você pode estender qualquer tipo com suporte no PowerShell e usar as propriedades e os métodos adicionados da mesma maneira que usa as propriedades definidas nos tipos de objeto.

Por exemplo, o PowerShell adiciona uma propriedade **DateTime** a todos os `System.DateTime` objetos, como aqueles que o `Get-Date` cmdlet retorna.

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

Você não encontrará a propriedade **DateTime** na descrição da estrutura [System. DateTime](/dotnet/api/system.datetime) , porque o PowerShell adiciona a propriedade e ela é visível somente no PowerShell.

O PowerShell define internamente um conjunto padrão de tipos estendidos. Essas informações de tipo são carregadas em todas as sessões do PowerShell na inicialização. A propriedade **DateTime** faz parte desse conjunto padrão. Antes do PowerShell 6, as definições de tipo eram armazenadas no `Types.ps1xml` diretório de instalação do PowerShell ( `$PSHOME` ).

## <a name="adding-extended-type-data-to-powershell"></a>Adicionando dados de tipo estendido ao PowerShell

Há três fontes de dados de tipo estendido em sessões do PowerShell.

- O definido pelo PowerShell e é carregado automaticamente em cada sessão do PowerShell. A partir do PowerShell 6, essas informações são compiladas no PowerShell e não são mais enviadas em um `Types.ps1xml` arquivo.

- Os `Types.ps1xml` arquivos que os módulos exportam são carregados quando o módulo é importado para a sessão atual.

- Os dados de tipo estendido que são definidos usando o `Update-TypeData` cmdlet são adicionados somente à sessão atual. Ele não é salvo em um arquivo.

Na sessão, os dados de tipo estendido das três fontes são aplicados aos objetos da mesma maneira e estão disponíveis em todos os objetos dos tipos especificados.

## <a name="the-typedata-cmdlets"></a>Os cmdlets TypeData

Os cmdlets a seguir estão incluídos no módulo **Microsoft. PowerShell. Utility** no PowerShell 3,0 e posterior.

- `Get-TypeData`: Obtém dados de tipo estendido na sessão atual.
- `Update-TypeData`: Recarrega `Types.ps1xml` os arquivos. Adiciona dados de tipo estendido à sessão atual.
- `Remove-TypeData`: Remove dados de tipo estendido da sessão atual.

Para obter mais informações sobre esses cmdlets, consulte o tópico da ajuda para cada cmdlet.

## <a name="built-in-typesps1xml-files"></a>Arquivos XML internos Types.ps1

Os `Types.ps1xml` arquivos no `$PSHOME` diretório são adicionados automaticamente a cada sessão.

O `Types.ps1xml` arquivo no diretório de instalação do PowerShell ( `$PSHOME` ) é um arquivo de texto baseado em XML que permite adicionar propriedades e métodos aos objetos usados no PowerShell. O PowerShell tem arquivos internos `Types.ps1xml` que adicionam vários elementos aos tipos .net, mas você pode criar arquivos adicionais `Types.ps1xml` para estender ainda mais os tipos.

Por exemplo, por padrão, os objetos de matriz ( `System.Array` ) têm uma propriedade **Length** que lista o número de objetos na matriz. No entanto, como o **comprimento** do nome não descreve claramente a propriedade, o PowerShell adiciona uma propriedade de alias chamada **Count** que exibe o mesmo valor. O XML a seguir adiciona a propriedade **Count** ao `System.Array` tipo.

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

Para obter o novo **AliasProperty** , use um `Get-Member` comando em qualquer matriz, conforme mostrado no exemplo a seguir.

```powershell
Get-Member -InputObject (1,2,3,4)
```

O comando retorna os seguintes resultados.

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

Como resultado, você pode usar a propriedade **Count** ou a propriedade **Length** de matrizes no PowerShell. Por exemplo:

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a>Criando novos arquivos XML Types.ps1

Os `.ps1xml` arquivos instalados com o PowerShell são assinados digitalmente para evitar a violação, pois a formatação pode incluir blocos de script. Portanto, para adicionar uma propriedade ou um método a um tipo .NET, crie seus próprios `Types.ps1xml` arquivos e, em seguida, adicione-os à sua sessão do PowerShell.

Para criar um novo arquivo, comece copiando um `Types.ps1xml` arquivo existente. O novo arquivo pode ter qualquer nome, mas deve ter uma `.ps1xml` extensão de nome de arquivo. Você pode posicionar o novo arquivo em qualquer diretório que esteja acessível ao PowerShell, mas é útil posicionar os arquivos no diretório de instalação do PowerShell ( `$PSHOME` ) ou em um subdiretório do diretório de instalação.

Depois de salvar o novo arquivo, use o `Update-TypeData` cmdlet para adicionar o novo arquivo à sua sessão do PowerShell. Se você quiser que os tipos tenham precedência sobre os tipos internos definidos, use o parâmetro **PrependData** do `Update-TypeData` cmdlet. `Update-TypeData` afeta apenas a sessão atual. Para fazer a alteração em todas as sessões futuras, exporte o console ou adicione o `Update-TypeData` comando ao seu perfil do PowerShell.

## <a name="typesps1xml-and-add-member"></a>Types.ps1XML e Add-Member

Os `Types.ps1xml` arquivos adicionam Propriedades e métodos a todas as instâncias dos objetos do tipo .net especificado na sessão do PowerShell afetada. No entanto, se você precisar adicionar propriedades ou métodos somente a uma instância de um objeto, use o `Add-Member` cmdlet.

Para obter mais informações, consulte [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a>Exemplo: adicionando um membro age a objetos FileInfo

Este exemplo mostra como adicionar uma propriedade **age** aos objetos **System. IO. FileInfo** . A idade de um arquivo é a diferença entre sua hora de criação e a hora atual em dias.

Como a propriedade **age** é calculada usando um bloco de script, localize uma `<ScriptProperty>` marca a ser usada como modelo para a nova propriedade **age** .

Salve o código XML a seguir no arquivo `$PSHOME\MyTypes.ps1xml` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

Execute `Update-TypeData` para adicionar o novo `Types.ps1xml` arquivo à sessão atual. O comando usa o parâmetro **PrependData** para posicionar o novo arquivo em uma ordem de precedência maior do que as definições originais.

Para obter mais informações sobre o `Update-TypeData` , consulte [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

Para testar a alteração, execute um `Get-ChildItem` comando para obter o arquivo de PowerShell.exe no `$PSHOME` diretório e, em seguida, direcione o arquivo para o `Format-List` cmdlet para listar todas as propriedades do arquivo. Como resultado da alteração, a propriedade **age** aparece na lista.

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a>O XML em arquivos Types.ps1XML

A definição de esquema completa pode ser encontrada em [Types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) no repositório de código-fonte do PowerShell no github.

A `<Types>` marca inclui todos os tipos que estão definidos no arquivo. Deve haver apenas uma `<Types>` marca.

Cada tipo de .NET mencionado no arquivo deve ser representado por uma `<Type>` marca.

As marcas de tipo devem conter as seguintes marcas:

`<Name>`: Inclui o nome do tipo .NET afetado.

`<Members>`: Inclui as marcas para as novas propriedades e métodos que são definidos para o tipo .NET.

Qualquer uma das seguintes marcas de membro pode estar dentro da `<Members>` marca.

`<AliasProperty>`: Define um novo nome para uma propriedade existente.

A `<AliasProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<ReferencedMemberName>` marca que especifica a propriedade existente.

Por exemplo, a propriedade de alias **Count** é um alias para a propriedade **Length** de objetos de matriz.

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

`<CodeMethod>`: Faz referência a um método estático de uma classe .NET.

A `<CodeMethod>` marca deve ter uma `<Name>` marca que especifica o nome do novo método e uma `<GetCodeReference>` marca que especifica o código no qual o método é definido.

Por exemplo, a propriedade **Mode** de `System.IO.DirectoryInfo` objetos é uma propriedade de código definida no provedor de sistema de arquivos do PowerShell.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<CodeProperty>`: Faz referência a um método estático de uma classe .NET.

A `<CodeProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<GetCodeReference>` marca que especifica o código no qual a propriedade é definida.

Por exemplo, a propriedade **Mode** de `System.IO.DirectoryInfo` objetos é uma propriedade de código definida no provedor de sistema de arquivos do PowerShell.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<MemberSet>`: Define uma coleção de Membros (Propriedades e métodos).

As `<MemberSet>` marcas aparecem dentro das marcas primárias `<Members>` . As marcas devem incluir uma `<Name>` marca ao redor do nome do conjunto de membros e uma `<Members>` marca secundária que envolve os membros (Propriedades e métodos) no conjunto. Qualquer uma das marcas que criam uma propriedade (como `<NoteProperty>` ou `<ScriptProperty>` ) ou um método (como `<Method>` ou `<ScriptMethod>` ) pode ser membros do conjunto.

Em `Types.ps1xml` arquivos, a `<MemberSet>` marca é usada para definir as exibições padrão dos objetos .net no PowerShell. Nesse caso, o nome do conjunto de Membros (o valor dentro das `<Name>` marcas) é sempre **PSStandardMembers** e os nomes das propriedades (o valor da `<Name>` marca) são um dos seguintes:

- `DefaultDisplayProperty`: Uma única propriedade de um objeto.

- `DefaultDisplayPropertySet`: Uma ou mais propriedades de um objeto.

- `DefaultKeyPropertySet`: Uma ou mais propriedades de chave de um objeto. Uma propriedade de chave identifica instâncias de valores de propriedade, como o número de identificação de itens em um histórico de sessão.

Por exemplo, o XML a seguir define a exibição padrão de serviços ( `System.ServiceProcess.ServiceController` objetos) que são retornados pelo `Get-Service` cmdlet. Ele define um conjunto de membros denominado **PSStandardMembers** que consiste em uma propriedade padrão definida com as propriedades **status** , **Name** e **DisplayName** .

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<Method>`: Faz referência a um método nativo do objeto subjacente.

`<Methods>`: Uma coleção de métodos do objeto.

`<NoteProperty>`: Define uma propriedade com um valor estático.

A `<NoteProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<Value>` marca que especifica o valor da propriedade.

Por exemplo, o XML a seguir cria uma propriedade de **status** para objetos **System. IO. DirectoryInfo** . O valor da propriedade **status** é sempre **êxito** .

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

`<ParameterizedProperty>`: Propriedades que usam argumentos e retornam um valor.

`<Properties>`: Uma coleção das propriedades do objeto.

`<Property>`: Uma propriedade do objeto base.

`<PropertySet>`: Define uma coleção de propriedades do objeto.

A `<PropertySet>` marca deve ter uma `<Name>` marca que especifica o nome do conjunto de propriedades e uma `<ReferencedProperty>` marca que especifica as propriedades. Os nomes das propriedades são colocados na `<Name>` marca.

No `Types.ps1xml` , as `<PropertySet>` marcas são usadas para definir conjuntos de propriedades para a exibição padrão de um objeto. Você pode identificar as exibições padrão pelo valor **PSStandardMembers** na `<Name>` marca de uma `<MemberSet>` marca.

Por exemplo, o XML a seguir cria uma propriedade de **status** para o `System.IO.DirectoryInfo` objeto. O valor da propriedade **status** é sempre **êxito** .

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<ScriptMethod>`: Define um método cujo valor é a saída de um script.

A `<ScriptMethod>` marca deve ter uma `<Name>` marca que especifica o nome do novo método e uma `<Script>` marca que inclui o bloco de script que retorna o resultado do método.

Por exemplo, os `ConvertToDateTime` `ConvertFromDateTime` métodos e dos objetos de gerenciamento ( `System.System.Management.ManagementObject` ) são métodos de script que usam os `ToDateTime` `ToDmtfDateTime` métodos estáticos e da `System.Management.ManagementDateTimeConverter` classe.

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

`<ScriptProperty>`: Define uma propriedade cujo valor é a saída de um script.

A `<ScriptProperty>` marca deve ter uma `<Name>` marca que especifica o nome da nova propriedade e uma `<GetScriptBlock>` marca que inclui o bloco de script que retorna o valor da propriedade.

Por exemplo, a propriedade **VERSIONINFO** do objeto **System. IO. FileInfo** é uma propriedade de script resultante do uso da propriedade **FullName** do método estático **GetVersionInfo** de objetos **System. Diagnostics. FileVersionInfo** .

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

Para obter mais informações, consulte o [SDK (Software Development Kit) do Windows PowerShell](/powershell/scripting/developer/windows-powershell).

## <a name="update-typedata"></a>Update-TypeData

Para carregar os `Types.ps1xml` arquivos em uma sessão do PowerShell, execute o `Update-TypeData` cmdlet. Se você quiser que os tipos em seu arquivo tenham precedência sobre os tipos no arquivo interno `Types.ps1xml` , adicione o parâmetro **PrependData** de `Update-TypeData` . `Update-TypeData` afeta apenas a sessão atual. Para fazer a alteração em todas as sessões futuras, exporte a sessão ou adicione o `Update-TypeData` comando ao seu perfil do PowerShell.

Exceções que ocorrem em Propriedades ou adicionando Propriedades a um `Update-TypeData` comando, não Relate erros ao `StdErr` . Isso é para suprimir exceções que podem ocorrer em muitos tipos comuns durante a formatação e a saída. Se você estiver obtendo propriedades do .NET, poderá contornar a supressão de exceções usando a sintaxe do método, conforme mostrado no exemplo a seguir:

```powershell
"hello".get_Length()
```

Observe que a sintaxe do método só pode ser usada com as propriedades do .NET. As propriedades que são adicionadas executando o `Update-TypeData` cmdlet não podem usar a sintaxe do método.

## <a name="signing-a-typesps1xml-file"></a>Assinando um arquivo XML Types.ps1

Para proteger os usuários de seu `Types.ps1xml` arquivo, você pode assinar o arquivo usando uma assinatura digital. Para obter mais informações, consulte [about_Signing](about_Signing.md).

## <a name="see-also"></a>Confira também

[about_Signing](about_Signing.md)

[Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)

[Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Get-TypeData](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[Remove-TypeData](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData)

