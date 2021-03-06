---
title: Status da porta de regra do FxCop
ms.date: 05/21/2019
ms.topic: reference
helpviewer_keywords:
- fxcop rules
- fxcop analyzers, ported rules
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 84b37bce062ec5f1f406bc6ef9f6507399820af9
ms.sourcegitcommit: 596f92fcc84e6f4494178863a66aed85afe0bb08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82189470"
---
# <a name="fxcop-rule-port-status"></a>Status da porta de regra do FxCop

Se você usou anteriormente a análise de código estático no Visual Studio, talvez esteja imaginando quais dessas regras estão disponíveis na implementação atual como [analisadores do FxCop](install-fxcop-analyzers.md). Esta página lista as regras que são portadas, bem como aquelas que não foram portadas e se há planos para portá-las.

## <a name="ported-rules"></a>Regras portadas

A [página de documentação gerada automaticamente](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md) no repositório Roslyn-Analyzers tem a lista mais atualizada de regras que foram modeladas para analisadores do FxCop. Essa página também tem informações adicionais, como se a regra está habilitada por padrão e se tem uma correção de *código*associada. (As[correções de código](../ide/quick-actions.md) são correções de um único clique disponíveis no menu de ícones de lâmpada no Visual Studio.)

A partir da data desta página, a lista de regras do FxCop que foram modeladas para [analisadores de FxCop](install-fxcop-analyzers.md) inclui:

ID da regra | Título
--------|---------
[CA1000](ca1000.md) | Não declarar membros estáticos em tipos genéricos
[CA1001](ca1001.md) | Tipos com campos descartáveis devem ser descartáveis
[CA1003](ca1003.md) | Usar instâncias do manipulador de eventos genérico
[CA1008](ca1008.md) | Enumerações devem ter valor zero
[CA1010](ca1010.md) | Coleções devem implementar uma interface genérica
[CA1012](ca1012.md) | Tipos abstratos não devem ter construtores
[CA1014](ca1014.md) | Marcar assemblies com CLSCompliant
[CA1016](ca1016.md) | Marcar assemblies com a versão do assembly
[CA1017](ca1017.md) | Marcar assemblies com ComVisible
[CA1018](ca1018.md) | Marcar atributos com AttributeUsageAttribute
[CA1019](ca1019.md) | Definir acessadores para argumentos de atributo
[CA1021](ca1021.md) | Evitar parâmetros out
[CA1024](ca1024.md) | Usar propriedades quando apropriado
[CA1027](ca1027.md) | Marcar enumerações com FlagsAttribute
[CA1028](ca1028.md) | O armazenamento de enumeração deve ser Int32
[CA1030](ca1030.md) | Usar eventos quando apropriado
[CA1031](ca1031.md) | Não capturar tipos de exceção geral
[CA1032](ca1032.md) | Implementar construtores de exceção padrão
[CA1033](ca1033.md) | Métodos de interface devem ser chamados por tipos filho
[CA1034](ca1034.md) | Tipos aninhados não devem ser visíveis
[CA1036](ca1036.md) | Substituir métodos em tipos comparáveis
[CA1040](ca1040.md) | Evitar interfaces vazias
[CA1041](ca1041.md) | Fornecer a mensagem ObsoleteAttribute
[CA1043](ca1043.md) | Usar argumento integral ou de cadeia de caracteres para indexadores
[CA1044](ca1044.md) | Propriedades não devem ser somente gravação
[CA1050](ca1050.md) | Declarar tipos em namespaces
[CA1051](ca1051.md) | Não declarar campos de instância visíveis
[CA1052](ca1052.md) | Tipos de detentor estáticos devem ser estáticos ou não herdáveis
[CA1053](ca1053.md) | Tipos de detentor estáticos não devem ter construtores (CA1053 é parte de [CA1052](ca1052.md) para analisadores de FxCop)
[CA1054](ca1054.md) | Parâmetros de URI não devem ser cadeias de caracteres
[CA1055](ca1055.md) | Os valores de retorno de URI não devem ser cadeias de caracteres
[CA1056](ca1056.md) | As propriedades de URI não devem ser cadeias de caracteres
[CA1058](ca1058.md) | Tipos não devem estender determinados tipos base
[CA1060](ca1060.md) | Mover PInvokes para classe de métodos nativos
[CA1061](ca1061.md) | Não ocultar métodos de classe base
[CA1062](ca1062.md) | Validar argumentos de métodos públicos
[CA1063](ca1063.md) | Implementar IDisposable corretamente
[CA1064](ca1064.md) | Exceções devem ser públicas
[CA1065](ca1065.md) | Não acionar exceções em locais inesperados
[CA1066](ca1066.md) | O {0} tipo deve implementar\<IEquatable T> porque ele substitui Equals
[CA1067](ca1067.md) | Substituir Object. Equals (Object) ao implementar\<IEquatable T>
[CA1068](ca1068.md) | Os parâmetros CancellationToken devem vir por último
CA1200 | Evitar o uso de marcas cref com um prefixo
[CA1303](ca1303.md) | Não passar literais como parâmetros localizados
[CA1304](ca1304.md) | Especificar CultureInfo
[CA1305](ca1305.md) | Especificar IFormatProvider
[CA1307](ca1307.md) | Especificar StringComparison
[CA1308](ca1308.md) | Normalizar cadeias de caracteres em maiúsculas
[CA1309](ca1309.md) | Usar comparação de cadeia de caracteres ordinal
[CA1401](ca1401.md) | P/Invokes não devem ser visíveis
[CA1501](ca1501.md) | Evitar herança excessiva
[CA1502](ca1502.md) | Evitar complexidade excessiva
[CA1505](ca1505.md) | Evitar código de difícil manutenção
[CA1506](ca1506.md) | Evitar acoplamento de classes excessivo
[CA1507](ca1507.md) | Usar nameof para expressar nomes de símbolo
[CA1508](ca1508.md) | Evitar código condicional inativo
CA1509 | Entrada inválida no arquivo de especificação de regra de métricas de código
[CA1707](ca1707.md) | Identificadores não devem conter sublinhados
[CA1708](ca1708.md) | Identificadores devem ser diferentes em algo além das maiúsculas e minúsculas
[CA1710](ca1710.md) | Identificadores devem ter um sufixo correto
[CA1711](ca1711.md) | Identificadores não devem ter um sufixo incorreto
[CA1712](ca1712.md) | Não prefixar valores de enumeração com um nome de tipo
[CA1714](ca1714.md) | Enumerações de sinalizador devem ter nomes no plural
[CA1715](ca1715.md) | Identificadores devem ter um prefixo correto
[CA1716](ca1716.md) | Identificadores não devem corresponder a palavras-chave
[CA1717](ca1717.md) | Apenas enumerações FlagsAttribute devem ter nomes no plural
[CA1720](ca1720.md) | O identificador contém o nome do tipo
[CA1721](ca1721.md) | Nomes de propriedades não devem corresponder a métodos get
[CA1724](ca1724.md) | Nomes de tipos não devem corresponder a namespaces
[CA1725](ca1725.md) | Nomes de parâmetros devem corresponder à declaração base
[CA1801](ca1801.md) | Examinar parâmetros não utilizados
[CA1802](ca1802.md) | Usar literais quando apropriado
[CA1806](ca1806.md) | Não ignorar resultados do método
[CA1810](ca1810.md) | Inicializar campos estáticos de tipo de referência em linha
[CA1812](ca1812.md) | Evitar classes internas sem instâncias
[CA1813](ca1813.md) | Evitar atributos não selados
[CA1814](ca1814.md) | Preferir matrizes denteadas a matrizes multidimensionais
[CA1815](ca1815.md) | Substituir equals e o operador equals em tipos de valor
[CA1816](ca1816.md) | Os métodos Dispose devem chamar SuppressFinalize
[CA1819](ca1819.md) | Propriedades não devem retornar matrizes
[CA1820](ca1820.md) | Testar para verificar se há cadeias de caracteres vazias usando o tamanho da cadeia de caracteres
[CA1821](ca1821.md) | Remover finalizadores vazios
[CA1822](ca1822.md) | Marcar membros como estáticos
[CA1823](ca1823.md) | Evitar campos particulares não utilizados
[CA1824](ca1824.md) | Marque assemblies com NeutralResourcesLanguageAttribute
[CA1825](ca1825.md) | Evite as alocações de matriz de comprimento zero.
CA1826 | Não use métodos enumeráveis em coleções indexáveis. Em vez disso, use a coleção diretamente
[CA2000](ca2000.md) | Descartar objetos antes de perder o escopo
[CA2002](ca2002.md) | Não bloquear objetos com identidade fraca
[CA2007](ca2007.md) | Considere chamar ConfigureAwait na tarefa esperada
CA2008 | Não criar tarefas sem passar um TaskScheduler
CA2009 | Não chamar ToImmutableCollection em um valor imutável
CA2010 | Sempre consumir o valor retornado pelos métodos marcados com PreserveSigAttribute
[CA2100](ca2100.md) | Examinar consultas SQL em busca de vulnerabilidades de segurança
[CA2101](ca2101.md) | Especificar marshaling para argumentos de cadeias de caracteres P/Invoke
[CA2119](ca2119.md) | Selar métodos que atendem a interfaces particulares
[CA2153](ca2153.md) | Não capturar exceções de estado corrompidas
[CA2200](ca2200.md) | Relançar para preservar os detalhes da pilha.
[CA2201](ca2201.md) | Não acionar tipos de exceção reservados
[CA2207](ca2207.md) | Inicializar campos estáticos de tipo de valor em linha
[CA2208](ca2208.md) | Criar instância de exceções de argumento corretamente
[CA2211](ca2211.md) | Campos não constantes não devem ser visíveis
[CA2213](ca2213.md) | Campos descartáveis devem ser descartados
[CA2214](ca2214.md) | Não chamar métodos substituíveis em construtores
[CA2216](ca2216.md) | Tipos descartáveis devem declarar o finalizador
[CA2217](ca2217.md) | Não marcar enumerações com FlagsAttribute
[CA2218](ca2218.md) | Substituir GetHashCode ao substituir Equals
[CA2219](ca2219.md) | Não gerar exceções em cláusulas finally
[CA2224](ca2224.md) | Substituir Equals no operador de sobrecarga igual a
[CA2225](ca2225.md) | Sobrecargas de operador têm alternativas nomeadas
[CA2226](ca2226.md) | Operadores devem ter sobrecargas simétricas
[CA2227](ca2227.md) | Propriedades de coleção devem ser somente leitura
[CA2229](ca2229.md) | Implementar construtores de serialização
[CA2231](ca2231.md) | Sobrecarga do operador Equals no tipo de valor de substituição é igual a
[CA2234](ca2234.md) | Passar objetos URI do sistema em vez de cadeias de caracteres
[CA2235](ca2235.md) | Marcar todos os campos não serializáveis
[CA2237](ca2237.md) | Marcar tipos ISerializable com serializável
[CA2241](ca2241.md) | Fornecer argumentos corretos para métodos de formatação
[CA2242](ca2242.md) | Testar para NaN corretamente
[CA2243](ca2243.md) | Literais de cadeias de caracteres de atributo devem ser analisados corretamente
CA2244 | Não duplicar inicializações de elemento indexado
[CA2300](ca2300.md) | Não usar o desserializador BinaryFormatter não seguro
[CA2301](ca2301.md) | Não chamar BinaryFormatter.Deserialize sem antes definir BinaryFormatter.Binder
[CA2302](ca2302.md) | Verificar se o BinaryFormatter.Binder está definido antes de chamar BinaryFormatter.Deserialize
[CA2305](ca2305.md) | Não usar o desserializador inseguro LosFormatter
[CA2310](ca2310.md) | Não usar o desserializador inseguro NetDataContractSerializer
[CA2311](ca2311.md) | Não desserializar sem definir primeiro NetDataContractSerializer.Binder
[CA2312](ca2312.md) | Verificar se NetDataContractSerializer.Binder foi definido antes de desserializar
[CA2315](ca2315.md) | Não usar o desserializador inseguro ObjectStateFormatter
[CA2321](ca2321.md) | Não desserializar com JavaScriptSerializer usando um SimpleTypeResolver
[CA2322](ca2322.md) | Garantir que o JavaScriptSerializer não seja inicializado com SimpleTypeResolver antes de desserializar
[CA3001](ca3001.md) | Examinar código quanto a vulnerabilidades de injeção de SQL
[CA3002](ca3002.md) | Examinar código quanto a vulnerabilidades de XSS
[CA3003](ca3003.md) | Examinar código quanto a vulnerabilidades de injeção de caminho
[CA3004](ca3004.md) | Examinar código quanto a vulnerabilidades de divulgação de informações
[CA3005](ca3005.md) | Examinar código quanto a vulnerabilidades de injeção de LDAP
[CA3006](ca3006.md) | Examinar código quanto a vulnerabilidades de injeção de comando de processo
[CA3007](ca3007.md) | Examinar código quanto a vulnerabilidades de redirecionamento aberto
[CA3008](ca3008.md) | Examinar código quanto a vulnerabilidades de injeção de XPath
[CA3009](ca3009.md) | Examinar código quanto a vulnerabilidades de injeção de XML
[CA3010](ca3010.md) | Examinar código quanto a vulnerabilidades de injeção de XAML
[CA3011](ca3011.md) | Examinar código quanto a vulnerabilidades de injeção de DLL
[CA3012](ca3012.md) | Examinar código quanto a vulnerabilidades de injeção de regex
[CA3061](ca3061.md) | Não adicionar esquema por URL
[CA3075](ca3075.md) | Processamento DTD não seguro em XML
[CA3076](ca3076.md) | Processamento de script XSLT inseguro.
[CA3077](ca3077.md) | Processamento inseguro em design de API, XmlDocument e XmlTextReader
[CA3147](ca3147.md) | Marcar manipuladores de verbo com o token de antifalsificação de validação
[CA5350](ca5350.md) | Não usar algoritmos de criptografia fracos
[CA5351](ca5351.md) | Não usar algoritmos de criptografia desfeitos
[CA5358](ca5358.md) | Não usar modos de criptografia não seguros
CA5359 | Não desabilitar a validação de certificado
CA5360 | Não chamar métodos perigosos na desserialização
[CA5361](ca5361.md) | Não desabilitar o uso do SChannel de criptografia forte
CA5362 | Não se referir à classe serializável Self
[CA5363](ca5363.md) | Não desabilitar a validação de solicitação
[CA5364](ca5364.md) | Não usar protocolos de segurança preteridos
CA5365 | Não desabilitar a verificação de cabeçalho HTTP
CA5366 | Usar XmlReader para XML de leitura de DataSet
CA5367 | Não serializar tipos com campos de ponteiro
CA5368 | Definir ViewStateUserKey para classes derivadas da página
[CA5369](ca5369.md) | Usar XmlReader para desserializar
[CA5370](ca5370.md) | Usar XmlReader para validar o leitor
[CA5371](ca5371.md) | Usar XmlReader para leitura de esquema
[CA5372](ca5372.md) | Usar XmlReader para XPathDocument
[CA5373](ca5373.md) | Não usar a função de derivação de chave obsoleta
CA5374 | Não usar XslTransform
CA5375 | Não usar assinatura de acesso compartilhado da conta
CA5376 | Usar SharedAccessProtocol HttpsOnly
CA5377 | Usar política de acesso no nível do contêiner
[CA5378](ca5378.md) | Não desabilite ServicePointManagerSecurityProtocols
CA5379 | Não usar algoritmo de função de derivação de chave fraca
CA9999 | Incompatibilidade de versão do analisador

## <a name="unported-rules"></a>Regras não portadas

O conjunto de regras que não foram modeladas para [analisadores de FxCop](install-fxcop-analyzers.md) consiste em regras que ainda não estão, mas que ainda [podem ser portadas](#rules-that-may-be-ported), e aquelas que foram preteridas e [não serão portadas](#deprecated-rules).

### <a name="rules-that-may-be-ported"></a>Regras que podem ser portadas

As seguintes regras de análise herdada do FxCop ainda não foram implementadas como analisadores, mas ainda podem ser. Isso pode ser devido a um motivo técnico de bloqueio ou simplesmente que a regra é de prioridade mais baixa. Para obter mais informações sobre o status de porta de cada regra, clique no link na coluna **problema de rastreamento** .

ID da regra | Problema de acompanhamento
--- | ---
[CA1002](ca1002.md) | [https://github.com/dotnet/roslyn-analyzers/issues/369](https://github.com/dotnet/roslyn-analyzers/issues/369)
[CA1004](ca1004.md) | [https://github.com/dotnet/roslyn-analyzers/issues/370](https://github.com/dotnet/roslyn-analyzers/issues/370)
[CA1005](ca1005.md) | [https://github.com/dotnet/roslyn-analyzers/issues/371](https://github.com/dotnet/roslyn-analyzers/issues/371)
[CA1006](ca1006.md) | [https://github.com/dotnet/roslyn-analyzers/issues/372](https://github.com/dotnet/roslyn-analyzers/issues/372)
[CA1007](ca1007.md) | [https://github.com/dotnet/roslyn-analyzers/issues/373](https://github.com/dotnet/roslyn-analyzers/issues/373)
[CA1011](ca1011.md) | [https://github.com/dotnet/roslyn-analyzers/issues/375](https://github.com/dotnet/roslyn-analyzers/issues/375)
[CA1021](ca1021.md) | [https://github.com/dotnet/roslyn-analyzers/issues/377](https://github.com/dotnet/roslyn-analyzers/issues/377)
[CA1023](ca1023.md) | [https://github.com/dotnet/roslyn-analyzers/issues/378](https://github.com/dotnet/roslyn-analyzers/issues/378)
[CA1045](ca1045.md) | [https://github.com/dotnet/roslyn-analyzers/issues/391](https://github.com/dotnet/roslyn-analyzers/issues/391)
[CA1046](ca1046.md) | [https://github.com/dotnet/roslyn-analyzers/issues/392](https://github.com/dotnet/roslyn-analyzers/issues/392)
[CA1047](ca1047.md) | [https://github.com/dotnet/roslyn-analyzers/issues/393](https://github.com/dotnet/roslyn-analyzers/issues/393)
[CA1048](ca1048.md) | [https://github.com/dotnet/roslyn-analyzers/issues/394](https://github.com/dotnet/roslyn-analyzers/issues/394)
[CA1049](ca1049.md) | [https://github.com/dotnet/roslyn-analyzers/issues/395](https://github.com/dotnet/roslyn-analyzers/issues/395)
[CA1057](ca1057.md) | [https://github.com/dotnet/roslyn-analyzers/issues/401](https://github.com/dotnet/roslyn-analyzers/issues/401)
[CA1300](ca1300.md) | [https://github.com/dotnet/roslyn-analyzers/issues/408](https://github.com/dotnet/roslyn-analyzers/issues/408)
[CA1301](ca1301.md) | [https://github.com/dotnet/roslyn-analyzers/issues/409](https://github.com/dotnet/roslyn-analyzers/issues/409)
[CA1306](ca1306.md) | [https://github.com/dotnet/roslyn-analyzers/issues/414](https://github.com/dotnet/roslyn-analyzers/issues/414)
[CA1402](ca1402.md) | [https://github.com/dotnet/roslyn-analyzers/issues/418](https://github.com/dotnet/roslyn-analyzers/issues/418)
[CA1403](ca1403.md) | [https://github.com/dotnet/roslyn-analyzers/issues/419](https://github.com/dotnet/roslyn-analyzers/issues/419)
[CA1404](ca1404.md) | [https://github.com/dotnet/roslyn-analyzers/issues/420](https://github.com/dotnet/roslyn-analyzers/issues/420)
[CA1405](ca1405.md) | [https://github.com/dotnet/roslyn-analyzers/issues/421](https://github.com/dotnet/roslyn-analyzers/issues/421)
[CA1407](ca1407.md) | [https://github.com/dotnet/roslyn-analyzers/issues/423](https://github.com/dotnet/roslyn-analyzers/issues/423)
[CA1408](ca1408.md) | [https://github.com/dotnet/roslyn-analyzers/issues/424](https://github.com/dotnet/roslyn-analyzers/issues/424)
[CA1409](ca1409.md) | [https://github.com/dotnet/roslyn-analyzers/issues/425](https://github.com/dotnet/roslyn-analyzers/issues/425)
[CA1410](ca1410.md) | [https://github.com/dotnet/roslyn-analyzers/issues/426](https://github.com/dotnet/roslyn-analyzers/issues/426)
[CA1411](ca1411.md) | [https://github.com/dotnet/roslyn-analyzers/issues/427](https://github.com/dotnet/roslyn-analyzers/issues/427)
[CA1412](ca1412.md) | [https://github.com/dotnet/roslyn-analyzers/issues/428](https://github.com/dotnet/roslyn-analyzers/issues/428)
[CA1413](ca1413.md) | [https://github.com/dotnet/roslyn-analyzers/issues/429](https://github.com/dotnet/roslyn-analyzers/issues/429)
[CA1414](ca1414.md) | [https://github.com/dotnet/roslyn-analyzers/issues/430](https://github.com/dotnet/roslyn-analyzers/issues/430)
[CA1415](ca1415.md) | [https://github.com/dotnet/roslyn-analyzers/issues/431](https://github.com/dotnet/roslyn-analyzers/issues/431)
[CA1500](ca1500.md) | [https://github.com/dotnet/roslyn-analyzers/issues/432](https://github.com/dotnet/roslyn-analyzers/issues/432)
[CA1600](ca1600.md) | [https://github.com/dotnet/roslyn-analyzers/issues/438](https://github.com/dotnet/roslyn-analyzers/issues/438)
[CA1601](ca1601.md) | [https://github.com/dotnet/roslyn-analyzers/issues/439](https://github.com/dotnet/roslyn-analyzers/issues/439)
[CA1700](ca1700.md) | [https://github.com/dotnet/roslyn-analyzers/issues/440](https://github.com/dotnet/roslyn-analyzers/issues/440)
[CA1704](ca1704.md) | [https://github.com/dotnet/roslyn-analyzers/issues/443](https://github.com/dotnet/roslyn-analyzers/issues/443)
[CA1709](ca1709.md) | [https://github.com/dotnet/roslyn-analyzers/issues/445](https://github.com/dotnet/roslyn-analyzers/issues/445)
[CA1713](ca1713.md) | [https://github.com/dotnet/roslyn-analyzers/issues/449](https://github.com/dotnet/roslyn-analyzers/issues/449)
[CA1719](ca1719.md) | [https://github.com/dotnet/roslyn-analyzers/issues/453](https://github.com/dotnet/roslyn-analyzers/issues/453)
[CA1722](ca1722.md) | [https://github.com/dotnet/roslyn-analyzers/issues/455](https://github.com/dotnet/roslyn-analyzers/issues/455)
[CA1726](ca1726.md) | [https://github.com/dotnet/roslyn-analyzers/issues/458](https://github.com/dotnet/roslyn-analyzers/issues/458)
[CA1804](ca1804.md) | [https://github.com/dotnet/roslyn-analyzers/issues/461](https://github.com/dotnet/roslyn-analyzers/issues/461)
[CA1811](ca1811.md) | [https://github.com/dotnet/roslyn-analyzers/issues/464](https://github.com/dotnet/roslyn-analyzers/issues/464)
[CA1900](ca1900.md) | [https://github.com/dotnet/roslyn-analyzers/issues/474](https://github.com/dotnet/roslyn-analyzers/issues/474)
[CA2001](ca2001.md) | [https://github.com/dotnet/roslyn-analyzers/issues/477](https://github.com/dotnet/roslyn-analyzers/issues/477)
[CA2004](ca2004.md) | [https://github.com/dotnet/roslyn-analyzers/issues/479](https://github.com/dotnet/roslyn-analyzers/issues/479)
[CA2006](ca2006.md) | [https://github.com/dotnet/roslyn-analyzers/issues/480](https://github.com/dotnet/roslyn-analyzers/issues/480)
[CA2109](ca2109.md) | [https://github.com/dotnet/roslyn-analyzers/issues/488](https://github.com/dotnet/roslyn-analyzers/issues/488)
[CA2204](ca2204.md) | [https://github.com/dotnet/roslyn-analyzers/issues/529](https://github.com/dotnet/roslyn-analyzers/issues/529)
[CA2205](ca2205.md) | [https://github.com/dotnet/roslyn-analyzers/issues/530](https://github.com/dotnet/roslyn-analyzers/issues/530)
[CA2212](ca2212.md) | [https://github.com/dotnet/roslyn-analyzers/issues/534](https://github.com/dotnet/roslyn-analyzers/issues/534)
[CA2215](ca2215.md) | [https://github.com/dotnet/roslyn-analyzers/issues/535](https://github.com/dotnet/roslyn-analyzers/issues/535)
[CA2232](ca2232.md) | [https://github.com/dotnet/roslyn-analyzers/issues/545](https://github.com/dotnet/roslyn-analyzers/issues/545)
[CA2236](ca2236.md) | [https://github.com/dotnet/roslyn-analyzers/issues/548](https://github.com/dotnet/roslyn-analyzers/issues/548)
[CA2238](ca2238.md) | [https://github.com/dotnet/roslyn-analyzers/issues/549](https://github.com/dotnet/roslyn-analyzers/issues/549)
[CA2239](ca2239.md) | [https://github.com/dotnet/roslyn-analyzers/issues/550](https://github.com/dotnet/roslyn-analyzers/issues/550)
[CA2240](ca2240.md) | [https://github.com/dotnet/roslyn-analyzers/issues/551](https://github.com/dotnet/roslyn-analyzers/issues/551)

### <a name="deprecated-rules"></a>Regras preteridas

As seguintes regras de análise herdada do FxCop foram preteridas e não serão implementadas como analisadores. Para obter mais informações, você pode pesquisar por ID de regra (por exemplo, **CA1009**) na [página de problemas do GitHub Roslyn-Analyzers](https://github.com/dotnet/roslyn-analyzers/issues?utf8=%E2%9C%93&q=is:issue+label:FxCop-Port).

- [CA1009](ca1009.md)
- [CA1020](ca1020.md)
- [CA1025](ca1025.md)
- [CA1026](ca1026.md)
- [CA1035](ca1035.md)
- [CA1038](ca1038.md)
- [CA1039](ca1039.md)
- [CA1059](ca1059.md)
- [CA1302](ca1302.md)
- [CA1400](ca1400.md)
- [CA1406](ca1406.md)
- [CA1504](ca1504.md)
- [CA1701](ca1701.md)
- [CA1702](ca1702.md)
- [CA1703](ca1703.md)
- [CA1800](ca1800.md)
- [CA1809](ca1809.md)
- [CA1901](ca1901.md)
- [CA1903](ca1903.md)
- [CA2003](ca2003.md)
- [CA2102](ca2102.md)
- [CA2103](ca2103.md)
- [CA2104](ca2104.md)
- [CA2105](ca2105.md)
- [CA2106](ca2106.md)
- [CA2107](ca2107.md)
- [CA2108](ca2108.md)
- [CA2111](ca2111.md)
- [CA2112](ca2112.md)
- [CA2114](ca2114.md)
- [CA2115](ca2115.md)
- [CA2116](ca2116.md)
- [CA2117](ca2117.md)
- [CA2118](ca2118.md)
- [CA2120](ca2120.md)
- [CA2121](ca2121.md)
- [CA2122](ca2122.md)
- [CA2123](ca2123.md)
- [CA2124](ca2124.md)
- [CA2126](ca2126.md)
- [CA2130](ca2130.md)
- [CA2131](ca2131.md)
- [CA2132](ca2132.md)
- [CA2133](ca2133.md)
- [CA2134](ca2134.md)
- [CA2135](ca2135.md)
- [CA2136](ca2136.md)
- [CA2137](ca2137.md)
- [CA2138](ca2138.md)
- [CA2139](ca2139.md)
- [CA2140](ca2140.md)
- [CA2141](ca2141.md)
- [CA2142](ca2142.md)
- [CA2143](ca2143.md)
- [CA2144](ca2144.md)
- [CA2145](ca2145.md)
- [CA2146](ca2146.md)
- [CA2147](ca2147.md)
- [CA2149](ca2149.md)
- [CA2151](ca2151.md)
- [CA2202](ca2202.md)
- [CA2210](ca2210.md)
- [CA2220](ca2220.md)
- [CA2221](ca2221.md)
- [CA2222](ca2222.md) ([justificativa](https://github.com/dotnet/roslyn-analyzers/issues/1378))
- [CA2223](ca2223.md)
- [CA2228](ca2228.md)
- [CA2230](ca2230.md)
- [CA2233](ca2233.md)
- [CA5122](ca5122.md)

## <a name="see-also"></a>Confira também

- [Regras Microsoft. CodeAnalysis. FxCopAnalyzers](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)
