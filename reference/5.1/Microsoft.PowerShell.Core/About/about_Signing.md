---
description: Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: dc882b4f62a9c08458d9c54ac2defcaad8c7809c
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685956"
---
# <a name="about-signing"></a>Sobre a assinatura

## <a name="short-description"></a>Descrição breve
Explica como assinar scripts para que eles estejam em conformidade com as políticas de execução do PowerShell.

## <a name="long-description"></a>Descrição longa

A política de execução restrita não permite que nenhum script seja executado. As políticas de execução **AllSigned** e **RemoteSigned** impedem que o PowerShell execute scripts que não têm uma assinatura digital.

Este tópico explica como executar scripts selecionados que não são assinados, mesmo que a política de execução seja **RemoteSigned** e como assinar scripts para seu próprio uso.

Para obter mais informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](about_Execution_Policies.md).

## <a name="to-permit-signed-scripts-to-run"></a>Para permitir que scripts assinados sejam executados

Quando você inicia o PowerShell em um computador pela primeira vez, a política de execução **restrita** (o padrão) provavelmente estará em vigor.

A política **restrita** não permite que nenhum script seja executado.

Para localizar a política de execução efetiva em seu computador, digite:

```powershell
Get-ExecutionPolicy
```

Para executar scripts não assinados que você escreve no computador local e os scripts assinados de outros usuários, inicie o PowerShell com a opção Executar como administrador e use o seguinte comando para alterar a política de execução no computador para **RemoteSigned**:

```powershell
Set-ExecutionPolicy RemoteSigned
```

Para obter mais informações, consulte o tópico da ajuda para o `Set-ExecutionPolicy` cmdlet.

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a>Executando scripts não assinados usando a política de execução RemoteSigned

Se a sua política de execução do PowerShell for **RemoteSigned**, o PowerShell não executará scripts não assinados que são baixados da Internet, incluindo scripts não assinados recebidos por email e programas de mensagens instantâneas.

Se você tentar executar um script baixado, o PowerShell exibirá a seguinte mensagem de erro:

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

Antes de executar o script, examine o código para garantir que você confie nele.
Os scripts têm o mesmo efeito que qualquer programa executável.

Para executar um script não assinado, use o cmdlet Unblock-File ou use o procedimento a seguir.

1. Salve o arquivo de script em seu computador.
2. Clique em Iniciar, em Meu Computador e localize o arquivo de script salvo.
3. Clique com o botão direito do mouse no arquivo de script e clique em Propriedades.
4. Clique em Desbloquear.

Se um script que foi baixado da Internet for assinado digitalmente, mas você ainda não tiver optado por confiar no editor, o PowerShell exibirá a seguinte mensagem:

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

Se você confiar no Publicador, selecione "executar uma vez" ou "sempre executar". Se você não confiar no Publicador, selecione "Nunca executar" ou "não executar". Se você selecionar "Nunca executar" ou "sempre executar", o PowerShell não solicitará novamente esse Publicador.

## <a name="methods-of-signing-scripts"></a>Métodos de assinatura de scripts

Você pode assinar os scripts que você escreve e os scripts obtidos de outras fontes. Antes de assinar qualquer script, examine cada comando para verificar se é seguro executá-lo.

Para obter as práticas recomendadas sobre a assinatura de código, consulte [práticas recomendadas de assinatura de código](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).

Para obter mais informações sobre como assinar um arquivo de script, consulte [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).

O `New-SelfSignedCertificate` cmdlet, introduzido no módulo PKI no PowerShell 3,0, cria um certificado autoassinado apropriado para teste. Para obter mais informações, consulte o tópico da ajuda para o cmdlet New-SelfSignedCertificate.

Para adicionar uma assinatura digital a um script, você deve assiná-lo com um certificado de assinatura de código. Dois tipos de certificados são adequados para assinar um arquivo de script:

- Certificados que são criados por uma autoridade de certificação: para uma taxa, uma autoridade de certificação pública verifica sua identidade e fornece um certificado de assinatura de código. Ao comprar seu certificado de uma autoridade de certificação respeitável, você poderá compartilhar seu script com usuários em outros computadores que estejam executando o Windows, pois esses outros computadores confiam na autoridade de certificação.

- Certificados que você cria: você pode criar um certificado autoassinado para o qual seu computador é a autoridade que cria o certificado. Esse certificado é gratuito e permite que você escreva, assine e execute scripts em seu computador. No entanto, um script assinado por um certificado autoassinado não será executado em outros computadores.

Normalmente, você usaria um certificado autoassinado somente para assinar scripts que você escreve para seu próprio uso e para assinar scripts que você obtém de outras fontes que você verificou que são seguros. Não é apropriado para scripts que serão compartilhados, mesmo dentro de uma empresa.

Se você criar um certificado autoassinado, certifique-se de habilitar a proteção forte de chave privada em seu certificado. Isso impede que programas mal-intencionados inscrevam scripts em seu nome. As instruções estão incluídas no final deste tópico.

## <a name="create-a-self-signed-certificate"></a>Crie um certificado autoassinado

Para criar um certificado autoassinado, use o `New-SelfSignedCertificate` cmdlet no módulo PKI. Esse módulo é introduzido no PowerShell 3,0 e está incluído no Windows 8 e no Windows Server 2012. Para obter mais informações, consulte o tópico da ajuda para o `New-SelfSignedCertificate` cmdlet.

Para criar um certificado autoassinado em versões anteriores do Windows, use a ferramenta de criação de certificado `MakeCert.exe` . Essa ferramenta está incluída no SDK do Microsoft .NET (versões 1,1 e posteriores) e no SDK do Microsoft Windows.

Para obter mais informações sobre a sintaxe e as descrições de parâmetro da ferramenta de MakeCert.exe, consulte [ferramenta de criação de certificado (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).

Para usar a ferramenta MakeCert.exe para criar um certificado, execute os comandos a seguir em uma janela de prompt de comando do SDK.

Observação: o primeiro comando cria uma autoridade de certificação local para seu computador. O segundo comando gera um certificado pessoal da autoridade de certificação.

Observação: você pode copiar ou digitar os comandos exatamente como eles aparecem. Nenhuma substituição é necessária, embora você possa alterar o nome do certificado.

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

A ferramenta de MakeCert.exe solicitará uma senha de chave privada. A senha garante que ninguém possa usar ou acessar o certificado sem o seu consentimento.
Crie e insira uma senha que você possa lembrar. Você usará essa senha posteriormente para recuperar o certificado.

Para verificar se o certificado foi gerado corretamente, use o comando a seguir para obter o certificado no repositório de certificados no computador. Você não encontrará um arquivo de certificado no diretório do sistema de arquivos.

No prompt do PowerShell, digite:

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

Esse comando usa o provedor de certificados do PowerShell para exibir informações sobre o certificado.

Se o certificado tiver sido criado, a saída mostrará a **impressão digital** que identifica o certificado em uma exibição semelhante à seguinte:

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a>Assinar um script

Depois de criar um certificado autoassinado, você pode assinar scripts. Se você usar a política de execução **AllSigned** , assinar um script permitirá que você execute o script em seu computador.

O script de exemplo a seguir, `Add-Signature.ps1` , assina um script. No entanto, se você estiver usando a política de execução **AllSigned** , deverá assinar o `Add-Signature.ps1` script antes de executá-lo.

> [!IMPORTANT]
> O script deve ser salvo usando a codificação ASCII ou UTF8NoBOM. Você pode assinar um arquivo de script que usa uma codificação diferente. Mas o script não é executado ou o módulo que contém o script não é importado.

Para usar esse script, copie o texto a seguir em um arquivo de texto e nomeie-o `Add-Signature.ps1` .

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

Para assinar o `Add-Signature.ps1` arquivo de script, digite os seguintes comandos no prompt de comando do PowerShell:

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

Depois que o script for assinado, você poderá executá-lo no computador local. No entanto, o script não será executado em computadores nos quais a política de execução do PowerShell requer uma assinatura digital de uma autoridade confiável. Se você tentar, o PowerShell exibirá a seguinte mensagem de erro:

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

Se o PowerShell exibir essa mensagem quando você executar um script que você não gravou, trate o arquivo como você trataria de qualquer script não assinado. Examine o código para determinar se você pode confiar no script.

## <a name="enable-strong-private-key-protection-for-your-certificate"></a>Habilitar a proteção de chave privada forte para seu certificado

Se você tiver um certificado particular em seu computador, programas mal-intencionados poderão assinar scripts em seu nome, o que autoriza o PowerShell a executá-los.

Para evitar a assinatura automatizada em seu nome, use `Certmgr.exe` o Gerenciador de certificados para exportar seu certificado de assinatura para um `.pfx` arquivo. O Gerenciador de certificados está incluído no SDK do Microsoft .NET, no SDK do Microsoft Windows e no Internet Explorer.

Para exportar o certificado:

1. Inicie o Gerenciador de certificados.
2. Selecione o certificado emitido pela raiz do certificado local do PowerShell.
3. Clique em exportar para iniciar o assistente para exportação de certificados.
4. Selecione "Sim, exportar a chave privada" e clique em Avançar.
5. Selecione "Habilitar proteção forte".
6. Digite uma senha e, em seguida, digite-a novamente para confirmar.
7. Digite um nome de arquivo que tenha a extensão de nome de arquivo. pfx.
8. Clique em Concluir.

Para importar novamente o certificado:

1. Inicie o Gerenciador de certificados.
2. Clique em importar para iniciar o assistente para importação de certificados.
3. Abra o local do arquivo. pfx que você criou durante o processo de exportação.
4. Na página senha, selecione "Habilitar proteção de chave privada forte" e insira a senha que você atribuiu durante o processo de exportação.
5. Selecione o repositório de certificados pessoal.
6. Clique em Concluir.

## <a name="prevent-the-signature-from-expiring"></a>Impedir que a assinatura expire

A assinatura digital em um script é válida até que o certificado de autenticação expire ou desde que um servidor de carimbo de data/hora possa verificar se o script foi assinado enquanto o certificado de autenticação era válido.

Como a maioria dos certificados de assinatura são válidos somente por um ano, o uso de um servidor de carimbo de data/hora garante que os usuários possam usar seu script por muitos anos.

## <a name="see-also"></a>Confira também

[about_Execution_Policies](about_Execution_Policies.md)

[about_Profiles](about_Profiles.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[Introdução à assinatura de código](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))
