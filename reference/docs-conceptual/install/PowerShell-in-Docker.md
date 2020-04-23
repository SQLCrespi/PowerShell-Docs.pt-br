---
title: Como usar o PowerShell no Docker
description: Como usar o PowerShell pré-instalado em uma imagem do Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: b16a31a04ca863ab55c7c9718b1a1a973e61ee46
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80646366"
---
# <a name="using-powershell-in-docker"></a>Como usar o PowerShell no Docker

Publicamos imagens do Docker com o PowerShell pré-instalado. Este artigo mostra como começar a usar o PowerShell no contêiner do Docker.

## <a name="finding-available-images"></a>Localizar imagens disponíveis

As imagens liberadas exigem o Docker 17.05 ou mais recente. Também é esperado que você possa executar o Docker sem `sudo` ou direitos administrativos locais. Siga as [instruções][install] oficiais do Docker para instalar o `docker` corretamente.

Os contêineres de versão derivam da imagem de distribuição oficial, como `centos:7`, instalam dependências e finalmente instalam o pacote do PowerShell.

Esses contêineres residem em [hub.docker.com/r/microsoft/powershell][docker-release].

Para obter mais informações sobre essas imagens do Docker, visite o repositório [PowerShell-Docker][PowerShell-Docker] no GitHub.

## <a name="using-powershell-in-a-container"></a>Usar o PowerShell em um contêiner

As etapas a seguir mostram os comandos do Docker necessários para baixar a imagem e iniciar uma sessão interativa do PowerShell.

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a>Remover a imagem quando não for mais necessária

O comando a seguir é usado para excluir a imagem do Docker quando você não precisa mais dela.

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a>Informações legais e licenciamento

O PowerShell está licenciado nos termos da [licença MIT][].

### <a name="windows-docker-file-and-image-licenses"></a>Licenças de arquivo e imagem do Docker do Windows

Ao solicitar e usar os contêineres Imagem do Sistema Operacional do Contêiner para Windows, você reconhece, entende e concorda com os Termos de Licença Complementares disponíveis no hub do Docker:

- [Window Server Core][Window Server Core]
- [Nano Server][Nano Server]

### <a name="telemetry"></a>Telemetria

Por padrão, o PowerShell coleta telemetria limitada sem informações de identificação pessoal para ajudar no desenvolvimento de versões futuras do PowerShell. Para desativar o envio de telemetria, crie uma variável de ambiente chamada `POWERSHELL_TELEMETRY_OPTOUT` definida como um valor de `1` antes de iniciar o PowerShell a partir do local instalado. A telemetria que coletamos se enquadra na [Política de Privacidade da Microsoft][privacy].

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[docker-release]: https://hub.docker.com/r/microsoft/powershell/
[appinsights]: https://azure.microsoft.com/services/application-insights/
[licença MIT]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[PowerShell-Docker]: https://github.com/PowerShell/PowerShell-Docker
[Window Server Core]: https://hub.docker.com/r/microsoft/windowsservercore/
[Nano Server]: https://hub.docker.com/r/microsoft/nanoserver/
[privacy]: https://privacy.microsoft.com/privacystatement/
