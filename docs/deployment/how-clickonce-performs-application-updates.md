---
title: Como o ClickOnce executa atualizações de aplicativos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9217558c68d47ef8f2bf34b10db16463ee76f857
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62900010"
---
# <a name="how-clickonce-performs-application-updates"></a>Como o ClickOnce executa atualizações de aplicativos
ClickOnce usa as informações de versão do arquivo especificadas no manifesto de implantação do aplicativo para decidir se deseja atualizar os arquivos do aplicativo. Depois que uma atualização começa, o ClickOnce usa uma técnica chamada *aplicação de patch de arquivo* para evitar o download redundante dos arquivos de aplicativo.

## <a name="file-patching"></a>Aplicação de patch de arquivo
 Ao atualizar um aplicativo, ClickOnce não baixa todos os arquivos para a nova versão do aplicativo, a menos que os arquivos foram alterados. Em vez disso, ele compara as assinaturas de hash dos arquivos especificados no manifesto do aplicativo para o aplicativo atual em relação as assinaturas no manifesto para a nova versão. Se as assinaturas de um arquivo forem diferentes, o ClickOnce baixa a nova versão. Se as assinaturas forem correspondentes, o arquivo não foi alterado de uma versão para a próxima. Nesse caso, o ClickOnce copia o arquivo existente e usa-o na nova versão do aplicativo. Essa abordagem impede que o ClickOnce precisar baixar todo o aplicativo novamente, mesmo que apenas um ou dois arquivos foram alterados.

 Aplicação de patch de arquivo também funciona para assemblies que são baixados sob demanda usando o <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> e <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> métodos.

 Se você usar o Visual Studio para compilar seu aplicativo, ele irá gerar novas assinaturas de hash para todos os arquivos sempre que você recompile o projeto inteiro. Nesse caso, todos os assemblies serão baixados para o cliente, embora apenas alguns assemblies podem ter sido alterado.

 Aplicação de patch de arquivo não funciona para arquivos que são marcados como dados e armazenados no diretório de dados. Eles são sempre baixados independentemente da assinatura de hash do arquivo. Para obter mais informações sobre o diretório de dados, consulte [acessar dados locais e remotos em aplicativos ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).

## <a name="see-also"></a>Consulte também
- [Escolher uma estratégia de atualização do ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)
- [Escolher uma estratégia de implantação do ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)