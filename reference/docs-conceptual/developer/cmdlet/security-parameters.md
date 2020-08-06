---
title: Parâmetros de segurança | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 290905b04547af932182005869b18dc1bc210ca4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786502"
---
# <a name="security-parameters"></a>Parâmetros de segurança

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros usados para fornecer informações de segurança para uma operação, como parâmetros que especificam informações de chave de certificado e de privilégios.

|Parâmetro|Funcionalidade|
|---|---|
|**LCA**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para especificar o nível de proteção de controle de acesso para um catálogo ou para um Uniform Resource Identifier (URI).|
|**CertFile**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome de um arquivo que contém um dos seguintes:<br>-Um certificado x. 509 codificado em base64 ou Distinguished Encoding Rules (DER)<br>-Um arquivo de #12 PKCS (padrões de criptografia de chave pública) que contém pelo menos um certificado e uma chave|
|**CertIssuerName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do emissor de um certificado ou para que o usuário possa especificar uma subcadeia de caracteres.|
|**CertRequestFile**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para especificar o nome de um arquivo que contém uma solicitação de certificado de #10 PKCS codificada em base64 ou DER.|
|**CertSerialNumber**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para especificar o número de série que foi emitido pela autoridade de certificação.|
|**CertStoreLocation**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o local do repositório de certificados. O local normalmente é um caminho de arquivo.|
|**CertSubjectName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o emissor de um certificado ou para que o usuário possa especificar uma subcadeia de caracteres.|
|**CertUsage**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para especificar o uso de chave ou o uso avançado de chave. A chave pode ser representada como uma máscara de bits, um bit, um OID (identificador de objeto) ou uma cadeia de caracteres.|
|**Credencial**<br>Tipo de dados: [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential)|Implemente esse parâmetro para que o cmdlet solicite automaticamente ao usuário um nome de usuário ou senha. Um prompt para ambos será exibido se uma credencial completa não for fornecida diretamente.|
|**CSPName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do provedor de serviços de certificado (CSP).|
|**CSPType**<br>Tipo de dados: inteiro|Implemente esse parâmetro para que o usuário possa especificar o tipo de CSP.|
|**Grupo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma coleção de entidades de acesso. Para obter mais informações, consulte a descrição do parâmetro **principal** .|
|**KeyAlgorithm**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o algoritmo de geração de chave a ser usado para segurança.|
|**KeyContainerName**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o nome do contêiner de chave.|
|**KeyLength da**<br>Tipo de dados: inteiro|Implemente esse parâmetro para que o usuário possa especificar o comprimento da chave em bits.|
|**Operação**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma ação que pode ser executada em um objeto protegido.|
|**Principal**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma entidade identificável exclusiva para acesso.|
|**Privilégio**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o direito que um cmdlet precisa para executar uma operação para uma entidade específica.|
|**Direitos**<br>Tipo de dados: matriz de privilégios|Implemente esse parâmetro para que o usuário possa especificar os direitos que um cmdlet precisa para executar sua operação para uma determinada entrada.|
|**Função**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um conjunto de operações que podem ser executadas por uma entidade.|
|**SaveCred**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro de forma que as credenciais que foram salvas anteriormente pelo usuário serão usadas quando o parâmetro for especificado.|
|**Escopo**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o grupo de objetos protegidos para o cmdlet.|
|**SIDs**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um identificador exclusivo que representa uma entidade de segurança.|
|**Confiável**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os níveis de confiança tenham suporte quando o parâmetro for especificado.|
|**TrustLevel**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para que o usuário possa especificar o nível de confiança que tem suporte. Por exemplo, os valores possíveis incluem Internet, intranet e FullTrust.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
