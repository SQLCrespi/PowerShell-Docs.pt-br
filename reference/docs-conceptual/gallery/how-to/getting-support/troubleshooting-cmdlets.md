---
ms.date: 12/01/2020
title: Cmdlets de solução de problemas
description: Este artigo fornece informações e etapas para solucionar erros usando a Galeria do PowerShell
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913311"
---
# <a name="troubleshooting-cmdlets"></a>Cmdlets de solução de problemas

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Como resolver o problema "AVISO: Falha ao baixar o pacote 'nome do seu pacote'"

Há relatos de que `Install-Module` ou `Update-Module` às vezes falha em alguns computadores. Com base em nossa investigação, isso está relacionado à conexão de rede. Recentemente, atualizamos o provedor do NuGet para que ele possa baixar pacotes de forma confiável. Siga as instruções abaixo para instalar o build mais recente do provedor do NuGet e instalar ou atualizar seu módulo. Vamos usar o módulo “Azure” como o exemplo abaixo.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a>Pontos de extremidade de rede necessários

Os cmdlets de instalação e atualização exigem acesso à Internet para se conectar aos pontos de extremidade de rede usados pela Galeria do PowerShell. Verifique se suas políticas de acesso à rede permitem a conexão aos pontos de extremidade a seguir.

- `psg-prod-eastus.azureedge.net` – nome do host CDN
- `az818661.vo.msecnd.net` – nome do host CDN
- `devopsgallerystorage.blob.core.windows.net` – nome do host da conta de armazenamento
- `*.powershellgallery.com` – site
- `go.microsoft.com` – serviço de redirecionamento

> [!NOTE]
> Os cmdlets que interagem com a Galeria do PowerShell podem falhar com erros inesperados quando há uma interrupção dos serviços dessa Galeria. Para ver o status atual da Galeria do PowerShell, confira a página [Status da Galeria do PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) no GitHub.
