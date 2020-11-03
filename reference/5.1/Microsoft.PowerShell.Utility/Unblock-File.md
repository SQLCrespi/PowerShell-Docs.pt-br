---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 1f56dce193cc3c7c8b6af3a7854021b420107255
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193727"
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

O cmdlet **Unblock-File** permite que você abra os arquivos que foram baixados da Internet.
Ele desbloqueia os arquivos de script do PowerShell que foram baixados da Internet para que você possa executá-los, mesmo quando a política de execução do PowerShell for **RemoteSigned** .
Por padrão, esses arquivos são bloqueados para proteger o computador contra arquivos não confiáveis.

Antes de usar o cmdlet **Unblock-File** , examine o arquivo e sua origem e verifique se é seguro abri-lo.

Internamente, o cmdlet **Unblock-File** remove o fluxo de dados alternados Zone.Identifier, que tem um valor "3" para indicar que foi baixado da Internet.

Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: desbloquear um arquivo

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

Esse comando desbloqueia o arquivo PowerShellTips.chm.

### Exemplo 2: desbloquear vários arquivos

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

Esse comando desbloqueia todos os arquivos no diretório C:\Downloads cujos nomes incluem "PowerShell".
Não execute um comando como esse até que tenha verificado se todos os arquivos são seguros.

### Exemplo 3: localizar e desbloquear scripts

```
The first command uses the *Stream* parameter of the Get-Item cmdlet get files with the Zone.Identifier stream.Although you could pipe the output directly to the **Unblock-File** cmdlet (Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue | ForEach {Unblock-File $_.FileName}), it is prudent to review the file and confirm that it is safe before unblocking.
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**. The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.
PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

The third command uses the **Unblock-File** cmdlet to unblock the script so it can run in the session.
PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

Este comando mostra como localizar e desbloquear scripts do PowerShell.

## PARAMETERS

### -LiteralPath
Especifica os arquivos que serão desbloqueados.
Ao contrário de *Path* , o valor do parâmetro *LiteralPath* é usado exatamente como foi digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Especifica os arquivos que serão desbloqueados.
Há suporte para caracteres curinga.

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

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

É possível canalizar um caminho de arquivo para **Unblock-File** .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

* O cmdlet **Unblock-File** funciona apenas em unidades de sistema de arquivos.
* **Desbloquear-File** executa a mesma operação que o botão **desbloquear** na caixa de diálogo **Propriedades** no explorador de arquivos.
* Se você usar o cmdlet **Unblock-File** em um arquivo que não está bloqueado, o comando não terá nenhum efeito no arquivo desbloqueado e o cmdlet não gerará erros.

## LINKS RELACIONADOS

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[Get-Item](../Microsoft.PowerShell.Management/Get-Item.md)

[Out-File](Out-File.md)

[FileSystem Provider](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
