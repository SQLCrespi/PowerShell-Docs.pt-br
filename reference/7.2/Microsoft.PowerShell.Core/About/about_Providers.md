---
description: Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando. Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 6073ef13a6d0a02cded69073d7ffaef903a807ea
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597189"
---
# <a name="about-providers"></a>Sobre provedores

## <a name="short-description"></a>Descrição breve
Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando.
Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.

## <a name="long-description"></a>Descrição longa

Os provedores do PowerShell são programas .NET que fornecem acesso a armazenamentos de dados especializados para facilitar a visualização e o gerenciamento. Os dados são exibidos em uma unidade e você acessa os dados em um caminho como faria em uma unidade de disco rígido. Você pode usar qualquer um dos cmdlets internos aos quais o provedor dá suporte para gerenciar os dados na unidade do provedor. Além disso, você pode usar cmdlets personalizados projetados especialmente para os dados.

Os provedores também podem adicionar parâmetros dinâmicos aos cmdlets internos. Esses parâmetros só estão disponíveis quando você usa o cmdlet com os dados do provedor.

## <a name="built-in-providers"></a>Provedores internos

O PowerShell inclui um conjunto de provedores internos que você pode usar para acessar os diferentes tipos de armazenamentos de dados.

| Provedor   |   Unidade (s)  |OutputType                                                    |
|----------- |------------ |--------------------------------------------------------------|
|Alias       |Alias:       |System. Management. Automation. AliasInfo                        |
|Certificado |Cert:        |Microsoft. PowerShell. Commands. X509StoreLocation               |
|            |             |System.Security.Cryptography.X509Certificates.X509Certificate2|
|Ambiente |Env:         |System. Collections. DictionaryEntry                            |
|FileSystem  |C: (*)       |System. IO. FileInfo                                            |
|            |             |System. IO. DirectoryInfo                                       |
|Função    |Função:    |System. Management. Automation. FunctionInfo                     |
|Registro    |HKLM: HKCU:  |Microsoft. Win32. RegistryKey                                   |
|Variável    |Variável:    |System. Management. Automation. PSVariable                       |
|WSMan       |WSMan:       |Microsoft. WSMan. Management. WSManConfigContainerElement        |

(*) As unidades do sistema de arquivos variam em cada sistema.

Você também pode criar seus próprios provedores do PowerShell e pode instalar provedores que outras pessoas desenvolvem. Para listar os provedores que estão disponíveis em sua sessão, digite:

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a>Instalando e removendo provedores

Normalmente, os provedores são instalados por meio de módulos do PowerShell. A importação do módulo carrega o provedor em sua sessão. Não é possível desinstalar os provedores internos. Você pode desinstalar provedores carregados por outros módulos.

Você pode descarregar um provedor da sessão atual usando o `Remove-Module` cmdlet. Esse cmdlet não desinstala o provedor, mas torna o provedor indisponível na sessão.

Você também pode usar o `Remove-PSDrive` cmdlet para remover qualquer unidade da sessão atual. Esses dados na unidade não são afetados, mas a unidade não está mais disponível nessa sessão.

## <a name="viewing-providers"></a>Exibindo provedores

Para exibir os provedores do PowerShell no seu computador, digite:

```powershell
Get-PSProvider
```

A saída lista os provedores internos e os provedores que você adicionou à sessão.

## <a name="the-provider-cmdlets"></a>Os cmdlets do provedor

Os cmdlets a seguir foram projetados para trabalhar com os dados expostos por qualquer provedor. Você pode usar os mesmos cmdlets da mesma maneira para gerenciar os diferentes tipos de dados que os provedores expõem. Depois de aprender a gerenciar os dados de um provedor, você pode usar os mesmos procedimentos com os dados de qualquer provedor.

Por exemplo, o `New-Item` cmdlet cria um novo item. Na `C:` unidade com suporte do provedor **FileSystem** , você pode usar o `New-Item` para criar um novo arquivo ou pasta. Nas unidades que têm suporte do provedor de **registro** , você pode usar o `New-Item` para criar uma nova chave do registro. Na `Alias:` unidade, você pode usar `New-Item` para criar um novo alias.

Para obter informações detalhadas sobre qualquer um dos seguintes cmdlets, digite:

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a>Cmdlets ChildItem

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a>Cmdlets de conteúdo

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a>Cmdlets de item

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Rename-Item](xref:Microsoft.PowerShell.Management.Rename-Item)
- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a>Cmdlets ItemProperty

- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Rename-ItemProperty](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a>Cmdlets de local

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Pop-Location](xref:Microsoft.PowerShell.Management.Pop-Location)
- [Push-Location](xref:Microsoft.PowerShell.Management.Push-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a>Cmdlets de caminho

- [Join-Path](xref:Microsoft.PowerShell.Management.Join-Path)
- [Convert-Path](xref:Microsoft.PowerShell.Management.Convert-Path)
- [Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)
- [Resolve-Path](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a>Cmdlets PSDrive

- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [New-PSDrive](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [Remove-PSDrive](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a>Cmdlets PSProvider

- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a>Exibindo dados do provedor

O principal benefício de um provedor é que ele expõe seus dados de uma maneira familiar e consistente. O modelo de apresentação de dados é uma unidade do sistema de arquivos.

O provedor permite exibir, navegar e alterar itens no armazenamento de dados, como se eles fossem dados em um sistema de arquivos. O armazenamento de dados é acessado pelo nome da unidade que ele suporta.

A unidade é listada na exibição padrão do `Get-PSProvider` cmdlet, mas você pode obter informações sobre a unidade do provedor usando o `Get-PSDrive` cmdlet. Por exemplo, para obter todas as propriedades da unidade Function:, digite:

```powershell
Get-PSDrive Function | Format-List *
```

Você pode exibir e percorrer os dados em uma unidade de provedor da mesma forma como faria em uma unidade de sistema de arquivos.

Para exibir o conteúdo de uma unidade de provedor, use os cmdlets Get-Item ou Get-ChildItem. Digite o nome da unidade seguido por dois-pontos (:). Por exemplo, para exibir o conteúdo da unidade Alias:, digite:

```powershell
Get-Item alias:
```

Você pode exibir e gerenciar os dados em qualquer unidade de outra unidade, incluindo o nome da unidade no caminho. Por exemplo, para exibir a chave do registro HKLM\Software na unidade HKLM: de outra unidade, digite:

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

Para abrir a unidade, use o cmdlet Set-Location. Lembre-se dos dois-pontos ao especificar o caminho da unidade. Por exemplo, para alterar o local para o diretório raiz da unidade CERT:, digite:

```powershell
Set-Location cert:
```

Em seguida, para exibir o conteúdo da unidade CERT:, digite:

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a>Movimentação por meio de dados hierárquicos

Você pode percorrer uma unidade de provedor assim como faria com uma unidade de disco rígido.
Se os dados forem organizados em uma hierarquia de itens dentro de itens, use uma barra invertida ( `\` ) para indicar um item filho. Use o seguinte formato:

```
drive:\location\child-location\...
```

Por exemplo, para alterar seu local para a chave do registro HKLM\Software, digite um comando Set-Location, como:

```powershell
Set-Location HKLM:\SOFTWARE\
```

Se qualquer elemento no nome totalmente qualificado incluir espaços, você deverá colocar o nome entre aspas duplas ( `"` ). O exemplo a seguir mostra um caminho totalmente qualificado que inclui espaços.

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

Você também pode usar referências relativas a locais. Um ponto ( `.` ) representa o local atual. Por exemplo, se você estiver na `HKLM:\Software\Microsoft` chave do registro e desejar listar as subchaves do registro na `HKLM:\Software\Microsoft\PowerShell` chave, digite o seguinte comando:

```powershell
Get-ChildItem .\PowerShell
```

Além disso, os pontos duplos ( `..` ) referem-se ao diretório ou contêiner diretamente acima do seu local atual. Você pode usar pontos duplos ( `..` ) para navegar por uma hierarquia de provedor.

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a>Página inicial do provedor

Os provedores também têm um local de **residência** .  Esse local é compartilhado por todos os `PSDrives` apoiados pelo provedor. Ele pode ser recuperado exibindo a propriedade **Home** do provedor.

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

O provedor **FileSystem** é o único provedor que tem um valor padrão para **Home**. É o mesmo valor que `$Home` . Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

Você pode definir o diretório **base** para um provedor, para a sessão atual, usando sua propriedade.

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

O `~` caractere pode ser usado para representar o diretório base do provedor.
Se o provedor não tiver um local de **residência** definido, você verá um erro.

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a>Localizando parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados a um cmdlet por um provedor. Esses parâmetros estão disponíveis somente quando o cmdlet é usado com o provedor que os adicionou.

Por exemplo, a `Cert:` unidade adiciona o parâmetro **CodeSigningCert** aos `Get-Item` `Get-ChildItem` cmdlets e. Você pode usar esse parâmetro somente quando usar `Get-Item` ou `Get-ChildItem` na `Cert:` unidade.

Para obter uma lista dos parâmetros dinâmicos aos quais um provedor dá suporte, consulte o arquivo de ajuda para o provedor. Tipo:

```
Get-Help <provider-name>
```

Por exemplo:

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a>Aprendendo sobre provedores

Embora todos os dados do provedor apareçam nas unidades e você use os mesmos métodos para movê-los, a similaridade é interrompida. Os armazenamentos de dados que o provedor expõe podem ser tão variados quanto Active Directory locais e caixas de correio do Microsoft Exchange Server.

Para obter informações sobre provedores individuais do PowerShell, digite:

```
Get-Help <ProviderName>
```

Por exemplo:

```powershell
Get-Help registry
```

Para obter uma lista de tópicos de ajuda sobre os provedores, digite:

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a>Consulte também

[about_Locations](about_Locations.md)

[about_Path_Syntax](about_Path_Syntax.md)

