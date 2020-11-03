---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193966"
---
# <span data-ttu-id="1f61a-103">New-WebServiceProxy</span><span class="sxs-lookup"><span data-stu-id="1f61a-103">New-WebServiceProxy</span></span>

## <span data-ttu-id="1f61a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1f61a-104">SYNOPSIS</span></span>
<span data-ttu-id="1f61a-105">Cria um objeto de proxy de serviço Web que permite que você use e gerencie o serviço Web no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f61a-105">Creates a Web service proxy object that lets you use and manage the Web service in PowerShell.</span></span>

## <span data-ttu-id="1f61a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f61a-106">SYNTAX</span></span>

### <span data-ttu-id="1f61a-107">Nocredentials (padrão)</span><span class="sxs-lookup"><span data-stu-id="1f61a-107">NoCredentials (Default)</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### <span data-ttu-id="1f61a-108">Credencial</span><span class="sxs-lookup"><span data-stu-id="1f61a-108">Credential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="1f61a-109">UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="1f61a-109">UseDefaultCredential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## <span data-ttu-id="1f61a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f61a-110">DESCRIPTION</span></span>

<span data-ttu-id="1f61a-111">O `New-WebServiceProxy` cmdlet permite que você use um serviço Web no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f61a-111">The `New-WebServiceProxy` cmdlet lets you use a Web service in PowerShell.</span></span> <span data-ttu-id="1f61a-112">O cmdlet se conecta a um serviço Web e cria um objeto de proxy de serviço Web no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f61a-112">The cmdlet connects to a Web service and creates a Web service proxy object in PowerShell.</span></span> <span data-ttu-id="1f61a-113">Você pode usar o objeto de proxy para gerenciar o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1f61a-113">You can use the proxy object to manage the Web service.</span></span>

<span data-ttu-id="1f61a-114">Um serviço Web é um programa baseado em XML que troca dados em uma rede, especialmente pela Internet.</span><span class="sxs-lookup"><span data-stu-id="1f61a-114">A Web service is an XML-based program that exchanges data over a network, especially over the Internet.</span></span> <span data-ttu-id="1f61a-115">O Microsoft .NET Framework fornece objetos de proxy de serviço Web que representam o serviço Web como um objeto do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f61a-115">The Microsoft .NET Framework provides Web service proxy objects that represent the Web service as a .NET Framework object.</span></span>

## <span data-ttu-id="1f61a-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1f61a-116">EXAMPLES</span></span>

### <span data-ttu-id="1f61a-117">Exemplo 1: criar um proxy para um serviço Web</span><span class="sxs-lookup"><span data-stu-id="1f61a-117">Example 1: Create a proxy for a Web service</span></span>

<span data-ttu-id="1f61a-118">Este exemplo cria um proxy de .NET Framework do serviço Web da calculadora no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f61a-118">This example creates a .NET Framework proxy of the calculator Web service in Windows PowerShell.</span></span>

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### <span data-ttu-id="1f61a-119">Exemplo 2: criar um proxy para um serviço Web e especificar o namespace e a classe</span><span class="sxs-lookup"><span data-stu-id="1f61a-119">Example 2: Create a proxy for a Web service and specify namespace and class</span></span>

<span data-ttu-id="1f61a-120">Este exemplo usa o `New-WebServiceProxy` cmdlet para criar um .NET Framework proxy do serviço Web da calculadora.</span><span class="sxs-lookup"><span data-stu-id="1f61a-120">This example uses the `New-WebServiceProxy` cmdlet to create a .NET Framework proxy of the calculator Web service.</span></span>

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

<span data-ttu-id="1f61a-121">O comando usa o parâmetro **URI** para especificar o URI e o **namespace** e os parâmetros de **classe** para especificar o namespace e a classe do objeto.</span><span class="sxs-lookup"><span data-stu-id="1f61a-121">The command uses the **Uri** parameter to specify the URI and the **Namespace** and **Class** parameters to specify the namespace and class of the object.</span></span>

### <span data-ttu-id="1f61a-122">Exemplo 3: Exibir métodos de um proxy de serviço Web</span><span class="sxs-lookup"><span data-stu-id="1f61a-122">Example 3: Display methods of a Web service proxy</span></span>

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

<span data-ttu-id="1f61a-123">Este exemplo usa o `Get-Member` cmdlet para exibir os métodos do objeto proxy do serviço Web na `$calc` variável.</span><span class="sxs-lookup"><span data-stu-id="1f61a-123">This example uses the `Get-Member` cmdlet to display the methods of the Web service proxy object in the `$calc` variable.</span></span> <span data-ttu-id="1f61a-124">Utilizamos esses métodos no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1f61a-124">We uses these methods in the following example.</span></span>

<span data-ttu-id="1f61a-125">Observe que o **TypeName** do objeto proxy, WebServiceProxy, reflete os nomes de classe e namespace que foram especificados no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="1f61a-125">Notice that the **TypeName** of the proxy object, WebServiceProxy, reflects the namespace and class names that were specified in the previous example.</span></span>

### <span data-ttu-id="1f61a-126">Exemplo 4: usar um proxy de serviço Web</span><span class="sxs-lookup"><span data-stu-id="1f61a-126">Example 4: Use a Web service proxy</span></span>

```powershell
PS> $calc.Multiply(6,7)
42
```

<span data-ttu-id="1f61a-127">Este exemplo usa o proxy de serviço Web armazenado na `$calc` variável.</span><span class="sxs-lookup"><span data-stu-id="1f61a-127">This example uses the Web service proxy stored in the `$calc` variable.</span></span> <span data-ttu-id="1f61a-128">O comando usa o método de **multiplicação** do proxy.</span><span class="sxs-lookup"><span data-stu-id="1f61a-128">The command uses the **Multiply** method of the proxy.</span></span>

## <span data-ttu-id="1f61a-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f61a-129">PARAMETERS</span></span>

### <span data-ttu-id="1f61a-130">-Classe</span><span class="sxs-lookup"><span data-stu-id="1f61a-130">-Class</span></span>

<span data-ttu-id="1f61a-131">Especifica um nome para a classe de proxy que o cmdlet cria para o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1f61a-131">Specifies a name for the proxy class that the cmdlet creates for the Web service.</span></span> <span data-ttu-id="1f61a-132">O valor desse parâmetro é usado junto com o parâmetro **namespace** para fornecer um nome totalmente qualificado para a classe.</span><span class="sxs-lookup"><span data-stu-id="1f61a-132">The value of this parameter is used together with the **Namespace** parameter to provide a fully qualified name for the class.</span></span> <span data-ttu-id="1f61a-133">O valor padrão é gerado a partir do Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="1f61a-133">The default value is generated from the Uniform Resource Identifier (URI).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f61a-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="1f61a-134">-Credential</span></span>

<span data-ttu-id="1f61a-135">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="1f61a-135">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="1f61a-136">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1f61a-136">The default is the current user.</span></span> <span data-ttu-id="1f61a-137">Essa é uma alternativa ao uso do parâmetro **UseDefaultCredential** .</span><span class="sxs-lookup"><span data-stu-id="1f61a-137">This is an alternative to using the **UseDefaultCredential** parameter.</span></span>

<span data-ttu-id="1f61a-138">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f61a-138">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1f61a-139">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="1f61a-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f61a-140">-Namespace</span><span class="sxs-lookup"><span data-stu-id="1f61a-140">-Namespace</span></span>

<span data-ttu-id="1f61a-141">Especifica um namespace para a nova classe.</span><span class="sxs-lookup"><span data-stu-id="1f61a-141">Specifies a namespace for the new class.</span></span>

<span data-ttu-id="1f61a-142">O valor desse parâmetro é usado junto com o valor do parâmetro de **classe** para gerar um nome totalmente qualificado para a classe.</span><span class="sxs-lookup"><span data-stu-id="1f61a-142">The value of this parameter is used together with the value of the **Class** parameter to generate a fully qualified name for the class.</span></span> <span data-ttu-id="1f61a-143">O valor padrão é **Microsoft. PowerShell. Commands. NewWebserviceProxy. AutoGeneratedTypes** mais um tipo que é gerado a partir do URI.</span><span class="sxs-lookup"><span data-stu-id="1f61a-143">The default value is **Microsoft.PowerShell.Commands.NewWebserviceProxy.AutogeneratedTypes** plus a type that is generated from the URI.</span></span>

<span data-ttu-id="1f61a-144">Você pode definir o valor do parâmetro **namespace** para que possa acessar vários serviços Web que têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="1f61a-144">You can set the value of the **Namespace** parameter so that you can access multiple Web services that have the same name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f61a-145">-URI</span><span class="sxs-lookup"><span data-stu-id="1f61a-145">-Uri</span></span>

<span data-ttu-id="1f61a-146">Especifica o URI do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1f61a-146">Specifies the URI of the Web service.</span></span> <span data-ttu-id="1f61a-147">Insira um URI ou o caminho e o nome do arquivo que contém uma descrição de serviço.</span><span class="sxs-lookup"><span data-stu-id="1f61a-147">Enter a URI or the path and filename of a file that contains a service description.</span></span>

<span data-ttu-id="1f61a-148">O URI deve retornar uma `.asmx` página ou uma página que retorne uma descrição de serviço.</span><span class="sxs-lookup"><span data-stu-id="1f61a-148">The URI must return an `.asmx` page or to a page that returns a service description.</span></span> <span data-ttu-id="1f61a-149">Para retornar uma descrição de serviço de um serviço Web que foi criado usando ASP.NET, acrescente "? WSDL "para a URL do serviço Web (por exemplo, `http://www.contoso.com/MyWebService.asmx?WSDL` ).</span><span class="sxs-lookup"><span data-stu-id="1f61a-149">To return a service description of a Web service that was created using ASP.NET, append "?WSDL" to the URL of the Web service (for example, `http://www.contoso.com/MyWebService.asmx?WSDL`).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f61a-150">-UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="1f61a-150">-UseDefaultCredential</span></span>

<span data-ttu-id="1f61a-151">Indica que esse cmdlet usa a credencial padrão.</span><span class="sxs-lookup"><span data-stu-id="1f61a-151">Indicates that this cmdlet uses the default credential.</span></span> <span data-ttu-id="1f61a-152">Esse cmdlet define a propriedade **UseDefaultCredential** no objeto de proxy resultante como true.</span><span class="sxs-lookup"><span data-stu-id="1f61a-152">This cmdlet sets the **UseDefaultCredential** property in the resulting proxy object to True.</span></span> <span data-ttu-id="1f61a-153">Essa é uma alternativa ao uso do parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="1f61a-153">This is an alternative to using the **Credential** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f61a-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1f61a-154">CommonParameters</span></span>

<span data-ttu-id="1f61a-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1f61a-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f61a-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1f61a-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f61a-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1f61a-157">INPUTS</span></span>

### <span data-ttu-id="1f61a-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1f61a-158">None</span></span>

<span data-ttu-id="1f61a-159">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f61a-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1f61a-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1f61a-160">OUTPUTS</span></span>

### <span data-ttu-id="1f61a-161">Um objeto proxy de serviço Web</span><span class="sxs-lookup"><span data-stu-id="1f61a-161">A Web service proxy object</span></span>

<span data-ttu-id="1f61a-162">Esse cmdlet retorna um objeto proxy de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1f61a-162">This cmdlet returns a Web service proxy object.</span></span> <span data-ttu-id="1f61a-163">O namespace e a classe do objeto são determinados pelos parâmetros do comando.</span><span class="sxs-lookup"><span data-stu-id="1f61a-163">The namespace and class of the object are determined by the parameters of the command.</span></span> <span data-ttu-id="1f61a-164">O padrão é gerado a partir do URI de entrada.</span><span class="sxs-lookup"><span data-stu-id="1f61a-164">The default is generated from the input URI.</span></span>

## <span data-ttu-id="1f61a-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1f61a-165">NOTES</span></span>

<span data-ttu-id="1f61a-166">`New-WebServiceProxy` usa a classe **System .net. WebClient** para carregar o serviço Web especificado.</span><span class="sxs-lookup"><span data-stu-id="1f61a-166">`New-WebServiceProxy` uses the **System.Net.WebClient** class to load the specified Web service.</span></span>

## <span data-ttu-id="1f61a-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1f61a-167">RELATED LINKS</span></span>

[<span data-ttu-id="1f61a-168">New-Service</span><span class="sxs-lookup"><span data-stu-id="1f61a-168">New-Service</span></span>](New-Service.md)
