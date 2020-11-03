---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 1be3034b1fb44b1dce1a592ea5a2c1622b54d28f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193872"
---
# Get-PfxCertificate

## SINOPSE
Obtém informações sobre os arquivos de certificado PFX no computador.

## SYNTAX

### ByPath (padrão)

```
Get-PfxCertificate [-FilePath] <String[]> [<CommonParameters>]
```

### ByLiteralPath

```
Get-PfxCertificate -LiteralPath <String[]> [<CommonParameters>]
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
