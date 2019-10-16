---
title: Parâmetros de fluxo de trabalho comuns | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5891467-8e13-484d-b7af-32e6bffab35d
caps.latest.revision: 4
ms.openlocfilehash: b2e8f272a82ee03de306fd8eac45e109142f6284
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366045"
---
# <a name="common-workflow-parameters"></a>Parâmetros de fluxo de trabalho comuns

Uma atividade de fluxo de trabalho gerada a partir de um cmdlet do Windows PowerShell define um número de parâmetros comuns a todas as atividades. Um subconjunto desses parâmetros pode ser especificado no momento da criação para que os autores de fluxo de trabalho possam personalizar atividades. Outro subconjunto desses parâmetros pode ser especificado pelo usuário ao chamar a atividade.

Os parâmetros de fluxo de trabalho comuns são agrupados em várias categorias da seguinte maneira.

## <a name="connectivity-parameters"></a>Parâmetros de conectividade

|Nome|Tipo|Descrição|Pode ser especificado pelo usuário final no momento da execução?|Pode ser especificado pelo autor do fluxo de trabalho no momento da criação?|Pode ser especificado pelo autor do fluxo de trabalho na instanciação?|
|----------|----------|-----------------|-----------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|PSComputerName|String[]|Uma lista de nomes de computador para os quais iniciar trabalhos.|Sim|Sim|Sim|
|PSCredential|[System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential)|A credencial de autenticação a ser usada para fazer logon nos computadores especificados pelo parâmetro PSComputerName. Esse parâmetro será válido somente se PSComputerName for especificado.|Sim|Sim|Sim|
|PSPort|UInt32|A porta a ser usada para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSUseSSL|Booliano|Use o protocolo protocolo SSL (SSL) para estabelecer uma conexão segura com o computador remoto para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSConfigurationName|Cadeia de caracteres|A configuração de sessão usada para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSApplicationName|Cadeia de caracteres|A parte do nome do aplicativo do URI de conexão para a execução do fluxo de trabalho. Use esse parâmetro somente quando não estiver usando o parâmetro Conexãouri.|Sim|Sim|Sim|
|PSThrottleLimit|UInt32|O número máximo de conexões simultâneas que podem ser estabelecidas para executar o fluxo de trabalho.|Sim|TBD|Sim|
|PSConnectionURI|String[]|Uma matriz de URIs totalmente qualificados que especificam os pontos de extremidade para as sessões interativas usadas para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSAllowRedirection|Booliano|Especifica se deve permitir o redirecionamento dessa conexão a um URI alternativo para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSSessionOption|[System. Management. Automation. Remoting. PSSessionOption](/dotnet/api/System.Management.Automation.Remoting.PSSessionOption)|Opções avançadas para a sessão usada para executar o fluxo de trabalho.|Sim|Sim|Sim|
|PSAuthentication|[System. Management. Automation. Runspaces. AuthenticationMechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)|Um valor da enumeração [System. Management. Automation. Runspaces. AuthenticationMechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism) que especifica o mecanismo de autenticação usado para autenticar as credenciais do usuário.|Sim|Sim|Sim|
|PSCertificateThumbprint|Cadeia de caracteres|O certificado de chave pública digital (X509) de uma conta de usuário que tem permissão para executar o fluxo de trabalho.|Sim|Sim|Sim|

### <a name="behavior-parameters"></a>Parâmetros de comportamento