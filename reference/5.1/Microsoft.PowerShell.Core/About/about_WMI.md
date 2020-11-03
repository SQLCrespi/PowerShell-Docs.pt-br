---
description: O Instrumentação de Gerenciamento do Windows (WMI) usa o modelo CIM (CIM) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciáveis da empresa moderna.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196136"
---
# <a name="about-wmi"></a>Sobre o WMI

## <a name="short-description"></a>DESCRIÇÃO BREVE

O Instrumentação de Gerenciamento do Windows (WMI) usa o modelo CIM (CIM) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciáveis da empresa moderna.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Instrumentação de Gerenciamento do Windows (WMI) é a implementação da Microsoft do WBEM (Web-Based Enterprise Management), o padrão do setor.

O WMI clássico usa DCOM para se comunicar com dispositivos de rede para gerenciar sistemas remotos. O Windows PowerShell 3,0 apresenta um modelo de provedor CIM que usa o WinRM para remover a dependência no DCOM. Esse modelo de provedor CIM também usa novas APIs de provedor de WMI que permitem aos desenvolvedores escrever cmdlets do Windows PowerShell em código nativo (C \+ \+ ).

Não confunda provedores WMI com provedores do Windows PowerShell. Muitos recursos do Windows têm um provedor WMI associado que expõe seus recursos de gerenciamento. Para obter provedores WMI, execute uma consulta WMI que obtém instâncias da classe __Provider WMI, como a consulta a seguir.

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a>TRÊS COMPONENTES DO WMI

Os três componentes do WMI a seguir interagem com o Windows PowerShell: namespaces, provedores e classes.

Os namespaces do WMI organizam provedores WMI e classes WMI em grupos de componentes relacionados. Dessa forma, eles são semelhantes aos namespaces .NET Framework.
Os namespaces não são locais físicos, mas são mais semelhantes aos bancos de dados lógicos.
Todos os namespaces WMI são instâncias da classe de sistema __Namespace. O namespace WMI padrão é raiz \/ CIMV2 (desde o Microsoft Windows 2000). Para usar o Windows PowerShell para obter namespaces WMI na sessão atual, use um comando com o formato a seguir.

```powershell
Get-WmiObject -Class __Namespace
```

Para obter namespaces WMI em outros namespaces, use o parâmetro namespace para alterar o local da pesquisa. O comando a seguir localiza namespaces WMI que residem no namespace root/Cimv2/Applications.

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

Os namespaces do WMI são hierárquicos. Portanto, a obtenção de uma lista de todos os namespaces em um sistema específico requer a execução de uma consulta recursiva começando no namespace raiz.

Os provedores WMI expõem informações sobre objetos gerenciáveis do Windows. Um provedor recupera dados de um componente e passa esses dados por meio do WMI para um aplicativo de gerenciamento, como o Windows PowerShell. A maioria dos provedores de WMI são provedores dinâmicos, o que significa que eles obtêm os dados dinamicamente quando solicitados por meio do aplicativo de gerenciamento.

## <a name="finding-wmi-classes"></a>LOCALIZANDO CLASSES WMI

Em uma instalação padrão do Windows 8, há mais de 1.100 classes WMI na raiz \/ Cimv2. Com essas muitas classes WMI, o desafio torna-se a identificação da classe WMI apropriada a ser usada para executar uma tarefa específica. O Windows PowerShell 3,0 fornece duas maneiras de localizar classes WMI relacionadas a um tópico específico.

Por exemplo, para localizar classes WMI no \\ namespace WMI cimv2 raiz que estão relacionadas a discos, você pode usar uma consulta como a mostrada aqui.

```powershell
Get-WmiObject -List *disk*
```

Para localizar classes WMI relacionadas à memória, você pode usar uma consulta como a mostrada aqui.

```powershell
Get-WmiObject -List *memory*
```

Os cmdlets do CIM também fornecem a capacidade de descobrir classes WMI. Para fazer isso, use o cmdlet Get-CIMClass. O comando mostrado aqui lista as classes WMI relacionadas ao vídeo.

```powershell
Get-CimClass *video*
```

A expansão de tabulação funciona quando os namespaces WMI são alterados e, portanto, o uso da expansão de tabulação torna os namespaces de subwmi facilmente detectáveis. No exemplo a seguir, o cmdlet Get-CimClass lista as classes WMI relacionadas às configurações de energia.
Para encontrá-lo, digite o `root/CIMV2/` namespace e pressione a tecla Tab várias vezes até que o namespace de energia seja exibido. Veja o código:

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
