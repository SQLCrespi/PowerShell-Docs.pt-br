---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: 62d88dc105121ea0f6194dcdcfe3a234b654c6ee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194986"
---
# <span data-ttu-id="517d6-103">Select-Xml</span><span class="sxs-lookup"><span data-stu-id="517d6-103">Select-Xml</span></span>

## <span data-ttu-id="517d6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="517d6-104">SYNOPSIS</span></span>
<span data-ttu-id="517d6-105">Localiza texto em uma cadeia de caracteres ou documento XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-105">Finds text in an XML string or document.</span></span>

## <span data-ttu-id="517d6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="517d6-106">SYNTAX</span></span>

### <span data-ttu-id="517d6-107">XML (padrão)</span><span class="sxs-lookup"><span data-stu-id="517d6-107">Xml (Default)</span></span>

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="517d6-108">Caminho</span><span class="sxs-lookup"><span data-stu-id="517d6-108">Path</span></span>

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="517d6-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="517d6-109">LiteralPath</span></span>

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="517d6-110">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="517d6-110">Content</span></span>

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="517d6-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="517d6-111">DESCRIPTION</span></span>

<span data-ttu-id="517d6-112">O cmdlet **Select-XML** permite que você use consultas XPath para Pesquisar texto em cadeias de caracteres e documentos XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-112">The **Select-Xml** cmdlet lets you use XPath queries to search for text in XML strings and documents.</span></span>
<span data-ttu-id="517d6-113">Insira uma consulta XPath e use o parâmetro *Content* , *Path* ou *XML* para especificar o XML a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="517d6-113">Enter an XPath query, and use the *Content* , *Path* , or *Xml* parameter to specify the XML to be searched.</span></span>

## <span data-ttu-id="517d6-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="517d6-114">EXAMPLES</span></span>

### <span data-ttu-id="517d6-115">Exemplo 1: selecionar nós AliasProperty</span><span class="sxs-lookup"><span data-stu-id="517d6-115">Example 1: Select AliasProperty nodes</span></span>

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

<span data-ttu-id="517d6-116">Este exemplo obtém as propriedades de alias no Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="517d6-116">This example gets the alias properties in the Types.ps1xml.</span></span>
<span data-ttu-id="517d6-117">(Para obter informações sobre esse arquivo, consulte about_Types.ps1xml.)</span><span class="sxs-lookup"><span data-stu-id="517d6-117">(For information about this file, see about_Types.ps1xml.)</span></span>

<span data-ttu-id="517d6-118">O primeiro comando salva o caminho para o arquivo Types.ps1xml na variável $Path.</span><span class="sxs-lookup"><span data-stu-id="517d6-118">The first command saves the path to the Types.ps1xml file in the $Path variable.</span></span>

<span data-ttu-id="517d6-119">O segundo comando salva o caminho XML para o nó AliasProperty na variável $XPath.</span><span class="sxs-lookup"><span data-stu-id="517d6-119">The second command saves the XML path to the AliasProperty node in the $XPath variable.</span></span>

<span data-ttu-id="517d6-120">O terceiro comando usa o **Select-Xml** para obter os nós de AliasProperty que são identificados pela instrução XPath do arquivo Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="517d6-120">The third command uses the **Select-Xml** cmdlet to get the AliasProperty nodes that are identified by the XPath statement from the Types.ps1xml file.</span></span>
<span data-ttu-id="517d6-121">O comando usa um operador de pipeline para enviar os nós AliasProperty para o cmdlet Select-Object.</span><span class="sxs-lookup"><span data-stu-id="517d6-121">The command uses a pipeline operator to send the AliasProperty nodes to the Select-Object cmdlet.</span></span>
<span data-ttu-id="517d6-122">O parâmetro *ExpandProperty* expande o objeto **node** e retorna suas propriedades Name e ReferencedMemberName.</span><span class="sxs-lookup"><span data-stu-id="517d6-122">The *ExpandProperty* parameter expands the **Node** object and returns its Name and ReferencedMemberName properties.</span></span>

<span data-ttu-id="517d6-123">O resultado mostra o Name e ReferencedMemberName de cada propriedade de alias no arquivo Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="517d6-123">The result shows the Name and ReferencedMemberName of each alias property in the Types.ps1xml file.</span></span>
<span data-ttu-id="517d6-124">Por exemplo, há uma propriedade **Count** que é um alias da propriedade **Length** .</span><span class="sxs-lookup"><span data-stu-id="517d6-124">For example, there is a **Count** property that is an alias of the **Length** property.</span></span>

### <span data-ttu-id="517d6-125">Exemplo 2: inserir um documento XML</span><span class="sxs-lookup"><span data-stu-id="517d6-125">Example 2: Input an XML document</span></span>

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

<span data-ttu-id="517d6-126">Este exemplo mostra como usar o parâmetro *XML* para fornecer um documento XML para o cmdlet **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="517d6-126">This example shows how to use the *XML* parameter to provide an XML document to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="517d6-127">O primeiro comando usa o cmdlet Get-Content para obter o conteúdo do arquivo XML Types.ps1e salvá-lo na variável $Types.</span><span class="sxs-lookup"><span data-stu-id="517d6-127">The first command uses the Get-Content cmdlet to get the content of the Types.ps1xml file and save it in the $Types variable.</span></span>
<span data-ttu-id="517d6-128">O \[ XML \] converte a variável como um objeto XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-128">The \[xml\] casts the variable as an XML object.</span></span>

<span data-ttu-id="517d6-129">O segundo comando usa o cmdlet **Select-Xml** para obter os nós MethodName no arquivo Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="517d6-129">The second command uses the **Select-Xml** cmdlet to get the MethodName nodes in the Types.ps1xml file.</span></span>
<span data-ttu-id="517d6-130">O comando usa o parâmetro *Xml* para especificar o conteúdo XML na variável $Types e o parâmetro *XPath* para especificar o caminho para o nó MethodName.</span><span class="sxs-lookup"><span data-stu-id="517d6-130">The command uses the *Xml* parameter to specify the XML content in the $Types variable and the *XPath* parameter to specify the path to the MethodName node.</span></span>

### <span data-ttu-id="517d6-131">Exemplo 3: Pesquisar arquivos de ajuda do PowerShell</span><span class="sxs-lookup"><span data-stu-id="517d6-131">Example 3: Search PowerShell Help files</span></span>

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

<span data-ttu-id="517d6-132">Este exemplo mostra como usar o cmdlet **Select-XML** para pesquisar os arquivos de ajuda do cmdlet baseado em XML do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="517d6-132">This example shows how to use the **Select-Xml** cmdlet to search the PowerShell XML-based cmdlet help files.</span></span>
<span data-ttu-id="517d6-133">Neste exemplo, pesquisaremos pelo nome do cmdlet que serve como título para cada arquivo de Ajuda e o caminho para o arquivo de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="517d6-133">In this example, we'll search for the cmdlet name that serves as a title for each help file and the path to the help file.</span></span>

<span data-ttu-id="517d6-134">O primeiro comando cria uma tabela de hash que representa o namespace XML usado nos arquivos de Ajuda e o salva na variável $Namespace.</span><span class="sxs-lookup"><span data-stu-id="517d6-134">The first command creates a hash table that represents the XML namespace that is used for the help files and saves it in the $Namespace variable.</span></span>

### <span data-ttu-id="517d6-135">Exemplo 4: maneiras diferentes de inserir XML</span><span class="sxs-lookup"><span data-stu-id="517d6-135">Example 4: Different ways to input XML</span></span>

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

<span data-ttu-id="517d6-136">Este exemplo mostra duas maneiras diferentes de enviar XML para o cmdlet **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="517d6-136">This example shows two different ways to send XML to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="517d6-137">O primeiro comando salva uma cadeia de caracteres here que contém XML na variável $Xml.</span><span class="sxs-lookup"><span data-stu-id="517d6-137">The first command saves a here-string that contains XML in the $Xml variable.</span></span>
<span data-ttu-id="517d6-138">(Para obter mais informações sobre as here-strings, consulte about_Quoting_Rules).</span><span class="sxs-lookup"><span data-stu-id="517d6-138">(For more information about here-strings, see about_Quoting_Rules.)</span></span>

### <span data-ttu-id="517d6-139">Exemplo 5: usar o namespace padrão xmlns</span><span class="sxs-lookup"><span data-stu-id="517d6-139">Example 5: Use the default xmlns namespace</span></span>

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

<span data-ttu-id="517d6-140">Este exemplo mostra como usar o cmdlet **Select-XML** com documentos XML que usam o namespace padrão xmlns.</span><span class="sxs-lookup"><span data-stu-id="517d6-140">This example shows how to use the **Select-Xml** cmdlet with XML documents that use the default xmlns namespace.</span></span>
<span data-ttu-id="517d6-141">O exemplo obtém os títulos dos arquivos de snippet do Windows PowerShell ISE criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="517d6-141">The example gets the titles of Windows PowerShell ISE user-created snippet files.</span></span>
<span data-ttu-id="517d6-142">Para obter informações sobre os snippets, consulte New-IseSnippet.</span><span class="sxs-lookup"><span data-stu-id="517d6-142">For information about snippets, see New-IseSnippet.</span></span>

<span data-ttu-id="517d6-143">O primeiro comando cria uma tabela de hash para o namespace padrão que os arquivos XML de trecho de código usam e os atribui à variável $SnippetNamespace.</span><span class="sxs-lookup"><span data-stu-id="517d6-143">The first command creates a hash table for the default namespace that snippet XML files use and assigns it to the $SnippetNamespace variable.</span></span>
<span data-ttu-id="517d6-144">O valor da tabela de hash é o URI do esquema XMLNS no snippet XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-144">The hash table value is the XMLNS schema URI in the snippet XML.</span></span>
<span data-ttu-id="517d6-145">O nome da chave da tabela de hash, recorte, é arbitrário.</span><span class="sxs-lookup"><span data-stu-id="517d6-145">The hash table key name, snip, is arbitrary.</span></span>
<span data-ttu-id="517d6-146">Você pode usar qualquer nome que não esteja reservado, mas não pode usar xmlns.</span><span class="sxs-lookup"><span data-stu-id="517d6-146">You can use any name that is not reserved, but you cannot use xmlns.</span></span>

## <span data-ttu-id="517d6-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="517d6-147">PARAMETERS</span></span>

### <span data-ttu-id="517d6-148">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="517d6-148">-Content</span></span>

<span data-ttu-id="517d6-149">Especifica uma cadeia de caracteres que contém o XML a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="517d6-149">Specifies a string that contains the XML to search.</span></span>
<span data-ttu-id="517d6-150">Você também pode canalizar cadeias de caracteres para **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="517d6-150">You can also pipe strings to **Select-Xml** .</span></span>

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

### <span data-ttu-id="517d6-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="517d6-151">-LiteralPath</span></span>

<span data-ttu-id="517d6-152">Especifica os caminhos e nomes de arquivo dos arquivos XML a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="517d6-152">Specifies the paths and file names of the XML files to search.</span></span>
<span data-ttu-id="517d6-153">Ao contrário de *Path* , o valor do parâmetro *LiteralPath* é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="517d6-153">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="517d6-154">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="517d6-154">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="517d6-155">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="517d6-155">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="517d6-156">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="517d6-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="517d6-157">-Namespace</span><span class="sxs-lookup"><span data-stu-id="517d6-157">-Namespace</span></span>

<span data-ttu-id="517d6-158">Especifica uma tabela de hash de namespaces utilizados no XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-158">Specifies a hash table of the namespaces used in the XML.</span></span>
<span data-ttu-id="517d6-159">Use o formato @ { \<namespaceName\>  =  \<namespaceValue\> }.</span><span class="sxs-lookup"><span data-stu-id="517d6-159">Use the format @{\<namespaceName\> = \<namespaceValue\>}.</span></span>

<span data-ttu-id="517d6-160">Quando o XML usa o namespace padrão, que começa com xmlns, use uma chave arbitrária para o nome do namespace.</span><span class="sxs-lookup"><span data-stu-id="517d6-160">When the XML uses the default namespace, which begins with xmlns, use an arbitrary key for the namespace name.</span></span>
<span data-ttu-id="517d6-161">Você não pode usar xmlns.</span><span class="sxs-lookup"><span data-stu-id="517d6-161">You cannot use xmlns.</span></span>
<span data-ttu-id="517d6-162">Na instrução XPath, Prefixe cada nome de nó com o nome do namespace e dois-pontos, como//namespaceName: node.</span><span class="sxs-lookup"><span data-stu-id="517d6-162">In the XPath statement, prefix each node name with the namespace name and a colon, such as //namespaceName:Node.</span></span>

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

### <span data-ttu-id="517d6-163">-Path</span><span class="sxs-lookup"><span data-stu-id="517d6-163">-Path</span></span>

<span data-ttu-id="517d6-164">Especifica os nomes do caminho e do arquivo XML a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="517d6-164">Specifies the path and file names of the XML files to search.</span></span>
<span data-ttu-id="517d6-165">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="517d6-165">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="517d6-166">-XML</span><span class="sxs-lookup"><span data-stu-id="517d6-166">-Xml</span></span>

<span data-ttu-id="517d6-167">Especifica um ou mais nós XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-167">Specifies one or more XML nodes.</span></span>

<span data-ttu-id="517d6-168">Um documento XML será processado como uma coleção de nós XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-168">An XML document will be processed as a collection of XML nodes.</span></span>
<span data-ttu-id="517d6-169">Se você canalizar um documento XML para **Select-XML** , cada nó de documento será pesquisado separadamente à medida que ele se originar no pipeline.</span><span class="sxs-lookup"><span data-stu-id="517d6-169">If you pipe an XML document to **Select-Xml** , each document node will be searched separately as it comes through the pipeline.</span></span>

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

### <span data-ttu-id="517d6-170">-XPath</span><span class="sxs-lookup"><span data-stu-id="517d6-170">-XPath</span></span>

<span data-ttu-id="517d6-171">Especifica uma consulta de pesquisa XPath.</span><span class="sxs-lookup"><span data-stu-id="517d6-171">Specifies an XPath search query.</span></span>
<span data-ttu-id="517d6-172">A linguagem de consulta diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="517d6-172">The query language is case-sensitive.</span></span>
<span data-ttu-id="517d6-173">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="517d6-173">This parameter is required.</span></span>

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

### <span data-ttu-id="517d6-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="517d6-174">CommonParameters</span></span>

<span data-ttu-id="517d6-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="517d6-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="517d6-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="517d6-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="517d6-177">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="517d6-177">INPUTS</span></span>

### <span data-ttu-id="517d6-178">Nó System. String ou System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="517d6-178">System.String or System.Xml.XmlNode</span></span>

<span data-ttu-id="517d6-179">É possível canalizar um caminho ou nó XML para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="517d6-179">You can pipe a path or XML node to this cmdlet.</span></span>

## <span data-ttu-id="517d6-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="517d6-180">OUTPUTS</span></span>

### <span data-ttu-id="517d6-181">Microsoft. PowerShell. Commands. SelectXmlInfo</span><span class="sxs-lookup"><span data-stu-id="517d6-181">Microsoft.PowerShell.Commands.SelectXmlInfo</span></span>

## <span data-ttu-id="517d6-182">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="517d6-182">NOTES</span></span>

* <span data-ttu-id="517d6-183">O XPath é uma linguagem padrão que foi projetada para identificar partes de um documento XML.</span><span class="sxs-lookup"><span data-stu-id="517d6-183">XPath is a standard language that is designed to identify parts of an XML document.</span></span> <span data-ttu-id="517d6-184">Para obter mais informações sobre a linguagem XPath, consulte [referência de XPath](https://msdn.microsoft.com/library/ms256115) e a seção filtros de seleção da seleção de [eventos](https://msdn.microsoft.com/library/aa385231) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="517d6-184">For more information about the XPath language, see [XPath Reference](https://msdn.microsoft.com/library/ms256115) and the Selection Filters section of the [Event Selection](https://msdn.microsoft.com/library/aa385231) in the MSDN library.</span></span>

## <span data-ttu-id="517d6-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="517d6-185">RELATED LINKS</span></span>

[<span data-ttu-id="517d6-186">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="517d6-186">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
