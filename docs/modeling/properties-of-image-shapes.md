---
title: Propriedades de formas de imagem
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords:
- Domain-Specific Language, image shape
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: beb401b4056edd8f1edac5e61d02237c60504cd9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748283"
---
# <a name="properties-of-image-shapes"></a>Propriedades de formas de imagem

Você pode usar formas de imagem para especificar como as classes de domínio aparecem em um designer gerado. Defina uma forma de imagem definindo a propriedade `Image` da classe como um arquivo de imagem predefinido. Há suporte para os seguintes formatos:

- .gif

- .jpg

- . jpeg

- .bmp

- .wmf

- . EMF

- .png

Por padrão, os arquivos de recursos do designer, como arquivos de imagem, estão localizados na pasta **recursos** no projeto **DSL** .

Para obter mais informações, consulte [como definir uma linguagem específica de domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [Personalizando e estendendo uma linguagem específica de domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

As formas de imagem têm as propriedades listadas na tabela a seguir.

|propriedade|Descrição|Padrão|
|-|-|-|
|Cor de preenchimento|A cor de preenchimento desta forma.|Branco|
|Preencher modo de gradiente|O modo de gradiente de preenchimento desta forma.|Horizontal|
|Tem pontos de conexão padrão|Se `True`, a forma usará os pontos de conexão superior, inferior, esquerdo e direito no designer gerado.|False|
|Cor do contorno|A cor da estrutura de tópicos desta forma.|Afasta|
|Estilo do contorno tracejado|O estilo de contorno tracejado dessa forma (sólido, traço, ponto, travessão ponto, travessão ponto ponto ou personalizado).|Sólido|
|Espessura do contorno|A espessura da estrutura de tópicos desta forma.|0, 3125|
|Cor do texto|A cor que é usada para decoradores de texto associados a essa forma.|Afasta|
|Modificador de acesso|O modificador de acesso da forma Geometry (público ou interno).|Público|
|Atributos personalizados|Usado para adicionar atributos à classe de código-fonte gerada com base nessa forma.|\<nenhum>|
|Gera derivação dupla|Se `True`, uma classe base e uma classe parcial (para dar suporte à personalização por meio de substituições) serão geradas. Para obter mais informações, consulte [substituindo e estendendo as classes geradas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Tem Construtor personalizado|Se `True`, um construtor personalizado será fornecido no código-fonte. Para obter mais informações, consulte [substituindo e estendendo as classes geradas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modificador de herança|Descreve o tipo de herança da classe de código-fonte gerada a partir da forma de imagem (`none`, `abstract` ou `sealed`).|nenhum|
|Forma da imagem base|A classe base dessa forma.|(nenhum)|
|Name|O nome desta forma.|Nome atual|
|espaço de nome|O namespace que é afiliado a esta forma.|Namespace atual|
|Tipo de dica de ferramenta|O local em que a dica de ferramenta é definida (fixa, variável ou nenhuma). Se for corrigido, o valor da propriedade `Fixed Tooltip Text` será usado como dica de ferramenta; Se for variável, a dica de ferramenta será definida no código personalizado.|nenhum|
|Anotações|Observações informais associadas a esta forma.|\<nenhum>|
|Altura inicial|A altura inicial dessa forma, em polegadas.|1|
|Largura inicial|A largura inicial dessa forma, em polegadas.|1.5|
|Cor de preenchimento exposta como Propriedade<br /><br /> Modo de gradiente de preenchimento exposto<br /><br /> Cor da estrutura de tópicos exposta como Propriedade<br /><br /> Contorno exposto traço estilo como Propriedade<br /><br /> Espessura da estrutura de tópicos exposta como Propriedade<br /><br /> Expõe a cor do texto|Se `True`, o usuário poderá definir a propriedade declarada de uma forma. Para definir isso, clique com o botão direito do mouse na definição de forma e clique em **Adicionar exposto**.|False|
|Descrição|Usado para documentar o designer gerado.|\<nenhum>|
|Nome de Exibição|O nome que será exibido no designer gerado para essa forma.|\<nenhum>|
|Texto de dica de ferramenta fixo|O texto que é usado para uma dica de ferramenta fixa.|\<nenhum>|
|Palavra-chave de ajuda|A palavra-chave usada para indexar a ajuda F1 para este elemento.|\<nenhum>|
|Image|O caminho para o arquivo de imagem usado para esta forma.|\<nenhum>|

## <a name="see-also"></a>Consulte também

- [Glossário das Ferramentas de Linguagem Específica de Domínio](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)