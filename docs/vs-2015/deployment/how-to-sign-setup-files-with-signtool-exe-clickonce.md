---
title: 'Como: Assinar arquivos com SignTool.exe (ClickOnce) de instalação | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 67dc8e858a8ee87ee9e1fef9d99bf24ea4994960
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68202171"
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>Como: Assinar arquivos de instalação com SignTool.exe (ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode usar o SignTool.exe para assinar um programa de instalação (setup.exe). Esse processo ajuda a garantir que arquivos violados não sejam instalados nos computadores dos usuários finais.  
  
 Por padrão, o ClickOnce tem manifestos e um programa de instalação assinados. No entanto, se você quiser alterar os parâmetros do programa de instalação mais tarde, assine o programa de instalação mais tarde. Se você alterar os parâmetros depois que o programa de instalação for assinado a assinatura é corrompida.  
  
 O procedimento a seguir gera manifestos assinados e um programa de instalação não assinado. A assinatura do ClickOnce está habilitada no Visual Studio para gerar manifestos assinados. O programa de instalação é deixado sem assinatura para que o cliente possa assinar o executável com seu próprio certificado.  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>Para gerar um programa de instalação não assinado e assinar mais tarde  
  
1. No computador de desenvolvimento, instale o certificado com qual você deseja assinar os manifestos.  
  
2. Selecione o projeto no **Gerenciador de Soluções**.  
  
3. No menu **Projeto**, clique em *ProjectName* **Propriedades**.  
  
4. Na página **Assinatura**, desmarque a opção **Assinar os manifestos do ClickOnce**.  
  
5. Na página **Publicar**, clique em **Pré-requisitos**.  
  
6. Verifique se todos os pré-requisitos estão selecionados e clique em **OK**.  
  
7. Na página **Publicar**, verifique as configurações de publicação e clique em **Publicar Agora**.  
  
     A solução publica o manifesto de aplicativo não assinado, o manifesto de implantação não assinado, os arquivos específicos de versão e o programa de instalação não assinado no local da pasta de publicação.  
  
8. Na página **Publicar**, clique em **Pré-requisitos**.  
  
9. Na caixa de diálogo **Pré-requisitos**, desmarque a opção **Criar programa de instalação para instalar os componentes dos pré-requisitos**.  
  
10. Na página **Publicar**, verifique as configurações de publicação e clique em **Publicar Agora**.  
  
     A solução publica o manifesto de aplicativo assinado, o manifesto de implantação assinado, os arquivos específicos de versão e o local da pasta de publicação. O programa de instalação não assinado não é substituído pelo processo de publicação.  
  
11. No site do cliente, abra um prompt de comando.  
  
12. Mude para o diretório que contém o arquivo .exe.  
  
13. Assine o arquivo .exe com o seguinte comando:  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     Por exemplo, para assinar o programa de instalação, use um dos seguintes comandos:  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Como: Assinar novamente os manifestos de aplicativo e implantação](../deployment/how-to-re-sign-application-and-deployment-manifests.md)
