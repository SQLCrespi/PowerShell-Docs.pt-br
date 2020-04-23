---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Executando tarefas de rede
ms.openlocfilehash: e0aa3b8ef3d911ab0fe851f6621d70e1265c5bd4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737195"
---
# <a name="performing-networking-tasks"></a><span data-ttu-id="59dba-103">Executando tarefas de rede</span><span class="sxs-lookup"><span data-stu-id="59dba-103">Performing Networking Tasks</span></span>

<span data-ttu-id="59dba-104">Como TCP/IP é o protocolo de rede mais frequentemente usado, a maioria das tarefas de administração de protocolo de rede de baixo nível envolve TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="59dba-104">Because TCP/IP is the most commonly used network protocol, most low-level network protocol administration tasks involve TCP/IP.</span></span> <span data-ttu-id="59dba-105">Nesta seção, usamos o PowerShell e o WMI para realizar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="59dba-105">In this section, we use PowerShell and WMI to do these tasks.</span></span>

## <a name="listing-ip-addresses-for-a-computer"></a><span data-ttu-id="59dba-106">Listando de endereços IP para um computador</span><span class="sxs-lookup"><span data-stu-id="59dba-106">Listing IP Addresses for a Computer</span></span>

<span data-ttu-id="59dba-107">Para obter todos os endereços IP em uso no computador local, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="59dba-107">To get all IP addresses in use on the local computer, use the following command:</span></span>

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExpandProperty IPAddress
```

<span data-ttu-id="59dba-108">A saída desse comando é diferente da maioria das listas de propriedades, porque os valores são colocados entre chaves:</span><span class="sxs-lookup"><span data-stu-id="59dba-108">The output of this command differs from most property lists, because values are enclosed in braces:</span></span>

```Output
10.0.0.1
fe80::60ea:29a7:a233:7cb7
2601:600:a27f:a470:f532:6451:5630:ec8b
2601:600:a27f:a470:e167:477d:6c5c:342d
2601:600:a27f:a470:b021:7f0d:eab9:6299
2601:600:a27f:a470:a40e:ebce:1a8c:a2f3
2601:600:a27f:a470:613c:12a2:e0e0:bd89
2601:600:a27f:a470:444f:17ec:b463:7edd
2601:600:a27f:a470:10fd:7063:28e9:c9f3
2601:600:a27f:a470:60ea:29a7:a233:7cb7
2601:600:a27f:a470::2ec1
```

<span data-ttu-id="59dba-109">Para entender por que as chaves são exibidas, use o cmdlet `Get-Member` para examinar a propriedade **IPAddress**:</span><span class="sxs-lookup"><span data-stu-id="59dba-109">To understand why the braces appear, use the `Get-Member` cmdlet to examine the **IPAddress** property:</span></span>

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Get-Member -Name IPAddress
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_NetworkAdapterConfiguration
Name      MemberType Definition
----      ---------- ----------
IPAddress Property   string[] IPAddress {get;}
```

<span data-ttu-id="59dba-110">A propriedade IPAddress para cada adaptador de rede na verdade é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="59dba-110">The IPAddress property for each network adapter is actually an array.</span></span> <span data-ttu-id="59dba-111">As chaves na definição indicam que **IPAddress** não é um valor de **System.String**, mas sim uma matriz de valores **System.String**.</span><span class="sxs-lookup"><span data-stu-id="59dba-111">The braces in the definition indicate that **IPAddress** is not a **System.String** value, but an array of **System.String** values.</span></span>

## <a name="listing-ip-configuration-data"></a><span data-ttu-id="59dba-112">Listando dados de configuração de IP</span><span class="sxs-lookup"><span data-stu-id="59dba-112">Listing IP Configuration Data</span></span>

<span data-ttu-id="59dba-113">Para exibir dados detalhados de configuração de IP de cada adaptador de rede, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="59dba-113">To display detailed IP configuration data for each network adapter, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true
```

<span data-ttu-id="59dba-114">A exibição padrão para o objeto de configuração do adaptador de rede é um conjunto muito reduzido das informações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="59dba-114">The default display for the network adapter configuration object is a very reduced set of the available information.</span></span> <span data-ttu-id="59dba-115">Para inspeção profunda e solução de problemas, use `Select-Object` ou um cmdlet de formatação, como `Format-List`, para especificar as propriedades a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="59dba-115">For in-depth inspection and troubleshooting, use `Select-Object` or a formatting cmdlet, such as `Format-List`, to specify the properties to be displayed.</span></span>

<span data-ttu-id="59dba-116">Em redes TCP/IP modernas, é provável que você não tenha interesse em propriedades IPX ou WINS.</span><span class="sxs-lookup"><span data-stu-id="59dba-116">In modern TCP/IP networks you are probably not interested in IPX or WINS properties.</span></span> <span data-ttu-id="59dba-117">Você pode usar o parâmetro **ExcludeProperty** de `Select-Object` para ocultar propriedades que têm nomes que começam com "WINS" ou "IPX".</span><span class="sxs-lookup"><span data-stu-id="59dba-117">You can use the **ExcludeProperty** parameter of `Select-Object` to hide properties with names that begin with "WINS" or "IPX".</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExcludeProperty IPX*,WINS*
```

<span data-ttu-id="59dba-118">Esse comando retorna informações detalhadas sobre o DHCP, DNS, roteamento e outras propriedades de configuração de IP secundárias.</span><span class="sxs-lookup"><span data-stu-id="59dba-118">This command returns detailed information about DHCP, DNS, routing, and other minor IP configuration properties.</span></span>

## <a name="pinging-computers"></a><span data-ttu-id="59dba-119">Executando ping em computadores</span><span class="sxs-lookup"><span data-stu-id="59dba-119">Pinging Computers</span></span>

<span data-ttu-id="59dba-120">Você pode executar um ping simples em um computador usando **Win32_PingStatus**.</span><span class="sxs-lookup"><span data-stu-id="59dba-120">You can perform a simple ping against a computer using by **Win32_PingStatus**.</span></span> <span data-ttu-id="59dba-121">O comando a seguir executa o ping, mas retorna uma saída longa:</span><span class="sxs-lookup"><span data-stu-id="59dba-121">The following command performs the ping, but returns lengthy output:</span></span>

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'"
```

<span data-ttu-id="59dba-122">Uma forma mais útil de resumir as informações é exibir as propriedades Address, ResponseTime e StatusCode geradas pelo comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="59dba-122">A more useful form for summary information a display of the Address, ResponseTime, and StatusCode properties, as generated by the following command.</span></span> <span data-ttu-id="59dba-123">O parâmetro **Autosize** de `Format-Table` redimensiona as colunas da tabela para que sejam exibidas corretamente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59dba-123">The **Autosize** parameter of `Format-Table` resizes the table columns so that they display properly in PowerShell.</span></span>

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'" |
  Format-Table -Property Address,ResponseTime,StatusCode -Autosize
```

```Output
Address   ResponseTime StatusCode
-------   ------------ ----------
127.0.0.1            0          0
```

<span data-ttu-id="59dba-124">Um StatusCode de 0 indica um ping bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="59dba-124">A StatusCode of 0 indicates a successful ping.</span></span>

<span data-ttu-id="59dba-125">Você pode usar uma matriz para executar o ping de vários computadores com um único comando.</span><span class="sxs-lookup"><span data-stu-id="59dba-125">You can use an array to ping multiple computers with a single command.</span></span> <span data-ttu-id="59dba-126">Como há mais de um endereço, use `ForEach-Object` para executar ping em cada endereço separadamente:</span><span class="sxs-lookup"><span data-stu-id="59dba-126">Because there is more than one address, use the `ForEach-Object` to ping each address separately:</span></span>

```powershell
'127.0.0.1','localhost','research.microsoft.com' |
  ForEach-Object -Process {
    Get-CimInstance -Class Win32_PingStatus -Filter ("Address='$_'") |
      Select-Object -Property Address,ResponseTime,StatusCode
  }
```

<span data-ttu-id="59dba-127">Você pode usar o mesmo formato de comando para executar o ping de todos os computadores em uma sub-rede, como uma rede privada que usa o número da rede 192.168.1.0 e uma máscara de sub-rede de classe C padrão (255.255.255.0)., somente os endereços no intervalo de 192.168.1.1 a 192.168.1.254 são endereços locais legítimos (0 é sempre reservado para o número da rede e 255 é um endereço de difusão de sub-rede).</span><span class="sxs-lookup"><span data-stu-id="59dba-127">You can use the same command format to ping all of the computers on a subnet, such as a private network that uses network number 192.168.1.0 and a standard Class C subnet mask (255.255.255.0)., Only addresses in the range of 192.168.1.1 through 192.168.1.254 are legitimate local addresses (0 is always reserved for the network number and 255 is a subnet broadcast address).</span></span>

<span data-ttu-id="59dba-128">Para representar uma matriz de números de 1 a 254 no PowerShell, use a instrução **1..254.**</span><span class="sxs-lookup"><span data-stu-id="59dba-128">To represent an array of the numbers from 1 through 254 in PowerShell, use the statement **1..254.**</span></span>
<span data-ttu-id="59dba-129">Um ping de sub-rede completa pode ser executado, gerando a matriz e adicionando os valores a um endereço parcial na instrução do ping:</span><span class="sxs-lookup"><span data-stu-id="59dba-129">A complete subnet ping can be performed by generating the array and then adding the values onto a partial address in the ping statement:</span></span>

```powershell
1..254| ForEach-Object -Process {
  Get-CimInstance -Class Win32_PingStatus -Filter ("Address='192.168.1.$_ '") } |
    Select-Object -Property Address,ResponseTime,StatusCode
```

<span data-ttu-id="59dba-130">Observe que essa técnica para a geração de um intervalo de endereços também pode ser usada em outro local.</span><span class="sxs-lookup"><span data-stu-id="59dba-130">Note that this technique for generating a range of addresses can be used elsewhere as well.</span></span> <span data-ttu-id="59dba-131">Você pode gerar um conjunto completo de endereços dessa forma:</span><span class="sxs-lookup"><span data-stu-id="59dba-131">You can generate a complete set of addresses in this way:</span></span>

```powershell
$ips = 1..254 | ForEach-Object -Process {'192.168.1.' + $_}
```

## <a name="retrieving-network-adapter-properties"></a><span data-ttu-id="59dba-132">Recuperando propriedades do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="59dba-132">Retrieving Network Adapter Properties</span></span>

<span data-ttu-id="59dba-133">Mencionamos anteriormente que você pode recuperar propriedades de configuração geral usando a classe **Win32_NetworkAdapterConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="59dba-133">Earlier, we mentioned that you could retrieve general configuration properties using the **Win32_NetworkAdapterConfiguration** class.</span></span> <span data-ttu-id="59dba-134">Embora não sejam estritamente informações TCP/IP, informações do adaptador de rede, como endereços MAC e tipos de adaptador podem ser úteis para entender o que está acontecendo com um computador.</span><span class="sxs-lookup"><span data-stu-id="59dba-134">Although not strictly TCP/IP information, network adapter information such as MAC addresses and adapter types can be useful for understanding what is going on with a computer.</span></span> <span data-ttu-id="59dba-135">Para obter um resumo dessas informações, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="59dba-135">To get a summary of this information, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapter -ComputerName .
```

## <a name="assigning-the-dns-domain-for-a-network-adapter"></a><span data-ttu-id="59dba-136">Atribuindo o domínio DNS a um adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="59dba-136">Assigning the DNS Domain for a Network Adapter</span></span>

<span data-ttu-id="59dba-137">Para atribuir o domínio DNS à resolução de nomes automática, use o método **SetDNSDomain** de **Win32_NetworkAdapterConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="59dba-137">To assign the DNS domain for automatic name resolution, use the **SetDNSDomain** method of the **Win32_NetworkAdapterConfiguration**.</span></span> <span data-ttu-id="59dba-138">Como você atribui o domínio DNS a cada configuração de adaptador de rede de modo independente, é necessário usar uma instrução `ForEach-Object` para atribuir o domínio a cada adaptador:</span><span class="sxs-lookup"><span data-stu-id="59dba-138">Because you assign the DNS domain for each network adapter configuration independently, you need to use a `ForEach-Object` statement to assign the domain to each adapter:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process { $_.SetDNSDomain('fabrikam.com') }
```

<span data-ttu-id="59dba-139">A instrução de filtragem `IPEnabled=$true` é necessária porque, mesmo em uma rede que usa apenas TCP/IP, várias das configurações de adaptador de rede em um computador não são adaptadores verdadeiros de TCP/IP. Eles são elementos de software comuns compatíveis com RAS, PPTP, QoS e outros serviços para todos os adaptadores, não tendo um endereço próprio.</span><span class="sxs-lookup"><span data-stu-id="59dba-139">The filtering statement `IPEnabled=$true` is necessary, because even on a network that uses only TCP/IP, several of the network adapter configurations on a computer are not true TCP/IP adapters; they are general software elements supporting RAS, PPTP, QoS, and other services for all adapters and thus do not have an address of their own.</span></span>

<span data-ttu-id="59dba-140">É possível filtrar o comando usando o cmdlet `Where-Object`, em vez de usar o filtro `Get-CimInstance`.</span><span class="sxs-lookup"><span data-stu-id="59dba-140">You can filter the command by using the `Where-Object` cmdlet, instead of using the `Get-CimInstance` filter.</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration |
  Where-Object {$_.IPEnabled} |
    ForEach-Object -Process {$_.SetDNSDomain('fabrikam.com')}
```

## <a name="performing-dhcp-configuration-tasks"></a><span data-ttu-id="59dba-141">Executar tarefas de configuração de DHCP</span><span class="sxs-lookup"><span data-stu-id="59dba-141">Performing DHCP Configuration Tasks</span></span>

<span data-ttu-id="59dba-142">Modificar os detalhes de DHCP envolve trabalhar com um conjunto de adaptadores de rede, assim como na configuração do DNS.</span><span class="sxs-lookup"><span data-stu-id="59dba-142">Modifying DHCP details involves working with a set of network adapters, just as the DNS configuration does.</span></span> <span data-ttu-id="59dba-143">Existem várias ações diferentes que você pode executar usando o WMI, e abordaremos algumas delas.</span><span class="sxs-lookup"><span data-stu-id="59dba-143">There are several distinct actions you can perform by using WMI, and we will step through a few of the common ones.</span></span>

### <a name="determining-dhcp-enabled-adapters"></a><span data-ttu-id="59dba-144">Determinação dos adaptadores habilitados para DHCP</span><span class="sxs-lookup"><span data-stu-id="59dba-144">Determining DHCP-Enabled Adapters</span></span>

<span data-ttu-id="59dba-145">Para localizar os adaptadores habilitados para DHCP em um computador, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="59dba-145">To find the DHCP-enabled adapters on a computer, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true"
```

<span data-ttu-id="59dba-146">Para excluir adaptadores com problemas de configuração de IP, você pode recuperar apenas adaptadores habilitados para IP:</span><span class="sxs-lookup"><span data-stu-id="59dba-146">To exclude adapters with IP configuration problems, you can retrieve only IP-enabled adapters:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true"
```

### <a name="retrieving-dhcp-properties"></a><span data-ttu-id="59dba-147">Recuperando propriedades de DHCP</span><span class="sxs-lookup"><span data-stu-id="59dba-147">Retrieving DHCP Properties</span></span>

<span data-ttu-id="59dba-148">Como as propriedades relacionadas a DHCP para um adaptador geralmente começam com `DHCP`, você pode usar o parâmetro Property de `Format-Table` para exibir somente essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="59dba-148">Because DHCP-related properties for an adapter generally begin with `DHCP`, you can use the Property parameter of `Format-Table` to display only those properties:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true" |
  Format-Table -Property DHCP*
```

### <a name="enabling-dhcp-on-each-adapter"></a><span data-ttu-id="59dba-149">Habilitando o DHCP em cada adaptador</span><span class="sxs-lookup"><span data-stu-id="59dba-149">Enabling DHCP on Each Adapter</span></span>

<span data-ttu-id="59dba-150">Para habilitar o DHCP em todos os adaptadores, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="59dba-150">To enable DHCP on all adapters, use the following command:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process {$_.EnableDHCP()}
```

<span data-ttu-id="59dba-151">É possível usar a instrução **Filter** `IPEnabled=$true and DHCPEnabled=$false` para evitar habilitar o DHCP nos locais em que ele já estiver habilitado, mas omitir essa etapa não causará erros.</span><span class="sxs-lookup"><span data-stu-id="59dba-151">You can use the **Filter** statement `IPEnabled=$true and DHCPEnabled=$false` to avoid enabling DHCP where it is already enabled, but omitting this step will not cause errors.</span></span>

### <a name="releasing-and-renewing-dhcp-leases-on-specific-adapters"></a><span data-ttu-id="59dba-152">Liberar e renovar concessões de DHCP nos adaptadores específicos</span><span class="sxs-lookup"><span data-stu-id="59dba-152">Releasing and Renewing DHCP Leases on Specific Adapters</span></span>

<span data-ttu-id="59dba-153">A classe **Win32_NetworkAdapterConfiguration** tem os métodos **ReleaseDHCPLease** e **RenewDHCPLease**.</span><span class="sxs-lookup"><span data-stu-id="59dba-153">The **Win32_NetworkAdapterConfiguration** class has **ReleaseDHCPLease** and **RenewDHCPLease** methods.</span></span> <span data-ttu-id="59dba-154">Ambos são usados da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="59dba-154">Both are used in the same way.</span></span> <span data-ttu-id="59dba-155">Em geral, use esses métodos se você só precisar liberar ou renovar endereços para um adaptador em uma sub-rede específica.</span><span class="sxs-lookup"><span data-stu-id="59dba-155">In general, use these methods if you only need to release or renew addresses for an adapter on a specific subnet.</span></span> <span data-ttu-id="59dba-156">A maneira mais fácil de filtrar os adaptadores em uma sub-rede é escolher apenas as configurações de adaptador que usam o gateway para essa sub-rede.</span><span class="sxs-lookup"><span data-stu-id="59dba-156">The easiest way to filter adapters on a subnet is to choose only the adapter configurations that use the gateway for that subnet.</span></span> <span data-ttu-id="59dba-157">Por exemplo, o comando a seguir libera todas as concessões DHCP nos adaptadores no computador local que estão obtendo concessões de DHCP do 192.168.1.254:</span><span class="sxs-lookup"><span data-stu-id="59dba-157">For example, the following command releases all DHCP leases on adapters on the local computer that are obtaining DHCP leases from 192.168.1.254:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

<span data-ttu-id="59dba-158">A única alteração para renovar uma concessão de DHCP é usar o método **RenewDHCPLease** em vez do **ReleaseDHCPLease**:</span><span class="sxs-lookup"><span data-stu-id="59dba-158">The only change for renewing a DHCP lease is to use the **RenewDHCPLease** method instead of the **ReleaseDHCPLease** method:</span></span>

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

> [!NOTE]
> <span data-ttu-id="59dba-159">Ao usar esses métodos em um computador remoto, lembre-se de que você poderá perder o acesso ao sistema remoto se estiver conectado a ele por meio do adaptador com a concessão liberada ou renovada.</span><span class="sxs-lookup"><span data-stu-id="59dba-159">When using these methods on a remote computer, be aware that you can lose access to the remote system if you are connected to it through the adapter with the released or renewed lease.</span></span>

### <a name="releasing-and-renewing-dhcp-leases-on-all-adapters"></a><span data-ttu-id="59dba-160">Liberar e renovar concessões de DHCP em todos os adaptadores</span><span class="sxs-lookup"><span data-stu-id="59dba-160">Releasing and Renewing DHCP Leases on All Adapters</span></span>

<span data-ttu-id="59dba-161">Você pode executar liberações ou renovações de endereço DHCP globais em todos os adaptadores usando os métodos **Win32_NetworkAdapterConfiguration**, **ReleaseDHCPLeaseAll** e **RenewDHCPLeaseAll**.</span><span class="sxs-lookup"><span data-stu-id="59dba-161">You can perform global DHCP address releases or renewals on all adapters by using the **Win32_NetworkAdapterConfiguration** methods, **ReleaseDHCPLeaseAll** and **RenewDHCPLeaseAll**.</span></span>
<span data-ttu-id="59dba-162">No entanto, o comando deve ser aplicado à classe WMI, em vez de um adaptador específico, pois liberações e renovações de concessões globais são executada na classe, não em um adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="59dba-162">However, the command must apply to the WMI class, rather than a particular adapter, because releasing and renewing leases globally is performed on the class, not on a specific adapter.</span></span>

<span data-ttu-id="59dba-163">Você pode obter uma referência a uma classe WMI, em vez de instâncias de classe, listando todas as classes WMI e selecionando somente a classe desejada por nome.</span><span class="sxs-lookup"><span data-stu-id="59dba-163">You can get a reference to a WMI class, instead of class instances, by listing all WMI classes and then selecting only the desired class by name.</span></span> <span data-ttu-id="59dba-164">Por exemplo, o comando a seguir retorna a classe **Win32_NetworkAdapterConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="59dba-164">For example, the following command returns the **Win32_NetworkAdapterConfiguration** class:</span></span>

```powershell
Get-CimInstance -List | Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}
```

<span data-ttu-id="59dba-165">Você pode tratar o comando inteiro como a classe e, em seguida, invocar o método **ReleaseDHCPAdapterLease**.</span><span class="sxs-lookup"><span data-stu-id="59dba-165">You can treat the entire command as the class and then invoke the **ReleaseDHCPAdapterLease** method on it.</span></span> <span data-ttu-id="59dba-166">No comando a seguir, os parênteses em torno dos elementos de pipeline `Get-CimInstance` e `Where-Object` direcionam o PowerShell para avaliá-los primeiro:</span><span class="sxs-lookup"><span data-stu-id="59dba-166">In the following command, the parentheses surrounding the `Get-CimInstance` and `Where-Object` pipeline elements direct PowerShell to evaluate them first:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).ReleaseDHCPLeaseAll()
```

<span data-ttu-id="59dba-167">Você pode usar o mesmo formato de comando para invocar o método **RenewDHCPLeaseAll**:</span><span class="sxs-lookup"><span data-stu-id="59dba-167">You can use the same command format to invoke the **RenewDHCPLeaseAll** method:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).RenewDHCPLeaseAll()
```

## <a name="creating-a-network-share"></a><span data-ttu-id="59dba-168">Criando um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="59dba-168">Creating a Network Share</span></span>

<span data-ttu-id="59dba-169">Para criar um compartilhamento de rede, use o método **Create** de **Win32_Share**:</span><span class="sxs-lookup"><span data-stu-id="59dba-169">To create a network share, use the **Create** method of **Win32_Share**:</span></span>

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_Share'}).Create(
    'C:\temp','TempShare',0,25,'test share of the temp folder'
  )
```

<span data-ttu-id="59dba-170">Você também pode criar o compartilhamento usando `net share` no PowerShell no Windows:</span><span class="sxs-lookup"><span data-stu-id="59dba-170">You can also create the share by using `net share` in PowerShell on Windows:</span></span>

```powershell
net share tempshare=c:\temp /users:25 /remark:"test share of the temp folder"
```

## <a name="removing-a-network-share"></a><span data-ttu-id="59dba-171">Removendo um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="59dba-171">Removing a Network Share</span></span>

<span data-ttu-id="59dba-172">É possível remover um compartilhamento de rede com o **Win32_Share**, mas o processo é ligeiramente diferente da criação de um compartilhamento, pois você precisa recuperar o compartilhamento específico a ser removido em vez da classe **Win32_Share**.</span><span class="sxs-lookup"><span data-stu-id="59dba-172">You can remove a network share with **Win32_Share**, but the process is slightly different from creating a share, because you need to retrieve the specific share to be removed, rather than the **Win32_Share** class.</span></span> <span data-ttu-id="59dba-173">A instrução a seguir exclui o compartilhamento **TempShare**:</span><span class="sxs-lookup"><span data-stu-id="59dba-173">The following statement deletes the share **TempShare**:</span></span>

```powershell
(Get-CimInstance -Class Win32_Share -Filter "Name='TempShare'").Delete()
```

<span data-ttu-id="59dba-174">No Windows, `net share` também funciona:</span><span class="sxs-lookup"><span data-stu-id="59dba-174">In Windows, `net share` works as well:</span></span>

```powershell
net share tempshare /delete
```

```Output
tempshare was deleted successfully.
```

## <a name="connecting-a-windows-accessible-network-drive"></a><span data-ttu-id="59dba-175">Conectando-se a uma unidade de rede acessível do Windows</span><span class="sxs-lookup"><span data-stu-id="59dba-175">Connecting a Windows Accessible Network Drive</span></span>

<span data-ttu-id="59dba-176">Os cmdlets `New-PSDrive` criam uma unidade do PowerShell, mas as unidades criadas dessa forma estão disponíveis somente para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59dba-176">The `New-PSDrive` cmdlets creates a PowerShell drive, but drives created this way are available only to PowerShell.</span></span> <span data-ttu-id="59dba-177">Para criar uma nova unidade em rede, você pode usar o objeto COM **WScript.Network**.</span><span class="sxs-lookup"><span data-stu-id="59dba-177">To create a new networked drive, you can use the **WScript.Network** COM object.</span></span> <span data-ttu-id="59dba-178">O comando a seguir mapeia o compartilhamento `\\FPS01\users` para a unidade `B:` local,</span><span class="sxs-lookup"><span data-stu-id="59dba-178">The following command maps the share `\\FPS01\users` to local drive `B:`,</span></span>

```powershell
(New-Object -ComObject WScript.Network).MapNetworkDrive('B:', '\\FPS01\users')
```

<span data-ttu-id="59dba-179">No Windows, o comando `net use` também funciona:</span><span class="sxs-lookup"><span data-stu-id="59dba-179">On Windows, the `net use` command works as well:</span></span>

```powershell
net use B: \\FPS01\users
```

<span data-ttu-id="59dba-180">Unidades mapeadas com um **WScript.Network** ou `net use` ficam disponíveis imediatamente para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59dba-180">Drives mapped with either **WScript.Network** or `net use` are immediately available to PowerShell.</span></span>
