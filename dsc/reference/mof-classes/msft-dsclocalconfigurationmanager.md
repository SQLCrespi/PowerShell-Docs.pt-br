---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Classe MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 09b30edd48384c0e8412e0e6ee926a719249c5b8
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726894"
---
# <a name="msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="40455-103">Classe MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="40455-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="40455-104">O LCM (Gerenciador de Configurações Local) que controla os estados dos arquivos de configuração e usa o Agente de Configuração para aplicar as configurações.</span><span class="sxs-lookup"><span data-stu-id="40455-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="40455-105">A sintaxe a seguir é simplificada do código MOF (Managed Object Format) e inclui todas as propriedades herdadas.</span><span class="sxs-lookup"><span data-stu-id="40455-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="40455-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="40455-106">Syntax</span></span>

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="40455-107">Membros</span><span class="sxs-lookup"><span data-stu-id="40455-107">Members</span></span>

<span data-ttu-id="40455-108">A classe **MSFT_DSCLocalConfigurationManager** tem os seguintes membros:</span><span class="sxs-lookup"><span data-stu-id="40455-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

- <span data-ttu-id="40455-109">[Métodos][]</span><span class="sxs-lookup"><span data-stu-id="40455-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="40455-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="40455-110">Methods</span></span>

<span data-ttu-id="40455-111">A classe **MSFT_DSCLocalConfigurationManager** tem os métodos a seguir.</span><span class="sxs-lookup"><span data-stu-id="40455-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="40455-112">Método</span><span class="sxs-lookup"><span data-stu-id="40455-112">Method</span></span> |<span data-ttu-id="40455-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="40455-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="40455-114">ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="40455-115">Usa o Agente de Configuração para aplicar a configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="40455-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="40455-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="40455-117">Desabilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="40455-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="40455-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="40455-119">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="40455-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="40455-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="40455-121">Envia o documento de configuração para o nó gerenciado e usa o método **Get** do Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="40455-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="40455-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="40455-123">Obtém a saída do Agente de Configuração relacionada a um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="40455-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="40455-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="40455-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="40455-125">Obtém o histórico do status de configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="40455-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="40455-127">Obtém as configurações LCM que são usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="40455-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="40455-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="40455-129">Inicia a verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="40455-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="40455-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="40455-131">Remove os arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="40455-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="40455-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="40455-133">Chama diretamente o método **Get** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="40455-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="40455-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="40455-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="40455-135">Chama diretamente o método **Set** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="40455-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="40455-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="40455-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="40455-137">Chama diretamente o método **Test** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="40455-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="40455-138">Reversão</span><span class="sxs-lookup"><span data-stu-id="40455-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="40455-139">Reverte a uma configuração anterior.</span><span class="sxs-lookup"><span data-stu-id="40455-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="40455-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="40455-141">Envia o documento de configuração para o nó gerenciado e o salva como alteração pendente.</span><span class="sxs-lookup"><span data-stu-id="40455-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="40455-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="40455-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="40455-143">Envia o documento de configuração para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="40455-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="40455-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="40455-145">Envia o documento de configuração para o nó gerenciado e começa a usar o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="40455-146">Use GetConfigurationResultOutput para recuperar a saída do resultado.</span><span class="sxs-lookup"><span data-stu-id="40455-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="40455-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="40455-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="40455-148">Obtém as configurações de LCM que são usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="40455-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="40455-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="40455-150">Interrompe a configuração em andamento.</span><span class="sxs-lookup"><span data-stu-id="40455-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="40455-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="40455-152">Envia o documento de configuração para o nó gerenciado e verifica a configuração atual de acordo com o documento.</span><span class="sxs-lookup"><span data-stu-id="40455-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|

## <a name="requirements"></a><span data-ttu-id="40455-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40455-153">Requirements</span></span>

<span data-ttu-id="40455-154">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="40455-154">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="40455-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="40455-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>
