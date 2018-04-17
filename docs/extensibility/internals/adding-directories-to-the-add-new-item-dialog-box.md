---
title: Přidávání do adresáře nové položky dialogové okno Přidat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8d9989e8cf4ec8f0eb714a26e73d89fba339b71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>Přidávání do adresáře přidat novou položku – dialogové okno
Následující příklad kódu ukazuje, jak zaregistrovat novou sadu adresářů pro **přidat novou položku** dialogové okno. Pro adresáře **přidat novou položku** dialogové okno se liší pro každý projekt. Proto jsou registrované adresáře v podklíči projekty v nalezen \<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>Skript registru  
  
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
  
 Hodnota Template_Path Určuje úplnou cestu k adresáři, obsahuje šablony projektu. Tyto šablony může být .vsz soubory nebo soubory Typickým případem šablony se dají klonovat.  
  
 Hodnota SortPriority určuje řazení prioritu.  
  
## <a name="adding-items-to-an-existing-project"></a>Přidávání položek do existujícího projektu  
 Můžete také přidat položky do existujícího projektu. Například [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projektu, můžete přidat položky do \<kořenové > \Program Files\Microsoft Visual Studio \VC#\CSharpProjectItems\LocalProjectItems složky. V takovém případě `%GUID_Project%` je identifikátor GUID pro projekt C# ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}).  
  
 Můžete také rozšířit existující projekt programování podtypem projektu. Pomocí projektu podtypem můžete rozšířit projektu bez nutnosti napsat nový typ projektu. Další informace o projektu podtypů najdete v tématu [projektu podtypů](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Viz také  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Přidávání položek do pro přidání nové položky dialogových oken](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Přidávání adresářů do dialogového okna Nový projekt](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)