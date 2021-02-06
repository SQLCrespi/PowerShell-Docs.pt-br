---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: 7686ade747345b7c770772067007b8abf13aac3d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603737"
---
# Select-Xml

## SINOPSE
Localiza texto em uma cadeia de caracteres ou documento XML.

## SYNTAX

### XML (padrão)

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Caminho

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### LiteralPath

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Conteúdo

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Select-XML** permite que você use consultas XPath para Pesquisar texto em cadeias de caracteres e documentos XML.
Insira uma consulta XPath e use o parâmetro *Content*, *Path* ou *XML* para especificar o XML a ser pesquisado.

## EXEMPLOS

### Exemplo 1: selecionar nós AliasProperty

```
PS C:\> $Path = "$Pshome\Types.ps1xml"
PS C:\> $XPath = "/Types/Type/Members/AliasProperty"
PS C:\> Select-Xml -Path $Path -XPath $Xpath | Select-Object -ExpandProperty Node
Name                 ReferencedMemberName
----                 --------------------
Count                Length
Name                 Key
Name                 ServiceName
RequiredServices     ServicesDependedOn
ProcessName          Name
Handles              Handlecount
VM                   VirtualSize
WS                   WorkingSetSize
Name                 ProcessName
Handles              Handlecount
VM                   VirtualMemorySize
WS                   WorkingSet
PM                   PagedMemorySize
NPM                  NonpagedSystemMemorySize
Name                 __Class
Namespace            ModuleName
```

Este exemplo obtém as propriedades de alias no Types.ps1xml.
(Para obter informações sobre esse arquivo, consulte about_Types.ps1xml.)

O primeiro comando salva o caminho para o arquivo Types.ps1xml na variável $Path.

O segundo comando salva o caminho XML para o nó AliasProperty na variável $XPath.

O terceiro comando usa o **Select-Xml** para obter os nós de AliasProperty que são identificados pela instrução XPath do arquivo Types.ps1xml.
O comando usa um operador de pipeline para enviar os nós AliasProperty para o cmdlet Select-Object.
O parâmetro *ExpandProperty* expande o objeto **node** e retorna suas propriedades Name e ReferencedMemberName.

O resultado mostra o Name e ReferencedMemberName de cada propriedade de alias no arquivo Types.ps1xml.
Por exemplo, há uma propriedade **Count** que é um alias da propriedade **Length** .

### Exemplo 2: inserir um documento XML

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

Este exemplo mostra como usar o parâmetro *XML* para fornecer um documento XML para o cmdlet **Select-XML** .

O primeiro comando usa o cmdlet Get-Content para obter o conteúdo do arquivo XML Types.ps1e salvá-lo na variável $Types.
O \[ XML \] converte a variável como um objeto XML.

O segundo comando usa o cmdlet **Select-Xml** para obter os nós MethodName no arquivo Types.ps1xml.
O comando usa o parâmetro *Xml* para especificar o conteúdo XML na variável $Types e o parâmetro *XPath* para especificar o caminho para o nó MethodName.

### Exemplo 3: Pesquisar arquivos de ajuda do PowerShell

```
PS C:\> $Namespace = @{command = "http://schemas.microsoft.com/maml/dev/command/2004/10"; maml = "http://schemas.microsoft.com/maml/2004/10"; dev = "http://schemas.microsoft.com/maml/dev/2004/10"}

The second command saves the path to the help files in the $Path variable.If there are no help files in this path on your computer, use the Update-Help cmdlet to download the help files. For more information about Updatable Help, see about_Updatable_Help (https://go.microsoft.com/fwlink/?LinkId=235801).
PS C:\> $Path = "$Pshome\en-us\*dll-Help.xml"

The third command uses the **Select-Xml** cmdlet to search the XML for cmdlet names by finding Command:Name element anywhere in the files. It saves the results in the $Xml variable.**Select-Xml** returns a **SelectXmlInfo** object that has a Node property, which is a **System.Xml.XmlElement** object. The Node property has an InnerXML property, which contains the actual XML that is retrieved.
PS C:\> $Xml = Select-Xml -Path $Path -Namespace $Namespace -XPath "//command:name"

The fourth command sends the XML in the $Xml variable to the Format-Table cmdlet. The **Format-Table** command uses a calculated property to get the Node.InnerXML property of each object in the $Xml variable, trim the white space before and after the text, and display it in the table, along with the path to the source file.
PS C:\> $Xml | Format-Table @{Label="Name"; Expression= {($_.node.innerxml).trim()}}, Path -AutoSize

Name                    Path
----                    ----
Export-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-Counter             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-WinEvent            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Import-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Add-Computer            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Add-Content             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Checkpoint-Computer     C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
...
```

Este exemplo mostra como usar o cmdlet **Select-XML** para pesquisar os arquivos de ajuda do cmdlet baseado em XML do PowerShell.
Neste exemplo, pesquisaremos pelo nome do cmdlet que serve como título para cada arquivo de Ajuda e o caminho para o arquivo de Ajuda.

O primeiro comando cria uma tabela de hash que representa o namespace XML usado nos arquivos de Ajuda e o salva na variável $Namespace.

### Exemplo 4: maneiras diferentes de inserir XML

```
PS C:\> $Xml = @"
<?xml version="1.0" encoding="utf-8"?>
<Book>
  <projects>
    <project name="Book1" date="2009-01-20">
      <editions>
        <edition language="English">En.Book1.com</edition>
        <edition language="German">Ge.Book1.Com</edition>
        <edition language="French">Fr.Book1.com</edition>
        <edition language="Polish">Pl.Book1.com</edition>
      </editions>
    </project>
  </projects>
</Book>
"@

The second command uses the *Content* parameter of **Select-Xml** to specify the XML in the $Xml variable.
PS C:\> Select-Xml -Content $Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com

The third command is equivalent to the second. It uses a pipeline operator (|) to send the XML in the $Xml variable to the **Select-Xml** cmdlet.
PS C:\> $Xml | Select-Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com
```

Este exemplo mostra duas maneiras diferentes de enviar XML para o cmdlet **Select-XML** .

O primeiro comando salva uma cadeia de caracteres here que contém XML na variável $Xml.
(Para obter mais informações sobre as here-strings, consulte about_Quoting_Rules).

### Exemplo 5: usar o namespace padrão xmlns

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

Este exemplo mostra como usar o cmdlet **Select-XML** com documentos XML que usam o namespace padrão xmlns.
O exemplo obtém os títulos dos arquivos de snippet do Windows PowerShell ISE criados pelo usuário.
Para obter informações sobre os snippets, consulte New-IseSnippet.

O primeiro comando cria uma tabela de hash para o namespace padrão que os arquivos XML de trecho de código usam e os atribui à variável $SnippetNamespace.
O valor da tabela de hash é o URI do esquema XMLNS no snippet XML.
O nome da chave da tabela de hash, recorte, é arbitrário.
Você pode usar qualquer nome que não esteja reservado, mas não pode usar xmlns.

## PARAMETERS

### -Conteúdo

Especifica uma cadeia de caracteres que contém o XML a ser pesquisado.
Você também pode canalizar cadeias de caracteres para **Select-XML**.

```yaml
Type: System.String[]
Parameter Sets: Content
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica os caminhos e nomes de arquivo dos arquivos XML a ser pesquisado.
Ao contrário de *Path*, o valor do parâmetro *LiteralPath* é usado exatamente como foi digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Especifica uma tabela de hash de namespaces utilizados no XML.
Use o formato @ { \<namespaceName\>  =  \<namespaceValue\> }.

Quando o XML usa o namespace padrão, que começa com xmlns, use uma chave arbitrária para o nome do namespace.
Você não pode usar xmlns.
Na instrução XPath, Prefixe cada nome de nó com o nome do namespace e dois-pontos, como//namespaceName: node.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica os nomes do caminho e do arquivo XML a ser pesquisado.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -XML

Especifica um ou mais nós XML.

Um documento XML será processado como uma coleção de nós XML.
Se você canalizar um documento XML para **Select-XML**, cada nó de documento será pesquisado separadamente à medida que ele se originar no pipeline.

```yaml
Type: System.Xml.XmlNode[]
Parameter Sets: Xml
Aliases: Node

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -XPath

Especifica uma consulta de pesquisa XPath.
A linguagem de consulta diferencia maiúsculas de minúsculas.
Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nó System. String ou System.Xml.Xml

É possível canalizar um caminho ou nó XML para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. SelectXmlInfo

## OBSERVAÇÕES

O XPath é uma linguagem padrão que foi projetada para identificar partes de um documento XML. Para obter mais informações sobre a linguagem XPath, consulte [referência de XPath](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) e a seção filtros de seleção da seleção de [eventos](/previous-versions//aa385231(v=vs.85)).

## LINKS RELACIONADOS

[ConvertTo-Xml](ConvertTo-Xml.md)
