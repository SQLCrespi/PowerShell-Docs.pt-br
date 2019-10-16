---
title: Declaração de atributo de credencial | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96a5dcad-faed-44d8-8c80-321f10499710
caps.latest.revision: 6
ms.openlocfilehash: 49a62ccb09f06f77862d4737199e58293e7fbe0a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369885"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="eb84c-102">Declaração de atributo de credencial</span><span class="sxs-lookup"><span data-stu-id="eb84c-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="eb84c-103">O atributo Credential é um atributo opcional que pode ser usado com parâmetros de credencial do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eb84c-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="eb84c-104">Quando esse atributo é adicionado a uma declaração de parâmetro, o Windows PowerShell converte a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="eb84c-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="eb84c-105">Por exemplo, o cmdlet [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) usa esse atributo para que o Windows PowerShell gere o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) que é retornado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb84c-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb84c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eb84c-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="eb84c-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="eb84c-107">Remarks</span></span>

- <span data-ttu-id="eb84c-108">Normalmente, esse atributo é usado por parâmetros do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eb84c-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="eb84c-109">Quando um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) é passado para o parâmetro, o Windows PowerShell não faz nada.</span><span class="sxs-lookup"><span data-stu-id="eb84c-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="eb84c-110">Ao criar o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , o Windows PowerShell usa o host atual para exibir os prompts apropriados para o usuário.</span><span class="sxs-lookup"><span data-stu-id="eb84c-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="eb84c-111">Por exemplo, o host padrão exibe um prompt para um nome de usuário e senha quando esse atributo é usado.</span><span class="sxs-lookup"><span data-stu-id="eb84c-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="eb84c-112">No entanto, se um host personalizado estiver sendo usado e definir um prompt diferente, esse prompt será exibido.</span><span class="sxs-lookup"><span data-stu-id="eb84c-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="eb84c-113">Esse atributo é usado com o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb84c-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="eb84c-114">Para obter mais informações sobre esse atributo, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="eb84c-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="eb84c-115">O atributo Credential é definido pela classe [System. Management. Automation. CredentialAttribute](/dotnet/api/System.Management.Automation.CredentialAttribute) .</span><span class="sxs-lookup"><span data-stu-id="eb84c-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb84c-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb84c-116">See Also</span></span>

[<span data-ttu-id="eb84c-117">Aliases de parâmetro</span><span class="sxs-lookup"><span data-stu-id="eb84c-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="eb84c-118">Declaração de atributo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="eb84c-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

<span data-ttu-id="eb84c-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="eb84c-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
