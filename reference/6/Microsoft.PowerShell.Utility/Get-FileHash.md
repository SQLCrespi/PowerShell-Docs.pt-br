---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: d9a83cc20042f7613dd1e6033beaa8b2341c3d15
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194482"
---
# <span data-ttu-id="1cd67-103">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="1cd67-103">Get-FileHash</span></span>

## <span data-ttu-id="1cd67-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1cd67-104">SYNOPSIS</span></span>
<span data-ttu-id="1cd67-105">Calcula o valor de hash para um arquivo utilizando um algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-105">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="1cd67-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1cd67-106">SYNTAX</span></span>

### <span data-ttu-id="1cd67-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="1cd67-107">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="1cd67-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1cd67-108">LiteralPath</span></span>

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="1cd67-109">StreamParameterSet</span><span class="sxs-lookup"><span data-stu-id="1cd67-109">StreamParameterSet</span></span>

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## <span data-ttu-id="1cd67-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1cd67-110">DESCRIPTION</span></span>

<span data-ttu-id="1cd67-111">O `Get-FileHash` cmdlet computa o valor de hash para um arquivo usando um algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-111">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="1cd67-112">Um valor de hash é um valor exclusivo que corresponde ao conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-112">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="1cd67-113">Em vez de identificar o conteúdo de um arquivo por seu nome, extensão ou outra designação, um hash atribui um valor exclusivo para o conteúdo de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-113">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="1cd67-114">Extensões e nomes de arquivo podem ser alterados sem alterar o conteúdo do arquivo e sem alterar o valor de hash.</span><span class="sxs-lookup"><span data-stu-id="1cd67-114">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="1cd67-115">Da mesma forma, o conteúdo do arquivo pode ser alterado sem alterar o nome ou a extensão.</span><span class="sxs-lookup"><span data-stu-id="1cd67-115">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="1cd67-116">No entanto, até mesmo um único caractere no conteúdo de um arquivo altera o valor de hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-116">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="1cd67-117">A finalidade dos valores de hash é fornecer uma maneira de proteger criptograficamente para verificar se o conteúdo de um arquivo não foi alterado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-117">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="1cd67-118">Embora alguns algoritmos de hash, incluindo MD5 e SHA1, não sejam mais considerados seguros contra ataques, o objetivo de um algoritmo de hash seguro é tornar impossível alterar o conteúdo de um arquivo, seja por acidente ou por tentativa mal-intencionada ou não autorizada, e manter o mesmo valor de hash.</span><span class="sxs-lookup"><span data-stu-id="1cd67-118">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="1cd67-119">Também é possível utilizar os valores de hash para determinar se dois arquivos diferentes têm exatamente o mesmo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-119">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="1cd67-120">Se os valores de hash de dois arquivos forem idênticos, o conteúdo dos arquivos também é idêntico.</span><span class="sxs-lookup"><span data-stu-id="1cd67-120">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="1cd67-121">Por padrão, o `Get-FileHash` cmdlet usa o algoritmo SHA256, embora qualquer algoritmo de hash compatível com o sistema operacional de destino possa ser usado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-121">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="1cd67-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1cd67-122">EXAMPLES</span></span>

### <span data-ttu-id="1cd67-123">Exemplo 1: calcular o valor de hash para um arquivo</span><span class="sxs-lookup"><span data-stu-id="1cd67-123">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="1cd67-124">Este exemplo usa o `Get-FileHash` cmdlet para calcular o valor de hash para o `/etc/apt/sources.list` arquivo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-124">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `/etc/apt/sources.list` file.</span></span> <span data-ttu-id="1cd67-125">O algoritmo de hash usado é o padrão, **SHA256** .</span><span class="sxs-lookup"><span data-stu-id="1cd67-125">The hash algorithm used is the default, **SHA256** .</span></span> <span data-ttu-id="1cd67-126">A saída é canalizada para o `Format-List` cmdlet para formatar a saída como uma lista.</span><span class="sxs-lookup"><span data-stu-id="1cd67-126">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### <span data-ttu-id="1cd67-127">Exemplo 2: calcular o valor de hash para um arquivo ISO</span><span class="sxs-lookup"><span data-stu-id="1cd67-127">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="1cd67-128">Este exemplo usa o `Get-FileHash` cmdlet e o algoritmo **Sha384** para calcular o valor de hash para um arquivo ISO que um administrador baixou da Internet.</span><span class="sxs-lookup"><span data-stu-id="1cd67-128">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="1cd67-129">A saída é canalizada para o `Format-List` cmdlet para formatar a saída como uma lista.</span><span class="sxs-lookup"><span data-stu-id="1cd67-129">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="1cd67-130">Exemplo 3: calcular o valor de hash de um fluxo</span><span class="sxs-lookup"><span data-stu-id="1cd67-130">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="1cd67-131">Para este exemplo, obtemos o uso do **System .net. WebClient** para baixar um pacote da [página de versão do PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span><span class="sxs-lookup"><span data-stu-id="1cd67-131">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="1cd67-132">A página versão também documenta o hash SHA256 de cada arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="1cd67-132">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="1cd67-133">Podemos comparar o valor de hash publicado com o que calculamos com `Get-FileHash` .</span><span class="sxs-lookup"><span data-stu-id="1cd67-133">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### <span data-ttu-id="1cd67-134">Exemplo 4: calcular o hash de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1cd67-134">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="1cd67-135">O PowerShell não fornece um cmdlet para computar o hash de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1cd67-135">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="1cd67-136">No entanto, você pode gravar uma cadeia de caracteres em um fluxo e usar o parâmetro **InputStream** de `Get-FileHash` para obter o valor de hash.</span><span class="sxs-lookup"><span data-stu-id="1cd67-136">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## <span data-ttu-id="1cd67-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1cd67-137">PARAMETERS</span></span>

### <span data-ttu-id="1cd67-138">-Algoritmo</span><span class="sxs-lookup"><span data-stu-id="1cd67-138">-Algorithm</span></span>

<span data-ttu-id="1cd67-139">Especifica a função de hash criptográfico a ser usada para calcular o valor de hash do conteúdo do arquivo ou fluxo especificado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-139">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="1cd67-140">Uma função de hash criptográfico tem a propriedade de que é impraticável encontrar dois arquivos diferentes com o mesmo valor de hash.</span><span class="sxs-lookup"><span data-stu-id="1cd67-140">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="1cd67-141">As funções de hash são utilizadas com assinaturas digitais e integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="1cd67-141">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="1cd67-142">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1cd67-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1cd67-143">SHA1</span><span class="sxs-lookup"><span data-stu-id="1cd67-143">SHA1</span></span>
- <span data-ttu-id="1cd67-144">SHA256</span><span class="sxs-lookup"><span data-stu-id="1cd67-144">SHA256</span></span>
- <span data-ttu-id="1cd67-145">SHA384</span><span class="sxs-lookup"><span data-stu-id="1cd67-145">SHA384</span></span>
- <span data-ttu-id="1cd67-146">SHA512</span><span class="sxs-lookup"><span data-stu-id="1cd67-146">SHA512</span></span>
- <span data-ttu-id="1cd67-147">MD5</span><span class="sxs-lookup"><span data-stu-id="1cd67-147">MD5</span></span>

<span data-ttu-id="1cd67-148">Se nenhum valor for especificado, ou se o parâmetro for omitido, o valor padrão é SHA256.</span><span class="sxs-lookup"><span data-stu-id="1cd67-148">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="1cd67-149">Por motivos de segurança, MD5 e SHA1, que não são considerados seguros, devem ser utilizados somente para validação de alteração simples e não devem ser utilizados para gerar valores de hash para arquivos que exigem proteção contra ataque ou violação.</span><span class="sxs-lookup"><span data-stu-id="1cd67-149">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1cd67-150">-InputStream</span><span class="sxs-lookup"><span data-stu-id="1cd67-150">-InputStream</span></span>

<span data-ttu-id="1cd67-151">Especifica o fluxo de entrada.</span><span class="sxs-lookup"><span data-stu-id="1cd67-151">Specifies the input stream.</span></span>

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1cd67-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1cd67-152">-LiteralPath</span></span>

<span data-ttu-id="1cd67-153">Especifica o caminho para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1cd67-153">Specifies the path to a file.</span></span> <span data-ttu-id="1cd67-154">Ao contrário do parâmetro **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="1cd67-154">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="1cd67-155">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="1cd67-155">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="1cd67-156">Se o caminho incluir caracteres de escape, coloque o caminho entre aspas.</span><span class="sxs-lookup"><span data-stu-id="1cd67-156">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="1cd67-157">As aspas simples instruem o PowerShell a não interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="1cd67-157">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1cd67-158">-Path</span><span class="sxs-lookup"><span data-stu-id="1cd67-158">-Path</span></span>

<span data-ttu-id="1cd67-159">Especifica o caminho para um ou mais arquivos como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1cd67-159">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="1cd67-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1cd67-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="1cd67-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1cd67-161">CommonParameters</span></span>

<span data-ttu-id="1cd67-162">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1cd67-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1cd67-163">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1cd67-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1cd67-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1cd67-164">INPUTS</span></span>

### <span data-ttu-id="1cd67-165">System.String</span><span class="sxs-lookup"><span data-stu-id="1cd67-165">System.String</span></span>

<span data-ttu-id="1cd67-166">É possível canalizar uma cadeia de caracteres para o `Get-FileHash` cmdlet que contém um caminho para um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="1cd67-166">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="1cd67-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1cd67-167">OUTPUTS</span></span>

### <span data-ttu-id="1cd67-168">Microsoft. PowerShell. Utility. FileHash</span><span class="sxs-lookup"><span data-stu-id="1cd67-168">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="1cd67-169">`Get-FileHash` Retorna um objeto que representa o caminho para o arquivo especificado, o valor do hash computado e o algoritmo usado para computar o hash.</span><span class="sxs-lookup"><span data-stu-id="1cd67-169">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="1cd67-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1cd67-170">NOTES</span></span>

## <span data-ttu-id="1cd67-171">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1cd67-171">RELATED LINKS</span></span>

[<span data-ttu-id="1cd67-172">Format-List</span><span class="sxs-lookup"><span data-stu-id="1cd67-172">Format-List</span></span>](Format-List.md)
