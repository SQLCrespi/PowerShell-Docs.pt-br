---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: e461c07360b3d9eaf7d9a3c8875d34cd1fc841e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598642"
---
# <span data-ttu-id="f0f1c-102">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="f0f1c-102">ConvertTo-Xml</span></span>

## <span data-ttu-id="f0f1c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f0f1c-103">SYNOPSIS</span></span>
<span data-ttu-id="f0f1c-104">Cria uma representação de um objeto baseada em XML.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-104">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="f0f1c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f0f1c-105">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="f0f1c-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f0f1c-106">DESCRIPTION</span></span>

<span data-ttu-id="f0f1c-107">O `ConvertTo-Xml` cmdlet cria uma representação [baseada em XML](/dotnet/api/system.xml.xmldocument) de um ou mais objetos .net.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-107">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="f0f1c-108">Para usar esse cmdlet, redirecione um ou mais objetos para o cmdlet ou use o parâmetro **InputObject** para especificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-108">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="f0f1c-109">Quando você canaliza vários objetos para `ConvertTo-Xml` ou usa o parâmetro **InputObject** para enviar vários objetos, `ConvertTo-Xml` o retorna um único documento XML na memória que inclui representações de todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-109">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="f0f1c-110">Esse cmdlet é semelhante a [Export-Clixml](./Export-Clixml.md) , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo [XML de Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) que pode ser reimportado como objetos com [Import-Clixml](./Import-Clixml.md).</span><span class="sxs-lookup"><span data-stu-id="f0f1c-110">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="f0f1c-111">`ConvertTo-Xml` Retorna uma representação na memória de um documento XML, para que você possa continuar a processá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-111">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="f0f1c-112">`ConvertTo-Xml` Não tem uma opção para converter objetos em CLI XML.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-112">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="f0f1c-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f0f1c-113">EXAMPLES</span></span>

### <span data-ttu-id="f0f1c-114">Exemplo 1: converter uma data em XML</span><span class="sxs-lookup"><span data-stu-id="f0f1c-114">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="f0f1c-115">Esse comando converte a data atual (um objeto **DateTime** ) em XML.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-115">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="f0f1c-116">Exemplo 2: converter processos em XML</span><span class="sxs-lookup"><span data-stu-id="f0f1c-116">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="f0f1c-117">Este comando converte os objetos de processo, que representam todos os processos no computador, em um documento XML.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-117">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="f0f1c-118">Os objetos são expandidos para uma profundidade de três níveis.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-118">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="f0f1c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f0f1c-119">PARAMETERS</span></span>

### <span data-ttu-id="f0f1c-120">-Como</span><span class="sxs-lookup"><span data-stu-id="f0f1c-120">-As</span></span>

<span data-ttu-id="f0f1c-121">Determina o formato de saída.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-121">Determines the output format.</span></span>
<span data-ttu-id="f0f1c-122">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f0f1c-122">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f0f1c-123">Cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-123">String.</span></span>
<span data-ttu-id="f0f1c-124">Retorna uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-124">Returns a single string.</span></span>
- <span data-ttu-id="f0f1c-125">Fluxo.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-125">Stream.</span></span>
<span data-ttu-id="f0f1c-126">Retorna uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-126">Returns an array of strings.</span></span>
- <span data-ttu-id="f0f1c-127">Documento.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-127">Document.</span></span>
<span data-ttu-id="f0f1c-128">Retorna um objeto **XmlDocument** .</span><span class="sxs-lookup"><span data-stu-id="f0f1c-128">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="f0f1c-129">O valor padrão é documento.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-129">The default value is Document.</span></span>

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

### <span data-ttu-id="f0f1c-130">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="f0f1c-130">-Depth</span></span>

<span data-ttu-id="f0f1c-131">Especifica quantos níveis de objetos contidos estão incluídos na representação XML.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-131">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="f0f1c-132">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-132">The default value is 1.</span></span>

<span data-ttu-id="f0f1c-133">Por exemplo, se as propriedades do objeto também contêm objetos e você deseja salvar uma representação XML das propriedades dos objetos nelas contidos, é necessário especificar uma profundidade igual a 2.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-133">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="f0f1c-134">O valor padrão pode ser substituído para o tipo de objeto em questão nos arquivos Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-134">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="f0f1c-135">Para obter mais informações, consulte about_Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-135">For more information, see about_Types.ps1xml.</span></span>

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

### <span data-ttu-id="f0f1c-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f0f1c-136">-InputObject</span></span>

<span data-ttu-id="f0f1c-137">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-137">Specifies the object to be converted.</span></span> <span data-ttu-id="f0f1c-138">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-138">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="f0f1c-139">Você também pode canalizar objetos para **ConvertTo-XML**.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-139">You can also pipe objects to **ConvertTo-XML**.</span></span>

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

### <span data-ttu-id="f0f1c-140">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="f0f1c-140">-NoTypeInformation</span></span>

<span data-ttu-id="f0f1c-141">Omite o atributo Type dos nós do objeto.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-141">Omits the Type attribute from the object nodes.</span></span>

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

### <span data-ttu-id="f0f1c-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f0f1c-142">CommonParameters</span></span>

<span data-ttu-id="f0f1c-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f0f1c-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f0f1c-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f0f1c-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f0f1c-145">INPUTS</span></span>

### <span data-ttu-id="f0f1c-146">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="f0f1c-146">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f0f1c-147">É possível canalizar qualquer objeto para **ConvertTo-XML**.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-147">You can pipe any object to **ConvertTo-XML**.</span></span>

## <span data-ttu-id="f0f1c-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f0f1c-148">OUTPUTS</span></span>

### <span data-ttu-id="f0f1c-149">Documento System. String ou System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="f0f1c-149">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="f0f1c-150">*O valor do parâmetro as* determina o tipo de objeto que o **ConvertTo-XML** retorna.</span><span class="sxs-lookup"><span data-stu-id="f0f1c-150">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="f0f1c-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f0f1c-151">NOTES</span></span>

## <span data-ttu-id="f0f1c-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f0f1c-152">RELATED LINKS</span></span>

[<span data-ttu-id="f0f1c-153">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="f0f1c-153">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="f0f1c-154">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="f0f1c-154">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="f0f1c-155">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="f0f1c-155">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="f0f1c-156">Obter Data</span><span class="sxs-lookup"><span data-stu-id="f0f1c-156">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="f0f1c-157">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="f0f1c-157">Import-Clixml</span></span>](Import-Clixml.md)

