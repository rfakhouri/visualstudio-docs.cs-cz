---
title: Přidávání adresářů do dialogového okna Nový projekt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9d8e68413795b7004542ee312dcb27492e55e7f0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62910779"
---
# <a name="add-directories-to-the-new-project-dialog-box"></a>Přidat adresářů do dialogového okna Nový projekt
Při vytváření nových typů projektů také můžete zaregistrovat nový adresář v **nový projekt** dialogové okno se zobrazí pro použití jako šablony. Následující příklad vysvětluje, jak zaregistrovat nový adresář, označované také jako uzel. V tomto příkladu šablony vystavené sady VSPackage *CLSID_Package*, jsou registrované. V důsledku toho na levé straně **nový projekt** dialogové okno nabízí přidání uzel s názvem určené *Folder_Label_ResID* prostředků. Tento prostředek je načtena z balíčku VSPackage satelitní knihovny DLL.

 **Složky** hodnota představuje GUID složky pod kterým *Folder_Label_ResID* uzel se zobrazí. V tomto příkladu představuje identifikátor GUID **ostatní projekty** složky **typy projektů** podokně **nový projekt** dialogové okno. Pokud **ostatní projekty** chybí hodnota, popisek je umístěn na nejvyšší úrovni.

 `TemplatesDir` Hodnota určuje úplnou cestu adresáře, který obsahuje šablony projektů. Tyto soubory mohou být buď *.vsz* soubory nebo soubory šablon typické ke klonování.

 Pokud zadáte `TemplatesLocalizedSubDir`, musí být ID prostředku řetězce, který pojmenovává podadresáři `TemplatesDir` , který obsahuje lokalizované šablony. Protože [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] načte prostředek řetězce ze satelitní knihovny DLL, máte-li každý satelitní knihovny DLL může obsahovat název jiné podadresáře. `SortPriority` Hodnota určuje prioritu třídění.

```
NoRemove NewProjectTemplates
{
    NoRemove TemplateDirs
  {
    ForceRemove %CLSID_Package%
    {
      ForceRemove /1 = s '#%Folder_Label_ResID%'
      {
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'
        val TemplatesDir = s '%Template_Path%'
        val TemplatesLocalizedSubDir = s '#100'
        val SortPriority = d 1000
      }
    }
  }
}
```

## <a name="see-also"></a>Viz také:
- [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)
- [Přidání položek do dialogových oken přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Přidat adresářů do dialogového okna Přidat novou položku](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)