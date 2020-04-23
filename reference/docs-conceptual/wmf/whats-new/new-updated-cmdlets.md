---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Cmdlets novos e atualizados
ms.openlocfilehash: ffd5db2d4fc9bf8f67ef5e352633ad3209f72c87
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147586"
---
# <a name="new-and-updated-cmdlets"></a>Cmdlets novos e atualizados

Adicionamos cmdlets novos e atualizados de acordo com os comentários da comunidade.

## <a name="archive-cmdlets"></a>Cmdlets Archive

Dois novos cmdlets, `Compress-Archive` e `Expand-Archive`, permitem compactar e expandir arquivos ZIP.

Saiba mais na documentação do módulo [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/).

## <a name="catalog-cmdlets"></a>Cmdlets de Catálogo

Dois novos cmdlets foram adicionados ao módulo Microsoft.PowerShell.Security.

- [New-FileCatalog](/powershell/module/microsoft.powershell.security/New-FileCatalog)
- [Test-FileCatalog](/powershell/module/microsoft.powershell.security/Test-FileCatalog)

Eles geram e validam os arquivos de catálogo do Windows.

## <a name="clipboard-cmdlets"></a>Área de transferência de Cmdlets

`Get-Clipboard` e `Set-Clipboard` facilitam a transferência do conteúdo de e para uma sessão do Windows PowerShell. Os cmdlets Clipboard dão suporte a imagens, arquivos de áudio, listas de arquivo e texto.

Para obter mais informações, consulte:

- [Get-Clipboard](/powershell/module/Microsoft.PowerShell.Management/Get-Clipboard)
- [Set-Clipboard](/powershell/module/Microsoft.PowerShell.Management/Set-Clipboard)

## <a name="cryptographic-message-syntax-cms-cmdlets"></a>Cmdlets da CMS (Sintaxe de Mensagem Criptografada)

Os cmdlets da Sintaxe de Mensagem Criptografada dão suporte à criptografia e descriptografia de conteúdo usando o formato padrão da IETF para proteger as mensagens criptograficamente, conforme documentado pelo [RFC5652](https://tools.ietf.org/html/rfc5652.html).

O padrão de criptografia CMS implementa a criptografia por chave pública, em que a chave usada para criptografar o conteúdo (a *chave pública*) e a chave usada para descriptografá-lo (a *chave privada*) são separadas.

Sua chave pública pode ser compartilhada amplamente e não contém dados confidenciais. Se algum conteúdo for criptografado com essa chave pública, somente sua chave privada poderá descriptografá-lo. Para obter mais informações, consulte [Criptografia por chave pública](https://en.wikipedia.org/wiki/Public-key_cryptography).

Para obter mais informações, consulte:

- [Get-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Get-CmsMessage)
- [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)
- [Unprotect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/unprotect-CmsMessage)

Os certificados exigem um EKU (identificador exclusivo de uso de chave), como “Assinatura de Código” ou “Mensagens Criptografadas”, para identificá-los como certificados de criptografia de dados no PowerShell. Para exibir certificados de criptografia de documento no provedor de certificados, é possível usar o parâmetro dinâmico **DocumentEncryptionCert** de `Get-ChildItem`:

```powershell
Get-ChildItem Cert:\CurrentUser -DocumentEncryptionCert -Recurse
```

## <a name="extract-and-parse-structured-objects-from-string-content"></a>Extrair e analisar objetos estruturados do conteúdo da cadeia de caracteres

### <a name="convertfrom-string"></a>ConvertFrom-String

O novo cmdlet `ConvertFrom-String` oferece suporte a dois modos:

- Análise básica delimitada
- Análise orientada por exemplo gerada automaticamente

A análise delimitada, por padrão, divide a entrada no espaço em branco e atribui nomes de propriedade aos grupos resultantes.

O parâmetro **UpdateTemplate** salva os resultados do algoritmo de aprendizado em um comentário no arquivo de modelo. Isso faz com que o processo de aprendizado (a etapa mais lenta) seja de custo único. A execução de `ConvertFrom-String` com um modelo que contém o algoritmo de aprendizado codificado agora é quase instantânea.

Saiba mais em [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).

### <a name="convert-string"></a>Convert-String

`Convert-String` permite que você forneça exemplos da aparência que deseja para o texto antes e depois. O cmdlet formata o texto automaticamente.

Saiba mais em [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).

## <a name="updates-to-fileinfo-object"></a>Atualizações ao objeto FileInfo

Informações de versão de arquivo podem ser confusas, especialmente nos casos em que foi aplicado patch ao arquivo. O WMF 5.0 adiciona novas propriedades de script **FileVersionRaw** e **ProductVersionRaw** a objetos **FileInfo**.
Aqui estão as propriedades conforme exibidas para powershell.exe (supondo que $pid é a ID do processo do PowerShell):

```powershell
Get-Process -Id $pid -FileVersionInfo | Format-List *version*
```

```Output
FileVersionRaw    : 10.0.17763.1
ProductVersionRaw : 10.0.17763.1
FileVersion       : 10.0.17763.1 (WinBuild.160101.0800)
ProductVersion    : 10.0.17763.1
```

## <a name="format-hex"></a>Format-Hex

`Format-Hex` permite exibir texto ou dados binários em formato hexadecimal.

Saiba mais em [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).

## <a name="get-childitem-has--depth-parameter"></a>Get-ChildItem contém o parâmetro -Depth

`Get-ChildItem` agora tem um parâmetro **Depth** que é usado com **Recurse** para limitar a recursão:

## <a name="modules-support-for-declaring-version-ranges-1-etc"></a>Suporte aos módulos para declaração dos intervalos de versão (1.*, etc.)

Agora é possível combinar **MinimumVersion** e **MaximumVersion** para importar o módulo dentro de um intervalo específico. O parâmetro também oferece suporte a caracteres curinga.

```powershell
Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*
```

```Output
VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```

## <a name="new-guid"></a>New-Guid

Existem muitos cenários para os quais você precisa de um identificador exclusivo. O cmdlet `New-GUID` fornece uma maneira simples de criar um novo GUID.

```powershell
New-Guid
```

```Output
Guid
----
e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
```

## <a name="nonewline-parameter"></a>Parâmetro NoNewLine

`Out-File`, `Add-Content` e `Set-Content` agora têm uma nova opção **NoNewline** que simplesmente omite uma nova linha após a saída. Por exemplo:

```powershell
"This is " | Out-File -FilePath Example.txt -NoNewline
"a single " | Add-Content -Path Example.txt -NoNewline
"sentence." | Add-Content -Path Example.txt -NoNewline
Get-Content .\Example.txt
```

```Output
This is a single sentence.
```

Sem **NoNewline** especificado, cada fragmento ficaria em uma linha separada:

```powershell
"This is " | Out-File -FilePath Example.txt
"a single " | Add-Content -Path Example.txt
"sentence." | Add-Content -Path Example.txt
Get-Content .\Example.txt
```

```Output
This is
a single
sentence.
```

## <a name="interact-with-symbolic-links-using-improved-item-cmdlets"></a>Interagir com Links simbólicos usando cmdlets Item aprimorados

Para dar suporte a links simbólicos, o cmdlet Item e alguns cmdlets relacionados foram estendidos.

### <a name="symbolic-link-files"></a>Arquivos de link simbólico

Neste exemplo, podemos criar um novo arquivo de link simbólico chamado MySymLinkFile.txt em C:\Temp que se vincula a $pshome\profile.ps1. Todos os três exemplos produzem o mesmo resultado.

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="symbolic-link-directories"></a>Diretórios de link simbólico

Neste exemplo, podemos criar um novo diretório de link simbólico chamado MySymLinkDir em C:\Temp que se vincula à pasta $pshome. Todos os três exemplos produzem o mesmo resultado.

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkDir -Value $pshome
```

### <a name="hard-links"></a>Links físicos

As mesmas combinações de **Path** e **Name** permitidas conforme descrito acima.

```powershell
New-Item -ItemType HardLink -Path C:\Temp -Name MyHardLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="directory-junctions"></a>Junções de diretório

As mesmas combinações de **Path** e **Name** permitidas conforme descrito acima.

```powershell
New-Item -ItemType Junction -Path C:\Temp\MyJunctionDir -Value $pshome
```

### <a name="get-childitem"></a>Get-ChildItem

`Get-ChildItem` agora exibe um "l" na propriedade **Mode** para indicar um link simbólico de arquivo ou diretório.

```powershell
Get-ChildItem C:\Temp | sort LastWriteTime -Descending

Directory: C:\Temp

Mode       LastWriteTime Length Name
----       ------------- ------ ----
-a---- 6/13/2014 3:00 PM     16 File.txt
d----- 6/13/2014 3:00 PM        Directory
-a---l 6/13/2014 3:21 PM      0 MySymLinkFile.txt
d----l 6/13/2014 3:22 PM        MySymLinkDir
-a---l 6/13/2014 3:23 PM  23304 MyHardLinkFile.txt
d----l 6/13/2014 3:24 PM        MyJunctionDir
```

### <a name="remove-item"></a>Remove-Item

Remover links simbólicos funciona como a remoção de qualquer outro tipo de item.

```powershell
Remove-Item C:\Temp\MySymLinkFile.txt
Remove-Item C:\Temp\MySymLinkDir
```

Use o parâmetro **Force** para remover os arquivos no diretório de destino e o link simbólico.

```powershell
Remove-Item C:\Temp\MySymLinkDir -Force
```

## <a name="new-temporaryfile"></a>New-TemporaryFile

Às vezes, em seus scripts, é necessário criar um arquivo temporário. Isso já pode ser feito com o cmdlet `New-TemporaryFile`:

```powershell
$tempFile = New-TemporaryFile
$tempFile.FullName
```

```Output
C:\Users\user1\AppData\Local\Temp\tmp375.tmp
```

## <a name="network-switch-management-with-powershell"></a>Gerenciamento de comutador de rede com o PowerShell

Os cmdlets Network Switch, introduzidos no WMF 5.0, permitem aplicar a configuração do comutador, da VLAN (LAN virtual) e a configuração básica de porta do comutador de rede da Camada 2 a comutadores de rede certificados com o logotipo do Windows Server 2012 R2. Com esses cmdlets, é possível executar:

- Configuração do comutador global, como:
  - Definir nome do host
  - Definir faixa do comutador
  - Persistir a configuração
  - Habilitar ou desabilitar um recurso

- Configuração de VLAN:
  - Criar ou remover uma VLAN
  - Habilitar ou desabilitar uma VLAN
  - Enumerar uma VLAN
  - Definir o nome amigável de uma VLAN

- Configuração de porta da Camada 2:
  - Enumerar portas
  - Habilitar ou desabilitar portas
  - Definir modos e propriedades de porta
  - Adicionar ou associar a VLAN ao Tronco ou Acesso na porta

Saiba mais na documentação do [NetworkSwitchManager](/powershell/module/networkswitchmanager/).

## <a name="generate-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a>Gerar cmdlets do PowerShell com base em um ponto de extremidade OData com ODataUtils

O módulo ODataUtils permite gerar cmdlets do PowerShell a partir de pontos de extremidade REST que oferecem suporte a OData. O módulo Microsoft.PowerShell.ODataUtils contém os seguintes recursos:

- Informações adicionais do canal do ponto de extremidade do lado do servidor para o do lado do cliente.
- Suporte à paginação do lado do cliente
- Filtragem do lado do servidor usando o parâmetro -Select
- Suporte para cabeçalhos de solicitação da Web

Os cmdlets de proxy gerados pelo cmdlet `Export-ODataEndPointProxy` fornecem mais informações do ponto de extremidade OData no lado do servidor no fluxo **Information**.

```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
```

No exemplo a seguir, recuperamos o produto principal e capturamos a saída na variável `$infoStream`.

Se especificarmos o parâmetro **IncludeTotalResponseCount**, obteremos a contagem total de todos os registros de **Product** disponíveis no servidor.

```powershell
Import-Module $generatedProxyModuleDir -Force
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
$additionalInfo['odata.count']
```

É possível obter os registros do servidor em lotes usando o suporte à paginação do lado do cliente. Isso é útil quando é necessário obter uma grande quantidade de dados do servidor pela rede.

```powershell
$skipCount = 0
$batchSize = 3
while($skipCount -le $additionalInfo['odata.count'])
{
  Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
  $skipCount += $batchSize
}
```

Os cmdlets do proxy gerados oferecem suporte ao parâmetro **Select** que pode ser usado como um filtro para receber apenas as propriedades de registro de que o cliente precisa. A filtragem ocorre no servidor e isso reduz a quantidade de dados transferidos pela rede.

```powershell
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

O cmdlet `Export-ODataEndpointProxy` e os cmdlets do proxy gerados por ele agora oferecem suporte ao parâmetro **Headers**. O cabeçalho pode ser usado para canalizar informações adicionais esperadas pelo ponto de extremidade OData.

No exemplo a seguir, uma tabela de hash que contém uma chave de Assinatura é fornecida ao parâmetro **Headers**. Isso é um exemplo típico de serviços que esperam uma chave de Assinatura para autenticação.

```powershell
Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```
