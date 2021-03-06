---
title: Visão geral do cache do ClickOnce | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3d7abeeec4a640119e3089c795ac529a10f8dc09
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84182619"
---
# <a name="clickonce-cache-overview"></a>Visão geral do cache do ClickOnce
Todos os [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativos, sejam eles instalados localmente ou hospedados online, são armazenados no computador cliente em um [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] *cache*de aplicativos. Um [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] cache é uma família de diretórios ocultos no diretório de configurações local da pasta Documents and Settings do usuário atual. Esse cache mantém todos os arquivos do aplicativo, incluindo os assemblies, os arquivos de configuração, as configurações do aplicativo e do usuário e o diretório de dados. O cache também é responsável por migrar o diretório de dados do aplicativo para a versão mais recente. Para obter mais informações sobre migração de dados, consulte [acessando dados locais e remotos em aplicativos ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).

 Ao fornecer um único local para o armazenamento de aplicativos, o [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] assume a tarefa de gerenciar a instalação física de um aplicativo do usuário. O cache também ajuda a isolar aplicativos mantendo os assemblies e arquivos de dados para todos os aplicativos e suas versões distintas separadas uns dos outros. Por exemplo, quando você atualiza um [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativo, essa versão e seus recursos de dados são fornecidos com seus próprios diretórios no cache.

## <a name="cache-storage-quota"></a>Cota de armazenamento em cache
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]os aplicativos hospedados online são restritos na quantidade de espaço que podem ocupar por uma cota que restringe o tamanho do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] cache. O tamanho do cache se aplica a todos os aplicativos online do usuário; um aplicativo online único e parcialmente confiável é limitado a ocupar metade do espaço da cota. Os aplicativos instalados não são limitados pelo tamanho do cache e não contam com relação ao limite de cache. Para todos os [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativos, o cache retém apenas a versão atual e a versão instalada anteriormente.

 Por padrão, os computadores cliente têm 250 MB de armazenamento para [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativos online. Os arquivos de dados não contam para esse limite. Um administrador do sistema pode aumentar ou reduzir essa cota em um determinado computador cliente alterando a chave do registro, **HKEY_CURRENT_USER \software\classes\software\microsoft\windows\currentversion\deployment\onlineappquotainkb**, que é um valor DWORD que expressa o tamanho do cache em kilobytes. Por exemplo, para reduzir o tamanho do cache para 50 MB, você alteraria esse valor para 51200.

## <a name="see-also"></a>Veja também
- [Acesso a dados locais e remotos em aplicativos ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)