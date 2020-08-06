---
title: Declaração de atributo de credencial | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a6deca52fa6c9e46138ae92401f58ac5dbd15852
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784360"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="0a42f-102">Declaração de atributo de credencial</span><span class="sxs-lookup"><span data-stu-id="0a42f-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="0a42f-103">O atributo Credential é um atributo opcional que pode ser usado com parâmetros de credencial do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0a42f-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0a42f-104">Quando esse atributo é adicionado a uma declaração de parâmetro, o Windows PowerShell converte a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="0a42f-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="0a42f-105">Por exemplo, o cmdlet [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) usa esse atributo para que o Windows PowerShell gere o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) que é retornado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0a42f-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a42f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0a42f-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="0a42f-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="0a42f-107">Remarks</span></span>

- <span data-ttu-id="0a42f-108">Normalmente, esse atributo é usado por parâmetros do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0a42f-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0a42f-109">Quando um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) é passado para o parâmetro, o Windows PowerShell não faz nada.</span><span class="sxs-lookup"><span data-stu-id="0a42f-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="0a42f-110">Ao criar o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , o Windows PowerShell usa o host atual para exibir os prompts apropriados para o usuário.</span><span class="sxs-lookup"><span data-stu-id="0a42f-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="0a42f-111">Por exemplo, o host padrão exibe um prompt para um nome de usuário e senha quando esse atributo é usado.</span><span class="sxs-lookup"><span data-stu-id="0a42f-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="0a42f-112">No entanto, se um host personalizado estiver sendo usado e definir um prompt diferente, esse prompt será exibido.</span><span class="sxs-lookup"><span data-stu-id="0a42f-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="0a42f-113">Esse atributo é usado com o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="0a42f-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="0a42f-114">Para obter mais informações sobre esse atributo, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="0a42f-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="0a42f-115">O atributo Credential é definido pela classe [System. Management. Automation. CredentialAttribute](/dotnet/api/System.Management.Automation.CredentialAttribute) .</span><span class="sxs-lookup"><span data-stu-id="0a42f-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a42f-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a42f-116">See Also</span></span>

[<span data-ttu-id="0a42f-117">Aliases de parâmetro</span><span class="sxs-lookup"><span data-stu-id="0a42f-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="0a42f-118">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="0a42f-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="0a42f-119">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a42f-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
