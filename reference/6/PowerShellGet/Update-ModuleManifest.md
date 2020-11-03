---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: f4eb5989f98517e70cc684457f0d0e3f0d12c1d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194443"
---
# Update-ModuleManifest

## SINOPSE
Atualiza um arquivo de manifesto do módulo.

## SYNTAX

### Tudo

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Update-ModuleManifest` cmdlet atualiza um arquivo de manifesto de módulo ( `.psd1` ).

## EXEMPLOS

### Exemplo 1: atualizar um manifesto de módulo

Este exemplo atualiza um arquivo de manifesto de módulo existente. Nivelamento é usado para passar valores de parâmetro para `Update-ModuleManifest` . Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

`$Parms` é um fragmentação que armazena os valores de parâmetro para **caminho** , **autor** , **CompanyName** e **direitos autorais** . `Update-ModuleManifest` Obtém os valores de parâmetro de `@Parms` e atualiza o manifesto do módulo, **TestManifest.psd1** .

## PARAMETERS

### -AliasesToExport

Especifica os aliases que o módulo exporta. Caracteres curinga são permitidos.

Use esse parâmetro para restringir os aliases exportados pelo módulo. **AliasesToExport** pode remover aliases da lista de aliases exportados, mas não pode adicionar aliases à lista.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Autor

Especifica o autor do módulo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClrVersion

Especifica a versão mínima do CLR (Common Language Runtime) do Microsoft .NET Framework que o módulo exige.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CmdletsToExport

Especifica os cmdlets que o módulo exporta. Caracteres curinga são permitidos.

Use esse parâmetro para restringir os cmdlets que são exportados pelo módulo. **CmdletsToExport** pode remover cmdlets da lista de cmdlets exportados, mas não pode adicionar cmdlets à lista.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -CompanyName

Especifica a empresa ou o fornecedor que criou o módulo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompatiblePSEditions

Especifica o **PSEditions** compatível do módulo. Para obter informações sobre **PSEdition** , consulte [módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar `Update-ModuleManifest` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direitos autorais

Especifica uma declaração de direitos autorais do módulo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultCommandPrefix

Especifica o prefixo de comando padrão.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Especifica uma descrição do módulo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DotNetFrameworkVersion

Especifica a versão mínima do Microsoft .NET Framework que o módulo exige.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DscResourcesToExport

Especifica os recursos de DSC (configuração de estado desejado) que o módulo exporta. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalModuleDependencies

Especifica uma matriz de dependências de módulo externas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileList

Especifica todos os itens incluídos no módulo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatsToProcess

Especifica os arquivos de formatação ( `.ps1xml` ) que são executados quando o módulo é importado.

Quando você importa um módulo, o PowerShell executa o `Update-FormatData` cmdlet com os arquivos especificados.
Como os arquivos de formatação não estão no escopo, eles afetam todos os Estados de sessão na sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionsToExport

Especifica as funções que o módulo exporta. Caracteres curinga são permitidos.

Use esse parâmetro para restringir as funções exportadas pelo módulo. **FunctionsToExport** pode remover funções da lista de aliases exportados, mas não pode adicionar funções à lista.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -GUID

Especifica um identificador exclusivo para o módulo. O GUID pode ser usado para distinguir entre módulos com o mesmo nome.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HelpInfoUri

Especifica o endereço da Internet do arquivo **XML HelpInfo** do módulo. Insira um Uniform Resource Identifier (URI) que comece com **http** ou **https** .

O arquivo **XML HelpInfo** dá suporte ao recurso de ajuda atualizável que foi introduzido no PowerShell versão 3,0. Ele contém informações sobre o local dos arquivos de ajuda baixáveis do módulo e os números de versão dos arquivos de ajuda mais recentes para cada localidade com suporte.

Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).
Para obter informações sobre o arquivo **XML HelpInfo** , consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IconUri

Especifica a URL de um ícone para o módulo. O ícone especificado é exibido na página da Galeria da Web para o módulo.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseUri

Especifica a URL dos termos de licenciamento do módulo.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleList

Especifica uma matriz de módulos que são incluídos no módulo.

Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion** . A tabela de hash também pode ter uma chave **GUID** opcional. Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.

Essa chave foi projetada para atuar como um inventário de módulo. Os módulos listados no valor dessa chave não são processados automaticamente.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleVersion

Especifica a versão do módulo.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NestedModules

Especifica módulos de script ( `.psm1` ) e módulos binários ( `.dll` ) que são importados para o estado de sessão do módulo. Os arquivos na chave **NestedModules** são executados na ordem em que estão listados no valor.

Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion** . A tabela de hash também pode ter uma chave **GUID** opcional. Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProviders

Especifica uma matriz de provedores de gerenciamento de pacotes.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com o qual você está trabalhando. Por padrão, o `Update-ModuleManifest` não gera nenhuma saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho e o nome do arquivo do manifesto do módulo. Insira um caminho e um nome de arquivo com uma `.psd1` extensão de nome de arquivo, como `$PSHOME\Modules\MyModule\MyModule.psd1` .

Se você especificar o caminho para um arquivo existente, `Update-ModuleManifest` o substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.

O manifesto deve estar localizado no diretório do módulo e o nome do arquivo de manifesto deve ser o mesmo que o nome do diretório do módulo, mas com uma `.psd1` extensão.

Você não pode usar variáveis, como `$PSHOME` ou `$HOME` , em resposta a um prompt para um valor de parâmetro de **caminho** . Para usar uma variável, inclua o parâmetro **Path** no comando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PowerShellHostName

Especifica o nome do programa de host do PowerShell que o módulo requer. Insira o nome do programa host, como o host do ISE do PowerShell ou ConsoleHost. Caracteres curinga não são permitidos.

Para localizar o nome de um programa de host, no programa, digite `$Host.Name` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellHostVersion

Especifica a versão mínima do programa de host do PowerShell que funciona com o módulo. Insira um número de versão, como 1.1.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellVersion

Especifica a versão mínima do PowerShell que funcionará com este módulo. Por exemplo, você pode especificar 3,0, 4,0 ou 5,0 como o valor desse parâmetro.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pré-lançamento

Indica que o módulo é de pré-lançamento.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateData

Especifica os dados que são passados para o módulo quando ele é importado.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessorArchitecture

Especifica a arquitetura do processador que o módulo requer.

Os valores aceitáveis para esse parâmetro são:

- AMD64
- Arm
- IA64
- MSIL
- Nenhum (desconhecido ou não especificado)
- X86

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectUri

Especifica a URL de uma página da Web sobre este projeto.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReleaseNotes

Especifica uma matriz de cadeia de caracteres que contém notas de versão ou comentários que você deseja disponibilizar para esta versão do script.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredAssemblies

Especifica os arquivos de assembly ( `.dll` ) que o módulo requer. Digite os nomes de arquivo de assembly.
O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave **RootModule** .

Use esse parâmetro para especificar todos os assemblies que o módulo requer, incluindo assemblies que devem ser carregados para atualizar qualquer formatação ou arquivos de tipo listados nas chaves **FormatsToProcess** ou **TypesToProcess** , mesmo se esses assemblies também estiverem listados como módulos binários na chave **NestedModules** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredModules

Especifica os módulos que devem estar no estado de sessão global. Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará. Se os módulos necessários não estiverem disponíveis, o `Import-Module` comando falhará.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireLicenseAcceptance

Especifica que uma aceitação de licença é necessária para o módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RootModule

Especifica o arquivo primário ou raiz do módulo. Insira o nome de arquivo de um script ( `.ps1` ), um módulo de script ( `.psm1` ), um manifesto de módulo ( `.psd1` ), um assembly ( `.dll` ), um arquivo XML de definição de cmdlet ( `.cdxml` ) ou um fluxo de trabalho ( `.xaml` ). Quando o módulo é importado, os membros que são exportados do arquivo do módulo raiz são importados para o estado de sessão do chamador.

Se um módulo tiver um arquivo de manifesto e nenhum arquivo raiz tiver sido especificado na chave **RootModule** , o manifesto se tornará o arquivo primário do módulo. E, o módulo torna-se um módulo de manifesto (Módulotype = manifesto).

Para exportar membros de `.psm1` ou `.dll` arquivos em um módulo que tenha um manifesto, os nomes desses arquivos devem ser especificados nos valores das chaves **RootModule** ou **NestedModules** no manifesto. Caso contrário, seus membros não serão exportados.

No PowerShell 2,0, essa chave foi chamada de **ModuleToProcess** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptsToProcess

Especifica os arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado.
Você pode usar esses scripts para preparar um ambiente, assim como você pode usar um script de logon.

Para especificar scripts que são executados no estado de sessão do módulo, use a chave **NestedModules** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Marcas

Especifica uma matriz de marcas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypesToProcess

Especifica os arquivos de tipo ( `.ps1xml` ) que são executados quando o módulo é importado.

Quando você importa o módulo, o PowerShell executa o `Update-TypeData` cmdlet com os arquivos especificados.
Como os arquivos de tipo não estão no escopo, eles afetam todos os Estados de sessão na sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VariablesToExport

Especifica as variáveis que o módulo exporta. Caracteres curinga são permitidos.

Use esse parâmetro para restringir as variáveis exportadas pelo módulo. **VariablesToExport** pode remover variáveis da lista de variáveis exportadas, mas não pode adicionar variáveis à lista.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -WhatIf

Mostra o que aconteceria se `Update-ModuleManifest` for executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS
