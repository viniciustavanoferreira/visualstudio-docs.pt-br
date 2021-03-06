---
title: Resolvendo assemblies em tempo de design| Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild
ms.assetid: 20dae076-733e-49c1-a2e9-b336757ae21d
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 69f5ba2627e2d659665fa0bd3fbf706f9cad5573
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77632557"
---
# <a name="resolve-assemblies-at-design-time"></a>Resolver assemblies em tempo de design

Quando você adiciona uma referência a um assembly por meio da guia **.NET** da caixa de diálogo **Adicionar Referência**, a referência aponta para um assembly de referência intermediário ou seja, um assembly que contém todas as informações de tipo e a assinatura, mas que não necessariamente contém qualquer código. A guia **.NET** lista conjuntos de referência que correspondem a assembléias em tempo de execução no Quadro .NET. Além disso, ela lista os assemblies de referência que correspondem aos assemblies de runtime nas pastas AssemblyFoldersEx registradas que são usados por terceiros.

## <a name="multi-targeting"></a>Multiplataforma

 O Visual Studio permite que você direcione versões do .NET Framework que são executadas em várias versões do .NET Framework. Quando uma nova versão do .NET Framework é lançada, o Framework pode ser instalado usando um pacote de segmentação, e ele aparecerá automaticamente como um alvo no Visual Studio.

## <a name="how-type-resolution-works"></a>Como funciona a resolução de tipo

 No tempo de execução, a CLR resolve os tipos na montagem olhando no GAC, no diretório *bin* e em qualquer caminho de sondagem. Isso é manipulado pelo carregador de fusão. Mas como o carregador de fusão sabe o que está procurando? Isso depende de uma resolução feita no tempo de design, quando o aplicativo é compilado.

 Durante o build, o compilador resolve tipos de aplicativos usando os assemblies de referência. Nas versões 2.0, 3.0, 3.5, 4, 4.5 e 4.5.1 do .NET Framework, os assemblies de referência são instalados quando o .NET Framework é instalado.

 Os assemblies de referência são fornecidos pelo pacote de direcionamento que acompanha a versão correspondente do SDK do .NET Framework. O Framework em si fornece apenas os assemblies de runtime. Para compilar aplicativos, você precisa instalar o .NET Framework e o SDK do .NET Framework correspondente.

 Quando você usa como destino um .NET Framework específico, o sistema de build resolve todos os tipos usando os assemblies de referência no pacote de destino. No tempo de execução, o carregador de fusão resolve esses mesmos tipos para os conjuntos de tempo de execução, que normalmente estão localizados no GAC.

 Se os assemblies de referência não estiverem disponíveis, o sistema de build resolverá tipos do assembly usando os assemblies de runtime. Já que os assemblies de runtime no GAC não são diferenciados por números de versão secundária, é possível que a resolução seja feita para o assembly errado. Isso poderá ocorrer, por exemplo, se um novo método introduzido no .NET Framework versão 3.5 for referenciado enquanto a versão 3.0 for usada como destino. O build será bem-sucedido e o aplicativo será executado no computador do build, mas falhará quando implantado em um computador que não tenha a versão 3.5 instalada.

 O pacote de direcionamento que agora é fornecido com o SDK do .NET Framework inclui uma lista de todos os assemblies de runtime nessa versão do Framework, denominada lista de redistribuição (redist), impossibilitando ao sistema de build resolver tipos contra a versão errada do assembly.

## <a name="see-also"></a>Confira também
- [Conceitos avançados](../msbuild/msbuild-advanced-concepts.md)
