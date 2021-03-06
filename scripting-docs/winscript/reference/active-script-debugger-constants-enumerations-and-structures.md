---
title: Estruturas, enumerações e constantes do depurador de Script ativo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Active Script Debugger structures
- Active Script Debugger enumerations
- Active Script Debugger constants
ms.assetid: b80b9207-fb19-4ee2-85fb-41f8c26e7706
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b287001371b80612a2b09a9672e59aff51309cc9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62997326"
---
# <a name="active-script-debugger-constants-enumerations-and-structures"></a>Constantes, enumerações e estruturas de depurador do script ativo
As seguintes constantes, enumerações e estruturas são usadas pelas interfaces ativas da depuração.  
  
## <a name="constants-enumerations-and-structures"></a>Constantes, Enumerações e Estruturas  
  
|Constantes|Descrição|  
|---------------|-----------------|  
|[Constantes APPBREAKFLAGS](../../winscript/reference/appbreakflags-enumeration.md)|Indica o estado atual da depuração para aplicativos e threads.|  
|[DEBUG_TEXT Constants](../../winscript/reference/debug-text-constants.md)|Sinalizadores de opção usados durante [IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md).|  
|[TEXT_DOC_ATTR Constants](../../winscript/reference/text-doc-attr-constants.md)|Descrevem os atributos do documento.|  
  
|Enumerações|Descrição|  
|------------------|-----------------|  
|[Constantes APPBREAKFLAGS](../../winscript/reference/appbreakflags-enumeration.md)|Indica o estado atual da depuração para aplicativos e threads.|  
|[APPLICATION_NODE_EVENT_FILTER Enumeration](../../winscript/reference/application-node-event-filter-enumeration.md)|Indicam os nós que serão excluídos com um filtro.|  
|[BREAKPOINT_STATE Enumeration](../../winscript/reference/breakpoint-state-enumeration.md)|Indica o estado de um ponto de interrupção.|  
|[BREAKREASON Enumeration](../../winscript/reference/breakreason-enumeration.md)|Indica o que causou a interrupção.|  
|[BREAKRESUMEACTION Enumeration](../../winscript/reference/breakresumeaction-enumeration.md)|Descreve como continuar de um ponto de interrupção.|  
|[DOCUMENTNAMETYPE Enumeration](../../winscript/reference/documentnametype-enumeration.md)|Descreve os tipos para se obter um documento.|  
|[ERRORRESUMEACTION Enumeration](../../winscript/reference/errorresumeaction-enumeration.md)|Descreve como continuar de um erro de execução.|  
|[JS_PROPERTY_ATTRIBUTES Enumeration](../../winscript/reference/js-property-attributes-enumeration.md)|Indica os atributos de uma propriedade.|  
|[JS_PROPERTY_MEMBERS Enumeration](../../winscript/reference/js-property-members-enumeration.md)|Sinaliza para especificar o tipo de informação a ser retornada em uma solicitação para membros de um objeto.|  
|[JsDebugReadMemoryFlags Enumeration](../../winscript/reference/jsdebugreadmemoryflags-enumeration.md)|Sinaliza para especificar o comportamento ao ler a memória.|  
|[SCRIPT_DEBUGGER_OPTIONS Enumeration](../../winscript/reference/script-debugger-options-enumeration.md)|Indica um conjunto de opções ou de recursos que se aplicam ao depurador anexado.|  
|[SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND Enumeration](../../winscript/reference/script-error-debug-exception-thrown-kind-enumeration.md)|Indica o tipo de exceção acionada.|  
|[Constantes SOURCE_TEXT_ATTR](../../winscript/reference/source-text-attr-enumeration.md)|Descrevem os atributos de um único caractere de texto de origem.|  
  
|Estruturas|Descrição|  
|----------------|-----------------|  
|[DebugStackFrameDescriptor Structure](../../winscript/reference/debugstackframedescriptor-structure.md)|Enumera os registros de ativação e mescla saídas de vários enumeradores no mesmo thread.|  
|[JS_NATIVE_FRAME Structure](../../winscript/reference/js-native-frame-structure.md)|Representa um registro de ativação.|  
|[JsDebugPropertyInfo Structure](../../winscript/reference/jsdebugpropertyinfo-structure.md)|Indica informações sobre uma propriedade.|  
|[TEXT_DOCUMENT_ARRAY Structure](../../winscript/reference/text-document-array-structure.md)|Fornece um conjunto de documentos.|