---
title: Modelo de projeto Web do Django para Python
description: O Visual Studio fornece um modelo abrangente para a criação rápida de aplicativos Web do Django com o Python.
ms.date: 11/12/2018
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 136c03ef11071e5d548e36e45a6a541cffce1469
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62784770"
---
# <a name="django-web-project-template"></a>Modelo de projeto Web Django

O [Django](https://www.djangoproject.com/) é uma estrutura do Python de alto nível projetada para um desenvolvimento da Web rápido, seguro e escalonável. O suporte do Python no Visual Studio fornece vários modelos de projeto para configurar a estrutura de um aplicativo Web baseado em Django. Para usar um modelo no Visual Studio, selecione **Arquivo** > **Novo** > **Projeto,** procure por "Django", e selecione no **Projeto Web de Django em branco,** projeto Web **Django**e modelos **do Projeto Web polls Django.** Confira o [Tutorial – Conheça o Django](learn-django-in-visual-studio-step-01-project-and-solution.md) para obter um passo a passo de todos os modelos.

O Visual Studio fornece o IntelliSense completo para projetos do Django:

- Variáveis de contexto passadas para o modelo:

    ![IntelliSense para variáveis de contexto](media/template-django-intellisense.png)

- Marcação e filtragem para elementos internos e definidos pelo usuário:

    ![IntelliSense para marcas e filtros](media/template-django-intellisense-filter.png)

- Realce de sintaxe para CSS e JavaScript inserido:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

O Visual Studio também fornece [suporte de depuração](debugging-python-in-visual-studio.md) completo para projetos do Django:

![Pontos de interrupção](media/template-django-debugging.png)

É comum que projetos do Django sejam gerenciados por meio do arquivo *manage.py*, que é um pressuposto adotado pelo Visual Studio. Se você parar de usar esse arquivo como o ponto de entrada, basicamente divide o arquivo de projeto. Nesse caso você precisa [recriar o projeto de arquivos existentes](managing-python-projects-in-visual-studio.md#create-a-project-from-existing-files) sem marcá-lo como um projeto do Django.

## <a name="django-management-console"></a>Console de gerenciamento do Django

O console de gerenciamento Django é acessado através de vários comandos no menu **Do Projeto** ou clicando com o botão direito do mouse no projeto no **Solution Explorer**.

- **Abra o Django Shell**: abre um shell no contexto do aplicativo que permite manipular seus modelos:

    ![Resultados do comando Shell Abrir o Django](media/template-django-console-shell.png)

- **Banco de Dados de Sincronização do Django**: executa `manage.py syncdb`em uma janela **interativa**:

    ![Resultado do comando Sincronizar BD do Django](media/template-django-console-sync-db.png)

- **Coletar Estáticos**: executa `manage.py collectstatic --noinput` para copiar todos os arquivos estáticos para o caminho especificado por `STATIC_ROOT` em *settings.py*.

    ![Resultado do comando Coletar Arquivos Estáticos](media/template-django-console-collect-static.png)

- **Validar**: executa `manage.py validate`, que relata os erros de validação nos modelos instalados especificados por `INSTALLED_APPS` em *settings.py*:

    ![Resultado do comando Validar](media/template-django-console-validate.png)

## <a name="see-also"></a>Confira também

- [Tutorial – Conheça o Django](learn-django-in-visual-studio-step-01-project-and-solution.md)
- [Publicar no Serviço de Aplicativo do Azure](publishing-python-web-applications-to-azure-from-visual-studio.md)
