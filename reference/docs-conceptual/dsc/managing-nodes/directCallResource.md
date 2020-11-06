---
ms.date: 08/11/2020
keywords: DSC,powershell,configuração,instalação
title: Chamando métodos do recurso DSC diretamente
description: O cmdlet Invoke-DscResource pode ser usado para chamar as funções ou os métodos de um recurso de DSC. Ele pode ser usado por terceiros que queiram usar recursos de DSC ou como uma ferramenta útil ao desenvolver recursos.
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650996"
---
# <a name="calling-dsc-resource-methods-directly"></a>Chamando métodos do recurso DSC diretamente

> Aplica-se a: Windows PowerShell 5.0

Use o cmdlet [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) para chamar diretamente as funções ou os métodos de um recurso de DSC (as funções `Get-TargetResource`, `Set-TargetResource` e `Test-TargetResource` de um recurso baseado em MOF ou os métodos **Get** , **Set** e **Test** de um recurso baseado em classe). Isso pode ser usado por terceiros que querem usar recursos DSC, ou como uma ferramenta útil ao desenvolver recursos.

> [!NOTE]
> No PowerShell 7.0+, `Invoke-DscResource` não é mais compatível com a invocação de recursos de DSC do WMI. Isso inclui os recursos de **Arquivo** e **Log** em **PSDesiredStateConfiguration**.

Geralmente, esse cmdlet é usado em combinação com uma propriedade de metaconfiguração `refreshMode = 'Disabled'`, mas pode ser usado, independentemente do **refreshMode** para o qual está definido.

Ao chamar o cmdlet `Invoke-DscResource`, você especifica qual método ou função chamar usando o parâmetro **Method**. Especifique as propriedades do recurso passando uma tabela de hash como o valor do parâmetro **Property**.

A seguir, exemplos de chamada direta aos métodos do recurso:

## <a name="ensure-a-file-is-present"></a>Certificar-se de que um arquivo está presente

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a>Testar se um arquivo está presente

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a>Obter o conteúdo do arquivo

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> não é permitido chamar diretamente métodos de recurso de composição. Em vez disso, chame os métodos de recursos subjacentes que compõem o recurso de composição.

## <a name="see-also"></a>Consulte Também

- [Escrevendo um recurso personalizado de DSC com MOF](../resources/authoringResourceMOF.md)
- [Escrevendo um recurso personalizado de DSC com classes do PowerShell](../resources/authoringResourceClass.md)
- [Depurando os recursos de DSC](../troubleshooting/debugResource.md)
