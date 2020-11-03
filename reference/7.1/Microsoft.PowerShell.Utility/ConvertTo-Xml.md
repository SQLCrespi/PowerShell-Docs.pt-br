---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: 2e7ebe3a528095873dc7ba5ba0deba2905f531ee
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194280"
---
# <span data-ttu-id="b549d-103">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="b549d-103">ConvertTo-Xml</span></span>

## <span data-ttu-id="b549d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b549d-104">SYNOPSIS</span></span>
<span data-ttu-id="b549d-105">Cria uma representação de um objeto baseada em XML.</span><span class="sxs-lookup"><span data-stu-id="b549d-105">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="b549d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b549d-106">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="b549d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b549d-107">DESCRIPTION</span></span>

<span data-ttu-id="b549d-108">O `ConvertTo-Xml` cmdlet cria uma representação [baseada em XML](/dotnet/api/system.xml.xmldocument) de um ou mais objetos .net.</span><span class="sxs-lookup"><span data-stu-id="b549d-108">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="b549d-109">Para usar esse cmdlet, redirecione um ou mais objetos para o cmdlet ou use o parâmetro **InputObject** para especificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="b549d-109">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="b549d-110">Quando você canaliza vários objetos para `ConvertTo-Xml` ou usa o parâmetro **InputObject** para enviar vários objetos, `ConvertTo-Xml` o retorna um único documento XML na memória que inclui representações de todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="b549d-110">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="b549d-111">Esse cmdlet é semelhante a [Export-Clixml](./Export-Clixml.md) , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo [XML de Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) que pode ser reimportado como objetos com [Import-Clixml](./Import-Clixml.md).</span><span class="sxs-lookup"><span data-stu-id="b549d-111">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="b549d-112">`ConvertTo-Xml` Retorna uma representação na memória de um documento XML, para que você possa continuar a processá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b549d-112">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="b549d-113">`ConvertTo-Xml` Não tem uma opção para converter objetos em CLI XML.</span><span class="sxs-lookup"><span data-stu-id="b549d-113">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="b549d-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b549d-114">EXAMPLES</span></span>

### <span data-ttu-id="b549d-115">Exemplo 1: converter uma data em XML</span><span class="sxs-lookup"><span data-stu-id="b549d-115">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="b549d-116">Esse comando converte a data atual (um objeto **DateTime** ) em XML.</span><span class="sxs-lookup"><span data-stu-id="b549d-116">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="b549d-117">Exemplo 2: converter processos em XML</span><span class="sxs-lookup"><span data-stu-id="b549d-117">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="b549d-118">Este comando converte os objetos de processo, que representam todos os processos no computador, em um documento XML.</span><span class="sxs-lookup"><span data-stu-id="b549d-118">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="b549d-119">Os objetos são expandidos para uma profundidade de três níveis.</span><span class="sxs-lookup"><span data-stu-id="b549d-119">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="b549d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b549d-120">PARAMETERS</span></span>

### <span data-ttu-id="b549d-121">-Como</span><span class="sxs-lookup"><span data-stu-id="b549d-121">-As</span></span>

<span data-ttu-id="b549d-122">Determina o formato de saída.</span><span class="sxs-lookup"><span data-stu-id="b549d-122">Determines the output format.</span></span>
<span data-ttu-id="b549d-123">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b549d-123">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b549d-124">Cadeia.</span><span class="sxs-lookup"><span data-stu-id="b549d-124">String.</span></span>
<span data-ttu-id="b549d-125">Retorna uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b549d-125">Returns a single string.</span></span>
- <span data-ttu-id="b549d-126">Fluxo.</span><span class="sxs-lookup"><span data-stu-id="b549d-126">Stream.</span></span>
<span data-ttu-id="b549d-127">Retorna uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b549d-127">Returns an array of strings.</span></span>
- <span data-ttu-id="b549d-128">Documento.</span><span class="sxs-lookup"><span data-stu-id="b549d-128">Document.</span></span>
<span data-ttu-id="b549d-129">Retorna um objeto **XmlDocument** .</span><span class="sxs-lookup"><span data-stu-id="b549d-129">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="b549d-130">O valor padrão é documento.</span><span class="sxs-lookup"><span data-stu-id="b549d-130">The default value is Document.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b549d-131">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="b549d-131">-Depth</span></span>

<span data-ttu-id="b549d-132">Especifica quantos níveis de objetos contidos estão incluídos na representação XML.</span><span class="sxs-lookup"><span data-stu-id="b549d-132">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="b549d-133">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="b549d-133">The default value is 1.</span></span>

<span data-ttu-id="b549d-134">Por exemplo, se as propriedades do objeto também contêm objetos e você deseja salvar uma representação XML das propriedades dos objetos nelas contidos, é necessário especificar uma profundidade igual a 2.</span><span class="sxs-lookup"><span data-stu-id="b549d-134">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="b549d-135">O valor padrão pode ser substituído para o tipo de objeto em questão nos arquivos Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="b549d-135">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="b549d-136">Para obter mais informações, consulte about_Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="b549d-136">For more information, see about_Types.ps1xml.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b549d-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b549d-137">-InputObject</span></span>

<span data-ttu-id="b549d-138">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="b549d-138">Specifies the object to be converted.</span></span> <span data-ttu-id="b549d-139">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="b549d-139">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="b549d-140">Você também pode canalizar objetos para **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="b549d-140">You can also pipe objects to **ConvertTo-XML** .</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b549d-141">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="b549d-141">-NoTypeInformation</span></span>

<span data-ttu-id="b549d-142">Omite o atributo Type dos nós do objeto.</span><span class="sxs-lookup"><span data-stu-id="b549d-142">Omits the Type attribute from the object nodes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b549d-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b549d-143">CommonParameters</span></span>

<span data-ttu-id="b549d-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b549d-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b549d-145">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b549d-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b549d-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b549d-146">INPUTS</span></span>

### <span data-ttu-id="b549d-147">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="b549d-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b549d-148">É possível canalizar qualquer objeto para **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="b549d-148">You can pipe any object to **ConvertTo-XML** .</span></span>

## <span data-ttu-id="b549d-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b549d-149">OUTPUTS</span></span>

### <span data-ttu-id="b549d-150">Documento System. String ou System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="b549d-150">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="b549d-151">*O valor do parâmetro as* determina o tipo de objeto que o **ConvertTo-XML** retorna.</span><span class="sxs-lookup"><span data-stu-id="b549d-151">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="b549d-152">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b549d-152">NOTES</span></span>

## <span data-ttu-id="b549d-153">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b549d-153">RELATED LINKS</span></span>

[<span data-ttu-id="b549d-154">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="b549d-154">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="b549d-155">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="b549d-155">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="b549d-156">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="b549d-156">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="b549d-157">Obter Data</span><span class="sxs-lookup"><span data-stu-id="b549d-157">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="b549d-158">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="b549d-158">Import-Clixml</span></span>](Import-Clixml.md)

