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
# New-WebServiceProxy

## SINOPSE
Cria um objeto de proxy de serviço Web que permite que você use e gerencie o serviço Web no PowerShell.

## SYNTAX

### Nocredentials (padrão)

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### Credencial

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### UseDefaultCredential

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-WebServiceProxy` cmdlet permite que você use um serviço Web no PowerShell. O cmdlet se conecta a um serviço Web e cria um objeto de proxy de serviço Web no PowerShell. Você pode usar o objeto de proxy para gerenciar o serviço Web.

Um serviço Web é um programa baseado em XML que troca dados em uma rede, especialmente pela Internet. O Microsoft .NET Framework fornece objetos de proxy de serviço Web que representam o serviço Web como um objeto do .NET Framework.

## EXEMPLOS

### Exemplo 1: criar um proxy para um serviço Web

Este exemplo cria um proxy de .NET Framework do serviço Web da calculadora no Windows PowerShell.

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### Exemplo 2: criar um proxy para um serviço Web e especificar o namespace e a classe

Este exemplo usa o `New-WebServiceProxy` cmdlet para criar um .NET Framework proxy do serviço Web da calculadora.

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

O comando usa o parâmetro **URI** para especificar o URI e o **namespace** e os parâmetros de **classe** para especificar o namespace e a classe do objeto.

### Exemplo 3: Exibir métodos de um proxy de serviço Web

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

Este exemplo usa o `Get-Member` cmdlet para exibir os métodos do objeto proxy do serviço Web na `$calc` variável. Utilizamos esses métodos no exemplo a seguir.

Observe que o **TypeName** do objeto proxy, WebServiceProxy, reflete os nomes de classe e namespace que foram especificados no exemplo anterior.

### Exemplo 4: usar um proxy de serviço Web

```powershell
PS> $calc.Multiply(6,7)
42
```

Este exemplo usa o proxy de serviço Web armazenado na `$calc` variável. O comando usa o método de **multiplicação** do proxy.

## PARAMETERS

### -Classe

Especifica um nome para a classe de proxy que o cmdlet cria para o serviço Web. O valor desse parâmetro é usado junto com o parâmetro **namespace** para fornecer um nome totalmente qualificado para a classe. O valor padrão é gerado a partir do Uniform Resource Identifier (URI).

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

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual. Essa é uma alternativa ao uso do parâmetro **UseDefaultCredential** .

Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

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

### -Namespace

Especifica um namespace para a nova classe.

O valor desse parâmetro é usado junto com o valor do parâmetro de **classe** para gerar um nome totalmente qualificado para a classe. O valor padrão é **Microsoft. PowerShell. Commands. NewWebserviceProxy. AutoGeneratedTypes** mais um tipo que é gerado a partir do URI.

Você pode definir o valor do parâmetro **namespace** para que possa acessar vários serviços Web que têm o mesmo nome.

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

### -URI

Especifica o URI do serviço Web. Insira um URI ou o caminho e o nome do arquivo que contém uma descrição de serviço.

O URI deve retornar uma `.asmx` página ou uma página que retorne uma descrição de serviço. Para retornar uma descrição de serviço de um serviço Web que foi criado usando ASP.NET, acrescente "? WSDL "para a URL do serviço Web (por exemplo, `http://www.contoso.com/MyWebService.asmx?WSDL` ).

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

### -UseDefaultCredential

Indica que esse cmdlet usa a credencial padrão. Esse cmdlet define a propriedade **UseDefaultCredential** no objeto de proxy resultante como true. Essa é uma alternativa ao uso do parâmetro **Credential** .

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Um objeto proxy de serviço Web

Esse cmdlet retorna um objeto proxy de serviço Web. O namespace e a classe do objeto são determinados pelos parâmetros do comando. O padrão é gerado a partir do URI de entrada.

## OBSERVAÇÕES

`New-WebServiceProxy` usa a classe **System .net. WebClient** para carregar o serviço Web especificado.

## LINKS RELACIONADOS

[New-Service](New-Service.md)
