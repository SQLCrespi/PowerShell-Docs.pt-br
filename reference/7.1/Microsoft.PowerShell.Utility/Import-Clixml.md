---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: d33b74101301ec5806f456ddd9cc73bd8b6bb3e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193560"
---
# <span data-ttu-id="01c3b-103">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="01c3b-103">Import-Clixml</span></span>

## <span data-ttu-id="01c3b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="01c3b-104">SYNOPSIS</span></span>
<span data-ttu-id="01c3b-105">Importa um arquivo CLIXML e cria objetos correspondentes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01c3b-105">Imports a CLIXML file and creates corresponding objects in PowerShell.</span></span>

## <span data-ttu-id="01c3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01c3b-106">SYNTAX</span></span>

### <span data-ttu-id="01c3b-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="01c3b-107">ByPath (Default)</span></span>

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### <span data-ttu-id="01c3b-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="01c3b-108">ByLiteralPath</span></span>

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## <span data-ttu-id="01c3b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01c3b-109">DESCRIPTION</span></span>

<span data-ttu-id="01c3b-110">O `Import-Clixml` cmdlet importa um arquivo XML Common Language Infrastructure (CLI) com dados que representam Microsoft .net objetos do Framework e cria os objetos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01c3b-110">The `Import-Clixml` cmdlet imports a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and creates the PowerShell objects.</span></span> <span data-ttu-id="01c3b-111">Para obter mais informações sobre a CLI, consulte [independência de idioma](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="01c3b-111">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="01c3b-112">Um uso valioso do `Import-Clixml` em computadores Windows é importar credenciais e proteger as cadeias de caracteres que foram exportadas como XML seguro usando o `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="01c3b-112">A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`.</span></span> <span data-ttu-id="01c3b-113">Para obter um exemplo, consulte o exemplo 2.</span><span class="sxs-lookup"><span data-stu-id="01c3b-113">For an example, see Example 2.</span></span>

<span data-ttu-id="01c3b-114">`Import-Clixml` usa a BOM (marca de ordem de byte) para detectar o formato de codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="01c3b-114">`Import-Clixml` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="01c3b-115">Se o arquivo não tiver uma BOM, ele assumirá que a codificação é UTF8.</span><span class="sxs-lookup"><span data-stu-id="01c3b-115">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="01c3b-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="01c3b-116">EXAMPLES</span></span>

### <span data-ttu-id="01c3b-117">Exemplo 1: importar um arquivo serializado e recriar um objeto</span><span class="sxs-lookup"><span data-stu-id="01c3b-117">Example 1: Import a serialized file and recreate an object</span></span>

<span data-ttu-id="01c3b-118">Este exemplo usa o `Export-Clixml` cmdlet para salvar uma cópia serializada das informações do processo retornadas pelo `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="01c3b-118">This example uses the `Export-Clixml` cmdlet to save a serialized copy of the process information returned by `Get-Process`.</span></span> <span data-ttu-id="01c3b-119">`Import-Clixml` Recupera o conteúdo do arquivo serializado e recria um objeto que é armazenado na `$Processes` variável.</span><span class="sxs-lookup"><span data-stu-id="01c3b-119">`Import-Clixml` retrieves the serialized file's contents and recreates an object that is stored in the `$Processes` variable.</span></span>

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### <span data-ttu-id="01c3b-120">Exemplo 2: importar um objeto de credencial de segurança</span><span class="sxs-lookup"><span data-stu-id="01c3b-120">Example 2: Import a secure credential object</span></span>

<span data-ttu-id="01c3b-121">Neste exemplo, dada uma credencial que você armazenou na `$Credential` variável executando o `Get-Credential` cmdlet, você pode executar o `Export-Clixml` cmdlet para salvar a credencial no disco.</span><span class="sxs-lookup"><span data-stu-id="01c3b-121">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01c3b-122">`Export-Clixml` o só exporta credenciais criptografadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="01c3b-122">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="01c3b-123">Em sistemas operacionais não Windows, como macOS e Linux, as credenciais são exportadas em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="01c3b-123">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="01c3b-124">O `Export-Clixml` cmdlet criptografa objetos de credencial usando a [API de proteção de dados](/previous-versions/windows/apps/hh464970(v=win.10))do Windows.</span><span class="sxs-lookup"><span data-stu-id="01c3b-124">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="01c3b-125">A criptografia garante que apenas sua conta de usuário possa descriptografar o conteúdo do objeto de credencial.</span><span class="sxs-lookup"><span data-stu-id="01c3b-125">The encryption ensures that only your user account can decrypt the contents of the credential object.</span></span> <span data-ttu-id="01c3b-126">O arquivo exportado `CLIXML` não pode ser usado em um computador diferente ou por um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="01c3b-126">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="01c3b-127">No exemplo, o arquivo no qual a credencial é armazenada é representado por `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="01c3b-127">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="01c3b-128">Substitua **TestScript** pelo nome do script com o qual você está carregando a credencial.</span><span class="sxs-lookup"><span data-stu-id="01c3b-128">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="01c3b-129">Você envia o objeto de credencial para baixo do pipeline para o `Export-Clixml` , e salva-o no caminho, `$Credxmlpath` , que você especificou no primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="01c3b-129">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="01c3b-130">Para importar a credencial automaticamente para o script, execute os dois comandos finais.</span><span class="sxs-lookup"><span data-stu-id="01c3b-130">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="01c3b-131">Execute `Import-Clixml` para importar o objeto de credencial protegido para o script.</span><span class="sxs-lookup"><span data-stu-id="01c3b-131">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="01c3b-132">Essa importação elimina o risco de expor senhas de texto sem formatação em seu script.</span><span class="sxs-lookup"><span data-stu-id="01c3b-132">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="01c3b-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01c3b-133">PARAMETERS</span></span>

### <span data-ttu-id="01c3b-134">-Primeiro</span><span class="sxs-lookup"><span data-stu-id="01c3b-134">-First</span></span>

<span data-ttu-id="01c3b-135">Obtém somente o número especificado de objetos.</span><span class="sxs-lookup"><span data-stu-id="01c3b-135">Gets only the specified number of objects.</span></span> <span data-ttu-id="01c3b-136">Insira o número de objetos a obter.</span><span class="sxs-lookup"><span data-stu-id="01c3b-136">Enter the number of objects to get.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01c3b-137">-IncludeTotalCount</span><span class="sxs-lookup"><span data-stu-id="01c3b-137">-IncludeTotalCount</span></span>

<span data-ttu-id="01c3b-138">Relata o número total de objetos no conjunto de dados seguido pelos objetos selecionados.</span><span class="sxs-lookup"><span data-stu-id="01c3b-138">Reports the total number of objects in the data set followed by the selected objects.</span></span> <span data-ttu-id="01c3b-139">Se o cmdlet não puder determinar a contagem total, ele exibirá a **contagem total desconhecida** .</span><span class="sxs-lookup"><span data-stu-id="01c3b-139">If the cmdlet can't determine the total count, it displays **Unknown total count** .</span></span> <span data-ttu-id="01c3b-140">O inteiro tem uma propriedade de **precisão** que indica a confiabilidade do valor total da contagem.</span><span class="sxs-lookup"><span data-stu-id="01c3b-140">The integer has an **Accuracy** property that indicates the reliability of the total count value.</span></span> <span data-ttu-id="01c3b-141">O valor de **precisão** varia de `0.0` até `1.0` onde `0.0` significa que o cmdlet não pôde contar os objetos, `1.0` significa que a contagem é exata e um valor entre `0.0` e `1.0` indica uma estimativa cada vez mais confiável.</span><span class="sxs-lookup"><span data-stu-id="01c3b-141">The value of **Accuracy** ranges from `0.0` to `1.0` where `0.0` means that the cmdlet couldn't count the objects, `1.0` means that the count is exact, and a value between `0.0` and `1.0` indicates an increasingly reliable estimate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01c3b-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="01c3b-142">-LiteralPath</span></span>

<span data-ttu-id="01c3b-143">Especifica o caminho para os arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="01c3b-143">Specifies the path to the XML files.</span></span> <span data-ttu-id="01c3b-144">Ao contrário do **caminho** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="01c3b-144">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="01c3b-145">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="01c3b-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="01c3b-146">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="01c3b-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="01c3b-147">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="01c3b-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="01c3b-148">-Path</span><span class="sxs-lookup"><span data-stu-id="01c3b-148">-Path</span></span>

<span data-ttu-id="01c3b-149">Especifica o caminho para os arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="01c3b-149">Specifies the path to the XML files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="01c3b-150">-Ignorar</span><span class="sxs-lookup"><span data-stu-id="01c3b-150">-Skip</span></span>

<span data-ttu-id="01c3b-151">Ignora o número especificado de objetos e obtém os objetos restantes.</span><span class="sxs-lookup"><span data-stu-id="01c3b-151">Ignores the specified number of objects and then gets the remaining objects.</span></span> <span data-ttu-id="01c3b-152">Insira o número de objetos a ignorar.</span><span class="sxs-lookup"><span data-stu-id="01c3b-152">Enter the number of objects to skip.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01c3b-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="01c3b-153">CommonParameters</span></span>

<span data-ttu-id="01c3b-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01c3b-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01c3b-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01c3b-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01c3b-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="01c3b-156">INPUTS</span></span>

### <span data-ttu-id="01c3b-157">System.String</span><span class="sxs-lookup"><span data-stu-id="01c3b-157">System.String</span></span>

<span data-ttu-id="01c3b-158">Você pode canalizar uma cadeia de caracteres que contém um caminho para `Import-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="01c3b-158">You can pipeline a string that contains a path to `Import-Clixml`.</span></span>

## <span data-ttu-id="01c3b-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="01c3b-159">OUTPUTS</span></span>

### <span data-ttu-id="01c3b-160">PSObject</span><span class="sxs-lookup"><span data-stu-id="01c3b-160">PSObject</span></span>

<span data-ttu-id="01c3b-161">`Import-Clixml` retorna objetos que foram desserializados dos arquivos XML armazenados.</span><span class="sxs-lookup"><span data-stu-id="01c3b-161">`Import-Clixml` returns objects that were deserialized from the stored XML files.</span></span>

## <span data-ttu-id="01c3b-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="01c3b-162">NOTES</span></span>

<span data-ttu-id="01c3b-163">Ao especificar vários valores para um parâmetro, use vírgulas para separá-los.</span><span class="sxs-lookup"><span data-stu-id="01c3b-163">When specifying multiple values for a parameter, use commas to separate the values.</span></span> <span data-ttu-id="01c3b-164">Por exemplo, `<parameter-name> <value1>, <value2>`.</span><span class="sxs-lookup"><span data-stu-id="01c3b-164">For example, `<parameter-name> <value1>, <value2>`.</span></span>

## <span data-ttu-id="01c3b-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="01c3b-165">RELATED LINKS</span></span>

[<span data-ttu-id="01c3b-166">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="01c3b-166">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="01c3b-167">Apresentando a serialização XML</span><span class="sxs-lookup"><span data-stu-id="01c3b-167">Introducing XML Serialization</span></span>](/dotnet/standard/serialization/introducing-xml-serialization)

[<span data-ttu-id="01c3b-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="01c3b-168">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="01c3b-169">Armazenar credenciais com segurança no disco</span><span class="sxs-lookup"><span data-stu-id="01c3b-169">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="01c3b-170">Usar o PowerShell para passar credenciais para sistemas herdados</span><span class="sxs-lookup"><span data-stu-id="01c3b-170">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

