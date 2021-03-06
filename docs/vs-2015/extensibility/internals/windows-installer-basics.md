---
title: Noções básicas do Windows Installer | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4693654e12dc37209cb92e3e2ba95bde8bd13e77
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687674"
---
# <a name="windows-installer-basics"></a>Noções básicas do Windows Installer
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

O Windows Installer instala e desinstala aplicativos ou produtos de software no computador do usuário, executar essas tarefas em unidades chamadas de componentes do Windows Installer (às vezes chamados de WICs ou apenas componentes). Um GUID que identifica cada WIC, que é a unidade básica de instalação e a contagem de referências para as configurações usando o Windows Installer.  
  
 Para obter uma documentação abrangente do Windows Installer, consulte o tópico do SDK da plataforma [Windows Installer](/previous-versions/2kt85ked(v=vs.120)).  
  
## <a name="authoring-a-vspackage"></a>Criação de um VSPackage  
 Windows Installer usa pacotes de instalação, que contêm informações que o Windows Installer precisa para instalar, desinstalar ou reparar um produto e para executar a interface de usuário (UI) de configuração. Cada pacote de instalação inclui um arquivo. msi, que contém um banco de dados de instalação, um fluxo de informações de resumo e fluxos de dados de várias partes da instalação. Para usar o instalador, você deve criar uma instalação. Como o instalador organiza as instalações em torno do conceito de componentes e armazena informações sobre a instalação em um banco de dados relacional, o processo de criação de um pacote de instalação em larga escala envolve as seguintes etapas:  
  
1. Planeje sua configuração de criação para dar suporte a suas estratégias de lado a lado e o controle de versão.  
  
2. Identifica os recursos a serem apresentados aos usuários.  
  
3. Organize o VSPackage e as dependências em componentes.  
  
4. Preencha o banco de dados com informações de instalação.  
  
5. Valide o pacote de instalação.  
  
   Esta documentação está preocupada principalmente com a primeira e terceira etapas do processo. Durante essas etapas você organizar seus recursos de VSPackage em WICs para que você pode estruturar seu controle de versão e preparando estratégia para levar em conta as versões subsequentes do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. As três etapas restantes são abordadas em detalhes na documentação do Windows Installer no SDK da plataforma.  
  
## <a name="key-terms"></a>Principais termos  
 A seguir está as definições dos termos principais relacionadas à tecnologia Windows Installer.  
  
 Recurso  
 Arquivos, chaves do registro, atalhos, ou e assim por diante que pode ser instalado em um computador. Esses recursos são agrupados logicamente em componentes do Windows Installer.  
  
 Component (WIC) do Windows Installer  
 A unidade básica de instalação que representa um agrupamento lógico de recursos relacionados que são instalados e desinstalados como uma unidade. Componentes do Windows Installer são identificados por uma ID exclusiva do componente ou um GUID. Além disso, o Windows Installer mantém sua referência de contagem no nível do WIC. Para obter flexibilidade máxima do controle de versão, inclua não mais de um recurso principal, tal como uma DLL, em um determinado WIC. Observe que, depois de identificar e preencher um WIC, dê a ele um GUID e implantá-lo, você não pode alterar sua composição. Para obter mais informações, consulte [organizando aplicativos em componentes](https://msdn.microsoft.com/library/aa370561.aspx).  
  
 Pacote (pacote de redistribuição)  
 Uma unidade de implantação que consiste em um arquivo. msi e arquivos de origem externa à qual esse arquivo pode apontar. Um pacote contém todas as informações que o Windows Installer precisa para executar a interface do usuário e para instalar ou desinstalar o aplicativo.  
  
 arquivo. msi  
 Um arquivo de armazenamento estruturado em COM que contém as instruções e os dados necessários para instalar um aplicativo. Cada pacote contém pelo menos um arquivo. msi. O arquivo. msi contém o banco de dados do instalador, um fluxo de informações de resumo e, possivelmente, uma ou mais transformações e os arquivos de origem interna. Arquivos a serem instalados podem ser compactados em um gabinete e armazenados em um fluxo no arquivo. msi ou armazenados, compactados ou descompactados, fora do arquivo. msi na mídia de origem. Para obter mais informações, consulte [extensões de arquivos do Windows Installer](https://msdn.microsoft.com/library/aa372842\(VS.85\).aspx).  
  
## <a name="windows-installer-rules-enforcement"></a>Imposição de regras do Windows Installer  
 Dois conjuntos de regras determinam a implantação de recursos por meio de componentes do seu programa de instalação. Um conjunto de regras é mantido pelo instalador do Windows em si, enquanto você deve aplicar o segundo conjunto como autor da instalação.  
  
> [!NOTE]
> A imposição de regras do Windows Installer ocorre somente se você executar uma validação de seu arquivo. msi. No entanto, são evitaram para tratar essas regras como as práticas recomendadas. Para obter mais informações, consulte [validação de um banco de dados de instalação](https://msdn.microsoft.com/library/aa372477\(VS.85\).aspx) e [validação de pacote](https://msdn.microsoft.com/library/aa370569\(VS.85\).aspx).  
  
#### <a name="installer-enforced-rules"></a>Regras aplicadas pelo instalador  
  
- Todos os arquivos em um determinado componente devem ser instalados no mesmo diretório. Por outro lado, os arquivos instalados para pastas diferentes devem pertencer para separar os componentes.  
  
- Pode haver apenas um caminho de chave por componente. O caminho da chave é simplesmente uma arquivo ou chave do registro que representa o componente inteiro.  
  
#### <a name="component-provider-responsibilities"></a>Responsabilidades do provedor de componente  
  
- Quaisquer dois recursos que podem ser enviado separadamente em versões subsequentes devem existir em componentes separados. Recursos devem ser agrupados no mesmo componente somente quando você tiver certeza de que esses recursos nunca serão fornecida separadamente. Na verdade, é recomendável que todos os principais recursos (por exemplo, DLLs) sempre existe no WICs separados. Para obter mais informações, consulte [definindo componentes do instalador](https://msdn.microsoft.com/library/aa368269\(VS.85\).aspx).  
  
- Nenhum recurso com versão nunca deve enviar em mais de um WIC.  
  
## <a name="see-also"></a>Consulte também  
 [O que acontece se as regras de componente são interrompidas?](https://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)
