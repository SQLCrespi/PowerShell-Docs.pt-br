---
title: Diretrizes de desenvolvimento de consultoria | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79c9bcbc-a2eb-4253-a4b8-65ba54ce8d01
caps.latest.revision: 9
ms.openlocfilehash: 980b488800587e31286e2ca2ece924e07f8af3f3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370035"
---
# <a name="advisory-development-guidelines"></a>Diretrizes para desenvolvimento de consultoria

Esta seção descreve as diretrizes que você deve considerar para garantir uma boa experiência de desenvolvimento e de usuário. Às vezes, eles podem se aplicar e, às vezes, podem não.

## <a name="design-guidelines"></a>Diretrizes de design

As diretrizes a seguir devem ser consideradas ao criar cmdlets. Quando encontrar uma diretriz de design que se aplique à sua situação, certifique-se de examinar as diretrizes de código para obter diretrizes semelhantes.

### <a name="support-an-inputobject-parameter-ad01"></a>Suporte a um parâmetro InputObject (AD01)

Como o Windows PowerShell funciona diretamente com os objetos do Microsoft .NET Framework, um objeto .NET Framework geralmente está disponível e corresponde exatamente ao tipo que o usuário precisa para executar uma operação específica. `InputObject` é o nome padrão para um parâmetro que usa tal objeto como entrada. Por exemplo, o cmdlet **Stop-proc** de exemplo no [tutorial StopProc](./stopproc-tutorial.md) define um parâmetro `InputObject` do tipo processo que dá suporte à entrada do pipeline. O usuário pode obter um conjunto de objetos de processo, manipulá-los para selecionar os objetos exatos a serem interrompidos e, em seguida, passá-los para o cmdlet **Stop-proc** diretamente.

### <a name="support-the-force-parameter-ad02"></a>Suporte ao parâmetro Force (AD02)

Ocasionalmente, um cmdlet precisa proteger o usuário de executar uma operação solicitada. Esse cmdlet deve dar suporte a um parâmetro `Force` para permitir que o usuário substitua essa proteção se o usuário tiver permissões para executar a operação.

Por exemplo, o cmdlet [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) normalmente não remove um arquivo somente leitura. No entanto, esse cmdlet dá suporte a um parâmetro `Force` para que um usuário possa forçar a remoção de um arquivo somente leitura. Se o usuário já tiver permissão para modificar o atributo somente leitura e o usuário remover o arquivo, o uso do parâmetro `Force` simplificará a operação. No entanto, se o usuário não tiver permissão para remover o arquivo, o parâmetro `Force` não terá nenhum efeito.

### <a name="handle-credentials-through-windows-powershell-ad03"></a>Tratar credenciais por meio do Windows PowerShell (AD03)

Um cmdlet deve definir um parâmetro `Credential` para representar credenciais. Esse parâmetro deve ser do tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) e deve ser definido usando uma declaração de atributo de credencial. Esse suporte solicita automaticamente ao usuário o nome de usuário, para a senha ou para ambos quando uma credencial completa não é fornecida diretamente. Para obter mais informações sobre o atributo Credential, consulte [declaração de atributo de credencial](./credential-attribute-declaration.md).

### <a name="support-encoding-parameters-ad04"></a>Suporte a parâmetros de codificação (AD04)

Se o cmdlet lê ou grava texto de ou para um formato binário, como gravar ou ler de um arquivo em um sistema de arquivos, o cmdlet deve ter o parâmetro de codificação que especifica como o texto é codificado no formato binário.

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a>Cmdlets de teste devem retornar um booliano (AD05)

Os cmdlets que executam testes em seus recursos devem retornar um tipo [System. Boolean](/dotnet/api/System.Boolean) para o pipeline para que eles possam ser usados em expressões condicionais.

## <a name="code-guidelines"></a>Diretrizes de código

As diretrizes a seguir devem ser consideradas ao escrever o código do cmdlet. Quando encontrar uma diretriz que se aplica à sua situação, certifique-se de examinar as diretrizes de design para obter diretrizes semelhantes.

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a>Seguir as convenções de nomenclatura de classe de cmdlet (AC01)

Seguindo as convenções de nomenclatura padrão, você torna os cmdlets mais detectáveis e ajuda o usuário a entender exatamente o que os cmdlets fazem. Essa prática é particularmente importante para outros desenvolvedores que usam o Windows PowerShell porque os cmdlets são tipos públicos.

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a>Definir um cmdlet no namespace correto

Normalmente, você define a classe para um cmdlet em um namespace .NET Framework que acrescenta ". Commands "para o namespace que representa o produto no qual o cmdlet é executado. Por exemplo, os cmdlets incluídos no Windows PowerShell são definidos no namespace `Microsoft.PowerShell.Commands`.

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a>Nomeie a classe de cmdlet para corresponder ao nome do cmdlet

Ao nomear a classe .NET Framework que implementa um cmdlet, nomeie a classe " *\<Verb > **\<Noun >** \<Command >* ", onde você *substitui os espaços reservados @no__t >* e @no__t *-8Noun >* por o verbo e o substantivo usados para o nome do cmdlet. Por exemplo, o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) é implementado por uma classe chamada `GetProcessCommand`.

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a>Se nenhuma entrada de pipeline substituir o método BeginProcessing (AC02)

Se o cmdlet não aceitar a entrada do pipeline, o processamento deverá ser implementado no método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) . O uso desse método permite que o Windows PowerShell mantenha a ordenação entre cmdlets. O primeiro cmdlet no pipeline sempre retorna seus objetos antes que os cmdlets restantes no pipeline tenham a oportunidade de iniciar o processamento.

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a>Para tratar as solicitações de parada, substitua o método StopProcessing (AC03)

Substitua o método [System. Management. Automation. cmdlet. StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) para que o cmdlet possa manipular o sinal de parada. Alguns cmdlets demoram muito para concluir sua operação e permitem um longo tempo entre chamadas para o tempo de execução do Windows PowerShell, como quando o cmdlet bloqueia o thread em chamadas RPC de longa execução. Isso inclui cmdlets que fazem chamadas para o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) , para o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) e para outros mecanismos de comentários que podem levar muito tempo para serem concluídos . Para esses casos, o usuário pode precisar enviar um sinal de parada para esses cmdlets.

### <a name="implement-the-idisposable-interface-ac04"></a>Implementar a interface IDisposable (AC04)

Se o cmdlet tiver objetos que não são descartados (gravados no pipeline) pelo método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , seu cmdlet poderá exigir descarte de objeto adicional. Por exemplo, se o cmdlet abrir um identificador de arquivo em seu método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) e mantiver o identificador aberto para uso pelo método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , esse identificador terá que ser fechado ao final do processamento.

O tempo de execução do Windows PowerShell nem sempre chama o método [System. Management. Automation. cmdlet. Endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Por exemplo, o método [System. Management. Automation. cmdlet. Endprocessor](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) pode não ser chamado se o cmdlet for cancelado ao meio de sua operação ou se ocorrer um erro de encerramento em qualquer parte do cmdlet. Portanto, a classe .NET Framework para um cmdlet que exige a limpeza de objeto deve implementar o padrão de interface [System. IDisposable](/dotnet/api/System.IDisposable) completo, incluindo o finalizador, para que o tempo de execução do Windows PowerShell possa chamar ambos os [ Métodos System. Management. Automation. cmdlet. noprocessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) e [System. IDisposable. Dispose *](/dotnet/api/System.IDisposable.Dispose) no final do processamento.

### <a name="use-serialization-friendly-parameter-types-ac05"></a>Usar tipos de parâmetro amigável de serialização (AC05)

Para dar suporte à execução de seu cmdlet em computadores remotos, use tipos que possam ser facilmente serializados no computador cliente e, em seguida, alimentados no computador do servidor. Os tipos a seguir são amigáveis para serialização.

Tipos primitivos:

- Byte, SByte, Decimal, Single, Double, Int16, Int32, Int64, UInt16, UInt32 e UInt64.

- Booliano, GUID, Byte [], TimeSpan, DateTime, URI e Version.

- Char, String, XmlDocument.

Tipos internos de rehydratable:

- PSPrimitiveDictionary

- SwitchParameter

- PSListModifier

- PSCredential

- IPAddress, MailAddress

- CultureInfo

- X509Certificate2, X500DistinguishedName

- DirectorySecurity, FileSecurity, RegistrySecurity

Outros tipos:

- SecureString

- Contêineres (listas e dicionários do tipo acima)

### <a name="use-securestring-for-sensitive-data-ac06"></a>Usar SecureString para dados confidenciais (AC06)

Ao lidar com dados confidenciais, sempre use o tipo de dados [System. Security. SecureString](/dotnet/api/System.Security.SecureString) . Isso pode incluir entrada de pipeline para parâmetros, bem como retornar dados confidenciais para o pipeline.

## <a name="see-also"></a>Consulte Também

[Diretrizes de desenvolvimento necessárias](./required-development-guidelines.md)

[Diretrizes de desenvolvimento altamente incentivadas](./strongly-encouraged-development-guidelines.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
