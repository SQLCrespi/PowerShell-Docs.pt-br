---
ms.date: 09/13/2016
ms.topic: reference
title: Suporte à ajuda online
description: Suporte à ajuda online
ms.openlocfilehash: 0164b5e6c6c8d66a6ab2467a8adfb7efffe0fe17
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645428"
---
# <a name="supporting-online-help"></a><span data-ttu-id="a2eff-103">Suporte à ajuda online</span><span class="sxs-lookup"><span data-stu-id="a2eff-103">Supporting Online Help</span></span>

<span data-ttu-id="a2eff-104">A partir do PowerShell 3,0, há duas maneiras de dar suporte ao `Get-Help` recurso online para comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2eff-104">Beginning in PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for PowerShell commands.</span></span> <span data-ttu-id="a2eff-105">Este tópico explica como implementar esse recurso para diferentes tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="a2eff-105">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="a2eff-106">Sobre a ajuda online</span><span class="sxs-lookup"><span data-stu-id="a2eff-106">About Online Help</span></span>

<span data-ttu-id="a2eff-107">A ajuda online sempre foi uma parte vital do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2eff-107">Online help has always been a vital part of PowerShell.</span></span> <span data-ttu-id="a2eff-108">Embora o `Get-Help` cmdlet exiba tópicos de ajuda no prompt de comando, muitos usuários preferem a experiência de leitura online, incluindo codificação por cores, hiperlinks e compartilhamento de ideias em conteúdo da Comunidade e documentos baseados em wiki.</span><span class="sxs-lookup"><span data-stu-id="a2eff-108">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="a2eff-109">O mais importante é que, antes do advento da ajuda atualizável, a ajuda online forneceu a versão mais atualizada dos arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="a2eff-109">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="a2eff-110">Com o advento da ajuda atualizável no PowerShell 3,0, a ajuda online ainda exerce uma função vital.</span><span class="sxs-lookup"><span data-stu-id="a2eff-110">With the advent of Updatable Help in PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="a2eff-111">Além da experiência do usuário flexível, a ajuda online fornece ajuda aos usuários que não ou que não podem usar a ajuda atualizável para baixar tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="a2eff-111">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="a2eff-112">Como o Get-Help-online funciona</span><span class="sxs-lookup"><span data-stu-id="a2eff-112">How Get-Help -Online Works</span></span>

<span data-ttu-id="a2eff-113">Para ajudar os usuários a encontrar os tópicos da ajuda online para comandos, o `Get-Help` comando tem um parâmetro online que abre a versão online do tópico da ajuda para um comando no navegador de Internet padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-113">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default internet browser.</span></span>

<span data-ttu-id="a2eff-114">Por exemplo, o comando a seguir abre o tópico da ajuda online para o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2eff-114">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="a2eff-115">Para implementar `Get-Help -Online` , o `Get-Help` cmdlet procura um Uniform Resource Identifier (URI) para o tópico de ajuda da versão online nos locais a seguir.</span><span class="sxs-lookup"><span data-stu-id="a2eff-115">To implement `Get-Help -Online`, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="a2eff-116">O primeiro link na seção **links relacionados** do tópico da ajuda para o comando.</span><span class="sxs-lookup"><span data-stu-id="a2eff-116">The first link in the **Related Links** section of the help topic for the command.</span></span> <span data-ttu-id="a2eff-117">O tópico da ajuda deve ser instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-117">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="a2eff-118">Esse recurso foi introduzido no PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="a2eff-118">This feature was introduced in PowerShell 2.0.</span></span>

- <span data-ttu-id="a2eff-119">A propriedade **HelpUri** de qualquer comando.</span><span class="sxs-lookup"><span data-stu-id="a2eff-119">The **HelpUri** property of any command.</span></span> <span data-ttu-id="a2eff-120">A propriedade **HelpUri** é acessível mesmo quando o tópico da ajuda do comando não está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-120">The **HelpUri** property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="a2eff-121">Esse recurso foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a2eff-121">This feature was introduced in PowerShell 3.0.</span></span>

  <span data-ttu-id="a2eff-122">`Get-Help` procura um URI na primeira entrada da seção **links relacionados** antes de obter o valor da propriedade **HelpUri** .</span><span class="sxs-lookup"><span data-stu-id="a2eff-122">`Get-Help` looks for a URI in the first entry in the **Related Links** section before getting the **HelpUri** property value.</span></span> <span data-ttu-id="a2eff-123">Se o valor da propriedade estiver incorreto ou alterado, você poderá substituí-lo inserindo um valor diferente no primeiro link relacionado.</span><span class="sxs-lookup"><span data-stu-id="a2eff-123">If the property value is incorrect or has changed, you can override it by entering a different value in the first related link.</span></span> <span data-ttu-id="a2eff-124">No entanto, o primeiro link relacionado funciona somente quando os tópicos da ajuda são instalados no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-124">However, the first related link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="a2eff-125">Adicionando um URI ao primeiro link relacionado de um tópico de ajuda de comando</span><span class="sxs-lookup"><span data-stu-id="a2eff-125">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="a2eff-126">Você pode dar suporte a `Get-Help -Online` qualquer comando, adicionando um URI válido à primeira entrada na seção **links relacionados** do tópico da ajuda baseada em XML para o comando.</span><span class="sxs-lookup"><span data-stu-id="a2eff-126">You can support `Get-Help -Online` for any command by adding a valid URI to the first entry in the **Related Links** section of the XML-based help topic for the command.</span></span> <span data-ttu-id="a2eff-127">Essa opção só é válida em tópicos de ajuda baseados em XML e funciona somente quando o tópico da ajuda está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-127">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="a2eff-128">Quando o tópico da ajuda é instalado e o URI é populado, esse valor tem precedência sobre a propriedade **HelpUri** do comando.</span><span class="sxs-lookup"><span data-stu-id="a2eff-128">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="a2eff-129">Para dar suporte a esse recurso, o URI deve aparecer no `maml:uri` elemento sob o primeiro `maml:relatedLinks/maml:navigationLink` elemento no `maml:relatedLinks` elemento.</span><span class="sxs-lookup"><span data-stu-id="a2eff-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="a2eff-130">O XML a seguir mostra o posicionamento correto do URI.</span><span class="sxs-lookup"><span data-stu-id="a2eff-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="a2eff-131">O `Online version:` texto no `maml:linkText` elemento é uma prática recomendada, mas não é necessário.</span><span class="sxs-lookup"><span data-stu-id="a2eff-131">The `Online version:` text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml
<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="a2eff-132">Adicionando a propriedade HelpUri a um comando</span><span class="sxs-lookup"><span data-stu-id="a2eff-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="a2eff-133">Esta seção mostra como adicionar a propriedade HelpUri a comandos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a2eff-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="a2eff-134">Adicionando uma propriedade HelpUri a um cmdlet</span><span class="sxs-lookup"><span data-stu-id="a2eff-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="a2eff-135">Para os cmdlets escritos em C#, adicione um atributo **HelpUri** à classe **cmdlet** .</span><span class="sxs-lookup"><span data-stu-id="a2eff-135">For cmdlets written in C#, add a **HelpUri** attribute to the **Cmdlet** class.</span></span> <span data-ttu-id="a2eff-136">O valor do atributo deve ser um URI que começa com `http` ou `https` .</span><span class="sxs-lookup"><span data-stu-id="a2eff-136">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="a2eff-137">O código a seguir mostra o atributo **HelpUri** da `Get-History` classe cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2eff-137">The following code shows the **HelpUri** attribute of the `Get-History` cmdlet class.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="a2eff-138">Adicionando uma propriedade HelpUri a uma função avançada</span><span class="sxs-lookup"><span data-stu-id="a2eff-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="a2eff-139">Para funções avançadas, adicione uma propriedade **HelpUri** ao atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="a2eff-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="a2eff-140">O valor da propriedade deve ser um URI que comece com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="a2eff-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="a2eff-141">O código a seguir mostra o atributo **HelpUri** da `New-Calendar` função</span><span class="sxs-lookup"><span data-stu-id="a2eff-141">The following code shows the **HelpUri** attribute of the `New-Calendar` function</span></span>

```powershell
function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="a2eff-142">Adicionando um atributo HelpUri a um comando CIM</span><span class="sxs-lookup"><span data-stu-id="a2eff-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="a2eff-143">Para comandos CIM, adicione um atributo **HelpUri** ao elemento **CMDLETMETADATA** no arquivo CDXML.</span><span class="sxs-lookup"><span data-stu-id="a2eff-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span>
<span data-ttu-id="a2eff-144">O valor do atributo deve ser um URI que começa com `http` ou `https` .</span><span class="sxs-lookup"><span data-stu-id="a2eff-144">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="a2eff-145">O código a seguir mostra o atributo HelpUri do `Start-Debug` comando CIM</span><span class="sxs-lookup"><span data-stu-id="a2eff-145">The following code shows the HelpUri attribute of the `Start-Debug` CIM command</span></span>

```xml
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="a2eff-146">Adicionando um atributo HelpUri a um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a2eff-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="a2eff-147">Para fluxos de trabalho que são gravados na linguagem do PowerShell, adicione um **. ExternalHelp** a diretiva de comentário para o código do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2eff-147">For workflows that are written in the PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="a2eff-148">O valor da diretiva deve ser um URI que começa com `http` ou `https` .</span><span class="sxs-lookup"><span data-stu-id="a2eff-148">The value of the directive must be a URI that begins with `http` or `https`.</span></span>

> [!NOTE]
> <span data-ttu-id="a2eff-149">A propriedade HelpUri não tem suporte para fluxos de trabalho baseados em XAML no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2eff-149">The HelpUri property is not supported for XAML-based workflows in PowerShell.</span></span>

<span data-ttu-id="a2eff-150">O código a seguir mostra o. Diretiva ExternalHelp em um arquivo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2eff-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
