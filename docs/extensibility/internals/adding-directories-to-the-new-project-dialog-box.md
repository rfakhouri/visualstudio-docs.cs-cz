---
title: Přidávání adresářů do dialogového okna Nový projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c4ad992785fdf8ab5ffdd3faa7043e2a0ee5411b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128075"
---
# <a name="adding-directories-to-the-new-project-dialog-box"></a>Přidávání adresářů do dialogového okna Nový projekt
Když vytvoříte nové typy projektů, také můžete zaregistrovat nový adresář v **nový projekt** dialogové okno pro zobrazení je pro použití jako šablony. Následující příklad kódu vysvětluje, jak zaregistrovat nový adresář, také známé jako uzel. V příkladu je zaregistrovaný vystavené VSPackage CLSID_Package šablony. V důsledku toho, na levé straně **nový projekt** dialogové okno nabízí přidané uzel s názvem dáno Folder_Label_ResID prostředků. Tento prostředek je načten z VSPackage satelitní knihovny DLL.  
  
 **Složky** hodnota představuje identifikátor GUID do složky, ve kterém se zobrazí Folder_Label_ResID uzlu. V příkladu představuje identifikátor GUID **ostatní projekty** složku **typy projektů** podokně **nový projekt** dialogové okno. Pokud **ostatní projekty** chybí hodnota, je štítek nastavený na nejvyšší úrovni.  
  
 Hodnota TemplatesDir Určuje úplnou cestu k adresáři, obsahuje šablony projektu. Tyto soubory mohou být soubory .vsz nebo soubory typické šablony se dají klonovat.  
  
 Pokud zadáte TemplatesLocalizedSubDir, musí být řetězec, který názvy podadresáři TemplatesDir, který obsahuje lokalizované šablony ID prostředku. Protože [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] načte řetězec prostředku z satelitní knihovny DLL Pokud ji máte, každý satelitní knihovny DLL může obsahovat podadresáři jiný název. Hodnota SortPriority určuje řazení prioritu.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Přidávání položek do pro přidání nové položky dialogových oken](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Přidávání adresářů do dialogového okna Přidat novou položku](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)