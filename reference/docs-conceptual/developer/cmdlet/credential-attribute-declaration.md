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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369885"
---
# <a name="credential-attribute-declaration"></a>Declaração de atributo de credencial

O atributo Credential é um atributo opcional que pode ser usado com parâmetros de credencial do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro. Quando esse atributo é adicionado a uma declaração de parâmetro, o Windows PowerShell converte a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) . Por exemplo, o cmdlet [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) usa esse atributo para que o Windows PowerShell gere o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) que é retornado pelo cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[Credential]
```

## <a name="remarks"></a>Comentários

- Normalmente, esse atributo é usado por parâmetros do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) para que uma cadeia de caracteres também possa ser passada como um argumento para o parâmetro. Quando um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) é passado para o parâmetro, o Windows PowerShell não faz nada.

- Ao criar o objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , o Windows PowerShell usa o host atual para exibir os prompts apropriados para o usuário. Por exemplo, o host padrão exibe um prompt para um nome de usuário e senha quando esse atributo é usado. No entanto, se um host personalizado estiver sendo usado e definir um prompt diferente, esse prompt será exibido.

- Esse atributo é usado com o atributo Parameter. Para obter mais informações sobre esse atributo, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

- O atributo Credential é definido pela classe [System. Management. Automation. CredentialAttribute](/dotnet/api/System.Management.Automation.CredentialAttribute) .

## <a name="see-also"></a>Consulte Também

[Aliases de parâmetro](./parameter-aliases.md)

[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
