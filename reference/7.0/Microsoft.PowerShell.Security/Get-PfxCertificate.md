---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 1642f30579e71835233431438172ffc1000c4203
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193048"
---
# Get-PfxCertificate

## SINOPSE
Obtém informações sobre os arquivos de certificado PFX no computador.

## SYNTAX

### ByPath (padrão)

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### ByLiteralPath

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## DESCRIPTION

O `Get-PfxCertificate` cmdlet obtém um objeto que representa cada arquivo de certificado pfx especificado.
Um arquivo PFX inclui o certificado e uma chave privada.

## EXEMPLOS

### Exemplo 1: obter um certificado PFX

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

Esse comando obtém informações sobre o arquivo de certificado. pfx de teste no sistema.

### Exemplo 2: obter um certificado PFX de um computador remoto

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

Esse comando obtém um arquivo de certificado PFX do computador remoto Server01. Ele usa `Invoke-Command` para executar um `Get-PfxCertificate` comando remotamente.

Quando o arquivo de certificado PFX não está protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.

## PARAMETERS

### -FilePath

Especifica o caminho completo para o arquivo PFX do arquivo protegido. Se você especificar um valor para esse parâmetro, não será necessário digitar `-FilePath` na linha de comando.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

O caminho completo para o arquivo PFX do arquivo protegido. Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

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

### -NoPromptForPassword

Suprime a solicitação de uma senha.

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

### -Password

Especifica uma senha necessária para acessar um `.pfx` arquivo de certificado.

Esse parâmetro foi introduzido no PowerShell 6,1.

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho de arquivo para `Get-PfxCertificate` .

## SAÍDAS

### System.Security.Cryptography.X509Certificates.X509Certificate2

`Get-PfxCertificate` Retorna um objeto para cada certificado que ele obtém.

## OBSERVAÇÕES

Ao usar o `Invoke-Command` cmdlet para executar um `Get-PfxCertificate` comando remotamente, e o arquivo de certificado pfx não é protegido por senha, o valor do parâmetro de **autenticação** de `Invoke-Command` deve ser CredSSP.

## LINKS RELACIONADOS

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)
