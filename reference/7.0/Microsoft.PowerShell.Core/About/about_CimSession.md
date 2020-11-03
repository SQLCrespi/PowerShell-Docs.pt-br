---
description: Descreve um objeto **CimSession** e a diferença entre sessões CIM e sessões do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CimSession
ms.openlocfilehash: 21015e1457dfcc037dd65cbf3b2f7f85c9076106
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195522"
---
# <a name="about-cimsession"></a>Sobre o CimSession

## <a name="short-description"></a>Descrição breve
Descreve um objeto **CimSession** e a diferença entre sessões CIM e sessões do PowerShell.

## <a name="long-description"></a>Descrição longa

Uma sessão de modelo CIM (CIM) é um objeto do lado do cliente que representa uma conexão com um computador local ou com um computador remoto. Você pode usar sessões CIM como uma alternativa para sessões do PowerShell (PSSessions). Ambas as abordagens têm vantagens.

Você pode usar o `New-CimSession` cmdlet para criar uma sessão CIM que contém informações sobre uma conexão, como o nome do computador, o protocolo usado para a conexão, a ID da sessão e a ID da instância.

Depois de criar um objeto **CimSession** que especifica as informações necessárias para estabelecer uma conexão, o PowerShell não estabelece a conexão imediatamente. Quando um cmdlet usa a sessão CIM, o PowerShell se conecta ao computador especificado e, em seguida, quando o cmdlet é concluído, o PowerShell encerra a conexão.

Se você criar uma **PSSession** em vez de usar uma sessão CIM, o PowerShell validará as configurações de conexão e, em seguida, estabelecerá e manterá a conexão. Se você usar sessões CIM, o PowerShell não abrirá uma conexão de rede até que seja necessário. Para obter mais informações sobre sessões do PowerShell, consulte [about_PSSessions](about_PSSessions.md).

## <a name="when-to-use-a-cim-session"></a>Quando usar uma sessão CIM

Somente os cmdlets que funcionam com um provedor Instrumentação de Gerenciamento do Windows (WMI) ou CIM WS-Man aceitam sessões CIM. Para outros cmdlets, use **PSSessions** .

Quando você usa uma sessão CIM, o PowerShell executa o cmdlet no cliente local. Ele se conecta ao provedor WMI usando a sessão CIM. O computador de destino não requer o PowerShell, nem mesmo qualquer versão do sistema operacional Windows.

Por outro lado, um cmdlet executado usando uma **PSSession** é executado no computador de destino.
Ele requer o PowerShell no sistema de destino. Além disso, o cmdlet envia dados de volta para o computador local. O PowerShell gerencia os dados enviados pela conexão e mantém o tamanho dentro dos limites definidos por Gerenciamento Remoto do Windows (WinRM). As sessões CIM não impõem os limites do WinRM.

## <a name="using-cdxml-cmdlets"></a>Usando cmdlets do CDXML

Os cmdlets de XML de definição de cmdlet (CDXML) baseados em CIM podem ser gravados para usar qualquer provedor WMI. Todos os provedores WMI usam objetos **CimSession** . Para obter mais informações sobre o CDXML, consulte [definição e termos do cdxml](/previous-versions/windows/desktop/wmi_v2/cdxml-overview).

Os cmdlets do CDXML têm um parâmetro **CimSession** automático que pode usar uma matriz de objetos **CimSession** . Por padrão, o PowerShell limita o número de conexões de CIM simultâneas a 15. Esse limite pode ser substituído por cmdlets CDXML que implementam o **ThrottleLimit** . Consulte a documentação do cmdlet individual para entender o **ThrottleLimit** .

## <a name="see-also"></a>CONSULTE TAMBÉM

[New-CimSession](xref:CimCmdlets.New-CimSession)

[about_PSSessions](about_PSSessions.md)
