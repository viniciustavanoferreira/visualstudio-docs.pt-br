---
title: Ações de Build
description: Este artigo descreve as diferentes ações de build que podem ser usadas para projetos em C#
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: d55ab6aea15dbad7f1cbd718136fba261dfa1c69
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "74983252"
---
# <a name="build-actions"></a>Ações de Build

Todos os arquivos em um projeto do Visual Studio para Mac têm uma ação de build. Ele controla o que acontece com o arquivo durante um build. Esse comportamento pode ser definido clicando com o botão direito do mouse em qualquer arquivo e navegando até **Ação de Build**, conforme ilustrado abaixo:

![Selecionando ação Compilar build no Gerenciador de Soluções](media/projects-and-solutions-image1.png)

Algumas das ações de build comuns para projetos C# são:

* **None** – O arquivo não faz parte do build de nenhuma forma, sendo incluído no projeto para fácil acesso no IDE.
* **Compile** – O arquivo será passado para o compilador C# como um arquivo de origem.
* **EmbeddedResource** – O arquivo será passado para o compilador C# como um recurso a ser inserido no assembly. O [Assembly.GetManifestResourceStream](/dotnet/api/system.reflection.assembly.getmanifestresourcestream), do namespace `System.Reflection`, pode ser usado para ler o arquivo do assembly.
* **Content** – Para projetos ASP.NET, esses arquivos serão incluídos como parte do site quando ele for implantado. Para projetos Xamarin.iOS e Xamarin.Mac, eles estarão incluídos no lote de aplicativo.

É possível selecionar mais de um arquivo no Gerenciador de Soluções, permitindo que você defina a ação de build para vários arquivos ao mesmo tempo.

Além disso, há ações de build para projetos específicos. Projetos Xamarin.iOS têm a ação de build **BundleResource**, que adiciona o arquivo como parte do pacote de aplicativo. Informações sobre as ações de build específicas do Xamarin.Android podem ser encontradas no guia de [processo de build](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions).

## <a name="see-also"></a>Confira também

- [Ações de build (Visual Studio no Windows)](/visualstudio/ide/build-actions)