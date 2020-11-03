---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193331"
---
# Export-Console

## SINOPSE
Exporta os nomes de snap-ins presentes na sessão atual para um arquivo de console.

## SYNTAX

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Export-Console** exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para um arquivo de console do Windows PowerShell (. psc1).
Você pode usar este cmdlet para salvar os snap-ins para uso em futuras sessões.

Para adicionar os snap-ins no arquivo de console. psc1 a uma sessão, inicie o Windows PowerShell (Powershell.exe) na linha de comando usando Cmd.exe ou outra sessão do Windows PowerShell e, em seguida, use o parâmetro *PSConsoleFile* de Powershell.exe para especificar o arquivo de console.

Para obter mais informações sobre os snap-ins do Windows PowerShell, consulte about_PSSnapins.

## EXEMPLOS

### Exemplo 1: exportar os nomes dos snap-ins na sessão atual

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

Esse comando exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para o arquivo ConsoleS1. psc1 na pasta consoles da pasta de instalação do Windows PowerShell, $pshome.

### Exemplo 2: exportar os nomes de snap-ins para o arquivo de console mais recente

```
PS C:\> Export-Console
```

Esse comando exporta os nomes dos snap-ins do Windows PowerShell da sessão atual para o arquivo de console do Windows PowerShell que foi usado mais recentemente na sessão atual.
Ele substitui o conteúdo do arquivo anterior.

Se não exportar um arquivo de console durante a sessão atual, será solicitado que você tenha permissão para continuar e, em seguida, o nome de um arquivo.

### Exemplo 3: adicionar um snap-in e exportar os nomes dos snap-ins

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

Esses comandos adicionam o snap-in NewPSSnapin Windows PowerShell à sessão atual, exportam os nomes dos snap-ins do Windows PowerShell na sessão atual para um arquivo de console e, em seguida, iniciam uma sessão do Windows PowerShell com o arquivo de console.

O primeiro comando usa o cmdlet **Add-PSSnapin** para adicionar o snap-in NewPSSnapin à sessão atual.
Você só pode adicionar snap-ins do Windows PowerShell registrados no seu sistema.

O segundo comando exporta os nomes de snap-in do Windows PowerShell para o arquivo NewPSSnapinConsole.psc1.

O terceiro comando inicia o Windows PowerShell com o arquivo NewPSSnapinConsole.psc1.
Como o arquivo de console inclui o nome do snap-in do Windows PowerShell, os cmdlets e provedores do snap-in estão disponíveis na sessão atual.

### Exemplo 4: exportar nomes de snap-ins para um local especificado

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

Esse comando exporta os nomes dos snap-ins do Windows PowerShell na sessão atual para o arquivo Console01.psc1 do diretório atual.

O segundo comando exibe o conteúdo do arquivo Console01.psc1 no bloco de notas.

### Exemplo 5: determinar o arquivo de console a ser atualizado

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

Este exemplo mostra como usar a variável automática $ConsoleFileName para determinar o arquivo de console que será atualizado se você usar o **Export-Console** sem um valor de parâmetro de *caminho* .

O primeiro comando usa o parâmetro *PSConsoleFile* de PowerShell.exe para abrir o Windows PowerShell com o arquivo arquivo Console01. psc1.

O segundo comando usa o cmdlet **Add-PSSnapin** para adicionar o snap-in MySnapin do Windows PowerShell à sessão atual.

O terceiro comando usa o cmdlet **Export-Console** para exportar os nomes de todos os snap-ins do Windows PowerShell na sessão para o arquivo NewConsole. psc1.

O quarto comando exibe a variável $ConsoleFileName.
Ele contém o arquivo de console usado mais recentemente.
A amostra de saída mostra que o NewConsole.ps1 é o arquivo usado mais recentemente.

O quinto comando adiciona SnapIn03 no console atual.

O sexto comando usa o cmdlet **Export-Console** sem um parâmetro *Path* .
Esse comando exporta os nomes de todos os snap-ins Windows PowerShell da sessão atual para o arquivo usado mais recentemente, NewConsole.psc1.

## PARAMETERS

### -Force
Indica que esse cmdlet substitui os dados em um arquivo de console sem aviso, mesmo que o arquivo tenha o atributo somente leitura.
O atributo somente leitura é alterado e não é redefinido quando o comando é concluído.

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

### -NoClobber
Indica que esse cmdlet não substitui um arquivo de console existente.
Por padrão, se um arquivo ocorrer no caminho especificado, o **Export-Console** substituirá o arquivo sem aviso.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Especifica um nome de arquivo e de caminho para o arquivo de console (*.psc1).
Insira um caminho e um nome opcionais.
Caracteres curinga não são permitidos.

Se você especificar apenas um nome de arquivo, o **Export-Console** criará um arquivo com esse nome e a extensão de nome de arquivo. psc1 no diretório atual.

Esse parâmetro é necessário, a menos que você tenha aberto o Windows PowerShell com o parâmetro *PSConsoleFile* ou exportou um arquivo de console durante a sessão atual.
Ele também é necessário quando você usa o parâmetro *NoClobber* para impedir que o arquivo de console atual seja substituído.

Se você omitir esse parâmetro, o **Export-Console** substituirá o arquivo de console que foi usado mais recentemente nesta sessão.
O caminho do arquivo de console usado mais recentemente é armazenado no valor da variável automática $ConsoleFileName.
Para obter mais informações, consulte about_Automatic_Variables.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
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
É possível canalizar uma cadeia de caracteres de caminho para esse cmdlet.

## SAÍDAS

### System. IO. FileInfo
Esse cmdlet cria um arquivo que contém os aliases exportados.

## OBSERVAÇÕES

* Quando um arquivo de console (.psc1) é usado para iniciar a sessão, o nome do arquivo de console é armazenado automaticamente na variável automática $ConsoleFileName. O valor de $ConsoleFileName é atualizado quando você usa o parâmetro *Path* de **Export-Console** para especificar um novo arquivo de console. Quando nenhum arquivo de console é usado, $ConsoleFileName não tem valor ($Null).

  Para usar um arquivo de console do Windows PowerShell em uma nova sessão, use a sintaxe a seguir para iniciar o Windows PowerShell:

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  Você também pode salvar os snap-ins do Windows PowerShell para futuras sessões, adicionando um comando Add-PSSnapin para seu perfil do Windows PowerShell.
Para obter mais informações, consulte about_Profiles.


## LINKS RELACIONADOS

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
