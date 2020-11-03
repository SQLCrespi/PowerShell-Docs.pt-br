---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 41b5ef4471ec2bef0bf4b30f8996f2e0010eceff
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192774"
---
# Test-ModuleManifest

## SINOPSE
Verifica se um arquivo de manifesto de módulo descreve com precisão o conteúdo de um módulo.

## SYNTAX

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Test-ModuleManifest** verifica se os arquivos listados no arquivo de manifesto do módulo (. psd1) estão na verdade nos caminhos especificados.

Este cmdlet é projetado para ajudar os autores de módulo a testar seus arquivos de manifesto.
Os usuários do módulo também podem usar esse cmdlet em scripts e comandos para detectar erros antes de executarem scripts que dependem do módulo.

**Test-ModuleManifest** retorna um objeto que representa o módulo.
Esse é o mesmo tipo de objeto que Get-Module retorna.
Se algum arquivo não estiver nos locais especificados no manifesto, o cmdlet também gera um erro para cada arquivo faltante.

## EXEMPLOS

### Exemplo 1: testar um manifesto

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

Este comando testa o manifesto de módulo TestModule.psd1.

### Exemplo 2: testar um manifesto usando o pipeline

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

Esse comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres de caminho para **Test-ModuleManifest** .

A saída do comando mostra que o teste falhou, porque o arquivo TestTypes.ps1xml, que estava listado no manifesto, não foi encontrado.

### Exemplo 3: escrever uma função para testar um manifesto de módulo

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

Essa função é como **Test-ModuleManifest** , mas retorna um valor booliano.
A função retornará $True se o manifesto tiver passado o teste e $False caso contrário.

A função usa o cmdlet Get-ChildItem, alias = dir, para obter o manifesto do módulo especificado pela variável $path.
O comando usa um operador de pipeline (|) para passar o objeto de arquivo para **Test-ModuleManifest** .

**Test-ModuleManifest** usa o parâmetro de *erro* comum com um valor de SilentlyContinue para suprimir a exibição de quaisquer erros gerados pelo comando.
Ele também salva o objeto **PSModuleInfo** que **Test-ModuleManifest** retorna na variável $a.
Portanto, o objeto não é exibido.

Em seguida, em um comando separado, a função exibe o valor de $?
variável automática.
Se o comando anterior não gerar nenhum erro, o comando exibirá $True e $False caso contrário.

Você pode usar essa função em instruções condicionais, como aquelas que podem preceder um comando **Import-Module** ou um comando que usa o módulo.

## PARAMETERS

### -Path

Especifica um caminho e um nome de arquivo para o arquivo de manifesto.
Insira um caminho opcional e o nome do arquivo de manifesto de módulo que tem a extensão de nome de arquivo. psd1.
O local padrão é o diretório atual.
Os caracteres curinga têm suporte, mas devem ser resolvidos para um único arquivo de manifesto de módulo.
Este parâmetro é necessário.
Você também pode canalizar um caminho para **Test-ModuleManifest** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar o caminho para um manifesto de módulo para esse cmdlet.

## SAÍDAS

### System. Management. Automation. PSModuleInfo

Esse cmdlet retorna um objeto **PSModuleInfo** que representa o módulo.
Ele retornará este objeto mesmo se o manifesto apresentar erros.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[New-Module](New-Module.md)

[New-ModuleManifest](New-ModuleManifest.md)

[Remove-Module](Remove-Module.md)

[about_Modules](About/about_Modules.md)
