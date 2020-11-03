---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: b246e316c209cd66602967d3ad41b03758057192
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193123"
---
# Set-AuthenticodeSignature

## SINOPSE
Adiciona uma assinatura [Authenticode](/windows-hardware/drivers/install/authenticode) a um script do PowerShell ou a outro arquivo.

## SYNTAX

### ByPath (padrão)

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByContent

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-AuthenticodeSignature` cmdlet adiciona uma assinatura Authenticode a qualquer arquivo que dê suporte ao SIP (pacote de interface de entidade).

Em um arquivo de script do PowerShell, a assinatura assume a forma de um bloco de texto que indica o fim das instruções que são executadas no script. Se houver uma assinatura no arquivo quando esse cmdlet é executado, essa assinatura será removida.

## EXEMPLOS

### Exemplo 1-assinar um script usando um certificado do repositório de certificados local

Esses comandos recuperam um certificado de assinatura de código do provedor de certificados do PowerShell e o usam para assinar um script do PowerShell.

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

O primeiro comando usa o `Get-ChildItem` cmdlet e o provedor de certificados do PowerShell para obter os certificados no `Cert:\CurrentUser\My` subdiretório do repositório de certificados. A `Cert:` unidade é a unidade exposta pelo provedor de certificado. O parâmetro **CodeSigningCert** , que é suportado apenas pelo provedor de certificado, limita os certificados recuperados para aqueles com autoridade de assinatura de código. O comando armazena o resultado na `$cert` variável.

O segundo comando usa o `Set-AuthenticodeSignature` cmdlet para assinar o `PSTestInternet2.ps1` script. Ele usa o parâmetro **FilePath** para especificar o nome do script e o parâmetro de **certificado** para especificar que o certificado seja armazenado na `$cert` variável.

> [!NOTE]
> O uso do parâmetro **CodeSigningCert** com `Get-ChildItem` apenas retorna certificados que têm autoridade de assinatura de código e contêm uma chave privada. Se não houver nenhuma chave privada, os certificados não poderão ser usados para assinatura.

### Exemplo 2-assinar um script usando um certificado de um arquivo PFX

Esses comandos usam o `Get-PfxCertificate` cmdlet para carregar um certificado de assinatura de código. Em seguida, use-o para assinar um script do PowerShell.

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

O primeiro comando usa o `Get-PfxCertificate` cmdlet para carregar o certificado C:\Test\MySign.pfx na `$cert` variável.

O segundo comando usa `Set-AuthenticodeSignature` para assinar o script. O parâmetro **FilePath** de `Set-AuthenticodeSignature` especifica o caminho para o arquivo de script que está sendo assinado e o parâmetro **CERT** passa a `$cert` variável que contém o certificado para `Set-AuthenticodeSignature` .

Se o arquivo de certificado for protegido por senha, o PowerShell solicitará a senha.

### Exemplo 3-adicionar uma assinatura que inclui a autoridade raiz

Este comando adiciona uma assinatura digital que inclui a autoridade raiz da cadeia de confiança e é assinado por um servidor de carimbo de hora de terceiros.

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

O comando usa o parâmetro **FilePath** para especificar o script que está sendo assinado e o parâmetro de **certificado** para especificar o certificado que é salvo na `$cert` variável. Ele usa o parâmetro **IncludeChain** para incluir todas as assinaturas na cadeia de confiança, incluindo a autoridade raiz. Ele também usa o parâmetro **TimeStampServer** para adicionar um carimbo de data/hora à assinatura.
Isso impede que o script falhe quando o certificado expirar.

## PARAMETERS

### -Certificado

Especifica o certificado que será usado para assinar o script ou arquivo. Insira uma variável que armazena um objeto que representa o certificado ou uma expressão que obtém o certificado.

Para localizar um certificado, use `Get-PfxCertificate` ou use o `Get-ChildItem` cmdlet na unidade do certificado `Cert:` . Se o certificado não for válido ou não tiver `code-signing` autoridade, o comando falhará.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica o caminho para um arquivo que está sendo assinado.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

Permite ao cmdlet anexar informações de rastreamento a um arquivo somente leitura. Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HashAlgorithm

Especifica o algoritmo de hash que o Windows usa para calcular a assinatura digital do arquivo.

Para o PowerShell 3,0, o padrão é SHA256, que é o algoritmo de hash padrão do Windows. Para o PowerShell 2,0, o padrão é SHA1. Arquivos assinados com um algoritmo de hash diferente poderão não ser reconhecidos em outros sistemas. Quais algoritmos têm suporte depende da versão do sistema operacional.

Para obter uma lista de possíveis valores, consulte [hashalgorithmname struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeChain

Determina quais certificados na cadeia de confiança de certificados são incluídos na assinatura digital.
Não **raiz** é o padrão.

Os valores válidos são:

- Signatário: inclui apenas o certificado do signatário.
- Não raiz: inclui todos os certificados na cadeia de certificados, exceto para a autoridade raiz.
- Todos: inclui todos os certificados na cadeia de certificados.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimestampServer

Usa o servidor do carimbo de data e hora especificada para adicionar um carimbo de data na assinatura. Digite a URL do servidor de carimbo de data e hora como uma cadeia de caracteres.

O carimbo de data e hora representa a hora exata em que o certificado foi adicionado ao arquivo. Um carimbo de data e hora impede que o script falhe se o certificado expirar, pois usuários e programas podem verificar se o certificado era válido no momento da assinatura.

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

### -LiteralPath

Especifica o caminho para um arquivo que está sendo assinado. Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

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

### -SourcePathOrExtension

Caminho para o arquivo ou tipo de arquivo do conteúdo para o qual a assinatura digital é adicionada. Esse parâmetro é usado com o **conteúdo** em que o conteúdo do arquivo é passado como uma matriz de bytes.

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Conteúdo

Conteúdo de um arquivo como uma matriz de bytes para a qual a assinatura digital é adicionada. Esse parâmetro deve ser usado com o parâmetro **SourcePathOrExtension** . O conteúdo do arquivo deve estar no formato Unicode (UTF-16LE).

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

É possível canalizar uma cadeia de caracteres que contém o caminho do arquivo para `Set-AuthenticodeSignature` .

## SAÍDAS

### System. Management. Automation. Signature

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Get-PfxCertificate](Get-PfxCertificate.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
