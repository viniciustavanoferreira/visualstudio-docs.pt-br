---
title: Exportar uma textura para aplicativos Direct2D e JavaScript
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 241c25fe-764e-4e1b-ad32-b1377dcbb605
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d163aafa8b00ce1d59b1fc7b597ab5ca535a1ee
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "72635505"
---
# <a name="how-to-export-a-texture-for-use-with-direct2d-or-javascript-apps"></a>Como: Exportar uma textura para uso com aplicativos Direct2D ou JavaScript

O Pipeline de conteúdo de imagem pode gerar texturas que são compatíveis com as convenções de renderização internas do Direct2D. Texturas desse tipo são adequadas para serem usadas em aplicativos que usam Direct2D e em aplicativos UWP criados usando JavaScript.

Este documento demonstra essas atividades:

- Configurando a imagem de origem a ser processada pelo Pipeline de conteúdo da imagem.

- Configurando o Pipeline de conteúdo de imagem para gerar uma textura que possa ser usada em um aplicativo Direct2D ou JavaScript.

  - Gerar um arquivo *.dds* compactado em bloco.

  - Gerar alfa pré-multiplicado.

  - Desabilite a geração de mipmap.

## <a name="rendering-conventions-in-direct2d"></a>Convenções de renderização do Direct2D

Texturas que são usadas no contexto do Direct2D devem estar em conformidade com as seguintes convenções de renderização internas do Direct2D:

- O Direct2D implementa a transparência e a translucência usando alfa pré-multiplicado. Texturas usadas com Direct2D devem conter alfa pré-multiplicado, mesmo se a textura não usar transparência ou translucência. Para obter mais informações sobre alfa pré-multiplicado, consulte [Como: Exportar uma textura que tenha Alfa pré-multiplicado](../designers/how-to-export-a-texture-that-has-premultiplied-alpha.md).

- A textura deve ser fornecida no formato *.dds,* utilizando um desses formatos de compressão de blocos:

  - Compactação BC1_UNORM

  - Compactação BC2_UNORM

  - Compactação BC3_UNORM

- Não há suporte para mipmaps.

### <a name="to-create-a-texture-thats-compatible-with-direct2d-rendering-conventions"></a>Para criar uma textura compatível com as convenções de renderização do Direct2D

1. Comece com uma textura básica. Carregue uma imagem existente ou crie uma nova conforme descrito em [Como: Criar uma textura básica](../designers/how-to-create-a-basic-texture.md). Para suportar a compactação de blocos no formato *.dds,* especifique uma textura que tenha uma largura e altura que são múltiplas de quatro tamanhos, por exemplo, 100x100, 128x128 ou 256x192. Como não há suporte para mipmap, a textura não precisa ser quadrada nem ser uma potência de dois de tamanho.

2. Configure o arquivo de textura para que ele seja processado pelo Pipeline de conteúdo de imagem. No **Gerenciador de Soluções**, abra o menu de atalho do arquivo de textura que acabou de criar e selecione **Propriedades**. Na página Propriedades > de **configuração****geral,** defina a propriedade **Item Type** como Image Content **Pipeline**. Verifique se a propriedade **Conteúdo** está definida como **Sim** e se **Excluir do Build** está definido como **Não** e, em seguida, escolha o botão **Aplicar**. A página de propriedades de configuração **Pipeline de Conteúdo de Imagem** é exibida.

3. Defina o formato de saída para um dos formatos de compactação em bloco. Na página **Configuração Propriedades de** > **conteúdo de** > imagem**Pipeline Geral,** defina a propriedade **Compacta** para **BC3_UNORM compactação (/compress:BC3_UNORM)**. Você pode escolher qualquer um dos outros formatos BC1, BC2 ou BC3, dependendo dos seus requisitos. O Direct2D não dá suporte a texturas BC4, BC5, BC6 ou BC7 no momento. Para obter mais informações sobre os diferentes formatos BC, consulte [Compressão de blocos (Direct3D 10)](/windows/desktop/direct3d10/d3d10-graphics-programming-guide-resources-block-compression).

   > [!NOTE]
   > O formato de compactação especificado determina o formato do arquivo que é produzido pelo Pipeline de conteúdo de imagem. Isso é diferente da propriedade **Format** da imagem de origem no Editor de imagens, que determina o formato do arquivo de imagens de origem quando armazenados em disco, ou seja, o *formato de trabalho*. Normalmente, um formato de trabalho compactado não é o desejado.

4. Configure o Pipeline de conteúdo de imagem para gerar uma saída que usa alfa pré-multiplicado. Na página **Configuração Propriedades De** > **conteúdo de imagem Pipeline** > **Geral,** defina a propriedade **Converter para formato alfa pré-multiplicado** como **Sim (/geraralfa pré-multiplicado)**.

5. Configure o pipeline de conteúdo de imagem para não gerar mipmaps. Na página **Configuração Propriedades de** > **conteúdo de imagem Pipeline** > **Geral,** defina a propriedade Gerar **Mips** como **No**.

6. Clique no botão **OK**.

   Quando você cria o projeto, o Pipeline de conteúdo de imagem converte a imagem de origem do formato do trabalho para o formato de saída especificado (a conversão inclui a geração de alfa pré-multiplicado) e o resultado é copiado para o diretório de saída do projeto.
