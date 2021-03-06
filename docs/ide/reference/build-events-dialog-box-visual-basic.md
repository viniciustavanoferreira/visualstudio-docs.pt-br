---
title: Caixa de diálogo de Eventos de Build (Visual Basic)
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb4cd0a46e5ab4cc9c3a9e00773818d536b84891
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "68461443"
---
# <a name="build-events-dialog-box-visual-basic"></a>Caixa de diálogo de Eventos de Build (Visual Basic)

Use a caixa de diálogo **Eventos de Build** para especificar as instruções de configuração de build. Você também pode especificar as condições sob as quais eventos de pré-build ou de pós-build são executados. Para obter mais informações, consulte [Como especificar eventos de build (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

**Linha de comando de evento de pré-compilação**

Especifica comandos serem executados antes do início do build. Para digitar comandos longos, clique em **Editar Pré-Build** para exibir a [Caixa de Diálogo Linha de Comando de Evento de Pré-Build/Evento de Pós-Build](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Eventos de pré-build não serão executados se o projeto estiver atualizado e nenhum build será disparado.

**Linha de comando de eventos pós-compilação**

Especifica comandos a serem executados após o fim do build. Para digitar comandos longos, clique em **Editar Pós-Build** para exibir a caixa de diálogo **Linha de Comando de Evento de Pré-Build/Evento de Pós-Build**.

> [!NOTE]
> Adicione uma instrução `call` antes de todos os comandos pós-build que executam arquivos .bat. Por exemplo, `call C:\MyFile.bat` ou `call C:\MyFile.bat call C:\MyFile2.bat`.

**Executar o evento pós-compilação**

Especifica as condições para o evento de pós-build ser executado, conforme mostrado na tabela a seguir.

|Opção|Result|
|------------|------------|
|**Sempre**|O evento de pós-build será executado independentemente de o build ser bem-sucedido.|
|**Na compilação bem-sucedida**|O evento de pós-build será executado se o build for bem-sucedido. O evento será executado mesmo para um projeto atualizado, desde que o build seja bem-sucedido. Essa é a configuração padrão.|
|**Quando o build atualizar a saída do projeto**|O evento de pós-build só será executado quando o arquivo de saída do compilador (.exe ou .dll) for diferente do arquivo de saída anterior do compilador. Um evento de pós-build não será executado se um projeto for atualizado.|

## <a name="see-also"></a>Confira também

- [Compilar página, designer de projeto (visual básico)](../../ide/reference/compile-page-project-designer-visual-basic.md)
- [Como especificar eventos de build (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Caixa de diálogo de linha de diálogo de linha de diálogo de linha de eventos pré-build/pós-compilação](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)