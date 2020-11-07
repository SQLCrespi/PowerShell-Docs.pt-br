---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 4774c87c4f6ebe7f374f30139ead833bde7074e3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343395"
---
# Unblock-File

## SINOPSE
Desbloqueia os arquivos que foram baixados da Internet.

## SYNTAX

### ByPath (padrão)

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Unblock-File` cmdlet permite abrir arquivos que foram baixados da Internet. Ele desbloqueia os arquivos de script do PowerShell que foram baixados da Internet para que você possa executá-los, mesmo quando a política de execução do PowerShell for **RemoteSigned**. Por padrão, esses arquivos são bloqueados para proteger o computador contra arquivos não confiáveis.

Antes de usar o `Unblock-File` cmdlet, examine o arquivo e sua origem e verifique se é seguro abrir.

Internamente, o `Unblock-File` cmdlet Remove o fluxo de dados alternativo Zone. Identifier, que tem um valor de "3" para indicar que foi baixado da Internet.

Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: desbloquear um arquivo

Esse comando desbloqueia o arquivo PowerShellTips.chm.

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### Exemplo 2: desbloquear vários arquivos

Esse comando desbloqueia todos os arquivos no `C:\Downloads` diretório cujos nomes incluem "PowerShell". Não execute um comando como esse até que tenha verificado se todos os arquivos são seguros.

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### Exemplo 3: localizar e desbloquear scripts

Este comando mostra como localizar e desbloquear scripts do PowerShell.

O primeiro comando usa o parâmetro **Stream** do cmdlet *Get-Item* obter arquivos com o fluxo Zone. identificador.

O segundo comando mostra o que acontece quando você executa um script bloqueado em uma sessão do PowerShell na qual a política de execução é **RemoteSigned**. A diretiva RemoteSigned impede a execução de scripts baixados da Internet, a menos que estejam assinados digitalmente.

O terceiro comando usa o `Unblock-File` cmdlet para desbloquear o script para que ele possa ser executado na sessão.

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## PARAMETERS

### -LiteralPath

Especifica os arquivos que serão desbloqueados. Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica os arquivos que serão desbloqueados. Há suporte para caracteres curinga.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

É possível canalizar um caminho de arquivo para `Unblock-File` .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

- O `Unblock-File` cmdlet funciona apenas em unidades do sistema de arquivos.
- `Unblock-File` executa a mesma operação que o botão **desbloquear** na caixa de diálogo **Propriedades** no explorador de arquivos.
- Se você usar o `Unblock-File` cmdlet em um arquivo que não está bloqueado, o comando não terá nenhum efeito sobre o arquivo não bloqueado e o cmdlet não gerará erros.

## LINKS RELACIONADOS

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[Get-Item](../Microsoft.PowerShell.Management/Get-Item.md)

[Out-File](Out-File.md)

[FileSystem Provider](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
