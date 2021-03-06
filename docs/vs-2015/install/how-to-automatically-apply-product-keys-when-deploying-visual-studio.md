---
title: Como aplicar as chaves de produto automaticamente durante a implantação do Visual Studio 2015 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
caps.latest.revision: 11
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: ec050cf8f365bfae2290593a0c7f215dcb2f39cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186001"
---
# <a name="how-to-automatically-apply-product-keys-when-deploying-visual-studio"></a>Como aplicar as chaves de produto automaticamente durante a implantação do Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obter a documentação mais recente sobre o Visual Studio, confira [Como aplicar as chaves de produto automaticamente durante a implantação do Visual Studio](/visualstudio/install/automatically-apply-product-keys-when-deploying-visual-studio).

É possível aplicar a chave do produto (Product Key) de forma programática como parte de um script usado para automatizar a implantação do Visual Studio 2015. Chaves do produto (Product Keys) podem ser definidas em um dispositivo de forma programática durante a instalação do Visual Studio ou após a conclusão de uma instalação.

## <a name="apply-the-license-during-installation"></a>Aplicar a licença durante a instalação
 Use o parâmetro /ProductKey para aplicar uma chave do produto (Product Key) durante o processo de instalação do Visual Studio. Esse parâmetro de instalação pode ser usado com o parâmetro /Silent para instalar o Visual Studio em um estado já licenciado de um usuário final. Para usar o parâmetro /ProductKey, abra um prompt de comando. Execute o programa de instalação (por exemplo, vs_enterprise.exe ou vs_professional.exe) e defina o parâmetro /ProductKey com uma chave do produto (Product Key) (25 caracteres) sem traços:

 Este é um comando de exemplo para a instalação do Visual Studio 2015 Enterprise com a chave do produto (Product Key) AAAAABBBBBCCCCCDDDDDEEEEEEE:

 `vs_enterprise.exe [any other setup parameters] /ProductKey AAAAABBBBBCCCCCDDDDDDEEEEEE`

## <a name="apply-the-license-after-installation"></a>Aplicar a licença após a instalação
 É possível ativar uma versão instalada do Visual Studio com uma chave do produto (Product Key) usando o utilitário storePID.exe nos computadores de destino no modo sem confirmação. StorePID.exe é um programa utilitário que é instalado com o Visual Studio em **\<drive>:\\\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe**.

 Execute o storePID.exe com privilégios elevados, usando um agente do System Center ou em um prompt de comandos com privilégios elevados, seguido pela chave do produto (Product Key) (incluindo os traços) e o MPC (Código do Produto da Microsoft). Verifique se você incluiu os traços na chave do produto (Product Key).

 `StorePID.exe [product key including the dashes] [MPC]`

 Esta é uma linha de comando de exemplo para a instalação do Visual Studio 2015 Enterprise, que tem o MPC 07060, com uma chave do produto (Product Key) “AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE”:

 `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 07060`

 A seguinte tabela lista os códigos MPC para cada edição do Visual Studio:

|Edição do Visual Studio|MPC|
|---------------------------|---------|
|Visual Studio Enterprise 2015|07060|
|Visual Studio Professional 2015|07062|
|Visual Studio Test Professional 2015|07066|
|Visual Studio Ultimate 2013|06181|
|Visual Studio Premium 2013|06191|
|Visual Studio Professional 2013|06177|
|Visual Studio Test Professional 2013|06194|

Para saber mais sobre como obter uma chave do produto, confira [Como localizar a chave do produto (Product Key) do Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md).

Se o StorePID.exe aplicou a chave do produto (Product Key) com êxito, ele retornará 0. Se ele encontrar erros, retornará um número entre 1 e 6.

## <a name="see-also"></a>Consulte também

- [Instalar o Visual Studio](../install/install-visual-studio-2015.md)