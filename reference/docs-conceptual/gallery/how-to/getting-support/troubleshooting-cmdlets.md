---
ms.date: 06/12/2017
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Cmdlets de solução de problemas
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72352103"
---
# <a name="troubleshooting-cmdlets"></a>Cmdlets de solução de problemas

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Como resolver o problema "AVISO: Falha ao baixar o pacote 'nome do seu pacote'"

Há relatos de que `Install-Module` ou `Update-Module` às vezes falha em alguns computadores. Com base em nossa investigação, isso está relacionado à conexão de rede. Recentemente, atualizamos o provedor do NuGet para que ele possa baixar pacotes de forma confiável. Siga as instruções abaixo para instalar o build mais recente do provedor do NuGet e instalar ou atualizar seu módulo. Vamos usar o módulo “Azure” como o exemplo abaixo.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a>Pontos de extremidade de rede necessários

Os cmdlets de instalação e atualização exigem acesso à Internet para se conectar aos pontos de extremidade de rede usados pela Galeria do PowerShell. Verifique se suas políticas de acesso à rede permitem a conexão aos pontos de extremidade a seguir.

- oneget.org
- go.microsoft.com
- az818661.vo.msecnd.net
- [www.powershellgallery.com](www.powershellgallery.com)
- devopsgallerystorage.blob.core.windows.net
