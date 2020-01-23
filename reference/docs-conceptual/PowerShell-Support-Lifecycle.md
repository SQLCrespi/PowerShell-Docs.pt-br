---
title: Ciclo de vida de suporte do PowerShell Core
description: Políticas que regem o suporte ao PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: 57804df830da01bee0f48acc374658b025a46b85
ms.sourcegitcommit: cab4e4e67dbed024864887c7f8984abb4db3a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2020
ms.locfileid: "76022222"
---
# <a name="powershell-core-support-lifecycle"></a>Ciclo de vida de suporte do PowerShell Core

O PowerShell Core é um conjunto distinto de ferramentas e componentes que é enviado, instalado e configurado separadamente do Windows PowerShell. Portanto, o PowerShell Core não está incluído nos contratos de licenciamento do Windows 7/8.1/10 ou Windows Server.

No entanto, o PowerShell Core é aceito pelos contratos de suporte tradicionais da Microsoft, incluindo [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement] e [Microsoft Software Assurance][assurance].
Você também pode pagar por [suporte assistido][] do PowerShell Core preenchendo uma solicitação de suporte para o seu problema.

## <a name="community-support"></a>Suporte da comunidade

Oferecemos também [suporte da comunidade][] no GitHub, no qual você pode registrar um problema, um bug ou uma solicitação de recurso.
Além disso, você pode encontrar ajuda de outros membros da comunidade na Microsoft [Comunidade tecnológica do PowerShell][] ou em qualquer um dos fóruns na seção Comunidade da página do hub do [PowerShell][pshub]. Não oferecemos nenhuma garantia de que a comunidade atenderá ou resolverá seu problema de maneira oportuna. Se você tiver um problema que requer atenção imediata, use as opções tradicionais de suporte pago.

## <a name="lifecycle-of-powershell-core"></a>Ciclo de vida do PowerShell Core

O PowerShell Core está adotando a [Política de ciclo de vida moderna da Microsoft][modern]. Esse ciclo de vida do suporte destina-se a manter os clientes atualizados com as versões mais recentes.

A ramificação da versão 6.x do PowerShell Core será atualizada aproximadamente a cada seis meses (por exemplo: 6.0, 6.1, 6.2 etc.)

> [!IMPORTANT]
> Você deve atualizar em seis meses após cada novo lançamento de versão secundária para continuar a receber suporte.

Por exemplo, se o PowerShell Core 6.1 for liberado em 1º de julho de 2018, espera-se que você atualize para o PowerShell Core 6.1 até 1º de janeiro de 2019 para manter o suporte.

> [!IMPORTANT]
> Você deve atualizar em 30 dias após cada novo lançamento de versão de patch para continuar a receber suporte.

Por exemplo, se você está executando o PowerShell Core 6.1 e o 6.1.3 foi lançado em 19 de fevereiro de 2019, é esperado que você atualize para o PowerShell Core 6.1.3 até 21 de março de 2019, que é 30 dias após o lançamento, para manter o suporte. Se qualquer correção for considerada necessária, ela será lançada na nossa próxima atualização cumulativa.

A política de ciclo de vida moderna também requer que a Microsoft forneça aos clientes um aviso 12 meses antes de interromper o suporte para um produto (ou seja, o PowerShell Core).

Por fim, esperamos que o PowerShell Core adote a abordagem de manutenção de longo prazo. Nessa abordagem de manutenção, exigiríamos apenas que as atualizações de serviço e segurança permanecessem em suporte em um branch/versão específica do 6.x.

## <a name="supported-platforms"></a>Plataformas compatíveis

Para confirmar se a plataforma e a versão do PowerShell Core têm suporte oficial, confira a tabela a seguir.

Nossa comunidade também contribuiu com pacotes para algumas plataformas, mas eles não têm suporte oficial. Esses pacotes são marcados como `Community` na tabela.

As plataformas listadas como `Experimental` não têm suporte oficial, mas estão disponíveis para experimentação e comentários.

| Plataforma                                          |      6.2      |    7.0    |
|---------------------------------------------------|:-------------:|:---------:|
| Windows 7, 8.1 e 10                            |   Com suporte   | Com suporte |
| Windows Server 2008 R2, 2012 R2, 2016             |   Com suporte   | Com suporte |
| [Canal Semestral do Windows Server][semi-annual] |   Com suporte   | Com suporte |
| Ubuntu 16.04 e 18.04                            |   Com suporte   | Com suporte |
| Ubuntu 18.10 (por meio do pacote Snap)                   |   Comunidade   | Comunidade |
| Ubuntu 19.04 (por meio do pacote Snap)                   |   Comunidade   | Comunidade |
| Debian 9                                          |   Com suporte   | Com suporte |
| Debian 10                                         | Sem suporte | Com suporte |
| CentOS 7                                          |   Com suporte   | Com suporte |
| CentOS 8                                          | Sem suporte | Com suporte |
| Red Hat Enterprise Linux 7                        |   Com suporte   | Com suporte |
| Red Hat Enterprise Linux 8                        | Sem suporte | Com suporte |
| OpenSUSE 42.3                                     |   Com suporte   | Com suporte |
| Fedora 28                                         |   Com suporte   | Com suporte |
| Fedora 29, 30                                     | Sem suporte | Com suporte |
| Alpine 3.8                                        |   Veja a observação    | Veja a observação  |
| Alpine 3.9 e 3.10                               | Sem suporte | Veja a observação  |
| macOS 10.12+                                      |   Com suporte   | Com suporte |
| Arch                                              |   Comunidade   | Comunidade |
| Raspbian                                          |   Comunidade   | Comunidade |
| Kali                                              |   Comunidade   | Comunidade |
| AppImage (funciona em várias plataformas Linux)      |   Comunidade   | Comunidade |
| [Pacote Snap](https://snapcraft.io/powershell)   |   Consultar a observação    | Consultar a observação  |

> [!NOTE]
> Os pacotes Snap têm suporte da mesma forma que a distribuição na qual você está executando o pacote.

> [!NOTE]
> O modelo CIM, a comunicação remota do PowerShell e a DSC não são compatíveis com o Alpine.

## <a name="powershell-releases-end-of-life"></a>Fim da vida útil das versões do PowerShell

Com base no [Ciclo de vida do PowerShell Core](#lifecycle-of-powershell-core), a tabela a seguir lista as datas em que várias versões não receberão mais suporte.

| Versão | Fim da vida útil                   |
|---------|-------------------------------|
| 6,0     | 13 de fevereiro de 2019             |
| 6.1     | 28 de setembro de 2019            |
| 6.2     | 6 meses após 7 lançamentos     |

## <a name="unsupported-platforms"></a>Plataformas sem suporte

Quando uma versão de plataforma atingir o final da vida, conforme definido pelo proprietário da plataforma, o PowerShell Core também encerrará o suporte dessa versão de plataforma. Os pacotes liberados anteriormente continuarão disponíveis para clientes que precisam de acesso, mas suporte formal e atualizações de qualquer tipo não serão fornecidos.

Portanto, os proprietários de distribuição encerraram o suporte para as versões a seguir, que não têm mais suporte.

| Plataforma | Versão | Fim de vida                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| Fedora   | 24      | [Agosto de 2017](https://fedoramagazine.org/fedora-24-eol/)                                    |
| Fedora   | 25      | [Dezembro de 2017](https://fedoramagazine.org/fedora-25-end-life/)                             |
| Fedora   | 26      | [Maio de 2018](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| openSUSE | 42.1    | [Maio de 2017](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| openSUSE | 42.2    | [Janeiro de 2018](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| Ubuntu   | 16.10   | [Julho de 2017](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| Ubuntu   | 17.04   | [Janeiro de 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| Ubuntu   | 17.10   | [Julho de 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| Debian   | 8       | [Junho de 2018](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| Fedora   | 27      | [Novembro de 2018](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| Ubuntu   | 14.04   | [Abril de 2019](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a>Observações sobre o licenciamento

O PowerShell Core foi lançado sob a [licença MIT][]. Sob essa licença e sem um contrato de suporte pago, os usuários estão limitados ao [suporte da comunidade][]. Com o suporte da comunidade, a Microsoft não faz nenhuma garantia de capacidade de resposta ou correções.

## <a name="windows-powershell-module"></a>Módulo do Windows PowerShell

O suporte para o PowerShell Core não inclui módulos do produto, a menos que esses módulos deem suporte explicitamente ao PowerShell Core. Por exemplo, usar o módulo `ActiveDirectory` fornecido como parte do Windows Server é um cenário sem suporte.

No entanto, os módulos que não dão suporte explicitamente ao PowerShell Core podem ser compatíveis em alguns casos. Instalando o módulo [WindowsPSModulePath][], é possível adicionar o `PSModulePath` do Windows PowerShell ao `PSModulePath` do seu PowerShell Core.

Primeiro, instale o módulo do **WindowsPSModulePath** pela Galeria do PowerShell:

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

Depois de instalar esse módulo, execute o cmdlet `Add-WindowsPSModulePath` para adicionar o Windows PowerShell `PSModulePath` ao PowerShell Core:

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a>Recursos experimentais

Os [recursos experimentais][] estão limitados ao [suporte da comunidade](#community-support).

[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[suporte da comunidade]: https://github.com/powershell/powershell/issues
[pshub]: https://docs.microsoft.com/powershell
[Comunidade tecnológica do PowerShell]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[suporte assistido]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[licença MIT]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[WindowsPSModulePath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Recursos experimentais]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
