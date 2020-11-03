---
description: PackageManagement é um agregador para gerenciadores de pacotes de software.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 5b4b42dfce03831da5cc317276e78e0777ff73d6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196287"
---
# <a name="about-packagemanagement"></a>Sobre PackageManagement

## <a name="short-description"></a>DESCRIÇÃO BREVE
PackageManagement é um agregador para gerenciadores de pacotes de software.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A funcionalidade de PackageManagement foi introduzida no Windows PowerShell 5,0.

O PackageManagement é uma interface unificada para sistemas de gerenciamento de pacotes de software; Você pode executar cmdlets do PackageManagement para executar tarefas de descoberta de software, instalação e inventário (SDII). Independentemente da tecnologia de instalação subjacente, você pode executar os cmdlets comuns no módulo PackageManagement para pesquisar, instalar ou desinstalar pacotes; Adicionar, remover e consultar repositórios de pacotes; e executar consultas em um computador para determinar quais pacotes de software estão instalados.

O PackageManagement dá suporte a um modelo de plug-in flexível que habilita o suporte para outros sistemas de gerenciamento de pacotes de software.

O módulo PackageManagement está incluído no Windows PowerShell 5,0 e versões posteriores do PowerShell e funciona em três níveis de estrutura de gerenciamento de pacotes: provedores de pacote, origens de pacote e os próprios pacotes. Vamos definir alguns termos:

- Gerenciador de pacotes: sistema de gerenciamento de pacotes de software. Em termos de PackageManagement, este é um provedor de pacote.
- Provedor de pacote: termo PackageManagement para um Gerenciador de pacotes. Os exemplos podem incluir Windows Installer, Chocolatey e outros.
- Origem do pacote: uma URL, uma pasta local ou uma pasta de rede compartilhada que você configura provedores de pacote para usar como um repositório.
- Pacote: uma parte do software que um provedor de pacote gerencia e que é armazenado em uma origem de pacote específica.

O módulo PackageManagement inclui os cmdlets a seguir. Para obter mais informações, consulte a ajuda do [PackageManagement](/powershell/module/packagemanagement) .

- `Get-PackageProvider`: Retorna uma lista de provedores de pacote que estão conectados ao PackageManagement.
- `Get-PackageSource`: Obtém uma lista de origens de pacote que são registradas para um provedor de pacote.
- `Register-PackageSource`: Adiciona uma origem de pacote para um provedor de pacote especificado.
- `Set-PackageSource`: Define as propriedades em uma origem de pacote existente.
- `Unregister-PackageSource`: Remove uma origem de pacote registrada.
- `Get-Package`: Retorna uma lista de pacotes de software instalados.
- `Find-Package`: Localiza pacotes de software em fontes de pacote disponíveis.
- `Install-Package`: Instala um ou mais pacotes de software.
- `Save-Package`: Salva pacotes no computador local sem instalá-los.
- `Uninstall-Package`: Desinstala um ou mais pacotes de software.

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a>Inicialização do provedor de pacote e parâmetros de cmdlet dinâmico

Por padrão, o PackageManagement é fornecido com um provedor de inicialização principal. Você pode instalar provedores de pacote adicionais conforme precisar deles inicializando os provedores; ou seja, responder a um prompt para instalar o provedor automaticamente, de um serviço Web. Você pode especificar um provedor de pacote com qualquer cmdlet de PackageManagement; Se o provedor especificado não estiver disponível, o PackageManagement solicitará que você inicialize (ou instale automaticamente) o provedor. Nos exemplos a seguir, se o provedor de Chocolatey ainda não estiver instalado, a inicialização de PackageManagement instalará o provedor.

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

Se o provedor de Chocolatey ainda não estiver instalado, quando você executar o comando anterior, será solicitado a instalá-lo.

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

Se o provedor de Chocolatey ainda não estiver instalado, quando você executar o comando anterior, o provedor será instalado; Mas como o parâmetro ForceBootstrap foi adicionado ao comando, você não será solicitado a instalá-lo; o provedor e o pacote são instalados automaticamente.

Ao tentar instalar um pacote, se você ainda não tiver o provedor de suporte instalado e não adicionar o parâmetro ForceBootstrap ao comando, o PackageManagement solicitará que você instale o provedor.

A especificação de um provedor de pacote no comando PackageManagement pode disponibilizar parâmetros dinâmicos específicos para esse provedor de pacote. Quando você executa Get-Help para um cmdlet de PackageManagement específico, uma lista de conjuntos de parâmetros é retornada, agrupando parâmetros dinâmicos para provedores de pacotes disponíveis em conjuntos de parâmetros separados.

Mais informações sobre o projeto PackageManagement

Para obter mais informações sobre o projeto de desenvolvimento aberto do PackageManagement, incluindo como criar um provedor de pacote de PackageManagement, consulte o projeto PackageManagement no GitHub em https://oneget.org .

## <a name="see-also"></a>CONSULTE TAMBÉM

[Get-PackageProvider](xref:PackageManagement.Get-PackageProvider)

[Get-PackageSource](xref:PackageManagement.Get-PackageSource)

[Register-PackageSource](xref:PackageManagement.Register-PackageSource)

[Set-PackageSource](xref:PackageManagement.Set-PackageSource)

[Unregister-PackageSource](xref:PackageManagement.Unregister-PackageSource)

[Get-Package](xref:PackageManagement.Get-Package)

[Find-Package](xref:PackageManagement.Find-Package)

[Install-Package](xref:PackageManagement.Install-Package)

[Save-Package](xref:PackageManagement.Save-Package)

[Uninstall-Package](xref:PackageManagement.Uninstall-Package)
