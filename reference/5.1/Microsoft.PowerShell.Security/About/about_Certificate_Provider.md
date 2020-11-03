---
description: Certificado
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Certificate
ms.openlocfilehash: b3ac701f18ba57d9108a76b7c478b8514075b3ee
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195829"
---
# <a name="certificate-provider"></a>Provedor Certificate

## <a name="provider-name"></a>Nome do provedor

Certificado

## <a name="drives"></a>Unidades

`Cert:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess**

## <a name="short-description"></a>Descrição breve

Fornece acesso a repositórios de certificados X. 509 e certificados no PowerShell.

## <a name="detailed-description"></a>Descrição detalhada

O provedor de **certificados** do PowerShell permite que você obtenha, adicione, altere, apague e exclua certificados e repositórios de certificados no PowerShell.

A unidade de **certificado** é um namespace hierárquico que contém os repositórios de certificados e certificados em seu computador.

O provedor de **certificado** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

A unidade do certificado expõe os tipos a seguir.

- Locais de armazenamento (Microsoft. PowerShell. Commands. X509StoreLocation), que são contêineres de alto nível que agrupam os certificados para o usuário atual e para todos os usuários. Cada sistema tem um local de armazenamento CurrentUser e LocalMachine (todos os usuários).

- Os certificados armazena (System. Security. Cryptography. X509Certificates. X509Store), que são repositórios físicos nos quais os certificados são salvos e gerenciados.

- Os certificados x. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** , cada um representando um certificado X. 509 no computador.
  Certificados são identificados por suas impressões digitais.

## <a name="navigating-the-certificate-drive"></a>Navegando pela unidade de certificado

O provedor de **certificado** expõe o namespace do certificado como a `Cert:` unidade no PowerShell. Esse comando usa o `Set-Location` comando para alterar o local atual para o repositório de certificados raiz no local de armazenamento LocalMachine. Use uma barra invertida ( \\ ) ou uma barra (/) para indicar um nível da `Cert:` unidade.

```powershell
Set-Location Cert:
```

Você também pode trabalhar com o provedor de certificado de qualquer outra unidade do PowerShell. Para fazer referência a um alias de outro local, use o `Cert:` nome da unidade no caminho.

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).
> e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-contents-of-the-cert-drive"></a>Exibindo o conteúdo da unidade CERT:

Esse comando usa o `Get-ChildItem` cmdlet para exibir os repositórios de certificados no local do repositório de certificados CurrentUser.

Se você não estiver na `Cert:` unidade, use um caminho absoluto.

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a>Exibindo Propriedades de certificado dentro da unidade CERT:

Este exemplo obtém um certificado com `Get-Item` e o armazena em uma variável.
O exemplo mostra as novas propriedades de script de certificado ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) usando `Select-Object` .

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a>Localizar todos os certificados de codesignação

Esse comando usa os parâmetros **CodeSigningCert** e **recurse** do `Get-ChildItem` cmdlet para obter todos os certificados no computador que têm autoridade de assinatura de código.

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a>Localizar certificados expirados

Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet para obter certificados que irão expirar nos próximos 30 dias.

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a>Localizar certificados SSL do servidor

Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter todos os certificados SSL do servidor nos repositórios My e webhosting.

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a>Localizar certificados expirados em computadores remotos

Esse comando usa o `Invoke-Command` cmdlet para executar um `Get-ChildItem` comando nos computadores Srv01 e Srv02. Um valor de zero (0) no parâmetro **ExpiringInDays** obtém certificados nos computadores Srv01 e Srv02 que expiraram.

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a>Combinando filtros para localizar um conjunto específico de certificados

Esse comando obtém todos os certificados no local do repositório LocalMachine que têm os seguintes atributos:

- "fabrikam" em seu nome DNS
- "Autenticação de cliente" em seu EKU
- um valor de `$true` para a propriedade **SendAsTrustedIssuer**
- Não expire nos próximos 30 dias.

A propriedade não **After** armazena a data de expiração do certificado.

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a>Abrir os certificados Snap-in MMC

O `Invoke-Item` cmdlet usará o aplicativo padrão para abrir um caminho que você especificar. Para certificados, o aplicativo padrão é o snap-in do MMC de certificados.

Esse comando abre o snap-in de certificados do MMC para gerenciar o certificado especificado.

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a>Copiando certificados

O provedor de **certificados** não dá suporte à cópia de certificados. Ao tentar copiar um certificado, você verá esse erro.

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a>Movendo certificados

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a>Mover todos os certificados de autenticação de servidor SSL para o repositório webhosting

Esse comando usa o `Move-Item` cmdlet para mover um certificado do repositório My para o repositório webhosting.

`Move-Item` Não moverá os repositórios de certificados e ele não moverá certificados para um local de repositório diferente, como mover um certificado de LocalMachine para CurrentUser. O `Move-Item` cmdlet Move certificados, mas não move chaves privadas.

Esse comando usa o parâmetro **SSLServerAuthentication** do `Get-ChildItem` cmdlet para obter certificados de autenticação de servidor SSL no meu repositório de certificados.

Os certificados retornados são canalizados para o `Move-Item` cmdlet, que move os certificados para o repositório webhosting.

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a>Excluindo certificados e chaves privadas

O `Remove-Item` cmdlet removerá os certificados que você especificar. O `-DeleteKey` parâmetro dinâmico exclui a chave privada.

### <a name="delete-a-certificate-from-the-ca-store"></a>Excluir um certificado do repositório de AC

Esse comando exclui um certificado do repositório de certificados de AC, mas deixa a chave privada associada intacta.

Na `Cert:` unidade, o `Remove-Item` cmdlet dá suporte apenas aos parâmetros **DeleteKey** , **Path** , **WhatIf** e **Confirm** . Todos os outros parâmetros são ignorados.

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a>Excluir um certificado usando curingas no nome DNS

Esse comando exclui todos os certificados que têm um nome DNS que contém "Fabrikam". Ele usa o parâmetro **DnsName** do `Get-ChildItem` cmdlet para obter os certificados e o `Remove-Item` cmdlet para excluí-los.

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a>Excluir chaves privadas de um computador remoto

Esta série de comandos permite a delegação e, em seguida, a exclusão do certificado e da chave privada associada em um computador remoto. Para excluir uma chave privada em um computador remoto, você deve usar credenciais delegadas.

Use o `Enable-WSManCredSSP` cmdlet para habilitar a autenticação de CredSSP (provedor de serviços de segurança de credencial) em um cliente no computador remoto S1.
O CredSSP permite a autenticação delegada.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

Use o `Connect-WSMan` cmdlet para conectar o computador S1 ao serviço WinRM no computador local. Quando esse comando for concluído, o computador S1 aparecerá na `WSMan:` unidade local no PowerShell.

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

Agora, você pode usar o cmdlet Set-Item na unidade WSMan: para habilitar o atributo CredSSP para o serviço WinRM.

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

Inicie uma sessão remota no computador S1 usando o `New-PSSession` cmdlet e especifique a autenticação CredSSP. Salva a sessão na `$s` variável.

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

Por fim, use o `Invoke-Command` cmdlet para executar um `Remove-Item` comando na sessão na `$s` variável. O `Remove-Item` comando usa o parâmetro **DeleteKey** para remover a chave privada junto com o certificado especificado.

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a>Excluir certificados expirados

Esse comando usa o parâmetro **ExpiringInDays** do `Get-ChildItem` cmdlet com um valor de 0 para obter certificados no repositório webhosting que expirou.

A variável que contém os certificados retornados é canalizada para o `Remove-Item` cmdlet, que os exclui. O comando usa o parâmetro **DeleteKey** para excluir a chave privada junto com o certificado.

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a>Criando certificados

O `New-Item` cmdlet não cria novos certificados no provedor de **certificados** . Use o cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) para criar um certificado para fins de teste.

## <a name="creating-certificate-stores"></a>Criação de repositórios de certificados

Na unidade CERT:, o `New-Item` cmdlet cria repositórios de certificados no local de armazenamento LocalMachine. Ele dá suporte aos parâmetros **Name** , **Path** , **WhatIf** e **Confirm** . Todos os outros parâmetros são ignorados. O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.

Este comando cria um novo repositório de certificados denominado "CustomStore" no local de armazenamento LocalMachine.

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a>Criar um novo repositório de certificados em um computador remoto

Este comando cria um novo repositório de certificados denominado "HostingStore" no local de repositório LocalMachine no computador Server01.

O comando usa o `Invoke-Command` cmdlet para executar um `New-Item` comando no computador Server01. O comando retorna um **System. Security. Cryptography. X509Certificates. X509Store** que representa o novo repositório de certificados.

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a>Criando certificados de cliente para WS-Man

Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente **WS-Management** . O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890". Todos os parâmetros são obrigatórios. O **emissor** precisa ser impressão digital do certificado dos emissores.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a>Excluindo repositórios de certificados

### <a name="delete-a-certificate-store-from-a-remote-computer"></a>Excluir um repositório de certificados de um computador remoto

Esse comando usa o `Invoke-Command` cmdlet para executar um `Remove-Item` comando nos computadores S1 e S2. O `Remove-Item` comando inclui o parâmetro **recurse** , que exclui os certificados no repositório antes de excluir o repositório.

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor. Esses parâmetros são válidos em todos os subdiretórios do provedor de certificado, mas entram em vigor apenas em certificados.

> [!NOTE]
> Os parâmetros que executam a filtragem em relação à `EnhancedKeyUsageList` propriedade também retornam itens com um `EnhancedKeyUsageList` valor de propriedade vazio.
> Os certificados que têm um **EnhancedKeyUsageList** vazio podem ser usados para todas as finalidades.

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a>CodeSigningCert <System. Management. Automation. SwitchParameter>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Esse parâmetro obtém certificados que têm "assinatura de código" em seu valor de propriedade **EnhancedKeyUsageList** .

### <a name="deletekey-systemmanagementautomationswitchparameter"></a>DeleteKey <System. Management. Automation. SwitchParameter>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

Esse parâmetro exclui a chave privada associada ao excluir o certificado.

> [!IMPORTANT]
> Para excluir uma chave privada associada a um certificado de usuário no `Cert:\CurrentUser` repositório em um computador remoto, você deve usar credenciais delegadas. O `Invoke-Command` cmdlet dá suporte à delegação de credenciais usando o parâmetro **CredSSP** . Você deve considerar qualquer risco de segurança antes `Remove-Item` de usar with `Invoke-Command` e a delegação de credenciais.

Esse parâmetro foi introduzido no PowerShell 3,0.

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a>DnsName <Microsoft. PowerShell. Commands. DnsNameRepresentation>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Esse parâmetro obtém certificados que têm o nome de domínio ou padrão de nome especificado na propriedade **DNSNameList** do certificado. O valor desse parâmetro pode ser "Unicode" ou "ASCII". Os valores Punycode são convertidos para Unicode. Caracteres curinga ( `*` ) são permitidos.

Esse parâmetro foi introduzido no PowerShell 3,0.

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a>DocumentEncryptionCert <System. Management. Automation. SwitchParameter>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Esse parâmetro obtém certificados que têm "criptografia de documentos" em seu valor de propriedade **EnhancedKeyUsageList** .

### <a name="eku-systemstring"></a>> EKU <System. String

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Esse parâmetro obtém certificados que têm o texto ou padrão de texto especificado na `EnhancedKeyUsageList` Propriedade do certificado. Caracteres curinga ( `*` ) são permitidos. A `EnhancedKeyUsageList` propriedade contém o nome amigável e os campos de OID do EKU.

Esse parâmetro foi introduzido no PowerShell 3,0.

### <a name="expiringindays-systemint32"></a>ExpiringInDays <System. Int32>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Esse parâmetro obtém certificados que expiram no número de dias especificado ou antes dele. Um valor de 0 (zero) obtém certificados expirados.

Esse parâmetro foi introduzido no PowerShell 3,0.

### <a name="itemtype-string"></a>ItemType \<String\>

Esse parâmetro permite que você especifique o tipo de item criado por `New-Item` .

Em uma `Certificate` unidade, os seguintes valores são permitidos:

- Provedor Certificate
- Certificado
- Repositório
- StoreLocation

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a>SSLServerAuthentication <System. Management. Automation. SwitchParameter>

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Obtém somente os certificados de servidor de hospedagem web SSL. Esse parâmetro obtém certificados que têm "autenticação de servidor" em seu `EnhancedKeyUsageList` valor de propriedade.

Esse parâmetro foi introduzido no PowerShell 3,0.

## <a name="script-properties"></a>Propriedades do script

Novas propriedades de script foram adicionadas ao objeto **X509Certificate2** que representa os certificados para facilitar a pesquisa e o gerenciamento dos certificados.

- `DnsNameList`: Para popular a `DnsNameList` propriedade, o provedor de certificado copia o conteúdo da entrada DnsName na extensão SubjectAlternativeName (San). Se a extensão de SAN estiver vazia, a propriedade será preenchida com o conteúdo do campo Assunto do certificado.

- `EnhancedKeyUsageList`: Para popular a `EnhancedKeyUsageList` propriedade, o provedor de certificado copia as propriedades de OID do campo EnhancedKeyUsage (EKU) no certificado e cria um nome amigável para ele.

- `SendAsTrustedIssuer`: Para popular a `SendAsTrustedIssuer` propriedade, o provedor de certificado copia a `SendAsTrustedIssuer` Propriedade do certificado.  Para obter mais informações, consulte [Gerenciamento de emissores confiáveis para autenticação de cliente](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).

Esses novos recursos permitem pesquisar certificados com base em seus nomes DNS e datas de vencimento e distinguir os certificados de autenticação de cliente e servidor, o valor de suas propriedades de Uso Avançado de Chave (EKU).

## <a name="using-the-pipeline"></a>Usando o pipeline

Os cmdlets do provedor aceitam a entrada do pipeline. Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.
Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.

## <a name="getting-help"></a>Obtendo ajuda

A partir do PowerShell 3,0, você pode obter tópicos de ajuda personalizados para cmdlets de provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.

Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de `Get-Help` para especificar uma unidade do sistema de arquivos.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a>Confira também

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Signing](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[Get-PfxCertificate](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
