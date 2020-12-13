---
ms.date: 07/17/2020
ms.topic: reference
title: Recurso nxFile de DSC para Linux
description: Recurso nxFile de DSC para Linux
ms.openlocfilehash: 14a8174a92f1bbde9b1f16cf814ef7c83309c737
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389021"
---
# <a name="dsc-for-linux-nxfile-resource"></a><span data-ttu-id="df7d6-103">Recurso nxFile de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="df7d6-103">DSC for Linux nxFile Resource</span></span>

<span data-ttu-id="df7d6-104">O recurso **nxFile** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar arquivos e diretórios em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="df7d6-104">The **nxFile** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and directories on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="df7d6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df7d6-105">Syntax</span></span>

```Syntax
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage | ignore } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="df7d6-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="df7d6-106">Properties</span></span>

|<span data-ttu-id="df7d6-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="df7d6-107">Property</span></span> |<span data-ttu-id="df7d6-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="df7d6-108">Description</span></span> |
|---|---|
|<span data-ttu-id="df7d6-109">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="df7d6-109">DestinationPath</span></span> |<span data-ttu-id="df7d6-110">Especifica o local onde você deseja garantir o estado de um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="df7d6-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="df7d6-111">SourcePath</span><span class="sxs-lookup"><span data-stu-id="df7d6-111">SourcePath</span></span> |<span data-ttu-id="df7d6-112">Especifica o caminho do qual o recurso de arquivo ou pasta deve ser copiado.</span><span class="sxs-lookup"><span data-stu-id="df7d6-112">Specifies the path from which to copy the file or folder resource.</span></span> <span data-ttu-id="df7d6-113">Esse caminho poderá ser um caminho local ou uma URL `http/https/ftp`.</span><span class="sxs-lookup"><span data-stu-id="df7d6-113">This path may be a local path, or an `http/https/ftp` URL.</span></span> <span data-ttu-id="df7d6-114">As URLs `http/https/ftp` remotas só são compatíveis quando o valor da propriedade **Type** é **file**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-114">Remote `http/https/ftp` URLs are only supported when the value of the **Type** property is **file**.</span></span> |
|<span data-ttu-id="df7d6-115">Type</span><span class="sxs-lookup"><span data-stu-id="df7d6-115">Type</span></span> |<span data-ttu-id="df7d6-116">Especifica se o recurso que está sendo configurado é um diretório ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="df7d6-116">Specifies whether the resource being configured is a directory or a file.</span></span> <span data-ttu-id="df7d6-117">Defina essa propriedade como **directory** para indicar que o recurso é um diretório.</span><span class="sxs-lookup"><span data-stu-id="df7d6-117">Set this property to **directory** to indicate that the resource is a directory.</span></span> <span data-ttu-id="df7d6-118">Defina-a como **file** para indicar que o recurso é um arquivo.</span><span class="sxs-lookup"><span data-stu-id="df7d6-118">Set it to **file** to indicate that the resource is a file.</span></span> <span data-ttu-id="df7d6-119">O valor padrão é **file**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-119">The default value is **file**.</span></span> |
|<span data-ttu-id="df7d6-120">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="df7d6-120">Contents</span></span> |<span data-ttu-id="df7d6-121">Especifica o conteúdo de um arquivo, como uma cadeia de caracteres específica.</span><span class="sxs-lookup"><span data-stu-id="df7d6-121">Specifies the contents of a file, such as a particular string.</span></span> |
|<span data-ttu-id="df7d6-122">Checksum (soma de verificação)</span><span class="sxs-lookup"><span data-stu-id="df7d6-122">Checksum</span></span> |<span data-ttu-id="df7d6-123">Define o tipo que deve ser usado para determinar se dois arquivos são iguais.</span><span class="sxs-lookup"><span data-stu-id="df7d6-123">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="df7d6-124">Se **Checksum** não for especificado, somente o nome de arquivo ou diretório será usado para comparação.</span><span class="sxs-lookup"><span data-stu-id="df7d6-124">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="df7d6-125">Os valores são: **ctime**, **mtime** ou **md5**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-125">Values are: **ctime**, **mtime**, or **md5**.</span></span> |
|<span data-ttu-id="df7d6-126">Recurse</span><span class="sxs-lookup"><span data-stu-id="df7d6-126">Recurse</span></span> |<span data-ttu-id="df7d6-127">Indica se subdiretórios são incluídos.</span><span class="sxs-lookup"><span data-stu-id="df7d6-127">Indicates if subdirectories are included.</span></span> <span data-ttu-id="df7d6-128">Defina essa propriedade como `$true` para indicar que você deseja que subdiretórios sejam incluídos.</span><span class="sxs-lookup"><span data-stu-id="df7d6-128">Set this property to `$true` to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="df7d6-129">O padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="df7d6-129">The default is `$false`.</span></span> <span data-ttu-id="df7d6-130">Essa propriedade é válida somente quando a propriedade **Type** está definida como **directory**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-130">This property is only valid when the **Type** property is set to **directory**.</span></span> |
|<span data-ttu-id="df7d6-131">Force</span><span class="sxs-lookup"><span data-stu-id="df7d6-131">Force</span></span> |<span data-ttu-id="df7d6-132">Determinadas operações de arquivo (como substituição de um arquivo ou exclusão de um diretório que não esteja vazio) resultarão em erro.</span><span class="sxs-lookup"><span data-stu-id="df7d6-132">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="df7d6-133">O uso da propriedade **Force** substitui esses erros.</span><span class="sxs-lookup"><span data-stu-id="df7d6-133">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="df7d6-134">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="df7d6-134">The default value is `$false`.</span></span> |
|<span data-ttu-id="df7d6-135">Links</span><span class="sxs-lookup"><span data-stu-id="df7d6-135">Links</span></span> |<span data-ttu-id="df7d6-136">Especifica o comportamento desejado para links simbólicos.</span><span class="sxs-lookup"><span data-stu-id="df7d6-136">Specifies the desired behavior for symbolic links.</span></span> <span data-ttu-id="df7d6-137">Defina essa propriedade como **follow** para seguir links simbólicos e agir sobre o destino de links.</span><span class="sxs-lookup"><span data-stu-id="df7d6-137">Set this property to **follow** to follow symbolic links and act on the links target.</span></span> <span data-ttu-id="df7d6-138">Por exemplo, copiar o arquivo em vez do link.</span><span class="sxs-lookup"><span data-stu-id="df7d6-138">For example, copy the file instead of the link.</span></span> <span data-ttu-id="df7d6-139">Defina essa propriedade como **manage** para agir sobre o link.</span><span class="sxs-lookup"><span data-stu-id="df7d6-139">Set this property to **manage** to act on the link.</span></span> <span data-ttu-id="df7d6-140">Por exemplo, copiar o próprio link.</span><span class="sxs-lookup"><span data-stu-id="df7d6-140">For example, copy the link itself.</span></span> <span data-ttu-id="df7d6-141">Defina essa propriedade como **ignore** para ignorar links simbólicos.</span><span class="sxs-lookup"><span data-stu-id="df7d6-141">Set this property to **ignore** to ignore symbolic links.</span></span> |
|<span data-ttu-id="df7d6-142">Agrupar</span><span class="sxs-lookup"><span data-stu-id="df7d6-142">Group</span></span> |<span data-ttu-id="df7d6-143">O nome do **Grupo** que terá permissões para o arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="df7d6-143">The name of the **Group** to have permissions to the file or directory.</span></span> |
|<span data-ttu-id="df7d6-144">Mode</span><span class="sxs-lookup"><span data-stu-id="df7d6-144">Mode</span></span> |<span data-ttu-id="df7d6-145">Especifica as permissões desejadas para o recurso, na notação octal ou simbólica.</span><span class="sxs-lookup"><span data-stu-id="df7d6-145">Specifies the desired permissions for the resource, in octal or symbolic notation.</span></span> <span data-ttu-id="df7d6-146">Por exemplo, **777** ou **rwxrwxrwx**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-146">For example, **777** or **rwxrwxrwx**.</span></span> <span data-ttu-id="df7d6-147">Se usar notação simbólica, não forneça o primeiro caractere que indica o diretório ou arquivo.</span><span class="sxs-lookup"><span data-stu-id="df7d6-147">If using symbolic notation, do not provide the first character which indicates directory or file.</span></span> |
|<span data-ttu-id="df7d6-148">Proprietário</span><span class="sxs-lookup"><span data-stu-id="df7d6-148">Owner</span></span> |<span data-ttu-id="df7d6-149">O nome do grupo que será proprietário do arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="df7d6-149">The name of the group to own the file or directory.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="df7d6-150">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="df7d6-150">Common properties</span></span>

|<span data-ttu-id="df7d6-151">Propriedade</span><span class="sxs-lookup"><span data-stu-id="df7d6-151">Property</span></span> |<span data-ttu-id="df7d6-152">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="df7d6-152">Description</span></span> |
|---|---|
|<span data-ttu-id="df7d6-153">DependsOn</span><span class="sxs-lookup"><span data-stu-id="df7d6-153">DependsOn</span></span> |<span data-ttu-id="df7d6-154">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="df7d6-154">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="df7d6-155">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="df7d6-155">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="df7d6-156">Ensure</span><span class="sxs-lookup"><span data-stu-id="df7d6-156">Ensure</span></span> |<span data-ttu-id="df7d6-157">Determina se é necessário verificar se o arquivo existe.</span><span class="sxs-lookup"><span data-stu-id="df7d6-157">Determines whether to check if the file exists.</span></span> <span data-ttu-id="df7d6-158">Defina essa propriedade como **Present** para garantir que o arquivo exista.</span><span class="sxs-lookup"><span data-stu-id="df7d6-158">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="df7d6-159">Defina-a como **Absent** para garantir que o arquivo não exista.</span><span class="sxs-lookup"><span data-stu-id="df7d6-159">Set it to **Absent** to ensure the file does not exist.</span></span> <span data-ttu-id="df7d6-160">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-160">The default value is **Present**.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="df7d6-161">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="df7d6-161">Additional Information</span></span>

<span data-ttu-id="df7d6-162">Linux e Windows usam diferentes caracteres de quebra de linha em arquivos de texto por padrão; isso pode causar resultados inesperados ao configurar alguns arquivos em um computador Linux com **nxFile**.</span><span class="sxs-lookup"><span data-stu-id="df7d6-162">Linux and Windows use different line break characters in text files by default, and this can cause unexpected results when configuring some files on a Linux computer with **nxFile**.</span></span> <span data-ttu-id="df7d6-163">Há várias maneiras de gerenciar o conteúdo de um arquivo do Linux e, ao mesmo tempo, evitar problemas causados por caracteres de quebra de linha inesperada:</span><span class="sxs-lookup"><span data-stu-id="df7d6-163">There are multiple ways to manage the content of a Linux file while avoiding issues caused by unexpected line break characters:</span></span>

1. <span data-ttu-id="df7d6-164">Copiar o arquivo de uma origem remota (http, https ou ftp)</span><span class="sxs-lookup"><span data-stu-id="df7d6-164">Copy the file from a remote source (http, https, or ftp)</span></span>

   <span data-ttu-id="df7d6-165">Crie um arquivo no Linux com o conteúdo desejado e prepare-o em um servidor da Web ou ftp acessível com os nós que vai configurar.</span><span class="sxs-lookup"><span data-stu-id="df7d6-165">Create a file on Linux with the desired contents, and stage it on a web or ftp server accessible the node(s) you will configure.</span></span> <span data-ttu-id="df7d6-166">Defina a propriedade **SourcePath** no recurso **nxFile** com a URL da web ou do ftp para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="df7d6-166">Define the **SourcePath** property in the **nxFile** resource with the web or ftp URL to the file.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      nxFile resolvConf
      {
         SourcePath = "http://10.185.85.11/conf/resolv.conf"
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
      }
   }
   ```

1. <span data-ttu-id="df7d6-167">Leia o conteúdo do arquivo no script do PowerShell com [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) depois de definir a propriedade **$OFS** para usar o caractere de quebra de linha do Linux.</span><span class="sxs-lookup"><span data-stu-id="df7d6-167">Read the file contents in the PowerShell script with [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) after setting the **$OFS** property to use the Linux line-break character.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      $OFS = "`n"
      $Contents = Get-Content C:\temp\resolv.conf

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = "$Contents"
      }
   }
   ```

1. <span data-ttu-id="df7d6-168">use uma função do PowerShell para substituir as quebras de linha do Windows com caracteres de quebra de linha do Linux.</span><span class="sxs-lookup"><span data-stu-id="df7d6-168">Use a PowerShell function to replace Windows line breaks with Linux line-break characters.</span></span>

   ```powershell
   Function LinuxString($inputStr){
      $outputStr = $inputStr.Replace("`r`n","`n")
      $outputStr += "`n"
      Return $outputStr
   }

   Import-DSCResource -Module nx

   Node $Node
   {
      $Contents = @'
   search contoso.com
   domain contoso.com
   nameserver 10.185.85.11
   '@
       $Contents = LinuxString $Contents

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = $Contents
      }
   }
   ```

## <a name="example"></a><span data-ttu-id="df7d6-169">Exemplo</span><span class="sxs-lookup"><span data-stu-id="df7d6-169">Example</span></span>

<span data-ttu-id="df7d6-170">O exemplo a seguir garante que o diretório `/opt/mydir` exista e que um arquivo com conteúdo especificado exista nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="df7d6-170">The following example ensures that the directory `/opt/mydir` exists, and that a file with specified contents exists this directory.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node {
    nxFile DirectoryExample
    {
        Ensure = "Present"
        DestinationPath = "/opt/mydir"
        Type = "Directory"
    }

    nxFile FileExample
    {
        Ensure = "Present"
        Destinationpath = "/opt/mydir/myfile"
        Contents=@"
#!/bin/bash`necho "hello world"`n
"@
        Mode = "755"
        DependsOn = "[nxFile]DirectoryExample"
    }
}
```
