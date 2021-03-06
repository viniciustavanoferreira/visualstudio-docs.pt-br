---
title: 'Como: Publicar um aplicativo ClickOnce usando o Assistente de publicação | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7ff519416d874462a86f7e615822d15139fc4726
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697630"
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>Como: Publicar um aplicativo ClickOnce usando o assistente de publicação
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para disponibilizar um aplicativo ClickOnce para os usuários, você deve publicá-lo para um compartilhamento de arquivo ou caminho, servidor FTP ou mídia removível. É possível publicar o aplicativo usando o Assistente de Publicação; as propriedades adicionais relacionadas à publicação estão disponíveis na página **Publicar** do **Designer de Projeto**. Para obter mais informações, consulte [publicando aplicativos ClickOnce](../deployment/publishing-clickonce-applications.md).  
  
 Antes de executar o Assistente de Publicação, configure as propriedades de publicação corretamente. Por exemplo, se você deseja designar uma chave para assinar o aplicativo ClickOnce, pode fazer isso na página **Assinatura** do **Designer de Projeto**. Para obter mais informações, consulte [Securing ClickOnce Applications](../deployment/securing-clickonce-applications.md) (Protegendo aplicativos ClickOnce).  
  
> [!NOTE]
> Ao instalar mais de uma versão de um aplicativo usando o ClickOnce, a instalação moverá as versões anteriores do aplicativo para uma pasta chamada Arquivo, no local de publicação especificado. O arquivamento de versões anteriores dessa maneira mantém o diretório de instalação livre de pastas da versão anterior.  
  
> [!NOTE]
> As caixas de diálogo e os comandos do menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da edição ou das configurações ativas. Para alterar as configurações, clique em **Importar e exportar configurações** no menu **Ferramentas**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-publish-to-a-file-share-or-path"></a>Para publicar em um compartilhamento de arquivo ou caminho  
  
1. No **Gerenciador de Soluções**, selecione o projeto do aplicativo.  
  
2. Sobre o **compilar** menu, clique em **Publish**`Projectname`.  
  
    O Assistente de Publicação será exibido.  
  
3. No **onde você deseja publicar o aplicativo?** página, insira um endereço válido do servidor FTP ou um caminho de arquivo válido usando um dos formatos mostrados e, em seguida, clique em **próxima**.  
  
4. Na página **Como os usuários instalarão o aplicativo?**, selecione a localização em que os usuários acessarão para instalar o aplicativo:  
  
   - Se os usuários forem instalar de um site, clique em **De um site** e insira a URL que corresponde ao caminho de arquivo inserido na etapa anterior. Clique em **Avançar**. (Essa opção geralmente é usada ao especificar um endereço FTP no local de publicação. O download direto do FTP não tem suporte. Portanto, é necessário inserir uma URL aqui.)  
  
   - Se os usuários forem instalar o aplicativo diretamente do compartilhamento de arquivos, clique em **De um caminho UNC ou compartilhamento de arquivos** e clique em **Avançar**. (Isso é para locais de publicação do formulário c:\deploy\myapp ou \\\server\myapp.)  
  
   - Se os usuários forem instalar de mídia removível, clique em **De um CD-ROM ou DVD-ROM** e clique em **Avançar**.  
  
5. Na página **O aplicativo estará disponível offline?**, clique na opção adequada:  
  
   - Se você quiser habilitar a execução do aplicativo quando o usuário estiver desconectado da rede, clique em **Sim, este aplicativo estará disponível online ou offline**. Será criado um atalho para o aplicativo no menu **Iniciar**.  
  
   - Se você deseja executar o aplicativo diretamente da localização de publicação, clique em **Não, este aplicativo está disponível apenas online**. Não será criado um atalho para o aplicativo no menu **Iniciar**.  
  
     Clique em **Próximo** para continuar.  
  
6. Clique em **Concluir** para publicar o aplicativo.  
  
    O status da publicação é exibido na área de notificação de status.  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>Publicar para um CD-ROM ou DVD-ROM  
  
1. No **Gerenciador de Soluções**, clique com o botão direito do mouse no projeto de aplicativo e clique em **Propriedades**.  
  
    O **Designer de Projeto** é exibido.  
  
2. Clique na guia **Publicar** para abrir a página **Publicar** no **Designer de Projeto** e clique no botão **Assistente de Publicação**.  
  
    O Assistente de Publicação será exibido.  
  
3. No **onde você deseja publicar o aplicativo?** página, insira o caminho do arquivo ou o local de FTP onde o aplicativo será publicado, por exemplo d:\deploy. Clique em **Avançar** para continuar.  
  
4. Na página **Como os usuários farão a instalação do aplicativo?**, clique em **De um CD-ROM ou DVD-ROM** e clique em **Avançar**.  
  
   > [!NOTE]
   > Se desejar executar a instalação automaticamente quando o CD-ROM for inserido na unidade, abra a página **Publicar** no **Designer de Projeto** e clique no botão **Opções** e, em seguida, no assistente **Opções de Publicação**, selecione **Em instalações com CD, o programa de instalação será iniciado automaticamente quando o CD for inserido**.  
  
5. Ao distribuir o aplicativo em CD-ROM, você poderá desejar fornecer atualizações a partir de um site da Web. Na página **Em que local o aplicativo verificará atualizações?**, escolha uma opção de atualização:  
  
   - Se o aplicativo for verificar atualizações, clique em **O aplicativo verificará atualizações na seguinte localização** e insira a localização em que as atualizações serão postadas. Poderá ser um local de arquivo, um site ou um servidor FTP.  
  
   - Se o aplicativo não for verificar atualizações, clique em **O aplicativo não verificará atualizações**.  
  
     Clique em **Próximo** para continuar.  
  
6. Clique em **Concluir** para publicar o aplicativo.  
  
    O status da publicação é exibido na área de notificação de status.  
  
   > [!NOTE]
   > Após a publicação estar concluída, será necessário utilizar um CD-Rewriter ou DVD-Rewriter para copiar os arquivos do local especificado na etapa 3 para a mídia de CD-ROM ou DVD-ROM.  
  
## <a name="see-also"></a>Consulte também  
 [Segurança e implantação do ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Protegendo aplicativos ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Implantando uma solução do Office usando o ClickOnce](https://msdn.microsoft.com/library/feb516b3-5e4d-449a-9fd2-347d08d90252)
