---
description: O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre os recursos experimentais
ms.openlocfilehash: 82f5ef9838fcbb98e71e362ad00b1ec68f9a9f67
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598033"
---
# <a name="experimental-features"></a>Recursos experimentais

O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.

Um recurso experimental é aquele em que o design não está finalizado. O recurso está disponível para os usuários testarem e fornecerem comentários. Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas. Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.

Os recursos experimentais são desabilitados por padrão e precisam ser explicitamente habilitados pelo usuário ou pelo administrador do sistema.

Os recursos experimentais habilitados são listados no `powershell.config.json` arquivo em `$PSHOME` para todos os usuários ou no arquivo de configuração específico do usuário para um usuário específico.

> [!NOTE]
> Os recursos experimentais habilitados no arquivo de configuração do usuário têm precedência sobre os recursos experimentais listados no arquivo de configuração do sistema.

## <a name="the-experimental-attribute"></a>O atributo experimental

Use o `Experimental` atributo para declarar algum código como experimental.

Use a sintaxe a seguir para declarar o `Experimental` atributo que fornece o nome do recurso experimental e a ação a ser tomada se o recurso experimental estiver habilitado:

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

Para módulos, o `NameOfExperimentalFeature` deve seguir a forma de `<modulename>.<experimentname>` . O `ExperimentAction` parâmetro deve ser especificado e os únicos valores válidos são:

- `Show` significa mostrar este recurso experimental se o recurso estiver habilitado
- `Hide` significa ocultar este recurso experimental se o recurso estiver habilitado

### <a name="declaring-experimental-features-in-modules-written-in-c"></a>Declarando recursos experimentais em módulos escritos em C\#

Os autores de módulo que desejam usar os sinalizadores de recursos experimentais podem declarar um cmdlet como experimental usando o `Experimental` atributo.

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a>Declarando recursos experimentais em módulos escritos no PowerShell

O módulo gravado no PowerShell também pode usar o `Experimental` atributo para declarar cmdlets experimentais:

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a>Recursos experimentais mutuamente exclusivos

Há casos em que um recurso experimental não pode coexistir lado a lado com um recurso existente ou outro recurso experimental.

Por exemplo, você pode ter um cmdlet experimental que substitui um cmdlet existente. As duas versões não podem coexistir lado a lado. A `ExperimentAction.Hide` configuração permite que apenas um dos dois cmdlets seja habilitado ao mesmo tempo.

Neste exemplo, criamos um novo cmdlet experimental `Invoke-WebRequest` .
`InvokeWebRequestCommand` contém a implementação não experimental.
`InvokeWebRequestCommandV2` contém a versão experimental do cmdlet.

O uso do `ExperimentAction.Hide` permitirá que apenas um dos dois recursos seja habilitado ao mesmo tempo:

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

Quando o `MyWebCmdlets.PSWebCmdletV2` recurso experimental é habilitado, a `InvokeWebRequestCommand` implementação existente é ocultada e o `InvokeWebRequestCommandV2` fornece a implementação de `Invoke-WebRequest` .

Isso permite que os usuários experimentem o novo cmdlet e forneçam comentários e, em seguida, revertam para a versão não experimental quando necessário.

### <a name="experimental-parameters-in-cmdlets"></a>Parâmetros experimentais em cmdlets

O `Experimental` atributo também pode ser aplicado a parâmetros individuais. Isso permite que você crie um conjunto experimental de parâmetros para um cmdlet existente em vez de um cmdlet totalmente novo.

Veja um exemplo em C#:

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

Aqui está um exemplo diferente no script do PowerShell:

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a>Verificando se um recurso experimental está habilitado

Em seu código, você precisará verificar se o seu recurso experimental está habilitado antes de tomar a ação apropriada. Você pode determinar se um recurso experimental está habilitado usando o `IsEnabled()` método estático na `System.Management.Automation.ExperimentalFeature` classe.

Veja um exemplo em C#:

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

Veja um exemplo no script do PowerShell:

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a>Consulte também

[Enable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[Disable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[Get-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

