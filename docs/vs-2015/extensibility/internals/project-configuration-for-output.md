---
title: Configuração de projeto para saída | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project configurations, output
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: addd7e8630ce35c6bdbbbb4c063197f75a74c97d
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300684"
---
# <a name="project-configuration-for-output"></a>Configuração de projeto para saída
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Cada configuração pode dar suporte a um conjunto de processos de compilação que produzem itens de saída, como arquivos executáveis ou de recursos. Esses itens de saída são privados para o usuário e podem ser colocados em grupos que vinculam tipos relacionados de saída, como arquivos executáveis (. exe,. dll,. lib) e arquivos de origem (arquivos. idl,. h).  
  
 Os itens de saída podem ser disponibilizados por meio dos métodos <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> e enumerados com os métodos <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>. Quando você deseja agrupar itens de saída, seu projeto também deve implementar a interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup>.  
  
 A construção desenvolvida pela implementação de `IVsOutputGroup` permite que os projetos agrupem saídas de acordo com o uso. Por exemplo, uma DLL pode ser agrupada com o seu banco de dados de programa (PDB).  
  
> [!NOTE]
> Um arquivo PDB contém informações de depuração e é criado quando a opção ' gerar informações de depuração ' é especificada durante a criação de. dll ou. exe. O arquivo. pdb geralmente é gerado para Depurar somente a configuração do projeto.  
  
 O projeto deve retornar o mesmo número de grupos para cada configuração que ele suporta, embora o número de saídas contidas em um grupo possa variar de configuração para configuração. Por exemplo, a DLL do projeto Matt pode incluir mattd. dll e mattd. pdb na configuração de depuração, mas incluir apenas Matt. dll na configuração de varejo.  
  
 Os grupos também têm as mesmas informações de identificador, como nome canônico, nome de exibição e informações de grupo, da configuração para a configuração em um projeto. Essa consistência permite que a implantação e o empacotamento continuem a operar mesmo que as configurações sejam alteradas.  
  
 Os grupos também podem ter uma saída de chave que permite que os atalhos de empacotamento apontem para algo significativo. Qualquer grupo pode estar vazio em uma determinada configuração, portanto, não devem ser feitas suposições sobre o tamanho de um grupo. O tamanho (número de saídas) de cada grupo em qualquer configuração pode ser diferente do tamanho de outro grupo na mesma configuração. Ele também pode ser diferente do tamanho do mesmo grupo em outra configuração.  
  
 ![Gráfico de grupos de saída](../../extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
Grupos de saída  
  
 O uso principal da interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> é fornecer acesso para compilar, implantar e depurar objetos de gerenciamento e permitir que os projetos tenham a liberdade de agrupar saídas. Para obter mais informações sobre o uso dessa interface, consulte [objeto de configuração de projeto](../../extensibility/internals/project-configuration-object.md).  
  
 No diagrama anterior, o grupo criado tem uma saída de chave entre configurações (bD. exe ou b. exe) para que o usuário possa criar um atalho para criado e saber que o atalho funcionará independentemente da configuração implantada. A origem do grupo não tem uma saída de chave, portanto, o usuário não pode criar um atalho para ele. Se o grupo de depuração criado tiver uma saída de chave, mas o grupo de varejo criado não, isso seria uma implementação incorreta. A seguir, então, se qualquer configuração tiver um grupo que não contém nenhuma saída e, como resultado, nenhum arquivo de chave, outras configurações com esse grupo que contêm saídas não poderão ter arquivos de chave. Os editores do instalador pressupõem que nomes canônicos e nomes de exibição de grupos, além da existência de um arquivo de chave, não sejam alterados com base nas configurações.  
  
 Observe que, se um projeto tiver um `IVsOutputGroup` que ele não deseja empacotar ou implantar, é suficiente não colocar essa saída em um grupo. A saída ainda pode ser enumerada normalmente implementando o método <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> que retorna todas as saídas de uma configuração, independentemente do agrupamento.  
  
 Para obter mais informações, consulte a implementação de `IVsOutputGroup` no exemplo de projeto personalizado no [MPF for projects](https://archive.codeplex.com/?p=mpfproj12).  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciando opções de configuração](../../extensibility/internals/managing-configuration-options.md)   
 [Configuração do projeto para a criação de](../../extensibility/internals/project-configuration-for-building.md)   
   de [objeto de configuração de projeto](../../extensibility/internals/project-configuration-object.md)  
 [Configuração da solução](../../extensibility/internals/solution-configuration.md)
