---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: ''
schema: 2.0.0
ms.openlocfilehash: 34998e7c4a6876821df949019970dc1d87297397
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196466"
---
# Get-PSSubsystem

## SINOPSE
Recupera informações sobre os subsistemas registrados no PowerShell.

## SYNTAX

### GetAllSet (padrão)

```
Get-PSSubsystem [<CommonParameters>]
```

### GetByKindSet

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### GetByTypeSet

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## DESCRIPTION

Recupera informações sobre os subsistemas registrados no PowerShell.

> [!NOTE]
> Esse é um recurso experimental. Esse cmdlet só está disponível quando o `PSSubsystemPluginModel` recurso está habilitado. Para obter mais informações, consulte [usando recursos experimentais](/powershell/scripting/learn/experimental-features).

Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly. Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.

Atualmente, há suporte apenas para o subsistema **CommandPredictor** . Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados. No futuro, será possível dividir **Job** , **CommandCompleter** , **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.

## EXEMPLOS

### Exemplo 1-exibir todos os subsistemas disponíveis

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### Exemplo 2-exibir todos os subsistemas disponíveis de um tipo específico

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## PARAMETERS

### -Tipo


Especifica o tipo de subsistema a ser retornado. Os valores válidos são: `CommandPredictor` .

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Subsistematype

Especifica o tipo de subsistema a ser retornado.

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. Subsystem. SubsystemKind

### System.Type

## SAÍDAS

### System. Management. Automation. Subsystem. SubsystemInfo

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_experimental_features](about/about_experimental_features.md)

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Get-ExperimentalFeature.md)

[Get-ExperimentalFeature](Get-ExperimentalFeature.md)

[Usar recursos experimentais](/powershell/scripting/learn/experimental-features)
