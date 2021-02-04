---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 1f502e01f6c8331f3a56844f9d2a96891a893b88
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490919"
---
# Test-FileCatalog

## SINOPSE
`Test-FileCatalog` Valida se os hashes contidos em um arquivo de catálogo (. cat) correspondem aos hashes dos arquivos reais a fim de validar sua autenticidade.

Só há suporte para esse cmdlet no Windows.

## SYNTAX

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Test-FileCatalog` valida a autenticidade dos arquivos comparando os hashes de arquivo de um arquivo de catálogo (. cat) com os hashes dos arquivos reais no disco. Se detectar qualquer incompatibilidade, ele retornará o status como ValidationFailed. Os usuários podem recuperar todas essas informações usando o parâmetro -Detailed. Ele também exibe o status de assinatura do catálogo na Propriedade Signature, que é equivalente a chamar `Get-AuthenticodeSignature` o cmdlet no arquivo de catálogo. Os usuários também podem ignorar qualquer arquivo durante a validação usando o parâmetro -FilesToSkip.

Só há suporte para esse cmdlet no Windows.

## EXEMPLOS

### Exemplo 1: criar e validar um catálogo de arquivos

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### Exemplo 2: validar um catálogo de arquivos com saída detalhada

```powershell
Test-FileCatalog -Detailed -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## PARAMETERS

### -CatalogFilePath

Um caminho para um arquivo de catálogo (. cat) que contém os hashes a serem usados para validação.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### -Detailed

Retorna mais informações um objeto mais detalhado `CatalogInformation` que contém os arquivos testados, seus hashes esperados/reais e uma assinatura Authenticode do arquivo de catálogo se ele estiver assinado.

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

### -FilesToSkip

Uma matriz de caminhos que não devem ser testados como parte da validação.

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

### -Path

Uma pasta ou matriz de arquivos que devem ser validados em relação ao arquivo de catálogo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System. IO. DirectoryInfo [], System. String []

O pipeline aceita uma matriz de cadeias de caracteres ou `DirectoryInfo` objetos que representam caminhos para os arquivos que precisam ser validados.

## SAÍDAS

### System. Management. Automation. CatalogValidationStatus

O tipo de retorno padrão que contém um valor de `Valid` ou `ValidationFailed` .

### System. Management. Automation. CatalogInformation

Um objeto mais detalhado retornado ao usar `-Detailed` o que pode ser usado para analisar arquivos específicos que podem ou não ter aprovado a validação, quais hashes eram esperados versus encontrados e o algoritmo usado no catálogo.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

## LINKS RELACIONADOS

[New-FileCatalog](New-FileCatalog.md)

[PowerShellGet](/powershell/module/PowerShellGet)
