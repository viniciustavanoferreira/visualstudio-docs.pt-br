---
title: Adicionando diretórios à caixa de diálogo adicionar novos itens | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1d4af79f95c87271e9a10eece6c728daa9a81305
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80710259"
---
# <a name="add-directories-to-the-add-new-item-dialog-box"></a>Adicionar diretórios à caixa de diálogo Adicionar novo item
O exemplo de código a seguir demonstra como registrar um novo conjunto de diretórios para a caixa de diálogo **Adicionar novo item.** Os diretórios para a caixa de diálogo **Adicionar novo item** são diferentes para cada projeto. Portanto, os diretórios são registrados sob a subchave **Projetos,** encontrada no **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects**.

## <a name="registry-script"></a>Script de registro

```
NoRemove Projects
{
  NoRemove %GUID_Project%
  {
    NoRemove AddItemTemplates
    {
      NoRemove TemplateDirs
      {
        ForceRemove %CLSID_Package%
        {
      ForceRemove /1 = s '#%Folder_Label_ResID%'
          {
            val TemplatesDir = s '%Template_Path%'
            val SortPriority = d 2000
          }
        }
      }
    }
  }
}
```

 O `%Template_Path%` valor especifica o caminho completo do diretório que contém os modelos do projeto. Esses modelos podem ser arquivos *.vsz* ou arquivos de modelo prototípicos a serem clonados.

 O `SortPriority` valor especifica uma prioridade de classificação.

## <a name="add-items-to-an-existing-project"></a>Adicionar itens a um projeto existente
 Você também pode adicionar itens a um projeto existente. Por exemplo, [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] para um projeto, você pode adicionar itens à * \<pasta root>\Program Files\Microsoft Visual Studio\VC\\CSharpProjectItems\LocalProjectItems.* Neste caso, `%GUID_Project%` é o GUID para um projeto C# ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}).

 Você também pode estender um projeto existente programando um subtipo de projeto. Com um subtipo de projeto, você pode estender um projeto sem escrever um novo tipo de projeto. Para obter mais informações sobre os subtipos do projeto, consulte [subtipos do Projeto](../../extensibility/internals/project-subtypes.md).

## <a name="see-also"></a>Confira também
- [Registre modelos de projetos e itens](../../extensibility/internals/registering-project-and-item-templates.md)
- [Adicionar itens à caixa de diálogo Adicionar novo item](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Adicionar diretórios à caixa de diálogo Do Novo Projeto](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)
