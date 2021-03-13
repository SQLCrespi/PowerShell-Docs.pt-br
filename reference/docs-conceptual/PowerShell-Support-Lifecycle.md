---
title: Ciclo de vida de suporte do PowerShell Core
description: Políticas que regem o suporte para o PowerShell
ms.date: 11/11/2020
ms.openlocfilehash: a11c4df1f105364307b8a99ffe9b0cc7e9c29122
ms.sourcegitcommit: 925819a5ad5799650c14944bd3e50fb309a7e6c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "102771470"
---
# <a name="powershell-support-lifecycle"></a>Ciclo de vida de suporte do PowerShell

O PowerShell é um conjunto distinto de ferramentas e componentes que é enviado, instalado e configurado separadamente do Windows PowerShell. O PowerShell não está incluído nos contratos de licenciamento do Windows.

O PowerShell é aceito pelos contratos de suporte tradicionais da Microsoft, incluindo [suporte pago][], [Microsoft Enterprise Agreements][enterprise-agreement] e [Microsoft Software Assurance][assurance]. Você também pode pagar por [suporte assistido][] do PowerShell preenchendo uma solicitação de suporte para o seu problema.

## <a name="community-support"></a>Suporte da comunidade

Oferecemos também [suporte da comunidade][] no GitHub, no qual você pode registrar um problema, um bug ou uma solicitação de recurso.
Além disso, você pode encontrar ajuda de outros membros da comunidade na Microsoft [Comunidade tecnológica do PowerShell][] ou em qualquer um dos fóruns na seção Comunidade da página do hub do [PowerShell][pshub]. Não oferecemos nenhuma garantia de que a comunidade atenderá ou resolverá seu problema de maneira oportuna. Se você tiver um problema que requer atenção imediata, use as opções tradicionais de suporte pago.

## <a name="lifecycle-of-powershell-7"></a>Ciclo de vida do PowerShell 7

Com o lançamento do PowerShell 7, o PowerShell continua a ter suporte na [Política de ciclo de vida moderna da Microsoft][modern], mas as datas de suporte estão vinculadas ao [ciclo de vida de suporte do .NET Core][Long-Term]. Nessa abordagem de manutenção, os clientes podem escolher versões de LTS (suporte de longo prazo) ou versões atuais. O PowerShell 7.0 é uma versão de LTS. O suporte termina com o suporte do .NET Core 3.1. A próxima versão de LTS segue a próxima versão de LTS do .NET Core. Confira a [tabela de fim da vida útil das versões do PowerShell](#powershell-releases-end-of-life) para obter as datas atuais do fim de suporte. As atualizações de versão de LTS contêm apenas atualizações críticas de segurança, de manutenção e correções que são projetadas para evitar ou minimizar o impacto nas cargas de trabalho existentes.

Uma versão atual é uma versão que ocorre entre as versões de LTS. As versões atuais podem conter correções críticas, inovações e novos recursos. A versão atual recebe suporte por três meses após a próxima versão atual ou com LTS.

> [!IMPORTANT]
> Você deve ter a atualização de patch mais recente instalada para se qualificar para o suporte. Por exemplo, se você estiver executando o PowerShell 7.0 e o 7.0.1 foi lançado, será necessário atualizar para o 7.0.1 para se qualificar para suporte.

## <a name="supported-platforms"></a>Plataformas compatíveis

Para confirmar se a plataforma e a versão do PowerShell Core têm suporte oficial, confira a tabela a seguir.

Nossa comunidade também contribuiu com pacotes para algumas plataformas, mas eles não têm suporte oficial. Esses pacotes são marcados como `Community` na tabela.

As plataformas listadas como `Experimental` não têm suporte oficial, mas estão disponíveis para experimentação e comentários.

<!-- TODO: update OS list -->

|                     Plataforma                      |      7.0      |      7.1      |
| ------------------------------------------------- | :-----------: | :-----------: |
| Windows 8.1 e 10                               |   Com suporte   |   Com suporte   |
| Windows Server 2012 R2, 2016, 2019                |   Com suporte   |   Com suporte   |
| [Canal Semestral do Windows Server][semi-annual] |   Com suporte   |   Com suporte   |
| Ubuntu 16.04, 18.04                               |   Com suporte   |   Com suporte   |
| Ubuntu 20.04                                      | Sem suporte |   Com suporte   |
| Ubuntu 19.10, 20.10 (via pacote Snap)            |   Comunidade   |   Com suporte   |
| Debian 9                                          |   Com suporte   |   Com suporte   |
| Debian 10                                         |   Com suporte   |   Com suporte   |
| CentOS 7                                          |   Com suporte   |   Com suporte   |
| CentOS 8                                          |   Com suporte   |   Com suporte   |
| Red Hat Enterprise Linux 7                        |   Com suporte   |   Com suporte   |
| Red Hat Enterprise Linux 8                        |   Com suporte   |   Com suporte   |
| Fedora 31+                                        |   Com suporte   | Sem suporte |
| Alpine 3.10                                       |   Confira a observação 1  | Sem suporte |
| Alpine 3.11+                                      |   Confira a observação 1  |   Confira a observação 1  |
| macOS 10.13 ou posterior                                      |   Com suporte   |   Com suporte   |
| Arch                                              |   Comunidade   |   Comunidade   |
| Raspbian                                          |   Comunidade   |   Comunidade   |
| Kali                                              |   Comunidade   |   Comunidade   |
| AppImage (funciona em várias plataformas Linux)      |   Comunidade   |   Comunidade   |
| [Pacote Snap](https://snapcraft.io/powershell)   |   Confira a observação 2  |   Consultar a observação    |

> [!NOTE]
> - 1 - O modelo CIM, a comunicação remota do PowerShell e a DSC não são compatíveis com o Alpine.
> - 2 - Os pacotes Snap têm suporte da mesma forma que a distribuição na qual você está executando o pacote.

## <a name="powershell-releases-end-of-life"></a>Fim da vida útil das versões do PowerShell

Com base no [Ciclo de vida do PowerShell](#lifecycle-of-powershell-7), a tabela a seguir lista as datas em que várias versões não receberão mais suporte.

| Versão |          Fim da vida útil           |
| :-----: | ------------------------------ |
|   7.1   | Meados de fevereiro de 2022 (projeção) |
|   7.0   | 3 de dezembro de 2022               |
|   6.2   | 4 de setembro de 2020              |
|   6.1   | 28 de setembro de 2019             |
|   6,0   | 13 de fevereiro de 2019              |

> [!NOTE]
> Este documento trata do suporte para o PowerShell Core. O Windows PowerShell (1.0 – 5.1) é um componente do sistema operacional Windows. Os componentes recebem o mesmo suporte que seu produto ou plataforma pai. Para saber mais, confira [Informações do ciclo de vida de produtos e serviços](/lifecycle/products/).

## <a name="unsupported-platforms"></a>Plataformas sem suporte

Quando uma versão de plataforma atingir o final da vida, conforme definido pelo proprietário da plataforma, o PowerShell Core também encerrará o suporte dessa versão de plataforma. Os pacotes liberados anteriormente continuarão disponíveis para clientes que precisam de acesso, mas suporte formal e atualizações de qualquer tipo não serão fornecidos.

Portanto, os proprietários de distribuição encerraram o suporte para as versões a seguir, que não têm mais suporte.

<!-- TODO: Update this table Jason-->

|    Plataforma    | Versão |                                                         Fim de vida                                                          |
| -------------- | :-----: | ---------------------------------------------------------------------------------------------------------------------------- |
| Debian         |    8    | [Junho de 2018](https://lists.debian.org/debian-security-announce/2018/msg00132.html)                                            |
| Fedora         |   24    | [Agosto de 2017](https://fedoramagazine.org/fedora-24-eol/)                                                                     |
| Fedora         |   25    | [Dezembro de 2017](https://fedoramagazine.org/fedora-25-end-life/)                                                              |
| Fedora         |   26    | [Maio de 2018](https://fedoramagazine.org/fedora-26-end-life/)                                                                   |
| Fedora         |   27    | [Novembro de 2018](https://fedoramagazine.org/fedora-27-end-of-life/)                                                           |
| Fedora         |   28    | [Maio de 2019](https://fedoramagazine.org/fedora-28-end-of-life/)                                                                |
| openSUSE       |  42.1   | [Maio de 2017](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)                                      |
| openSUSE       |  42.2   | [Janeiro de 2018](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html)                                  |
| openSUSE       |  42.3   | [Julho de 2019](https://lists.opensuse.org/opensuse-security-announce/2019-07/msg00000.html)                                     |
| Ubuntu         |  14.04  | [Abril de 2019](https://wiki.ubuntu.com/Releases)                                                                               |
| Ubuntu         |  16.10  | [Julho de 2017](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)                                         |
| Ubuntu         |  17.04  | [Janeiro de 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)                                           |
| Ubuntu         |  17.10  | [Julho de 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)                                         |
| Windows        |    7    | [Janeiro de 2020](https://support.microsoft.com/help/4057281/windows-7-support-ended-on-january-14-2020)                        |
| Windows Server | 2008 R2 | [Janeiro de 2020](https://support.microsoft.com/help/4456235/end-of-support-for-windows-server-2008-and-windows-server-2008-r2) |

## <a name="notes-on-licensing"></a>Observações sobre o licenciamento

O PowerShell Core foi lançado sob a [licença MIT][]. Sob essa licença e sem um contrato de suporte pago, os usuários estão limitados ao [suporte da comunidade][]. Com o suporte da comunidade, a Microsoft não faz nenhuma garantia de capacidade de resposta ou correções.

## <a name="windows-powershell-compatibility"></a>Compatibilidade do Windows PowerShell

O ciclo de vida de suporte do PowerShell não abrange os módulos fornecidos fora do pacote de versão do PowerShell 7. Por exemplo, usar o módulo `ActiveDirectory` fornecido como parte do Windows Server tem suporte com base no [Ciclo de vida de suporte do Windows][].

O PowerShell 7 melhora a compatibilidade com módulos existentes do PowerShell criados para o Windows PowerShell.
Para saber mais, confira o artigo [about_Windows_Compatibility][] e a [lista de compatibilidade do módulo][].

> [!NOTE]
> O módulo [**WindowsPSModulePath**](https://www.powershellgallery.com/packages/WindowsPSModulePath) não é mais necessário no PowerShell 7 e não tem suporte.

## <a name="experimental-features"></a>Recursos experimentais

Os [recursos experimentais][] estão limitados ao [suporte da comunidade](#community-support).

## <a name="security-servicing-criteria"></a>Critérios de manutenção de segurança

O PowerShell segue os [Critérios da manutenção de segurança da Microsoft no Windows][].
A tabela a seguir descreve os recursos que atendem aos critérios de manutenção e os que não atendem.

|                  Recurso                   |       Type       |
| ------------------------------------------ | ---------------- |
| Política de execução                           | Defesa em profundidade |
| Bloqueio do sistema – com o AppLocker           | Defesa em profundidade |
| Modo de linguagem restrita – com o AppLocker | Defesa em profundidade |
| Bloqueio do sistema – com o WDAC                | Recurso de segurança |
| Modo de linguagem restrita – com o WDAC      | Recurso de segurança |

Para obter mais informações sobre o AppLocker e o WDAC (Controle de Aplicativos do Windows Defender), confira [Controles de Aplicativos para Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control).

## <a name="release-history"></a>Histórico de versões

A tabela a seguir contém uma linha do tempo das principais versões do PowerShell. Esta tabela é fornecida para referência histórica. Ela não se destina ao uso para determinar o ciclo de vida do suporte.

|         Versão          | Data de lançamento |                                                                     Observação                                                                      |
| ------------------------ | :----------: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| PowerShell 7.1 (atual) |   Novembro de 2020   | Criado no .NET Core 5.0 (atual).                                                                                                             |
| PowerShell 7.0 (LTS)     |   Março de 2020   | Criado no .NET Core 3.1 (LTS).                                                                                                                 |
| PowerShell 6.2           |   Março de 2019   |                                                                                                                                               |
| PowerShell 6.1           |   Setembro de 2018   | Criado no .NET Core 2.1.                                                                                                                       |
| PowerShell 6.0           |   Janeiro de 2018   | Primeira versão, criada no .NET Core 2.0. Instalável no Windows, Linux e macOS.                                                              |
| PowerShell 5.1           |   Agosto de 2016   | Lançado na Atualização de Aniversário do Windows 10 e no Windows Server 2016.                                                                            |
| PowerShell 5.0           |   Fevereiro de 2016   | Lançado no WMF (Windows Management Framework) 5.0.                                                                                           |
| PowerShell 4.0           |   Outubro de 2013   | Integrado no Windows 8.1 e no Windows Server 2012 R2. Instalável no Windows 7 SP1, Windows Server 2008 R2 SP1 e Windows Server 2012. |
| PowerShell 3.0           |   Outubro de 2012   | Integrado no Windows 8 e no Windows Server 2012. Instalável no Windows 7 SP1, Windows Server 2008 SP1 e Windows Server 2008 R2 SP1.  |
| PowerShell 2.0           |   Julho de 2009   | Integrado no Windows 7 e no Windows Server 2008 R2. Instalável no Windows XP SP3, Windows Server 2003 SP2 e Windows Vista SP1.            |
| PowerShell 1.0           |   Novembro de 2006   | Instalável no Windows XP SP2, Windows Server 2003 SP1 e Windows Vista. Componente opcional do Windows Server 2008.                          |

<!-- hyperlink references -->
[suporte pago]: https://support.microsoft.com/hub/4343728/support-for-business
[enterprise-agreement]: https://www.microsoft.com/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx
[suporte da comunidade]: /powershell/scripting/community/community-support
[pshub]: /powershell
[Comunidade tecnológica do PowerShell]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[suporte assistido]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[Long-Term]: https://dotnet.microsoft.com/platform/support/policy/dotnet-core
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: /windows-server/get-started/semi-annual-channel-overview
[licença MIT]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[about_Windows_Compatibility]: /powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility
[Ciclo de vida de suporte do Windows]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[lista de compatibilidade do módulo]: /powershell/scripting/whats-new/module-compatibility
[WindowsPSModulePath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Recursos experimentais]: /powershell/module/microsoft.powershell.core/about/about_powershell_config#experimentalfeatures
[Critérios da manutenção de segurança da Microsoft no Windows]: https://www.microsoft.com/msrc/windows-security-servicing-criteria
